---
title: ファイルとその他のソースからデータを読み込む
description: API を利用し、処理とトレーニング用のデータを ML.NET に読み込む方法について説明します。 データはファイル、データベース、JSON、XML、メモリ内コレクションに格納されます。
ms.date: 11/07/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to, title-hack-0625
ms.openlocfilehash: 83aaae2d2e75b3076841750bf5d505390a538bc0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344754"
---
# <a name="load-data-from-files-and-other-sources"></a><span data-ttu-id="22802-104">ファイルとその他のソースからデータを読み込む</span><span class="sxs-lookup"><span data-stu-id="22802-104">Load data from files and other sources</span></span>

<span data-ttu-id="22802-105">API を利用し、処理とトレーニング用のデータを ML.NET に読み込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="22802-105">Learn how to load data for processing and training into ML.NET using the API.</span></span> <span data-ttu-id="22802-106">データは、もともとはファイルか、またはデータベース、JSON、XML、メモリ内コレクションなどのその他のデータソースに格納されています。</span><span class="sxs-lookup"><span data-stu-id="22802-106">The data is originally stored in files or other data sources such as databases, JSON, XML or in-memory collections.</span></span>

<span data-ttu-id="22802-107">モデル ビルダーを使用している場合、「[モデル ビルダーにトレーニング データを読み込む](load-data-model-builder.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22802-107">If you're using Model Builder, see [Load training data into Model Builder](load-data-model-builder.md).</span></span>

## <a name="create-the-data-model"></a><span data-ttu-id="22802-108">データ モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="22802-108">Create the data model</span></span>

<span data-ttu-id="22802-109">ML.NET を使用すると、クラスを介してデータ モデルを定義できます。</span><span class="sxs-lookup"><span data-stu-id="22802-109">ML.NET enables you to define data models via classes.</span></span> <span data-ttu-id="22802-110">たとえば、次のような入力データがあるとします。</span><span class="sxs-lookup"><span data-stu-id="22802-110">For example, given the following input data:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

<span data-ttu-id="22802-111">以下のスニペットを表すデータ モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="22802-111">Create a data model that represents the snippet below:</span></span>

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

### <a name="annotating-the-data-model-with-column-attributes"></a><span data-ttu-id="22802-112">列属性を使用してデータ モデルに注釈を付ける</span><span class="sxs-lookup"><span data-stu-id="22802-112">Annotating the data model with column attributes</span></span>

<span data-ttu-id="22802-113">属性を使用すると、データ モデルとデータ ソースについてより多くの情報を ML.NET に与えられます。</span><span class="sxs-lookup"><span data-stu-id="22802-113">Attributes give ML.NET more information about the data model and the data source.</span></span>

<span data-ttu-id="22802-114">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) 属性では、プロパティの列インデックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="22802-114">The [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute specifies your properties' column indices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="22802-115">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) は、ファイルからデータを読み込む場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="22802-115">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) is only required when loading data from a file.</span></span>

<span data-ttu-id="22802-116">列は次のように読み込みます。</span><span class="sxs-lookup"><span data-stu-id="22802-116">Load columns as:</span></span>

- <span data-ttu-id="22802-117">`HousingData` クラスの `Size` や `CurrentPrices` のように個々の列。</span><span class="sxs-lookup"><span data-stu-id="22802-117">Individual columns like `Size` and `CurrentPrices` in the `HousingData` class.</span></span>
- <span data-ttu-id="22802-118">`HousingData` クラスの `HistoricalPrices` のようにベクター形式で一度に複数の列。</span><span class="sxs-lookup"><span data-stu-id="22802-118">Multiple columns at a time in the form of a vector like `HistoricalPrices` in the `HousingData` class.</span></span>

<span data-ttu-id="22802-119">ベクター プロパティがある場合は、データ モデルのプロパティに [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) 属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="22802-119">If you have a vector property, apply the [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) attribute to the property in your data model.</span></span> <span data-ttu-id="22802-120">ベクター内のすべての要素は同じ型にする必要がある点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="22802-120">It's important to note that all of the elements in the vector need to be the same type.</span></span> <span data-ttu-id="22802-121">列を分割したままにすると、特徴エンジニアリングが容易になり、柔軟性が向上しますが、列数が非常に多い場合、個々の列を操作するとトレーニング速度に影響します。</span><span class="sxs-lookup"><span data-stu-id="22802-121">Keeping the columns separated allows for ease and flexibility of feature engineering, but for a very large number of columns, operating on the individual columns causes an impact on training speed.</span></span>

<span data-ttu-id="22802-122">ML.NET は列名を介して動作します。</span><span class="sxs-lookup"><span data-stu-id="22802-122">ML.NET Operates through column names.</span></span> <span data-ttu-id="22802-123">列の名前をプロパティ名以外に変更する場合は、[`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="22802-123">If you want to change the name of a column to something other than the property name, use the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span> <span data-ttu-id="22802-124">メモリ内オブジェクトを作成するときも、プロパティ名を使ってオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="22802-124">When creating in-memory objects, you still create objects using the property name.</span></span> <span data-ttu-id="22802-125">ただし、データ処理と機械学習モデルの構築の場合、ML.NET では [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 属性に指定された値でプロパティがオーバーライドされ、参照されます。</span><span class="sxs-lookup"><span data-stu-id="22802-125">However, for data processing and building machine learning models, ML.NET overrides and references the property with the value provided in the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span>

## <a name="load-data-from-a-single-file"></a><span data-ttu-id="22802-126">1 つのファイルからデータを読み込む</span><span class="sxs-lookup"><span data-stu-id="22802-126">Load data from a single file</span></span>

<span data-ttu-id="22802-127">ファイルからデータを読み込むには、読み込むデータのデータ モデルと共に [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="22802-127">To load data from a file use the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method along with the data model for the data to be loaded.</span></span> <span data-ttu-id="22802-128">`separatorChar` パラメーターは既定でタブ区切りなので、必要に応じてデータ ファイルに合わせて変更します。</span><span class="sxs-lookup"><span data-stu-id="22802-128">Since `separatorChar` parameter is tab-delimited by default, change it for your data file as needed.</span></span> <span data-ttu-id="22802-129">ファイルにヘッダーがある場合は、ファイルの最初の行を無視して 2 行目からデータの読み込みを開始するように、`hasHeader` パラメーターを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="22802-129">If your file has a header, set the `hasHeader` parameter to `true` to ignore the first line in the file and begin to load data from the second line.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a><span data-ttu-id="22802-130">複数のファイルからデータを読み込む</span><span class="sxs-lookup"><span data-stu-id="22802-130">Load data from multiple files</span></span>

<span data-ttu-id="22802-131">データが複数のファイルに格納されている場合、データ スキーマが同じである限り、ML.NET では、同じディレクトリまたは複数のディレクトリ内にある複数のファイルからデータを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="22802-131">In the event that your data is stored in multiple files, as long as the data schema is the same, ML.NET allows you to load data from multiple files that are either in the same directory or multiple directories.</span></span>

### <a name="load-from-files-in-a-single-directory"></a><span data-ttu-id="22802-132">1 つのディレクトリ内のファイルから読み込む</span><span class="sxs-lookup"><span data-stu-id="22802-132">Load from files in a single directory</span></span>

<span data-ttu-id="22802-133">すべてのデータ ファイルが同じディレクトリ内にある場合は、[`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) メソッドでワイルドカードを使用します。</span><span class="sxs-lookup"><span data-stu-id="22802-133">When all of your data files are in the same directory, use wildcards in the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a><span data-ttu-id="22802-134">複数のディレクトリ内にあるファイルから読み込む</span><span class="sxs-lookup"><span data-stu-id="22802-134">Load from files in multiple directories</span></span>

<span data-ttu-id="22802-135">複数のディレクトリからデータを読み込むには、[`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) メソッドを使用して [`TextLoader`](xref:Microsoft.ML.Data.TextLoader) を作成します。</span><span class="sxs-lookup"><span data-stu-id="22802-135">To load data from multiple directories, use the [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) method to create a [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span></span> <span data-ttu-id="22802-136">次に、[`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) メソッドを使用して個々のファイル パスを指定します (ワイルドカードは使用できません)。</span><span class="sxs-lookup"><span data-stu-id="22802-136">Then, use the [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) method and specify the individual file paths (wildcards can't be used).</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-a-relational-database"></a><span data-ttu-id="22802-137">リレーショナル データベースからデータを読み込む</span><span class="sxs-lookup"><span data-stu-id="22802-137">Load data from a relational database</span></span>

<span data-ttu-id="22802-138">ML.NET では、SQL Server、Azure SQL Database、Oracle、SQLite、PostgreSQL、Progress、IBM DB2 など数多くの、[`System.Data`](xref:System.Data) でサポートされている多様なリレーショナル データベースからのデータの読み込みがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="22802-138">ML.NET supports loading data from a variety of relational databases supported by [`System.Data`](xref:System.Data) that include SQL Server, Azure SQL Database, Oracle, SQLite, PostgreSQL, Progress, IBM DB2, and many more.</span></span>

> [!NOTE]
> <span data-ttu-id="22802-139">`DatabaseLoader` を使用するには、[System.Data.SqlClient](https://www.nuget.org/packages/System.Data.SqlClient) NuGet パッケージを参照します。</span><span class="sxs-lookup"><span data-stu-id="22802-139">To use `DatabaseLoader`, reference the [System.Data.SqlClient](https://www.nuget.org/packages/System.Data.SqlClient) NuGet package.</span></span>

<span data-ttu-id="22802-140">`House` という名前のテーブルと、次のスキーマが指定されたデータベースがあるとします。</span><span class="sxs-lookup"><span data-stu-id="22802-140">Given a database with a table named `House` and the following schema:</span></span>

```SQL
CREATE TABLE [House] (
    [HouseId] INT NOT NULL IDENTITY,
    [Size] INT NOT NULL,
    [NumBed] INT NOT NULL,
    [Price] REAL NOT NULL
    CONSTRAINT [PK_House] PRIMARY KEY ([HouseId])
);
```

<span data-ttu-id="22802-141">データは `HouseData` などのクラスでモデル化できます。</span><span class="sxs-lookup"><span data-stu-id="22802-141">The data can be modeled by a class like `HouseData`.</span></span>

```csharp
public class HouseData
{
    public float Size { get; set; }

    public float NumBed { get; set; }

    public float Price { get; set; }
}
```

<span data-ttu-id="22802-142">次に、アプリケーション内で `DatabaseLoader` を作成します。</span><span class="sxs-lookup"><span data-stu-id="22802-142">Then, inside of your application, create a `DatabaseLoader`.</span></span>

```csharp
MLContext mlContext = new MLContext();

DatabaseLoader loader = mlContext.Data.CreateDatabaseLoader<HouseData>();
```

<span data-ttu-id="22802-143">接続文字列と、データベースで実行される SQL コマンドを定義して、`DatabaseSource` インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="22802-143">Define your connection string as well as the SQL command to be executed on the database and create a `DatabaseSource` instance.</span></span> <span data-ttu-id="22802-144">このサンプルでは、LocalDB の SQL Server データベースをファイル パスと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="22802-144">This sample uses a LocalDB SQL Server database with a file path.</span></span> <span data-ttu-id="22802-145">ただし、DatabaseLoader では、オンプレミスとクラウドのデータベースに対して、その他のすべての有効な接続文字列がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="22802-145">However, DatabaseLoader supports any other valid connection string for databases on-premises and in the cloud.</span></span>

```csharp
string connectionString = @"Data Source=(LocalDB)\MSSQLLocalDB;AttachDbFilename=<YOUR-DB-FILEPATH>;Database=<YOUR-DB-NAME>;Integrated Security=True;Connect Timeout=30";

string sqlCommand = "SELECT Size, CAST(NumBed as REAL) as NumBed, Price FROM House";

DatabaseSource dbSource = new DatabaseSource(SqlClientFactory.Instance, connectionString, sqlCommand);
```

<span data-ttu-id="22802-146">[`Real`](xref:System.Data.SqlDbType) 型ではない数値データは [`Real`](xref:System.Data.SqlDbType)に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22802-146">Numerical data that is not of type [`Real`](xref:System.Data.SqlDbType) has to be converted to [`Real`](xref:System.Data.SqlDbType).</span></span> <span data-ttu-id="22802-147">[`Real`](xref:System.Data.SqlDbType) 型は、単精度浮動小数点値または ML.NET アルゴリズムによって求められる入力型の [`Single`](xref:System.Single) として表されます。</span><span class="sxs-lookup"><span data-stu-id="22802-147">The [`Real`](xref:System.Data.SqlDbType) type is represented as a single-precision floating-point value or [`Single`](xref:System.Single), the input type expected by ML.NET algorithms.</span></span> <span data-ttu-id="22802-148">このサンプルでは、`NumBed` 列はデータベース内では整数になります。</span><span class="sxs-lookup"><span data-stu-id="22802-148">In this sample, the `NumBed` column is an integer in the database.</span></span> <span data-ttu-id="22802-149">`CAST` 組み込み関数を使用すると、[`Real`](xref:System.Data.SqlDbType) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="22802-149">Using the `CAST` built-in function, it's converted to [`Real`](xref:System.Data.SqlDbType).</span></span> <span data-ttu-id="22802-150">`Price` プロパティは既に [`Real`](xref:System.Data.SqlDbType) 型であるため、そのまま読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="22802-150">Because the `Price` property is already of type [`Real`](xref:System.Data.SqlDbType) it is loaded as is.</span></span>

<span data-ttu-id="22802-151">`Load` メソッドを使用して [`IDataView`](xref:Microsoft.ML.IDataView) にデータを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="22802-151">Use the `Load` method to load the data into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

```csharp
IDataView data = loader.Load(dbSource);
```

## <a name="load-data-from-other-sources"></a><span data-ttu-id="22802-152">その他のソースからデータを読み込む</span><span class="sxs-lookup"><span data-stu-id="22802-152">Load data from other sources</span></span>

<span data-ttu-id="22802-153">ファイル内の格納データの読み込みに加え、ML.NET では、以下のようなソースからのデータの読み込みがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="22802-153">In addition to loading data stored in files, ML.NET supports loading data from sources that include but are not limited to:</span></span>

- <span data-ttu-id="22802-154">メモリ内コレクション</span><span class="sxs-lookup"><span data-stu-id="22802-154">In-memory collections</span></span>
- <span data-ttu-id="22802-155">JSON/XML</span><span class="sxs-lookup"><span data-stu-id="22802-155">JSON/XML</span></span>

<span data-ttu-id="22802-156">ストリーミング ソースを使用する場合、ML.NET では入力がメモリ内コレクション形式であると想定される点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="22802-156">Note that when working with streaming sources, ML.NET expects input to be in the form of an in-memory collection.</span></span> <span data-ttu-id="22802-157">そのため、JSON/XML などのソースを使用するときは、必ずデータをメモリ内コレクション形式にします。</span><span class="sxs-lookup"><span data-stu-id="22802-157">Therefore, when working with sources like JSON/XML, make sure to format the data into an in-memory collection.</span></span>

<span data-ttu-id="22802-158">次のメモリ内コレクションがあるとします。</span><span class="sxs-lookup"><span data-stu-id="22802-158">Given the following in-memory collection:</span></span>

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

<span data-ttu-id="22802-159">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) メソッドを使用してメモリ内コレクションを [`IDataView`](xref:Microsoft.ML.IDataView) に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="22802-159">Load the in-memory collection into an [`IDataView`](xref:Microsoft.ML.IDataView) with the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="22802-160">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) では、この読み込み元の [`IEnumerable`](xref:System.Collections.IEnumerable) がスレッドセーフであると想定されています。</span><span class="sxs-lookup"><span data-stu-id="22802-160">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) assumes that the [`IEnumerable`](xref:System.Collections.IEnumerable) it loads from is thread-safe.</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```

## <a name="next-steps"></a><span data-ttu-id="22802-161">次の手順</span><span class="sxs-lookup"><span data-stu-id="22802-161">Next steps</span></span>

- <span data-ttu-id="22802-162">データを消去するか、消去以外の処理を行う方法については、「[モデル構築用のデータを準備する](prepare-data-ml-net.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22802-162">To clean or otherwise process data, see [Prepare data for building a model](prepare-data-ml-net.md).</span></span>
- <span data-ttu-id="22802-163">モデルを構築する用意ができたら、「[モデルのトレーニングと評価](train-machine-learning-model-ml-net.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22802-163">When you're ready to build a model, see [Train and evaluate a model](train-machine-learning-model-ml-net.md).</span></span>
