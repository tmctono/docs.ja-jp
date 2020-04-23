---
title: 'チュートリアル: Web サイトのコメントを分析する - 二項分類'
description: このチュートリアルでは、Web サイトのコメントからセンチメントを分類して適切なアクションを実行する .NET Core コンソール アプリケーションの作成方法について説明します。 この二項センチメント分類子には、Visual Studio で C# を使用します。
ms.date: 09/30/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c6e13cfca93c54648b1a0423c5983013d3e2a1a0
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243298"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-with-binary-classification-in-mlnet"></a><span data-ttu-id="85b0c-104">チュートリアル: ML.NET の二項分類を使用して Web サイトのコメントのセンチメントを分析する</span><span class="sxs-lookup"><span data-stu-id="85b0c-104">Tutorial: Analyze sentiment of website comments with binary classification in ML.NET</span></span>

<span data-ttu-id="85b0c-105">このチュートリアルでは、Web サイトのコメントからセンチメントを分類して適切なアクションを実行する .NET Core コンソール アプリケーションの作成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-105">This tutorial shows you how to create a .NET Core console application that classifies sentiment from website comments and takes the appropriate action.</span></span> <span data-ttu-id="85b0c-106">この二項センチメント分類子には、Visual Studio 2017 で C# を使用します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-106">The binary sentiment classifier uses C# in Visual Studio 2017.</span></span>

<span data-ttu-id="85b0c-107">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="85b0c-108">コンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="85b0c-108">Create a console application</span></span>
> - <span data-ttu-id="85b0c-109">データの準備</span><span class="sxs-lookup"><span data-stu-id="85b0c-109">Prepare data</span></span>
> - <span data-ttu-id="85b0c-110">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="85b0c-110">Load the data</span></span>
> - <span data-ttu-id="85b0c-111">モデルを構築してトレーニングする</span><span class="sxs-lookup"><span data-stu-id="85b0c-111">Build and train the model</span></span>
> - <span data-ttu-id="85b0c-112">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="85b0c-112">Evaluate the model</span></span>
> - <span data-ttu-id="85b0c-113">モデルを使用して予測する</span><span class="sxs-lookup"><span data-stu-id="85b0c-113">Use the model to make a prediction</span></span>
> - <span data-ttu-id="85b0c-114">結果を見る</span><span class="sxs-lookup"><span data-stu-id="85b0c-114">See the results</span></span>

<span data-ttu-id="85b0c-115">このチュートリアルのソース コードは [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) リポジトリで確認できます。</span><span class="sxs-lookup"><span data-stu-id="85b0c-115">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="85b0c-116">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="85b0c-116">Prerequisites</span></span>

- <span data-ttu-id="85b0c-117">[Visual Studio 2017 バージョン 15.6 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)が ".NET Core クロスプラット フォーム開発" ワークロードと共にインストールされている</span><span class="sxs-lookup"><span data-stu-id="85b0c-117">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed</span></span>

- <span data-ttu-id="85b0c-118">[UCI Sentiment Labeled Sentences データセット](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (ZIP ファイル)</span><span class="sxs-lookup"><span data-stu-id="85b0c-118">[UCI Sentiment Labeled Sentences dataset](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (ZIP file)</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="85b0c-119">コンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="85b0c-119">Create a console application</span></span>

1. <span data-ttu-id="85b0c-120">"SentimentAnalysis" という名前の **.NET Core コンソール アプリケーション**を作成します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-120">Create a **.NET Core Console Application** called "SentimentAnalysis".</span></span>

2. <span data-ttu-id="85b0c-121">データ セット ファイルを保存するために、プロジェクトに *Data* という名前のディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-121">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="85b0c-122">**Microsoft.ML NuGet パッケージ**をインストールします。</span><span class="sxs-lookup"><span data-stu-id="85b0c-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="85b0c-123">ソリューション エクスプローラーで、プロジェクトを右クリックし、 **[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="85b0c-124">パッケージ ソースとして "nuget.org" を選択してから、 **[参照]** タブを選択します。**Microsoft.ML** を検索し、目的のパッケージを選択して、 **[インストール]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-124">Choose "nuget.org" as the package source, and then select the **Browse** tab. Search for **Microsoft.ML**, select the package you want, and then select the **Install** button.</span></span> <span data-ttu-id="85b0c-125">選択したパッケージのライセンス条項に同意してインストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-125">Proceed with the installation by agreeing to the license terms for the package you choose.</span></span> <span data-ttu-id="85b0c-126">**Microsoft.ML.FastTree** NuGet パッケージに対して同じことを行います。</span><span class="sxs-lookup"><span data-stu-id="85b0c-126">Do the same for the **Microsoft.ML.FastTree** NuGet package.</span></span>

## <a name="prepare-your-data"></a><span data-ttu-id="85b0c-127">データを準備する</span><span class="sxs-lookup"><span data-stu-id="85b0c-127">Prepare your data</span></span>

> [!NOTE]
> <span data-ttu-id="85b0c-128">このチュートリアルのデータセットは、「From Group to Individual Labels using Deep Features」 (Kotzias 他</span><span class="sxs-lookup"><span data-stu-id="85b0c-128">The datasets for this tutorial are from the 'From Group to Individual Labels using Deep Features', Kotzias et.</span></span> <span data-ttu-id="85b0c-129">著、</span><span class="sxs-lookup"><span data-stu-id="85b0c-129">al,.</span></span> <span data-ttu-id="85b0c-130">KDD 2015) のものであり、UCI 機械学習リポジトリ (Dua, D. and Karra Taniskidou, E.(2017)) でホストされています。</span><span class="sxs-lookup"><span data-stu-id="85b0c-130">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="85b0c-131">UCI 機械学習リポジトリ [http://archive.ics.uci.edu/ml ]。</span><span class="sxs-lookup"><span data-stu-id="85b0c-131">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="85b0c-132">カリフォルニア州アーバイン: カリフォルニア大学情報コンピュータサイエンス学部。</span><span class="sxs-lookup"><span data-stu-id="85b0c-132">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

1. <span data-ttu-id="85b0c-133">[UCI Sentiment Labeled Sentences データセットの ZIP ファイル](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)をダウンロードし、展開します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-133">Download [UCI Sentiment Labeled Sentences dataset ZIP file](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip.</span></span>

2. <span data-ttu-id="85b0c-134">`yelp_labelled.txt` ファイルを、作成した *Data* ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="85b0c-134">Copy the `yelp_labelled.txt` file into the *Data* directory you created.</span></span>

3. <span data-ttu-id="85b0c-135">ソリューション エクスプローラーで、`yelp_labeled.txt` ファイルを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-135">In Solution Explorer, right-click the `yelp_labeled.txt` file and select **Properties**.</span></span> <span data-ttu-id="85b0c-136">**[詳細設定]** で、 **[出力ディレクトリにコピー]** の値を **[新しい場合はコピーする]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-136">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="85b0c-137">クラスを作成してパスを定義する</span><span class="sxs-lookup"><span data-stu-id="85b0c-137">Create classes and define paths</span></span>

1. <span data-ttu-id="85b0c-138">次に示す追加の `using` ステートメントを *Program.cs* ファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-138">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="85b0c-139">`Main` メソッドの直前の行に次のコードを追加して、最近ダウンロードしたデータセット ファイルのパスを保持するフィールドを作成します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-139">Add the following code to the line right above the `Main` method, to create a field to hold the recently downloaded dataset file path:</span></span>

    [!code-csharp[Declare global variables](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

1. <span data-ttu-id="85b0c-140">次に、入力データと予測のためにクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-140">Next, create classes for your input data and predictions.</span></span> <span data-ttu-id="85b0c-141">プロジェクトに新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-141">Add a new class to your project:</span></span>

    - <span data-ttu-id="85b0c-142">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、 **[追加]**  >  **[新しい項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-142">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

    - <span data-ttu-id="85b0c-143">**[新しい項目の追加]** ダイアログ ボックスで、 **[クラス]** を選択し、 **[名前]** フィールドを *SentimentData.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-143">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="85b0c-144">次に **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-144">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="85b0c-145">コード エディターで *SentimentData.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="85b0c-145">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="85b0c-146">*SentimentData.cs* の先頭に次の `using` ステートメントを 追加します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-146">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

    [!code-csharp[AddUsings](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/SentimentData.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="85b0c-147">既存のクラス定義を削除し、`SentimentData` と `SentimentPrediction` の 2 つのクラスを含む次のコードを *SentimentData.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-147">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

    [!code-csharp[DeclareTypes](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/SentimentData.cs#DeclareTypes "Declare data record types")]

### <a name="how-the-data-was-prepared"></a><span data-ttu-id="85b0c-148">データの準備方法</span><span class="sxs-lookup"><span data-stu-id="85b0c-148">How the data was prepared</span></span>

<span data-ttu-id="85b0c-149">入力データセット クラスの `SentimentData` には、ユーザー コメント用の `string` (`SentimentText`) と、センチメント用の 1 (肯定的) または 0 (否定的) のいずれかの `bool` (`Sentiment`) 値があります。</span><span class="sxs-lookup"><span data-stu-id="85b0c-149">The input dataset class, `SentimentData`, has a `string` for user comments (`SentimentText`) and a `bool` (`Sentiment`) value of either 1 (positive) or 0 (negative) for sentiment.</span></span> <span data-ttu-id="85b0c-150">どちらのフィールドにも [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) 属性が添付され、各フィールドのデータ ファイルの順序が記述されています。</span><span class="sxs-lookup"><span data-stu-id="85b0c-150">Both fields have [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attributes attached to them, which describes the data file order of each field.</span></span>  <span data-ttu-id="85b0c-151">さらに、`Sentiment` プロパティには、それを `Label` フィールドとして指定する [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) 属性があります。</span><span class="sxs-lookup"><span data-stu-id="85b0c-151">In addition, the `Sentiment` property has a [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) attribute to designate it as the `Label` field.</span></span> <span data-ttu-id="85b0c-152">次のファイル例にはヘッダー行がなく、次のような内容です。</span><span class="sxs-lookup"><span data-stu-id="85b0c-152">The following example file doesn't have a header row, and looks like this:</span></span>

|<span data-ttu-id="85b0c-153">SentimentText</span><span class="sxs-lookup"><span data-stu-id="85b0c-153">SentimentText</span></span>                         |<span data-ttu-id="85b0c-154">Sentiment (ラベル)</span><span class="sxs-lookup"><span data-stu-id="85b0c-154">Sentiment (Label)</span></span> |
|--------------------------------------|----------|
|<span data-ttu-id="85b0c-155">Waitress was a little slow in service.</span><span class="sxs-lookup"><span data-stu-id="85b0c-155">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="85b0c-156">0</span><span class="sxs-lookup"><span data-stu-id="85b0c-156">0</span></span>     |
|<span data-ttu-id="85b0c-157">Crust is not good.</span><span class="sxs-lookup"><span data-stu-id="85b0c-157">Crust is not good.</span></span>                    |    <span data-ttu-id="85b0c-158">0</span><span class="sxs-lookup"><span data-stu-id="85b0c-158">0</span></span>     |
|<span data-ttu-id="85b0c-159">Wow...Loved this place.</span><span class="sxs-lookup"><span data-stu-id="85b0c-159">Wow... Loved this place.</span></span>              |    <span data-ttu-id="85b0c-160">1</span><span class="sxs-lookup"><span data-stu-id="85b0c-160">1</span></span>     |
|<span data-ttu-id="85b0c-161">Service was very prompt.</span><span class="sxs-lookup"><span data-stu-id="85b0c-161">Service was very prompt.</span></span>              |    <span data-ttu-id="85b0c-162">1</span><span class="sxs-lookup"><span data-stu-id="85b0c-162">1</span></span>     |

<span data-ttu-id="85b0c-163">`SentimentPrediction` はモデルのトレーニング後に使用される予測クラスです。</span><span class="sxs-lookup"><span data-stu-id="85b0c-163">`SentimentPrediction` is the prediction class used after model training.</span></span> <span data-ttu-id="85b0c-164">`SentimentData` から継承されるため、入力 `SentimentText` を出力予測と共に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="85b0c-164">It inherits from `SentimentData` so that the input `SentimentText` can be displayed along with the output prediction.</span></span> <span data-ttu-id="85b0c-165">`Prediction` ブール値は、新しい入力 `SentimentText` が指定されたときにモデルで予測される値です。</span><span class="sxs-lookup"><span data-stu-id="85b0c-165">The `Prediction` boolean is the value that the model predicts when supplied with new input `SentimentText`.</span></span>

<span data-ttu-id="85b0c-166">出力クラス `SentimentPrediction` にはモデルによって計算されたその他の 2 つのプロパティが含まれています。1 つはモデルによって計算された生のスコアの `Score`、もう 1 つは肯定的センチメントを持つテキストの尤度に調整されたスコアの `Probability` です。</span><span class="sxs-lookup"><span data-stu-id="85b0c-166">The output class `SentimentPrediction` contains two other properties calculated by the model: `Score` - the raw score calculated by the model, and `Probability` - the score calibrated to the likelihood of the text having positive sentiment.</span></span>

<span data-ttu-id="85b0c-167">このチュートリアルで最も重要なプロパティは `Prediction` です。</span><span class="sxs-lookup"><span data-stu-id="85b0c-167">For this tutorial, the most important property is `Prediction`.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="85b0c-168">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="85b0c-168">Load the data</span></span>

<span data-ttu-id="85b0c-169">ML.NET 内のデータは、[IDataView クラス](xref:Microsoft.ML.IDataView)として表されます。</span><span class="sxs-lookup"><span data-stu-id="85b0c-169">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="85b0c-170">`IDataView` は、表形式のデータ (数値とテキスト) を表すための柔軟で効率的な方法です。</span><span class="sxs-lookup"><span data-stu-id="85b0c-170">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="85b0c-171">データはテキスト ファイルから、またはリアルタイムで (SQL データベースやログ ファイルなど) `IDataView` オブジェクトに読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="85b0c-171">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="85b0c-172">[MLContext クラス](xref:Microsoft.ML.MLContext)は、すべての ML.NET 操作の始点です。</span><span class="sxs-lookup"><span data-stu-id="85b0c-172">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations.</span></span> <span data-ttu-id="85b0c-173">`mlContext` を初期化することで、モデル作成ワークフローのオブジェクト間で共有できる新しい ML.NET 環境が作成されます。</span><span class="sxs-lookup"><span data-stu-id="85b0c-173">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="85b0c-174">これは Entity Framework における `DBContext` と概念的には同じです。</span><span class="sxs-lookup"><span data-stu-id="85b0c-174">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="85b0c-175">アプリを準備してからデータを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="85b0c-175">You prepare the app, and then load data:</span></span>

1. <span data-ttu-id="85b0c-176">`Main` メソッドの `Console.WriteLine("Hello World!")` の行は、mlContext 変数を宣言して初期化する次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="85b0c-176">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the mlContext variable:</span></span>

    [!code-csharp[CreateMLContext](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreateMLContext "Create the ML Context")]

2. <span data-ttu-id="85b0c-177">`Main()` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-177">Add the following as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallLoadData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallLoadData)]

3. <span data-ttu-id="85b0c-178">`Main()` メソッドの直後に、次のコードを使用して `LoadData()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-178">Create the `LoadData()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static TrainTestData LoadData(MLContext mlContext)
    {

    }
    ```

    <span data-ttu-id="85b0c-179">`LoadData()` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-179">The `LoadData()` method executes the following tasks:</span></span>

    - <span data-ttu-id="85b0c-180">データを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="85b0c-180">Loads the data.</span></span>
    - <span data-ttu-id="85b0c-181">読み込んだデータセットを、トレーニングデータセットとテスト データセットに分割します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-181">Splits the loaded dataset into train and test datasets.</span></span>
    - <span data-ttu-id="85b0c-182">分割されたトレーニングデータセットとテスト データセットを返します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-182">Returns the split train and test datasets.</span></span>

4. <span data-ttu-id="85b0c-183">`LoadData()` メソッドの最初の行として、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-183">Add the following code as the first line of the `LoadData()` method:</span></span>

    [!code-csharp[LoadData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#LoadData "loading dataset")]

    <span data-ttu-id="85b0c-184">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) メソッドを使用してデータ スキーマを定義し、ファイルを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="85b0c-184">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) method defines the data schema and reads in the file.</span></span> <span data-ttu-id="85b0c-185">データ パス変数を取得して、`IDataView` を返します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-185">It takes in the data path variables and returns an `IDataView`.</span></span>

### <a name="split-the-dataset-for-model-training-and-testing"></a><span data-ttu-id="85b0c-186">モデルのトレーニング用とテスト用にデータセットを分割する</span><span class="sxs-lookup"><span data-stu-id="85b0c-186">Split the dataset for model training and testing</span></span>

<span data-ttu-id="85b0c-187">モデルを準備するときは、データセットの一部を使用してモデルをトレーニングし、データセットの一部を使用してモデルの正確度をテストします。</span><span class="sxs-lookup"><span data-stu-id="85b0c-187">When preparing a model, you use part of the dataset to train it and part of the dataset to test the model's accuracy.</span></span>

1. <span data-ttu-id="85b0c-188">読み込まれたデータを必要なデータセットに分割するには、`LoadData()` メソッドの次の行として、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-188">To split the loaded data into the needed datasets, add the following code as the next line in the `LoadData()` method:</span></span>

    [!code-csharp[SplitData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#SplitData "Split the Data")]

    <span data-ttu-id="85b0c-189">前のコードでは、[TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) メソッドを使用して、読み込まれたデータセットをトレーニング データセットとテスト データセットに分割し、それらを <xref:Microsoft.ML.DataOperationsCatalog.TrainTestData> クラスで返します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-189">The previous code uses the [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) method to split the loaded dataset into train and test datasets and return them in the <xref:Microsoft.ML.DataOperationsCatalog.TrainTestData> class.</span></span> <span data-ttu-id="85b0c-190">`testFraction` パラメーターを使用して、データに占めるテスト セットの割合を指定します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-190">Specify the test set percentage of data with the `testFraction`parameter.</span></span> <span data-ttu-id="85b0c-191">既定値は 10% です。この場合、より多くのデータを評価するために 20% を使用します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-191">The default is 10%, in this case you use 20% to evaluate more data.</span></span>

2. <span data-ttu-id="85b0c-192">`LoadData()` メソッドの最後に、`splitDataView` が返されます。</span><span class="sxs-lookup"><span data-stu-id="85b0c-192">Return the `splitDataView` at the end of the `LoadData()` method:</span></span>

    [!code-csharp[ReturnSplitData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a><span data-ttu-id="85b0c-193">モデルを構築してトレーニングする</span><span class="sxs-lookup"><span data-stu-id="85b0c-193">Build and train the model</span></span>

1. <span data-ttu-id="85b0c-194">`Main()` メソッドの次のコード行として、`BuildAndTrainModel` メソッドに次の呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-194">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallBuildAndTrainModel](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallBuildAndTrainModel)]

    <span data-ttu-id="85b0c-195">`BuildAndTrainModel()` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-195">The `BuildAndTrainModel()` method executes the following tasks:</span></span>

    - <span data-ttu-id="85b0c-196">データを抽出して変換します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-196">Extracts and transforms the data.</span></span>
    - <span data-ttu-id="85b0c-197">モデルをトレーニングする。</span><span class="sxs-lookup"><span data-stu-id="85b0c-197">Trains the model.</span></span>
    - <span data-ttu-id="85b0c-198">テスト データに基づいてセンチメントを予測する。</span><span class="sxs-lookup"><span data-stu-id="85b0c-198">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="85b0c-199">モデルを返します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-199">Returns the model.</span></span>

2. <span data-ttu-id="85b0c-200">`Main()` メソッドの直後に、次のコードを使用して `BuildAndTrainModel()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-200">Create the `BuildAndTrainModel()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
    {

    }
    ```

### <a name="extract-and-transform-the-data"></a><span data-ttu-id="85b0c-201">データを抽出して変換する</span><span class="sxs-lookup"><span data-stu-id="85b0c-201">Extract and transform the data</span></span>

1. <span data-ttu-id="85b0c-202">次のコード行として `FeaturizeText` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-202">Call `FeaturizeText` as the next line of code:</span></span>

    [!code-csharp[FeaturizeText](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#FeaturizeText "Featurize the text")]

    <span data-ttu-id="85b0c-203">前のコードの `FeaturizeText()` メソッドでは、テキスト列 (`SentimentText`) を機械学習アルゴリズムから使用される数値キー型の `Features` 列に変換し、それを新しいデータセット列として追加します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-203">The `FeaturizeText()` method in the previous code converts the text column (`SentimentText`) into a numeric key type `Features` column used by the machine learning algorithm and adds it as a new dataset column:</span></span>

    |<span data-ttu-id="85b0c-204">SentimentText</span><span class="sxs-lookup"><span data-stu-id="85b0c-204">SentimentText</span></span>                         |<span data-ttu-id="85b0c-205">Sentiment</span><span class="sxs-lookup"><span data-stu-id="85b0c-205">Sentiment</span></span> |<span data-ttu-id="85b0c-206">フィーチャー</span><span class="sxs-lookup"><span data-stu-id="85b0c-206">Features</span></span>              |
    |--------------------------------------|----------|----------------------|
    |<span data-ttu-id="85b0c-207">Waitress was a little slow in service.</span><span class="sxs-lookup"><span data-stu-id="85b0c-207">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="85b0c-208">0</span><span class="sxs-lookup"><span data-stu-id="85b0c-208">0</span></span>     |<span data-ttu-id="85b0c-209">[0.76, 0.65, 0.44, …]</span><span class="sxs-lookup"><span data-stu-id="85b0c-209">[0.76, 0.65, 0.44, …]</span></span> |
    |<span data-ttu-id="85b0c-210">Crust is not good.</span><span class="sxs-lookup"><span data-stu-id="85b0c-210">Crust is not good.</span></span>                    |    <span data-ttu-id="85b0c-211">0</span><span class="sxs-lookup"><span data-stu-id="85b0c-211">0</span></span>     |<span data-ttu-id="85b0c-212">[0.98, 0.43, 0.54, …]</span><span class="sxs-lookup"><span data-stu-id="85b0c-212">[0.98, 0.43, 0.54, …]</span></span> |
    |<span data-ttu-id="85b0c-213">Wow...Loved this place.</span><span class="sxs-lookup"><span data-stu-id="85b0c-213">Wow... Loved this place.</span></span>              |    <span data-ttu-id="85b0c-214">1</span><span class="sxs-lookup"><span data-stu-id="85b0c-214">1</span></span>     |<span data-ttu-id="85b0c-215">[0.35, 0.73, 0.46, …]</span><span class="sxs-lookup"><span data-stu-id="85b0c-215">[0.35, 0.73, 0.46, …]</span></span> |
    |<span data-ttu-id="85b0c-216">Service was very prompt.</span><span class="sxs-lookup"><span data-stu-id="85b0c-216">Service was very prompt.</span></span>              |    <span data-ttu-id="85b0c-217">1</span><span class="sxs-lookup"><span data-stu-id="85b0c-217">1</span></span>     |<span data-ttu-id="85b0c-218">[0.39, 0, 0.75, …]</span><span class="sxs-lookup"><span data-stu-id="85b0c-218">[0.39, 0, 0.75, …]</span></span>    |

### <a name="add-a-learning-algorithm"></a><span data-ttu-id="85b0c-219">学習アルゴリズムを追加する</span><span class="sxs-lookup"><span data-stu-id="85b0c-219">Add a learning algorithm</span></span>

<span data-ttu-id="85b0c-220">このアプリでは、データの項目または行を分類する分類アルゴリズムを使用しています。</span><span class="sxs-lookup"><span data-stu-id="85b0c-220">This app uses a classification algorithm that categorizes items or rows of data.</span></span> <span data-ttu-id="85b0c-221">このアプリでは、Web サイトのコメントが肯定的または否定的に分類されるので、二項分類タスクが使用されます。</span><span class="sxs-lookup"><span data-stu-id="85b0c-221">The app categorizes website comments as either positive or negative, so use the binary classification task.</span></span>

<span data-ttu-id="85b0c-222">データ変換定義に機械学習タスクを追加するには、`BuildAndTrainModel()` の次のコード行に以下を追加します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-222">Append the machine learning task to the data transformation definitions by adding the following as the next line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[SdcaLogisticRegressionBinaryTrainer](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#AddTrainer "Add a SdcaLogisticRegressionBinaryTrainer")]

<span data-ttu-id="85b0c-223">[SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) が分類トレーニング アルゴリズムです。</span><span class="sxs-lookup"><span data-stu-id="85b0c-223">The [SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) is your classification training algorithm.</span></span> <span data-ttu-id="85b0c-224">これは `estimator` に追加されます。また、特徴付けされた `SentimentText` (`Features`) と `Label` 入力パラメーターを受け取って履歴データから学習します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-224">This is appended to the `estimator` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="85b0c-225">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="85b0c-225">Train the model</span></span>

<span data-ttu-id="85b0c-226">`BuildAndTrainModel()` メソッドの次のコード行として以下を追加して、モデルを `splitTrainSet` データに適合させ、トレーニング済みモデルを返します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-226">Fit the model to the `splitTrainSet` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[TrainModel](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#TrainModel "Train the model")]

<span data-ttu-id="85b0c-227">[Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) メソッドでは、データセットを変換して、トレーニングを適用することにより、モデルがトレーニングされます。</span><span class="sxs-lookup"><span data-stu-id="85b0c-227">The [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model by transforming the dataset and applying the training.</span></span>

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="85b0c-228">評価に使用する、トレーニング済みのモデルを返す</span><span class="sxs-lookup"><span data-stu-id="85b0c-228">Return the model trained to use for evaluation</span></span>

 <span data-ttu-id="85b0c-229">`BuildAndTrainModel()` メソッドの終了時にモデルを返します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-229">Return the model at the end of the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[ReturnModel](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="85b0c-230">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="85b0c-230">Evaluate the model</span></span>

<span data-ttu-id="85b0c-231">モデルのトレーニングが終わったら、テスト データを使用してモデルのパフォーマンスを検証します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-231">After your model is trained, use your test data validate the model's performance.</span></span>

1. <span data-ttu-id="85b0c-232">`BuildAndTrainModel()` の直後に、次のコードを使用して `Evaluate()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-232">Create the `Evaluate()` method, just after `BuildAndTrainModel()`, with the following code:</span></span>

    ```csharp
    public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
    {

    }
    ```

    <span data-ttu-id="85b0c-233">`Evaluate()` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-233">The `Evaluate()` method executes the following tasks:</span></span>

    - <span data-ttu-id="85b0c-234">テスト データ セットを読み込む。</span><span class="sxs-lookup"><span data-stu-id="85b0c-234">Loads the test dataset.</span></span>
    - <span data-ttu-id="85b0c-235">BinaryClassification エバリュエーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-235">Creates the BinaryClassification evaluator.</span></span>
    - <span data-ttu-id="85b0c-236">モデルを評価し、メトリックを作成する。</span><span class="sxs-lookup"><span data-stu-id="85b0c-236">Evaluates the model and creates metrics.</span></span>
    - <span data-ttu-id="85b0c-237">メトリックを表示する。</span><span class="sxs-lookup"><span data-stu-id="85b0c-237">Displays the metrics.</span></span>

2. <span data-ttu-id="85b0c-238">`BuildAndTrainModel()` メソッドの呼び出しのすぐ下に、次のコードを使用して、`Main()` メソッドからの新しいメソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-238">Add a call to the new method from the `Main()` method, right under the `BuildAndTrainModel()` method call, using the following code:</span></span>

    [!code-csharp[CallEvaluate](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallEvaluate "Call the Evaluate method")]

3. <span data-ttu-id="85b0c-239">次のコードを `Evaluate()` に追加して、`splitTestSet` データを変換します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-239">Transform the `splitTestSet` data by adding the following code to `Evaluate()`:</span></span>

    [!code-csharp[PredictWithTransformer](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#TransformData "Predict using the Transformer")]

    <span data-ttu-id="85b0c-240">前のコードでは、[Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) メソッドを使用して、テスト データセットの指定した複数の入力行に対して予測しています。</span><span class="sxs-lookup"><span data-stu-id="85b0c-240">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple provided input rows of a test dataset.</span></span>

4. <span data-ttu-id="85b0c-241">`Evaluate()` メソッドの次のコード行として以下を追加して、モデルを評価します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-241">Evaluate the model by adding the following as the next line of code in the `Evaluate()` method:</span></span>

    [!code-csharp[ComputeMetrics](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#Evaluate "Compute Metrics")]

<span data-ttu-id="85b0c-242">予測セット (`predictions`) ができると、[Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A)メソッドによってモデルが評価され、予測値とテスト データセット内の実際の `Labels` が比較され、モデルのパフォーマンスに関する [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="85b0c-242">Once you have the prediction set (`predictions`), the [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns a [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) object on how the model is performing.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="85b0c-243">モデル検証のためのメトリックを表示する</span><span class="sxs-lookup"><span data-stu-id="85b0c-243">Displaying the metrics for model validation</span></span>

<span data-ttu-id="85b0c-244">次のコードを使用してメトリックを表示します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-244">Use the following code to display the metrics:</span></span>

[!code-csharp[DisplayMetrics](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#DisplayMetrics "Display selected metrics")]

- <span data-ttu-id="85b0c-245">`Accuracy` メトリックでは、モデルの正確度が取得されます。これは、テスト セットに含まれる正しい予測の割合です。</span><span class="sxs-lookup"><span data-stu-id="85b0c-245">The `Accuracy` metric gets the accuracy of a model, which is the proportion of correct predictions in the test set.</span></span>

- <span data-ttu-id="85b0c-246">`AreaUnderRocCurve` メトリックは、そのモデルで肯定的クラスと否定的クラスが正しく分類されている信用度を示します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-246">The `AreaUnderRocCurve` metric indicates how confident the model is correctly classifying the positive and negative classes.</span></span> <span data-ttu-id="85b0c-247">`AreaUnderRocCurve` を可能な限り 1 に近づけることが目標です。</span><span class="sxs-lookup"><span data-stu-id="85b0c-247">You want the `AreaUnderRocCurve` to be as close to one as possible.</span></span>

- <span data-ttu-id="85b0c-248">`F1Score` メトリックでは、モデルの F1 スコアが取得されます。これは[精度](../resources/glossary.md#precision)と[再現率](../resources/glossary.md#recall)間のバランスのメジャーです。</span><span class="sxs-lookup"><span data-stu-id="85b0c-248">The `F1Score` metric gets the model's F1 score, which is a measure of balance between [precision](../resources/glossary.md#precision) and [recall](../resources/glossary.md#recall).</span></span>  <span data-ttu-id="85b0c-249">`F1Score` を可能な限り 1 に近づけることが目標です。</span><span class="sxs-lookup"><span data-stu-id="85b0c-249">You want the `F1Score` to be as close to one as possible.</span></span>

### <a name="predict-the-test-data-outcome"></a><span data-ttu-id="85b0c-250">テスト データの結果を予測する</span><span class="sxs-lookup"><span data-stu-id="85b0c-250">Predict the test data outcome</span></span>

1. <span data-ttu-id="85b0c-251">`Evaluate()` メソッドの直後に、次のコードを使用して `UseModelWithSingleItem()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-251">Create the `UseModelWithSingleItem()` method, just after the `Evaluate()` method, using the following code:</span></span>

    ```csharp
    private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="85b0c-252">`UseModelWithSingleItem()` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-252">The `UseModelWithSingleItem()` method executes the following tasks:</span></span>

    - <span data-ttu-id="85b0c-253">テスト データの 1 つのコメントを作成する。</span><span class="sxs-lookup"><span data-stu-id="85b0c-253">Creates a single comment of test data.</span></span>
    - <span data-ttu-id="85b0c-254">テスト データに基づいてセンチメントを予測する。</span><span class="sxs-lookup"><span data-stu-id="85b0c-254">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="85b0c-255">テスト データと予測をレポート用に結合する。</span><span class="sxs-lookup"><span data-stu-id="85b0c-255">Combines test data and predictions for reporting.</span></span>
    - <span data-ttu-id="85b0c-256">予測された結果を表示する。</span><span class="sxs-lookup"><span data-stu-id="85b0c-256">Displays the predicted results.</span></span>

2. <span data-ttu-id="85b0c-257">`Evaluate()` メソッドの呼び出しのすぐ下に、次のコードを使用して、`Main()` メソッドからの新しいメソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-257">Add a call to the new method from the `Main()` method, right under the `Evaluate()` method call, using the following code:</span></span>

    [!code-csharp[CallUseModelWithSingleItem](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

3. <span data-ttu-id="85b0c-258">次のコードを追加して、`UseModelWithSingleItem()` メソッドの 1 行目として作成します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-258">Add the following code to create as the first line in the `UseModelWithSingleItem()` Method:</span></span>

    [!code-csharp[CreatePredictionEngine](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]

    <span data-ttu-id="85b0c-259">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) は、データの 1 つのインスタンスに対して予測を実行できる便利な API です。</span><span class="sxs-lookup"><span data-stu-id="85b0c-259">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="85b0c-260">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) はスレッド セーフではありません。</span><span class="sxs-lookup"><span data-stu-id="85b0c-260">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="85b0c-261">シングル スレッド環境またはプロトタイプ環境で使用できます。</span><span class="sxs-lookup"><span data-stu-id="85b0c-261">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="85b0c-262">運用環境でパフォーマンスとスレッド セーフを向上させるには、`PredictionEnginePool` サービスを使用します。これにより、アプリケーション全体で使用するできる [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) オブジェクトの [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="85b0c-262">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="85b0c-263">[ASP.NET Core Web API で `PredictionEnginePool` を使用する](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application)方法については、こちらのガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="85b0c-263">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

    > [!NOTE]
    > <span data-ttu-id="85b0c-264">`PredictionEnginePool` サービスの拡張機能は、現在プレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="85b0c-264">`PredictionEnginePool` service extension is currently in preview.</span></span>

4. <span data-ttu-id="85b0c-265">コメントを追加して、`UseModelWithSingleItem()` メソッドでトレーニングされたモデルの予測をテストします。これには `SentimentData` のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-265">Add a comment to test the trained model's prediction in the `UseModelWithSingleItem()` method by creating an instance of `SentimentData`:</span></span>

    [!code-csharp[PredictionData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

5. <span data-ttu-id="85b0c-266">`UseModelWithSingleItem()` メソッドの次のコード行として以下を追加して、テスト コメント データを [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) に渡します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-266">Pass the test comment data to the [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) by adding the following as the next lines of code in the `UseModelWithSingleItem()` method:</span></span>

    [!code-csharp[Predict](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#Predict "Create a prediction of sentiment")]

    <span data-ttu-id="85b0c-267">[Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) 関数では、データの 1 つの行に対して予測を行います。</span><span class="sxs-lookup"><span data-stu-id="85b0c-267">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data.</span></span>

6. <span data-ttu-id="85b0c-268">次のコードを使用して、`SentimentText` とそれに対応するセンチメント予測を表示します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-268">Display `SentimentText` and corresponding sentiment prediction using the following code:</span></span>

    [!code-csharp[OutputPrediction](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#OutputPrediction "Display prediction output")]

## <a name="use-the-model-for-prediction"></a><span data-ttu-id="85b0c-269">予測にモデルを使用する</span><span class="sxs-lookup"><span data-stu-id="85b0c-269">Use the model for prediction</span></span>

### <a name="deploy-and-predict-batch-items"></a><span data-ttu-id="85b0c-270">バッチ項目の展開と予測</span><span class="sxs-lookup"><span data-stu-id="85b0c-270">Deploy and predict batch items</span></span>

1. <span data-ttu-id="85b0c-271">`UseModelWithSingleItem()` メソッドの直後に、次のコードを使用して `UseModelWithBatchItems()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-271">Create the `UseModelWithBatchItems()` method, just after the `UseModelWithSingleItem()` method, using the following code:</span></span>

    ```csharp
    public static void UseModelWithBatchItems(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="85b0c-272">`UseModelWithBatchItems()` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-272">The `UseModelWithBatchItems()` method executes the following tasks:</span></span>

    - <span data-ttu-id="85b0c-273">バッチ テスト データを作成します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-273">Creates batch test data.</span></span>
    - <span data-ttu-id="85b0c-274">テスト データに基づいてセンチメントを予測する。</span><span class="sxs-lookup"><span data-stu-id="85b0c-274">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="85b0c-275">テスト データと予測をレポート用に結合する。</span><span class="sxs-lookup"><span data-stu-id="85b0c-275">Combines test data and predictions for reporting.</span></span>
    - <span data-ttu-id="85b0c-276">予測された結果を表示する。</span><span class="sxs-lookup"><span data-stu-id="85b0c-276">Displays the predicted results.</span></span>

2. <span data-ttu-id="85b0c-277">`UseModelWithSingleItem()` メソッドの呼び出しのすぐ下に、次のコードを使用して、`Main` メソッドからの新しいメソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-277">Add a call to the new method from the `Main` method, right under the `UseModelWithSingleItem()` method call, using the following code:</span></span>

    [!code-csharp[CallPredictModelBatchItems](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallUseModelWithBatchItems "Call the CallUseModelWithBatchItems method")]

3. <span data-ttu-id="85b0c-278">`UseModelWithBatchItems()` メソッドでトレーニングされるモデルの予測をテストするために、いくつかのコメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-278">Add some comments to test the trained model's predictions in the `UseModelWithBatchItems()` method:</span></span>

    [!code-csharp[PredictionData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreateTestIssues "Create test data for predictions")]

### <a name="predict-comment-sentiment"></a><span data-ttu-id="85b0c-279">コメントのセンチメントを予測する</span><span class="sxs-lookup"><span data-stu-id="85b0c-279">Predict comment sentiment</span></span>

<span data-ttu-id="85b0c-280">モデルを使用し、[Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) メソッドを使用してコメント データのセンチメントを予測します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-280">Use the model to predict the comment data sentiment using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method:</span></span>

[!code-csharp[Predict](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="combine-and-display-the-predictions"></a><span data-ttu-id="85b0c-281">予測を組み合わせて表示する</span><span class="sxs-lookup"><span data-stu-id="85b0c-281">Combine and display the predictions</span></span>

<span data-ttu-id="85b0c-282">次のコードを使用して、予測のヘッダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="85b0c-282">Create a header for the predictions using the following code:</span></span>

[!code-csharp[OutputHeaders](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#AddInfoMessage "Display prediction outputs")]

<span data-ttu-id="85b0c-283">`SentimentPrediction` は `SentimentData` から継承されているため、`Transform()` メソッドによって `SentimentText` に予測されたフィールドが設定されました。</span><span class="sxs-lookup"><span data-stu-id="85b0c-283">Because `SentimentPrediction` is inherited from `SentimentData`, the `Transform()` method populated `SentimentText` with the predicted fields.</span></span> <span data-ttu-id="85b0c-284">ML.NET プロセスが進むにつれて、各コンポーネントに列が追加されます。これで、結果が簡単に表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="85b0c-284">As the ML.NET process processes, each component adds columns, and this makes it easy to display the results:</span></span>

[!code-csharp[DisplayPredictions](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#DisplayResults "Display the predictions")]

## <a name="results"></a><span data-ttu-id="85b0c-285">結果</span><span class="sxs-lookup"><span data-stu-id="85b0c-285">Results</span></span>

<span data-ttu-id="85b0c-286">結果は以下のようになるはずです。</span><span class="sxs-lookup"><span data-stu-id="85b0c-286">Your results should be similar to the following.</span></span> <span data-ttu-id="85b0c-287">処理中にメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="85b0c-287">During processing, messages are displayed.</span></span> <span data-ttu-id="85b0c-288">警告または処理メッセージが表示されることがありますが、</span><span class="sxs-lookup"><span data-stu-id="85b0c-288">You may see warnings, or processing messages.</span></span> <span data-ttu-id="85b0c-289">わかりやすくするために、それらは次の結果から削除してあります。</span><span class="sxs-lookup"><span data-stu-id="85b0c-289">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 83.96%
Auc: 90.51%
F1Score: 84.04%

=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.1027377
=============== End of Predictions ===============

=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1369192
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9960636
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

<span data-ttu-id="85b0c-290">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="85b0c-290">Congratulations!</span></span> <span data-ttu-id="85b0c-291">これで、メッセージのセンチメントを分類および予測するための機械学習モデルをビルドできました。</span><span class="sxs-lookup"><span data-stu-id="85b0c-291">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span>

<span data-ttu-id="85b0c-292">優れたモデルの構築は、反復的なプロセスです。</span><span class="sxs-lookup"><span data-stu-id="85b0c-292">Building successful models is an iterative process.</span></span> <span data-ttu-id="85b0c-293">このチュートリアルでは、モデルのトレーニングを短時間で実行するために小さなデータセットを使用しているため、このモデルの品質は最初は低くなっています。</span><span class="sxs-lookup"><span data-stu-id="85b0c-293">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="85b0c-294">このモデルの品質に満足できなければ、大規模なトレーニング データセットを使用するか、別のトレーニング アルゴリズムとアルゴリズムごとに異なる[ハイパーパラメーター](../resources/glossary.md#hyperparameter)を選択してモデルの改良を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="85b0c-294">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different [hyper-parameters](../resources/glossary.md#hyperparameter) for each algorithm.</span></span>

<span data-ttu-id="85b0c-295">このチュートリアルのソース コードは [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) リポジトリで確認できます。</span><span class="sxs-lookup"><span data-stu-id="85b0c-295">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="85b0c-296">次の手順</span><span class="sxs-lookup"><span data-stu-id="85b0c-296">Next steps</span></span>

<span data-ttu-id="85b0c-297">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="85b0c-297">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="85b0c-298">コンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="85b0c-298">Create a console application</span></span>
> - <span data-ttu-id="85b0c-299">データの準備</span><span class="sxs-lookup"><span data-stu-id="85b0c-299">Prepare data</span></span>
> - <span data-ttu-id="85b0c-300">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="85b0c-300">Load the data</span></span>
> - <span data-ttu-id="85b0c-301">モデルを構築してトレーニングする</span><span class="sxs-lookup"><span data-stu-id="85b0c-301">Build and train the model</span></span>
> - <span data-ttu-id="85b0c-302">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="85b0c-302">Evaluate the model</span></span>
> - <span data-ttu-id="85b0c-303">モデルを使用して予測する</span><span class="sxs-lookup"><span data-stu-id="85b0c-303">Use the model to make a prediction</span></span>
> - <span data-ttu-id="85b0c-304">結果を見る</span><span class="sxs-lookup"><span data-stu-id="85b0c-304">See the results</span></span>

<span data-ttu-id="85b0c-305">さらに詳しく学習するには、次のチュートリアルに進んでください。</span><span class="sxs-lookup"><span data-stu-id="85b0c-305">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="85b0c-306">問題の分類</span><span class="sxs-lookup"><span data-stu-id="85b0c-306">Issue Classification</span></span>](github-issue-classification.md)
