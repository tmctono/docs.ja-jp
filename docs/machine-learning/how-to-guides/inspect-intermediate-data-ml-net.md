---
title: ML.NET 処理中に中間データを検査する
description: ML.NET 機械学習パイプラインの読み込み中、処理中に中間データを検査する方法と、ML.NET のモデル トレーニング手順について説明します。
ms.date: 06/25/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: 11df1d5caaa7b7974360d863f85afbff18985e47
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "73977097"
---
# <a name="inspect-intermediate-data-during-processing"></a><span data-ttu-id="cf30a-103">処理中に中間データを検査する</span><span class="sxs-lookup"><span data-stu-id="cf30a-103">Inspect intermediate data during processing</span></span>

<span data-ttu-id="cf30a-104">読み込み中、処理中に中間データを検査する方法と、ML.NET のモデル トレーニング手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="cf30a-104">Learn how to inspect intermediate data during loading, processing, and model training steps in ML.NET.</span></span> <span data-ttu-id="cf30a-105">中間データは機械学習パイプラインの各ステージの出力です。</span><span class="sxs-lookup"><span data-stu-id="cf30a-105">Intermediate data is the output of each stage in the machine learning pipeline.</span></span>

<span data-ttu-id="cf30a-106">[`IDataView`](xref:Microsoft.ML.IDataView) に読み込まれる以下に示すような中間データは、ML.NET においてさまざまな方法で検査できます。</span><span class="sxs-lookup"><span data-stu-id="cf30a-106">Intermediate data like the one represented below which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView) can be inspected in various ways in ML.NET.</span></span>

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

## <a name="convert-idataview-to-ienumerable"></a><span data-ttu-id="cf30a-107">IDataView を IEnumerable に変換する</span><span class="sxs-lookup"><span data-stu-id="cf30a-107">Convert IDataView to IEnumerable</span></span>

<span data-ttu-id="cf30a-108">[`IDataView`](xref:Microsoft.ML.IDataView) を検査する最も簡単な方法の 1 つは、[`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) に変換することです。</span><span class="sxs-lookup"><span data-stu-id="cf30a-108">One of the quickest ways to inspect an [`IDataView`](xref:Microsoft.ML.IDataView) is to convert it to an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span></span> <span data-ttu-id="cf30a-109">[`IDataView`](xref:Microsoft.ML.IDataView) を [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) に変換するには、[`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf30a-109">To convert an [`IDataView`](xref:Microsoft.ML.IDataView) to [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) use the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method.</span></span>

<span data-ttu-id="cf30a-110">パフォーマンスを最適化するには、`reuseRowObject` を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="cf30a-110">To optimize performance, set `reuseRowObject` to `true`.</span></span> <span data-ttu-id="cf30a-111">これにより、同一オブジェクトには現在の行のデータが遅れて設定され、データセット内の行ごとに新しいオブジェクトを作成する場合とは対照的に評価されます。</span><span class="sxs-lookup"><span data-stu-id="cf30a-111">Doing so will lazily populate the same object with the data of the current row as it's being evaluated as opposed to creating a new object for each row in the dataset.</span></span>

```csharp
// Create an IEnumerable of HousingData objects from IDataView
IEnumerable<HousingData> housingDataEnumerable =
    mlContext.Data.CreateEnumerable<HousingData>(data, reuseRowObject: true);

// Iterate over each row
foreach (HousingData row in housingDataEnumerable)
{
    // Do something (print out Size property) with current Housing Data object being evaluated
    Console.WriteLine(row.Size);
}
```

## <a name="accessing-specific-indices-with-ienumerable"></a><span data-ttu-id="cf30a-112">IEnumerable を使用して特定のインデックスにアクセスする</span><span class="sxs-lookup"><span data-stu-id="cf30a-112">Accessing specific indices with IEnumerable</span></span>

<span data-ttu-id="cf30a-113">データの一部や特定のインデックスにしかアクセスする必要がない場合は、データセット内の要求された各行に対して新しいオブジェクトが作成されるように、[`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) を使用すると共に `reuseRowObject` パラメータ―の値を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="cf30a-113">If you only need access to a portion of the data or specific indices, use [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) and set the `reuseRowObject` parameter value to `false` so a new object is created for each of the requested rows in the dataset.</span></span> <span data-ttu-id="cf30a-114">その後、[`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) を配列またはリストに変換します。</span><span class="sxs-lookup"><span data-stu-id="cf30a-114">Then, convert the [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) to an array or list.</span></span>

> [!WARNING]
> <span data-ttu-id="cf30a-115">[`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) の結果を配列またはリストに変換すると、要求されたすべての [`IDataView`](xref:Microsoft.ML.IDataView) 行がメモリに読み込まれ、パフォーマンスに影響を及ぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cf30a-115">Converting the result of [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) to an array or list will load all the requested [`IDataView`](xref:Microsoft.ML.IDataView) rows into memory which may affect performance.</span></span>

<span data-ttu-id="cf30a-116">コレクションが作成されたら、データに対する操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="cf30a-116">Once the collection has been created, you can perform operations on the data.</span></span> <span data-ttu-id="cf30a-117">以下のコード スニペットでは、データセット内の最初の 3 つの行を取得して、現在の平均価格を計算します。</span><span class="sxs-lookup"><span data-stu-id="cf30a-117">The code snippet below takes the first three rows in the dataset and calculates the average current price.</span></span>

```csharp
// Create an Array of HousingData objects from IDataView
HousingData[] housingDataArray =
    mlContext.Data.CreateEnumerable<HousingData>(data, reuseRowObject: false)
        .Take(3)
        .ToArray();

// Calculate Average CurrentPrice of First Three Elements
HousingData firstRow = housingDataArray[0];
HousingData secondRow = housingDataArray[1];
HousingData thirdRow = housingDataArray[2];
float averageCurrentPrice = (firstRow.CurrentPrice + secondRow.CurrentPrice + thirdRow.CurrentPrice) / 3;
```

## <a name="inspect-values-in-a-single-column"></a><span data-ttu-id="cf30a-118">単一列内の値を検査する</span><span class="sxs-lookup"><span data-stu-id="cf30a-118">Inspect values in a single column</span></span>

<span data-ttu-id="cf30a-119">モデル構築プロセスの任意の時点で、[`IDataView`](xref:Microsoft.ML.IDataView) の単一列内の値には [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) メソッドを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cf30a-119">At any point in the model building process, values in a single column of an [`IDataView`](xref:Microsoft.ML.IDataView) can be accessed using the [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) method.</span></span> <span data-ttu-id="cf30a-120">[`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) メソッドは、単一列内のすべての値を [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) として返します。</span><span class="sxs-lookup"><span data-stu-id="cf30a-120">The [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) method returns all of the values in a single column as an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span></span>

```csharp
IEnumerable<float> sizeColumn = data.GetColumn<float>("Size").ToList();
```

## <a name="inspect-idataview-values-one-row-at-a-time"></a><span data-ttu-id="cf30a-121">IDataView の値を 1 行ずつ検査する</span><span class="sxs-lookup"><span data-stu-id="cf30a-121">Inspect IDataView values one row at a time</span></span>

<span data-ttu-id="cf30a-122">[`IDataView`](xref:Microsoft.ML.IDataView) は遅れて評価されます。</span><span class="sxs-lookup"><span data-stu-id="cf30a-122">[`IDataView`](xref:Microsoft.ML.IDataView) is lazily evaluated.</span></span> <span data-ttu-id="cf30a-123">このドキュメントの前のセクションで示したように、[`IDataView`](xref:Microsoft.ML.IDataView) に変換せずに [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) の複数の行にわたって反復処理を行うには、[`DataViewRowCursor`](xref:Microsoft.ML.DataViewRowCursor) メソッドを使用して [`GetRowCursor`](xref:Microsoft.ML.IDataView.GetRowCursor*) の [DataViewSchema](xref:Microsoft.ML.DataViewSchema) をパラメーターとして渡すことで、[`IDataView`](xref:Microsoft.ML.IDataView) を作成します。</span><span class="sxs-lookup"><span data-stu-id="cf30a-123">To iterate over the rows of an [`IDataView`](xref:Microsoft.ML.IDataView) without converting to an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) as demonstrated in previous sections of this document, create a [`DataViewRowCursor`](xref:Microsoft.ML.DataViewRowCursor) by using the [`GetRowCursor`](xref:Microsoft.ML.IDataView.GetRowCursor*) method and passing in the [DataViewSchema](xref:Microsoft.ML.DataViewSchema) of your [`IDataView`](xref:Microsoft.ML.IDataView) as a parameter.</span></span> <span data-ttu-id="cf30a-124">その後、複数の行にわたって反復処理を行うために、[`MoveNext`](xref:Microsoft.ML.DataViewRowCursor.MoveNext*) カーソル メソッドを [`ValueGetter`](xref:Microsoft.ML.ValueGetter%601) デリゲートと共に使用して、各列からそれぞれの値を抽出します。</span><span class="sxs-lookup"><span data-stu-id="cf30a-124">Then, to iterate over rows, use the [`MoveNext`](xref:Microsoft.ML.DataViewRowCursor.MoveNext*) cursor method along with [`ValueGetter`](xref:Microsoft.ML.ValueGetter%601) delegates to extract the respective values from each of the columns.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf30a-125">パフォーマンスのために、ML.NET 内のベクターには、ネイティブなコレクション型 (つまり、[、`VBuffer`) ではなく、](xref:Microsoft.ML.Data.VBuffer%601)`Vector``float[]` を使用します。</span><span class="sxs-lookup"><span data-stu-id="cf30a-125">For performance purposes, vectors in ML.NET use [`VBuffer`](xref:Microsoft.ML.Data.VBuffer%601) instead of native collection types (that is, `Vector`,`float[]`).</span></span>

```csharp
// Get DataViewSchema of IDataView
DataViewSchema columns = data.Schema;

// Create DataViewCursor
using (DataViewRowCursor cursor = data.GetRowCursor(columns))
{
    // Define variables where extracted values will be stored to
    float size = default;
    VBuffer<float> historicalPrices = default;
    float currentPrice = default;

    // Define delegates for extracting values from columns
    ValueGetter<float> sizeDelegate = cursor.GetGetter<float>(columns[0]);
    ValueGetter<VBuffer<float>> historicalPriceDelegate = cursor.GetGetter<VBuffer<float>>(columns[1]);
    ValueGetter<float> currentPriceDelegate = cursor.GetGetter<float>(columns[2]);

    // Iterate over each row
    while (cursor.MoveNext())
    {
        //Get values from respective columns
        sizeDelegate.Invoke(ref size);
        historicalPriceDelegate.Invoke(ref historicalPrices);
        currentPriceDelegate.Invoke(ref currentPrice);
    }
}
```

## <a name="preview-result-of-pre-processing-or-training-on-a-subset-of-the-data"></a><span data-ttu-id="cf30a-126">データのサブセットに対する前処理またはトレーニングの結果をプレビューする</span><span class="sxs-lookup"><span data-stu-id="cf30a-126">Preview result of pre-processing or training on a subset of the data</span></span>

> [!WARNING]
> <span data-ttu-id="cf30a-127">`Preview` はデバッグを目的としており、パフォーマンスを低下させる可能性があるため、実稼働環境のコードでは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="cf30a-127">Do not use `Preview` in production code because it is intended for debugging and may reduce performance.</span></span>

<span data-ttu-id="cf30a-128">モデルのビルド プロセスは実験的であり、反復されます。</span><span class="sxs-lookup"><span data-stu-id="cf30a-128">The model building process is experimental and iterative.</span></span> <span data-ttu-id="cf30a-129">データのサブセットに対して機械学習モデルの前処理またはトレーニングを行った後にデータがどうなってるかをプレビューするには、[`Preview`](xref:Microsoft.ML.DebuggerExtensions.Preview*) を返す [`DataDebuggerPreview`](xref:Microsoft.ML.Data.DataDebuggerPreview) メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf30a-129">To preview what data would look like after pre-processing or training a machine learning model on a subset of the data, use the [`Preview`](xref:Microsoft.ML.DebuggerExtensions.Preview*) method which returns a [`DataDebuggerPreview`](xref:Microsoft.ML.Data.DataDebuggerPreview).</span></span> <span data-ttu-id="cf30a-130">結果のオブジェクトは `ColumnView` および `RowView` プロパティを含み、どちらも [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) になっていて、特定の列または行の値が格納されています。</span><span class="sxs-lookup"><span data-stu-id="cf30a-130">The result is an object with `ColumnView` and `RowView` properties which are both an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) and contain the values in a particular column or row.</span></span> <span data-ttu-id="cf30a-131">`maxRows` パラメータ―を使って、変換を適用する行数を指定します。</span><span class="sxs-lookup"><span data-stu-id="cf30a-131">Specify the number of rows to apply the transformation to with the `maxRows` parameter.</span></span>

![データ デバッガーによるオブジェクトのプレビュー](./media/inspect-intermediate-data-ml-net/data-debugger-preview-01.png)

<span data-ttu-id="cf30a-133">[`IDataView`](xref:Microsoft.ML.IDataView) を検査した結果は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="cf30a-133">The result of inspecting an [`IDataView`](xref:Microsoft.ML.IDataView) would look similar to the following:</span></span>

![データ デバッガーによる行のプレビューの表示](./media/inspect-intermediate-data-ml-net/data-debugger-preview-02.png)
