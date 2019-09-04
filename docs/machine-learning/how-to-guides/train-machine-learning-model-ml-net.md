---
title: モデルのトレーニングと評価
description: ML.NET を使用して、機械学習モデルの構築、メトリックの収集、およびパフォーマンスの測定を行う方法について説明します。 機械学習モデルによって、トレーニング データ内のパターンが識別され、新しいデータを使って予測が実行されます。
ms.date: 08/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: 3fb586b218f1769949efc362cacc3957623dd43b
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2019
ms.locfileid: "70169046"
---
# <a name="train-and-evaluate-a-model"></a><span data-ttu-id="7fddc-104">モデルのトレーニングと評価</span><span class="sxs-lookup"><span data-stu-id="7fddc-104">Train and evaluate a model</span></span>

<span data-ttu-id="7fddc-105">ML.NET を使用して、機械学習モデルの構築、メトリックの収集、およびパフォーマンスの測定を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7fddc-105">Learn how to build machine learning models, collect metrics, and measure performance with ML.NET.</span></span> <span data-ttu-id="7fddc-106">このサンプルでは回帰モデルがトレーニングされますが、この概念は他の主なアルゴリズムに適用できます。</span><span class="sxs-lookup"><span data-stu-id="7fddc-106">Although this sample trains a regression model, the concepts are applicable throughout a majority of the other algorithms.</span></span>

## <a name="split-data-for-training-and-testing"></a><span data-ttu-id="7fddc-107">トレーニングとテストのためにデータを分割する</span><span class="sxs-lookup"><span data-stu-id="7fddc-107">Split data for training and testing</span></span>

<span data-ttu-id="7fddc-108">機械学習モデルの目的は、トレーニング データ内のパターンを識別することです。</span><span class="sxs-lookup"><span data-stu-id="7fddc-108">The goal of a machine learning model is to identify patterns within training data.</span></span> <span data-ttu-id="7fddc-109">これらのパターンは、新しいデータを使用して予測を行うために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7fddc-109">These patterns are used to make predictions using new data.</span></span>

<span data-ttu-id="7fddc-110">データは `HousingData` などのクラスでモデル化できます。</span><span class="sxs-lookup"><span data-stu-id="7fddc-110">The data can be modeled by a class like `HousingData`.</span></span>

```csharp
public class HousingData
{
    [LoadColumn(0)]
    public float Size { get; set; }

    [LoadColumn(1, 3)]
    [VectorType(3)]
    public float[] HistoricalPrices { get; set; }

    [LoadColumn(4)]
    [ColumnName("Label")]
    public float CurrentPrice { get; set; }
}
```

<span data-ttu-id="7fddc-111">[`IDataView`](xref:Microsoft.ML.IDataView) にロードされた、次のデータがあるとします。</span><span class="sxs-lookup"><span data-stu-id="7fddc-111">Given the following data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

```csharp
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 600f,
        HistoricalPrices = new float[] { 100000f ,125000f ,122000f },
        CurrentPrice = 170000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 200000f, 250000f, 230000f },
        CurrentPrice = 225000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 126000f, 130000f, 200000f },
        CurrentPrice = 195000f
    },
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f,175000f,210000f },
        CurrentPrice = 205000f
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f },
        CurrentPrice = 210000f
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f },
        CurrentPrice = 180000f
    }
};
```

<span data-ttu-id="7fddc-112">[`TrainTestSplit`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit*) メソッドを使用して、データをトレーニング セットとテスト セットに分割します。</span><span class="sxs-lookup"><span data-stu-id="7fddc-112">Use the [`TrainTestSplit`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit*) method to split the data into train and test sets.</span></span> <span data-ttu-id="7fddc-113">結果は、2 つの [`IDataView`](xref:Microsoft.ML.IDataView) メンバー (トレーニング セット用とテスト セット用) が含まれる [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) オブジェクトになります。</span><span class="sxs-lookup"><span data-stu-id="7fddc-113">The result will be a [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) object which contains two [`IDataView`](xref:Microsoft.ML.IDataView) members, one for the train set and the other for the test set.</span></span> <span data-ttu-id="7fddc-114">データ分割の割合は、`testFraction` パラメーターによって決まります。</span><span class="sxs-lookup"><span data-stu-id="7fddc-114">The data split percentage is determined by the `testFraction` parameter.</span></span> <span data-ttu-id="7fddc-115">以下のスニペットは、テスト セットの元のデータの 20% を保持しています。</span><span class="sxs-lookup"><span data-stu-id="7fddc-115">The snippet below is holding out 20 percent of the original data for the test set.</span></span>

```csharp
DataOperationsCatalog.TrainTestData dataSplit = mlContext.Data.TrainTestSplit(data, testFraction: 0.2);
IDataView trainData = dataSplit.TrainSet;
IDataView testData = dataSplit.TestSet;
```

## <a name="prepare-the-data"></a><span data-ttu-id="7fddc-116">データを準備する</span><span class="sxs-lookup"><span data-stu-id="7fddc-116">Prepare the data</span></span>

<span data-ttu-id="7fddc-117">機械学習モデルをトレーニングする前に、データを前処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fddc-117">The data needs to be pre-processed before training a machine learning model.</span></span> <span data-ttu-id="7fddc-118">データ準備の詳細については、[データ準備のハウツー記事](prepare-data-ml-net.md)と [`transforms page`](../resources/transforms.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fddc-118">More information on data preparation can be found on the [data prep how-to article](prepare-data-ml-net.md) as well as the [`transforms page`](../resources/transforms.md).</span></span>

<span data-ttu-id="7fddc-119">ML.NET のアルゴリズムには、入力列の型に制約があります。</span><span class="sxs-lookup"><span data-stu-id="7fddc-119">ML.NET algorithms have constraints on input column types.</span></span> <span data-ttu-id="7fddc-120">さらに、値が指定されていない場合は、入力列名と出力列名に既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7fddc-120">Additionally, default values are used for input and output column names when no values are specified.</span></span>

### <a name="working-with-expected-column-types"></a><span data-ttu-id="7fddc-121">予想される列の型を使用する</span><span class="sxs-lookup"><span data-stu-id="7fddc-121">Working with expected column types</span></span>

<span data-ttu-id="7fddc-122">ML.NET の機械学習アルゴリズムは、入力として既知のサイズの float 型のベクターを想定しています。</span><span class="sxs-lookup"><span data-stu-id="7fddc-122">The machine learning algorithms in ML.NET expect a float vector of known size as input.</span></span> <span data-ttu-id="7fddc-123">すべてのデータが既に数値形式であり、一緒に処理されることが意図されている場合 (つまり、画像のピクセル)、データ モデルに [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) 属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="7fddc-123">Apply the [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) attribute to your data model when all of the data is already in numerical format and is intended to be processed together (i.e. image pixels).</span></span> 

<span data-ttu-id="7fddc-124">データがすべて数値ではなく、各列に異なるデータ変換が個別に適用される場合は、すべての列が処理された後に [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) メソッドを使用して、個々の列すべてを、新しい列に出力される 1 つの特徴ベクターに結合します。</span><span class="sxs-lookup"><span data-stu-id="7fddc-124">If data is not all numerical and you want to apply different data transformations on each of the columns individually, use the [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) method after all of the columns have been processed to combine all of the individual columns into a single feature vector that is output to a new column.</span></span> 

<span data-ttu-id="7fddc-125">次のスニペットは、`Size` 列と `HistoricalPrices` 列を 1 つの特徴ベクターにまとめ、それを `Features` という名前の新しい列に出力します。</span><span class="sxs-lookup"><span data-stu-id="7fddc-125">The following snippet combines the `Size` and `HistoricalPrices` columns into a single feature vector that is output to a new column called `Features`.</span></span> <span data-ttu-id="7fddc-126">スケールに違いがあるため、データを正規化するように [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) が `Features` 列に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7fddc-126">Because there is a difference in scales, [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) is applied to the `Features` column to normalize the data.</span></span>

```csharp
// Define Data Prep Estimator
// 1. Concatenate Size and Historical into a single feature vector output to a new column called Features
// 2. Normalize Features vector
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", "Size", "HistoricalPrices")
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// Create data prep transformer
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(trainData);

// Apply transforms to training data
IDataView transformedTrainingData = dataPrepTransformer.Transform(trainData);
```

### <a name="working-with-default-column-names"></a><span data-ttu-id="7fddc-127">既定の列名を使用する</span><span class="sxs-lookup"><span data-stu-id="7fddc-127">Working with default column names</span></span>

<span data-ttu-id="7fddc-128">何も指定されていない場合、ML.NET アルゴリズムでは既定の列名が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7fddc-128">ML.NET algorithms use default column names when none are specified.</span></span> <span data-ttu-id="7fddc-129">すべてのトレーナーには、アルゴリズムの入力用に `featureColumnName` というパラメーターがあり、適用可能な場合は `labelColumnName` という予期される値のパラメーターもあります。</span><span class="sxs-lookup"><span data-stu-id="7fddc-129">All trainers have a parameter called `featureColumnName` for the inputs of the algorithm and when applicable they also have a parameter for the expected value called `labelColumnName`.</span></span> <span data-ttu-id="7fddc-130">既定では、これらの値はそれぞれ `Features` と `Label` です。</span><span class="sxs-lookup"><span data-stu-id="7fddc-130">By default those values are `Features` and `Label` respectively.</span></span> 

<span data-ttu-id="7fddc-131">前処理中に [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) メソッドを使用して `Features` という名前の新しい列を作成すると、前処理済みの `IDataView` に既に存在するため、アルゴリズムのパラメーターで特徴列の名前を指定する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="7fddc-131">By using the [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) method during pre-processing to create a new column called `Features`, there is no need to specify the feature column name in the parameters of the algorithm since it already exists in the pre-processed `IDataView`.</span></span> <span data-ttu-id="7fddc-132">このラベル列は `CurrentPrice` ですが、データ モデルでは [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 属性が使用されているため、ML.NET によって `CurrentPrice` 列の名前が `Label` に変更され、機械学習アルゴリズム エスティメーターに `labelColumnName` パラメーターを指定する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="7fddc-132">The label column is `CurrentPrice`, but since the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute is used in the data model, ML.NET renames the `CurrentPrice` column to `Label` which removes the need to provide the `labelColumnName` parameter to the machine learning algorithm estimator.</span></span> 

<span data-ttu-id="7fddc-133">既定の列名を使用しない場合は、後続のスニペットで示すように、機械学習アルゴリズム エスティメーターを定義するときに、特徴列とラベル列の名前をパラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="7fddc-133">If you don't want to use the default column names, pass in the names of the feature and label columns as parameters when defining the machine learning algorithm estimator as demonstrated by the subsequent snippet:</span></span>

```csharp
var UserDefinedColumnSdcaEstimator = mlContext.Regression.Trainers.Sdca(labelColumnName: "MyLabelColumnName", featureColumnName: "MyFeatureColumnName");
```

## <a name="train-the-machine-learning-model"></a><span data-ttu-id="7fddc-134">機械学習モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="7fddc-134">Train the machine learning model</span></span>

<span data-ttu-id="7fddc-135">データの前処理を完了したら、[`Fit`](xref:Microsoft.ML.Trainers.TrainerEstimatorBase`2.Fit*) メソッドを使用して、[`StochasticDualCoordinateAscent`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer) 回帰アルゴリズムで機械学習モデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="7fddc-135">Once the data is pre-processed, use the [`Fit`](xref:Microsoft.ML.Trainers.TrainerEstimatorBase`2.Fit*) method to train the machine learning model with the [`StochasticDualCoordinateAscent`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer) regression algorithm.</span></span>

```csharp
// Define StochasticDualCoordinateAscent regression algorithm estimator
var sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Build machine learning model
var trainedModel = sdcaEstimator.Fit(transformedTrainingData);
```

## <a name="extract-model-parameters"></a><span data-ttu-id="7fddc-136">モデル パラメーターを抽出する</span><span class="sxs-lookup"><span data-stu-id="7fddc-136">Extract model parameters</span></span>

<span data-ttu-id="7fddc-137">モデルがトレーニングされた後、検査または再トレーニングのために学習済みの [`ModelParameters`](xref:Microsoft.ML.Trainers.ModelParametersBase%601) を抽出します。</span><span class="sxs-lookup"><span data-stu-id="7fddc-137">After the model has been trained, extract the learned [`ModelParameters`](xref:Microsoft.ML.Trainers.ModelParametersBase%601) for inspection or re-training.</span></span> <span data-ttu-id="7fddc-138">[`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters) には、トレーニング済みモデルの偏り係数、学習済み係数、または重みが用意されています。</span><span class="sxs-lookup"><span data-stu-id="7fddc-138">The [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters) provide the bias and learned coefficients or weights of the trained model.</span></span> 

```csharp
var trainedModelParameters = trainedModel.Model as LinearRegressionModelParameters;
```

> [!NOTE]
> <span data-ttu-id="7fddc-139">他のモデルには、それぞれのタスクに固有のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="7fddc-139">Other models have parameters that are specific to their tasks.</span></span> <span data-ttu-id="7fddc-140">たとえば、[K-Means アルゴリズム](xref:Microsoft.ML.Trainers.KMeansTrainer)では重心に基づいてデータがクラスターに配置され、[`KMeansModelParameters`](xref:Microsoft.ML.Trainers.KMeansModelParameters) にはその学習済みの重心を格納するプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7fddc-140">For example, the [K-Means algorithm](xref:Microsoft.ML.Trainers.KMeansTrainer) puts data into cluster based on centroids and the [`KMeansModelParameters`](xref:Microsoft.ML.Trainers.KMeansModelParameters) contains a property that stores these learned centroids.</span></span> <span data-ttu-id="7fddc-141">詳細については、[`Microsoft.ML.Trainers` API ドキュメント](xref:Microsoft.ML.Trainers)を参照し、名前に `ModelParameters` を含むクラスを探します。</span><span class="sxs-lookup"><span data-stu-id="7fddc-141">To learn more, visit the [`Microsoft.ML.Trainers` API Documentation](xref:Microsoft.ML.Trainers) and look for classes that contain `ModelParameters` in their name.</span></span> 

## <a name="evaluate-model-quality"></a><span data-ttu-id="7fddc-142">モデルの品質を評価する</span><span class="sxs-lookup"><span data-stu-id="7fddc-142">Evaluate model quality</span></span>

<span data-ttu-id="7fddc-143">最適なパフォーマンスを発揮するモデルを選択するには、テスト データでそのパフォーマンスを評価することが重要です。</span><span class="sxs-lookup"><span data-stu-id="7fddc-143">To help choose the best performing model, it is essential to evaluate its performance on test data.</span></span> <span data-ttu-id="7fddc-144">[`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate*) メソッドを使用して、トレーニング済みモデルのさまざまなメトリックを測定します。</span><span class="sxs-lookup"><span data-stu-id="7fddc-144">Use the [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate*) method, to measure various metrics for the trained model.</span></span>

> [!NOTE]
> <span data-ttu-id="7fddc-145">`Evaluate` メソッドによって生成されるメトリックは、実行された機械学習タスクによって異なります。</span><span class="sxs-lookup"><span data-stu-id="7fddc-145">The `Evaluate` method produces different metrics depending on which machine learning task was performed.</span></span> <span data-ttu-id="7fddc-146">詳細については、[`Microsoft.ML.Data` API ドキュメント](xref:Microsoft.ML.Data)を参照し、名前に `Metrics` を含むクラスを探します。</span><span class="sxs-lookup"><span data-stu-id="7fddc-146">For more details, visit the [`Microsoft.ML.Data` API Documentation](xref:Microsoft.ML.Data) and look for classes that contain `Metrics` in their name.</span></span> 

```csharp
// Measure trained model performance
// Apply data prep transformer to test data
IDataView transformedTestData = dataPrepTransformer.Transform(testData);

// Use trained model to make inferences on test data
IDataView testDataPredictions = trainedModel.Transform(transformedTestData);

// Extract model metrics and get RSquared
RegressionMetrics trainedModelMetrics = mlContext.Regression.Evaluate(testDataPredictions);
double rSquared = trainedModelMetrics.RSquared;
```

<span data-ttu-id="7fddc-147">前のコード サンプルの内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7fddc-147">In the previous code sample:</span></span>  
1. <span data-ttu-id="7fddc-148">テスト データ セットは、以前に定義されたデータ準備変換を使用して前処理されます。</span><span class="sxs-lookup"><span data-stu-id="7fddc-148">Test data set is pre-processed using the data preparation transforms previously defined.</span></span> 
2. <span data-ttu-id="7fddc-149">トレーニング済み機械学習モデルは、テスト データに基づいて予測するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7fddc-149">The trained machine learning model is used to make predictions on the test data.</span></span>
3. <span data-ttu-id="7fddc-150">`Evaluate` メソッドでは、テスト データ セットの `CurrentPrice` 列の値を新しく出力された予測の `Score` 列と比較して、回帰モデルのメトリックを計算します。そのうちの 1 つである R-2 乗値は `rSquared` 変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="7fddc-150">In the `Evaluate` method, the values in the `CurrentPrice` column of the test data set are compared against the `Score` column of the newly output predictions to calculate the metrics for the regression model, one of which, R-Squared is stored in the `rSquared` variable.</span></span>

> [!NOTE]
> <span data-ttu-id="7fddc-151">この小さな例では、データのサイズが限られているため、R-2 乗値は 0 から 1 の範囲に含まれない数値です。</span><span class="sxs-lookup"><span data-stu-id="7fddc-151">In this small example, the R-Squared is a number not in the range of 0-1 because of the limited size of the data.</span></span> <span data-ttu-id="7fddc-152">実際のシナリオでは、0 から 1 の間の値が示されると想定されます。</span><span class="sxs-lookup"><span data-stu-id="7fddc-152">In a real-world scenario, you should expect to see a value between 0 and 1.</span></span>
