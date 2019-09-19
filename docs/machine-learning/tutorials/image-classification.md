---
title: 'チュートリアル: TensorFlow 画像分類器を再トレーニングする - 転移学習'
description: 転移学習と ML.NET を使用して画像分類 TensorFlow モデルを再トレーニングする方法について説明します。 元のモデルは、個々の画像を分類するようにトレーニングされました。 再トレーニング後、新しいモデルは、画像を広範なカテゴリに整理します。
ms.date: 07/09/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: eb6e3d3f3a33aa7360802ce1bc6c16532539c828
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70929238"
---
# <a name="tutorial-retrain-a-tensorflow-image-classifier-with-transfer-learning-and-mlnet"></a><span data-ttu-id="a6c71-105">チュートリアル: 転移学習と ML.NET を使用して TensorFlow 画像分類子を再トレーニングする</span><span class="sxs-lookup"><span data-stu-id="a6c71-105">Tutorial: Retrain a TensorFlow image classifier with transfer learning and ML.NET</span></span>

<span data-ttu-id="a6c71-106">転移学習と ML.NET を使用して画像分類 TensorFlow モデルを再トレーニングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-106">Learn how to retrain an image classification TensorFlow model with transfer learning and ML.NET.</span></span> <span data-ttu-id="a6c71-107">元のモデルは、個々の画像を分類するようにトレーニングされました。</span><span class="sxs-lookup"><span data-stu-id="a6c71-107">The original model was trained to classify individual images.</span></span> <span data-ttu-id="a6c71-108">再トレーニング後の新しいモデルは、画像を広範なカテゴリに整理します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-108">After retraining, the new model organizes the images into broad categories.</span></span> 

<span data-ttu-id="a6c71-109">[画像分類](https://en.wikipedia.org/wiki/Outline_of_object_recognition)モデルを最初からトレーニングするには、数百万のパラメーター、大量のラベル付きトレーニング データ、膨大な量の計算リソース (数百時間の GPU) を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6c71-109">Training an [Image Classification](https://en.wikipedia.org/wiki/Outline_of_object_recognition) model from scratch requires setting millions of parameters, a ton of labeled training data and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="a6c71-110">最初からカスタム モデルをトレーニングするほど効果的ではありませんが、転移学習を使用すると、何千もの画像と何百万ものラベル付き画像を使用し、カスタマイズされたモデルを短時間 (GPU が搭載されていないマシンで 1 時間以内) で構築できます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-110">While not as effective as training a custom model from scratch, transfer learning allows you to shortcut this process by working with thousands of images vs. millions of labeled images and build a customized model fairly quickly (within an hour on a machine without a GPU).</span></span>

<span data-ttu-id="a6c71-111">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="a6c71-112">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="a6c71-112">Understand the problem</span></span>
> * <span data-ttu-id="a6c71-113">トレーニング済みのモデルを再利用して調整する</span><span class="sxs-lookup"><span data-stu-id="a6c71-113">Reuse and tune the pre-trained model</span></span>
> * <span data-ttu-id="a6c71-114">画像を分類する</span><span class="sxs-lookup"><span data-stu-id="a6c71-114">Classify Images</span></span>

## <a name="what-is-transfer-learning"></a><span data-ttu-id="a6c71-115">転移学習とは何か</span><span class="sxs-lookup"><span data-stu-id="a6c71-115">What is transfer learning?</span></span>

<span data-ttu-id="a6c71-116">トレーニング済みのモデルを再利用して同様の問題を解決し、そのモデルのレイヤーの全部または一部を再トレーニングして問題を解決することもできます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-116">What if you could reuse a model that's already been pre trained to solve a similar problem and retrain either all or some of the layers of that model to make it solve your problem?</span></span> <span data-ttu-id="a6c71-117">トレーニング済みのモデルの一部を再利用して新しいモデルを構築するこの手法は、[転移学習](https://en.wikipedia.org/wiki/Transfer_learning)と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-117">This technique of reusing part of an already trained model to build a new model is known as [transfer learning](https://en.wikipedia.org/wiki/Transfer_learning).</span></span>

## <a name="image-classification-sample-overview"></a><span data-ttu-id="a6c71-118">画像分類サンプルの概要</span><span class="sxs-lookup"><span data-stu-id="a6c71-118">Image classification sample overview</span></span>

<span data-ttu-id="a6c71-119">このサンプルは、トレーニング済みのモデルを再利用して少量のトレーニング データで画像を分類することによって、ML.NET を使用して画像分類器を構築するコンソール アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="a6c71-119">The sample is a console application that uses ML.NET to build an image classifier by reusing a pre-trained model to classify images with a small amount of training data.</span></span>

<span data-ttu-id="a6c71-120">このチュートリアルのソース コードは [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) リポジトリで確認できます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-120">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span> <span data-ttu-id="a6c71-121">既定では、このチュートリアルの .NET プロジェクトの構成は .NET Core 2.2 を対象としています。</span><span class="sxs-lookup"><span data-stu-id="a6c71-121">Note that by default, the .NET project configuration for this tutorial targets .NET core 2.2.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a6c71-122">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a6c71-122">Prerequisites</span></span>

* <span data-ttu-id="a6c71-123">[Visual Studio 2017 15.6 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)が ".NET Core クロスプラット フォーム開発" とともにインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="a6c71-123">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span> 

* <span data-ttu-id="a6c71-124">Microsoft.ML 1.0.0 Nuget パッケージ</span><span class="sxs-lookup"><span data-stu-id="a6c71-124">Microsoft.ML 1.0.0 Nuget package</span></span>
* <span data-ttu-id="a6c71-125">Microsoft.ML.ImageAnalytics 1.0.0 Nuget パッケージ</span><span class="sxs-lookup"><span data-stu-id="a6c71-125">Microsoft.ML.ImageAnalytics 1.0.0 Nuget package</span></span>
* <span data-ttu-id="a6c71-126">Microsoft.ML.TensorFlow 0.12.0 Nuget パッケージ</span><span class="sxs-lookup"><span data-stu-id="a6c71-126">Microsoft.ML.TensorFlow 0.12.0 Nuget package</span></span>

* [<span data-ttu-id="a6c71-127">チュートリアル資産ディレクトリの .ZIP ファイル</span><span class="sxs-lookup"><span data-stu-id="a6c71-127">The tutorial assets directory .ZIP file</span></span>](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)

* [<span data-ttu-id="a6c71-128">InceptionV1 機械学習モデル</span><span class="sxs-lookup"><span data-stu-id="a6c71-128">The InceptionV1 machine learning model</span></span>](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="a6c71-129">適切な機械学習タスクを選択する</span><span class="sxs-lookup"><span data-stu-id="a6c71-129">Select the appropriate machine learning task</span></span>

<span data-ttu-id="a6c71-130">[ディープ ラーニング](https://en.wikipedia.org/wiki/Deep_learning)は、Computer Vision や音声認識などの分野に革命を起こしている Machine Learning のサブセットです。</span><span class="sxs-lookup"><span data-stu-id="a6c71-130">[Deep learning](https://en.wikipedia.org/wiki/Deep_learning) is a subset of Machine Learning, which is revolutionizing areas like Computer Vision and Speech Recognition.</span></span>

<span data-ttu-id="a6c71-131">ディープ ラーニング モデルは、複数の学習レイヤーを含む多数の[ラベル付きデータ](https://en.wikipedia.org/wiki/Labeled_data)と[ニューラル ネットワーク](https://en.wikipedia.org/wiki/Artificial_neural_network)を使用してトレーニングされます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-131">Deep learning models are trained by using large sets of [labeled data](https://en.wikipedia.org/wiki/Labeled_data) and [neural networks](https://en.wikipedia.org/wiki/Artificial_neural_network) that contain multiple learning layers.</span></span> <span data-ttu-id="a6c71-132">ディープ ラーニング:</span><span class="sxs-lookup"><span data-stu-id="a6c71-132">Deep learning:</span></span>

* <span data-ttu-id="a6c71-133">Computer Vision などの一部のタスクでより効果的に機能します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-133">Performs better on some tasks like Computer Vision.</span></span>

* <span data-ttu-id="a6c71-134">膨大なデータ量に対しても適切に機能します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-134">Performs well on huge data amounts.</span></span>

<span data-ttu-id="a6c71-135">画像分類は、画像を次のような複数のカテゴリに自動的に分類することができる一般的な機械学習タスクです。</span><span class="sxs-lookup"><span data-stu-id="a6c71-135">Image Classification is a common Machine Learning task that allows us to automatically classify images into multiple categories such as:</span></span>

* <span data-ttu-id="a6c71-136">画像から人の顔を検出するかどうか。</span><span class="sxs-lookup"><span data-stu-id="a6c71-136">Detecting a human face in an image or not.</span></span>
* <span data-ttu-id="a6c71-137">猫と犬を検出する。</span><span class="sxs-lookup"><span data-stu-id="a6c71-137">Detecting Cats vs. dogs.</span></span>

 <span data-ttu-id="a6c71-138">または、次のような各画像で、食品、おもちゃ、または電化製品の画像であるかどうかを判別する。</span><span class="sxs-lookup"><span data-stu-id="a6c71-138">Or as in the following images determining if an image is a(n)  food, toy, or appliance:</span></span>

<span data-ttu-id="a6c71-139">![ピザの画像](./media/image-classification/220px-Pepperoni_pizza.jpg)
![テディ ベアの画像](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![トースターの画像](./media/image-classification/193px-Broodrooster.jpg)</span><span class="sxs-lookup"><span data-stu-id="a6c71-139">![pizza image](./media/image-classification/220px-Pepperoni_pizza.jpg)
![teddy bear image](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![toaster image](./media/image-classification/193px-Broodrooster.jpg)</span></span>

>[!Note]
> <span data-ttu-id="a6c71-140">上の画像は Wikimedia Commons に属し、次のように属性が付けられています。</span><span class="sxs-lookup"><span data-stu-id="a6c71-140">The preceding images belong to Wikimedia Commons and are attributed as follows:</span></span>
>
> * <span data-ttu-id="a6c71-141">"220px-Pepperoni_pizza.jpg" パブリック ドメイン、 https://commons.wikimedia.org/w/index.php?curid=79505 、</span><span class="sxs-lookup"><span data-stu-id="a6c71-141">"220px-Pepperoni_pizza.jpg" Public Domain, https://commons.wikimedia.org/w/index.php?curid=79505,</span></span>
> * <span data-ttu-id="a6c71-142">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" By [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - 自己撮影、CC BY-SA 2.0、 https://commons.wikimedia.org/w/index.php?curid=48166 。</span><span class="sxs-lookup"><span data-stu-id="a6c71-142">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" By [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Self-photographed, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.</span></span>
> * <span data-ttu-id="a6c71-143">"193px-Broodrooster.jpg" By [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - 自分の作品、CC BY-SA 3.0、 https://commons.wikimedia.org/w/index.php?curid=27403</span><span class="sxs-lookup"><span data-stu-id="a6c71-143">"193px-Broodrooster.jpg" By [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Own work, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403</span></span>

<span data-ttu-id="a6c71-144">転移学習には、*すべてのレイヤーの再トレーニング*、*最後から 2 番目のレイヤー*など、いくつかの戦略があります。</span><span class="sxs-lookup"><span data-stu-id="a6c71-144">Transfer learning includes a few strategies, such as *retrain all layers* and *penultimate layer*.</span></span> <span data-ttu-id="a6c71-145">このチュートリアルでは、"*最後から 2 番目のレイヤー戦略*" の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-145">This tutorial will explain and show how to use the *penultimate layer strategy*.</span></span> <span data-ttu-id="a6c71-146">"*最後から 2 番目のレイヤー戦略*" は、トレーニング済みのモデルを再利用して特定の問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-146">The *penultimate layer strategy* reuses a model that's already been pre-trained to solve a specific problem.</span></span> <span data-ttu-id="a6c71-147">次に、この戦略では、そのモデルの最後のレイヤーを再トレーニングして新しい問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-147">The strategy then retrains the final layer of that model to make it solve a new problem.</span></span> <span data-ttu-id="a6c71-148">トレーニング済みのモデルを新しいモデルの一部として再利用すると、時間とリソースを大幅に節約できます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-148">Reusing the pre-trained model as part of your new model will save significant time and resources.</span></span>

<span data-ttu-id="a6c71-149">この画像分類モデルでは [Inception モデル](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)を再利用します。これは、TensorFlow モデルによって画像全体の 1,000 個のクラス ("傘"、"ジャージー"、"皿洗い機" など) への分類を試行する、`ImageNet` データセットに対してトレーニングされた人気のある画像認識モデルです。</span><span class="sxs-lookup"><span data-stu-id="a6c71-149">Your image classification model reuses the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), a popular image recognition model trained on the `ImageNet` dataset where the TensorFlow model tries to classify entire images into a thousand classes, like “Umbrella”, “Jersey”, and “Dishwasher”.</span></span>

<span data-ttu-id="a6c71-150">`Inception v1 model` は[ディープ畳み込みニューラル ネットワーク](https://en.wikipedia.org/wiki/Convolutional_neural_network)と分類することができます。また、分野によっては、困難な視覚認識タスクで、人間のパフォーマンスに匹敵するかそれを超える妥当なパフォーマンスを達成できます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-150">The `Inception v1 model` can be classified as a [deep convolutional neural network](https://en.wikipedia.org/wiki/Convolutional_neural_network) and can achieve reasonable performance on hard visual recognition tasks, matching or exceeding human performance in some domains.</span></span> <span data-ttu-id="a6c71-151">モデル/アルゴリズムは、複数の研究者によって開発され、以下の元の論文に基づいています。[「Rethinking the Inception Architecture for Computer Vision (Computer Vision のためのインセプション アーキテクチャの再考)」(Szegedy 他)](https://arxiv.org/abs/1512.00567)</span><span class="sxs-lookup"><span data-stu-id="a6c71-151">The model/algorithm was developed by multiple researchers and based on the original paper: ["Rethinking the Inception Architecture for Computer Vision” by Szegedy, et. al.](https://arxiv.org/abs/1512.00567)</span></span>

<span data-ttu-id="a6c71-152">`Inception model` は何千種類もの画像に対して事前にトレーニングされているため、画像の識別に必要な[画像の特徴](https://en.wikipedia.org/wiki/Feature_(computer_vision))が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6c71-152">Because the `Inception model` has already been pre trained on thousands of different images, it contains the [image features](https://en.wikipedia.org/wiki/Feature_(computer_vision)) needed for image identification.</span></span> <span data-ttu-id="a6c71-153">以下の画像機能レイヤーは単純な特徴 (端など) を認識し、上のレイヤーはより複雑な特徴 (図形など) を認識します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-153">The lower image feature layers recognize simple features (such as edges) and the higher layers recognize more complex features (such as shapes).</span></span> <span data-ttu-id="a6c71-154">最後のレイヤーは、画像の分類方法を既に理解しているトレーニング済みのモデルから始めているため、はるかに小さいデータ セットに対してトレーニングされます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-154">The final layer is trained against a much smaller set of data because you're starting with a pre trained model that already understands how to classify images.</span></span> <span data-ttu-id="a6c71-155">モデルで 3 つ以上のカテゴリを分類できるので、これは[複数クラス分類器](../resources/tasks.md#multiclass-classification)の一例です。</span><span class="sxs-lookup"><span data-stu-id="a6c71-155">As your model allows you to classify more than two categories, this is an example of a [multi-class classifier](../resources/tasks.md#multiclass-classification).</span></span> 

<span data-ttu-id="a6c71-156">`TensorFlow` は、ディープ ニューラル ネットワーク (および一般的な数値計算) をトレーニングできる人気のあるディープ ラーニングおよび機械学習ツールキットであり、.ML.NET では `transformer` として実装されています。</span><span class="sxs-lookup"><span data-stu-id="a6c71-156">`TensorFlow` is a popular deep learning and machine learning toolkit that enables training deep neural networks (and general numeric computations), and is implemented as a `transformer` in ML.NET.</span></span> <span data-ttu-id="a6c71-157">このチュートリアルでは、`Inception model` を再利用するために使用されています。</span><span class="sxs-lookup"><span data-stu-id="a6c71-157">For this tutorial, it's used to reuse the `Inception model`.</span></span>

<span data-ttu-id="a6c71-158">次の図に示すように、.NET Core または .NET Framework アプリケーションに ML.NET NuGet パッケージへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-158">As shown in the following diagram, you add a reference to the ML.NET NuGet packages in your .NET Core or .NET Framework applications.</span></span> <span data-ttu-id="a6c71-159">内部的には、スコア付けのために既存のトレーニング済み `TensorFlow` モデル ファイルを読み込むコードを作成できるネイティブ `TensorFlow` ライブラリが ML.NET には含まれ、参照されています。</span><span class="sxs-lookup"><span data-stu-id="a6c71-159">Under the covers, ML.NET includes and references the native `TensorFlow` library that allows you to write code that loads an existing trained `TensorFlow` model file for scoring.</span></span>  

![TensorFlow 変換 ML.NET Arch 図](./media/image-classification/tensorflow-mlnet.png)

<span data-ttu-id="a6c71-161">`Inception model` は、画像を 1,000 個のカテゴリに分類するようにトレーニングされていますが、画像をより小さなカテゴリ セットにのみ分類する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6c71-161">The `Inception model` is trained to classify images into a thousand categories, but you need to classify images in a smaller category set, and only those categories.</span></span> <span data-ttu-id="a6c71-162">`transfer learning` の `transfer` 部分を入力します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-162">Enter the `transfer` part of `transfer learning`.</span></span> <span data-ttu-id="a6c71-163">`Inception model` の画像を認識および分類する能力をカスタム画像分類器の新しい限られたカテゴリに転移ことができます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-163">You can transfer the `Inception model`'s ability to recognize and classify images to the new limited categories of your custom image classifier.</span></span>  

 <span data-ttu-id="a6c71-164">3 つのカテゴリ セットを使用して、そのモデルの最後のレイヤーを再トレーニングします。</span><span class="sxs-lookup"><span data-stu-id="a6c71-164">You're going to retrain the final layer of that model using a set of three categories:</span></span>

* <span data-ttu-id="a6c71-165">食品</span><span class="sxs-lookup"><span data-stu-id="a6c71-165">Food</span></span>
* <span data-ttu-id="a6c71-166">おもちゃ</span><span class="sxs-lookup"><span data-stu-id="a6c71-166">Toy</span></span>
* <span data-ttu-id="a6c71-167">アプライアンス</span><span class="sxs-lookup"><span data-stu-id="a6c71-167">Appliance</span></span>

<span data-ttu-id="a6c71-168">レイヤーは、[多項ロジスティック回帰アルゴリズム](https://en.wikipedia.org/wiki/Multinomial_logistic_regression)を使用して正しいカテゴリを可能な限り早く見つけます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-168">Your layer uses a [multinomial logistic regression algorithm](https://en.wikipedia.org/wiki/Multinomial_logistic_regression) to find the correct category as quickly as possible.</span></span> <span data-ttu-id="a6c71-169">このアルゴリズムでは、確率を使用して答えを決定し、正しいカテゴリに 1 の値を与え、他のカテゴリに 0 の値を与えます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-169">This algorithm classifies using probabilities to determine the answer, giving a one value to the correct category and a zero value to the others.</span></span>  

### <a name="dataset"></a><span data-ttu-id="a6c71-170">DataSet</span><span class="sxs-lookup"><span data-stu-id="a6c71-170">DataSet</span></span>

<span data-ttu-id="a6c71-171">データ ソースは 2 つあります。`.tsv` ファイルと画像ファイルです。</span><span class="sxs-lookup"><span data-stu-id="a6c71-171">There are two data sources: the `.tsv` file, and the image files.</span></span>  <span data-ttu-id="a6c71-172">`tags.tsv` ファイルには 2 つの列があります。最初の列は `ImagePath` と定義され、2 番目の列は画像に対応する `Label` です。</span><span class="sxs-lookup"><span data-stu-id="a6c71-172">The `tags.tsv` file contains two columns: the first one is defined as `ImagePath` and the second one is the `Label` corresponding to the image.</span></span> <span data-ttu-id="a6c71-173">次のファイル例にはヘッダー行がなく、次のような内容です。</span><span class="sxs-lookup"><span data-stu-id="a6c71-173">The following example file doesn't have a header row, and looks like this:</span></span>

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

<span data-ttu-id="a6c71-174">トレーニングとテストの画像は、zip ファイルでダウンロードする資産フォルダー内にあります。</span><span class="sxs-lookup"><span data-stu-id="a6c71-174">The training and testing images are located in the assets folders that you'll download in a zip file.</span></span> <span data-ttu-id="a6c71-175">これらの画像は Wikimedia Commons に属します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-175">These images belong to Wikimedia Commons.</span></span>
> <span data-ttu-id="a6c71-176">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208)、無料メディア リポジトリ。*</span><span class="sxs-lookup"><span data-stu-id="a6c71-176">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), the free media repository.*</span></span> <span data-ttu-id="a6c71-177">2018 年 10 月 17 日 10:48 に以下から取得:</span><span class="sxs-lookup"><span data-stu-id="a6c71-177">Retrieved 10:48, October 17, 2018 from:</span></span>  
> https://commons.wikimedia.org/wiki/Pizza  
> https://commons.wikimedia.org/wiki/Toaster  
> https://commons.wikimedia.org/wiki/Teddy_bear  

## <a name="create-a-console-application"></a><span data-ttu-id="a6c71-178">コンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="a6c71-178">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="a6c71-179">プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="a6c71-179">Create a project</span></span>

1. <span data-ttu-id="a6c71-180">"TransferLearningTF" という **.NET Core Console アプリケーション**を作成します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-180">Create a **.NET Core Console Application** called "TransferLearningTF".</span></span>

2. <span data-ttu-id="a6c71-181">**Microsoft.ML NuGet パッケージ**をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a6c71-181">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="a6c71-182">ソリューション エクスプローラーで、プロジェクトを右クリックし、 **[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-182">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="a6c71-183">[パッケージ ソース] として "nuget.org" を選択し、[参照] タブを選択し、"**Microsoft.ML**" を検索します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-183">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**.</span></span> <span data-ttu-id="a6c71-184">**[バージョン]** ドロップダウンをクリックし、一覧から **1.0.0** パッケージを選択し、 **[インストール]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-184">Click on the **Version** drop-down, select the **1.0.0** package in the list, and select the **Install** button.</span></span> <span data-ttu-id="a6c71-185">**[変更のプレビュー]** ダイアログの **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、 **[ライセンスの同意]** ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-185">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="a6c71-186">**Microsoft.ML.ImageAnalytics v1.0.0** と **Microsoft.ML.TensorFlow v0.12.0** についても、これらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-186">Repeat these steps for **Microsoft.ML.ImageAnalytics v1.0.0** and **Microsoft.ML.TensorFlow v0.12.0**.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="a6c71-187">データを準備する</span><span class="sxs-lookup"><span data-stu-id="a6c71-187">Prepare your data</span></span>

1. <span data-ttu-id="a6c71-188">[プロジェクト資産ディレクトリの zip ファイル](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)をダウンロードし、展開します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-188">Download [The project assets directory zip file](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip), and unzip.</span></span>

2. <span data-ttu-id="a6c71-189">`assets` ディレクトリを *TransferLearningTF* プロジェクト ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a6c71-189">Copy the `assets` directory into your *TransferLearningTF* project directory.</span></span> <span data-ttu-id="a6c71-190">このディレクトリとそのサブディレクトリには、このチュートリアルに必要なデータ ファイルとサポート ファイル (次の手順でダウンロードして追加する Inception モデルを除く) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6c71-190">This directory and its subdirectories contain the data and support files (except for the Inception model, which you'll download and add in the next step) needed for this tutorial.</span></span>

3. <span data-ttu-id="a6c71-191">[Inception モデル](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)をダウンロードして展開します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-191">Download the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), and unzip.</span></span>

4. <span data-ttu-id="a6c71-192">`inception5h` ディレクトリの内容をコピーし、*TransferLearningTF* プロジェクトの `assets\inputs-train\inception` ディレクトリに展開します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-192">Copy the contents of the `inception5h` directory just unzipped into your *TransferLearningTF* project `assets\inputs-train\inception` directory.</span></span> <span data-ttu-id="a6c71-193">次の画像に示すように、このディレクトリには、このチュートリアルに必要なモデルと追加のサポート ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6c71-193">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![Inception ディレクトリの内容](./media/image-classification/inception-files.png)

5. <span data-ttu-id="a6c71-195">ソリューション エクスプローラーで、資産ディレクトリとサブディレクトリ内の各ファイルを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-195">In Solution Explorer, right-click each of the files in the asset directory and subdirectories and select **Properties**.</span></span> <span data-ttu-id="a6c71-196">**[詳細設定]** で、 **[出力ディレクトリにコピー]** の値を **[新しい場合はコピーする]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-196">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="a6c71-197">クラスを作成してパスを定義する</span><span class="sxs-lookup"><span data-stu-id="a6c71-197">Create classes and define paths</span></span>

<span data-ttu-id="a6c71-198">次に示す追加の `using` ステートメントを *Program.cs* ファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-198">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddUsings)]

<span data-ttu-id="a6c71-199">さまざまな資産のパスを保持するグローバル フィールドと、`LabelTokey`、`ImageReal`、および `PredictedLabelValue` のグローバル変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-199">Create global fields to hold the paths to the various assets, and global variables for the `LabelTokey`,`ImageReal`, and  `PredictedLabelValue`:</span></span>

* <span data-ttu-id="a6c71-200">`_assetsPath` には、資産のパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-200">`_assetsPath` has the path to the assets.</span></span>
* <span data-ttu-id="a6c71-201">`_trainTagsTsv` には、トレーニング画像データ タグの tsv ファイルのパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-201">`_trainTagsTsv` has the path to the training image data tags tsv file.</span></span>
* <span data-ttu-id="a6c71-202">`_predictTagsTsv` には、予測画像データ タグの tsv ファイルのパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-202">`_predictTagsTsv` has the path to the prediction image data tags tsv file.</span></span>
* <span data-ttu-id="a6c71-203">`_trainImagesFolder` には、モデルのトレーニングに使用される画像のパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-203">`_trainImagesFolder` has the path to the images used to train the model.</span></span>
* <span data-ttu-id="a6c71-204">`_predictImagesFolder` には、トレーニング済みのモデルによって分類される画像のパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-204">`_predictImagesFolder` has the path to the images to be classified by the trained model.</span></span>
* <span data-ttu-id="a6c71-205">`_inceptionPb` には、モデルの再トレーニングに再利用できるトレーニング済みの Inception モデルのパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-205">`_inceptionPb` has the path to the pre-trained Inception model to be reused to retrain your model.</span></span>
* <span data-ttu-id="a6c71-206">`_inputImageClassifierZip` には、トレーニング済みのモデルの読み込み元のパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-206">`_inputImageClassifierZip` has the path where the trained model is loaded from.</span></span>
* <span data-ttu-id="a6c71-207">`_outputImageClassifierZip` には、トレーニング済みのモデルを保存するパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-207">`_outputImageClassifierZip` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="a6c71-208">`LabelTokey` は、キーにマップされた `Label` 値です。</span><span class="sxs-lookup"><span data-stu-id="a6c71-208">`LabelTokey` is the `Label` value mapped to a key.</span></span>
* <span data-ttu-id="a6c71-209">`ImageReal` は予測された画像値を含む列です。</span><span class="sxs-lookup"><span data-stu-id="a6c71-209">`ImageReal`  is the column containing the predicted image value.</span></span>
* <span data-ttu-id="a6c71-210">`PredictedLabelValue` は予測されたラベル値を含む列です。</span><span class="sxs-lookup"><span data-stu-id="a6c71-210">`PredictedLabelValue` is the column containing the predicted label value.</span></span>

<span data-ttu-id="a6c71-211">`Main` メソッドのすぐ上にある行に次のコードを追加して、それらのパスとその他の変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-211">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="a6c71-212">入力データと予測のために、いくつかのクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-212">Create some classes for your input data, and predictions.</span></span> <span data-ttu-id="a6c71-213">プロジェクトに新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-213">Add a new class to your project:</span></span>

1. <span data-ttu-id="a6c71-214">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、 **[追加]**  >  **[新しい項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-214">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="a6c71-215">**[新しい項目の追加]** ダイアログ ボックスで、 **[クラス]** を選択し、 **[名前]** フィールドを「*ImageData.cs*」に変更します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-215">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImageData.cs*.</span></span> <span data-ttu-id="a6c71-216">次に **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-216">Then, select the **Add** button.</span></span>

    <span data-ttu-id="a6c71-217">コード エディターで *ImageData.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-217">The *ImageData.cs* file opens in the code editor.</span></span> <span data-ttu-id="a6c71-218">次の `using` ステートメントを *ImageData.cs* の先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-218">Add the following `using` statement to the top of *ImageData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#AddUsings)]

<span data-ttu-id="a6c71-219">既存のクラス定義を削除し、`ImageData` クラスの次のコードを *ImageData.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-219">Remove the existing class definition and add the following code for the `ImageData` class to the *ImageData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#DeclareTypes)]

<span data-ttu-id="a6c71-220">`ImageData` は、入力画像データ クラスであり、次の <xref:System.String> フィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="a6c71-220">`ImageData` is the input image data class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="a6c71-221">`ImagePath` には、画像ファイル名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-221">`ImagePath` contains the image file name.</span></span>
* <span data-ttu-id="a6c71-222">`Label` には、画像ラベルの値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-222">`Label` contains a value for the image label.</span></span>

<span data-ttu-id="a6c71-223">`ImagePrediction` のプロジェクトに新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-223">Add a new class to your project for `ImagePrediction`:</span></span>

1. <span data-ttu-id="a6c71-224">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、 **[追加]**  >  **[新しい項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-224">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="a6c71-225">**[新しい項目の追加]** ダイアログ ボックスで、 **[クラス]** を選択し、 **[名前]** フィールドを *ImagePrediction.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-225">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImagePrediction.cs*.</span></span> <span data-ttu-id="a6c71-226">次に **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-226">Then, select the **Add** button.</span></span>

    <span data-ttu-id="a6c71-227">コード エディターに *ImagePrediction.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-227">The *ImagePrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="a6c71-228">*ImagePrediction.cs* の先頭にある `System.Collections.Generic` と `System.Text` `using` の両方のステートメントを削除します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-228">Remove both the `System.Collections.Generic` and the `System.Text` `using` statements at the top of *ImagePrediction.cs*:</span></span>

<span data-ttu-id="a6c71-229">既存のクラス定義を削除し、`ImagePrediction` クラスを含む次のコードを *ImagePrediction.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-229">Remove the existing class definition and add the following code, which has the `ImagePrediction` class, to the *ImagePrediction.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/ImagePrediction.cs#DeclareTypes)]

<span data-ttu-id="a6c71-230">`ImagePrediction` は、画像予測クラスであり、次のフィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="a6c71-230">`ImagePrediction` is the image prediction class and has the following fields:</span></span>

* <span data-ttu-id="a6c71-231">`Score` には、指定した画像分類の信頼度が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6c71-231">`Score` contains the confidence percentage for a given image classification.</span></span>
* <span data-ttu-id="a6c71-232">`PredictedLabelValue` には、予測された画像分類ラベルの値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6c71-232">`PredictedLabelValue` contains a value for the predicted image classification label.</span></span>

<span data-ttu-id="a6c71-233">`ImagePrediction` は、モデルがトレーニングされた後に、予測に使用されるクラスです。</span><span class="sxs-lookup"><span data-stu-id="a6c71-233">`ImagePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="a6c71-234">これには画像パスの `string` (`ImagePath`) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-234">It has a `string` (`ImagePath`) for the image path.</span></span> <span data-ttu-id="a6c71-235">`Label` はモデルの再利用と再トレーニングに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-235">The `Label` is used to reuse and retrain the model.</span></span> <span data-ttu-id="a6c71-236">`PredictedLabelValue` は予測と評価の際に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-236">The `PredictedLabelValue` is used during prediction and evaluation.</span></span> <span data-ttu-id="a6c71-237">評価では、トレーニング データを含む入力、予測された値、およびモデルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-237">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="a6c71-238">[MLContext クラス](xref:Microsoft.ML.MLContext)は、すべての ML.NET 操作の開始点で、`mlContext` を初期化することで、モデル作成ワークフローのオブジェクト間で共有できる新しい ML.NET 環境が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-238">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="a6c71-239">これは Entity Framework における `DBContext` と概念的には同じです。</span><span class="sxs-lookup"><span data-stu-id="a6c71-239">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="a6c71-240">Main で変数を初期化する</span><span class="sxs-lookup"><span data-stu-id="a6c71-240">Initialize variables in Main</span></span>

<span data-ttu-id="a6c71-241">新しいインスタンスの `MLContext` を使用して `mlContext` 変数を初期化します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-241">Initialize the `mlContext` variable with a new instance of `MLContext`.</span></span>  <span data-ttu-id="a6c71-242">`Main` メソッドの `Console.WriteLine("Hello World!")` 行を、次のコードで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-242">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CreateMLContext)]

### <a name="create-a-struct-for-default-parameters"></a><span data-ttu-id="a6c71-243">既定のパラメーター用に構造体を作成する</span><span class="sxs-lookup"><span data-stu-id="a6c71-243">Create a struct for default parameters</span></span>

<span data-ttu-id="a6c71-244">Inception モデルには、渡す必要がある既定のパラメーターがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="a6c71-244">The Inception model has several default parameters you need to pass in.</span></span> <span data-ttu-id="a6c71-245">次のコードを使用して、`Main()` メソッドの直後に、既定のパラメーター値をフレンドリ名にマップする構造体を作成します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-245">Create a struct to map the default parameter values to friendly names with the following code, just after the `Main()` method:</span></span>

[!code-csharp[InceptionSettings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a><span data-ttu-id="a6c71-246">表示ユーティリティ メソッドを作成する</span><span class="sxs-lookup"><span data-stu-id="a6c71-246">Create a display utility method</span></span>

<span data-ttu-id="a6c71-247">画像データとそれに関連する予測を複数回表示するので、画像と予測結果の表示を処理する表示ユーティリティ メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-247">Since you'll display the image data and the related predictions more than once, create a display utility method to handle displaying the image and prediction results.</span></span>

<span data-ttu-id="a6c71-248">`DisplayResults()` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-248">The `DisplayResults()` method executes the following tasks:</span></span>

* <span data-ttu-id="a6c71-249">予測された結果を表示する。</span><span class="sxs-lookup"><span data-stu-id="a6c71-249">Displays the predicted results.</span></span>

<span data-ttu-id="a6c71-250">`InceptionSettings` 構造体の直後に、次のコードを使用して `DisplayResults()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-250">Create the `DisplayResults()` method, just after the `InceptionSettings` struct, using the following code:</span></span>

```csharp
private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
{

}
```

<span data-ttu-id="a6c71-251">`Transform()` メソッドによって、予測済みフィールドと共に `ImagePrediction` に `ImagePath` が設定されました。</span><span class="sxs-lookup"><span data-stu-id="a6c71-251">The `Transform()` method populated `ImagePath` in `ImagePrediction` along with the predicted fields.</span></span> <span data-ttu-id="a6c71-252">ML.NET プロセスが進むにつれて、各コンポーネントに列が追加されます。これで、結果が簡単に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-252">As the ML.NET process progresses, each component adds columns, and this makes it easy to display the results:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPredictions)]

<span data-ttu-id="a6c71-253">2 つの画像分類メソッドのうち `DisplayResults()` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-253">You'll call the `DisplayResults()` method in the two image classification methods.</span></span>

### <a name="create-a-tsv-file-utility-method"></a><span data-ttu-id="a6c71-254">.tsv ファイル ユーティリティ メソッドを作成する</span><span class="sxs-lookup"><span data-stu-id="a6c71-254">Create a .tsv file utility method</span></span>

<span data-ttu-id="a6c71-255">`ReadFromTsv()` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-255">The `ReadFromTsv()` method executes the following tasks:</span></span>

* <span data-ttu-id="a6c71-256">画像データ `tags.tsv` ファイルを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="a6c71-256">Reads the image data `tags.tsv` file.</span></span>
* <span data-ttu-id="a6c71-257">画像ファイル名のファイル パスを追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-257">Adds the file path to the image file name.</span></span>
* <span data-ttu-id="a6c71-258">ファイル データを IEnumerable `ImageData` オブジェクトに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-258">Loads the file data into an IEnumerable`ImageData` object.</span></span>

<span data-ttu-id="a6c71-259">`PairAndDisplayResults()` メソッドの直後に、次のコードを使用して `ReadFromTsv()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-259">Create the `ReadFromTsv()` method, just after the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
{

}
```

<span data-ttu-id="a6c71-260">次のコードは、`tags.tsv` ファイルを解析して、ファイルパスを `ImagePath` プロパティの画像ファイル名に追加し、それと `Label` を `ImageData` オブジェクトに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-260">The following code parses through the `tags.tsv` file to add the file path to the image file name for the `ImagePath` property and load it and the `Label` into an `ImageData` object.</span></span> <span data-ttu-id="a6c71-261">`ReadFromTsv()` メソッドの最初の行として追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-261">Add it as the first line of the `ReadFromTsv()` method.</span></span>  <span data-ttu-id="a6c71-262">予測結果を表示するには、完全修飾ファイル パスが必要です。</span><span class="sxs-lookup"><span data-stu-id="a6c71-262">You need the fully qualified file path to display the prediction results.</span></span>

[!code-csharp[ReadFromTsv](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTsv)]
<span data-ttu-id="a6c71-263">ML.NET には、次の 3 つの主要な概念があります。[データ](../resources/glossary.md#data)、[トランスフォーマー](../resources/glossary.md#transformer)、および[エスティメーター](../resources/glossary.md#estimator)です。</span><span class="sxs-lookup"><span data-stu-id="a6c71-263">There are three major concepts in ML.NET: [Data](../resources/glossary.md#data), [Transformers](../resources/glossary.md#transformer), and [Estimators](../resources/glossary.md#estimator).</span></span>

## <a name="reuse-and-tune-pre-trained-model"></a><span data-ttu-id="a6c71-264">トレーニング済みのモデルを再利用して調整する</span><span class="sxs-lookup"><span data-stu-id="a6c71-264">Reuse and tune pre-trained model</span></span>

<span data-ttu-id="a6c71-265">`Main()` メソッドの次のコード行として、`ReuseAndTuneInceptionModel()` メソッドに次の呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-265">Add the following call to the `ReuseAndTuneInceptionModel()`method as the next line of code in the `Main()` method:</span></span>

[!code-csharp[CallReuseAndTuneInceptionModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReuseAndTuneInceptionModel)]

<span data-ttu-id="a6c71-266">`ReuseAndTuneInceptionModel()` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-266">The `ReuseAndTuneInceptionModel()` method executes the following tasks:</span></span>

* <span data-ttu-id="a6c71-267">データを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-267">Loads the data</span></span>
* <span data-ttu-id="a6c71-268">データを抽出して変換します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-268">Extracts and transforms the data.</span></span>
* <span data-ttu-id="a6c71-269">TensorFlow モデルにスコアを付けます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-269">Scores the TensorFlow model.</span></span>
* <span data-ttu-id="a6c71-270">モデルを調整 (再トレーニング) します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-270">Tunes (retrains) the model.</span></span>
* <span data-ttu-id="a6c71-271">モデルの結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-271">Displays model results.</span></span>
* <span data-ttu-id="a6c71-272">モデルを評価します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-272">Evaluates the model.</span></span>
* <span data-ttu-id="a6c71-273">モデルを返します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-273">Returns the model.</span></span>

<span data-ttu-id="a6c71-274">`InceptionSettings` 構造体の直後、かつ `DisplayResults()` メソッドの直前に、次のコードを使用して `ReuseAndTuneInceptionModel()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-274">Create the `ReuseAndTuneInceptionModel()` method, just after the `InceptionSettings` struct and just before the `DisplayResults()` method, using the following code:</span></span>

```csharp
public static ITransformer ReuseAndTuneInceptionModel(MLContext mlContext, string dataLocation, string imagesFolder, string inputModelLocation, string outputModelLocation)
{

}
```

### <a name="load-the-data"></a><span data-ttu-id="a6c71-275">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="a6c71-275">Load the data</span></span>

<span data-ttu-id="a6c71-276">ML.NET 内のデータは、[IDataView クラス](xref:Microsoft.ML.IDataView)として表されます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-276">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="a6c71-277">`IDataView` は、表形式のデータ (数値とテキスト) を表すための柔軟で効率的な方法です。</span><span class="sxs-lookup"><span data-stu-id="a6c71-277">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="a6c71-278">データはテキスト ファイルから、またはリアルタイムで (SQL データベースやログ ファイルなど) `IDataView` オブジェクトに読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-278">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="a6c71-279">`MLContext.Data.LoadFromTextFile` ラッパーを使用して、データを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-279">Load the data using the `MLContext.Data.LoadFromTextFile` wrapper.</span></span> <span data-ttu-id="a6c71-280">`ReuseAndTuneInceptionModel()` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-280">Add the following code as the next line in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadData "Load the data")]

### <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="a6c71-281">特徴を抽出してデータを変換する</span><span class="sxs-lookup"><span data-stu-id="a6c71-281">Extract Features and transform the data</span></span>

<span data-ttu-id="a6c71-282">データの前処理とクリーニングは、機械学習でデータ セットを効果的に使用する前に発生する重要なタスクです。</span><span class="sxs-lookup"><span data-stu-id="a6c71-282">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span>  <span data-ttu-id="a6c71-283">これらのモデル化タスクを行わずにデータを使用すると、誤解を招く結果が生じるおそれがあります。</span><span class="sxs-lookup"><span data-stu-id="a6c71-283">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="a6c71-284">機械学習アルゴリズムは、[特徴を生成した](../resources/glossary.md#feature)データを理解します。ディープ ニューラル ネットワークを扱うときは、画像をネットワークで想定されている形式に合わせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6c71-284">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, and when dealing with deep neural networks you must adapt the images to the format expected by the network.</span></span> <span data-ttu-id="a6c71-285">その形式は、[数値ベクトル](../resources/glossary.md#numerical-feature-vector)です。</span><span class="sxs-lookup"><span data-stu-id="a6c71-285">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="a6c71-286">トレーニングと評価の後、**Label** 列の値を使用して予測します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-286">After training and evaluation, predict with the **Label** column values.</span></span> <span data-ttu-id="a6c71-287">トレーニング済みのモデルを使用しているので、[MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) メソッドを使用してフィールドを新しいモデルにマップします。</span><span class="sxs-lookup"><span data-stu-id="a6c71-287">As you're using a pre-trained model, map fields to the new model with the [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) method.</span></span> <span data-ttu-id="a6c71-288">このメソッドは、`Label` を数値キー型 (`LabelTokey`) の列に変換し、それを新しいデータセット列として追加します。トレーナーも追加するので、これに `estimator` と名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-288">This method transforms the `Label` into a numeric key type (`LabelTokey`) column and add it as new dataset column:  Name this `estimator` as you'll also add the trainer to it.</span></span> <span data-ttu-id="a6c71-289">次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-289">Add the next line of code:</span></span>

[!code-csharp[MapValueToKey1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey1)]

<span data-ttu-id="a6c71-290">画像処理エスティメーターは、特徴の抽出のために事前にトレーニングされた[ディープ ニューラル ネットワーク (DNN)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks) フィーチャライザーを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-290">Your image processing estimator uses pre-trained [Deep Neural Network(DNN)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks) featurizers for feature extraction.</span></span> <span data-ttu-id="a6c71-291">ディープ ニューラル ネットワークを扱うときは、画像を想定されているネットワーク形式に合わせます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-291">When dealing with deep neural networks, you  adapt the images to the expected network format.</span></span> <span data-ttu-id="a6c71-292">これが、画像データをモデルの想定されている形式に変換するために複数の画像変換を使用する理由です。</span><span class="sxs-lookup"><span data-stu-id="a6c71-292">This is the reason you use several image transforms to get the image data into the model's expected form:</span></span>

1. <span data-ttu-id="a6c71-293">`LoadImages` 変換画像は、ビットマップ型としてメモリに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-293">The `LoadImages`transform images are loaded in memory as a Bitmap type.</span></span>
2. <span data-ttu-id="a6c71-294">トレーニング済みのモデルには定義された入力画像の幅と高さがあるので、`ResizeImages` 変換は画像のサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-294">The `ResizeImages` transform resizes the images as the pre-trained model has a defined input image width and height.</span></span>
3. <span data-ttu-id="a6c71-295">`ExtractPixels` 変換は入力画像からピクセルを抽出し、それを数値ベクトルに変換します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-295">The `ExtractPixels` transform extracts the pixels from the input images and converts them into a numeric vector.</span></span>

<span data-ttu-id="a6c71-296">これらの画像変換を次のコード行として追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-296">Add these image transforms as the next lines of code:</span></span>

[!code-csharp[ImageTransforms](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ImageTransforms)]

<span data-ttu-id="a6c71-297">`LoadTensorFlowModel` は、`TensorFlow` モデルを一度読み込んでから `ScoreTensorFlowModel` を使用して `TensorFlowEstimator` を作成する場合に便利なメソッドです。</span><span class="sxs-lookup"><span data-stu-id="a6c71-297">The `LoadTensorFlowModel` is a convenience method that allows the `TensorFlow` model to be loaded once and then creates the `TensorFlowEstimator` using `ScoreTensorFlowModel`.</span></span> <span data-ttu-id="a6c71-298">`ScoreTensorFlowModel` は指定された出力 (`Inception model` の画像の特徴 `softmax2_pre_activation`) を抽出し、トレーニング済みの `TensorFlow` モデルを使用してデータセットにスコアを付けます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-298">The `ScoreTensorFlowModel` extracts specified outputs (the `Inception model`'s image features `softmax2_pre_activation`), and scores a dataset using the pre-trained `TensorFlow` model.</span></span>

<span data-ttu-id="a6c71-299">`softmax2_pre_activation` は、画像がどのクラスに属するかを判断できるようにモデルを支援します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-299">`softmax2_pre_activation` assists the model with determining which class the images belongs to.</span></span> <span data-ttu-id="a6c71-300">`softmax2_pre_activation` は、画像の各カテゴリの確率を返します。また、確率をすべて合計すると、常に 1 になります。</span><span class="sxs-lookup"><span data-stu-id="a6c71-300">`softmax2_pre_activation` returns a probability for each of the categories for an image, and all of those probabilities must add up to 1.</span></span> <span data-ttu-id="a6c71-301">次の例に示すように、画像は 1 つのカテゴリにのみ属すると想定しています。</span><span class="sxs-lookup"><span data-stu-id="a6c71-301">It assumes that an image will belong to only one category, as shown in the following example:</span></span>

| <span data-ttu-id="a6c71-302">クラス</span><span class="sxs-lookup"><span data-stu-id="a6c71-302">Class</span></span>         | <span data-ttu-id="a6c71-303">確率</span><span class="sxs-lookup"><span data-stu-id="a6c71-303">Probability</span></span>   |
| ------------- | ------------- |
| `Food`        |  <span data-ttu-id="a6c71-304">0.001</span><span class="sxs-lookup"><span data-stu-id="a6c71-304">0.001</span></span>        |
| `Toy`         |  <span data-ttu-id="a6c71-305">0.95</span><span class="sxs-lookup"><span data-stu-id="a6c71-305">0.95</span></span>         |
| `Appliance`   |  <span data-ttu-id="a6c71-306">0.06</span><span class="sxs-lookup"><span data-stu-id="a6c71-306">0.06</span></span>         |

<span data-ttu-id="a6c71-307">次のコード行を使用して、`TensorFlowTransform` を `estimator` に追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-307">Append the `TensorFlowTransform` to the `estimator` with the following line of code:</span></span>

[!code-csharp[ScoreTensorFlowModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ScoreTensorFlowModel)]

### <a name="choose-a-training-algorithm"></a><span data-ttu-id="a6c71-308">トレーニング アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="a6c71-308">Choose a training algorithm</span></span>

<span data-ttu-id="a6c71-309">トレーニング アルゴリズムを追加するには、`mlContext.MulticlassClassification.Trainers.LbfgsMaximumEntropy()` ラッパー メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-309">To add the training algorithm, call the `mlContext.MulticlassClassification.Trainers.LbfgsMaximumEntropy()` wrapper method.</span></span>  <span data-ttu-id="a6c71-310">[LbfgsMaximumEntropy](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer) は `estimator` に追加され、Inception 画像の特徴 (`softmax2_pre_activation`) および `Label` 入力パラメーターを受け入れて、履歴データから学習します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-310">The [LbfgsMaximumEntropy](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer) is appended to the `estimator` and accepts the Inception image features (`softmax2_pre_activation`) and the `Label` input parameters to learn from the historic data.</span></span>  <span data-ttu-id="a6c71-311">次のコードを使用してトレーナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-311">Add the trainer with the following code:</span></span>

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddTrainer)]

<span data-ttu-id="a6c71-312">また、`predictedlabel` を `predictedlabelvalue` にマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6c71-312">You also need to map the `predictedlabel` to the `predictedlabelvalue`:</span></span>

[!code-csharp[MapValueToKey2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey2)]

<span data-ttu-id="a6c71-313">`Fit()` メソッドでは、データセットを変換して、トレーニングを適用することにより、モデルがトレーニングされます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-313">The `Fit()` method trains your model by transforming the dataset and applying the training.</span></span> <span data-ttu-id="a6c71-314">`ReuseAndTuneInceptionModel()` メソッドの次のコード行として以下を追加して、モデルをトレーニング データセットに適合させ、トレーニング済みモデルを返します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-314">Fit the model to the training dataset and return the trained model by adding the following as the next line of code in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TrainModel)]

<span data-ttu-id="a6c71-315">[Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) メソッドはテスト データセットの指定した複数の入力行に対して予測を行います。</span><span class="sxs-lookup"><span data-stu-id="a6c71-315">The [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method makes predictions for multiple provided input rows of a test dataset.</span></span>  <span data-ttu-id="a6c71-316">次のコードを `ReuseAndTuneInceptionModel()` に追加して、`Training` データを変換します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-316">Transform the `Training` data by adding the following code to `ReuseAndTuneInceptionModel()`:</span></span>

[!code-csharp[TransformData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TransformData)]

<span data-ttu-id="a6c71-317">表示を簡単にするために、画像データと予測の `DataViews` を厳密に型指定された `IEnumerables` に変換します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-317">Convert your image data and prediction `DataViews` into strongly-typed `IEnumerables` to pair for easier display.</span></span> <span data-ttu-id="a6c71-318">この処理を行うには、次のコードを使用して `MLContext.CreateEnumerable()` メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-318">Use the `MLContext.CreateEnumerable()` method to do that, using the following code:</span></span>

[!code-csharp[EnumerateDataViews](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#EnumerateDataViews)]

<span data-ttu-id="a6c71-319">`ReuseAndTuneInceptionModel()` メソッドの次の行として、`DisplayResults()` メソッドを呼び出してデータと予測を表示します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-319">Call the `DisplayResults()` method to display your data and predictions as the next line in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[CallDisplayResults1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults1)]

<span data-ttu-id="a6c71-320">予測セットを作成したら、[Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-320">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method:</span></span>

* <span data-ttu-id="a6c71-321">モデルを評価します (予測値と実際のデータセット `Labels` を比較します)。</span><span class="sxs-lookup"><span data-stu-id="a6c71-321">Assesses the model (compares the predicted values with the actual dataset `Labels`).</span></span>

* <span data-ttu-id="a6c71-322">モデルのパフォーマンス メトリックを返します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-322">Returns the model performance metrics.</span></span>

<span data-ttu-id="a6c71-323">`ReuseAndTuneInceptionModel()` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-323">Add the following code to the `ReuseAndTuneInceptionModel()` method as the next line:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Evaluate)]

<span data-ttu-id="a6c71-324">画像分類では、次のメトリックが評価されます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-324">The following metrics are evaluated for image classification:</span></span>

* <span data-ttu-id="a6c71-325">`Log-loss` - 「[対数損失](../resources/glossary.md#log-loss)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6c71-325">`Log-loss` - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="a6c71-326">対数損失は可能な限り 1 に近づけます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-326">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="a6c71-327">`Per class Log-loss`。</span><span class="sxs-lookup"><span data-stu-id="a6c71-327">`Per class Log-loss`.</span></span> <span data-ttu-id="a6c71-328">クラスごとの対数損失は可能な限り 1 に近づけます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-328">You want per class Log-loss to be as close to zero as possible.</span></span>

<span data-ttu-id="a6c71-329">次のコードを使用してメトリックを表示し、結果を共有し、それに対してアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-329">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayMetrics)]

 <span data-ttu-id="a6c71-330">次の行としてトレーニング済みモデルを返すように次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-330">Add the following code to return the trained model as the next line:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReturnModel)]

## <a name="classify-images-with-a-loaded-model"></a><span data-ttu-id="a6c71-331">読み込み済みのモデルを使用して画像を分類する</span><span class="sxs-lookup"><span data-stu-id="a6c71-331">Classify images with a loaded model</span></span>

<span data-ttu-id="a6c71-332">`Main` メソッドの次のコード行として、`ClassifyImages()` メソッドに次の呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-332">Add the following call to the `ClassifyImages()` method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallClassifyImages](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifyImages)]

<span data-ttu-id="a6c71-333">`ClassifyImages()` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-333">The `ClassifyImages()` method executes the following tasks:</span></span>

* <span data-ttu-id="a6c71-334">.TSV ファイルを `IEnumerable` に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-334">Reads .TSV file into `IEnumerable`.</span></span>
* <span data-ttu-id="a6c71-335">テスト データに基づいて画像分類を予測します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-335">Predicts image classifications based on test data.</span></span>

<span data-ttu-id="a6c71-336">`ReuseAndTuneInceptionModel()` メソッドの直後、かつ `PairAndDisplayResults()` メソッドの直前に、次のコードを使用して `ClassifyImages()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-336">Create the `ClassifyImages()` method, just after the `ReuseAndTuneInceptionModel()` method and just before the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static void ClassifyImages(MLContext mlContext, string dataLocation, string imagesFolder, string outputModelLocation, ITransformer model)
{

}
```

<span data-ttu-id="a6c71-337">まず `ReadFromTsv()` メソッドを呼び出して、各 `ImagePath` の完全修飾パスを含む `IEnumerable<ImageData>` クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-337">First, call the `ReadFromTsv()` method to create an `IEnumerable<ImageData>` class that contains the fully qualified path for each `ImagePath`.</span></span> <span data-ttu-id="a6c71-338">データと予測結果を組み合わせるには、そのファイル パスが必要です。</span><span class="sxs-lookup"><span data-stu-id="a6c71-338">You need that file path to pair your data and prediction results.</span></span> <span data-ttu-id="a6c71-339">また、`IEnumerable<ImageData>` クラスを `IDataView` に変換して予測に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6c71-339">You also need to convert the `IEnumerable<ImageData>` class to an `IDataView` that you will use to predict.</span></span> <span data-ttu-id="a6c71-340">`ClassifyImages()` メソッドの次の 2 行として次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-340">Add the following code as the next two lines in the `ClassifyImages()` method:</span></span>

[!code-csharp[CallReadFromTSV](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReadFromTSV)]

<span data-ttu-id="a6c71-341">トレーニング画像データを使用して以前に実行したように、渡されたモデルの [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) メソッドを使用してテスト画像データのカテゴリを予測します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-341">As you did previously with the training image data, predict the category of the test image data using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method of the model passed in.</span></span> <span data-ttu-id="a6c71-342">予測のために次のコードを `ClassifyImages()` メソッドに追加し、ペアリングと表示のために `predictions` `IDataView` を `IEnumerable` に変換します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-342">Add the following code to the `ClassifyImages()` method for the predictions and to convert the `predictions` `IDataView` into an `IEnumerable` for pairing and display:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Predict)]

<span data-ttu-id="a6c71-343">テスト画像データと予測を組み合わせて表示するには、次のコードを追加して、`ClassifyImages()` メソッドの次の行として以前に作成した `DisplayResults()` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-343">To pair and display your test image data and predictions, add the following code to call the `DisplayResults()` method previously created as the next line in the `ClassifyImages()` method:</span></span>

[!code-csharp[CallDisplayResults2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults2)]

## <a name="classify-a-single-image-with-a-loaded-model"></a><span data-ttu-id="a6c71-344">読み込み済みのモデルを使用して単一の画像を分類する</span><span class="sxs-lookup"><span data-stu-id="a6c71-344">Classify a single image with a loaded model</span></span>

<span data-ttu-id="a6c71-345">`Main` メソッドの次のコード行として、`ClassifySingleImage()` メソッドに次の呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-345">Add the following call to the `ClassifySingleImage()` method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallClassifySingleImage](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifySingleImage)]

<span data-ttu-id="a6c71-346">`ClassifySingleImage()` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-346">The `ClassifySingleImage()` method executes the following tasks:</span></span>

* <span data-ttu-id="a6c71-347">`ImageData` インスタンスを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-347">Loads an `ImageData` instance.</span></span>
* <span data-ttu-id="a6c71-348">テスト データに基づいて画像分類を予測します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-348">Predicts image classification based on test data.</span></span>

<span data-ttu-id="a6c71-349">`ClassifyImages()` メソッドの直後、かつ `PairAndDisplayResults()` メソッドの直前に、次のコードを使用して `ClassifySingleImage()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-349">Create the `ClassifySingleImage()` method, just after the `ClassifyImages()` method and just before the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static void ClassifySingleImage(MLContext mlContext, string imagePath, string outputModelLocation, ITransformer model)
{

}
```

<span data-ttu-id="a6c71-350">まず 1 つの `ImagePath` の完全修飾パスと画像ファイル名を含む `ImageData` クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-350">First, create an `ImageData` class that contains the fully qualified path and image file name for the single `ImagePath`.</span></span> <span data-ttu-id="a6c71-351">`ClassifySingleImage()` メソッドの次の行として、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-351">Add the following code as the next  lines in the `ClassifySingleImage()` method:</span></span>

[!code-csharp[LoadImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadImageData)]

<span data-ttu-id="a6c71-352">[PredictionEngine クラス](xref:Microsoft.ML.PredictionEngine%602)は、単一のデータ インスタンスに対して予測を実行する便利な API です。</span><span class="sxs-lookup"><span data-stu-id="a6c71-352">The [PredictionEngine class](xref:Microsoft.ML.PredictionEngine%602) is a convenience API that performs a prediction on a single instance of data.</span></span> <span data-ttu-id="a6c71-353">[Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) 関数はデータの 1 つの列で予測を行います。</span><span class="sxs-lookup"><span data-stu-id="a6c71-353">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single column of data.</span></span> <span data-ttu-id="a6c71-354">次のコードを `ClassifySingleImage()` に追加して、`imageData` を `PredictionEngine` に渡して画像カテゴリを予測します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-354">Pass `imageData` to the `PredictionEngine` to predict the image category by adding the following code to `ClassifySingleImage()`:</span></span>

[!code-csharp[PredictSingle](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#PredictSingle)]

<span data-ttu-id="a6c71-355">`ClassifySingleImage()` メソッドの次のコード行として予測結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="a6c71-355">Display the prediction result as the next line of code in the `ClassifySingleImage()` method:</span></span>

[!code-csharp[DisplayPrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPrediction)]

## <a name="results"></a><span data-ttu-id="a6c71-356">結果</span><span class="sxs-lookup"><span data-stu-id="a6c71-356">Results</span></span>

<span data-ttu-id="a6c71-357">上記の手順を実行した後、コンソール アプリを実行します (Ctrl + F5 キー)。</span><span class="sxs-lookup"><span data-stu-id="a6c71-357">After following the previous steps, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="a6c71-358">結果は以下の出力のようになるはずです。</span><span class="sxs-lookup"><span data-stu-id="a6c71-358">Your results should be similar to the following output.</span></span>  <span data-ttu-id="a6c71-359">警告メッセージまたは処理中のメッセージが表示される場合がありますが、わかりやすくするため、これらのメッセージは結果から削除してあります。</span><span class="sxs-lookup"><span data-stu-id="a6c71-359">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

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
=============== Making classifications ===============
Image: broccoli.png predicted as: food with score: 0.905548
Image: pizza3.jpg predicted as: food with score: 0.9709008
Image: teddy6.jpg predicted as: toy with score: 0.9750155
=============== Making single image classification ===============
Image: toaster3.jpg predicted as: appliance with score: 0.9625379

C:\Program Files\dotnet\dotnet.exe (process 4304) exited with code 0.
Press any key to close this window . . .
```

<span data-ttu-id="a6c71-360">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="a6c71-360">Congratulations!</span></span> <span data-ttu-id="a6c71-361">これで、ML.NET でトレーニング済みの `TensorFlow` モデルを再利用して画像分類用の機械学習モデルを構築できました。</span><span class="sxs-lookup"><span data-stu-id="a6c71-361">You've now successfully built a machine learning model for image classification by reusing a pre-trained `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="a6c71-362">このチュートリアルのソース コードは [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) リポジトリで確認できます。</span><span class="sxs-lookup"><span data-stu-id="a6c71-362">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span>

<span data-ttu-id="a6c71-363">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="a6c71-363">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="a6c71-364">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="a6c71-364">Understand the problem</span></span>
> * <span data-ttu-id="a6c71-365">トレーニング済みのモデルを再利用して調整する</span><span class="sxs-lookup"><span data-stu-id="a6c71-365">Reuse and tune the pre-trained model</span></span>
> * <span data-ttu-id="a6c71-366">読み込み済みのモデルを使用して画像を分類する</span><span class="sxs-lookup"><span data-stu-id="a6c71-366">Classify images with a loaded model</span></span>

<span data-ttu-id="a6c71-367">Machine Learning サンプルの GitHub リポジトリを確認し、拡張された画像分類サンプルを探索してください。</span><span class="sxs-lookup"><span data-stu-id="a6c71-367">Check out the Machine Learning samples GitHub repository to explore an expanded image classification sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="a6c71-368">dotnet/machinelearning-samples GitHub リポジトリ</span><span class="sxs-lookup"><span data-stu-id="a6c71-368">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/)
