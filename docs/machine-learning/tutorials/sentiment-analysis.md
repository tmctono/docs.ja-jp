---
title: センチメント分析のバイナリ分類のシナリオで ML.NET を使用する
description: バイナリ分類のシナリオで ML.NET を使用する方法を学習して、センチメント予測をどのように使用して適切なアクションを実行するかを理解します。
ms.date: 02/15/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 9afdf1d8369e71f9614ebc2bf327e98d31b988ff
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "56748389"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a><span data-ttu-id="e0e2d-103">チュートリアル: センチメント分析のバイナリ分類のシナリオで ML.NET を使用する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-103">Tutorial: Use ML.NET in a sentiment analysis binary classification scenario</span></span>

> [!NOTE]
> <span data-ttu-id="e0e2d-104">このトピックは現在プレビュー中の ML.NET について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="e0e2d-105">詳細については、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="e0e2d-106">このサンプル チュートリアルでは、Visual Studio 2017 で ML.NET を使用して、C# を使用する .NET Core コンソール アプリケーションからセンチメント分類器を作成する方法を示 します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-106">This sample tutorial illustrates using ML.NET to create a sentiment classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="e0e2d-107">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="e0e2d-108">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-108">Understand the problem</span></span>
> * <span data-ttu-id="e0e2d-109">適切な機械学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-109">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="e0e2d-110">データを準備する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-110">Prepare your data</span></span>
> * <span data-ttu-id="e0e2d-111">データを変換する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-111">Transform the data</span></span>
> * <span data-ttu-id="e0e2d-112">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="e0e2d-112">Train the model</span></span>
> * <span data-ttu-id="e0e2d-113">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-113">Evaluate the model</span></span>
> * <span data-ttu-id="e0e2d-114">トレーニング済みモデルを使用して予測する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-114">Predict with the trained model</span></span>
> * <span data-ttu-id="e0e2d-115">読み込み済みのモデルを使用して配置および予測する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-115">Deploy and Predict with a loaded model</span></span>

## <a name="sentiment-analysis-sample-overview"></a><span data-ttu-id="e0e2d-116">センチメント分析のサンプルの概要</span><span class="sxs-lookup"><span data-stu-id="e0e2d-116">Sentiment analysis sample overview</span></span>

<span data-ttu-id="e0e2d-117">このサンプルは ML.NET を使用するコンソール アプリケーションであり、センチメントを分類して肯定的か否定的かを予測するモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-117">The sample is a console app that uses ML.NET to train a model that classifies and predicts sentiment as either positive or negative.</span></span> <span data-ttu-id="e0e2d-118">また、高品質な分析のために、2 番目のデータ セットを使用してモデルを評価します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-118">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="e0e2d-119">センチメントのデータ セットは、WikiDetox プロジェクトからのものです。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-119">The sentiment datasets are from the WikiDetox project.</span></span>

<span data-ttu-id="e0e2d-120">このチュートリアルのソース コードは [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) リポジトリで確認できます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-120">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e0e2d-121">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e0e2d-121">Prerequisites</span></span>

* <span data-ttu-id="e0e2d-122">[Visual Studio 2017 15.6 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)が ".NET Core クロスプラット フォーム開発" とともにインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-122">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="e0e2d-123">[Wikipedia detox line data タブ区切りファイル (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv)。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-123">The [Wikipedia detox line data tab separated file (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).</span></span>
* <span data-ttu-id="e0e2d-124">[Wikipedia detox line test タブ区切りファイル (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv)。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-124">The [Wikipedia detox line test tab separated file (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="e0e2d-125">機械学習ワークフロー</span><span class="sxs-lookup"><span data-stu-id="e0e2d-125">Machine learning workflow</span></span>

<span data-ttu-id="e0e2d-126">このチュートリアルでは、プロセスを順序立てて進められるようにする機械学習ワークフローに従います。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-126">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="e0e2d-127">このワークフローには次のフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-127">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="e0e2d-128">**問題を把握する**</span><span class="sxs-lookup"><span data-stu-id="e0e2d-128">**Understand the problem**</span></span>
2. <span data-ttu-id="e0e2d-129">**データを準備する**</span><span class="sxs-lookup"><span data-stu-id="e0e2d-129">**Prepare your data**</span></span>
   * <span data-ttu-id="e0e2d-130">**データを読み込む**</span><span class="sxs-lookup"><span data-stu-id="e0e2d-130">**Load the data**</span></span>
   * <span data-ttu-id="e0e2d-131">**特徴を抽出する (データを変換する)**</span><span class="sxs-lookup"><span data-stu-id="e0e2d-131">**Extract features (Transform your data)**</span></span>
3. <span data-ttu-id="e0e2d-132">**ビルドしてトレーニングする**</span><span class="sxs-lookup"><span data-stu-id="e0e2d-132">**Build and train**</span></span> 
   * <span data-ttu-id="e0e2d-133">**モデルをトレーニングする**</span><span class="sxs-lookup"><span data-stu-id="e0e2d-133">**Train the model**</span></span>
   * <span data-ttu-id="e0e2d-134">**モデルを評価する**</span><span class="sxs-lookup"><span data-stu-id="e0e2d-134">**Evaluate the model**</span></span>
4. <span data-ttu-id="e0e2d-135">**モデルの配置**</span><span class="sxs-lookup"><span data-stu-id="e0e2d-135">**Deploy Model**</span></span>
   * <span data-ttu-id="e0e2d-136">**モデルを使用して予測する**</span><span class="sxs-lookup"><span data-stu-id="e0e2d-136">**Use the Model to predict**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="e0e2d-137">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-137">Understand the problem</span></span>

<span data-ttu-id="e0e2d-138">まず、問題を把握して、モデルのビルドおよびトレーニングに使用できるパーツに分ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-138">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="e0e2d-139">問題を分けることで、結果の予測および評価ができるようになります。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-139">Breaking the problem down allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="e0e2d-140">このチュートリアルでの問題は、書き込まれた Web サイト コメントのセンチメントを解釈して適切なアクションを実行することです。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-140">The problem for this tutorial is to understand incoming website comment sentiment to take the appropriate action.</span></span>

<span data-ttu-id="e0e2d-141">この問題は、モデルのトレーニングに使用するセンチメント テキストおよびセンチメント値と、評価して運用に使用することができる予測されたセンチメント値に分けることができます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-141">You can break down the problem to the sentiment text and sentiment value for the data you want to train the model with, and a predicted sentiment value that you can evaluate and then use operationally.</span></span>

<span data-ttu-id="e0e2d-142">次に、センチメントを**決定**する必要があります。これは機械学習タスクを選択するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-142">You then need to **determine** the sentiment, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-algorithm"></a><span data-ttu-id="e0e2d-143">適切な機械学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-143">Select the appropriate machine learning algorithm</span></span>

<span data-ttu-id="e0e2d-144">この問題に関してわかっていることは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-144">With this problem, you know the following facts:</span></span>

<span data-ttu-id="e0e2d-145">トレーニング データである Web サイト コメントは、有害 (1) か無害 (0) (**センチメント**) のいずれかとなります。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-145">Training data: website comments can be toxic (1) or not toxic (0) (**sentiment**).</span></span>
<span data-ttu-id="e0e2d-146">次の例のような、新しい Web サイト コメントの**センチメント**が有害か無害かを予測します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-146">Predict the **sentiment** of a new website comment, either toxic or not toxic, such as in the following examples:</span></span>

* <span data-ttu-id="e0e2d-147">Wikipedia に無意味な記述を追加するのはやめてください。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-147">Please refrain from adding nonsense to Wikipedia.</span></span>
* <span data-ttu-id="e0e2d-148">彼は最高です。記事ではそのことを記述するべきです。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-148">He is the best, and the article should say that.</span></span>

<span data-ttu-id="e0e2d-149">このシナリオには、分類機械学習アルゴリズムが適しています。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-149">The classification machine learning algorithm is best suited for this scenario.</span></span>

### <a name="about-the-classification-task"></a><span data-ttu-id="e0e2d-150">分類タスクについて</span><span class="sxs-lookup"><span data-stu-id="e0e2d-150">About the classification task</span></span>

<span data-ttu-id="e0e2d-151">分類は、データを使用して項目またはデータ行のカテゴリ、型、クラスを**判断**する機械学習アルゴリズムです。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-151">Classification is a machine learning algorithm that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="e0e2d-152">分類はたとえば、次のような目的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-152">For example, you can use classification to:</span></span>

* <span data-ttu-id="e0e2d-153">センチメントが肯定的か否定的かを判断する。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-153">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="e0e2d-154">電子メールをスパム、迷惑メール、正常なメールに分類する。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-154">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="e0e2d-155">患者の検体が癌性かどうかを判断する。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-155">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="e0e2d-156">顧客を販売キャンペーンへの反応性で分類する。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-156">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="e0e2d-157">多くの場合、分類アルゴリズムは次のいずれかの種類です。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-157">Classification algorithms are frequently one of the following types:</span></span>

* <span data-ttu-id="e0e2d-158">バイナリ: A か B のいずれかである。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-158">Binary: either A or B.</span></span>
* <span data-ttu-id="e0e2d-159">多クラス: 1 つのモデルを使用して予測できるカテゴリが多数ある。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-159">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="e0e2d-160">コンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-160">Create a console application</span></span>

1. <span data-ttu-id="e0e2d-161">Visual Studio 2017 を開きます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-161">Open Visual Studio 2017.</span></span> <span data-ttu-id="e0e2d-162">**[ファイル]** > **[新規作成]** > **[プロジェクト]** をメニュー バーから選択します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-162">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="e0e2d-163">**[新しいプロジェクト]** ダイアログで、**[Visual C#]** ノードを選択し、**[.NET Core]** ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-163">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="e0e2d-164">次に、**[コンソール アプリ (.NET Core)]** プロジェクト テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-164">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="e0e2d-165">**[名前]** テキスト ボックスに「SentimentAnalysis」と入力し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-165">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="e0e2d-166">プロジェクトに *Data* という名前のディレクトリを作成して、データ セット ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-166">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="e0e2d-167">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[追加]** > **[新しいフォルダー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-167">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="e0e2d-168">「Data」と入力して Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-168">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="e0e2d-169">**Microsoft.ML NuGet パッケージ**をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-169">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="e0e2d-170">ソリューション エクスプローラーで、プロジェクトを右クリックし、**[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-170">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="e0e2d-171">[パッケージ ソース] として "nuget.org" を選択し、[参照] タブを選択して「**Microsoft.ML**」を検索します。一覧からそのパッケージを選択し、**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-171">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="e0e2d-172">**[変更のプレビュー]** ダイアログの **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、**[ライセンスの同意]** ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-172">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="e0e2d-173">データを準備する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-173">Prepare your data</span></span>

1. <span data-ttu-id="e0e2d-174">[Wikipedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) データ セットと [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) データ セットをダウンロードして、作成済みの *Data* フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-174">Download the [Wikipedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) and the [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="e0e2d-175">1 番目のデータ セットでは機械学習モデルをトレーニングし、2 番目のデータ セットはモデルの精度を評価するために使用します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-175">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="e0e2d-176">ソリューション エクスプローラーで、各 \*.tsv ファイルを右クリックし、**[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-176">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="e0e2d-177">**[詳細設定]** で、**[出力ディレクトリにコピー]** の値を **[新しい場合はコピーする]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-177">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="e0e2d-178">クラスを作成してパスを定義する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-178">Create classes and define paths</span></span>

<span data-ttu-id="e0e2d-179">次に示す追加の `using` ステートメントを *Program.cs* ファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-179">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="e0e2d-180">最近ダウンロードしたファイルのパスを保存する 3 つのグローバル フィールドと、`TextLoader` のためのグローバル変数を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-180">You need to create three global fields to hold the paths to the recently downloaded files, and a global variable for the `TextLoader`:</span></span>

* <span data-ttu-id="e0e2d-181">`_trainDataPath` には、モデルのトレーニングに使用するデータ セットのパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-181">`_trainDataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="e0e2d-182">`_testDataPath` には、モデルの評価に使用するデータ セットのパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-182">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="e0e2d-183">`_modelPath` には、トレーニング済みのモデルを保存するパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-183">`_modelPath` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="e0e2d-184">`_textLoader` は、データセットの読み込みと変換に使用される <xref:Microsoft.ML.Data.TextLoader> です。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-184">`_textLoader` is the <xref:Microsoft.ML.Data.TextLoader> used to load and transform the datasets.</span></span>

<span data-ttu-id="e0e2d-185">`Main` メソッドのすぐ上にある行に次のコードを追加して、それらのパスと `_textLoader` 変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-185">Add the following code to the line right above the `Main` method to specify those paths and the `_textLoader` variable:</span></span>

[!code-csharp[Declare global variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#2 "Declare global variables")]

<span data-ttu-id="e0e2d-186">入力データと予測のために、いくつかのクラスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-186">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="e0e2d-187">プロジェクトに新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-187">Add a new class to your project:</span></span>

1. <span data-ttu-id="e0e2d-188">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[追加]** > **[新しい項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-188">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="e0e2d-189">**[新しい項目の追加]** ダイアログ ボックスで、**[クラス]** を選択し、**[名前]** フィールドを *SentimentData.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-189">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="e0e2d-190">次に、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-190">Then, select the **Add** button.</span></span>

    <span data-ttu-id="e0e2d-191">コード エディターで *SentimentData.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-191">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="e0e2d-192">*SentimentData.cs* の先頭に次の `using` ステートメントを 追加します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-192">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#1 "Add necessary usings")]

<span data-ttu-id="e0e2d-193">既存のクラス定義を削除し、`SentimentData` と `SentimentPrediction` の 2 つのクラスを含む次のコードを *SentimentData.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-193">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#2 "Declare data record types")]

<span data-ttu-id="e0e2d-194">`SentimentData` は入力データ セット クラスで、肯定的か否定的のいずれかのセンチメント値を持つ `float` (`Sentiment`) と、コメントの文字列 (`SentimentText`) を含みます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-194">`SentimentData` is the input dataset class and has a `float` (`Sentiment`) that has a value for sentiment of either positive or negative, and a string for the comment (`SentimentText`).</span></span> <span data-ttu-id="e0e2d-195">どちらのフィールドにも `Column` 属性が添付されています。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-195">Both fields have `Column` attributes attached to them.</span></span> <span data-ttu-id="e0e2d-196">この属性はデータ ファイル内での各フィールドの順序と、どちらが `Label` フィールドであるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-196">This attribute describes the order of each field in the data file, and which is the `Label` field.</span></span> <span data-ttu-id="e0e2d-197">`SentimentPrediction` は、モデルがトレーニングされた後に、予測に使用されるクラスです。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-197">`SentimentPrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="e0e2d-198">これは、1 つのブール値 (`Sentiment`) と、`PredictedLabel` `ColumnName` 属性を持ちます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-198">It has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="e0e2d-199">`Label` はモデルを作成してトレーニングするために使用され、2 番目のデータ セットでもモデルを評価するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-199">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="e0e2d-200">`PredictedLabel` は予測と評価の際に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-200">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="e0e2d-201">評価では、トレーニング データを含む入力、予測された値、およびモデルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-201">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="e0e2d-202">ML.NET を使用してモデルをビルドするときは、まず `MLContext` を作成します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-202">When building a model with ML.NET you start by creating an `MLContext`.</span></span> <span data-ttu-id="e0e2d-203">これは、概念的には Entity Framework での `DbContext` の使用に相当します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-203">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="e0e2d-204">環境によって、例外の追跡とログ記録に使用できる ML ジョブのコンテキストが提供されます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-204">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="e0e2d-205">Main で変数を初期化する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-205">Initialize variables in Main</span></span>

<span data-ttu-id="e0e2d-206">`mlContext` という変数を作成し、`MLContext` の新しいインスタンスで初期化します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-206">Create a variable called `mlContext` and initialize it with a new instance of `MLContext`.</span></span>  <span data-ttu-id="e0e2d-207">`Main` メソッドの `Console.WriteLine("Hello World!")` 行を、次のコードで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-207">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#3 "Create the ML Context")]

<span data-ttu-id="e0e2d-208">次に、データ読み込みを設定するために、再利用できるように `_textLoader` グローバル変数を初期化します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-208">Next, to setup for data loading initialize the `_textLoader` global variable in order to reuse it.</span></span>  <span data-ttu-id="e0e2d-209">`MLContext.Data.CreateTextLoader` を使用して `TextLoader` を作成するとき、必要なコンテキストと、カスタマイズを可能にする <xref:Microsoft.ML.Data.TextLoader.Arguments> クラスを渡します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-209">When you create a `TextLoader` using  `MLContext.Data.CreateTextLoader`, you pass in the context needed and the <xref:Microsoft.ML.Data.TextLoader.Arguments> class which enables customization.</span></span>

 <span data-ttu-id="e0e2d-210">すべての列名とそれらの型を含む <xref:Microsoft.ML.Data.TextLoader.Column> オブジェクトの配列をローダーに渡して、データ スキーマを指定します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-210">Specify the data schema by passing an array of <xref:Microsoft.ML.Data.TextLoader.Column> objects to the loader containing all the column names and their types.</span></span> <span data-ttu-id="e0e2d-211">データ スキーマは、`SentimentData` クラスを作成したときに既に定義しています。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-211">You defined the data schema previously when you created our `SentimentData` class.</span></span> <span data-ttu-id="e0e2d-212">このスキーマでは、最初の列 (Label) は <xref:System.Boolean> (予測) で、2 番目の列 (SentimentText) はセンチメントの予測に使用される text/string 型の特徴です。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-212">For our schema, the first column (Label) is a <xref:System.Boolean> (the prediction) and the second column (SentimentText) is the feature of type text/string used for predicting the sentiment.</span></span>
<span data-ttu-id="e0e2d-213">`TextLoader` クラスは、完全に初期化された <xref:Microsoft.ML.Data.TextLoader> を返します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-213">The `TextLoader` class returns a fully initialized <xref:Microsoft.ML.Data.TextLoader></span></span>  

<span data-ttu-id="e0e2d-214">必要なデータセットで再利用するために `_textLoader` グローバル変数を初期化するには、`mlContext` 初期化の後に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-214">To initialize the `_textLoader` global variable in order to reuse it for the needed datasets, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[initTextLoader](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#4 "Initialize the TextLoader")]

<span data-ttu-id="e0e2d-215">`Main` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-215">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[Train](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#5 "Train your model")]

<span data-ttu-id="e0e2d-216">`Train` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-216">The `Train` method executes the following tasks:</span></span>

* <span data-ttu-id="e0e2d-217">データを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-217">Loads the data.</span></span>
* <span data-ttu-id="e0e2d-218">データを抽出して変換します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-218">Extracts and transforms the data.</span></span>
* <span data-ttu-id="e0e2d-219">モデルをトレーニングする。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-219">Trains the model.</span></span>
* <span data-ttu-id="e0e2d-220">テスト データに基づいてセンチメントを予測する。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-220">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="e0e2d-221">モデルを返します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-221">Returns the model.</span></span>

<span data-ttu-id="e0e2d-222">`Main` メソッドの直後に、次のコードを使用して `Train` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-222">Create the `Train` method, just after the `Main` method, using the following code:</span></span>

```csharp
 public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

<span data-ttu-id="e0e2d-223">Train メソッドに 2 つのパラメーターが渡されていることに注意してください。`MLContext` はコンテキスト (`mlContext`)、<xref:System.String> はデータセットのパス (`dataPath`) に関するものです。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-223">Notice that two parameters are passed into the Train method; a `MLContext` for the context (`mlContext`), and a <xref:System.String> for the dataset path (`dataPath`).</span></span> <span data-ttu-id="e0e2d-224">トレーニングとテストのためにこのメソッドは複数回使用します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-224">You're going to use this method more than once for training and testing.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="e0e2d-225">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="e0e2d-225">Load the data</span></span>

<span data-ttu-id="e0e2d-226">`_textLoader` グローバル変数と `dataPath` パラメーターを使用してデータを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-226">You'll load the data using the `_textLoader` global variable with the `dataPath` parameter.</span></span> <span data-ttu-id="e0e2d-227"><xref:Microsoft.Data.DataView.IDataView> が返されます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-227">It returns a <xref:Microsoft.Data.DataView.IDataView>.</span></span> <span data-ttu-id="e0e2d-228">`Transforms` の入力および出力として、`DataView` は基本的なデータ パイプラインの種類であり、`LINQ` の `IEnumerable` と同等です。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-228">As the input and output of `Transforms`, a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="e0e2d-229">ML.NET ではデータは SQL ビューに似ています。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-229">In ML.NET, data is similar to a SQL view.</span></span> <span data-ttu-id="e0e2d-230">つまり、遅延評価、体系的、異種です。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-230">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="e0e2d-231">オブジェクトはパイプラインの最初の部分であり、データを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-231">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="e0e2d-232">このチュートリアルでは、コメントと対応する有害または無害のセンチメントを含むデータセットが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-232">For this tutorial, it loads a dataset with comments and corresponding toxic or non toxic sentiment.</span></span> <span data-ttu-id="e0e2d-233">これを使用して、モデルを作成してトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-233">This is used to create the model, and train it.</span></span>

 <span data-ttu-id="e0e2d-234">`Train` メソッドの最初の行として、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-234">Add the following code as the first line of the `Train` method:</span></span>

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#6 "loading training dataset")]

## <a name="extract-and-transform-the-data"></a><span data-ttu-id="e0e2d-235">データを抽出して変換する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-235">Extract and transform the data</span></span>

<span data-ttu-id="e0e2d-236">データの前処理とクリーニングは、機械学習でデータ セットを効果的に使用する前に発生する重要なタスクです。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-236">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="e0e2d-237">多くの場合、生データはノイズが多くて信頼性が低く、値が欠落している可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-237">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="e0e2d-238">これらのモデル化タスクを行わずにデータを使用すると、誤解を招く結果が生じるおそれがあります。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-238">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="e0e2d-239">ML.NET の変換パイプラインによって、トレーニングまたはテストの前にデータに適用するカスタム変換セットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-239">ML.NET's transform pipelines compose a custom set of transforms that are applied to your data before training or testing.</span></span> <span data-ttu-id="e0e2d-240">この変換の主な目的は、データの[特徴付け](../resources/glossary.md#feature-engineering)です。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-240">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="e0e2d-241">機械学習アルゴリズムによって理解されるのは、[特徴付け](../resources/glossary.md#feature)されたデータです。したがって、次の手順では、テキスト データを ML アルゴリズムが認識できる形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-241">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="e0e2d-242">その形式は、[数値ベクトル](../resources/glossary.md#numerical-feature-vector)です。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-242">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="e0e2d-243">次に、`mlContext.Transforms.Text.FeaturizeText` を呼び出します。これによってテキスト列 (`SentimentText`) が特徴付けされ、機械学習アルゴリズムで使用される `Features` という数値ベクトルになります。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-243">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text column (`SentimentText`) column into a numeric vector called `Features` used by the machine learning algorithm.</span></span> <span data-ttu-id="e0e2d-244">これは、実質的にパイプラインになる <xref:Microsoft.ML.Data.EstimatorChain%601> を返すラッパー呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-244">This is a wrapper call that returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="e0e2d-245">後でトレーナーを `EstimatorChain` に付加するときに、この `pipeline` を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-245">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="e0e2d-246">次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-246">Add this as the next line of code:</span></span>

[!code-csharp[TextFeaturizingEstimator](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#7 "Add a TextFeaturizingEstimator")]

>[!WARNING]
> <span data-ttu-id="e0e2d-247">ML.NET バージョン 0.10 では、変換パラメーターの順序が変更されました。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-247">ML.NET Version 0.10 has changed the order of the Transform parameters.</span></span> <span data-ttu-id="e0e2d-248">アプリケーションを実行してモデルを構築するまで、これによるエラーは出力されません。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-248">This will not error out until you run the application and build the model.</span></span> <span data-ttu-id="e0e2d-249">変換パラメーターの名前を上記のコード スニペットに示すように使用してください。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-249">Use the parameter names for Transforms as illustrated in the previous code snippet.</span></span>

<span data-ttu-id="e0e2d-250">これが前処理/特徴付けのステップです。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-250">This is the preprocessing/featurization step.</span></span> <span data-ttu-id="e0e2d-251">ML.NET に用意されているその他のコンポーネントを使用すると、モデルでより良い結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-251">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="e0e2d-252">学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-252">Choose a learning algorithm</span></span>

<span data-ttu-id="e0e2d-253">トレーナーを追加するには、<xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer> オブジェクトを返す `mlContext.Transforms.Text.FeaturizeText` ラッパー メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-253">To add the trainer, call the `mlContext.Transforms.Text.FeaturizeText` wrapper method which returns a <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer> object.</span></span> <span data-ttu-id="e0e2d-254">これは、このパイプラインで使用するデシジョン ツリーの学習器です。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-254">This is a decision tree learner you'll use in this pipeline.</span></span> <span data-ttu-id="e0e2d-255">`FastTreeBinaryClassificationTrainer` が `pipeline` に追加されます。これは、特徴付けされた `SentimentText` (`Features`) と `Label` 入力パラメーターを受け入れて、履歴データから学習します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-255">The `FastTreeBinaryClassificationTrainer` is appended to the `pipeline` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

<span data-ttu-id="e0e2d-256">`Train` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-256">Add the following code to the `Train` method:</span></span>

[!code-csharp[FastTreeBinaryClassificationTrainer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#8 "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="e0e2d-257">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="e0e2d-257">Train the model</span></span>

<span data-ttu-id="e0e2d-258">読み込まれて変換されたデータ セットに基づいて、モデル <xref:Microsoft.ML.Data.TransformerChain%601> をトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-258">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="e0e2d-259">推定器が定義されたら、既に読み込まれたトレーニング データを提供しながら、<xref:Microsoft.ML.Data.EstimatorChain%601.Fit*> を使用してモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-259">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit*> while providing the already loaded training data.</span></span> <span data-ttu-id="e0e2d-260">これにより、予測で使用されるモデルが返されます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-260">This returns a model to use for predictions.</span></span> <span data-ttu-id="e0e2d-261">`pipeline.Fit()` でパイプラインをトレーニングし、`DataView` に基づいて `Transformer` を返します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-261">`pipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="e0e2d-262">これが行われるまで、実験は実行されません。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-262">The experiment is not executed until this happens.</span></span>

<span data-ttu-id="e0e2d-263">`Train` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-263">Add the following code to the `Train` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#9 "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="e0e2d-264">評価に使用する、トレーニングされたモデルを保存して返す</span><span class="sxs-lookup"><span data-stu-id="e0e2d-264">Save and Return the model trained to use for evaluation</span></span>

<span data-ttu-id="e0e2d-265">この時点で、既存または新規のどの .NET アプリケーションにも統合できる、型が <xref:Microsoft.ML.Data.TransformerChain%601> のモデルができました。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-265">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="e0e2d-266">`Train` メソッドの最後で、モデルを返します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-266">Return the model at the end of the `Train` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#10 "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="e0e2d-267">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-267">Evaluate the model</span></span>

<span data-ttu-id="e0e2d-268">これでモデルの作成とトレーニングが完了したので、品質保証と検証のために、別のデータ セットを使用してモデルを評価します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-268">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="e0e2d-269">`Evaluate` メソッドでは、`Train` で作成されたモデルが渡されて評価されます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-269">In the `Evaluate` method, the model created in `Train` is passed in to be evaluated.</span></span> <span data-ttu-id="e0e2d-270">`Train` の直後に、次のコードに示すように `Evaluate` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-270">Create the `Evaluate` method, just after `Train`, as in the following code:</span></span>

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="e0e2d-271">`Evaluate` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-271">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="e0e2d-272">テスト データ セットを読み込む。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-272">Loads the test dataset.</span></span>
* <span data-ttu-id="e0e2d-273">バイナリ評価器を作成する。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-273">Creates the binary evaluator.</span></span>
* <span data-ttu-id="e0e2d-274">モデルを評価し、メトリックを作成する。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-274">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="e0e2d-275">メトリックを表示する。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-275">Displays the metrics.</span></span>

<span data-ttu-id="e0e2d-276">`Train` メソッドの呼び出しのすぐ下に、次のコードを使用して、`Main` メソッドからの新しいメソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-276">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#11 "Call the Evaluate method")]

<span data-ttu-id="e0e2d-277">前に初期化した `_textLoader` グローバル変数と `_testDataPath` グローバル フィールドを使用して、テスト データセットを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-277">You'll load the test dataset using the previously initialized  `_textLoader` global variable with the `_testDataPath` global field.</span></span> <span data-ttu-id="e0e2d-278">このデータ セットを品質チェックとして使用して、モデルを評価できます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-278">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="e0e2d-279">`Evaluate` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-279">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#12 "Load the test dataset")]

<span data-ttu-id="e0e2d-280">次に、機械学習の `model` パラメーター (変換器) を使用し、特徴を入力して予測を返します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-280">Next, you'll use the machine learning `model` parameter (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="e0e2d-281">`Evaluate` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-281">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[PredictWithTransformer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#13 "Predict using the Transformer")]

<span data-ttu-id="e0e2d-282">`BinaryClassificationContext.Evaluate` メソッドは、指定されたデータセットを使用して `PredictionModel` の品質メトリックを計算します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-282">The `BinaryClassificationContext.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="e0e2d-283">これによって返される `BinaryClassificationEvaluator.CalibratedResult` オブジェクトには、バイナリ分類評価器によって計算されるメトリック全体が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-283">It returns a `BinaryClassificationEvaluator.CalibratedResult` object contains the overall metrics computed by binary classification evaluators.</span></span> <span data-ttu-id="e0e2d-284">これらを表示してモデルの品質を判定するには、最初にメトリックを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-284">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="e0e2d-285">`Evaluate` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-285">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#14 "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="e0e2d-286">モデル検証のためのメトリックを表示する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-286">Displaying the metrics for model validation</span></span>

<span data-ttu-id="e0e2d-287">次のコードを使用してメトリックを表示し、結果を共有し、それに対してアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-287">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#15 "Display selected metrics")]

<span data-ttu-id="e0e2d-288">モデルを返す前に .zip ファイルに保存するには、`Evaluate` 内に次の行を追加して `SaveModelAsFile` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-288">To save your model to a .zip file before returning, add the following code to call the `SaveModelAsFile` method as the next line in `Evaluate`:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#23 "Save the model")]

## <a name="save-the-model-as-azip-file"></a><span data-ttu-id="e0e2d-289">モデルを .zip ファイルとして保存する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-289">Save the model as a.zip file</span></span>

<span data-ttu-id="e0e2d-290">`Evaluate` メソッドの直後に、次のコードを使用して `SaveModelAsFile` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-290">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="e0e2d-291">`SaveModelAsFile` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-291">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="e0e2d-292">モデルを .zip ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-292">Saves the model as a .zip file.</span></span>

<span data-ttu-id="e0e2d-293">次に、モデルを再利用して他のアプリケーションで使用できるようにモデルを保存するメソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-293">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="e0e2d-294">`ITransformer` には <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> メソッドがあり、`_modelPath` グローバル フィールドと <xref:System.IO.Stream> を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-294">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="e0e2d-295">これを zip ファイルとして保存するには、`FileStream` を作成した直後に `SaveTo` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-295">To save this as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="e0e2d-296">`SaveModelAsFile` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-296">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveToMethod](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#24 "Add the SaveTo Method")]
<span data-ttu-id="e0e2d-297">読み込み済みのモデルを使用して配置および予測する `_modelPath` を使用してコンソール メッセージを記述することで、ファイルが書き込まれた場所も表示できるようになります。これには次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-297">Deploy and Predict with a loaded model You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-saved-model"></a><span data-ttu-id="e0e2d-298">保存したモデルを使用してテスト データの結果を予測する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-298">Predict the test data outcome with the saved model</span></span>

<span data-ttu-id="e0e2d-299">`Evaluate` メソッドの直後に、次のコードを使用して `Predict` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-299">Create the `Predict` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void Predict(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="e0e2d-300">`Predict` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-300">The `Predict` method executes the following tasks:</span></span>

* <span data-ttu-id="e0e2d-301">テスト データの 1 つのコメントを作成する。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-301">Creates a single comment of test data.</span></span>
* <span data-ttu-id="e0e2d-302">テスト データに基づいてセンチメントを予測する。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-302">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="e0e2d-303">テスト データと予測をレポート用に結合する。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-303">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="e0e2d-304">予測された結果を表示する。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-304">Displays the predicted results.</span></span>

<span data-ttu-id="e0e2d-305">`Evaluate` メソッドの呼び出しのすぐ下に、次のコードを使用して、`Main` メソッドからの新しいメソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-305">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#16 "Call the Predict method")]

<span data-ttu-id="e0e2d-306">`model` は多数のデータ行を操作する `transformer` ですが、よくある運用シナリオとして個々の例に対する予測のニーズがあります。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-306">While the `model` is a `transformer` that operates on many rows of data, a very common production scenario is a need for predictions on individual examples.</span></span> <span data-ttu-id="e0e2d-307"><xref:Microsoft.ML.PredictionEngine%602> は、`CreatePredictionEngine` メソッドから返されるラッパーです。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-307">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="e0e2d-308">次の行を追加して、`PredictionEngine` を `Predict` メソッドの 1 行目として作成しましょう。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-308">Let's add the following code to create the `PredictionEngine` as the first line in the `Predict` Method:</span></span>

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#17 "Create the PredictionEngine")]
  
<span data-ttu-id="e0e2d-309">コメントを追加して、`Predict` メソッドでトレーニングされたモデルの予測をテストします。これには `SentimentData` のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-309">Add a comment to test the trained model's prediction in the `Predict` method by creating an instance of `SentimentData`:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#18 "Create test data for single prediction")]

 <span data-ttu-id="e0e2d-310">これを使用すると、コメント データの 1 インスタンスのセンチメントが有害か無害かを予測できます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-310">You can use that to predict the Toxic or Non Toxic sentiment of a single instance of the comment data.</span></span> <span data-ttu-id="e0e2d-311">予測を取得するには、データに対して <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-311">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="e0e2d-312">入力データは文字列であり、モデルには、特徴付けが含まれることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-312">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="e0e2d-313">トレーニングと予測の間は、パイプラインが同期されます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-313">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="e0e2d-314">予測のために前処理/特徴付けのコードを特別に記述する必要はなく、同じ API によってバッチと 1 回限りの予測の両方が処理されます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-314">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#19 "Create a prediction of sentiment")]

### <a name="using-the-model-prediction"></a><span data-ttu-id="e0e2d-315">モデルの使用: 予測</span><span class="sxs-lookup"><span data-stu-id="e0e2d-315">Using the model: prediction</span></span>

<span data-ttu-id="e0e2d-316">結果を共有し、それに応じたアクションを実行するために、`SentimentText` および対応するセンチメント予測を表示します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-316">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="e0e2d-317">これは運用化と呼ばれ、返されたデータを運用ポリシーとして使用します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-317">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="e0e2d-318">次の <xref:System.Console.WriteLine?displayProperty=nameWithType> コードを使用して、結果の表示を作成します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-318">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#20 "Display prediction output")]

## <a name="deploy-and-predict-with-a-loaded-model"></a><span data-ttu-id="e0e2d-319">読み込み済みのモデルを使用して配置および予測する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-319">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="e0e2d-320">`SaveModelAsFile` メソッドの直前に、次のコードを使用して `PredictWithModelLoadedFromFile` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-320">Create the `PredictWithModelLoadedFromFile` method, just before the `SaveModelAsFile` method, using the following code:</span></span>

```csharp
public static void PredictWithModelLoadedFromFile(MLContext mlContext)
{

}
```

<span data-ttu-id="e0e2d-321">`PredictWithModelLoadedFromFile` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-321">The `PredictWithModelLoadedFromFile` method executes the following tasks:</span></span>

* <span data-ttu-id="e0e2d-322">バッチ テスト データを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-322">Creates batch test data.</span></span>
* <span data-ttu-id="e0e2d-323">テスト データに基づいてセンチメントを予測する。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-323">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="e0e2d-324">テスト データと予測をレポート用に結合する。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-324">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="e0e2d-325">予測された結果を表示する。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-325">Displays the predicted results.</span></span>

<span data-ttu-id="e0e2d-326">`Predict` メソッドの呼び出しのすぐ下に、次のコードを使用して、`Main` メソッドからの新しいメソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-326">Add a call to the new method from the `Main` method, right under the `Predict` method call, using the following code:</span></span>

[!code-csharp[CallPredictModelLoaded](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#25 "Call the PredictWithModelLoadedFromFile method")]

<span data-ttu-id="e0e2d-327">`PredictWithModelLoadedFromFile` メソッドでトレーニングされるモデルの予測をテストするために、いくつかのコメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-327">Add some comments to test the trained model's predictions in the `PredictWithModelLoadedFromFile` method:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#26 "Create test data for predictions")]

<span data-ttu-id="e0e2d-328">モデルを読み込みます</span><span class="sxs-lookup"><span data-stu-id="e0e2d-328">Load the model</span></span>

[!code-csharp[LoadTheModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#27 "Load the model")]

<span data-ttu-id="e0e2d-329">モデルは既にあるので、それを利用して、<xref:Microsoft.ML.Core.Data.ITransformer.Transform%2A> メソッドでコメント データのセンチメントが有害か無害かを予測できます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-329">Now that you have a model, you can use that to predict the Toxic or Non Toxic sentiment of the comment data using the <xref:Microsoft.ML.Core.Data.ITransformer.Transform%2A> method.</span></span> <span data-ttu-id="e0e2d-330">予測を取得するには、新しいデータに対して `Predict` を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-330">To get a prediction, use `Predict` on new data.</span></span> <span data-ttu-id="e0e2d-331">入力データは文字列であり、モデルには、特徴付けが含まれることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-331">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="e0e2d-332">トレーニングと予測の間は、パイプラインが同期されます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-332">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="e0e2d-333">予測のために前処理/特徴付けのコードを特別に記述する必要はなく、同じ API によってバッチと 1 回限りの予測の両方が処理されます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-333">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="e0e2d-334">予測のために `PredictWithModelLoadedFromFile` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-334">Add the following code to the `PredictWithModelLoadedFromFile` method for the predictions:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#28 "Create predictions of sentiments")]

### <a name="using-the-loaded-model-for-prediction"></a><span data-ttu-id="e0e2d-335">予測のために読み込み済みのモデルを使用する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-335">Using the loaded model for prediction</span></span>

<span data-ttu-id="e0e2d-336">結果を共有し、それに応じたアクションを実行するために、`SentimentText` および対応するセンチメント予測を表示します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-336">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="e0e2d-337">これは運用化と呼ばれ、返されたデータを運用ポリシーとして使用します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-337">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="e0e2d-338">次の <xref:System.Console.WriteLine?displayProperty=nameWithType> コードを使用して、結果のヘッダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-338">Create a header for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#29 "Display prediction outputs")]

<span data-ttu-id="e0e2d-339">予測された結果を表示する前に、元のコメントとその予測されたセンチメントが一緒に表示されるように、センチメントと予測を結合します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-339">Before displaying the predicted results, combine the sentiment and prediction together to see the original comment with its predicted sentiment.</span></span> <span data-ttu-id="e0e2d-340">次のコードでは <xref:System.Linq.Enumerable.Zip%2A> メソッドを使用してそれを行うため、そのコードを次に追加します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-340">The following code uses the <xref:System.Linq.Enumerable.Zip%2A> method to make that happen, so add that code next:</span></span>

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#30 "Build the pairs of sentiment data and predictions")]

<span data-ttu-id="e0e2d-341">これで `SentimentText` と `Sentiment` が 1 つのクラスに結合されたので、<xref:System.Console.WriteLine?displayProperty=nameWithType> メソッドを使用して結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-341">Now that you've combined the `SentimentText` and `Sentiment` into a class, you can display the results using the <xref:System.Console.WriteLine?displayProperty=nameWithType> method:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#31 "Display the predictions")]

<span data-ttu-id="e0e2d-342">推定されたタプル要素名は C# 7.1 の新機能であり、このプロジェクトの既定の言語バージョンは C# 7.0 であるため、言語バージョンを C# 7.1 以降に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-342">Because inferred tuple element names are a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="e0e2d-343">そのためには、**ソリューション エクスプローラー**でプロジェクト ノードを右クリックして、**[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-343">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="e0e2d-344">**[ビルド]** タブを選択し、**[詳細設定]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-344">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="e0e2d-345">ドロップダウンで **[C# 7.1]** (またはそれ以降のバージョン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-345">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="e0e2d-346">**[OK]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-346">Select the **OK** button.</span></span>

## <a name="results"></a><span data-ttu-id="e0e2d-347">結果</span><span class="sxs-lookup"><span data-stu-id="e0e2d-347">Results</span></span>

<span data-ttu-id="e0e2d-348">結果は以下のようになるはずです。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-348">Your results should be similar to the following.</span></span> <span data-ttu-id="e0e2d-349">パイプラインが処理されると、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-349">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="e0e2d-350">警告または処理メッセージが表示されることがありますが、</span><span class="sxs-lookup"><span data-stu-id="e0e2d-350">You may see warnings, or processing messages.</span></span> <span data-ttu-id="e0e2d-351">わかりやすくするために、それらは次の結果から削除してあります。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-351">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 94.44%
Auc: 98.77%
F1Score: 94.74%
=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This is a very rude movie | Prediction: Toxic | Probability: 0.5297049
=============== End of Predictions ===============

=============== New iteration of Model ===============
=============== Create and Train the Model ===============
=============== End of training ===============


The model is saved to: C:\Tutorial\SentimentAnalysis\bin\Debug\netcoreapp2.1\Data\Model.zip

=============== Prediction Test of loaded model with a multiple sample ===============

Sentiment: This is a very rude movie | Prediction: Toxic | Probability: 0.4585565
Sentiment: I love this article. | Prediction: Not Toxic | Probability: 0.09454837

```

<span data-ttu-id="e0e2d-352">おめでとうございます! </span><span class="sxs-lookup"><span data-stu-id="e0e2d-352">Congratulations!</span></span> <span data-ttu-id="e0e2d-353">これで、メッセージのセンチメントを分類および予測するための機械学習モデルをビルドできました。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-353">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span> <span data-ttu-id="e0e2d-354">このチュートリアルのソース コードは [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) リポジトリで確認できます。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-354">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e0e2d-355">次の手順</span><span class="sxs-lookup"><span data-stu-id="e0e2d-355">Next steps</span></span>

<span data-ttu-id="e0e2d-356">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-356">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="e0e2d-357">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-357">Understand the problem</span></span>
> * <span data-ttu-id="e0e2d-358">適切な機械学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-358">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="e0e2d-359">データを準備する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-359">Prepare your data</span></span>
> * <span data-ttu-id="e0e2d-360">データを変換する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-360">Transform the data</span></span>
> * <span data-ttu-id="e0e2d-361">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="e0e2d-361">Train the model</span></span>
> * <span data-ttu-id="e0e2d-362">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-362">Evaluate the model</span></span>
> * <span data-ttu-id="e0e2d-363">トレーニング済みモデルを使用して予測する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-363">Predict with the trained model</span></span>
> * <span data-ttu-id="e0e2d-364">読み込み済みのモデルを使用して配置および予測する</span><span class="sxs-lookup"><span data-stu-id="e0e2d-364">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="e0e2d-365">さらに詳しく学習するには、次のチュートリアルに進んでください。</span><span class="sxs-lookup"><span data-stu-id="e0e2d-365">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="e0e2d-366">問題の分類</span><span class="sxs-lookup"><span data-stu-id="e0e2d-366">Issue Classification</span></span>](github-issue-classification.md)
