---
title: トレーニング済みモデルの保存と読み込み
description: トレーニング済みモデルの保存と読み込みの方法について説明します
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: f1a3131126f9f3af0bab0b1592430fbf7dddf78a
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799091"
---
# <a name="save-and-load-trained-models"></a><span data-ttu-id="c9f74-103">トレーニング済みモデルの保存と読み込み</span><span class="sxs-lookup"><span data-stu-id="c9f74-103">Save and load trained models</span></span>

<span data-ttu-id="c9f74-104">アプリケーションでのトレーニング済みモデルの保存と読み込みの方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9f74-104">Learn how to save and load trained models in your application.</span></span> 

<span data-ttu-id="c9f74-105">モデルは、モデル構築プロセス全体を通してメモリ内に存在し、アプリケーションのライフサイクル全体を通してアクセス可能です。</span><span class="sxs-lookup"><span data-stu-id="c9f74-105">Throughout the model building process, a model lives in memory and is accessible throughout the application's lifecycle.</span></span> <span data-ttu-id="c9f74-106">ただし、アプリケーションの実行が停止した後は、モデルがローカルまたはリモートのどこかに保存されていないと、アクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="c9f74-106">However, once the application stops running, if the model is not saved somewhere locally or remotely, it's no longer accessible.</span></span> <span data-ttu-id="c9f74-107">通常、モデルは、トレーニング後のどこかの時点で推論または再トレーニングのために他のアプリケーションで使用されます。</span><span class="sxs-lookup"><span data-stu-id="c9f74-107">Typically models are used at some point after training in other applications either for inference or re-training.</span></span> <span data-ttu-id="c9f74-108">そのため、モデルを保存することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c9f74-108">Therefore, it's important to store the model.</span></span> <span data-ttu-id="c9f74-109">後述するようにデータ準備とモデル トレーニング パイプラインを使用する場合は、このドキュメントの以降のセクションで説明する手順を使用してモデルを保存し、読み込みます。</span><span class="sxs-lookup"><span data-stu-id="c9f74-109">Save and load models using the steps described in subsequent sections of this document when using data preparation and model training pipelines like the one detailed below.</span></span> <span data-ttu-id="c9f74-110">このサンプルでは線形回帰モデルを使用しますが、他の ML.NET アルゴリズムにも同じプロセスが適用されます。</span><span class="sxs-lookup"><span data-stu-id="c9f74-110">Although this sample uses a linear regression model, the same process applies to other ML.NET algorithms.</span></span>

```csharp
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 600f,
        HistoricalPrices = new float[] { 100000f, 125000f, 122000f },
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
    }
};

// Create MLContext
MLContext mlContext = new MLContext();

// Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(housingData);

// Define data preparation estimator
EstimatorChain<RegressionPredictionTransformer<LinearRegressionModelParameters>> pipelineEstimator =
    mlContext.Transforms.Concatenate("Features", new string[] { "Size", "HistoricalPrices" })
        .Append(mlContext.Transforms.NormalizeMinMax("Features"))
        .Append(mlContext.Regression.Trainers.Sdca());

// Train model
ITransformer trainedModel = pipelineEstimator.Fit(data);

// Save model
mlContext.Model.Save(trainedModel, data.Schema, "model.zip");
```

<span data-ttu-id="c9f74-111">ほとんどのモデルとデータ準備パイプラインは同じクラスのセットから継承するため、このようなコンポーネントの save メソッドと load メソッドのシグネチャは同じです。</span><span class="sxs-lookup"><span data-stu-id="c9f74-111">Because most models and data preparation pipelines inherit from the same set of classes, the save and load method signatures for these components is the same.</span></span> <span data-ttu-id="c9f74-112">実際のユース ケースに応じて、データ準備パイプラインとモデルを 1 つの [`EstimatorChain`](xref:Microsoft.ML.Data.TransformerChain%601) に結合して 1 つの [`ITransformer`](xref:Microsoft.ML.ITransformer) を出力するか、それぞれを分けて個別の [`ITransformer`](xref:Microsoft.ML.ITransformer) を作成します。</span><span class="sxs-lookup"><span data-stu-id="c9f74-112">Depending on your use case, you can either combine the data preparation pipeline and model into a single [`EstimatorChain`](xref:Microsoft.ML.Data.TransformerChain%601) which would output a single [`ITransformer`](xref:Microsoft.ML.ITransformer) or separate them thus creating a separate [`ITransformer`](xref:Microsoft.ML.ITransformer) for each.</span></span> 

## <a name="save-a-model-locally"></a><span data-ttu-id="c9f74-113">モデルをローカルに保存する</span><span class="sxs-lookup"><span data-stu-id="c9f74-113">Save a model locally</span></span>

<span data-ttu-id="c9f74-114">モデルを保存するときには、以下の 2 つが必要です。</span><span class="sxs-lookup"><span data-stu-id="c9f74-114">When saving a model you need two things:</span></span>

1. <span data-ttu-id="c9f74-115">モデルの [`ITransformer`](xref:Microsoft.ML.ITransformer)。</span><span class="sxs-lookup"><span data-stu-id="c9f74-115">The [`ITransformer`](xref:Microsoft.ML.ITransformer) of the model.</span></span>
2. <span data-ttu-id="c9f74-116">[`ITransformer`](xref:Microsoft.ML.ITransformer) の想定される入力の [`DataViewSchema`](xref:Microsoft.ML.DataViewSchema)。</span><span class="sxs-lookup"><span data-stu-id="c9f74-116">The [`DataViewSchema`](xref:Microsoft.ML.DataViewSchema) of the [`ITransformer`](xref:Microsoft.ML.ITransformer)'s expected input.</span></span>

<span data-ttu-id="c9f74-117">モデルのトレーニング後、[`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save*) メソッドを使用し、入力データの `DataViewSchema` を使用してトレーニング済みモデルを `model.zip` というファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="c9f74-117">After training the model, use the [`Save`](xref:Microsoft.ML.ModelOperationsCatalog.Save*) method to save the trained model to a file called `model.zip` using the `DataViewSchema` of the input data.</span></span> 

```csharp
// Save Trained Model
mlContext.Model.Save(trainedModel, data.Schema, "model.zip");
```

## <a name="load-a-model-stored-locally"></a><span data-ttu-id="c9f74-118">ローカルに保存されているモデルを読み込む</span><span class="sxs-lookup"><span data-stu-id="c9f74-118">Load a model stored locally</span></span>

<span data-ttu-id="c9f74-119">ローカルに保存されたモデルは、他のプロセスやアプリケーション (`ASP.NET Core`、`Serverless Web Applications` など) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9f74-119">Models stored locally can be used in other processes or applications like `ASP.NET Core` and `Serverless Web Applications`.</span></span> <span data-ttu-id="c9f74-120">詳細については、[Web API での ML.NET の使用](./serve-model-web-api-ml-net.md)と [ML.NET サーバーレス Web アプリの展開](./serve-model-serverless-azure-functions-ml-net.md)に関するハウツー記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9f74-120">See [Use ML.NET in Web API](./serve-model-web-api-ml-net.md) and [Deploy ML.NET Serverless Web App](./serve-model-serverless-azure-functions-ml-net.md) how-to articles to learn more.</span></span> 

<span data-ttu-id="c9f74-121">個別のアプリケーションまたはプロセスでは、ファイル パスと共に [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load*) メソッドを使用して、トレーニング済みモデルをアプリケーションに取り込みます。</span><span class="sxs-lookup"><span data-stu-id="c9f74-121">In a separate application or process, use the [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load*) method along with the file path to get the trained model into your application.</span></span>

```csharp
//Define DataViewSchema for data preparation pipeline and trained model
DataViewSchema modelSchema;

// Load trained model
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```

## <a name="load-a-model-stored-remotely"></a><span data-ttu-id="c9f74-122">リモートに保存されているモデルを読み込む</span><span class="sxs-lookup"><span data-stu-id="c9f74-122">Load a model stored remotely</span></span>

<span data-ttu-id="c9f74-123">リモートの場所に保存されているデータ準備パイプラインとモデルをアプリケーションに読み込むには、[`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load*) メソッドでファイル パスではなく [`Stream`](xref:System.IO.Stream) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f74-123">To load data preparation pipelines and models stored in a remote location into your application, use a [`Stream`](xref:System.IO.Stream) instead of a file path in the [`Load`](xref:Microsoft.ML.ModelOperationsCatalog.Load*) method.</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define DataViewSchema and ITransformers
DataViewSchema modelSchema;
ITransformer trainedModel;

// Load data prep pipeline and trained model 
using (HttpClient client = new HttpClient())
{
    Stream modelFile = await client.GetStreamAsync("<YOUR-REMOTE-FILE-LOCATION>");

    trainedModel = mlContext.Model.Load(modelFile, out modelSchema);
}
```

## <a name="working-with-separate-data-preparation-and-model-pipelines"></a><span data-ttu-id="c9f74-124">個別のデータ準備パイプラインとモデル パイプラインを使用する</span><span class="sxs-lookup"><span data-stu-id="c9f74-124">Working with separate data preparation and model pipelines</span></span>

> [!NOTE]
> <span data-ttu-id="c9f74-125">個別のデータ準備パイプラインとモデル トレーニング パイプラインの使用は任意です。</span><span class="sxs-lookup"><span data-stu-id="c9f74-125">Working with separate data preparation and model training pipelines is optional.</span></span> <span data-ttu-id="c9f74-126">パイプラインを分けると、学習したモデルのパラメーターを簡単に調べることができます。</span><span class="sxs-lookup"><span data-stu-id="c9f74-126">Separation of pipelines makes it easier to inspect the learned model parameters.</span></span> <span data-ttu-id="c9f74-127">予測のためには、データ準備とモデル トレーニング操作を含む 1 つのパイプラインを保存して読み込む方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="c9f74-127">For predictions, it's easier to save and load a single pipeline that includes the data preparation and model training operations.</span></span>

<span data-ttu-id="c9f74-128">個別のデータ準備パイプラインとモデルを使用するときは、1 つのパイプラインと同じプロセスが適用されます。ただし、この場合は両方のパイプラインを同時に保存して読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9f74-128">When working with separate data preparation pipelines and models, the same process as single pipelines applies; except now both pipelines need to be saved and loaded simultaneously.</span></span>

<span data-ttu-id="c9f74-129">個別のデータ準備パイプラインとモデル トレーニング パイプラインの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c9f74-129">Given separate data preparation and model training pipelines:</span></span>

```csharp
// Define data preparation estimator
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", new string[] { "Size", "HistoricalPrices" })
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// Create data preparation transformer
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(data);

// Define StochasticDualCoordinateAscent regression algorithm estimator
var sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Pre-process data using data prep operations
IDataView transformedData = dataPrepTransformer.Transform(data);

// Train regression model
RegressionPredictionTransformer<LinearRegressionModelParameters> trainedModel = sdcaEstimator.Fit(transformedData);
```

### <a name="save-data-preparation-pipeline-and-trained-model"></a><span data-ttu-id="c9f74-130">データ準備パイプラインとトレーニング済みモデルを保存する</span><span class="sxs-lookup"><span data-stu-id="c9f74-130">Save data preparation pipeline and trained model</span></span>

<span data-ttu-id="c9f74-131">データ準備パイプラインとトレーニング済みモデルの両方を保存するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9f74-131">To save both the data preparation pipeline and trained model, use the following commands:</span></span>

```csharp
// Save Data Prep transformer
mlContext.Model.Save(dataPrepTransformer, data.Schema, "data_preparation_pipeline.zip");

// Save Trained Model
mlContext.Model.Save(trainedModel, transformedData.Schema, "model.zip");
```

### <a name="load-data-preparation-pipeline-and-trained-model"></a><span data-ttu-id="c9f74-132">データ準備パイプラインとトレーニング済みモデルを読み込む</span><span class="sxs-lookup"><span data-stu-id="c9f74-132">Load data preparation pipeline and trained model</span></span> 

<span data-ttu-id="c9f74-133">個別のプロセスまたはアプリケーションで、次のようにデータ準備パイプラインとトレーニング済みモデルを同時に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="c9f74-133">In a separate process or application, load the data preparation pipeline and trained model simultaneously as follows:</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define data preparation and trained model schemas
DataViewSchema dataPrepPipelineSchema, modelSchema;

// Load data preparation pipeline and trained model
ITransformer dataPrepPipeline = mlContext.Model.Load("data_preparation_pipeline.zip",out dataPrepPipelineSchema);
ITransformer trainedModel = mlContext.Model.Load("model.zip", out modelSchema);
```
