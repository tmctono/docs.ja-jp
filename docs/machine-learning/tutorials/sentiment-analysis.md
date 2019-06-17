---
title: 'チュートリアル: Web サイトのコメントを分析する - 二項分類'
description: このチュートリアルでは、Web サイトのコメントからセンチメントを分類して適切なアクションを実行する .NET Core コンソール アプリケーションの作成方法について説明します。 この二項センチメント分類子には、Visual Studio で C# を使用します。
ms.date: 05/13/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 674dc2d12cb8f65753730e187e13fc5e522ff6b3
ms.sourcegitcommit: ced0cccf15adfd492f8196cb739f01dde52c9252
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2019
ms.locfileid: "67135702"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-with-binary-classification-in-mlnet"></a><span data-ttu-id="66ba3-104">チュートリアル: ML.NET の二項分類を使用して Web サイトのコメントのセンチメントを分析する</span><span class="sxs-lookup"><span data-stu-id="66ba3-104">Tutorial: Analyze sentiment of website comments with binary classification in ML.NET</span></span>

<span data-ttu-id="66ba3-105">このチュートリアルでは、Web サイトのコメントからセンチメントを分類して適切なアクションを実行する .NET Core コンソール アプリケーションの作成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-105">This tutorial shows you how to create a .NET Core console application that classifies sentiment from website comments and takes the appropriate action.</span></span> <span data-ttu-id="66ba3-106">この二項センチメント分類子には、Visual Studio 2017 で C# を使用します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-106">The binary sentiment classifier uses C# in Visual Studio 2017.</span></span>

<span data-ttu-id="66ba3-107">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="66ba3-108">コンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="66ba3-108">Create a console application</span></span>
> * <span data-ttu-id="66ba3-109">データの準備</span><span class="sxs-lookup"><span data-stu-id="66ba3-109">Prepare data</span></span>
> * <span data-ttu-id="66ba3-110">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="66ba3-110">Load the data</span></span>
> * <span data-ttu-id="66ba3-111">モデルを構築してトレーニングする</span><span class="sxs-lookup"><span data-stu-id="66ba3-111">Build and train the model</span></span>
> * <span data-ttu-id="66ba3-112">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="66ba3-112">Evaluate the model</span></span>
> * <span data-ttu-id="66ba3-113">モデルを使用して予測する</span><span class="sxs-lookup"><span data-stu-id="66ba3-113">Use the model to make a prediction</span></span>
> * <span data-ttu-id="66ba3-114">結果を見る</span><span class="sxs-lookup"><span data-stu-id="66ba3-114">See the results</span></span>

<span data-ttu-id="66ba3-115">このチュートリアルのソース コードは [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) リポジトリで確認できます。</span><span class="sxs-lookup"><span data-stu-id="66ba3-115">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="66ba3-116">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="66ba3-116">Prerequisites</span></span>

* <span data-ttu-id="66ba3-117">[Visual Studio 2017 15.6 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)が ".NET Core クロスプラット フォーム開発" ワークロードと共にインストールされている</span><span class="sxs-lookup"><span data-stu-id="66ba3-117">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed</span></span>

* <span data-ttu-id="66ba3-118">[UCI Sentiment Labeled Sentences データセット](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (ZIP ファイル)</span><span class="sxs-lookup"><span data-stu-id="66ba3-118">[UCI Sentiment Labeled Sentences dataset](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (ZIP file)</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="66ba3-119">コンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="66ba3-119">Create a console application</span></span>

1. <span data-ttu-id="66ba3-120">"SentimentAnalysis" という名前の **.NET Core コンソール アプリケーション**を作成します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-120">Create a **.NET Core Console Application** called "SentimentAnalysis".</span></span>

2. <span data-ttu-id="66ba3-121">データ セット ファイルを保存するために、プロジェクトに *Data* という名前のディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-121">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="66ba3-122">**Microsoft.ML NuGet パッケージ**をインストールします。</span><span class="sxs-lookup"><span data-stu-id="66ba3-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="66ba3-123">ソリューション エクスプローラーで、プロジェクトを右クリックし、 **[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="66ba3-124">パッケージ ソースとして "nuget.org" を選択してから、 **[参照]** タブを選択します。**Microsoft.ML** を検索し、目的のパッケージを選択して、 **[インストール]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-124">Choose "nuget.org" as the package source, and then select the **Browse** tab. Search for **Microsoft.ML**, select the package you want, and then select the **Install** button.</span></span> <span data-ttu-id="66ba3-125">選択したパッケージのライセンス条項に同意してインストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-125">Proceed with the installation by agreeing to the the license terms for the package you choose.</span></span> <span data-ttu-id="66ba3-126">**Microsoft.ML.FastTree** NuGet パッケージに対して同じことを行います。</span><span class="sxs-lookup"><span data-stu-id="66ba3-126">Do the same for the **Microsoft.ML.FastTree** NuGet package.</span></span>

## <a name="prepare-your-data"></a><span data-ttu-id="66ba3-127">データを準備する</span><span class="sxs-lookup"><span data-stu-id="66ba3-127">Prepare your data</span></span>

> [!NOTE]
> <span data-ttu-id="66ba3-128">このチュートリアルのデータセットは、「From Group to Individual Labels using Deep Features」 (Kotzias 他</span><span class="sxs-lookup"><span data-stu-id="66ba3-128">The datasets for this tutorial are from the 'From Group to Individual Labels using Deep Features', Kotzias et.</span></span> <span data-ttu-id="66ba3-129">著、</span><span class="sxs-lookup"><span data-stu-id="66ba3-129">al,.</span></span> <span data-ttu-id="66ba3-130">KDD 2015) のものであり、UCI 機械学習リポジトリ (Dua, D. and Karra Taniskidou, E.(2017)) でホストされています。</span><span class="sxs-lookup"><span data-stu-id="66ba3-130">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="66ba3-131">UCI 機械学習リポジトリ [http://archive.ics.uci.edu/ml ]。</span><span class="sxs-lookup"><span data-stu-id="66ba3-131">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="66ba3-132">カリフォルニア州アーバイン: カリフォルニア大学情報コンピュータサイエンス学部。</span><span class="sxs-lookup"><span data-stu-id="66ba3-132">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

1. <span data-ttu-id="66ba3-133">[UCI Sentiment Labeled Sentences データセットの ZIP ファイル](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)をダウンロードし、展開します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-133">Download [UCI Sentiment Labeled Sentences dataset ZIP file](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip.</span></span>

2. <span data-ttu-id="66ba3-134">`yelp_labelled.txt` ファイルを、作成した *Data* ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="66ba3-134">Copy the `yelp_labelled.txt` file into the *Data* directory you created.</span></span>

3. <span data-ttu-id="66ba3-135">ソリューション エクスプローラーで、`yelp_labeled.txt` ファイルを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-135">In Solution Explorer, right-click the `yelp_labeled.txt` file and select **Properties**.</span></span> <span data-ttu-id="66ba3-136">**[詳細設定]** で、 **[出力ディレクトリにコピー]** の値を **[新しい場合はコピーする]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-136">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="66ba3-137">クラスを作成してパスを定義する</span><span class="sxs-lookup"><span data-stu-id="66ba3-137">Create classes and define paths</span></span>

1. <span data-ttu-id="66ba3-138">次に示す追加の `using` ステートメントを *Program.cs* ファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-138">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddUsings "Add necessary usings")]

2. <span data-ttu-id="66ba3-139">最近ダウンロードしたデータセット ファイルのパスと保存したモデル ファイルのパスを保持するために、2 つのグローバル フィールドを作成します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-139">Create two global fields to hold the recently downloaded dataset file path and the saved model file path:</span></span>

    * <span data-ttu-id="66ba3-140">`_dataPath` には、モデルのトレーニングに使用するデータ セットのパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="66ba3-140">`_dataPath` has the path to the dataset used to train the model.</span></span>
    * <span data-ttu-id="66ba3-141">`_modelPath` には、トレーニング済みのモデルを保存するパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="66ba3-141">`_modelPath` has the path where the trained model is saved.</span></span>

3. <span data-ttu-id="66ba3-142">`Main` メソッドのすぐ上にある行に次のコードを追加して、それらのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-142">Add the following code to the line right above the `Main` method to specify the paths:</span></span>

    [!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DeclareGlobalVariables "Declare global variables")]

4. <span data-ttu-id="66ba3-143">次に、入力データと予測のためにクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-143">Next, create classes for your input data and predictions.</span></span> <span data-ttu-id="66ba3-144">プロジェクトに新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-144">Add a new class to your project:</span></span>

    - <span data-ttu-id="66ba3-145">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、 **[追加]**  >  **[新しい項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-145">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

    - <span data-ttu-id="66ba3-146">**[新しい項目の追加]** ダイアログ ボックスで、 **[クラス]** を選択し、 **[名前]** フィールドを *SentimentData.cs* に変更します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-146">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="66ba3-147">次に、 **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-147">Then, select the **Add** button.</span></span>

5. <span data-ttu-id="66ba3-148">コード エディターで *SentimentData.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="66ba3-148">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="66ba3-149">*SentimentData.cs* の先頭に次の `using` ステートメントを 追加します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-149">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#AddUsings "Add necessary usings")]

6. <span data-ttu-id="66ba3-150">既存のクラス定義を削除し、`SentimentData` と `SentimentPrediction` の 2 つのクラスを含む次のコードを *SentimentData.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-150">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

    [!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#DeclareTypes "Declare data record types")]

### <a name="how-the-data-was-prepared"></a><span data-ttu-id="66ba3-151">データの準備方法</span><span class="sxs-lookup"><span data-stu-id="66ba3-151">How the data was prepared</span></span>
<span data-ttu-id="66ba3-152">入力データセット クラスの `SentimentData` には、ユーザー コメント用の `string` (`SentimentText`) と、センチメント用の 1 (肯定的) または 0 (否定的) のいずれかの `bool` (`Sentiment`) 値があります。</span><span class="sxs-lookup"><span data-stu-id="66ba3-152">The input dataset class, `SentimentData`, has a `string` for user comments (`SentimentText`) and a `bool` (`Sentiment`) value of either 1 (positive) or 0 (negative) for sentiment.</span></span> <span data-ttu-id="66ba3-153">どちらのフィールドにも [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) 属性が添付され、各フィールドのデータ ファイルの順序が記述されています。</span><span class="sxs-lookup"><span data-stu-id="66ba3-153">Both fields have [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attributes attached to them, which describes the data file order of each field.</span></span>  <span data-ttu-id="66ba3-154">さらに、`Sentiment` プロパティには、それを `Label` フィールドとして指定する [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) 属性があります。</span><span class="sxs-lookup"><span data-stu-id="66ba3-154">In addition, the `Sentiment` property has a [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) attribute to designate it as the `Label` field.</span></span> <span data-ttu-id="66ba3-155">次のファイル例にはヘッダー行がなく、次のような内容です。</span><span class="sxs-lookup"><span data-stu-id="66ba3-155">The following example file doesn't have a header row, and looks like this:</span></span>

|<span data-ttu-id="66ba3-156">SentimentText</span><span class="sxs-lookup"><span data-stu-id="66ba3-156">SentimentText</span></span>                         |<span data-ttu-id="66ba3-157">Sentiment (ラベル)</span><span class="sxs-lookup"><span data-stu-id="66ba3-157">Sentiment (Label)</span></span> |
|--------------------------------------|----------|
|<span data-ttu-id="66ba3-158">Waitress was a little slow in service.</span><span class="sxs-lookup"><span data-stu-id="66ba3-158">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="66ba3-159">0</span><span class="sxs-lookup"><span data-stu-id="66ba3-159">0</span></span>     |
|<span data-ttu-id="66ba3-160">Crust is not good.</span><span class="sxs-lookup"><span data-stu-id="66ba3-160">Crust is not good.</span></span>                    |    <span data-ttu-id="66ba3-161">0</span><span class="sxs-lookup"><span data-stu-id="66ba3-161">0</span></span>     |
|<span data-ttu-id="66ba3-162">Wow...Loved this place.</span><span class="sxs-lookup"><span data-stu-id="66ba3-162">Wow... Loved this place.</span></span>              |    <span data-ttu-id="66ba3-163">1</span><span class="sxs-lookup"><span data-stu-id="66ba3-163">1</span></span>     |
|<span data-ttu-id="66ba3-164">Service was very prompt.</span><span class="sxs-lookup"><span data-stu-id="66ba3-164">Service was very prompt.</span></span>              |    <span data-ttu-id="66ba3-165">1</span><span class="sxs-lookup"><span data-stu-id="66ba3-165">1</span></span>     |

<span data-ttu-id="66ba3-166">`SentimentPrediction` はモデルのトレーニング後に使用される予測クラスです。</span><span class="sxs-lookup"><span data-stu-id="66ba3-166">`SentimentPrediction` is the prediction class used after the model training.</span></span> <span data-ttu-id="66ba3-167">予測と共に `SentimentText` を表示するために `SentimentData` から継承されます。</span><span class="sxs-lookup"><span data-stu-id="66ba3-167">It inherits from `SentimentData` for displaying the `SentimentText` with the predictions.</span></span> <span data-ttu-id="66ba3-168">`SentimentPrediction` には 1 つのブール値 (`Sentiment`) と `PredictedLabel` `ColumnName` 属性があります。</span><span class="sxs-lookup"><span data-stu-id="66ba3-168">`SentimentPrediction` has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="66ba3-169">`Label` はモデルを作成してトレーニングするために使用され、モデルを評価するための分割されたテスト データセットでも使用されます。</span><span class="sxs-lookup"><span data-stu-id="66ba3-169">The `Label` is used to create and train the model, and it's also used with the split out test dataset to evaluate the model.</span></span> <span data-ttu-id="66ba3-170">`PredictedLabel` は予測と評価の際に使用されます。</span><span class="sxs-lookup"><span data-stu-id="66ba3-170">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="66ba3-171">評価には、トレーニング データ、予測値、およびモデルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="66ba3-171">For evaluation, training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="66ba3-172">[MLContext クラス](xref:Microsoft.ML.MLContext)は、すべての ML.NET 操作の始点です。</span><span class="sxs-lookup"><span data-stu-id="66ba3-172">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations.</span></span> <span data-ttu-id="66ba3-173">`mlContext` を初期化することで、モデル作成ワークフローのオブジェクト間で共有できる新しい ML.NET 環境が作成されます。</span><span class="sxs-lookup"><span data-stu-id="66ba3-173">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="66ba3-174">これは Entity Framework における `DBContext` と概念的には同じです。</span><span class="sxs-lookup"><span data-stu-id="66ba3-174">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="66ba3-175">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="66ba3-175">Load the data</span></span>
<span data-ttu-id="66ba3-176">ML.NET 内のデータは、[IDataView クラス](xref:Microsoft.ML.IDataView)として表されます。</span><span class="sxs-lookup"><span data-stu-id="66ba3-176">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="66ba3-177">`IDataView` は、表形式のデータ (数値とテキスト) を表すための柔軟で効率的な方法です。</span><span class="sxs-lookup"><span data-stu-id="66ba3-177">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="66ba3-178">データはテキスト ファイルから、またはリアルタイムで (SQL データベースやログ ファイルなど) `IDataView` オブジェクトに読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="66ba3-178">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="66ba3-179">アプリを準備してからデータを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="66ba3-179">You prepare the app, and then load data:</span></span>

1. <span data-ttu-id="66ba3-180">`Main` メソッドの `Console.WriteLine("Hello World!")` の行は、mlContext 変数を宣言して初期化する次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="66ba3-180">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the mlContext variable:</span></span>

    [!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateMLContext "Create the ML Context")]

2. <span data-ttu-id="66ba3-181">`Main()` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-181">Add the following as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallLoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallLoadData)]

3. <span data-ttu-id="66ba3-182">`Main()` メソッドの直後に、次のコードを使用して `LoadData()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-182">Create the `LoadData()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static TrainTestData LoadData(MLContext mlContext)
    {

    }
    ```

    <span data-ttu-id="66ba3-183">`LoadData()` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-183">The `LoadData()` method executes the following tasks:</span></span>

    * <span data-ttu-id="66ba3-184">データを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="66ba3-184">Loads the data.</span></span>
    * <span data-ttu-id="66ba3-185">読み込んだデータセットを、トレーニングデータセットとテスト データセットに分割します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-185">Splits the loaded dataset into train and test datasets.</span></span>
    * <span data-ttu-id="66ba3-186">分割されたトレーニングデータセットとテスト データセットを返します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-186">Returns the split train and test datasets.</span></span>

4. <span data-ttu-id="66ba3-187">`LoadData()` メソッドの最初の行として、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-187">Add the following code as the first line of the `LoadData()` method:</span></span>

    [!code-csharp[LoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadData "loading dataset")]

    <span data-ttu-id="66ba3-188">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) は、データ スキーマを定義し、ファイルを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="66ba3-188">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="66ba3-189">データ パス変数を取得して、`IDataView` を返します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-189">It takes in the data path variables and returns an `IDataView`.</span></span>

### <a name="split-the-dataset-for-model-training-and-testing"></a><span data-ttu-id="66ba3-190">モデルのトレーニング用とテスト用にデータセットを分割する</span><span class="sxs-lookup"><span data-stu-id="66ba3-190">Split the dataset for model training and testing</span></span>

<span data-ttu-id="66ba3-191">モデルを準備するときは、データセットの一部を使用してモデルをトレーニングし、データセットの一部を使用してモデルの正確度をテストします。</span><span class="sxs-lookup"><span data-stu-id="66ba3-191">When preparing a model, you use part of the dataset to train it and part of the dataset to test the model's accuracy.</span></span>

1. <span data-ttu-id="66ba3-192">読み込まれたデータを必要なデータセットに分割するには、`LoadData()` メソッドの次の行として、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-192">To split the loaded data into the needed datasets, add the following code as the next line in the `LoadData()` method:</span></span>

    [!code-csharp[SplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SplitData "Split the Data")]

    <span data-ttu-id="66ba3-193">前のコードでは、[TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) メソッドを使用して、読み込まれたデータセットをトレーニング データセットとテスト データセットに分割し、それらを [TrainTestData](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) クラスで返します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-193">The previous code uses the [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) method to split the loaded dataset into train and test datasets and return them in the [TrainTestData](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) class.</span></span> <span data-ttu-id="66ba3-194">`testFraction` パラメーターを使用して、データに占めるテスト セットの割合を指定します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-194">Specify the test set percentage of data with the `testFraction`parameter.</span></span> <span data-ttu-id="66ba3-195">既定値は 10% です。この場合、より多くのデータを評価するために 20% を使用します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-195">The default is 10%, in this case you use 20% to evaluate more data.</span></span>

2. <span data-ttu-id="66ba3-196">`LoadData()` メソッドの最後に、`splitDataView` が返されます。</span><span class="sxs-lookup"><span data-stu-id="66ba3-196">Return the `splitDataView` at the end of the `LoadData()` method:</span></span>

    [!code-csharp[ReturnSplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a><span data-ttu-id="66ba3-197">モデルを構築してトレーニングする</span><span class="sxs-lookup"><span data-stu-id="66ba3-197">Build and train the model</span></span>

1. <span data-ttu-id="66ba3-198">`Main()` メソッドの次のコード行として、`BuildAndTrainModel` メソッドに次の呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-198">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallBuildAndTrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallBuildAndTrainModel)]

    <span data-ttu-id="66ba3-199">`BuildAndTrainModel()` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-199">The `BuildAndTrainModel()` method executes the following tasks:</span></span>

    * <span data-ttu-id="66ba3-200">データを抽出して変換します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-200">Extracts and transforms the data.</span></span>
    * <span data-ttu-id="66ba3-201">モデルをトレーニングする。</span><span class="sxs-lookup"><span data-stu-id="66ba3-201">Trains the model.</span></span>
    * <span data-ttu-id="66ba3-202">テスト データに基づいてセンチメントを予測する。</span><span class="sxs-lookup"><span data-stu-id="66ba3-202">Predicts sentiment based on test data.</span></span>
    * <span data-ttu-id="66ba3-203">モデルを返します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-203">Returns the model.</span></span>

2. <span data-ttu-id="66ba3-204">`Main()` メソッドの直後に、次のコードを使用して `BuildAndTrainModel()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-204">Create the `BuildAndTrainModel()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
    {

    }
    ```

### <a name="extract-and-transform-the-data"></a><span data-ttu-id="66ba3-205">データを抽出して変換する</span><span class="sxs-lookup"><span data-stu-id="66ba3-205">Extract and transform the data</span></span>

1. <span data-ttu-id="66ba3-206">次のコード行として `FeaturizeText` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-206">Call `FeaturizeText` as the next line of code:</span></span>

    [!code-csharp[FeaturizeText](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#FeaturizeText "Featurize the text")]

    <span data-ttu-id="66ba3-207">前のコードの `FeaturizeText()` メソッドでは、テキスト列 (`SentimentText`) を機械学習アルゴリズムから使用される数値キー型の `Features` 列に変換し、それを新しいデータセット列として追加します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-207">The `FeaturizeText()` method in the previous code converts the text column (`SentimentText`) into a numeric key type `Features` column used by the machine learning algorithm and adds it as a new dataset column:</span></span>

    |<span data-ttu-id="66ba3-208">SentimentText</span><span class="sxs-lookup"><span data-stu-id="66ba3-208">SentimentText</span></span>                         |<span data-ttu-id="66ba3-209">Sentiment</span><span class="sxs-lookup"><span data-stu-id="66ba3-209">Sentiment</span></span> |<span data-ttu-id="66ba3-210">フィーチャー</span><span class="sxs-lookup"><span data-stu-id="66ba3-210">Features</span></span>              |
    |--------------------------------------|----------|----------------------|
    |<span data-ttu-id="66ba3-211">Waitress was a little slow in service.</span><span class="sxs-lookup"><span data-stu-id="66ba3-211">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="66ba3-212">0</span><span class="sxs-lookup"><span data-stu-id="66ba3-212">0</span></span>     |<span data-ttu-id="66ba3-213">[0.76, 0.65, 0.44, …]</span><span class="sxs-lookup"><span data-stu-id="66ba3-213">[0.76, 0.65, 0.44, …]</span></span> |
    |<span data-ttu-id="66ba3-214">Crust is not good.</span><span class="sxs-lookup"><span data-stu-id="66ba3-214">Crust is not good.</span></span>                    |    <span data-ttu-id="66ba3-215">0</span><span class="sxs-lookup"><span data-stu-id="66ba3-215">0</span></span>     |<span data-ttu-id="66ba3-216">[0.98, 0.43, 0.54, …]</span><span class="sxs-lookup"><span data-stu-id="66ba3-216">[0.98, 0.43, 0.54, …]</span></span> |
    |<span data-ttu-id="66ba3-217">Wow...Loved this place.</span><span class="sxs-lookup"><span data-stu-id="66ba3-217">Wow... Loved this place.</span></span>              |    <span data-ttu-id="66ba3-218">1</span><span class="sxs-lookup"><span data-stu-id="66ba3-218">1</span></span>     |<span data-ttu-id="66ba3-219">[0.35, 0.73, 0.46, …]</span><span class="sxs-lookup"><span data-stu-id="66ba3-219">[0.35, 0.73, 0.46, …]</span></span> |
    |<span data-ttu-id="66ba3-220">Service was very prompt.</span><span class="sxs-lookup"><span data-stu-id="66ba3-220">Service was very prompt.</span></span>              |    <span data-ttu-id="66ba3-221">1</span><span class="sxs-lookup"><span data-stu-id="66ba3-221">1</span></span>     |<span data-ttu-id="66ba3-222">[0.39, 0, 0.75, …]</span><span class="sxs-lookup"><span data-stu-id="66ba3-222">[0.39, 0, 0.75, …]</span></span>    |

### <a name="add-a-learning-algorithm"></a><span data-ttu-id="66ba3-223">学習アルゴリズムを追加する</span><span class="sxs-lookup"><span data-stu-id="66ba3-223">Add a learning algorithm</span></span>

<span data-ttu-id="66ba3-224">このアプリでは、データの項目または行を分類する分類アルゴリズムを使用しています。</span><span class="sxs-lookup"><span data-stu-id="66ba3-224">This app uses a classification algorithm that categorizes items or rows of data.</span></span> <span data-ttu-id="66ba3-225">このアプリでは、Web サイトのコメントが肯定的または否定的に分類されるので、二項分類タスクが使用されます。</span><span class="sxs-lookup"><span data-stu-id="66ba3-225">The app categorizes website comments as either positive or negative, so use the binary classification task.</span></span>

<span data-ttu-id="66ba3-226">データ変換定義に機械学習タスクを追加するには、`BuildAndTrainModel()` の次のコード行に以下を追加します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-226">Append the machine learning task to the data transformation definitions by adding the following as the next line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[SdcaLogisticRegressionBinaryTrainer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddTrainer "Add a SdcaLogisticRegressionBinaryTrainer")]

<span data-ttu-id="66ba3-227">[SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) が分類トレーニング アルゴリズムです。</span><span class="sxs-lookup"><span data-stu-id="66ba3-227">The [SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) is your classification training algorithm.</span></span> <span data-ttu-id="66ba3-228">これは `estimator` に追加されます。また、特徴付けされた `SentimentText` (`Features`) と `Label` 入力パラメーターを受け取って履歴データから学習します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-228">This is appended to the `estimator` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="66ba3-229">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="66ba3-229">Train the model</span></span>

<span data-ttu-id="66ba3-230">`BuildAndTrainModel()` メソッドの次のコード行として以下を追加して、モデルを `splitTrainSet` データに適合させ、トレーニング済みモデルを返します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-230">Fit the model to the `splitTrainSet` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TrainModel "Train the model")]

<span data-ttu-id="66ba3-231">[Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) メソッドでは、データセットを変換して、トレーニングを適用することにより、モデルがトレーニングされます。</span><span class="sxs-lookup"><span data-stu-id="66ba3-231">The [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model by transforming the dataset and applying the training.</span></span>

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="66ba3-232">評価に使用する、トレーニング済みのモデルを返す</span><span class="sxs-lookup"><span data-stu-id="66ba3-232">Return the model trained to use for evaluation</span></span>

 <span data-ttu-id="66ba3-233">`BuildAndTrainModel()` メソッドの終了時にモデルを返します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-233">Return the model at the end of the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="66ba3-234">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="66ba3-234">Evaluate the model</span></span>

<span data-ttu-id="66ba3-235">モデルのトレーニングが終わったら、テスト データを使用してモデルのパフォーマンスを検証します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-235">After your model is trained, use your test data validate the model's performance.</span></span>

1. <span data-ttu-id="66ba3-236">`BuildAndTrainModel()` の直後に、次のコードを使用して `Evaluate()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-236">Create the `Evaluate()` method, just after `BuildAndTrainModel()`, with the following code:</span></span>

    ```csharp
    public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
    {

    }
    ```

    <span data-ttu-id="66ba3-237">`Evaluate()` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-237">The `Evaluate()` method executes the following tasks:</span></span>

    * <span data-ttu-id="66ba3-238">テスト データ セットを読み込む。</span><span class="sxs-lookup"><span data-stu-id="66ba3-238">Loads the test dataset.</span></span>
    * <span data-ttu-id="66ba3-239">BinaryClassification エバリュエーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-239">Creates the BinaryClassification evaluator.</span></span>
    * <span data-ttu-id="66ba3-240">モデルを評価し、メトリックを作成する。</span><span class="sxs-lookup"><span data-stu-id="66ba3-240">Evaluates the model and creates metrics.</span></span>
    * <span data-ttu-id="66ba3-241">メトリックを表示する。</span><span class="sxs-lookup"><span data-stu-id="66ba3-241">Displays the metrics.</span></span>

2. <span data-ttu-id="66ba3-242">`BuildAndTrainModel()` メソッドの呼び出しのすぐ下に、次のコードを使用して、`Main()` メソッドからの新しいメソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-242">Add a call to the new method from the `Main()` method, right under the `BuildAndTrainModel()` method call, using the following code:</span></span>

    [!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallEvaluate "Call the Evaluate method")]

3. <span data-ttu-id="66ba3-243">次のコードを `Evaluate()` に追加して、`splitTestSet` データを変換します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-243">Transform the `splitTestSet` data by adding the following code to `Evaluate()`:</span></span>

    [!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TransformData "Predict using the Transformer")]

    <span data-ttu-id="66ba3-244">前のコードでは、[Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) メソッドを使用して、テスト データセットの指定した複数の入力行に対して予測しています。</span><span class="sxs-lookup"><span data-stu-id="66ba3-244">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple provided input rows of a test dataset.</span></span>

4. <span data-ttu-id="66ba3-245">`Evaluate()` メソッドの次のコード行として以下を追加して、モデルを評価します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-245">Evaluate the model by adding the following as the next line of code in the `Evaluate()` method:</span></span>

    [!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Evaluate "Compute Metrics")]

<span data-ttu-id="66ba3-246">予測セット (`predictions`) ができると、[Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A)メソッドによってモデルが評価され、予測値とテスト データセット内の実際の `Labels` が比較され、モデルのパフォーマンスに関する [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="66ba3-246">Once you have the prediction set (`predictions`), the [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns a [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) object on how the model is performing.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="66ba3-247">モデル検証のためのメトリックを表示する</span><span class="sxs-lookup"><span data-stu-id="66ba3-247">Displaying the metrics for model validation</span></span>

<span data-ttu-id="66ba3-248">次のコードを使用してメトリックを表示します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-248">Use the following code to display the metrics:</span></span>

[!code-csharp[DisplayMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayMetrics "Display selected metrics")]

* <span data-ttu-id="66ba3-249">`Accuracy` メトリックでは、モデルの正確度が取得されます。これは、テスト セットに含まれる正しい予測の割合です。</span><span class="sxs-lookup"><span data-stu-id="66ba3-249">The `Accuracy` metric gets the accuracy of a model, which is the proportion of correct predictions in the test set.</span></span>

* <span data-ttu-id="66ba3-250">`AreaUnderRocCurve` メトリックは、そのモデルで肯定的クラスと否定的クラスが正しく分類されている信用度を示します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-250">The `AreaUnderRocCurve` metric indicates how confident the model is correctly classifying the positive and negative classes.</span></span> <span data-ttu-id="66ba3-251">`AreaUnderRocCurve` を可能な限り 1 に近づけることが目標です。</span><span class="sxs-lookup"><span data-stu-id="66ba3-251">You want the `AreaUnderRocCurve` to be as close to one as possible.</span></span>

* <span data-ttu-id="66ba3-252">`F1Score` メトリックでは、モデルの F1 スコアが取得されます。これは[精度](../resources/glossary.md#precision)と[再現率](../resources/glossary.md#recall)間のバランスのメジャーです。</span><span class="sxs-lookup"><span data-stu-id="66ba3-252">The `F1Score` metric gets the model's F1 score, which is a measure of balance between [precision](../resources/glossary.md#precision) and [recall](../resources/glossary.md#recall).</span></span>  <span data-ttu-id="66ba3-253">`F1Score` を可能な限り 1 に近づけることが目標です。</span><span class="sxs-lookup"><span data-stu-id="66ba3-253">You want the `F1Score` to be as close to one as possible.</span></span>

### <a name="predict-the-test-data-outcome"></a><span data-ttu-id="66ba3-254">テスト データの結果を予測する</span><span class="sxs-lookup"><span data-stu-id="66ba3-254">Predict the test data outcome</span></span>

1. <span data-ttu-id="66ba3-255">`Evaluate()` メソッドの直後に、次のコードを使用して `UseModelWithSingleItem()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-255">Create the `UseModelWithSingleItem()` method, just after the `Evaluate()` method, using the following code:</span></span>

    ```csharp
    private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="66ba3-256">`UseModelWithSingleItem()` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-256">The `UseModelWithSingleItem()` method executes the following tasks:</span></span>

    * <span data-ttu-id="66ba3-257">テスト データの 1 つのコメントを作成する。</span><span class="sxs-lookup"><span data-stu-id="66ba3-257">Creates a single comment of test data.</span></span>
    * <span data-ttu-id="66ba3-258">テスト データに基づいてセンチメントを予測する。</span><span class="sxs-lookup"><span data-stu-id="66ba3-258">Predicts sentiment based on test data.</span></span>
    * <span data-ttu-id="66ba3-259">テスト データと予測をレポート用に結合する。</span><span class="sxs-lookup"><span data-stu-id="66ba3-259">Combines test data and predictions for reporting.</span></span>
    * <span data-ttu-id="66ba3-260">予測された結果を表示する。</span><span class="sxs-lookup"><span data-stu-id="66ba3-260">Displays the predicted results.</span></span>

2. <span data-ttu-id="66ba3-261">`Evaluate()` メソッドの呼び出しのすぐ下に、次のコードを使用して、`Main()` メソッドからの新しいメソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-261">Add a call to the new method from the `Main()` method, right under the `Evaluate()` method call, using the following code:</span></span>

    [!code-csharp[CallUseModelWithSingleItem](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

3. <span data-ttu-id="66ba3-262">次のコードを追加して、`UseModelWithSingleItem()` メソッドの 1 行目として作成します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-262">Add the following code to create as the first line in the `UseModelWithSingleItem()` Method:</span></span>

    [!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]

    <span data-ttu-id="66ba3-263">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) は、データの 1 つのインスタンスを渡してから、その予測を実行できる便利な API です。</span><span class="sxs-lookup"><span data-stu-id="66ba3-263">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to pass in and then perform a prediction on a single instance of data.</span></span>

4. <span data-ttu-id="66ba3-264">コメントを追加して、`UseModelWithSingleItem()` メソッドでトレーニングされたモデルの予測をテストします。これには `SentimentData` のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-264">Add a comment to test the trained model's prediction in the `UseModelWithSingleItem()` method by creating an instance of `SentimentData`:</span></span>

    [!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

5. <span data-ttu-id="66ba3-265">`UseModelWithSingleItem()` メソッドの次のコード行として以下を追加して、テスト コメント データを `Prediction Engine` に渡します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-265">Pass the test comment data to the `Prediction Engine` by adding the following as the next lines of code in the `UseModelWithSingleItem()` method:</span></span>

    [!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Predict "Create a prediction of sentiment")]

    <span data-ttu-id="66ba3-266">[Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) 関数では、データの 1 つの行に対して予測を行います。</span><span class="sxs-lookup"><span data-stu-id="66ba3-266">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data.</span></span>

6. <span data-ttu-id="66ba3-267">次のコードを使用して、`SentimentText` とそれに対応するセンチメント予測を表示します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-267">Display `SentimentText` and corresponding sentiment prediction using the following code:</span></span>

    [!code-csharp[OutputPrediction](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#OutputPrediction "Display prediction output")]

## <a name="use-the-model-for-prediction"></a><span data-ttu-id="66ba3-268">予測にモデルを使用する</span><span class="sxs-lookup"><span data-stu-id="66ba3-268">Use the model for prediction</span></span>

### <a name="deploy-and-predict-batch-items"></a><span data-ttu-id="66ba3-269">バッチ項目の展開と予測</span><span class="sxs-lookup"><span data-stu-id="66ba3-269">Deploy and predict batch items</span></span>

1. <span data-ttu-id="66ba3-270">`UseModelWithSingleItem()` メソッドの直後に、次のコードを使用して `UseModelWithBatchItems()` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-270">Create the `UseModelWithBatchItems()` method, just after the `UseModelWithSingleItem()` method, using the following code:</span></span>

    ```csharp
    public static void UseModelWithBatchItems(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="66ba3-271">`UseModelWithBatchItems()` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-271">The `UseModelWithBatchItems()` method executes the following tasks:</span></span>

    * <span data-ttu-id="66ba3-272">バッチ テスト データを作成します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-272">Creates batch test data.</span></span>
    * <span data-ttu-id="66ba3-273">テスト データに基づいてセンチメントを予測する。</span><span class="sxs-lookup"><span data-stu-id="66ba3-273">Predicts sentiment based on test data.</span></span>
    * <span data-ttu-id="66ba3-274">テスト データと予測をレポート用に結合する。</span><span class="sxs-lookup"><span data-stu-id="66ba3-274">Combines test data and predictions for reporting.</span></span>
    * <span data-ttu-id="66ba3-275">予測された結果を表示する。</span><span class="sxs-lookup"><span data-stu-id="66ba3-275">Displays the predicted results.</span></span>

2. <span data-ttu-id="66ba3-276">`UseModelWithSingleItem()` メソッドの呼び出しのすぐ下に、次のコードを使用して、`Main` メソッドからの新しいメソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-276">Add a call to the new method from the `Main` method, right under the `UseModelWithSingleItem()` method call, using the following code:</span></span>

    [!code-csharp[CallPredictModelBatchItems](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithBatchItems "Call the CallUseModelWithBatchItems method")]

3. <span data-ttu-id="66ba3-277">`UseModelWithBatchItems()` メソッドでトレーニングされるモデルの予測をテストするために、いくつかのコメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-277">Add some comments to test the trained model's predictions in the `UseModelWithBatchItems()` method:</span></span>

    [!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssues "Create test data for predictions")]

### <a name="predict-comment-sentiment"></a><span data-ttu-id="66ba3-278">コメントのセンチメントを予測する</span><span class="sxs-lookup"><span data-stu-id="66ba3-278">Predict comment sentiment</span></span>

<span data-ttu-id="66ba3-279">モデルを使用し、[Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) メソッドを使用してコメント データのセンチメントを予測します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-279">Use the model to predict the comment data sentiment using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method:</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="combine-and-display-the-predictions"></a><span data-ttu-id="66ba3-280">予測を組み合わせて表示する</span><span class="sxs-lookup"><span data-stu-id="66ba3-280">Combine and display the predictions</span></span>

<span data-ttu-id="66ba3-281">次のコードを使用して、予測のヘッダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="66ba3-281">Create a header for the predictions using the following code:</span></span>

[!code-csharp[OutputHeaders](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddInfoMessage "Display prediction outputs")]

<span data-ttu-id="66ba3-282">`SentimentPrediction` は `SentimentData` から継承されているため、`Transform()` メソッドによって `SentimentText` に予測されたフィールドが設定されました。</span><span class="sxs-lookup"><span data-stu-id="66ba3-282">Because `SentimentPrediction` is inherited from `SentimentData`, the `Transform()` method populated `SentimentText` with the predicted fields.</span></span> <span data-ttu-id="66ba3-283">ML.NET プロセスが進むにつれて、各コンポーネントに列が追加されます。これで、結果が簡単に表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="66ba3-283">As the ML.NET process processes, each component adds columns, and this makes it easy to display the results:</span></span>

[!code-csharp[DisplayPredictions](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayResults "Display the predictions")]

## <a name="results"></a><span data-ttu-id="66ba3-284">結果</span><span class="sxs-lookup"><span data-stu-id="66ba3-284">Results</span></span>

<span data-ttu-id="66ba3-285">結果は以下のようになるはずです。</span><span class="sxs-lookup"><span data-stu-id="66ba3-285">Your results should be similar to the following.</span></span> <span data-ttu-id="66ba3-286">処理中にメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="66ba3-286">During processing, messages are displayed.</span></span> <span data-ttu-id="66ba3-287">警告または処理メッセージが表示されることがありますが、</span><span class="sxs-lookup"><span data-stu-id="66ba3-287">You may see warnings, or processing messages.</span></span> <span data-ttu-id="66ba3-288">わかりやすくするために、それらは次の結果から削除してあります。</span><span class="sxs-lookup"><span data-stu-id="66ba3-288">These have been removed from the following results for clarity.</span></span>

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

<span data-ttu-id="66ba3-289">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="66ba3-289">Congratulations!</span></span> <span data-ttu-id="66ba3-290">これで、メッセージのセンチメントを分類および予測するための機械学習モデルをビルドできました。</span><span class="sxs-lookup"><span data-stu-id="66ba3-290">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span>

<span data-ttu-id="66ba3-291">優れたモデルの構築は、反復的なプロセスです。</span><span class="sxs-lookup"><span data-stu-id="66ba3-291">Building successful models is an iterative process.</span></span> <span data-ttu-id="66ba3-292">このチュートリアルでは、モデルのトレーニングを短時間で実行するために小さなデータセットを使用しているため、このモデルの品質は最初は低くなっています。</span><span class="sxs-lookup"><span data-stu-id="66ba3-292">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="66ba3-293">このモデルの品質に満足できなければ、大規模なトレーニング データセットを使用するか、別のトレーニング アルゴリズムとアルゴリズムごとに異なる[ハイパーパラメーター](../resources/glossary.md##hyperparameter)を選択してモデルの改良を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="66ba3-293">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different [hyper-parameters](../resources/glossary.md##hyperparameter) for each algorithm.</span></span>

<span data-ttu-id="66ba3-294">このチュートリアルのソース コードは [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) リポジトリで確認できます。</span><span class="sxs-lookup"><span data-stu-id="66ba3-294">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="66ba3-295">次の手順</span><span class="sxs-lookup"><span data-stu-id="66ba3-295">Next steps</span></span>

<span data-ttu-id="66ba3-296">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="66ba3-296">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="66ba3-297">コンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="66ba3-297">Create a console application</span></span>
> * <span data-ttu-id="66ba3-298">データの準備</span><span class="sxs-lookup"><span data-stu-id="66ba3-298">Prepare data</span></span>
> * <span data-ttu-id="66ba3-299">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="66ba3-299">Load the data</span></span>
> * <span data-ttu-id="66ba3-300">モデルを構築してトレーニングする</span><span class="sxs-lookup"><span data-stu-id="66ba3-300">Build and train the model</span></span>
> * <span data-ttu-id="66ba3-301">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="66ba3-301">Evaluate the model</span></span>
> * <span data-ttu-id="66ba3-302">モデルを使用して予測する</span><span class="sxs-lookup"><span data-stu-id="66ba3-302">Use the model to make a prediction</span></span>
> * <span data-ttu-id="66ba3-303">結果を見る</span><span class="sxs-lookup"><span data-stu-id="66ba3-303">See the results</span></span>

<span data-ttu-id="66ba3-304">さらに詳しく学習するには、次のチュートリアルに進んでください。</span><span class="sxs-lookup"><span data-stu-id="66ba3-304">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="66ba3-305">問題の分類</span><span class="sxs-lookup"><span data-stu-id="66ba3-305">Issue Classification</span></span>](github-issue-classification.md)
