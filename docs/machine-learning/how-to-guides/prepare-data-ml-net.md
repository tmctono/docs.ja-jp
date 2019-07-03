---
title: データの準備
description: ML.NET での変換を利用して、追加処理やモデルのビルドのためにデータを操作して準備する方法について説明します。
author: luisquintanilla
ms.author: luquinta
ms.date: 05/03/2019
ms.custom: mvc, how-to
ms.openlocfilehash: abf43260a438c9b1febffc77cf39e7328e0377ee
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2019
ms.locfileid: "67268237"
---
# <a name="prepare-data"></a><span data-ttu-id="5d44a-103">データの準備</span><span class="sxs-lookup"><span data-stu-id="5d44a-103">Prepare Data</span></span>

<span data-ttu-id="5d44a-104">ML.NET を利用して、追加処理やモデルのビルドのためのデータを準備する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-104">Learn how to use ML.NET to prepare data for additional processing or building a model.</span></span>

<span data-ttu-id="5d44a-105">多くの場合、データは未整理であり、分散しています。</span><span class="sxs-lookup"><span data-stu-id="5d44a-105">Data is often unclean and sparse.</span></span> <span data-ttu-id="5d44a-106">加えて、ML.NET 機械学習アルゴリズムでは、入力値などの特性が単一の数値ベクターになっていることを期待します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-106">Additionally, ML.NET machine learning algorithms expect input or features to be in a single numerical vector.</span></span> <span data-ttu-id="5d44a-107">したがって、データ準備の目標の 1 つは、データを ML.NET アルゴリズムから期待されている形式にすることです。</span><span class="sxs-lookup"><span data-stu-id="5d44a-107">Therefore one of the goals of data preparation is to get the data into the format expected by ML.NET algorithms.</span></span> 

## <a name="filter-data"></a><span data-ttu-id="5d44a-108">データのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="5d44a-108">Filter data</span></span>

<span data-ttu-id="5d44a-109">データセット内の全データが、分析に関係するわけではない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="5d44a-109">Sometimes, not all data in a dataset is relevant for analysis.</span></span> <span data-ttu-id="5d44a-110">関係のないデータを除去する方法が、フィルター処理です。</span><span class="sxs-lookup"><span data-stu-id="5d44a-110">An approach to remove irrelevant data is filtering.</span></span> <span data-ttu-id="5d44a-111">[`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) には、全データを含む [`IDataView`](xref:Microsoft.ML.IDataView) を取得して目的のデータだけを含む [IDataView](xref:Microsoft.ML.IDataView) を返す一連のフィルター操作が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5d44a-111">The [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) contains a set of filter operations that take in an [`IDataView`](xref:Microsoft.ML.IDataView) containing all of the data and return an [IDataView](xref:Microsoft.ML.IDataView) containing only the data points of interest.</span></span> <span data-ttu-id="5d44a-112">フィルター操作は、[`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog) にあるような [`IEstimator`](xref:Microsoft.ML.IEstimator%601) または [`ITransformer`](xref:Microsoft.ML.ITransformer) ではないため、[`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) または [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601) データ準備パイプラインの一部に含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="5d44a-112">It's important to note that because filter operations are not an [`IEstimator`](xref:Microsoft.ML.IEstimator%601) or [`ITransformer`](xref:Microsoft.ML.ITransformer) like those in the [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), they cannot be included as part of an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) or [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601) data preparation pipeline.</span></span> 

<span data-ttu-id="5d44a-113">次の入力データを使用して、[`IDataView`](xref:Microsoft.ML.IDataView) に読み込ませます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-113">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms=1f,
        Price=100000f
    },
    new HomeData
    {
        NumberOfBedrooms=2f,
        Price=300000f
    },
    new HomeData
    {
        NumberOfBedrooms=6f,
        Price=600000f
    }
};
```

<span data-ttu-id="5d44a-114">列の値に基づいてデータをフィルター処理するには、[`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*) メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-114">To filter data based on the value of a column, use the [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*) method.</span></span>

```csharp
// Apply filter
IDataView filteredData = mlContext.Data.FilterRowsByColumn(data, "Price", lowerBound: 200000, upperBound: 1000000);
```

<span data-ttu-id="5d44a-115">上記のサンプルでは、データセット内の価格が 200000 から 1000000 までの行を取得します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-115">The sample above takes rows in the dataset with a price between 200000 and 1000000.</span></span> <span data-ttu-id="5d44a-116">このフィルターを適用した結果として、データ内の最後の 2 行だけが返されます。最初の行は価格が 100000 になっており、指定された範囲外にあるために除外されます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-116">The result of applying this filter would return only the last two rows in the data and exclude the first row because its price is 100000 and not between the specified range.</span></span>

## <a name="replace-missing-values"></a><span data-ttu-id="5d44a-117">欠損値を置き換える</span><span class="sxs-lookup"><span data-stu-id="5d44a-117">Replace missing values</span></span>

<span data-ttu-id="5d44a-118">欠損値は、データセット内でよく発生します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-118">Missing values are a common occurrence in datasets.</span></span> <span data-ttu-id="5d44a-119">欠損値を処理する 1 つの方法は、指定された型の既定値があればその値に、またはそのデータの平均値などの意味のある別の値に置き換えることです。</span><span class="sxs-lookup"><span data-stu-id="5d44a-119">One approach to dealing with missing values is to replace them with the default value for the given type if any or another meaningful value such as the mean value in the data.</span></span> 

<span data-ttu-id="5d44a-120">次の入力データを使用して、[`IDataView`](xref:Microsoft.ML.IDataView) に読み込ませます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-120">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms=1f,
        Price=100000f
    },
    new HomeData
    {
        NumberOfBedrooms=2f,
        Price=300000f
    },
    new HomeData
    {
        NumberOfBedrooms=6f,
        Price=float.NaN
    }
};
```

<span data-ttu-id="5d44a-121">リスト内の最後の要素では、`Price` が欠損値になっていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5d44a-121">Notice that the last element in our list has a missing value for `Price`.</span></span> <span data-ttu-id="5d44a-122">`Price` 列内の欠損値を置き換えるには、[`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) メソッドを使用して該当の欠損値を入力します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-122">To replace the missing values in the `Price` column, use the [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) method to fill in that missing value.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d44a-123">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) は、数値データのみで機能します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-123">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) only works with numerical data.</span></span>

```csharp
// Define replacement estimator
var replacementEstimator = mlContext.Transforms.ReplaceMissingValues("Price", replacementMode: MissingValueReplacingEstimator.ReplacementMode.Mean);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer replacementTransformer = replacementEstimator.Fit(data);

// Transform data
IDataView transformedData = replacementTransformer.Transform(data);
```

<span data-ttu-id="5d44a-124">ML.NET では、さまざまな[置換モード](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode)をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5d44a-124">ML.NET supports various [replacement modes](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode).</span></span> <span data-ttu-id="5d44a-125">上記のサンプルでは、該当の列の平均値を使って欠損値を入力する、`Mean` 置換モードを使用しています。</span><span class="sxs-lookup"><span data-stu-id="5d44a-125">The sample above uses the `Mean` replacement mode which will fill in the missing value with that column's average value.</span></span> <span data-ttu-id="5d44a-126">置換の結果、データ内の最後の要素である `Price` プロパティには、100,000 と 300,000 の平均として 200,000 が入力されます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-126">The replacement 's result fills in the `Price` property for the last element in our data with 200,000 since it's the average of 100,000 and 300,000.</span></span> 

## <a name="use-normalizers"></a><span data-ttu-id="5d44a-127">ノーマライザーを使用する</span><span class="sxs-lookup"><span data-stu-id="5d44a-127">Use normalizers</span></span>

<span data-ttu-id="5d44a-128">[正規化](https://en.wikipedia.org/wiki/Feature_scaling)は、アルゴリズムの適用を迅速に行えるように、同じスケール上にない特性を標準化する目的で使用されるデータの事前処理手法です。</span><span class="sxs-lookup"><span data-stu-id="5d44a-128">[Normalization](https://en.wikipedia.org/wiki/Feature_scaling) is a data pre-processing technique used to standardize features that are not on the same scale which helps algorithms converge faster.</span></span> <span data-ttu-id="5d44a-129">たとえば、年齢と収入のような値の範囲は、年齢は一般的に 0 から 100 の範囲で、また、収入は一般的に 0 から 1000 単位の範囲で、大きく変わります。</span><span class="sxs-lookup"><span data-stu-id="5d44a-129">For example, the ranges for values like age and income vary significantly with age generally being in the range of 0-100 and income generally being in the range of zero to thousands.</span></span> <span data-ttu-id="5d44a-130">正規化変換のより詳細な一覧と説明については、[変換に関するページ](../resources/transforms.md)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="5d44a-130">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of normalization transforms.</span></span> 

### <a name="min-max-normalization"></a><span data-ttu-id="5d44a-131">最小 - 最大の正規化</span><span class="sxs-lookup"><span data-stu-id="5d44a-131">Min-Max normalization</span></span>

<span data-ttu-id="5d44a-132">次の入力データを使用して、[`IDataView`](xref:Microsoft.ML.IDataView) に読み込ませます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-132">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms = 2f,
        Price = 200000f
    },
    new HomeData
    {
        NumberOfBedrooms = 1f,
        Price = 100000f
    }
};
```

<span data-ttu-id="5d44a-133">正規化は、1 つの数値およびベクターを含む列に適用できます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-133">Normalization can be applied to columns with single numerical values as well as vectors.</span></span> <span data-ttu-id="5d44a-134">[`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) メソッドによる最小 - 最大の正規化を使って、`Price` 列のデータを正規化します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-134">Normalize the data in the `Price` column using min-max normalization with the [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) method.</span></span>

```csharp
// Define min-max estimator
var minMaxEstimator = mlContext.Transforms.NormalizeMinMax("Price");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer minMaxTransformer = minMaxEstimator.Fit(data);

// Transform data
IDataView transformedData = minMaxTransformer.Transform(data);
```

<span data-ttu-id="5d44a-135">0 から 1 の範囲で出力値を生成する `MinMax` 正規化の数式を使用して、元の価格値 `[200000,100000]` が `[ 1, 0.5 ]` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-135">The original price values `[200000,100000]` are converted to `[ 1, 0.5 ]` using the `MinMax` normalization formula which generates output values in the range of 0-1.</span></span>

### <a name="binning"></a><span data-ttu-id="5d44a-136">ビン分割</span><span class="sxs-lookup"><span data-stu-id="5d44a-136">Binning</span></span>

<span data-ttu-id="5d44a-137">[ビン分割](https://en.wikipedia.org/wiki/Data_binning)では、連続する値を不連続な入力値表現に変換します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-137">[Binning](https://en.wikipedia.org/wiki/Data_binning) converts continuous values into a discrete representation of the input.</span></span> <span data-ttu-id="5d44a-138">たとえば、特性の 1 つが年齢だとします。</span><span class="sxs-lookup"><span data-stu-id="5d44a-138">For example, suppose one of your features is age.</span></span> <span data-ttu-id="5d44a-139">実際の年齢値を使用する代わりに、ビン分割によってその値の範囲を作成します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-139">Instead of using the actual age value,  binning creates ranges for that value.</span></span> <span data-ttu-id="5d44a-140">0 から 18 を 1 つのビン、19 から 35 をもう 1 つのビン、のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-140">0-18 could be one bin, another could be 19-35 and so on.</span></span> 

<span data-ttu-id="5d44a-141">次の入力データを使用して、[`IDataView`](xref:Microsoft.ML.IDataView) に読み込ませます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-141">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms=1f,
        Price=100000f
    },
    new HomeData
    {
        NumberOfBedrooms=2f,
        Price=300000f
    },
    new HomeData
    {
        NumberOfBedrooms=6f,
        Price=600000f
    }
};
```

<span data-ttu-id="5d44a-142">[`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning*) メソッドを使用して、データをビンに正規化します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-142">Normalize the data into bins using the [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning*) method.</span></span> <span data-ttu-id="5d44a-143">`maximumBinCount` パラメータ―を使用すると、データを分類するために必要なビン数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-143">The `maximumBinCount` parameter enables you to specify the number of bins needed to classify your data.</span></span> <span data-ttu-id="5d44a-144">この例では、データは 2 つのビンに配置されます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-144">In this example, data will be put into two bins.</span></span>  

```csharp
// Define binning estimator
var binningEstimator = mlContext.Transforms.NormalizeBinning("Price", maximumBinCount: 2);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
var binningTransformer = binningEstimator.Fit(data);

// Transform Data
IDataView transformedData = binningTransformer.Transform(data);
```

<span data-ttu-id="5d44a-145">ビン分割の結果、`[0,200000,Infinity]` のビン境界が作成されます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-145">The result of binning creates bin bounds of `[0,200000,Infinity]`.</span></span> <span data-ttu-id="5d44a-146">したがって、最初の測定範囲を 0 から 200000 まで、それ以外を 200000 より大きいが無限大より小さいとするため、結果として得られるビンは `[0,1,1]` となります。</span><span class="sxs-lookup"><span data-stu-id="5d44a-146">Therefore the resulting bins are `[0,1,1]` because the first observation is between 0-200000 and the others are greater than 200000 but less than infinity.</span></span>

## <a name="work-with-categorical-data"></a><span data-ttu-id="5d44a-147">カテゴリ別データを扱う</span><span class="sxs-lookup"><span data-stu-id="5d44a-147">Work with categorical data</span></span>

<span data-ttu-id="5d44a-148">非数値のカテゴリ別データは、機械学習モデルのビルドに使用する前に、数値に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d44a-148">Non-numeric categorical data needs to be converted to a number before being used to build a machine learning model.</span></span> 

<span data-ttu-id="5d44a-149">次の入力データを使用して、[`IDataView`](xref:Microsoft.ML.IDataView) に読み込ませます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-149">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
CarData[] cars = new CarData[] 
{
    new CarData
    {
        Color="Red",
        VehicleType="SUV"
    },
    new CarData
    {
        Color="Blue",
        VehicleType="Sedan"
    },
    new CarData
    {
        Color="Black",
        VehicleType="SUV"
    }
};
```

<span data-ttu-id="5d44a-150">カテゴリ別の `VehicleType` プロパティは、[`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*) メソッドを使用して数値に変換できます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-150">The categorical `VehicleType` property can be converted into a number using the [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*) method.</span></span> 

```csharp
// Define categorical transform estimator
var categoricalEstimator = mlContext.Transforms.Categorical.OneHotEncoding("VehicleType");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer categoricalTransformer = categoricalEstimator.Fit(data);

// Transform Data
IDataView transformedData = categoricalTransformer.Transform(data);
```

<span data-ttu-id="5d44a-151">変換の結果、`VehicleType` のテキスト値が数値に変わります。</span><span class="sxs-lookup"><span data-stu-id="5d44a-151">The resulting transform converts the text value of `VehicleType` to a number.</span></span> <span data-ttu-id="5d44a-152">変換が適用されると、`VehicleType` 列内の項目は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5d44a-152">The entries in the `VehicleType` column become the following when the transform is applied:</span></span> 

```text
[
    1, // SUV
    2, // Sedan
    1 // SUV
]
```

## <a name="work-with-text-data"></a><span data-ttu-id="5d44a-153">テキスト データを操作する</span><span class="sxs-lookup"><span data-stu-id="5d44a-153">Work with text data</span></span>

<span data-ttu-id="5d44a-154">テキスト データは、機械学習モデルのビルドに使用する前に、数値に変換される必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d44a-154">Text data needs to be transformed into numbers before using it to build a machine learning model.</span></span> <span data-ttu-id="5d44a-155">テキスト変換のより詳細な一覧と説明については、[変換に関するページ](../resources/transforms.md)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="5d44a-155">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of text transforms.</span></span>

<span data-ttu-id="5d44a-156">以下のようなデータを使用します。データは [`IDataView`](xref:Microsoft.ML.IDataView) に読み込まれています。</span><span class="sxs-lookup"><span data-stu-id="5d44a-156">Using data like the data below that has been loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
ReviewData[] reviews = new ReviewData[]
{
    new ReviewData
    {
        Description="This is a good product",
        Rating=4.7f
    },
    new ReviewData
    {
        Description="This is a bad product",
        Rating=2.3f
    }
};
```

<span data-ttu-id="5d44a-157">テキストを数値ベクター表現に変換する最も簡単な手順は、[`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) メソッドを使用することです。</span><span class="sxs-lookup"><span data-stu-id="5d44a-157">The minimum step to convert text to a numerical vector representation is to use the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) method.</span></span> <span data-ttu-id="5d44a-158">[`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) 変換を使用することで、一連の変換が入力テキストの列に適用されて、Ip 正則化による単語と文字の N グラムを表した数値ベクターになります。</span><span class="sxs-lookup"><span data-stu-id="5d44a-158">By using the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) transform, a series of transformations is applied to the input text column resulting in a numerical vector representing the lp-normalized word and character ngrams.</span></span> 

```csharp
// Define text transform estimator
var textEstimator  = mlContext.Transforms.Text.FeaturizeText("Description");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer textTransformer = textEstimator.Fit(data);

// Transform data
IDataView transformedData = textTransformer.Transform(data);
```

<span data-ttu-id="5d44a-159">変換の結果、`Description` 列内のテキスト値が、以下の出力のような数値ベクターに変換されます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-159">The resulting transform would convert the text values in the `Description` column to a numerical vector that looks similar to the output below:</span></span>

```text
[ 0.2041241, 0.2041241, 0.2041241, 0.4082483, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0, 0, 0, 0, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0 ]
```

<span data-ttu-id="5d44a-160">複数のテキスト処理の手順を [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) に結合してノイズを除去し、必要な処理リソース量をニーズに応じて潜在的に低減させます。</span><span class="sxs-lookup"><span data-stu-id="5d44a-160">Combine complex text processing steps into an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) to remove noise and potentially reduce the amount of required processing resources as needed.</span></span>

```csharp
// Define text transform estimator
var textEstimator = mlContext.Transforms.Text.NormalizeText("Description")
    .Append(mlContext.Transforms.Text.TokenizeIntoWords("Description"))
    .Append(mlContext.Transforms.Text.RemoveDefaultStopWords("Description"))
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Description"))
    .Append(mlContext.Transforms.Text.ProduceNgrams("Description"))
    .Append(mlContext.Transforms.NormalizeLpNorm("Description"));
```

<span data-ttu-id="5d44a-161">`textEstimator` には、[`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) メソッドによって実行される操作のサブセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5d44a-161">`textEstimator` contains a subset of operations performed by the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) method.</span></span> <span data-ttu-id="5d44a-162">より複雑なパイプラインの利点は、データに適用される変換に対する制御と可視性です。</span><span class="sxs-lookup"><span data-stu-id="5d44a-162">The benefit of a more complex pipeline is control and visibility over the transformations applied to the data.</span></span> 

<span data-ttu-id="5d44a-163">最初の項目を例として使用した場合、`textEstimator` によって定義された変換手順で生成した結果を詳細に説明すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5d44a-163">Using the first entry as an example, the following is a detailed description of the results produced by the transformation steps defined by `textEstimator`:</span></span>

<span data-ttu-id="5d44a-164">**元のテキスト:This is a good product**</span><span class="sxs-lookup"><span data-stu-id="5d44a-164">**Original Text: This is a good product**</span></span>

|<span data-ttu-id="5d44a-165">変換</span><span class="sxs-lookup"><span data-stu-id="5d44a-165">Transform</span></span> | <span data-ttu-id="5d44a-166">説明</span><span class="sxs-lookup"><span data-stu-id="5d44a-166">Description</span></span> | <span data-ttu-id="5d44a-167">結果</span><span class="sxs-lookup"><span data-stu-id="5d44a-167">Result</span></span>
|--|--|--|
|<span data-ttu-id="5d44a-168">1.NormalizeText</span><span class="sxs-lookup"><span data-stu-id="5d44a-168">1. NormalizeText</span></span> | <span data-ttu-id="5d44a-169">既定ですべての文字を小文字に変換します</span><span class="sxs-lookup"><span data-stu-id="5d44a-169">Converts all letters to lowercase by default</span></span> | <span data-ttu-id="5d44a-170">this is a good product</span><span class="sxs-lookup"><span data-stu-id="5d44a-170">this is a good product</span></span>
|<span data-ttu-id="5d44a-171">2.TokenizeWords</span><span class="sxs-lookup"><span data-stu-id="5d44a-171">2. TokenizeWords</span></span> | <span data-ttu-id="5d44a-172">文字列を個々の単語に分割します</span><span class="sxs-lookup"><span data-stu-id="5d44a-172">Splits string into individual words</span></span> | <span data-ttu-id="5d44a-173">["this","is","a","good","product"]</span><span class="sxs-lookup"><span data-stu-id="5d44a-173">["this","is","a","good","product"]</span></span>
|<span data-ttu-id="5d44a-174">3.RemoveDefaultStopWords</span><span class="sxs-lookup"><span data-stu-id="5d44a-174">3. RemoveDefaultStopWords</span></span> | <span data-ttu-id="5d44a-175">*is* や *a* のようなストップワードを削除します。</span><span class="sxs-lookup"><span data-stu-id="5d44a-175">Removes stopwords like *is* and *a*.</span></span> | <span data-ttu-id="5d44a-176">["good","product"]</span><span class="sxs-lookup"><span data-stu-id="5d44a-176">["good","product"]</span></span>
|<span data-ttu-id="5d44a-177">4.MapValueToKey</span><span class="sxs-lookup"><span data-stu-id="5d44a-177">4. MapValueToKey</span></span> | <span data-ttu-id="5d44a-178">入力データに基づくキー (カテゴリ) に値をマップします</span><span class="sxs-lookup"><span data-stu-id="5d44a-178">Maps the values to keys (categories) based on the input data</span></span> |  <span data-ttu-id="5d44a-179">[1,2]</span><span class="sxs-lookup"><span data-stu-id="5d44a-179">[1,2]</span></span>
|<span data-ttu-id="5d44a-180">5.ProduceNGrams</span><span class="sxs-lookup"><span data-stu-id="5d44a-180">5. ProduceNGrams</span></span> | <span data-ttu-id="5d44a-181">テキストを連続する単語のシーケンスに変換します</span><span class="sxs-lookup"><span data-stu-id="5d44a-181">Transforms text into sequence of consecutive words</span></span> | <span data-ttu-id="5d44a-182">[1,1,1,0,0]</span><span class="sxs-lookup"><span data-stu-id="5d44a-182">[1,1,1,0,0]</span></span>
|<span data-ttu-id="5d44a-183">6.NormalizeLpNorm</span><span class="sxs-lookup"><span data-stu-id="5d44a-183">6. NormalizeLpNorm</span></span> | <span data-ttu-id="5d44a-184">lp 正則化によって入力値をスケーリングします</span><span class="sxs-lookup"><span data-stu-id="5d44a-184">Scale inputs by their lp-norm</span></span> | <span data-ttu-id="5d44a-185">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span><span class="sxs-lookup"><span data-stu-id="5d44a-185">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span></span>
