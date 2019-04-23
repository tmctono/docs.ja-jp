---
title: センチメント分析のバイナリ分類のシナリオで ML.NET を使用する
description: バイナリ分類のシナリオで ML.NET を使用する方法を学習して、センチメント予測をどのように使用して適切なアクションを実行するかを理解します。
ms.date: 03/07/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: e88a85b96c1e5d33d748332991cb9480222a9c66
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612096"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a><span data-ttu-id="301e5-103">チュートリアル: センチメント分析のバイナリ分類のシナリオで ML.NET を使用する</span><span class="sxs-lookup"><span data-stu-id="301e5-103">Tutorial: Use ML.NET in a sentiment analysis binary classification scenario</span></span>

<span data-ttu-id="301e5-104">このサンプル チュートリアルでは、ML.NET を使用して、肯定的または否定的な感情のいずれかを予測するセンチメント分類器の作成を示します。これは、Visual Studio 2017 で C# を使用する .NET Core コンソール アプリケーションを通して実行されます。</span><span class="sxs-lookup"><span data-stu-id="301e5-104">This sample tutorial illustrates using ML.NET to create a sentiment classifier to predict either positive or negative sentiment via a .NET Core console application using C# in Visual Studio 2017.</span></span> <span data-ttu-id="301e5-105">機械学習の世界では、この種の予測は二項分類と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="301e5-105">In the world of machine learning, this type of prediction is known as binary classification.</span></span>

> [!NOTE]
> <span data-ttu-id="301e5-106">このトピックは現在プレビュー中の ML.NET について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="301e5-106">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="301e5-107">詳細については、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="301e5-107">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="301e5-108">このチュートリアルと関連サンプルでは、現時点では **ML.NET バージョン 0.11** が使用されています。</span><span class="sxs-lookup"><span data-stu-id="301e5-108">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="301e5-109">詳細については、リリース ノート ([GitHub リポジトリの dotnet/machinelearning ](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="301e5-109">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)</span></span>

<span data-ttu-id="301e5-110">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="301e5-110">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="301e5-111">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="301e5-111">Understand the problem</span></span>
> * <span data-ttu-id="301e5-112">適切な機械学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="301e5-112">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="301e5-113">データを準備する</span><span class="sxs-lookup"><span data-stu-id="301e5-113">Prepare your data</span></span>
> * <span data-ttu-id="301e5-114">データを変換する</span><span class="sxs-lookup"><span data-stu-id="301e5-114">Transform the data</span></span>
> * <span data-ttu-id="301e5-115">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="301e5-115">Train the model</span></span>
> * <span data-ttu-id="301e5-116">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="301e5-116">Evaluate the model</span></span>
> * <span data-ttu-id="301e5-117">トレーニング済みモデルを使用して予測する</span><span class="sxs-lookup"><span data-stu-id="301e5-117">Predict with the trained model</span></span>
> * <span data-ttu-id="301e5-118">読み込み済みのモデルを使用して配置および予測する</span><span class="sxs-lookup"><span data-stu-id="301e5-118">Deploy and Predict with a loaded model</span></span>

## <a name="sentiment-analysis-sample-overview"></a><span data-ttu-id="301e5-119">センチメント分析のサンプルの概要</span><span class="sxs-lookup"><span data-stu-id="301e5-119">Sentiment analysis sample overview</span></span>

<span data-ttu-id="301e5-120">このサンプルは ML.NET を使用するコンソール アプリケーションであり、センチメントを分類して肯定的か否定的かを予測するモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="301e5-120">The sample is a console app that uses ML.NET to train a model that classifies and predicts sentiment as either positive or negative.</span></span> <span data-ttu-id="301e5-121">Yelp センチメント データセットは、カリフォルニア大学アーバイン校 (UCI) 提供のデータセットです。これがトレーニング データセットとテスト データセットに分割されます。</span><span class="sxs-lookup"><span data-stu-id="301e5-121">The Yelp sentiment dataset is from University of California, Irvine (UCI), which is split into a train dataset and a test dataset.</span></span> <span data-ttu-id="301e5-122">サンプルでは、テスト データセットを使用してモデルを評価して、品質分析を実行します。</span><span class="sxs-lookup"><span data-stu-id="301e5-122">The sample evaluates the model with the test dataset for quality analysis.</span></span>

<span data-ttu-id="301e5-123">このチュートリアルのソース コードは [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) リポジトリで確認できます。</span><span class="sxs-lookup"><span data-stu-id="301e5-123">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="301e5-124">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="301e5-124">Prerequisites</span></span>

* <span data-ttu-id="301e5-125">[Visual Studio 2017 15.6 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)が ".NET Core クロスプラット フォーム開発" とともにインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="301e5-125">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* [<span data-ttu-id="301e5-126">UCI Sentiment Labeled Sentences データセット zip ファイル</span><span class="sxs-lookup"><span data-stu-id="301e5-126">The UCI Sentiment Labeled Sentences dataset zip file</span></span>](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)

## <a name="machine-learning-workflow"></a><span data-ttu-id="301e5-127">機械学習ワークフロー</span><span class="sxs-lookup"><span data-stu-id="301e5-127">Machine learning workflow</span></span>

<span data-ttu-id="301e5-128">このチュートリアルでは、プロセスを順序立てて進められるようにする機械学習ワークフローに従います。</span><span class="sxs-lookup"><span data-stu-id="301e5-128">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="301e5-129">このワークフローには次のフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="301e5-129">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="301e5-130">**問題を把握する**</span><span class="sxs-lookup"><span data-stu-id="301e5-130">**Understand the problem**</span></span>
2. <span data-ttu-id="301e5-131">**データを準備する**</span><span class="sxs-lookup"><span data-stu-id="301e5-131">**Prepare your data**</span></span>
   * <span data-ttu-id="301e5-132">**データを読み込む**</span><span class="sxs-lookup"><span data-stu-id="301e5-132">**Load the data**</span></span>
   * <span data-ttu-id="301e5-133">**特徴を抽出する (データを変換する)**</span><span class="sxs-lookup"><span data-stu-id="301e5-133">**Extract features (Transform your data)**</span></span>
3. <span data-ttu-id="301e5-134">**ビルドしてトレーニングする**</span><span class="sxs-lookup"><span data-stu-id="301e5-134">**Build and train**</span></span>
   * <span data-ttu-id="301e5-135">**モデルをトレーニングする**</span><span class="sxs-lookup"><span data-stu-id="301e5-135">**Train the model**</span></span>
   * <span data-ttu-id="301e5-136">**モデルを評価する**</span><span class="sxs-lookup"><span data-stu-id="301e5-136">**Evaluate the model**</span></span>
4. <span data-ttu-id="301e5-137">**モデルの配置**</span><span class="sxs-lookup"><span data-stu-id="301e5-137">**Deploy Model**</span></span>
   * <span data-ttu-id="301e5-138">**モデルを使用して予測する**</span><span class="sxs-lookup"><span data-stu-id="301e5-138">**Use the Model to predict**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="301e5-139">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="301e5-139">Understand the problem</span></span>

<span data-ttu-id="301e5-140">まず、問題を把握して、モデルのビルドおよびトレーニングに使用できるパーツに分ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="301e5-140">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="301e5-141">問題を分けることで、結果の予測および評価ができるようになります。</span><span class="sxs-lookup"><span data-stu-id="301e5-141">Breaking the problem down allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="301e5-142">このチュートリアルでの問題は、書き込まれた Web サイト コメントのセンチメントを解釈して適切なアクションを実行することです。</span><span class="sxs-lookup"><span data-stu-id="301e5-142">The problem for this tutorial is to understand incoming website comment sentiment to take the appropriate action.</span></span>

<span data-ttu-id="301e5-143">この問題は、モデルのトレーニングに使用するセンチメント テキストおよびセンチメント値と、評価して運用に使用することができる予測されたセンチメント値に分けることができます。</span><span class="sxs-lookup"><span data-stu-id="301e5-143">You can break down the problem to the sentiment text and sentiment value for the data you want to train the model with, and a predicted sentiment value that you can evaluate and then use operationally.</span></span>

<span data-ttu-id="301e5-144">次に、センチメントを**決定**する必要があります。これは機械学習タスクを選択するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="301e5-144">You then need to **determine** the sentiment, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-algorithm"></a><span data-ttu-id="301e5-145">適切な機械学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="301e5-145">Select the appropriate machine learning algorithm</span></span>

<span data-ttu-id="301e5-146">この問題に関してわかっていることは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="301e5-146">With this problem, you know the following facts:</span></span>

<span data-ttu-id="301e5-147">トレーニング データ: Web サイトのコメントは、肯定的 (1) または否定的 (0) (**センチメント**) のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="301e5-147">Training data: website comments can be positive (1) or negative (0) (**sentiment**).</span></span>

<span data-ttu-id="301e5-148">次の例のような、新しい Web サイト コメントの**センチメント**が肯定的か否定的かを予測します。</span><span class="sxs-lookup"><span data-stu-id="301e5-148">Predict the **sentiment** of a new website comment, either positive or negative, such as in the following examples:</span></span>

* <span data-ttu-id="301e5-149">ここの給仕スタッフは最高です。</span><span class="sxs-lookup"><span data-stu-id="301e5-149">I love the wait staff here.</span></span> <span data-ttu-id="301e5-150">とても有能です。</span><span class="sxs-lookup"><span data-stu-id="301e5-150">They rock.</span></span>
* <span data-ttu-id="301e5-151">この場所のスープは最悪です。</span><span class="sxs-lookup"><span data-stu-id="301e5-151">This place has the worst soup.</span></span>

<span data-ttu-id="301e5-152">このシナリオには、分類機械学習アルゴリズムが適しています。</span><span class="sxs-lookup"><span data-stu-id="301e5-152">The classification machine learning algorithm is best suited for this scenario.</span></span>

### <a name="about-the-classification-algorithm"></a><span data-ttu-id="301e5-153">分類アルゴリズムについて</span><span class="sxs-lookup"><span data-stu-id="301e5-153">About the classification algorithm</span></span>

<span data-ttu-id="301e5-154">分類は、データを使用して項目またはデータ行のカテゴリ、型、クラスを**判断**する機械学習アルゴリズムです。</span><span class="sxs-lookup"><span data-stu-id="301e5-154">Classification is a machine learning algorithm that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="301e5-155">分類はたとえば、次のような目的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="301e5-155">For example, you can use classification to:</span></span>

* <span data-ttu-id="301e5-156">センチメントが肯定的か否定的かを判断する。</span><span class="sxs-lookup"><span data-stu-id="301e5-156">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="301e5-157">電子メールをスパム、迷惑メール、正常なメールに分類する。</span><span class="sxs-lookup"><span data-stu-id="301e5-157">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="301e5-158">患者の検体が癌性かどうかを判断する。</span><span class="sxs-lookup"><span data-stu-id="301e5-158">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="301e5-159">顧客を販売キャンペーンへの反応性で分類する。</span><span class="sxs-lookup"><span data-stu-id="301e5-159">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="301e5-160">多くの場合、分類アルゴリズムは次のいずれかの種類です。</span><span class="sxs-lookup"><span data-stu-id="301e5-160">Classification algorithms are frequently one of the following types:</span></span>

* <span data-ttu-id="301e5-161">バイナリ: A か B のいずれかである。</span><span class="sxs-lookup"><span data-stu-id="301e5-161">Binary: either A or B.</span></span>
* <span data-ttu-id="301e5-162">多クラス: 1 つのモデルを使用して予測できるカテゴリが多数ある。</span><span class="sxs-lookup"><span data-stu-id="301e5-162">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="301e5-163">Web サイトのコメントは、肯定的または否定的のいずれかとして分類する必要があるため、二項分類アルゴリズムが使用されます。</span><span class="sxs-lookup"><span data-stu-id="301e5-163">Because the website comments need to be classified as either positive or negative, you use the Binary Classification algorithm.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="301e5-164">コンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="301e5-164">Create a console application</span></span>

1. <span data-ttu-id="301e5-165">Visual Studio 2017 を開きます。</span><span class="sxs-lookup"><span data-stu-id="301e5-165">Open Visual Studio 2017.</span></span> <span data-ttu-id="301e5-166">**[ファイル]** > **[新規作成]** > **[プロジェクト]** をメニュー バーから選択します。</span><span class="sxs-lookup"><span data-stu-id="301e5-166">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="301e5-167">**[新しいプロジェクト]** ダイアログで、**[Visual C#]** ノードを選択し、**[.NET Core]** ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="301e5-167">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="301e5-168">次に、**[コンソール アプリ (.NET Core)]** プロジェクト テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="301e5-168">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="301e5-169">**[名前]** テキスト ボックスに「SentimentAnalysis」と入力し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="301e5-169">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="301e5-170">プロジェクトに *Data* という名前のディレクトリを作成して、データ セット ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="301e5-170">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="301e5-171">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[追加]** > **[新しいフォルダー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="301e5-171">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="301e5-172">「Data」と入力して Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="301e5-172">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="301e5-173">**Microsoft.ML NuGet パッケージ**をインストールします。</span><span class="sxs-lookup"><span data-stu-id="301e5-173">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="301e5-174">ソリューション エクスプローラーで、プロジェクトを右クリックし、**[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="301e5-174">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="301e5-175">[パッケージ ソース] として "nuget.org" を選択し、[参照] タブを選択して「**Microsoft.ML**」を検索します。一覧からそのパッケージを選択し、**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="301e5-175">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="301e5-176">**[変更のプレビュー]** ダイアログの **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、**[ライセンスの同意]** ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="301e5-176">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="301e5-177">データを準備する</span><span class="sxs-lookup"><span data-stu-id="301e5-177">Prepare your data</span></span>

1. <span data-ttu-id="301e5-178">[UCI Sentiment Labeled Sentences データセット zip ファイル (次の注の引用を参照)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) をダウンロードして解凍します。</span><span class="sxs-lookup"><span data-stu-id="301e5-178">Download [The UCI Sentiment Labeled Sentences dataset zip file (see citations in the following note)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip.</span></span>

2. <span data-ttu-id="301e5-179">`yelp_labelled.txt` ファイルを、作成した *Data* ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="301e5-179">Copy the `yelp_labelled.txt` file into the *Data* directory you created.</span></span>

> [!NOTE]
> <span data-ttu-id="301e5-180">このチュートリアルで使用されるデータセットは、「From Group to Individual Labels using Deep Features」 (Kotzias 他</span><span class="sxs-lookup"><span data-stu-id="301e5-180">The datasets this tutorial uses are from the 'From Group to Individual Labels using Deep Features', Kotzias et.</span></span> <span data-ttu-id="301e5-181">著、</span><span class="sxs-lookup"><span data-stu-id="301e5-181">al,.</span></span> <span data-ttu-id="301e5-182">KDD 2015) のものであり、UCI 機械学習リポジトリ (Dua, D. and Karra Taniskidou, E.(2017)) でホストされています。</span><span class="sxs-lookup"><span data-stu-id="301e5-182">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="301e5-183">UCI 機械学習リポジトリ [http://archive.ics.uci.edu/ml]。</span><span class="sxs-lookup"><span data-stu-id="301e5-183">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="301e5-184">カリフォルニア州アーバイン: カリフォルニア大学情報コンピュータサイエンス学部。</span><span class="sxs-lookup"><span data-stu-id="301e5-184">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

3. <span data-ttu-id="301e5-185">ソリューション エクスプローラーで、`yelp_labeled.txt` ファイルを右クリックし、**[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="301e5-185">In Solution Explorer, right-click the `yelp_labeled.txt` file and select **Properties**.</span></span> <span data-ttu-id="301e5-186">**[詳細設定]** で、**[出力ディレクトリにコピー]** の値を **[新しい場合はコピーする]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="301e5-186">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="301e5-187">クラスを作成してパスを定義する</span><span class="sxs-lookup"><span data-stu-id="301e5-187">Create classes and define paths</span></span>

<span data-ttu-id="301e5-188">次に示す追加の `using` ステートメントを *Program.cs* ファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="301e5-188">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddUsings "Add necessary usings")]

<span data-ttu-id="301e5-189">最近ダウンロードしたデータセット ファイルのパスと保存したモデル ファイルのパスを保持するために、2 つのグローバル フィールドを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="301e5-189">You need to create two global fields to hold the recently downloaded dataset file path and the saved model file path:</span></span>

* <span data-ttu-id="301e5-190">`_dataPath` には、モデルのトレーニングに使用するデータ セットのパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="301e5-190">`_dataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="301e5-191">`_modelPath` には、トレーニング済みのモデルを保存するパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="301e5-191">`_modelPath` has the path where the trained model is saved.</span></span>

<span data-ttu-id="301e5-192">`Main` メソッドのすぐ上にある行に次のコードを追加して、それらのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="301e5-192">Add the following code to the line right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DeclareGlobalVariables "Declare global variables")]

<span data-ttu-id="301e5-193">入力データと予測のために、いくつかのクラスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="301e5-193">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="301e5-194">プロジェクトに新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="301e5-194">Add a new class to your project:</span></span>

1. <span data-ttu-id="301e5-195">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[追加]** > **[新しい項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="301e5-195">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="301e5-196">**[新しい項目の追加]** ダイアログ ボックスで、**[クラス]** を選択し、**[名前]** フィールドを *SentimentData.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="301e5-196">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="301e5-197">次に、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="301e5-197">Then, select the **Add** button.</span></span>

    <span data-ttu-id="301e5-198">コード エディターで *SentimentData.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="301e5-198">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="301e5-199">*SentimentData.cs* の先頭に次の `using` ステートメントを 追加します。</span><span class="sxs-lookup"><span data-stu-id="301e5-199">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#AddUsings "Add necessary usings")]

<span data-ttu-id="301e5-200">既存のクラス定義を削除し、`SentimentData` と `SentimentPrediction` の 2 つのクラスを含む次のコードを *SentimentData.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="301e5-200">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

[!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#DeclareTypes "Declare data record types")]

<span data-ttu-id="301e5-201">入力データセット クラス `SentimentData` には、コメントの `string` (`SentimentText`) と、肯定的または否定的のいずれかであるセンチメントの値を持つ `bool` (`Sentiment`) があります。</span><span class="sxs-lookup"><span data-stu-id="301e5-201">The input dataset class, `SentimentData`, has a `string` for the comment (`SentimentText`) and a `bool` (`Sentiment`) that has a value for sentiment of either positive or negative.</span></span> <span data-ttu-id="301e5-202">どちらのフィールドにも <xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29> 属性が添付されています。</span><span class="sxs-lookup"><span data-stu-id="301e5-202">Both fields have <xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29> attributes attached to them.</span></span> <span data-ttu-id="301e5-203">この属性は、データ ファイルの各フィールドの順序を示しています。</span><span class="sxs-lookup"><span data-stu-id="301e5-203">This attribute describes the order of each field in the data file.</span></span>  <span data-ttu-id="301e5-204">さらに、`Sentiment` プロパティには、それを `Label` フィールドとして指定する <xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A> があります。</span><span class="sxs-lookup"><span data-stu-id="301e5-204">In addition, the `Sentiment` property has a <xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A> to designate it as the `Label` field.</span></span> <span data-ttu-id="301e5-205">`SentimentPrediction` は、モデルがトレーニングされた後に、予測に使用されるクラスです。</span><span class="sxs-lookup"><span data-stu-id="301e5-205">`SentimentPrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="301e5-206">これは、1 つのブール値 (`Sentiment`) と、`PredictedLabel` `ColumnName` 属性を持ちます。</span><span class="sxs-lookup"><span data-stu-id="301e5-206">It has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="301e5-207">`Label` はモデルを作成してトレーニングするために使用され、モデルを評価するための分割されたテスト データセットでも使用されます。</span><span class="sxs-lookup"><span data-stu-id="301e5-207">The `Label` is used to create and train the model, and it's also used with the split out test dataset to evaluate the model.</span></span> <span data-ttu-id="301e5-208">`PredictedLabel` は予測と評価の際に使用されます。</span><span class="sxs-lookup"><span data-stu-id="301e5-208">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="301e5-209">評価では、トレーニング データを含む入力、予測された値、およびモデルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="301e5-209">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="301e5-210">ML.NET を使用してモデルをビルドするときは、まず <xref:Microsoft.ML.MLContext> を作成します。</span><span class="sxs-lookup"><span data-stu-id="301e5-210">When building a model with ML.NET you start by creating an <xref:Microsoft.ML.MLContext>.</span></span> <span data-ttu-id="301e5-211">`MLContext` は、概念的には Entity Framework での `DbContext` の使用に相当します。</span><span class="sxs-lookup"><span data-stu-id="301e5-211">`MLContext` is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="301e5-212">環境によって、例外の追跡とログ記録に使用できる ML ジョブのコンテキストが提供されます。</span><span class="sxs-lookup"><span data-stu-id="301e5-212">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="301e5-213">Main で変数を初期化する</span><span class="sxs-lookup"><span data-stu-id="301e5-213">Initialize variables in Main</span></span>

<span data-ttu-id="301e5-214">`mlContext` という変数を作成し、`MLContext` の新しいインスタンスで初期化します。</span><span class="sxs-lookup"><span data-stu-id="301e5-214">Create a variable called `mlContext` and initialize it with a new instance of `MLContext`.</span></span>  <span data-ttu-id="301e5-215">`Main` メソッドの `Console.WriteLine("Hello World!")` 行を、次のコードで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="301e5-215">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateMLContext "Create the ML Context")]

<span data-ttu-id="301e5-216">`Main` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="301e5-216">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallLoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallLoadData)]

<span data-ttu-id="301e5-217">`LoadData` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="301e5-217">The `LoadData` method executes the following tasks:</span></span>

* <span data-ttu-id="301e5-218">データを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="301e5-218">Loads the data.</span></span>
* <span data-ttu-id="301e5-219">読み込んだデータセットを、トレーニングデータセットとテスト データセットに分割します。</span><span class="sxs-lookup"><span data-stu-id="301e5-219">Splits the loaded dataset into train and test datasets.</span></span>
* <span data-ttu-id="301e5-220">分割されたトレーニングデータセットとテスト データセットを返します。</span><span class="sxs-lookup"><span data-stu-id="301e5-220">Returns the split train and test datasets.</span></span>

<span data-ttu-id="301e5-221">`Main` メソッドの直後に、次のコードを使用して `LoadData` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="301e5-221">Create the `LoadData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static TrainCatalogBase.TrainTestData LoadData(MLContext mlContext)
{

}
```

## <a name="load-the-data"></a><span data-ttu-id="301e5-222">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="301e5-222">Load the data</span></span>

<span data-ttu-id="301e5-223">前に作成した `SentimentData` データ モデルの種類がデータセット スキーマと一致するため、[LoadFromTextFile メソッド](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)の `MLContext.Data.LoadFromTextFile` ラッパーを使用して、初期化、マッピング、およびデータセットの読み込みを 1 行のコードに組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="301e5-223">Since your previously created `SentimentData` data model type matches the dataset schema, you can combine the initialization, mapping, and dataset loading into one line of code using the `MLContext.Data.LoadFromTextFile` wrapper for the [LoadFromTextFile method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span></span> <span data-ttu-id="301e5-224"><xref:Microsoft.Data.DataView.IDataView> が返されます。</span><span class="sxs-lookup"><span data-stu-id="301e5-224">It returns a <xref:Microsoft.Data.DataView.IDataView>.</span></span>

<span data-ttu-id="301e5-225">`Transforms` の入力および出力として、`DataView` は基本的なデータ パイプラインの種類であり、`LINQ` の `IEnumerable` と同等です。</span><span class="sxs-lookup"><span data-stu-id="301e5-225">As the input and output of `Transforms`, a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="301e5-226">ML.NET ではデータは SQL ビューに似ています。</span><span class="sxs-lookup"><span data-stu-id="301e5-226">In ML.NET, data is similar to a SQL view.</span></span> <span data-ttu-id="301e5-227">つまり、遅延評価、体系的、異種です。</span><span class="sxs-lookup"><span data-stu-id="301e5-227">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="301e5-228">オブジェクトはパイプラインの最初の部分であり、データを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="301e5-228">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="301e5-229">このチュートリアルでは、コメントと対応する有害または無害のセンチメントを含むデータセットが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="301e5-229">For this tutorial, it loads a dataset with comments and corresponding toxic or non toxic sentiment.</span></span> <span data-ttu-id="301e5-230">これを使用して、モデルを作成してトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="301e5-230">This is used to create the model, and train it.</span></span>

<span data-ttu-id="301e5-231">`LoadData` メソッドの最初の行として、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="301e5-231">Add the following code as the first line of the `LoadData` method:</span></span>

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadData "loading dataset")]

### <a name="split-the-dataset-for-model-training-and-testing"></a><span data-ttu-id="301e5-232">モデルのトレーニング用とテスト用にデータセットを分割する</span><span class="sxs-lookup"><span data-stu-id="301e5-232">Split the dataset for model training and testing</span></span>

<span data-ttu-id="301e5-233">次に、モデルをトレーニングするためのトレーニング データセットと、モデルを評価するためのテスト データセットの両方が必要です。</span><span class="sxs-lookup"><span data-stu-id="301e5-233">Next, you need both a training dataset to train the model and a test dataset to evaluate the model.</span></span> <span data-ttu-id="301e5-234"><xref:Microsoft.ML.StaticPipe.TrainingStaticExtensions.TrainTestSplit%2A> をラップする `MLContext.BinaryClassification.TrainTestSplit` を使用して、読み込まれたデータセットをトレーニング データセットとテスト データセットに分割し、それらを <xref:Microsoft.ML.TrainCatalogBase.TrainTestData> に返します。</span><span class="sxs-lookup"><span data-stu-id="301e5-234">Use the `MLContext.BinaryClassification.TrainTestSplit` which wraps <xref:Microsoft.ML.StaticPipe.TrainingStaticExtensions.TrainTestSplit%2A> to split the loaded dataset into train and test datasets and return them inside of a <xref:Microsoft.ML.TrainCatalogBase.TrainTestData>.</span></span> <span data-ttu-id="301e5-235">`testFraction` パラメーターを使用して、テスト セット用のデータの割合を指定できます。</span><span class="sxs-lookup"><span data-stu-id="301e5-235">You can specify the fraction of data for the test set with the `testFraction`parameter.</span></span> <span data-ttu-id="301e5-236">既定値は 10% ですが、ここでは、評価でより多くのデータを使用するために 20% を使用します。</span><span class="sxs-lookup"><span data-stu-id="301e5-236">The default is 10% but you use 20% in this case to use more data for the evaluation.</span></span>

<span data-ttu-id="301e5-237">読み込まれたデータを必要なデータセットに分割するには、`LoadData` メソッドの次の行として、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="301e5-237">To split the loaded data into the needed datasets, add the following code as the next line in the `LoadData` method:</span></span>

[!code-csharp[SplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SplitData "Split the Data")]

<span data-ttu-id="301e5-238">`LoadData` メソッドの最後に、`splitDataView` が返されます。</span><span class="sxs-lookup"><span data-stu-id="301e5-238">Return the `splitDataView` at the end of the `LoadData` method:</span></span>

[!code-csharp[ReturnSplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a><span data-ttu-id="301e5-239">モデルを構築してトレーニングする</span><span class="sxs-lookup"><span data-stu-id="301e5-239">Build and train the model</span></span>

<span data-ttu-id="301e5-240">`Main` メソッドの次のコード行として、`BuildAndTrainModel` メソッドに次の呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="301e5-240">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="301e5-241">`BuildAndTrainModel` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="301e5-241">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="301e5-242">データを抽出して変換します。</span><span class="sxs-lookup"><span data-stu-id="301e5-242">Extracts and transforms the data.</span></span>
* <span data-ttu-id="301e5-243">モデルをトレーニングする。</span><span class="sxs-lookup"><span data-stu-id="301e5-243">Trains the model.</span></span>
* <span data-ttu-id="301e5-244">テスト データに基づいてセンチメントを予測する。</span><span class="sxs-lookup"><span data-stu-id="301e5-244">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="301e5-245">モデルを返します。</span><span class="sxs-lookup"><span data-stu-id="301e5-245">Returns the model.</span></span>

<span data-ttu-id="301e5-246">`Main` メソッドの直後に、次のコードを使用して `BuildAndTrainModel` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="301e5-246">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
{

}
```

<span data-ttu-id="301e5-247">Train メソッドに 2 つのパラメーターが渡されていることに注意してください。`MLContext` はコンテキスト (`mlContext`)、`IDataView` はトレーニング データセット (`splitTrainSet`) に関するものです。</span><span class="sxs-lookup"><span data-stu-id="301e5-247">Notice that two parameters are passed into the Train method; a `MLContext` for the context (`mlContext`), and an `IDataView`for the training dataset (`splitTrainSet`).</span></span>

## <a name="extract-and-transform-the-data"></a><span data-ttu-id="301e5-248">データを抽出して変換する</span><span class="sxs-lookup"><span data-stu-id="301e5-248">Extract and transform the data</span></span>

<span data-ttu-id="301e5-249">データの前処理とクリーニングは、機械学習でデータ セットを効果的に使用する前に発生する重要なタスクです。</span><span class="sxs-lookup"><span data-stu-id="301e5-249">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="301e5-250">多くの場合、生データはノイズが多くて信頼性が低く、値が欠落している可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="301e5-250">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="301e5-251">これらのモデル化タスクを行わずにデータを使用すると、誤解を招く結果が生じるおそれがあります。</span><span class="sxs-lookup"><span data-stu-id="301e5-251">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="301e5-252">ML.NET の変換パイプラインによって、トレーニングまたはテストの前にデータに適用するカスタム変換セットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="301e5-252">ML.NET's transform pipelines compose a custom set of transforms that are applied to your data before training or testing.</span></span> <span data-ttu-id="301e5-253">この変換の主な目的は、データの[特徴付け](../resources/glossary.md#feature-engineering)です。</span><span class="sxs-lookup"><span data-stu-id="301e5-253">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="301e5-254">機械学習アルゴリズムによって理解されるのは、[特徴付け](../resources/glossary.md#feature)されたデータです。したがって、次の手順では、テキスト データを ML アルゴリズムが認識できる形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="301e5-254">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="301e5-255">その形式は、[数値ベクトル](../resources/glossary.md#numerical-feature-vector)です。</span><span class="sxs-lookup"><span data-stu-id="301e5-255">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="301e5-256">次に、`mlContext.Transforms.Text.FeaturizeText` を呼び出します。これによってテキスト列 (`SentimentText`) が特徴付けされ、機械学習アルゴリズムで使用される `Features` という数値ベクトルになります。</span><span class="sxs-lookup"><span data-stu-id="301e5-256">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text column (`SentimentText`) column into a numeric vector called `Features` used by the machine learning algorithm.</span></span> <span data-ttu-id="301e5-257">これは、実質的にパイプラインになる <xref:Microsoft.ML.Data.EstimatorChain%601> を返すラッパー呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="301e5-257">This is a wrapper call that returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="301e5-258">後でトレーナーを `EstimatorChain` に付加するときに、この `pipeline` を指定します。</span><span class="sxs-lookup"><span data-stu-id="301e5-258">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="301e5-259">次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="301e5-259">Add this as the next line of code:</span></span>

[!code-csharp[FeaturizeText](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#FeaturizeText "Featurize the text")]

>[!WARNING]
> <span data-ttu-id="301e5-260">ML.NET バージョン 0.10 では、変換パラメーターの順序が変更されました。</span><span class="sxs-lookup"><span data-stu-id="301e5-260">ML.NET Version 0.10 changed the order of the Transform parameters.</span></span> <span data-ttu-id="301e5-261">アプリケーションを実行してモデルを構築するまで、これによるエラーは出力されません。</span><span class="sxs-lookup"><span data-stu-id="301e5-261">This will not error out until you run the application and build the model.</span></span> <span data-ttu-id="301e5-262">変換パラメーターの名前を上記のコード スニペットに示すように使用してください。</span><span class="sxs-lookup"><span data-stu-id="301e5-262">Use the parameter names for Transforms as illustrated in the previous code snippet.</span></span>

<span data-ttu-id="301e5-263">これが前処理/特徴付けのステップです。</span><span class="sxs-lookup"><span data-stu-id="301e5-263">This is the preprocessing/featurization step.</span></span> <span data-ttu-id="301e5-264">ML.NET に用意されているその他のコンポーネントを使用すると、モデルでより良い結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="301e5-264">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="301e5-265">学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="301e5-265">Choose a learning algorithm</span></span>

<span data-ttu-id="301e5-266">トレーナーを追加するには、<xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer> オブジェクトを返す `mlContext.BinaryClassification.Trainers.FastTree` ラッパー メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="301e5-266">To add the trainer, call the `mlContext.BinaryClassification.Trainers.FastTree` wrapper method which returns a <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer> object.</span></span> <span data-ttu-id="301e5-267">これは、このパイプラインで使用するデシジョン ツリーの学習器です。</span><span class="sxs-lookup"><span data-stu-id="301e5-267">This is a decision tree learner you'll use in this pipeline.</span></span> <span data-ttu-id="301e5-268">`FastTreeBinaryClassificationTrainer` が `pipeline` に追加されます。これは、特徴付けされた `SentimentText` (`Features`) と `Label` 入力パラメーターを受け入れて、履歴データから学習します。</span><span class="sxs-lookup"><span data-stu-id="301e5-268">The `FastTreeBinaryClassificationTrainer` is appended to the `pipeline` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

<span data-ttu-id="301e5-269">`BuildAndTrainModel` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="301e5-269">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[FastTreeBinaryClassificationTrainer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddTrainer "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="301e5-270">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="301e5-270">Train the model</span></span>

<span data-ttu-id="301e5-271">読み込まれて変換されたデータ セットに基づいて、モデル <xref:Microsoft.ML.Data.TransformerChain%601> をトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="301e5-271">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="301e5-272">推定器が定義されたら、既に読み込まれたトレーニング データを提供しながら、<xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> メソッドを使用してモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="301e5-272">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> method while providing the already loaded training data.</span></span> <span data-ttu-id="301e5-273">これにより、予測で使用されるモデルが返されます。</span><span class="sxs-lookup"><span data-stu-id="301e5-273">This returns a model to use for predictions.</span></span> <span data-ttu-id="301e5-274">`pipeline.Fit()` でパイプラインをトレーニングし、`DataView` に基づいて `Transformer` を返します。</span><span class="sxs-lookup"><span data-stu-id="301e5-274">`pipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="301e5-275">`.Fit()` メソッドが実行されるまで、実験は実行されません。</span><span class="sxs-lookup"><span data-stu-id="301e5-275">The experiment is not executed until the `.Fit()` method runs.</span></span>

<span data-ttu-id="301e5-276">`BuildAndTrainModel` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="301e5-276">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TrainModel "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="301e5-277">評価に使用する、トレーニングされたモデルを保存して返す</span><span class="sxs-lookup"><span data-stu-id="301e5-277">Save and Return the model trained to use for evaluation</span></span>

<span data-ttu-id="301e5-278">この時点で、既存または新規のどの .NET アプリケーションにも統合できる、型が <xref:Microsoft.ML.Data.TransformerChain%601> のモデルができました。</span><span class="sxs-lookup"><span data-stu-id="301e5-278">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="301e5-279">`BuildAndTrainModel` メソッドの最後で、モデルを返します。</span><span class="sxs-lookup"><span data-stu-id="301e5-279">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="301e5-280">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="301e5-280">Evaluate the model</span></span>

<span data-ttu-id="301e5-281">これでモデルの作成とトレーニングが完了したので、品質保証と検証のために、別のデータ セットを使用してモデルを評価します。</span><span class="sxs-lookup"><span data-stu-id="301e5-281">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="301e5-282">`Evaluate` メソッドでは、`BuildAndTrainModel` で作成されたモデルが渡されて評価されます。</span><span class="sxs-lookup"><span data-stu-id="301e5-282">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="301e5-283">`BuildAndTrainModel` の直後に、次のコードに示すように `Evaluate` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="301e5-283">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
{

}
```

<span data-ttu-id="301e5-284">`Evaluate` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="301e5-284">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="301e5-285">テスト データ セットを読み込む。</span><span class="sxs-lookup"><span data-stu-id="301e5-285">Loads the test dataset.</span></span>
* <span data-ttu-id="301e5-286">binaryclassification 評価器を作成します。</span><span class="sxs-lookup"><span data-stu-id="301e5-286">Creates the binaryclassification evaluator.</span></span>
* <span data-ttu-id="301e5-287">モデルを評価し、メトリックを作成する。</span><span class="sxs-lookup"><span data-stu-id="301e5-287">Evaluates the model and creates metrics.</span></span>
* <span data-ttu-id="301e5-288">メトリックを表示する。</span><span class="sxs-lookup"><span data-stu-id="301e5-288">Displays the metrics.</span></span>

<span data-ttu-id="301e5-289">`Train` メソッドの呼び出しのすぐ下に、次のコードを使用して、`Main` メソッドからの新しいメソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="301e5-289">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallEvaluate "Call the Evaluate method")]

<span data-ttu-id="301e5-290">次に、機械学習の `model` パラメーター (変換器) と `splitTestSet` パラメーターを使用して特徴を入力し、予測を返します。</span><span class="sxs-lookup"><span data-stu-id="301e5-290">Next, you'll use the machine learning `model` parameter (a transformer) and the `splitTestSet` parameter to input the features and return predictions.</span></span> <span data-ttu-id="301e5-291">`Evaluate` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="301e5-291">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TransformData "Predict using the Transformer")]

<span data-ttu-id="301e5-292">`mlContext.BinaryClassification.Evaluate` メソッドは、指定されたデータセットを使用して `PredictionModel` の品質メトリックを計算します。</span><span class="sxs-lookup"><span data-stu-id="301e5-292">The `mlContext.BinaryClassification.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="301e5-293">これによって返される <xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics> オブジェクトには、バイナリ分類評価器によって計算されるメトリック全体が含まれます。</span><span class="sxs-lookup"><span data-stu-id="301e5-293">It returns a <xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics> object that contains the overall metrics computed by binary classification evaluators.</span></span> <span data-ttu-id="301e5-294">これらを表示してモデルの品質を判定するには、最初にメトリックを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="301e5-294">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="301e5-295">`Evaluate` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="301e5-295">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Evaluate "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="301e5-296">モデル検証のためのメトリックを表示する</span><span class="sxs-lookup"><span data-stu-id="301e5-296">Displaying the metrics for model validation</span></span>

<span data-ttu-id="301e5-297">次のコードを使用してメトリックを表示し、結果を共有し、それに対してアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="301e5-297">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayMetrics "Display selected metrics")]

<span data-ttu-id="301e5-298">モデルを返す前に .zip ファイルに保存するには、`Evaluate` 内に次の行を追加して `SaveModelAsFile` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="301e5-298">To save your model to a .zip file before returning, add the following code to call the `SaveModelAsFile` method as the next line in `Evaluate`:</span></span>

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallSaveModel "Save the model")]

## <a name="save-the-model-as-azip-file"></a><span data-ttu-id="301e5-299">モデルを .zip ファイルとして保存する</span><span class="sxs-lookup"><span data-stu-id="301e5-299">Save the model as a.zip file</span></span>

<span data-ttu-id="301e5-300">`Evaluate` メソッドの直後に、次のコードを使用して `SaveModelAsFile` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="301e5-300">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="301e5-301">`SaveModelAsFile` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="301e5-301">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="301e5-302">モデルを .zip ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="301e5-302">Saves the model as a .zip file.</span></span>

<span data-ttu-id="301e5-303">次に、モデルを再利用して他のアプリケーションで使用できるようにモデルを保存するメソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="301e5-303">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="301e5-304">`ITransformer` には <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> メソッドがあり、`_modelPath` グローバル フィールドと <xref:System.IO.Stream> を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="301e5-304">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="301e5-305">これを zip ファイルとして保存するには、`FileStream` を作成した直後に `SaveTo` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="301e5-305">To save this as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="301e5-306">`SaveModelAsFile` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="301e5-306">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveToMethod](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SaveModel "Add the SaveTo Method")]

<span data-ttu-id="301e5-307">`_modelPath` を使用してコンソール メッセージを記述することで、ファイルが書き込まれた場所も表示できるようになります。これには次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="301e5-307">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-saved-model"></a><span data-ttu-id="301e5-308">保存したモデルを使用してテスト データの結果を予測する</span><span class="sxs-lookup"><span data-stu-id="301e5-308">Predict the test data outcome with the saved model</span></span>

<span data-ttu-id="301e5-309">`Evaluate` メソッドの直後に、次のコードを使用して `UseModelWithSingleItem` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="301e5-309">Create the `UseModelWithSingleItem` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="301e5-310">`UseModelWithSingleItem` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="301e5-310">The `UseModelWithSingleItem` method executes the following tasks:</span></span>

* <span data-ttu-id="301e5-311">テスト データの 1 つのコメントを作成する。</span><span class="sxs-lookup"><span data-stu-id="301e5-311">Creates a single comment of test data.</span></span>
* <span data-ttu-id="301e5-312">テスト データに基づいてセンチメントを予測する。</span><span class="sxs-lookup"><span data-stu-id="301e5-312">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="301e5-313">テスト データと予測をレポート用に結合する。</span><span class="sxs-lookup"><span data-stu-id="301e5-313">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="301e5-314">予測された結果を表示する。</span><span class="sxs-lookup"><span data-stu-id="301e5-314">Displays the predicted results.</span></span>

<span data-ttu-id="301e5-315">`Evaluate` メソッドの呼び出しのすぐ下に、次のコードを使用して、`Main` メソッドからの新しいメソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="301e5-315">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallUseModelWithSingleItem](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

<span data-ttu-id="301e5-316">`model` は多数のデータ行を操作する `transformer` ですが、よくある運用シナリオとして個々の例に対する予測のニーズがあります。</span><span class="sxs-lookup"><span data-stu-id="301e5-316">While the `model` is a `transformer` that operates on many rows of data, a very common production scenario is a need for predictions on individual examples.</span></span> <span data-ttu-id="301e5-317"><xref:Microsoft.ML.PredictionEngine%602> は、`CreatePredictionEngine` メソッドから返されるラッパーです。</span><span class="sxs-lookup"><span data-stu-id="301e5-317">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="301e5-318">次の行を追加して、`PredictionEngine` を `Predict` メソッドの 1 行目として作成しましょう。</span><span class="sxs-lookup"><span data-stu-id="301e5-318">Let's add the following code to create the `PredictionEngine` as the first line in the `Predict` Method:</span></span>

[!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]

<span data-ttu-id="301e5-319">コメントを追加して、`Predict` メソッドでトレーニングされたモデルの予測をテストします。これには `SentimentData` のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="301e5-319">Add a comment to test the trained model's prediction in the `Predict` method by creating an instance of `SentimentData`:</span></span>

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

 <span data-ttu-id="301e5-320">これを使用すると、コメント データの 1 つのインスタンスのセンチメントが肯定的か否定的かを予測できます。</span><span class="sxs-lookup"><span data-stu-id="301e5-320">You can use that to predict the positive or negative sentiment of a single instance of the comment data.</span></span> <span data-ttu-id="301e5-321">予測を取得するには、データに対して <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> を使用します。</span><span class="sxs-lookup"><span data-stu-id="301e5-321">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="301e5-322">入力データは文字列であり、モデルには、特徴付けが含まれることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="301e5-322">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="301e5-323">トレーニングと予測の間は、パイプラインが同期されます。</span><span class="sxs-lookup"><span data-stu-id="301e5-323">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="301e5-324">予測のために前処理/特徴付けのコードを特別に記述する必要はなく、同じ API によってバッチと 1 回限りの予測の両方が処理されます。</span><span class="sxs-lookup"><span data-stu-id="301e5-324">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Predict "Create a prediction of sentiment")]

### <a name="use-the-model-prediction"></a><span data-ttu-id="301e5-325">モデルを使用する: 予測</span><span class="sxs-lookup"><span data-stu-id="301e5-325">Use the model: prediction</span></span>

<span data-ttu-id="301e5-326">結果を共有し、それに応じたアクションを実行するために、`SentimentText` および対応するセンチメント予測を表示します。</span><span class="sxs-lookup"><span data-stu-id="301e5-326">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="301e5-327">これは運用化と呼ばれ、返されたデータを運用ポリシーとして使用します。</span><span class="sxs-lookup"><span data-stu-id="301e5-327">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="301e5-328">次の <xref:System.Console.WriteLine?displayProperty=nameWithType> コードを使用して、結果の表示を作成します。</span><span class="sxs-lookup"><span data-stu-id="301e5-328">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#OutputPrediction "Display prediction output")]

## <a name="deploy-and-predict-with-a-loaded-model"></a><span data-ttu-id="301e5-329">読み込み済みのモデルを使用して配置および予測する</span><span class="sxs-lookup"><span data-stu-id="301e5-329">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="301e5-330">`SaveModelAsFile` メソッドの直前に、次のコードを使用して `UseLoadedModelWithBatchItems` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="301e5-330">Create the `UseLoadedModelWithBatchItems` method, just before the `SaveModelAsFile` method, using the following code:</span></span>

```csharp
public static void UseLoadedModelWithBatchItems(MLContext mlContext)
{

}
```

<span data-ttu-id="301e5-331">`UseLoadedModelWithBatchItems` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="301e5-331">The `UseLoadedModelWithBatchItems` method executes the following tasks:</span></span>

* <span data-ttu-id="301e5-332">バッチ テスト データを作成します。</span><span class="sxs-lookup"><span data-stu-id="301e5-332">Creates batch test data.</span></span>
* <span data-ttu-id="301e5-333">テスト データに基づいてセンチメントを予測する。</span><span class="sxs-lookup"><span data-stu-id="301e5-333">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="301e5-334">テスト データと予測をレポート用に結合する。</span><span class="sxs-lookup"><span data-stu-id="301e5-334">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="301e5-335">予測された結果を表示する。</span><span class="sxs-lookup"><span data-stu-id="301e5-335">Displays the predicted results.</span></span>

<span data-ttu-id="301e5-336">`UseModelWithSingleItem` メソッドの呼び出しのすぐ下に、次のコードを使用して、`Main` メソッドからの新しいメソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="301e5-336">Add a call to the new method from the `Main` method, right under the `UseModelWithSingleItem` method call, using the following code:</span></span>

[!code-csharp[CallPredictModelLoaded](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseLoadedModelWithBatchItems "Call the CallUseLoadedModelWithBatchItems method")]

<span data-ttu-id="301e5-337">`UseLoadedModelWithBatchItems` メソッドでトレーニングされるモデルの予測をテストするために、いくつかのコメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="301e5-337">Add some comments to test the trained model's predictions in the `UseLoadedModelWithBatchItems` method:</span></span>

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssues "Create test data for predictions")]

<span data-ttu-id="301e5-338">モデルを読み込みます</span><span class="sxs-lookup"><span data-stu-id="301e5-338">Load the model</span></span>

[!code-csharp[LoadTheModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadModel "Load the model")]

<span data-ttu-id="301e5-339">モデルは既にあるので、それを利用して、<xref:Microsoft.ML.ITransformer.Transform%2A> メソッドでコメント データのセンチメントが有害か無害かを予測できます。</span><span class="sxs-lookup"><span data-stu-id="301e5-339">Now that you have a model, you can use that to predict the Toxic or Non Toxic sentiment of the comment data using the <xref:Microsoft.ML.ITransformer.Transform%2A> method.</span></span> <span data-ttu-id="301e5-340">予測を取得するには、新しいデータに対して `Predict` を使用します。</span><span class="sxs-lookup"><span data-stu-id="301e5-340">To get a prediction, use `Predict` on new data.</span></span> <span data-ttu-id="301e5-341">入力データは文字列であり、モデルには、特徴付けが含まれることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="301e5-341">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="301e5-342">トレーニングと予測の間は、パイプラインが同期されます。</span><span class="sxs-lookup"><span data-stu-id="301e5-342">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="301e5-343">予測のために前処理/特徴付けのコードを特別に記述する必要はなく、同じ API によってバッチと 1 回限りの予測の両方が処理されます。</span><span class="sxs-lookup"><span data-stu-id="301e5-343">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="301e5-344">予測のために `UseLoadedModelWithBatchItems` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="301e5-344">Add the following code to the `UseLoadedModelWithBatchItems` method for the predictions:</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="use-the-loaded-model-for-prediction"></a><span data-ttu-id="301e5-345">読み込み済みのモデルを予測のために使用する</span><span class="sxs-lookup"><span data-stu-id="301e5-345">Use the loaded model for prediction</span></span>

<span data-ttu-id="301e5-346">結果を共有し、それに応じたアクションを実行するために、`SentimentText` および対応するセンチメント予測を表示します。</span><span class="sxs-lookup"><span data-stu-id="301e5-346">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="301e5-347">これは運用化と呼ばれ、返されたデータを運用ポリシーとして使用します。</span><span class="sxs-lookup"><span data-stu-id="301e5-347">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="301e5-348">次の <xref:System.Console.WriteLine?displayProperty=nameWithType> コードを使用して、結果のヘッダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="301e5-348">Create a header for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputHeaders](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddInfoMessage "Display prediction outputs")]

<span data-ttu-id="301e5-349">予測された結果を表示する前に、元のコメントとその予測されたセンチメントが一緒に表示されるように、センチメントと予測を結合します。</span><span class="sxs-lookup"><span data-stu-id="301e5-349">Before displaying the predicted results, combine the sentiment and prediction together to see the original comment with its predicted sentiment.</span></span> <span data-ttu-id="301e5-350">次のコードでは <xref:System.Linq.Enumerable.Zip%2A> メソッドを使用してそれを行うため、そのコードを次に追加します。</span><span class="sxs-lookup"><span data-stu-id="301e5-350">The following code uses the <xref:System.Linq.Enumerable.Zip%2A> method to make that happen, so add that code next:</span></span>

[!code-csharp[BuildTuples](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#BuildSentimentPredictionPairs "Build the pairs of sentiment data and predictions")]

<span data-ttu-id="301e5-351">これで `SentimentText` と `Sentiment` が 1 つのクラスに結合されたので、<xref:System.Console.WriteLine?displayProperty=nameWithType> メソッドを使用して結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="301e5-351">Now that you've combined the `SentimentText` and `Sentiment` into a class, you can display the results using the <xref:System.Console.WriteLine?displayProperty=nameWithType> method:</span></span>

[!code-csharp[DisplayPredictions](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayResults "Display the predictions")]

<span data-ttu-id="301e5-352">推定されたタプル要素名は C# 7.1 の新機能であり、このプロジェクトの既定の言語バージョンは C# 7.0 であるため、言語バージョンを C# 7.1 以降に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="301e5-352">Because inferred tuple element names are a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="301e5-353">そのためには、**ソリューション エクスプローラー**でプロジェクト ノードを右クリックして、**[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="301e5-353">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="301e5-354">**[ビルド]** タブを選択し、**[詳細設定]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="301e5-354">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="301e5-355">ドロップダウンで **[C# 7.1]** (またはそれ以降のバージョン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="301e5-355">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="301e5-356">**[OK]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="301e5-356">Select the **OK** button.</span></span>

## <a name="results"></a><span data-ttu-id="301e5-357">結果</span><span class="sxs-lookup"><span data-stu-id="301e5-357">Results</span></span>

<span data-ttu-id="301e5-358">結果は以下のようになるはずです。</span><span class="sxs-lookup"><span data-stu-id="301e5-358">Your results should be similar to the following.</span></span> <span data-ttu-id="301e5-359">パイプラインが処理されると、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="301e5-359">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="301e5-360">警告または処理メッセージが表示されることがありますが、</span><span class="sxs-lookup"><span data-stu-id="301e5-360">You may see warnings, or processing messages.</span></span> <span data-ttu-id="301e5-361">わかりやすくするために、それらは次の結果から削除してあります。</span><span class="sxs-lookup"><span data-stu-id="301e5-361">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 79.14%
Auc: 86.27%
F1Score: 80.60%

=============== End of model evaluation ===============
The model is saved to C:\Tutorials\SentimentAnalysis\bin\Debug\netcoreapp2.1\Data\Model.zip

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.4641322
=============== End of Predictions ===============


=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1391833
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9819039
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

<span data-ttu-id="301e5-362">おめでとうございます! </span><span class="sxs-lookup"><span data-stu-id="301e5-362">Congratulations!</span></span> <span data-ttu-id="301e5-363">これで、メッセージのセンチメントを分類および予測するための機械学習モデルをビルドできました。</span><span class="sxs-lookup"><span data-stu-id="301e5-363">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span>

<span data-ttu-id="301e5-364">優れたモデルの構築は、反復的なプロセスです。</span><span class="sxs-lookup"><span data-stu-id="301e5-364">Building successful models is an iterative process.</span></span> <span data-ttu-id="301e5-365">このチュートリアルでは、モデルのトレーニングを短時間で実行するために小さなデータセットを使用しているため、このモデルの品質は最初は低くなっています。</span><span class="sxs-lookup"><span data-stu-id="301e5-365">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="301e5-366">このモデルの品質に満足できなければ、大規模なトレーニング データセットを使用するか、別のトレーニング アルゴリズムとアルゴリズムごとに異なるハイパーパラメーターを選択することで、モデルを改良することを試行できます。</span><span class="sxs-lookup"><span data-stu-id="301e5-366">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different hyper-parameters for each algorithm.</span></span>

<span data-ttu-id="301e5-367">このチュートリアルのソース コードは [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) リポジトリで確認できます。</span><span class="sxs-lookup"><span data-stu-id="301e5-367">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="301e5-368">次の手順</span><span class="sxs-lookup"><span data-stu-id="301e5-368">Next steps</span></span>

<span data-ttu-id="301e5-369">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="301e5-369">In this tutorial, you learned how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="301e5-370">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="301e5-370">Understand the problem</span></span>
> * <span data-ttu-id="301e5-371">適切な機械学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="301e5-371">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="301e5-372">データを準備する</span><span class="sxs-lookup"><span data-stu-id="301e5-372">Prepare your data</span></span>
> * <span data-ttu-id="301e5-373">データを変換する</span><span class="sxs-lookup"><span data-stu-id="301e5-373">Transform the data</span></span>
> * <span data-ttu-id="301e5-374">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="301e5-374">Train the model</span></span>
> * <span data-ttu-id="301e5-375">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="301e5-375">Evaluate the model</span></span>
> * <span data-ttu-id="301e5-376">トレーニング済みモデルを使用して予測する</span><span class="sxs-lookup"><span data-stu-id="301e5-376">Predict with the trained model</span></span>
> * <span data-ttu-id="301e5-377">読み込み済みのモデルを使用して配置および予測する</span><span class="sxs-lookup"><span data-stu-id="301e5-377">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="301e5-378">さらに詳しく学習するには、次のチュートリアルに進んでください。</span><span class="sxs-lookup"><span data-stu-id="301e5-378">Advance to the next tutorial to learn more</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="301e5-379">問題の分類</span><span class="sxs-lookup"><span data-stu-id="301e5-379">Issue Classification</span></span>](github-issue-classification.md)
