---
title: モデルを再トレーニングする
description: ML.NET でモデルを再トレーニングする方法について説明します
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 552698c02a7846db588822fa68d094dece160ea0
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063566"
---
# <a name="re-train-a-model"></a><span data-ttu-id="89037-103">モデルを再トレーニングする</span><span class="sxs-lookup"><span data-stu-id="89037-103">Re-train a model</span></span>

<span data-ttu-id="89037-104">ML.NET で機械学習モデルを再トレーニングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="89037-104">Learn how to retrain a machine learning model in ML.NET.</span></span>

<span data-ttu-id="89037-105">世界とその周りのデータは一定のペースで変化します。</span><span class="sxs-lookup"><span data-stu-id="89037-105">The world and the data around it change at a constant pace.</span></span> <span data-ttu-id="89037-106">そのため、モデルも同様に変更および更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89037-106">As such, models need to change and update as well.</span></span> <span data-ttu-id="89037-107">ML.NET には、学習したモデルのパラメーターを出発点として使用してモデルを再トレーニングする機能が用意されており、毎回最初から始めるのではなく、以前のエクスペリエンスを継続的に利用できます。</span><span class="sxs-lookup"><span data-stu-id="89037-107">ML.NET provides functionality for re-training models using learned model parameters as a starting point to continually build on previous experience rather than starting from scratch every time.</span></span>  

<span data-ttu-id="89037-108">ML.NET では以下のアルゴリズムを再トレーニングできます。</span><span class="sxs-lookup"><span data-stu-id="89037-108">The following algorithms are re-trainable in ML.NET:</span></span>

- [<span data-ttu-id="89037-109">AveragedPerceptronTrainer</span><span class="sxs-lookup"><span data-stu-id="89037-109">AveragedPerceptronTrainer</span></span>](xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer)
- [<span data-ttu-id="89037-110">FieldAwareFactorizationMachineTrainer</span><span class="sxs-lookup"><span data-stu-id="89037-110">FieldAwareFactorizationMachineTrainer</span></span>](xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer)
- [<span data-ttu-id="89037-111">LbfgsLogisticRegressionBinaryTrainer</span><span class="sxs-lookup"><span data-stu-id="89037-111">LbfgsLogisticRegressionBinaryTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer)
- [<span data-ttu-id="89037-112">LbfgsMaximumEntropyMulticlassTrainer</span><span class="sxs-lookup"><span data-stu-id="89037-112">LbfgsMaximumEntropyMulticlassTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer)
- [<span data-ttu-id="89037-113">LbfgsPoissonRegressionTrainer</span><span class="sxs-lookup"><span data-stu-id="89037-113">LbfgsPoissonRegressionTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer)
- [<span data-ttu-id="89037-114">LinearSvmTrainer</span><span class="sxs-lookup"><span data-stu-id="89037-114">LinearSvmTrainer</span></span>](xref:Microsoft.ML.Trainers.LinearSvmTrainer)
- [<span data-ttu-id="89037-115">OnlineGradientDescentTrainer</span><span class="sxs-lookup"><span data-stu-id="89037-115">OnlineGradientDescentTrainer</span></span>](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer)
- [<span data-ttu-id="89037-116">SgdCalibratedTrainer</span><span class="sxs-lookup"><span data-stu-id="89037-116">SgdCalibratedTrainer</span></span>](xref:Microsoft.ML.Trainers.SgdCalibratedTrainer)
- [<span data-ttu-id="89037-117">SgdNonCalibratedTrainer</span><span class="sxs-lookup"><span data-stu-id="89037-117">SgdNonCalibratedTrainer</span></span>](xref:Microsoft.ML.Trainers.SgdNonCalibratedTrainer)
- [<span data-ttu-id="89037-118">SymbolicSgdLogisticRegressionBinaryTrainer</span><span class="sxs-lookup"><span data-stu-id="89037-118">SymbolicSgdLogisticRegressionBinaryTrainer</span></span>](xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer)

## <a name="load-pre-trained-model"></a><span data-ttu-id="89037-119">トレーニング済みモデルを読み込む</span><span class="sxs-lookup"><span data-stu-id="89037-119">Load pre-trained model</span></span>

<span data-ttu-id="89037-120">まず、トレーニング済みモデルをアプリケーションに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="89037-120">First, load the pre-trained model into your application.</span></span> <span data-ttu-id="89037-121">トレーニング パイプラインとモデルの読み込みの詳細については、関連する[ハウツー記事](./consuming-model-ml-net.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89037-121">To learn more about loading training pipelines and models, see the related [how-to article](./consuming-model-ml-net.md).</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define DataViewSchema of data prep pipeline and trained model
DataViewSchema dataPrepPipelineSchema, modelSchema;

// Load data prepration pipeline
ITransformer dataPrepPipeline = mlContext.Model.Load("data_preparation_pipeline.zip", out dataPrepPipelineSchema);

// Load trained model
ITransformer trainedModel = mlContext.Model.Load("ogd_model.zip", out modelSchema);
```

## <a name="extract-pre-trained-model-parameters"></a><span data-ttu-id="89037-122">トレーニング済みモデルのパラメーターを抽出する</span><span class="sxs-lookup"><span data-stu-id="89037-122">Extract pre-trained model parameters</span></span>

<span data-ttu-id="89037-123">モデルが読み込まれたら、トレーニング済みモデルの [`Model`](xref:Microsoft.ML.Data.PredictionTransformerBase`1.Model*) プロパティにアクセスして、学習済みモデルのパラメーターを抽出します。</span><span class="sxs-lookup"><span data-stu-id="89037-123">Once the model is loaded, extract the learned model parameters by accessing the [`Model`](xref:Microsoft.ML.Data.PredictionTransformerBase`1.Model*) property of the pre-trained model.</span></span> <span data-ttu-id="89037-124">トレーニング済みモデルは、[`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters) を出力する [`RegressionPredictionTransformer`](xref:Microsoft.ML.Data.RegressionPredictionTransformer`1) を作成する線形回帰モデル [`OnlineGradientDescentTrainer`](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer) を使用して学習されています。</span><span class="sxs-lookup"><span data-stu-id="89037-124">The pre-trained model was trained using the linear regression model [`OnlineGradientDescentTrainer`](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer) which creates a[`RegressionPredictionTransformer`](xref:Microsoft.ML.Data.RegressionPredictionTransformer`1) that outputs [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters).</span></span> <span data-ttu-id="89037-125">これらの線形回帰モデルのパラメーターには、学習済みのバイアスと、モデルの重みまたは係数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="89037-125">These linear regression model parameters contain the learned bias and weights or coefficients of the model.</span></span> <span data-ttu-id="89037-126">これらの値は、新しい再トレーニング済みモデルの出発点として使用されます。</span><span class="sxs-lookup"><span data-stu-id="89037-126">These values will be used as a starting point for the new re-trained model.</span></span>

```csharp
// Extract trained model parameters
LinearRegressionModelParameters originalModelParameters = 
    ((ISingleFeaturePredictionTransformer<object>)trainedModel).Model as LinearRegressionModelParameters;
```

## <a name="re-train-model"></a><span data-ttu-id="89037-127">モデルを再トレーニングする</span><span class="sxs-lookup"><span data-stu-id="89037-127">Re-train model</span></span>

<span data-ttu-id="89037-128">モデルを再トレーニングするプロセスは、モデルをトレーニングするプロセスと同じです。</span><span class="sxs-lookup"><span data-stu-id="89037-128">The process for retraining a model is no different than that of training a model.</span></span> <span data-ttu-id="89037-129">唯一の違いは、データに加えて [`Fit`](xref:Microsoft.ML.Trainers.OnlineLinearTrainer`2.Fit*) メソッドも元の学習済みモデル パラメーターを入力として受け取り、それらを再トレーニング プロセスの開始点として使用することです。</span><span class="sxs-lookup"><span data-stu-id="89037-129">The only difference is, the [`Fit`](xref:Microsoft.ML.Trainers.OnlineLinearTrainer`2.Fit*) method in addition to the data also takes as input the original learned model parameters and uses them as a starting point in the re-training process.</span></span>  

```csharp
// New Data
HousingData[] housingData = new HousingData[]
{
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

//Load New Data
IDataView newData = mlContext.Data.LoadFromEnumerable<HousingData>(housingData);

// Preprocess Data
IDataView transformedNewData = dataPrepPipeline.Transform(newData);

// Retrain model
RegressionPredictionTransformer<LinearRegressionModelParameters> retrainedModel = 
    mlContext.Regression.Trainers.OnlineGradientDescent()
        .Fit(transformedNewData, originalModelParameters);
```

## <a name="compare-model-parameters"></a><span data-ttu-id="89037-130">モデルのパラメーターを比較する</span><span class="sxs-lookup"><span data-stu-id="89037-130">Compare model parameters</span></span>

<span data-ttu-id="89037-131">再トレーニングが実際に行われたかどうかを判断するにはどうすればよいでしょうか。</span><span class="sxs-lookup"><span data-stu-id="89037-131">How do you know if re-training actually happened?</span></span> <span data-ttu-id="89037-132">1 つの方法は、再トレーニング済みモデルのパラメーターが元のモデルのものと異なるかどうかを比較することです。</span><span class="sxs-lookup"><span data-stu-id="89037-132">One way would be to compare whether the re-trained model's parameters are different than those of the original model.</span></span> <span data-ttu-id="89037-133">次のコード サンプルでは、元のモデルと再トレーニング済みモデルの重みを比較し、それをコンソールに出力します。</span><span class="sxs-lookup"><span data-stu-id="89037-133">The code sample below compares the original against the re-trained model weights and outputs them to the console.</span></span>

```csharp
// Extract Model Parameters of re-trained model
LinearRegressionModelParameters retrainedModelParameters = retrainedModel.Model as LinearRegressionModelParameters;

// Inspect Change in Weights
var weightDiffs = 
    originalModelParameters.Weights.Zip(
        retrainedModelParameters.Weights, (original, retrained) => original - retrained).ToArray();

Console.WriteLine("Original | Retrained | Difference");
for(int i=0;i < weightDiffs.Count();i++)
{
    Console.WriteLine($"{originalModelParameters.Weights[i]} | {retrainedModelParameters.Weights[i]} | {weightDiffs[i]}");
}
```

<span data-ttu-id="89037-134">以下の表は、出力がどのようになるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="89037-134">The table below shows what the output might look like.</span></span> 

|<span data-ttu-id="89037-135">元</span><span class="sxs-lookup"><span data-stu-id="89037-135">Original</span></span> | <span data-ttu-id="89037-136">再トレーニング済み</span><span class="sxs-lookup"><span data-stu-id="89037-136">Retrained</span></span> | <span data-ttu-id="89037-137">相違点</span><span class="sxs-lookup"><span data-stu-id="89037-137">Difference</span></span> |
|---|---|---|
| <span data-ttu-id="89037-138">33039.86</span><span class="sxs-lookup"><span data-stu-id="89037-138">33039.86</span></span> | <span data-ttu-id="89037-139">56293.76</span><span class="sxs-lookup"><span data-stu-id="89037-139">56293.76</span></span> | <span data-ttu-id="89037-140">-23253.9</span><span class="sxs-lookup"><span data-stu-id="89037-140">-23253.9</span></span> |
| <span data-ttu-id="89037-141">29099.14</span><span class="sxs-lookup"><span data-stu-id="89037-141">29099.14</span></span> | <span data-ttu-id="89037-142">49586.03</span><span class="sxs-lookup"><span data-stu-id="89037-142">49586.03</span></span> | <span data-ttu-id="89037-143">-20486.89</span><span class="sxs-lookup"><span data-stu-id="89037-143">-20486.89</span></span> |
| <span data-ttu-id="89037-144">28938.38</span><span class="sxs-lookup"><span data-stu-id="89037-144">28938.38</span></span> | <span data-ttu-id="89037-145">48609.23</span><span class="sxs-lookup"><span data-stu-id="89037-145">48609.23</span></span> | <span data-ttu-id="89037-146">-19670.85</span><span class="sxs-lookup"><span data-stu-id="89037-146">-19670.85</span></span> |
| <span data-ttu-id="89037-147">30484.02</span><span class="sxs-lookup"><span data-stu-id="89037-147">30484.02</span></span> | <span data-ttu-id="89037-148">53745.43</span><span class="sxs-lookup"><span data-stu-id="89037-148">53745.43</span></span> | <span data-ttu-id="89037-149">-23261.41</span><span class="sxs-lookup"><span data-stu-id="89037-149">-23261.41</span></span> |
