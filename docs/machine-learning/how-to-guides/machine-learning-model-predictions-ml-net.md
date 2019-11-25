---
title: トレーニング済みモデルを使用して予測する
description: トレーニング済みモデルを使用して予測する方法について説明します
ms.date: 09/18/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 182350cc5143155133385c6fd77986b271f6db91
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977040"
---
# <a name="make-predictions-with-a-trained-model"></a><span data-ttu-id="b89ea-103">トレーニング済みモデルを使用して予測する</span><span class="sxs-lookup"><span data-stu-id="b89ea-103">Make predictions with a trained model</span></span>

<span data-ttu-id="b89ea-104">トレーニング済みモデルを使用して予測する方法について説明します</span><span class="sxs-lookup"><span data-stu-id="b89ea-104">Learn how to use a trained model to make predictions</span></span>

## <a name="create-data-models"></a><span data-ttu-id="b89ea-105">データ モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="b89ea-105">Create data models</span></span>

### <a name="input-data"></a><span data-ttu-id="b89ea-106">データを入力する</span><span class="sxs-lookup"><span data-stu-id="b89ea-106">Input data</span></span>

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

### <a name="output-data"></a><span data-ttu-id="b89ea-107">データを出力する</span><span class="sxs-lookup"><span data-stu-id="b89ea-107">Output data</span></span>

<span data-ttu-id="b89ea-108">`Features` と `Label` の入力列名と同様に、ML.NET にはモデルによって生成される予測値列の既定の名前があります。</span><span class="sxs-lookup"><span data-stu-id="b89ea-108">Like the `Features` and `Label` input column names, ML.NET has default names for the predicted value columns produced by a model.</span></span> <span data-ttu-id="b89ea-109">タスクによっては名前が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b89ea-109">Depending on the task the name may differ.</span></span>

<span data-ttu-id="b89ea-110">このサンプルで使用されているアルゴリズムは線形回帰アルゴリズムなので、出力列の既定の名前は `Score` です。これは `PredictedPrice` プロパティの [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 属性によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="b89ea-110">Because the algorithm used in this sample is a linear regression algorithm, the default name of the output column is `Score` which is defined by the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute on the `PredictedPrice` property.</span></span>

```csharp
class HousingPrediction
{
    [ColumnName("Score")]
    public float PredictedPrice { get; set; }
}
```

## <a name="set-up-a-prediction-pipeline"></a><span data-ttu-id="b89ea-111">予測パイプラインを設定する</span><span class="sxs-lookup"><span data-stu-id="b89ea-111">Set up a prediction pipeline</span></span>

<span data-ttu-id="b89ea-112">1 つの予測でもバッチ予測でも、予測パイプラインをアプリケーションに読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="b89ea-112">Whether making a single or batch prediction, the prediction pipeline needs to be loaded into the application.</span></span> <span data-ttu-id="b89ea-113">このパイプラインには、データの前処理変換とトレーニング済みモデルの両方が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b89ea-113">This pipeline contains both the data pre-processing transformations as well as the trained model.</span></span> <span data-ttu-id="b89ea-114">次のコード スニペットは、`model.zip` という名前のファイルから予測パイプラインを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="b89ea-114">The code snippet below loads the prediction pipeline from a file named `model.zip`.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Load Trained Model
DataViewSchema predictionPipelineSchema;
ITransformer predictionPipeline = mlContext.Model.Load("model.zip", out predictionPipelineSchema);
```

## <a name="single-prediction"></a><span data-ttu-id="b89ea-115">1 つの予測</span><span class="sxs-lookup"><span data-stu-id="b89ea-115">Single prediction</span></span>

<span data-ttu-id="b89ea-116">1 つの予測を行うには、読み込まれた予測パイプラインを使用して [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) を作成します。</span><span class="sxs-lookup"><span data-stu-id="b89ea-116">To make a single prediction, create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) using the loaded prediction pipeline.</span></span>

```csharp
// Create PredictionEngines
PredictionEngine<HousingData, HousingPrediction> predictionEngine = mlContext.Model.CreatePredictionEngine<HousingData, HousingPrediction>(predictionPipeline);
```

<span data-ttu-id="b89ea-117">次に、[`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) メソッドを使用して、入力データをパラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="b89ea-117">Then, use the [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) method and pass in your input data as a parameter.</span></span> <span data-ttu-id="b89ea-118">[`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) メソッドを使用する場合、入力が [`IDataView`](xref:Microsoft.ML.IDataView) である必要はない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b89ea-118">Notice that using the [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) method does not require the input to be an [`IDataView`](xref:Microsoft.ML.IDataView)).</span></span> <span data-ttu-id="b89ea-119">これは、入力データ型のオブジェクトを渡すことができるように、入力データ型の操作を簡単に内部化できるためです。</span><span class="sxs-lookup"><span data-stu-id="b89ea-119">This is because it conveniently internalizes the input data type manipulation so you can pass in an object of the input data type.</span></span> <span data-ttu-id="b89ea-120">さらに、`CurrentPrice` は新しいデータを使用して予測しようとしているターゲットまたはラベルなので、この時点では値がないと見なされます。</span><span class="sxs-lookup"><span data-stu-id="b89ea-120">Additionally, since `CurrentPrice` is the target or label you're trying to predict using new data, it's assumed there is no value for it at the moment.</span></span>

```csharp
// Input Data
HousingData inputData = new HousingData
{
    Size = 900f,
    HistoricalPrices = new float[] { 155000f, 190000f, 220000f }
};

// Get Prediction
HousingPrediction prediction = predictionEngine.Predict(inputData);
```

<span data-ttu-id="b89ea-121">`prediction` オブジェクトの `Score` プロパティにアクセスすると、`150079` のような値になります。</span><span class="sxs-lookup"><span data-stu-id="b89ea-121">If you access the `Score` property of the `prediction` object, you should get a value similar to `150079`.</span></span>

## <a name="multiple-predictions"></a><span data-ttu-id="b89ea-122">複数の予測</span><span class="sxs-lookup"><span data-stu-id="b89ea-122">Multiple predictions</span></span>

<span data-ttu-id="b89ea-123">次のデータがあるとして、[`IDataView`](xref:Microsoft.ML.IDataView) に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="b89ea-123">Given the following data, load it into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="b89ea-124">この場合、[`IDataView`](xref:Microsoft.ML.IDataView) の名前は `inputData` です。</span><span class="sxs-lookup"><span data-stu-id="b89ea-124">In this case, the name of the [`IDataView`](xref:Microsoft.ML.IDataView) is `inputData`.</span></span> <span data-ttu-id="b89ea-125">`CurrentPrice` は新しいデータを使用して予測しようとしているターゲットまたはラベルなので、この時点では値がないと見なされます。</span><span class="sxs-lookup"><span data-stu-id="b89ea-125">Because `CurrentPrice` is the target or label you're trying to predict using new data, it's assumed there is no value for it at the moment.</span></span>

```csharp
// Actual data
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f, 175000f, 210000f }
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f }
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f }
    }
};
```

<span data-ttu-id="b89ea-126">次に、[`Transform`](xref:Microsoft.ML.ITransformer.Transform*) メソッドを使用してデータ変換を適用し、予測を生成します。</span><span class="sxs-lookup"><span data-stu-id="b89ea-126">Then, use the [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) method to apply the data transformations and generate predictions.</span></span>

```csharp
// Predicted Data
IDataView predictions = predictionPipeline.Transform(inputData);
```

<span data-ttu-id="b89ea-127">[`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) メソッドを使用して予測値を調べます。</span><span class="sxs-lookup"><span data-stu-id="b89ea-127">Inspect the predicted values by using the [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) method.</span></span>

```csharp
// Get Predictions
float[] scoreColumn = predictions.GetColumn<float>("Score").ToArray();
```

<span data-ttu-id="b89ea-128">スコア列の予測値は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b89ea-128">The predicted values in the score column should look like the following:</span></span>

| <span data-ttu-id="b89ea-129">監視</span><span class="sxs-lookup"><span data-stu-id="b89ea-129">Observation</span></span> | <span data-ttu-id="b89ea-130">予測</span><span class="sxs-lookup"><span data-stu-id="b89ea-130">Prediction</span></span> |
|---|---|
| <span data-ttu-id="b89ea-131">1</span><span class="sxs-lookup"><span data-stu-id="b89ea-131">1</span></span> | <span data-ttu-id="b89ea-132">144638.2</span><span class="sxs-lookup"><span data-stu-id="b89ea-132">144638.2</span></span> |
| <span data-ttu-id="b89ea-133">2</span><span class="sxs-lookup"><span data-stu-id="b89ea-133">2</span></span> | <span data-ttu-id="b89ea-134">150079.4</span><span class="sxs-lookup"><span data-stu-id="b89ea-134">150079.4</span></span> |
| <span data-ttu-id="b89ea-135">3</span><span class="sxs-lookup"><span data-stu-id="b89ea-135">3</span></span> | <span data-ttu-id="b89ea-136">107789.8</span><span class="sxs-lookup"><span data-stu-id="b89ea-136">107789.8</span></span> |
