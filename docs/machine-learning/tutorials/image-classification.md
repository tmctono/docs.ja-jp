---
title: 'チュートリアル: 事前トレーニング済みの TensorFlow モデルから ML.NET 画像分類モデルを生成する'
description: 既存の TensorFlow モデルから新しい ML.NET 画像分類モデルに知識を転移する方法について説明します。 TensorFlow モデルは、画像を 1,000 個のカテゴリに分類するためにトレーニングされました。 ML.NET モデルでは、転移学習を利用して、さらに少ない数のカテゴリに画像を分類します。
ms.date: 09/30/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
author: natke
ms.author: nakersha
ms.openlocfilehash: 8ae966330ca85722c72c92e26363d99c7d9de3e7
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698643"
---
# <a name="tutorial-generate-an-mlnet-image-classification-model-from-a-pre-trained-tensorflow-model"></a><span data-ttu-id="b774c-105">チュートリアル: 事前トレーニング済みの TensorFlow モデルから ML.NET 画像分類モデルを生成する</span><span class="sxs-lookup"><span data-stu-id="b774c-105">Tutorial: Generate an ML.NET image classification model from a pre-trained TensorFlow model</span></span>

<span data-ttu-id="b774c-106">既存の TensorFlow モデルから新しい ML.NET 画像分類モデルに知識を転移する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b774c-106">Learn how to transfer the knowledge from an existing TensorFlow model into a new ML.NET image classification model.</span></span>

<span data-ttu-id="b774c-107">TensorFlow モデルは、画像を 1,000 個のカテゴリに分類するためにトレーニングされました。</span><span class="sxs-lookup"><span data-stu-id="b774c-107">The TensorFlow model was trained to classify images into a thousand categories.</span></span> <span data-ttu-id="b774c-108">ML.NET モデルでは、パイプラインで TensorFlow モデルの一部を利用し、モデルをトレーニングし、画像を 3 つのカテゴリに分類しています。</span><span class="sxs-lookup"><span data-stu-id="b774c-108">The ML.NET model makes use of part of the TensorFlow model in its pipeline to train a model to classify images into 3 categories.</span></span>

<span data-ttu-id="b774c-109">[画像分類](https://en.wikipedia.org/wiki/Outline_of_object_recognition)モデルを最初からトレーニングするには、数百万のパラメーター、大量のラベル付きトレーニング データ、膨大な量の計算リソース (数百時間の GPU) を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b774c-109">Training an [Image Classification](https://en.wikipedia.org/wiki/Outline_of_object_recognition) model from scratch requires setting millions of parameters, a ton of labeled training data and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="b774c-110">最初からカスタム モデルをトレーニングするほど効果的ではありませんが、転移学習を使用すると、何千もの画像と何百万ものラベル付き画像を使用し、カスタマイズされたモデルを短時間 (GPU が搭載されていないマシンで 1 時間以内) で構築できます。</span><span class="sxs-lookup"><span data-stu-id="b774c-110">While not as effective as training a custom model from scratch, transfer learning allows you to shortcut this process by working with thousands of images vs. millions of labeled images and build a customized model fairly quickly (within an hour on a machine without a GPU).</span></span> <span data-ttu-id="b774c-111">このチュートリアルでは、1 ダースのトレーニング画像のみを使用して、そのプロセスをさらにスケールダウンします。</span><span class="sxs-lookup"><span data-stu-id="b774c-111">This tutorial scales that process down even further, using only a dozen training images.</span></span>

<span data-ttu-id="b774c-112">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b774c-112">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="b774c-113">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="b774c-113">Understand the problem</span></span>
> * <span data-ttu-id="b774c-114">事前トレーニング済みの TensorFlow モデルを ML.NET パイプラインに組み込む</span><span class="sxs-lookup"><span data-stu-id="b774c-114">Incorporate the pre-trained TensorFlow model into the ML.NET pipeline</span></span>
> * <span data-ttu-id="b774c-115">ML.NET モデルのトレーニングと評価</span><span class="sxs-lookup"><span data-stu-id="b774c-115">Train and evaluate the ML.NET model</span></span>
> * <span data-ttu-id="b774c-116">テスト画像を分類する</span><span class="sxs-lookup"><span data-stu-id="b774c-116">Classify a test image</span></span>

<span data-ttu-id="b774c-117">このチュートリアルのソース コードは [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) リポジトリで確認できます。</span><span class="sxs-lookup"><span data-stu-id="b774c-117">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span> <span data-ttu-id="b774c-118">既定では、このチュートリアルの .NET プロジェクトの構成は .NET Core 2.2 を対象としています。</span><span class="sxs-lookup"><span data-stu-id="b774c-118">Note that by default, the .NET project configuration for this tutorial targets .NET core 2.2.</span></span>

## <a name="what-is-transfer-learning"></a><span data-ttu-id="b774c-119">転移学習とは何か</span><span class="sxs-lookup"><span data-stu-id="b774c-119">What is transfer learning?</span></span>

<span data-ttu-id="b774c-120">転移学習は、1 つの問題を解決し、それを別の関連する問題に適用するときに得た知識を使用するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="b774c-120">Transfer learning is the process of using knowledge gained while solving one problem and applying it to a different but related problem.</span></span>

<span data-ttu-id="b774c-121">このチュートリアルでは、TensorFlow モデル (画像を 1,000 個のカテゴリに分類するようにトレーニング済み) の一部を、画像を 3 つのカテゴリに分類する ML.NET モデルで使用します。</span><span class="sxs-lookup"><span data-stu-id="b774c-121">For this tutorial, you use part of a TensorFlow model - trained to classify images into a thousand categories - in an ML.NET model that classifies images into 3 categories.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b774c-122">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b774c-122">Prerequisites</span></span>

* <span data-ttu-id="b774c-123">[Visual Studio 2017 15.6 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)が ".NET Core クロスプラット フォーム開発" とともにインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="b774c-123">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="b774c-124">Microsoft.ML 1.3.1 Nuget パッケージ</span><span class="sxs-lookup"><span data-stu-id="b774c-124">Microsoft.ML 1.3.1 Nuget package</span></span>
* <span data-ttu-id="b774c-125">Microsoft.ML.ImageAnalytics 1.3.1 Nuget パッケージ</span><span class="sxs-lookup"><span data-stu-id="b774c-125">Microsoft.ML.ImageAnalytics 1.3.1 Nuget package</span></span>
* <span data-ttu-id="b774c-126">Microsoft.ML.TensorFlow 1.3.1 Nuget パッケージ</span><span class="sxs-lookup"><span data-stu-id="b774c-126">Microsoft.ML.TensorFlow 1.3.1 Nuget package</span></span>

* [<span data-ttu-id="b774c-127">チュートリアル資産ディレクトリの .ZIP ファイル</span><span class="sxs-lookup"><span data-stu-id="b774c-127">The tutorial assets directory .ZIP file</span></span>](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)

* [<span data-ttu-id="b774c-128">InceptionV1 機械学習モデル</span><span class="sxs-lookup"><span data-stu-id="b774c-128">The InceptionV1 machine learning model</span></span>](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-right-machine-learning-task"></a><span data-ttu-id="b774c-129">適切な機械学習タスクを選択する</span><span class="sxs-lookup"><span data-stu-id="b774c-129">Select the right machine learning task</span></span>

### <a name="deep-learning"></a><span data-ttu-id="b774c-130">ディープ ラーニング</span><span class="sxs-lookup"><span data-stu-id="b774c-130">Deep learning</span></span>

<span data-ttu-id="b774c-131">[ディープ ラーニング](https://en.wikipedia.org/wiki/Deep_learning)は、Computer Vision や音声認識などの分野に革命を起こしている Machine Learning のサブセットです。</span><span class="sxs-lookup"><span data-stu-id="b774c-131">[Deep learning](https://en.wikipedia.org/wiki/Deep_learning) is a subset of Machine Learning, which is revolutionizing areas like Computer Vision and Speech Recognition.</span></span>

<span data-ttu-id="b774c-132">ディープ ラーニング モデルは、複数の学習レイヤーを含む多数の[ラベル付きデータ](https://en.wikipedia.org/wiki/Labeled_data)と[ニューラル ネットワーク](https://en.wikipedia.org/wiki/Artificial_neural_network)を使用してトレーニングされます。</span><span class="sxs-lookup"><span data-stu-id="b774c-132">Deep learning models are trained by using large sets of [labeled data](https://en.wikipedia.org/wiki/Labeled_data) and [neural networks](https://en.wikipedia.org/wiki/Artificial_neural_network) that contain multiple learning layers.</span></span> <span data-ttu-id="b774c-133">ディープ ラーニング:</span><span class="sxs-lookup"><span data-stu-id="b774c-133">Deep learning:</span></span>

* <span data-ttu-id="b774c-134">Computer Vision などの一部のタスクでより効果的に機能します。</span><span class="sxs-lookup"><span data-stu-id="b774c-134">Performs better on some tasks like Computer Vision.</span></span>
* <span data-ttu-id="b774c-135">大量のトレーニング データが必要です。</span><span class="sxs-lookup"><span data-stu-id="b774c-135">Requires huge amounts of training data.</span></span>

<span data-ttu-id="b774c-136">画像分類は、画像を次のようなカテゴリに自動的に分類することができる一般的な機械学習タスクです。</span><span class="sxs-lookup"><span data-stu-id="b774c-136">Image Classification is a common Machine Learning task that allows us to automatically classify images into categories such as:</span></span>

* <span data-ttu-id="b774c-137">画像から人の顔を検出するかどうか。</span><span class="sxs-lookup"><span data-stu-id="b774c-137">Detecting a human face in an image or not.</span></span>
* <span data-ttu-id="b774c-138">猫と犬の検出。</span><span class="sxs-lookup"><span data-stu-id="b774c-138">Detecting cats vs. dogs.</span></span>

 <span data-ttu-id="b774c-139">または、次の画像のように、画像が食品、おもちゃ、または電化製品のいずれであるかを判断する場合。</span><span class="sxs-lookup"><span data-stu-id="b774c-139">Or as in the following images, determining if an image is a(n)  food, toy, or appliance:</span></span>

<span data-ttu-id="b774c-140">![ピザの画像](./media/image-classification/220px-Pepperoni_pizza.jpg)
![テディ ベアの画像](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![トースターの画像](./media/image-classification/193px-Broodrooster.jpg)</span><span class="sxs-lookup"><span data-stu-id="b774c-140">![pizza image](./media/image-classification/220px-Pepperoni_pizza.jpg)
![teddy bear image](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![toaster image](./media/image-classification/193px-Broodrooster.jpg)</span></span>

>[!Note]
> <span data-ttu-id="b774c-141">上の画像は Wikimedia Commons に属し、次のように属性が付けられています。</span><span class="sxs-lookup"><span data-stu-id="b774c-141">The preceding images belong to Wikimedia Commons and are attributed as follows:</span></span>
>
> * <span data-ttu-id="b774c-142">"220px-Pepperoni_pizza.jpg" パブリック ドメイン、 https://commons.wikimedia.org/w/index.php?curid=79505 、</span><span class="sxs-lookup"><span data-stu-id="b774c-142">"220px-Pepperoni_pizza.jpg" Public Domain, https://commons.wikimedia.org/w/index.php?curid=79505,</span></span>
> * <span data-ttu-id="b774c-143">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" By [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - 自己撮影、CC BY-SA 2.0、 https://commons.wikimedia.org/w/index.php?curid=48166 。</span><span class="sxs-lookup"><span data-stu-id="b774c-143">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" By [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Self-photographed, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.</span></span>
> * <span data-ttu-id="b774c-144">"193px-Broodrooster.jpg" By [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - 自分の作品、CC BY-SA 3.0、 https://commons.wikimedia.org/w/index.php?curid=27403</span><span class="sxs-lookup"><span data-stu-id="b774c-144">"193px-Broodrooster.jpg" By [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Own work, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403</span></span>

<span data-ttu-id="b774c-145">`Inception model` は、画像を 1,000 個のカテゴリに分類するようにトレーニングされていますが、このチュートリアルでは、画像をより小さなカテゴリ セットにのみ分類する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b774c-145">The `Inception model` is trained to classify images into a thousand categories, but for this tutorial, you need to classify images in a smaller category set, and only those categories.</span></span> <span data-ttu-id="b774c-146">`transfer learning` の `transfer` 部分を入力します。</span><span class="sxs-lookup"><span data-stu-id="b774c-146">Enter the `transfer` part of `transfer learning`.</span></span> <span data-ttu-id="b774c-147">`Inception model` の画像を認識および分類する能力をカスタム画像分類器の新しい限られたカテゴリに転移ことができます。</span><span class="sxs-lookup"><span data-stu-id="b774c-147">You can transfer the `Inception model`'s ability to recognize and classify images to the new limited categories of your custom image classifier.</span></span>

* <span data-ttu-id="b774c-148">食品</span><span class="sxs-lookup"><span data-stu-id="b774c-148">Food</span></span>
* <span data-ttu-id="b774c-149">おもちゃ</span><span class="sxs-lookup"><span data-stu-id="b774c-149">Toy</span></span>
* <span data-ttu-id="b774c-150">アプライアンス</span><span class="sxs-lookup"><span data-stu-id="b774c-150">Appliance</span></span>

<span data-ttu-id="b774c-151">このチュートリアルでは、TensorFlow の [Inception モデル](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) ディープ ラーニング モデルを使用します。これは、`ImageNet` データセットに対してトレーニングされた、よく使われる画像認識モデルです。</span><span class="sxs-lookup"><span data-stu-id="b774c-151">This tutorial uses the TensorFlow [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip) deep learning model, a popular image recognition model trained on the `ImageNet` dataset.</span></span> <span data-ttu-id="b774c-152">TensorFlow モデルでは、画像全体を "傘"、"ジャージー"、"食器洗い機" などの 1,000 個のクラスに分類します。</span><span class="sxs-lookup"><span data-stu-id="b774c-152">The TensorFlow model classifies entire images into a thousand classes, such as “Umbrella”, “Jersey”, and “Dishwasher”.</span></span>

<span data-ttu-id="b774c-153">`Inception model` は何千種類もの画像に対して事前にトレーニングされているため、画像の識別に必要な[画像の特徴](https://en.wikipedia.org/wiki/Feature_(computer_vision))が内部に含まれています。</span><span class="sxs-lookup"><span data-stu-id="b774c-153">Because the `Inception model` has already been pre trained on thousands of different images, internally it contains the [image features](https://en.wikipedia.org/wiki/Feature_(computer_vision)) needed for image identification.</span></span> <span data-ttu-id="b774c-154">モデルでこれらの内部画像機能を利用して、はるかに少数のクラスで新しいモデルをトレーニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="b774c-154">We can make use of these internal image features in the model to train a new model with far fewer classes.</span></span>

<span data-ttu-id="b774c-155">次の図に示すように、.NET Core または .NET Framework アプリケーションに ML.NET NuGet パッケージへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="b774c-155">As shown in the following diagram, you add a reference to the ML.NET NuGet packages in your .NET Core or .NET Framework applications.</span></span> <span data-ttu-id="b774c-156">内部的には、既存のトレーニング済み `TensorFlow` モデル ファイルを読み込むコードを作成できるネイティブ `TensorFlow` ライブラリが ML.NET には含まれ、参照されています。</span><span class="sxs-lookup"><span data-stu-id="b774c-156">Under the covers, ML.NET includes and references the native `TensorFlow` library that allows you to write code that loads an existing trained `TensorFlow` model file.</span></span>

![TensorFlow 変換 ML.NET Arch 図](./media/image-classification/tensorflow-mlnet.png)

### <a name="multiclass-classification"></a><span data-ttu-id="b774c-158">多クラス分類</span><span class="sxs-lookup"><span data-stu-id="b774c-158">Multiclass classification</span></span>

<span data-ttu-id="b774c-159">TensorFlow Inception モデルを使用して、従来の機械学習アルゴリズムの入力に適した特徴を抽出したら、ML.NET の[多クラス分類器](../resources/tasks.md#multiclass-classification)を追加します。</span><span class="sxs-lookup"><span data-stu-id="b774c-159">After using the TensorFlow inception model to extract features suitable as input for a classical machine learning algorithm, we add an ML.NET [multi-class classifier](../resources/tasks.md#multiclass-classification).</span></span>

<span data-ttu-id="b774c-160">この場合に使用される特定のトレーナーは、[多項ロジスティック回帰アルゴリズム](https://en.wikipedia.org/wiki/Multinomial_logistic_regression)です。</span><span class="sxs-lookup"><span data-stu-id="b774c-160">The specific trainer used in this case is the [multinomial logistic regression algorithm](https://en.wikipedia.org/wiki/Multinomial_logistic_regression).</span></span>

<span data-ttu-id="b774c-161">このトレーナーに実装されているアルゴリズムは、多数の特徴を持つ問題 (画像データに対して機能するディープ ラーニング モデルのケース) に適しています。</span><span class="sxs-lookup"><span data-stu-id="b774c-161">The algorithm implemented by this trainer performs well on problems with a large number of features, which is the case for a deep learning model operating on image data.</span></span>

### <a name="data"></a><span data-ttu-id="b774c-162">データ</span><span class="sxs-lookup"><span data-stu-id="b774c-162">Data</span></span>

<span data-ttu-id="b774c-163">データ ソースは 2 つあります。`.tsv` ファイルと画像ファイルです。</span><span class="sxs-lookup"><span data-stu-id="b774c-163">There are two data sources: the `.tsv` file, and the image files.</span></span>  <span data-ttu-id="b774c-164">`tags.tsv` ファイルには 2 つの列があります。最初の列は `ImagePath` と定義され、2 番目の列は画像に対応する `Label` です。</span><span class="sxs-lookup"><span data-stu-id="b774c-164">The `tags.tsv` file contains two columns: the first one is defined as `ImagePath` and the second one is the `Label` corresponding to the image.</span></span> <span data-ttu-id="b774c-165">次のファイル例にはヘッダー行がなく、次のような内容です。</span><span class="sxs-lookup"><span data-stu-id="b774c-165">The following example file doesn't have a header row, and looks like this:</span></span>

<!-- markdownlint-disable MD010 -->
```tsv
broccoli.jpg    food
pizza.jpg   food
pizza2.jpg  food
teddy2.jpg  toy
teddy3.jpg  toy
teddy4.jpg  toy
toaster.jpg appliance
toaster2.png    appliance
```
<!-- markdownlint-enable MD010 -->

<span data-ttu-id="b774c-166">トレーニングとテストの画像は、zip ファイルでダウンロードする資産フォルダー内にあります。</span><span class="sxs-lookup"><span data-stu-id="b774c-166">The training and testing images are located in the assets folders that you'll download in a zip file.</span></span> <span data-ttu-id="b774c-167">これらの画像は Wikimedia Commons に属します。</span><span class="sxs-lookup"><span data-stu-id="b774c-167">These images belong to Wikimedia Commons.</span></span>
> <span data-ttu-id="b774c-168">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208)、無料メディア リポジトリ。*</span><span class="sxs-lookup"><span data-stu-id="b774c-168">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), the free media repository.*</span></span> <span data-ttu-id="b774c-169">2018 年 10 月 17 日 10:48 に以下から取得: https://commons.wikimedia.org/wiki/Pizza https://commons.wikimedia.org/wiki/Toaster https://commons.wikimedia.org/wiki/Teddy_bear</span><span class="sxs-lookup"><span data-stu-id="b774c-169">Retrieved 10:48, October 17, 2018 from: https://commons.wikimedia.org/wiki/Pizza https://commons.wikimedia.org/wiki/Toaster https://commons.wikimedia.org/wiki/Teddy_bear</span></span>

## <a name="setup"></a><span data-ttu-id="b774c-170">セットアップ</span><span class="sxs-lookup"><span data-stu-id="b774c-170">Setup</span></span>

### <a name="create-a-project"></a><span data-ttu-id="b774c-171">プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="b774c-171">Create a project</span></span>

1. <span data-ttu-id="b774c-172">"TransferLearningTF" という **.NET Core Console アプリケーション**を作成します。</span><span class="sxs-lookup"><span data-stu-id="b774c-172">Create a **.NET Core Console Application** called "TransferLearningTF".</span></span>

1. <span data-ttu-id="b774c-173">**Microsoft.ML NuGet パッケージ**をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b774c-173">Install the **Microsoft.ML NuGet Package**:</span></span>

    * <span data-ttu-id="b774c-174">ソリューション エクスプローラーで、プロジェクトを右クリックし、 **[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b774c-174">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span>
    * <span data-ttu-id="b774c-175">[パッケージ ソース] として "nuget.org" を選択し、[参照] タブを選択し、"**Microsoft.ML**" を検索します。</span><span class="sxs-lookup"><span data-stu-id="b774c-175">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**.</span></span>
    * <span data-ttu-id="b774c-176">**[バージョン]** ドロップダウンをクリックし、一覧から **1.3.1** パッケージを選択し、 **[インストール]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="b774c-176">Click on the **Version** drop-down, select the **1.3.1** package in the list, and select the **Install** button.</span></span>
    * <span data-ttu-id="b774c-177">**[変更のプレビュー]** ダイアログで **[OK]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="b774c-177">Select the **OK** button on the **Preview Changes** dialog.</span></span>
    * <span data-ttu-id="b774c-178">一覧表示されているパッケージのライセンス条項に同意する場合は、 **[ライセンスへの同意]** ダイアログで **[同意する]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="b774c-178">Select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>
    * <span data-ttu-id="b774c-179">**Microsoft.ML.ImageAnalytics v1.3.1** と **Microsoft.ML.TensorFlow v1.3.1** について、これらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b774c-179">Repeat these steps for **Microsoft.ML.ImageAnalytics v1.3.1** and **Microsoft.ML.TensorFlow v1.3.1**.</span></span>

### <a name="download-assets"></a><span data-ttu-id="b774c-180">資産をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="b774c-180">Download assets</span></span>

1. <span data-ttu-id="b774c-181">[プロジェクト資産ディレクトリの zip ファイル](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)をダウンロードし、展開します。</span><span class="sxs-lookup"><span data-stu-id="b774c-181">Download [The project assets directory zip file](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip), and unzip.</span></span>

1. <span data-ttu-id="b774c-182">`assets` ディレクトリを *TransferLearningTF* プロジェクト ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="b774c-182">Copy the `assets` directory into your *TransferLearningTF* project directory.</span></span> <span data-ttu-id="b774c-183">このディレクトリとそのサブディレクトリには、このチュートリアルに必要なデータ ファイルとサポート ファイル (次の手順でダウンロードして追加する Inception モデルを除く) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b774c-183">This directory and its subdirectories contain the data and support files (except for the Inception model, which you'll download and add in the next step) needed for this tutorial.</span></span>

1. <span data-ttu-id="b774c-184">[Inception モデル](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)をダウンロードして展開します。</span><span class="sxs-lookup"><span data-stu-id="b774c-184">Download the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), and unzip.</span></span>

1. <span data-ttu-id="b774c-185">`inception5h` ディレクトリの内容をコピーし、*TransferLearningTF* プロジェクトの `assets/inputs-train/inception` ディレクトリに展開します。</span><span class="sxs-lookup"><span data-stu-id="b774c-185">Copy the contents of the `inception5h` directory just unzipped into your *TransferLearningTF* project `assets/inputs-train/inception` directory.</span></span> <span data-ttu-id="b774c-186">次の画像に示すように、このディレクトリには、このチュートリアルに必要なモデルと追加のサポート ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b774c-186">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![Inception ディレクトリの内容](./media/image-classification/inception-files.png)

1. <span data-ttu-id="b774c-188">ソリューション エクスプローラーで、資産ディレクトリとサブディレクトリ内の各ファイルを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b774c-188">In Solution Explorer, right-click each of the files in the asset directory and subdirectories and select **Properties**.</span></span> <span data-ttu-id="b774c-189">**[詳細設定]** で、 **[出力ディレクトリにコピー]** の値を **[新しい場合はコピーする]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="b774c-189">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="b774c-190">クラスを作成してパスを定義する</span><span class="sxs-lookup"><span data-stu-id="b774c-190">Create classes and define paths</span></span>

1. <span data-ttu-id="b774c-191">次に示す追加の `using` ステートメントを *Program.cs* ファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="b774c-191">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddUsings)]

1. <span data-ttu-id="b774c-192">`Main` メソッドのすぐ上にある行に次のコードを追加して、資産のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b774c-192">Add the following code to the line right above the `Main` method to specify the asset paths:</span></span>

    [!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareGlobalVariables)]

1. <span data-ttu-id="b774c-193">入力データと予測のためにクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b774c-193">Create classes for your input data, and predictions.</span></span>

    [!code-csharp[DeclareImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareImageData)]

    <span data-ttu-id="b774c-194">`ImageData` は、入力画像データ クラスであり、次の <xref:System.String> フィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="b774c-194">`ImageData` is the input image data class and has the following <xref:System.String> fields:</span></span>

    * <span data-ttu-id="b774c-195">`ImagePath` には、画像ファイル名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b774c-195">`ImagePath` contains the image file name.</span></span>
    * <span data-ttu-id="b774c-196">`Label` には、画像ラベルの値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b774c-196">`Label` contains a value for the image label.</span></span>

1. <span data-ttu-id="b774c-197">`ImagePrediction` のプロジェクトに新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="b774c-197">Add a new class to your project for `ImagePrediction`:</span></span>

    [!code-csharp[DeclareImagePrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareImagePrediction)]

    <span data-ttu-id="b774c-198">`ImagePrediction` は、画像予測クラスであり、次のフィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="b774c-198">`ImagePrediction` is the image prediction class and has the following fields:</span></span>

    * <span data-ttu-id="b774c-199">`Score` には、指定した画像分類の信頼度が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b774c-199">`Score` contains the confidence percentage for a given image classification.</span></span>
    * <span data-ttu-id="b774c-200">`PredictedLabelValue` には、予測された画像分類ラベルの値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b774c-200">`PredictedLabelValue` contains a value for the predicted image classification label.</span></span>

    <span data-ttu-id="b774c-201">`ImagePrediction` は、モデルがトレーニングされた後に、予測に使用されるクラスです。</span><span class="sxs-lookup"><span data-stu-id="b774c-201">`ImagePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="b774c-202">これには画像パスの `string` (`ImagePath`) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b774c-202">It has a `string` (`ImagePath`) for the image path.</span></span> <span data-ttu-id="b774c-203">`Label` はモデルの再利用とトレーニングに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b774c-203">The `Label` is used to reuse and train the model.</span></span> <span data-ttu-id="b774c-204">`PredictedLabelValue` は予測と評価の際に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b774c-204">The `PredictedLabelValue` is used during prediction and evaluation.</span></span> <span data-ttu-id="b774c-205">評価では、トレーニング データを含む入力、予測された値、およびモデルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b774c-205">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="b774c-206">Main で変数を初期化する</span><span class="sxs-lookup"><span data-stu-id="b774c-206">Initialize variables in Main</span></span>

1. <span data-ttu-id="b774c-207">新しいインスタンスの `MLContext` を使用して `mlContext` 変数を初期化します。</span><span class="sxs-lookup"><span data-stu-id="b774c-207">Initialize the `mlContext` variable with a new instance of `MLContext`.</span></span>  <span data-ttu-id="b774c-208">`Main` メソッドの `Console.WriteLine("Hello World!")` 行を、次のコードで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="b774c-208">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

    [!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CreateMLContext)]

    <span data-ttu-id="b774c-209">[MLContext クラス](xref:Microsoft.ML.MLContext)は、すべての ML.NET 操作の開始点で、`mlContext` を初期化することで、モデル作成ワークフローのオブジェクト間で共有できる新しい ML.NET 環境が作成されます。</span><span class="sxs-lookup"><span data-stu-id="b774c-209">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="b774c-210">これは Entity Framework における `DBContext` と概念的には同じです。</span><span class="sxs-lookup"><span data-stu-id="b774c-210">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="create-a-struct-for-inception-model-parameters"></a><span data-ttu-id="b774c-211">Inception モデル パラメーターの構造体を作成する</span><span class="sxs-lookup"><span data-stu-id="b774c-211">Create a struct for Inception model parameters</span></span>

1. <span data-ttu-id="b774c-212">Inception モデルには、渡す必要があるパラメーターがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="b774c-212">The Inception model has several parameters you need to pass in.</span></span> <span data-ttu-id="b774c-213">次のコードを使用して、`Main()` メソッドの直後に、パラメーター値をフレンドリ名にマップする構造体を作成します。</span><span class="sxs-lookup"><span data-stu-id="b774c-213">Create a struct to map the parameter values to friendly names with the following code, just after the `Main()` method:</span></span>

    [!code-csharp[InceptionSettings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a><span data-ttu-id="b774c-214">表示ユーティリティ メソッドを作成する</span><span class="sxs-lookup"><span data-stu-id="b774c-214">Create a display utility method</span></span>

<span data-ttu-id="b774c-215">画像データとそれに関連する予測を複数回表示するので、画像と予測結果の表示を処理する表示ユーティリティ メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="b774c-215">Since you'll display the image data and the related predictions more than once, create a display utility method to handle displaying the image and prediction results.</span></span>

1. <span data-ttu-id="b774c-216">`InceptionSettings` 構造体の直後に、次のコードを使用して `DisplayResults()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="b774c-216">Create the `DisplayResults()` method, just after the `InceptionSettings` struct, using the following code:</span></span>

    ```csharp
    private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
    {

    }
    ```

1. <span data-ttu-id="b774c-217">`DisplayResults` メソッドの本体を入力します。</span><span class="sxs-lookup"><span data-stu-id="b774c-217">Fill in the body of the `DisplayResults` method:</span></span>

    [!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPredictions)]

### <a name="create-a-tsv-file-utility-method"></a><span data-ttu-id="b774c-218">.tsv ファイル ユーティリティ メソッドを作成する</span><span class="sxs-lookup"><span data-stu-id="b774c-218">Create a .tsv file utility method</span></span>

1. <span data-ttu-id="b774c-219">`DisplayResults()` メソッドの直後に、次のコードを使用して `ReadFromTsv()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="b774c-219">Create the `ReadFromTsv()` method, just after the `DisplayResults()` method, using the following code:</span></span>

    ```csharp
    public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
    {

    }
    ```

1. <span data-ttu-id="b774c-220">`ReadFromTsv` メソッドの本体を入力します。</span><span class="sxs-lookup"><span data-stu-id="b774c-220">Fill in the body of the `ReadFromTsv` method:</span></span>

    [!code-csharp[ReadFromTsv](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTsv)]

    <span data-ttu-id="b774c-221">このコードでは、`tags.tsv` ファイルを解析して、ファイルパスを `ImagePath` プロパティの画像ファイル名に追加し、それと `Label` を `ImageData` オブジェクトに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="b774c-221">The code parses through the `tags.tsv` file to add the file path to the image file name for the `ImagePath` property and load it and the `Label` into an `ImageData` object.</span></span>

### <a name="create-a-method-to-make-a-prediction"></a><span data-ttu-id="b774c-222">予測を行うメソッドを作成する</span><span class="sxs-lookup"><span data-stu-id="b774c-222">Create a method to make a prediction</span></span>

1. <span data-ttu-id="b774c-223">`DisplayResults()` メソッドの直前に、次のコードを使用して `ClassifySingleImage()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="b774c-223">Create the `ClassifySingleImage()` method, just before the `DisplayResults()` method, using the following code:</span></span>

    ```csharp
    public static void ClassifySingleImage(MLContext mlContext, ITransformer model)
    {

    }
    ```

1. <span data-ttu-id="b774c-224">1 つの `ImagePath` の完全修飾パスと画像ファイル名を含む `ImageData` オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b774c-224">Create an `ImageData` object that contains the fully qualified path and image file name for the single `ImagePath`.</span></span> <span data-ttu-id="b774c-225">`ClassifySingleImage()` メソッドの次の行として、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="b774c-225">Add the following code as the next  lines in the `ClassifySingleImage()` method:</span></span>

    [!code-csharp[LoadImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadImageData)]

1. <span data-ttu-id="b774c-226">次のコードを `ClassifySingleImage` メソッドの次の行として追加して、1 つの予測を作成します。</span><span class="sxs-lookup"><span data-stu-id="b774c-226">Make a single prediction, by adding the following code as the next line in the `ClassifySingleImage` method:</span></span>

    [!code-csharp[PredictSingle](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#PredictSingle)]

    <span data-ttu-id="b774c-227">予測を取得するには、[Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b774c-227">To get the prediction, use the [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) method.</span></span> <span data-ttu-id="b774c-228">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) は、データの 1 つのインスタンスに対して予測を実行できる便利な API です。</span><span class="sxs-lookup"><span data-stu-id="b774c-228">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="b774c-229">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) はスレッド セーフではありません。</span><span class="sxs-lookup"><span data-stu-id="b774c-229">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="b774c-230">シングル スレッド環境またはプロトタイプ環境で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b774c-230">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="b774c-231">運用環境でパフォーマンスとスレッド セーフを向上させるには、`PredictionEnginePool` サービスを使用します。これにより、アプリケーション全体で使用するできる [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) オブジェクトの [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="b774c-231">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="b774c-232">ASP.NET Core Web API で `PredictionEnginePool` を使用する方法については、[こちらのガイド](https://docs.microsoft.com/en-us/dotnet/machine-learning/how-to-guides/serve-model-web-api-ml-net#register-predictionenginepool-for-use-in-the-application)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b774c-232">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](https://docs.microsoft.com/en-us/dotnet/machine-learning/how-to-guides/serve-model-web-api-ml-net#register-predictionenginepool-for-use-in-the-application)</span></span>

    > [!NOTE]
    > <span data-ttu-id="b774c-233">`PredictionEnginePool` サービスの拡張機能は、現在プレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="b774c-233">`PredictionEnginePool` service extension is currently in preview.</span></span>

1. <span data-ttu-id="b774c-234">`ClassifySingleImage()` メソッドの次のコード行として予測結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="b774c-234">Display the prediction result as the next line of code in the `ClassifySingleImage()` method:</span></span>

   [!code-csharp[DisplayPrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPrediction)]

## <a name="construct-the-mlnet-model-pipeline"></a><span data-ttu-id="b774c-235">ML.NET モデルのパイプラインを構築する</span><span class="sxs-lookup"><span data-stu-id="b774c-235">Construct the ML.NET model pipeline</span></span>

<span data-ttu-id="b774c-236">ML.NET モデルのパイプラインは推定器のチェーンです。</span><span class="sxs-lookup"><span data-stu-id="b774c-236">An ML.NET model pipeline is a chain of estimators.</span></span> <span data-ttu-id="b774c-237">パイプラインの構築中に実行は発生しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b774c-237">Note that no execution happens during pipeline construction.</span></span> <span data-ttu-id="b774c-238">推定器オブジェクトは作成されますが、実行されません。</span><span class="sxs-lookup"><span data-stu-id="b774c-238">The estimator objects are created but not executed.</span></span>

1. <span data-ttu-id="b774c-239">モデルを生成するメソッドを追加する</span><span class="sxs-lookup"><span data-stu-id="b774c-239">Add a method to generate the model</span></span>

    <span data-ttu-id="b774c-240">このメソッドは、このチュートリアルの中核となるものです。</span><span class="sxs-lookup"><span data-stu-id="b774c-240">This method is the heart of the tutorial.</span></span> <span data-ttu-id="b774c-241">モデルのパイプラインを作成し、パイプラインをトレーニングして ML.NET モデルを生成します。</span><span class="sxs-lookup"><span data-stu-id="b774c-241">It creates a pipeline for the model, and trains the pipeline to produce the ML.NET model.</span></span> <span data-ttu-id="b774c-242">また、未認識のテスト データに対してモデルを評価します。</span><span class="sxs-lookup"><span data-stu-id="b774c-242">It also evaluates the model against some previously unseen test data.</span></span>

    <span data-ttu-id="b774c-243">`InceptionSettings` 構造体の直後、かつ `DisplayResults()` メソッドの直前に、次のコードを使用して `GenerateModel()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="b774c-243">Create the `GenerateModel()` method, just after the `InceptionSettings` struct and just before the `DisplayResults()` method, using the following code:</span></span>

    ```csharp
    public static ITransformer GenerateModel(MLContext mlContext)
    {

    }
    ```

1. <span data-ttu-id="b774c-244">画像データを読み込み、サイズを変更し、ピクセルを抽出する推定器を追加します。</span><span class="sxs-lookup"><span data-stu-id="b774c-244">Add the estimators to load, resize and extract the pixels from the image data:</span></span>

    [!code-csharp[ImageTransforms](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ImageTransforms)]

    <span data-ttu-id="b774c-245">画像データは、TensorFlow モデルで想定されている形式に処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b774c-245">The image data needs to be processed into the format that the TensorFlow model expects.</span></span> <span data-ttu-id="b774c-246">この場合、画像はメモリに読み込まれ、サイズが一貫したサイズに変更され、ピクセルが数値ベクターに抽出されます。</span><span class="sxs-lookup"><span data-stu-id="b774c-246">In this case, the images are loaded into memory, resized to a consistent size, and the pixels are extracted into a numeric vector.</span></span>

1. <span data-ttu-id="b774c-247">TensorFlow モデルを読み込み、評価する推定器を追加します。</span><span class="sxs-lookup"><span data-stu-id="b774c-247">Add the estimator to load the TensorFlow model, and score it:</span></span>

    [!code-csharp[ScoreTensorFlowModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ScoreTensorFlowModel)]

    <span data-ttu-id="b774c-248">パイプラインのこのステージでは、TensorFlow モデルをメモリに読み込み、次に TensorFlow モデル ネットワークを介してピクセル値のベクターを処理します。</span><span class="sxs-lookup"><span data-stu-id="b774c-248">This stage in the pipeline loads the TensorFlow model into memory, then processes the vector of pixel values through the TensorFlow model network.</span></span> <span data-ttu-id="b774c-249">ディープ ラーニング モデルに入力を適用し、モデルを使用して出力を生成することは、**スコアリング**と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="b774c-249">Applying inputs to a deep learning model, and generating an output using the model, is referred to as **Scoring**.</span></span> <span data-ttu-id="b774c-250">モデル全体を使用する場合、スコアリングによって推論または予測が行われます。</span><span class="sxs-lookup"><span data-stu-id="b774c-250">When using the model in its entirety, scoring makes an inference, or prediction.</span></span> 

    <span data-ttu-id="b774c-251">この場合、最後のレイヤー (推論を行うレイヤー) を除き、すべての TensorFlow モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="b774c-251">In this case, you use all of the TensorFlow model except the last layer, which is the layer that makes the inference.</span></span> <span data-ttu-id="b774c-252">最後から 2 番目のレイヤーの出力には、`softmax_2_preactivation` というラベルが付けられます。</span><span class="sxs-lookup"><span data-stu-id="b774c-252">The output of the penultimate layer is labeled `softmax_2_preactivation`.</span></span> <span data-ttu-id="b774c-253">このレイヤーの出力は、実質的に、元の入力画像を特徴付ける特徴のベクターです。</span><span class="sxs-lookup"><span data-stu-id="b774c-253">The output of this layer is effectively a vector of features that characterize the original input images.</span></span>

    <span data-ttu-id="b774c-254">TensorFlow モデルによって生成されるこの特徴ベクターは、ML.NET トレーニング アルゴリズムへの入力として使用されます。</span><span class="sxs-lookup"><span data-stu-id="b774c-254">This feature vector generated by the TensorFlow model will be used as input to an ML.NET training algorithm.</span></span>

1. <span data-ttu-id="b774c-255">トレーニング データの文字列ラベルを整数キー値にマップする推定器を追加します。</span><span class="sxs-lookup"><span data-stu-id="b774c-255">Add the estimator to map the string labels in the training data to integer key values:</span></span>

    [!code-csharp[MapValueToKey](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey)]

    <span data-ttu-id="b774c-256">次に追加される ML.NET トレーナーでは、ラベルが任意の文字列ではなく `key` 形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b774c-256">The ML.NET trainer that is appended next requires its labels to be in `key` format rather than arbitrary strings.</span></span> <span data-ttu-id="b774c-257">キーは、文字列値への 1 対 1 のマッピングを持つ数値です。</span><span class="sxs-lookup"><span data-stu-id="b774c-257">A key is a number that has a one to one mapping to a string value.</span></span>

1. <span data-ttu-id="b774c-258">ML.NET トレーニング アルゴリズムを追加します。</span><span class="sxs-lookup"><span data-stu-id="b774c-258">Add the ML.NET training algorithm:</span></span>

    [!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddTrainer)]

1. <span data-ttu-id="b774c-259">予測されたキー値を元の文字列にマップする推定器を追加します。</span><span class="sxs-lookup"><span data-stu-id="b774c-259">Add the estimator to map the predicted key value back into a string:</span></span>

    [!code-csharp[MapKeyToValue](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapKeyToValue)]

## <a name="train-the-model"></a><span data-ttu-id="b774c-260">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="b774c-260">Train the model</span></span>

1. <span data-ttu-id="b774c-261">[LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile(Microsoft.ML.DataOperationsCatalog,System.String,Microsoft.ML.Data.TextLoader.Options)) ラッパーを使用してトレーニング データを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="b774c-261">Load the training data using the [LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile(Microsoft.ML.DataOperationsCatalog,System.String,Microsoft.ML.Data.TextLoader.Options)) wrapper.</span></span> <span data-ttu-id="b774c-262">`GenerateModel()` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="b774c-262">Add the following code as the next line in the `GenerateModel()` method:</span></span>

    [!code-csharp[LoadData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadData "Load the data")]

    <span data-ttu-id="b774c-263">ML.NET 内のデータは、[IDataView クラス](xref:Microsoft.ML.IDataView)として表されます。</span><span class="sxs-lookup"><span data-stu-id="b774c-263">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="b774c-264">`IDataView` は、表形式のデータ (数値とテキスト) を表すための柔軟で効率的な方法です。</span><span class="sxs-lookup"><span data-stu-id="b774c-264">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="b774c-265">データはテキスト ファイルから、またはリアルタイムで (SQL データベースやログ ファイルなど) `IDataView` オブジェクトに読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="b774c-265">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

1. <span data-ttu-id="b774c-266">前の手順で読み込まれたデータを使用してモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="b774c-266">Train the model with the data loaded above:</span></span>

    [!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TrainModel)]

    <span data-ttu-id="b774c-267">`Fit()` メソッドで、トレーニング データセットをパイプラインに適用してモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="b774c-267">The `Fit()` method trains your model by applying the training dataset to the pipeline.</span></span>

## <a name="evaluate-the-accuracy-of-the-model"></a><span data-ttu-id="b774c-268">モデルの精度を評価する</span><span class="sxs-lookup"><span data-stu-id="b774c-268">Evaluate the accuracy of the model</span></span>

1. <span data-ttu-id="b774c-269">`GenerateModel` メソッドの次の行に次のコードを追加して、テスト データを読み込んで変換します。</span><span class="sxs-lookup"><span data-stu-id="b774c-269">Load and transform the test data, by adding the following code to the next line of the `GenerateModel` method:</span></span>

    [!code-csharp[LoadAndTransformTestData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadAndTransformTestData "Load and transform test data")]

    <span data-ttu-id="b774c-270">モデルの評価に使用できるサンプル画像がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="b774c-270">There are a few sample images that you can use to evaluate the model.</span></span> <span data-ttu-id="b774c-271">トレーニング データと同様に、モデルで変換できるように、これらを `IDataView` に読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="b774c-271">Like the training data, these need to be loaded into an `IDataView`, so that they can be transformed by the model.</span></span>
   
1. <span data-ttu-id="b774c-272">`GenerateModel()` メソッドに次のコードを追加して、モデルを評価します。</span><span class="sxs-lookup"><span data-stu-id="b774c-272">Add the following code to the `GenerateModel()` method to evaluate the model:</span></span>

    [!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Evaluate)]

    <span data-ttu-id="b774c-273">予測セットを作成したら、[Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b774c-273">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method:</span></span>

    * <span data-ttu-id="b774c-274">モデルを評価します (予測値とテスト データセット `labels` を比較します)。</span><span class="sxs-lookup"><span data-stu-id="b774c-274">Assesses the model (compares the predicted values with the test dataset `labels`).</span></span>
    * <span data-ttu-id="b774c-275">モデルのパフォーマンス メトリックを返します。</span><span class="sxs-lookup"><span data-stu-id="b774c-275">Returns the model performance metrics.</span></span>

1. <span data-ttu-id="b774c-276">モデルの精度のメトリックを表示する</span><span class="sxs-lookup"><span data-stu-id="b774c-276">Display the model accuracy metrics</span></span>

    <span data-ttu-id="b774c-277">次のコードを使用してメトリックを表示し、結果を共有し、それに対してアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="b774c-277">Use the following code to display the metrics, share the results, and then act on them:</span></span>

    [!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayMetrics)]

    <span data-ttu-id="b774c-278">画像分類では、次のメトリックが評価されます。</span><span class="sxs-lookup"><span data-stu-id="b774c-278">The following metrics are evaluated for image classification:</span></span>

    * <span data-ttu-id="b774c-279">`Log-loss` - 「[対数損失](../resources/glossary.md#log-loss)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b774c-279">`Log-loss` - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="b774c-280">対数損失は可能な限り 1 に近づけます。</span><span class="sxs-lookup"><span data-stu-id="b774c-280">You want Log-loss to be as close to zero as possible.</span></span>
    * <span data-ttu-id="b774c-281">`Per class Log-loss`。</span><span class="sxs-lookup"><span data-stu-id="b774c-281">`Per class Log-loss`.</span></span> <span data-ttu-id="b774c-282">クラスごとの対数損失は可能な限り 1 に近づけます。</span><span class="sxs-lookup"><span data-stu-id="b774c-282">You want per class Log-loss to be as close to zero as possible.</span></span>

1. <span data-ttu-id="b774c-283">次の行としてトレーニング済みモデルを返すように次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="b774c-283">Add the following code to return the trained model as the next line:</span></span>

    [!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReturnModel)]

## <a name="run-the-application"></a><span data-ttu-id="b774c-284">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="b774c-284">Run the application!</span></span>

1. <span data-ttu-id="b774c-285">MLContext クラスを作成した後、`Main` メソッドに `GenerateModel` の呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="b774c-285">Add the call to `GenerateModel` in the `Main` method after the creation of the MLContext class:</span></span>

    [!code-csharp[CallGenerateModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallGenerateModel)]

1. <span data-ttu-id="b774c-286">`Main` メソッドの次のコード行として、`ClassifySingleImage()` メソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="b774c-286">Add the call to the `ClassifySingleImage()` method as the next line of code in the `Main` method:</span></span>

    [!code-csharp[CallClassifySingleImage](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifySingleImage)]

1. <span data-ttu-id="b774c-287">コンソール アプリを実行します (Ctrl + F5 キー)。</span><span class="sxs-lookup"><span data-stu-id="b774c-287">Run your console app (Ctrl + F5).</span></span> <span data-ttu-id="b774c-288">結果は以下の出力のようになるはずです。</span><span class="sxs-lookup"><span data-stu-id="b774c-288">Your results should be similar to the following output.</span></span>  <span data-ttu-id="b774c-289">警告メッセージまたは処理中のメッセージが表示される場合がありますが、わかりやすくするため、これらのメッセージは結果から削除してあります。</span><span class="sxs-lookup"><span data-stu-id="b774c-289">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

    ```console
    =============== Training classification model ===============
    Image: broccoli.jpg predicted as: food with score: 0.976743
    Image: pizza.jpg predicted as: food with score: 0.9751652
    Image: pizza2.jpg predicted as: food with score: 0.9660203
    Image: teddy2.jpg predicted as: toy with score: 0.9748783
    Image: teddy3.jpg predicted as: toy with score: 0.9829691
    Image: teddy4.jpg predicted as: toy with score: 0.9868168
    Image: toaster.jpg predicted as: appliance with score: 0.9769174
    Image: toaster2.png predicted as: appliance with score: 0.9800823
    =============== Classification metrics ===============
    LogLoss is: 0.0228266745633507
    PerClassLogLoss is: 0.0277501705149937 , 0.0186303530571291 , 0.0217359128952187
    =============== Making single image classification ===============
    Image: toaster3.jpg predicted as: appliance with score: 0.9625379

    C:\Program Files\dotnet\dotnet.exe (process 4304) exited with code 0.
    Press any key to close this window . . .
    ```

<span data-ttu-id="b774c-290">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="b774c-290">Congratulations!</span></span> <span data-ttu-id="b774c-291">これで、ML.NET で `TensorFlow` モデルに転移学習を適用して、画像分類の機械学習モデルを構築できました。</span><span class="sxs-lookup"><span data-stu-id="b774c-291">You've now successfully built a machine learning model for image classification by applying transfer learning to a `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="b774c-292">このチュートリアルのソース コードは [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) リポジトリで確認できます。</span><span class="sxs-lookup"><span data-stu-id="b774c-292">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span>

<span data-ttu-id="b774c-293">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="b774c-293">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="b774c-294">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="b774c-294">Understand the problem</span></span>
> * <span data-ttu-id="b774c-295">事前トレーニング済みの TensorFlow モデルを ML.NET パイプラインに組み込む</span><span class="sxs-lookup"><span data-stu-id="b774c-295">Incorporate the pre-trained TensorFlow model into the ML.NET pipeline</span></span>
> * <span data-ttu-id="b774c-296">ML.NET モデルのトレーニングと評価</span><span class="sxs-lookup"><span data-stu-id="b774c-296">Train and evaluate the ML.NET model</span></span>
> * <span data-ttu-id="b774c-297">テスト画像を分類する</span><span class="sxs-lookup"><span data-stu-id="b774c-297">Classify a test image</span></span>

<span data-ttu-id="b774c-298">Machine Learning サンプルの GitHub リポジトリを確認し、拡張された画像分類サンプルを探索してください。</span><span class="sxs-lookup"><span data-stu-id="b774c-298">Check out the Machine Learning samples GitHub repository to explore an expanded image classification sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="b774c-299">dotnet/machinelearning-samples GitHub リポジトリ</span><span class="sxs-lookup"><span data-stu-id="b774c-299">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/)
