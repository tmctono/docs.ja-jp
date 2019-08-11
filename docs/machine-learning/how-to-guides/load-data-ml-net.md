---
title: ファイルとその他のソースからデータを読み込む
description: このハウツーでは、処理とトレーニング用のデータを ML.NET に読み込む方法について説明します。 データは、もともとはファイルか、またはデータベース、JSON、XML、メモリ内コレクションなどのその他のデータソースに格納されています。
ms.date: 08/01/2019
ms.custom: mvc,how-to, title-hack-0625
ms.openlocfilehash: d5f3aab14a60a8c9860dc67f1cc98f3b1b3188ed
ms.sourcegitcommit: 8c6426a3d2adff5fbcbe1fed0f28eda718c15351
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2019
ms.locfileid: "68733369"
---
# <a name="load-data-from-files-and-other-sources"></a><span data-ttu-id="990c6-104">ファイルとその他のソースからデータを読み込む</span><span class="sxs-lookup"><span data-stu-id="990c6-104">Load data from files and other sources</span></span>

<span data-ttu-id="990c6-105">このハウツーでは、処理とトレーニング用のデータを ML.NET に読み込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="990c6-105">This how-to shows you how to load data for processing and training into ML.NET.</span></span> <span data-ttu-id="990c6-106">データは、もともとはファイルか、またはデータベース、JSON、XML、メモリ内コレクションなどのその他のデータソースに格納されています。</span><span class="sxs-lookup"><span data-stu-id="990c6-106">The data is originally stored in files or other data sources such as databases, JSON, XML or in-memory collections.</span></span>

## <a name="create-the-data-model"></a><span data-ttu-id="990c6-107">データ モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="990c6-107">Create the data model</span></span>

<span data-ttu-id="990c6-108">ML.NET を使用すると、クラスを介してデータ モデルを定義できます。</span><span class="sxs-lookup"><span data-stu-id="990c6-108">ML.NET enables you to define data models via classes.</span></span> <span data-ttu-id="990c6-109">たとえば、次のような入力データがあるとします。</span><span class="sxs-lookup"><span data-stu-id="990c6-109">For example, given the following input data:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

<span data-ttu-id="990c6-110">以下のスニペットを表すデータ モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="990c6-110">Create a data model that represents the snippet below:</span></span>

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

### <a name="annotating-the-data-model-with-column-attributes"></a><span data-ttu-id="990c6-111">列属性を使用してデータ モデルに注釈を付ける</span><span class="sxs-lookup"><span data-stu-id="990c6-111">Annotating the data model with column attributes</span></span>

<span data-ttu-id="990c6-112">属性を使用すると、データ モデルとデータ ソースについてより多くの情報を ML.NET に与えられます。</span><span class="sxs-lookup"><span data-stu-id="990c6-112">Attributes give ML.NET more information about the data model and the data source.</span></span>

<span data-ttu-id="990c6-113">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) 属性では、プロパティの列インデックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="990c6-113">The [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute specifies your properties' column indices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="990c6-114">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) は、ファイルからデータを読み込む場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="990c6-114">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) is only required when loading data from a file.</span></span>

<span data-ttu-id="990c6-115">列は次のように読み込みます。</span><span class="sxs-lookup"><span data-stu-id="990c6-115">Load columns as:</span></span> 
- <span data-ttu-id="990c6-116">`HousingData` クラスの `Size` や `CurrentPrices` のように個々の列。</span><span class="sxs-lookup"><span data-stu-id="990c6-116">Individual columns like `Size` and `CurrentPrices` in the `HousingData` class.</span></span>
- <span data-ttu-id="990c6-117">`HousingData` クラスの `HistoricalPrices` のようにベクター形式で一度に複数の列。</span><span class="sxs-lookup"><span data-stu-id="990c6-117">Multiple columns at a time in the form of a vector like `HistoricalPrices` in the `HousingData` class.</span></span>

<span data-ttu-id="990c6-118">ベクター プロパティがある場合は、データ モデルのプロパティに [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) 属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="990c6-118">If you have a vector property, apply the [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) attribute to the property in your data model.</span></span> <span data-ttu-id="990c6-119">ベクター内のすべての要素は同じ型にする必要がある点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="990c6-119">It's important to note that all of the elements in the vector need to be the same type.</span></span> <span data-ttu-id="990c6-120">列を分割したままにすると、特徴エンジニアリングが容易になり、柔軟性が向上しますが、列数が非常に多い場合、個々の列を操作するとトレーニング速度に影響します。</span><span class="sxs-lookup"><span data-stu-id="990c6-120">Keeping the columns separated allows for ease and flexibility of feature engineering, but for a very large number of columns, operating on the individual columns causes an impact on training speed.</span></span>

<span data-ttu-id="990c6-121">ML.NET は列名を介して動作します。</span><span class="sxs-lookup"><span data-stu-id="990c6-121">ML.NET Operates through column names.</span></span> <span data-ttu-id="990c6-122">列の名前をプロパティ名以外に変更する場合は、[`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="990c6-122">If you want to change the name of a column to something other than the property name, use the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span> <span data-ttu-id="990c6-123">メモリ内オブジェクトを作成するときも、プロパティ名を使ってオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="990c6-123">When creating in-memory objects, you still create objects using the property name.</span></span> <span data-ttu-id="990c6-124">ただし、データ処理と機械学習モデルの構築の場合、ML.NET では [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 属性に指定された値でプロパティがオーバーライドされ、参照されます。</span><span class="sxs-lookup"><span data-stu-id="990c6-124">However, for data processing and building machine learning models, ML.NET overrides and references the property with the value provided in the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span>

## <a name="load-data-from-a-single-file"></a><span data-ttu-id="990c6-125">1 つのファイルからデータを読み込む</span><span class="sxs-lookup"><span data-stu-id="990c6-125">Load data from a single file</span></span>

<span data-ttu-id="990c6-126">ファイルからデータを読み込むには、読み込むデータのデータ モデルと共に [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="990c6-126">To load data from a file use the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method along with the data model for the data to be loaded.</span></span> <span data-ttu-id="990c6-127">`separatorChar` パラメーターは既定でタブ区切りなので、必要に応じてデータ ファイルに合わせて変更します。</span><span class="sxs-lookup"><span data-stu-id="990c6-127">Since `separatorChar` parameter is tab-delimited by default, change it for your data file as needed.</span></span> <span data-ttu-id="990c6-128">ファイルにヘッダーがある場合は、ファイルの最初の行を無視して 2 行目からデータの読み込みを開始するように、`hasHeader` パラメーターを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="990c6-128">If your file has a header, set the `hasHeader` parameter to `true` to ignore the first line in the file and begin to load data from the second line.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a><span data-ttu-id="990c6-129">複数のファイルからデータを読み込む</span><span class="sxs-lookup"><span data-stu-id="990c6-129">Load data from multiple files</span></span>

<span data-ttu-id="990c6-130">データが複数のファイルに格納されている場合、データ スキーマが同じである限り、ML.NET では、同じディレクトリまたは複数のディレクトリ内にある複数のファイルからデータを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="990c6-130">In the event that your data is stored in multiple files, as long as the data schema is the same, ML.NET allows you to load data from multiple files that are either in the same directory or multiple directories.</span></span>

### <a name="load-from-files-in-a-single-directory"></a><span data-ttu-id="990c6-131">1 つのディレクトリ内のファイルから読み込む</span><span class="sxs-lookup"><span data-stu-id="990c6-131">Load from files in a single directory</span></span>

<span data-ttu-id="990c6-132">すべてのデータ ファイルが同じディレクトリ内にある場合は、[`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) メソッドでワイルドカードを使用します。</span><span class="sxs-lookup"><span data-stu-id="990c6-132">When all of your data files are in the same directory, use wildcards in the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a><span data-ttu-id="990c6-133">複数のディレクトリ内にあるファイルから読み込む</span><span class="sxs-lookup"><span data-stu-id="990c6-133">Load from files in multiple directories</span></span>

<span data-ttu-id="990c6-134">複数のディレクトリからデータを読み込むには、[`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) メソッドを使用して [`TextLoader`](xref:Microsoft.ML.Data.TextLoader) を作成します。</span><span class="sxs-lookup"><span data-stu-id="990c6-134">To load data from multiple directories, use the [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) method to create a [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span></span> <span data-ttu-id="990c6-135">次に、[`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) メソッドを使用して個々のファイル パスを指定します (ワイルドカードは使用できません)。</span><span class="sxs-lookup"><span data-stu-id="990c6-135">Then, use the [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) method and specify the individual file paths (wildcards can't be used).</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-other-sources"></a><span data-ttu-id="990c6-136">その他のソースからデータを読み込む</span><span class="sxs-lookup"><span data-stu-id="990c6-136">Load data from other sources</span></span>

<span data-ttu-id="990c6-137">ファイル内の格納データの読み込みに加え、ML.NET では、以下のようなソースからのデータの読み込みがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="990c6-137">In addition to loading data stored in files, ML.NET supports loading data from sources that include but are not limited to:</span></span>

- <span data-ttu-id="990c6-138">メモリ内コレクション</span><span class="sxs-lookup"><span data-stu-id="990c6-138">In-memory collections</span></span>
- <span data-ttu-id="990c6-139">JSON/XML</span><span class="sxs-lookup"><span data-stu-id="990c6-139">JSON/XML</span></span>
- <span data-ttu-id="990c6-140">データベース</span><span class="sxs-lookup"><span data-stu-id="990c6-140">Databases</span></span>

<span data-ttu-id="990c6-141">ストリーミング ソースを使用する場合、ML.NET では入力がメモリ内コレクション形式であると想定される点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="990c6-141">Note that when working with streaming sources, ML.NET expects input to be in the form of an in-memory collection.</span></span> <span data-ttu-id="990c6-142">そのため、JSON/XML などのソースを使用するときは、必ずデータをメモリ内コレクション形式にします。</span><span class="sxs-lookup"><span data-stu-id="990c6-142">Therefore, when working with sources like JSON/XML, make sure to format the data into an in-memory collection.</span></span>

<span data-ttu-id="990c6-143">次のメモリ内コレクションがあるとします。</span><span class="sxs-lookup"><span data-stu-id="990c6-143">Given the following in-memory collection:</span></span>

```csharp
HousingData[] inMemoryCollection = new HousingData[]
{
    new HousingData
    {
        Size =700f,
        HistoricalPrices = new float[]
        {
            100000f, 3000000f, 250000f
        },
        CurrentPrice = 500000f
    },
    new HousingData
    {
        Size =1000f,
        HistoricalPrices = new float[]
        {
            600000f, 400000f, 650000f
        },
        CurrentPrice=700000f
    }
};
```

<span data-ttu-id="990c6-144">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) メソッドを使用してメモリ内コレクションを [`IDataView`](xref:Microsoft.ML.IDataView) に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="990c6-144">Load the in-memory collection into an [`IDataView`](xref:Microsoft.ML.IDataView) with the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="990c6-145">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) では、この読み込み元の [`IEnumerable`](xref:System.Collections.IEnumerable) がスレッドセーフであると想定されています。</span><span class="sxs-lookup"><span data-stu-id="990c6-145">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) assumes that the [`IEnumerable`](xref:System.Collections.IEnumerable) it loads from is thread-safe.</span></span> 

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```
