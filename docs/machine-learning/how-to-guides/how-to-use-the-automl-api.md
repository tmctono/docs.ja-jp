---
title: ML.NET の自動 ML API を使用する方法
description: ML.NET の自動 ML API によって、モデル構築プロセスが自動化され、展開できる状態のモデルが生成されます。 自動機械学習タスクの構成に使用できるオプションについて説明します。
ms.date: 04/24/2019
ms.custom: mvc,how-to
ms.openlocfilehash: bb1cd66e7341f2ada57d533d8b2dcbb48f08f726
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774553"
---
# <a name="how-to-use-the-mlnet-automated-machine-learning-api"></a><span data-ttu-id="482c5-104">ML.NET の自動機械学習 API を使用する方法</span><span class="sxs-lookup"><span data-stu-id="482c5-104">How to use the ML.NET automated machine learning API</span></span>

<span data-ttu-id="482c5-105">自動機械学習 (AutoML) によって、機械学習をデータに適用するプロセスが自動化されます。</span><span class="sxs-lookup"><span data-stu-id="482c5-105">Automated machine learning (AutoML) automates the process of applying machine learning to data.</span></span> <span data-ttu-id="482c5-106">データセットがある場合、さまざまなデータの特徴付け、機械学習アルゴリズム、およびハイパーパラメーターを反復処理する AutoML の**実験**を実行することで、最適なモデルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="482c5-106">Given a dataset, you can run an AutoML **experiment** to iterate over different data featurizations, machine learning algorithms, and hyperparameters to select the best model.</span></span>

> [!NOTE]
> <span data-ttu-id="482c5-107">このトピックは、現在プレビュー段階の ML.NET 用の自動機械学習 API について述べています。</span><span class="sxs-lookup"><span data-stu-id="482c5-107">This topic refers to the automated machine learning API for ML.NET, which is currently in preview.</span></span> <span data-ttu-id="482c5-108">内容は変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="482c5-108">Material may be subject to change.</span></span>

## <a name="load-data"></a><span data-ttu-id="482c5-109">データの読み込み</span><span class="sxs-lookup"><span data-stu-id="482c5-109">Load data</span></span>

<span data-ttu-id="482c5-110">自動機械学習は、[IDataView](xref:Microsoft.ML.IDataView) へのデータ セットの読み込みをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="482c5-110">Automated machine learning supports loading a dataset into an [IDataView](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="482c5-111">タブ区切り値 (TSV) ファイルとコンマ区切り値 (CSV) ファイルの形式のデータを使用できます。</span><span class="sxs-lookup"><span data-stu-id="482c5-111">Data can be in the form of tab-separated value (TSV) files and comma separated value (CSV) files.</span></span>

<span data-ttu-id="482c5-112">例:</span><span class="sxs-lookup"><span data-stu-id="482c5-112">Example:</span></span>

```csharp
using Microsoft.ML;
using Microsoft.ML.AutoML;
    // ...
    MLContext mlContext = new MLContext();
    IDataView trainDataView = mlContext.Data.LoadFromTextFile<SentimentIssue>("my-data-file.csv", hasHeader: true);
```

## <a name="select-the-machine-learning-task-type"></a><span data-ttu-id="482c5-113">機械学習タスクの種類を選択する</span><span class="sxs-lookup"><span data-stu-id="482c5-113">Select the machine learning task type</span></span>
<span data-ttu-id="482c5-114">実験を作成する前に、解決する機械学習の問題の種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="482c5-114">Before creating an experiment, determine the kind of machine learning problem you want to solve.</span></span> <span data-ttu-id="482c5-115">自動機械学習は、以下の ML タスクをサポートします。</span><span class="sxs-lookup"><span data-stu-id="482c5-115">Automated machine learning supports the following ML tasks:</span></span>

* <span data-ttu-id="482c5-116">二項分類</span><span class="sxs-lookup"><span data-stu-id="482c5-116">Binary Classification</span></span>
* <span data-ttu-id="482c5-117">多クラス分類</span><span class="sxs-lookup"><span data-stu-id="482c5-117">Multiclass Classification</span></span>
* <span data-ttu-id="482c5-118">回帰</span><span class="sxs-lookup"><span data-stu-id="482c5-118">Regression</span></span>

## <a name="create-experiment-settings"></a><span data-ttu-id="482c5-119">実験設定を作成する</span><span class="sxs-lookup"><span data-stu-id="482c5-119">Create experiment settings</span></span>

<span data-ttu-id="482c5-120">決定した ML タスクの種類の実験設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="482c5-120">Create experiment settings for the determined ML task type:</span></span>

* <span data-ttu-id="482c5-121">二項分類</span><span class="sxs-lookup"><span data-stu-id="482c5-121">Binary Classification</span></span>

  ```csharp
  var experimentSettings = new BinaryExperimentSettings();
  ```

* <span data-ttu-id="482c5-122">多クラス分類</span><span class="sxs-lookup"><span data-stu-id="482c5-122">Multiclass Classification</span></span>

  ```csharp
  var experimentSettings = new MulticlassExperimentSettings();
  ```

* <span data-ttu-id="482c5-123">回帰</span><span class="sxs-lookup"><span data-stu-id="482c5-123">Regression</span></span>

  ```csharp
  var experimentSettings = new RegressionExperimentSettings();
  ```

## <a name="configure-experiment-settings"></a><span data-ttu-id="482c5-124">実験設定を構成する</span><span class="sxs-lookup"><span data-stu-id="482c5-124">Configure experiment settings</span></span>

<span data-ttu-id="482c5-125">実験は高度な構成が可能です。</span><span class="sxs-lookup"><span data-stu-id="482c5-125">Experiments are highly configurable.</span></span> <span data-ttu-id="482c5-126">構成設定の詳細な一覧については、[AutoML API ドキュメント](https://docs.microsoft.com/dotnet/api/?view=automl-dotnet)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="482c5-126">See the [AutoML API docs](https://docs.microsoft.com/dotnet/api/?view=automl-dotnet) for a full list of configuration settings.</span></span>

<span data-ttu-id="482c5-127">次に、それらの例の一部を示します。</span><span class="sxs-lookup"><span data-stu-id="482c5-127">Some examples include:</span></span>

1. <span data-ttu-id="482c5-128">実験を実行できる最長時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="482c5-128">Specify the maximum time that the experiment is allowed to run.</span></span>

    ```csharp
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    ```

1. <span data-ttu-id="482c5-129">実験が完了する前にキャンセル トークンを使用して実験を取り消します。</span><span class="sxs-lookup"><span data-stu-id="482c5-129">Use a cancellation token to cancel the experiment before it is scheduled to finish.</span></span>

    ```csharp
    experimentSettings.CancellationToken = cts.Token;

    // Cancel experiment after the user presses any key
    CancelExperimentAfterAnyKeyPress(cts);
    ```

1. <span data-ttu-id="482c5-130">別の最適化メトリックを指定します。</span><span class="sxs-lookup"><span data-stu-id="482c5-130">Specify a different optimizing metric.</span></span>

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.OptimizingMetric = RegressionMetric.MeanSquaredError;
    ```

1. <span data-ttu-id="482c5-131">`CacheDirectory` 設定は、AutoML タスク中にトレーニングされたすべてのモデルが保存されるディレクトリへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="482c5-131">The `CacheDirectory` setting is a pointer to a directory where all models trained during the AutoML task will be saved.</span></span> <span data-ttu-id="482c5-132">`CacheDirectory` が null に設定されている場合、モデルはディスクに書き込まれるのではなくメモリに保持されます。</span><span class="sxs-lookup"><span data-stu-id="482c5-132">If `CacheDirectory` is set to null, models will be kept in memory instead of written to disk.</span></span>

    ```csharp
    experimentSettings.CacheDirectory = null;
    ```

1. <span data-ttu-id="482c5-133">特定のトレーナーを使用しないように自動 ML に指示します。</span><span class="sxs-lookup"><span data-stu-id="482c5-133">Instruct automated ML not to use certain trainers.</span></span>

    <span data-ttu-id="482c5-134">最適化するトレーナーの既定の一覧がタスクごとに探索されます。</span><span class="sxs-lookup"><span data-stu-id="482c5-134">A default list of trainers to optimize are explored per task.</span></span> <span data-ttu-id="482c5-135">この一覧は実験ごとに変更できます。</span><span class="sxs-lookup"><span data-stu-id="482c5-135">This list can be modified for each experiment.</span></span> <span data-ttu-id="482c5-136">たとえば、データセットの実行速度が遅いトレーナーは一覧から削除できます。</span><span class="sxs-lookup"><span data-stu-id="482c5-136">For instance, trainers that run slowly on your dataset can be removed from the list.</span></span> <span data-ttu-id="482c5-137">特定のトレーナーを最適化するには、`experimentSettings.Trainers.Clear()` を呼び出してから、使用するトレーナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="482c5-137">To optimize on one specific trainer call `experimentSettings.Trainers.Clear()`, then add the trainer that you want to use.</span></span>

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.Trainers.Remove(RegressionTrainer.LbfgsPoissonRegression);
    experimentSettings.Trainers.Remove(RegressionTrainer.OnlineGradientDescent);
    ```

<span data-ttu-id="482c5-138">ML タスクごとにサポートされるトレーナーの一覧は、以下の対応するリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="482c5-138">The list of supported trainers per ML task can be found at the corresponding link below:</span></span>

* [<span data-ttu-id="482c5-139">サポートされる二項分類アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="482c5-139">Supported Binary Classification Algorithms</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationTrainer)
* [<span data-ttu-id="482c5-140">サポートされる多クラス分類アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="482c5-140">Supported Multiclass Classification Algorithms</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationTrainer)
* [<span data-ttu-id="482c5-141">サポートされる回帰アルゴリズム</span><span class="sxs-lookup"><span data-stu-id="482c5-141">Supported Regression Algorithms</span></span>](xref:Microsoft.ML.AutoML.RegressionTrainer)

## <a name="optimizing-metric"></a><span data-ttu-id="482c5-142">最適化メトリック</span><span class="sxs-lookup"><span data-stu-id="482c5-142">Optimizing metric</span></span>

<span data-ttu-id="482c5-143">上の例に示すように、最適化メトリックによって、モデルのトレーニング中に最適化されるメトリックが決まります。</span><span class="sxs-lookup"><span data-stu-id="482c5-143">The optimizing metric, as shown in the example above, determines the metric to be optimized during model training.</span></span> <span data-ttu-id="482c5-144">選択できる最適化メトリックは、選択したタスクの種類によって決まります。</span><span class="sxs-lookup"><span data-stu-id="482c5-144">The optimizing metric you can select is determined by the task type you choose.</span></span> <span data-ttu-id="482c5-145">利用できるメトリックの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="482c5-145">Below is a list of available metrics.</span></span>

|[<span data-ttu-id="482c5-146">二項分類</span><span class="sxs-lookup"><span data-stu-id="482c5-146">Binary Classification</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationMetric) | [<span data-ttu-id="482c5-147">多クラス分類</span><span class="sxs-lookup"><span data-stu-id="482c5-147">Multiclass Classification</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric) |[<span data-ttu-id="482c5-148">回帰</span><span class="sxs-lookup"><span data-stu-id="482c5-148">Regression</span></span>](xref:Microsoft.ML.AutoML.RegressionMetric)
|-- |-- |--
|<span data-ttu-id="482c5-149">正確度</span><span class="sxs-lookup"><span data-stu-id="482c5-149">Accuracy</span></span>| <span data-ttu-id="482c5-150">LogLoss</span><span class="sxs-lookup"><span data-stu-id="482c5-150">LogLoss</span></span> | <span data-ttu-id="482c5-151">RSquared</span><span class="sxs-lookup"><span data-stu-id="482c5-151">RSquared</span></span>
|<span data-ttu-id="482c5-152">AreaUnderPrecisionRecallCurve</span><span class="sxs-lookup"><span data-stu-id="482c5-152">AreaUnderPrecisionRecallCurve</span></span> | <span data-ttu-id="482c5-153">LogLossReduction</span><span class="sxs-lookup"><span data-stu-id="482c5-153">LogLossReduction</span></span> | <span data-ttu-id="482c5-154">MeanAbsoluteError</span><span class="sxs-lookup"><span data-stu-id="482c5-154">MeanAbsoluteError</span></span>
|<span data-ttu-id="482c5-155">AreaUnderRocCurve</span><span class="sxs-lookup"><span data-stu-id="482c5-155">AreaUnderRocCurve</span></span> | <span data-ttu-id="482c5-156">MacroAccuracy</span><span class="sxs-lookup"><span data-stu-id="482c5-156">MacroAccuracy</span></span> | <span data-ttu-id="482c5-157">MeanSquaredError</span><span class="sxs-lookup"><span data-stu-id="482c5-157">MeanSquaredError</span></span>
|<span data-ttu-id="482c5-158">F1Score</span><span class="sxs-lookup"><span data-stu-id="482c5-158">F1Score</span></span> | <span data-ttu-id="482c5-159">MicroAccuracy</span><span class="sxs-lookup"><span data-stu-id="482c5-159">MicroAccuracy</span></span> | <span data-ttu-id="482c5-160">RootMeanSquaredError</span><span class="sxs-lookup"><span data-stu-id="482c5-160">RootMeanSquaredError</span></span>
|<span data-ttu-id="482c5-161">NegativePrecision</span><span class="sxs-lookup"><span data-stu-id="482c5-161">NegativePrecision</span></span> | <span data-ttu-id="482c5-162">TopKAccuracy</span><span class="sxs-lookup"><span data-stu-id="482c5-162">TopKAccuracy</span></span>
|<span data-ttu-id="482c5-163">NegativeRecall</span><span class="sxs-lookup"><span data-stu-id="482c5-163">NegativeRecall</span></span> |
|<span data-ttu-id="482c5-164">PositivePrecision</span><span class="sxs-lookup"><span data-stu-id="482c5-164">PositivePrecision</span></span>
|<span data-ttu-id="482c5-165">PositiveRecall</span><span class="sxs-lookup"><span data-stu-id="482c5-165">PositiveRecall</span></span>

## <a name="data-pre-processing-and-featurization"></a><span data-ttu-id="482c5-166">データの前処理と特徴付け</span><span class="sxs-lookup"><span data-stu-id="482c5-166">Data pre-processing and featurization</span></span>

> [!NOTE]
> <span data-ttu-id="482c5-167">特徴列では、<xref:System.Boolean>、<xref:System.Single>、<xref:System.String> の種類のみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="482c5-167">The feature column only supported types of <xref:System.Boolean>, <xref:System.Single>, and <xref:System.String>.</span></span>

<span data-ttu-id="482c5-168">データの前処理は既定で行われ、次の手順が自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="482c5-168">Data pre-processing happens by default and the following steps are performed automatically for you:</span></span>

1. <span data-ttu-id="482c5-169">有用な情報がない特徴を削除する</span><span class="sxs-lookup"><span data-stu-id="482c5-169">Drop features with no useful information</span></span>

    <span data-ttu-id="482c5-170">トレーニングおよび検証セットから有用な情報がない特徴を削除します。</span><span class="sxs-lookup"><span data-stu-id="482c5-170">Drop features with no useful information from training and validation sets.</span></span> <span data-ttu-id="482c5-171">これには、すべての値が欠落している、すべての行の値が同じである、またはカーディナリティが非常に高い (ハッシュ、ID、GUID など) 特徴が含まれます。</span><span class="sxs-lookup"><span data-stu-id="482c5-171">These include features with all values missing, same value across all rows or with extremely high cardinality (e.g., hashes, IDs or GUIDs).</span></span>

1. <span data-ttu-id="482c5-172">欠落値の表示と補完</span><span class="sxs-lookup"><span data-stu-id="482c5-172">Missing value indication and imputation</span></span>

    <span data-ttu-id="482c5-173">欠落値のセルにそのデータ型の既定値を入力します。</span><span class="sxs-lookup"><span data-stu-id="482c5-173">Fill missing value cells with the default value for the datatype.</span></span> <span data-ttu-id="482c5-174">入力列と同じ数のスロットを持つインジケーター特徴を追加します。</span><span class="sxs-lookup"><span data-stu-id="482c5-174">Append indicator features with the same number of slots as the input column.</span></span> <span data-ttu-id="482c5-175">追加されるインジケーター特徴の値は、入力列の値が欠落している場合は `1`、それ以外の場合は `0` です。</span><span class="sxs-lookup"><span data-stu-id="482c5-175">The value in the appended indicator features is `1` if the value in the input column is missing and `0` otherwise.</span></span>

1. <span data-ttu-id="482c5-176">追加の特徴を生成する</span><span class="sxs-lookup"><span data-stu-id="482c5-176">Generate additional features</span></span>

    <span data-ttu-id="482c5-177">テキスト特徴の場合:ユニグラムとトライキャラクターグラムを使用する bag-of-word 特徴。</span><span class="sxs-lookup"><span data-stu-id="482c5-177">For text features: Bag-of-word features using unigrams and tri-character-grams.</span></span>

    <span data-ttu-id="482c5-178">カテゴリ別特徴の場合:カーディナリティの低い特徴向きのワンホット エンコードと、カーディナリティの高いカテゴリ別特徴向きのワンホットハッシュ エンコード。</span><span class="sxs-lookup"><span data-stu-id="482c5-178">For categorical features: One-hot encoding for low cardinality features, and one-hot-hash encoding for high cardinality categorical features.</span></span>

1. <span data-ttu-id="482c5-179">変換とエンコード</span><span class="sxs-lookup"><span data-stu-id="482c5-179">Transformations and encodings</span></span>

    <span data-ttu-id="482c5-180">一意の値がほとんどなく、カテゴリ別特徴に変換されるテキスト特徴。</span><span class="sxs-lookup"><span data-stu-id="482c5-180">Text features with very few unique values transformed into categorical features.</span></span> <span data-ttu-id="482c5-181">カテゴリ別特徴のカーディナリティに応じて、ワンホット エンコードまたはワンホットハッシュ エンコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="482c5-181">Depending on cardinality of categorical features, perform one-hot encoding or one-hot hash encoding.</span></span>

## <a name="exit-criteria"></a><span data-ttu-id="482c5-182">終了基準</span><span class="sxs-lookup"><span data-stu-id="482c5-182">Exit criteria</span></span>

<span data-ttu-id="482c5-183">タスクを完了する基準を定義します。</span><span class="sxs-lookup"><span data-stu-id="482c5-183">Define the criteria to complete your task:</span></span>

1. <span data-ttu-id="482c5-184">一定の時間で終了する - 実験設定に `MaxExperimentTimeInSeconds` を使用して、タスクを継続して実行する時間を秒単位で定義することができます。</span><span class="sxs-lookup"><span data-stu-id="482c5-184">Exit after a length of time - Using `MaxExperimentTimeInSeconds` in your experiment settings you can define how long in seconds that an task should continue to run.</span></span>

1. <span data-ttu-id="482c5-185">キャンセル トークンで終了する - キャンセル トークンを使用して、タスクが完了する予定の前に取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="482c5-185">Exit on a cancellation token -  You can use a cancellation token that lets you cancel the task before it is scheduled to finish.</span></span>

    ```csharp
    var cts = new CancellationTokenSource();
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    experimentSettings.CancellationToken = cts.Token;
    ```

## <a name="create-an-experiment"></a><span data-ttu-id="482c5-186">実験を作成する</span><span class="sxs-lookup"><span data-stu-id="482c5-186">Create an experiment</span></span>

<span data-ttu-id="482c5-187">実験設定を構成したら、実験を作成する準備は完了です。</span><span class="sxs-lookup"><span data-stu-id="482c5-187">Once you have configured the experiment settings, you are ready to create the experiment.</span></span>

```csharp
RegressionExperiment experiment = mlContext.Auto().CreateRegressionExperiment(experimentSettings);
```

## <a name="run-the-experiment"></a><span data-ttu-id="482c5-188">実験を実行する</span><span class="sxs-lookup"><span data-stu-id="482c5-188">Run the experiment</span></span>

<span data-ttu-id="482c5-189">実験を実行すると、データの前処理、学習アルゴリズムの選択、およびハイパーパラメーターの調整が開始されます。</span><span class="sxs-lookup"><span data-stu-id="482c5-189">Running the experiment triggers data pre-processing, learning algorithm selection, and hyperparameter tuning.</span></span> <span data-ttu-id="482c5-190">`MaxExperimentTimeInSeconds` に達するか実験が終了するまで、AutoML によって特徴付け、学習アルゴリズム、およびハイパーパラメーターの組み合わせが継続して生成されます。</span><span class="sxs-lookup"><span data-stu-id="482c5-190">AutoML will continue to generate combinations of featurization, learning algorithms, and hyperparameters until the `MaxExperimentTimeInSeconds` is reached or the experiment is terminated.</span></span>

```csharp
ExperimentResult<RegressionMetrics> experimentResult = experiment
    .Execute(trainingDataView, LabelColumnName, progressHandler: progressHandler);
```

<span data-ttu-id="482c5-191">検証データ、列の目的を示す列情報、または事前特徴付け器を渡す場合は、`Execute()` のその他のオーバーロードを調べてください。</span><span class="sxs-lookup"><span data-stu-id="482c5-191">Explore other overloads for `Execute()` if you want to pass in validation data, column information indicating the column purpose, or prefeaturizers.</span></span>

## <a name="training-modes"></a><span data-ttu-id="482c5-192">トレーニング モード</span><span class="sxs-lookup"><span data-stu-id="482c5-192">Training modes</span></span>

### <a name="training-dataset"></a><span data-ttu-id="482c5-193">トレーニング データセット</span><span class="sxs-lookup"><span data-stu-id="482c5-193">Training dataset</span></span>

<span data-ttu-id="482c5-194">AutoML には、オーバーロードされた実験の実行でトレーニング データを指定できる方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="482c5-194">AutoML provides an overloaded experiment execute method which allows you to provide training data.</span></span> <span data-ttu-id="482c5-195">内部的には、自動 ML によってトレーニング分割と検証分割にデータが分けられます。</span><span class="sxs-lookup"><span data-stu-id="482c5-195">Internally, automated ML divides the data into train-validate splits.</span></span>

```csharp
experiment.Execute(trainDataView);
```

### <a name="custom-validation-dataset"></a><span data-ttu-id="482c5-196">カスタム検証データセット</span><span class="sxs-lookup"><span data-stu-id="482c5-196">Custom validation dataset</span></span>

<span data-ttu-id="482c5-197">時系列データでは通常のことですが、ランダムな分割を許容できない場合は、カスタム検証データセットを使用します。</span><span class="sxs-lookup"><span data-stu-id="482c5-197">Use custom validation dataset if random split is not acceptable, as is usually the case with time series data.</span></span> <span data-ttu-id="482c5-198">独自の検証データセットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="482c5-198">You can specify your own validation dataset.</span></span> <span data-ttu-id="482c5-199">モデルは、1 つ以上のランダムなデータセットではなく、指定した検証データセットに対して評価されます。</span><span class="sxs-lookup"><span data-stu-id="482c5-199">The model will be evaluated against the validation dataset specified instead of one or more random datasets.</span></span>

```csharp
experiment.Execute(trainDataView, validationDataView);
```

## <a name="explore-model-metrics"></a><span data-ttu-id="482c5-200">モデルのメトリックを調べる</span><span class="sxs-lookup"><span data-stu-id="482c5-200">Explore model metrics</span></span>

<span data-ttu-id="482c5-201">ML 実験の各反復処理の後に、そのタスクに関するメトリックは保存されます。</span><span class="sxs-lookup"><span data-stu-id="482c5-201">After each iteration of an ML experiment, metrics relating to that task are stored.</span></span>

<span data-ttu-id="482c5-202">たとえば、最適な実行から検証メトリックにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="482c5-202">For example, we can access validation metrics from the best run:</span></span>

```csharp
RegressionMetrics metrics = experimentResult.BestRun.ValidationMetrics;
Console.WriteLine($"R-Squared: {metrics.RSquared:0.##}");
Console.WriteLine($"Root Mean Squared Error: {metrics.RootMeanSquaredError:0.##}");
```

<span data-ttu-id="482c5-203">ML タスクごとに利用できるすべてのメトリックを次に示します。</span><span class="sxs-lookup"><span data-stu-id="482c5-203">The following are all the available metrics per ML task:</span></span>

* [<span data-ttu-id="482c5-204">二項分類メトリック</span><span class="sxs-lookup"><span data-stu-id="482c5-204">Binary classification metrics</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationMetric)
* [<span data-ttu-id="482c5-205">多クラス分類メトリック</span><span class="sxs-lookup"><span data-stu-id="482c5-205">Multiclass classification metrics</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric)
* [<span data-ttu-id="482c5-206">回帰メトリック</span><span class="sxs-lookup"><span data-stu-id="482c5-206">Regression metrics</span></span>](xref:Microsoft.ML.AutoML.RegressionMetric)

## <a name="see-also"></a><span data-ttu-id="482c5-207">関連項目</span><span class="sxs-lookup"><span data-stu-id="482c5-207">See also</span></span>

<span data-ttu-id="482c5-208">すべてのコード サンプルについては、[dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state) GitHub リポジトリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="482c5-208">For full code samples and more visit the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state) GitHub repository.</span></span>
