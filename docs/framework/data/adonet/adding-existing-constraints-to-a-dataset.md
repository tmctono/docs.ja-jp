---
title: DataSet への既存の制約の追加
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: db072692eba4044e854f25ff2c7f8c9960714018
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785115"
---
# <a name="adding-existing-constraints-to-a-dataset"></a><span data-ttu-id="f6b79-102">DataSet への既存の制約の追加</span><span class="sxs-lookup"><span data-stu-id="f6b79-102">Adding Existing Constraints to a DataSet</span></span>
<span data-ttu-id="f6b79-103">**DataAdapter**の<xref:System.Data.DataSet> **Fill**メソッドは、データソースのテーブルの列と行だけを格納します。制約は通常、データソースによって設定されますが、このスキーマ情報 **は Fill メソッドによって**既定ではデータセットです。</span><span class="sxs-lookup"><span data-stu-id="f6b79-103">The **Fill** method of the **DataAdapter** fills a <xref:System.Data.DataSet> only with table columns and rows from a data source; though constraints are commonly set by the data source, the **Fill** method does not add this schema information to the **DataSet** by default.</span></span> <span data-ttu-id="f6b79-104">データソースからの既存の primary key 制約情報を**DataSet**に設定するには、 **dataadapter**の**FillSchema**メソッドを呼び出すか、 **dataadapter**の**MissingSchemaAction**プロパティを設定します。**Fill**を呼び出す前に、 **addwithkey**に設定します。</span><span class="sxs-lookup"><span data-stu-id="f6b79-104">To populate a **DataSet** with existing primary key constraint information from a data source, you can either call the **FillSchema** method of the **DataAdapter**, or set the **MissingSchemaAction** property of the **DataAdapter** to **AddWithKey** before calling **Fill**.</span></span> <span data-ttu-id="f6b79-105">これにより、データ**セット**内の primary key 制約がデータソースの主キー制約を反映するようになります。</span><span class="sxs-lookup"><span data-stu-id="f6b79-105">This will ensure that primary key constraints in the **DataSet** reflect those at the data source.</span></span> <span data-ttu-id="f6b79-106">外部キー制約情報は含まれていません。 [DataTable 制約](./dataset-datatable-dataview/datatable-constraints.md)に示すように、明示的に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6b79-106">Foreign key constraint information is not included and must be created explicitly, as shown in [DataTable Constraints](./dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="f6b79-107">データを格納する前に、データ**セット**にスキーマ情報を追加することで、主キー <xref:System.Data.DataTable>制約が**dataset**のオブジェクトに含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="f6b79-107">Adding schema information to a **DataSet** before filling it with data ensures that primary key constraints are included with the <xref:System.Data.DataTable> objects in the **DataSet**.</span></span> <span data-ttu-id="f6b79-108">その結果、データ**セット**への追加の呼び出しが行われたときに、主キー列の情報が使用され、データソースからの新しい行と各**DataTable**の現在の行が一致します。テーブル内の現在のデータは、データソース。</span><span class="sxs-lookup"><span data-stu-id="f6b79-108">As a result, when additional calls to fill the **DataSet** are made, the primary key column information is used to match new rows from the data source with current rows in each **DataTable**, and current data in the tables is overwritten with data from the data source.</span></span> <span data-ttu-id="f6b79-109">スキーマ情報がない場合、データソースからの新しい行がデータ**セット**に追加され、行が重複します。</span><span class="sxs-lookup"><span data-stu-id="f6b79-109">Without the schema information, the new rows from the data source are appended to the **DataSet**, resulting in duplicate rows.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f6b79-110">データソース内の列が自動インクリメントとして識別された場合、 **FillSchema**メソッド、または**MissingSchemaAction**が**Addwithkey**である**Fill**メソッドによって、 **autoincrement**プロパティを持つ**DataColumn**が作成されます。をに`true`設定します。</span><span class="sxs-lookup"><span data-stu-id="f6b79-110">If a column in a data source is identified as auto-incrementing, the **FillSchema** method, or the **Fill** method with a **MissingSchemaAction** of **AddWithKey**, creates a **DataColumn** with an **AutoIncrement** property set to `true`.</span></span> <span data-ttu-id="f6b79-111">ただし、 **AutoIncrementStep**と**AutoIncrementSeed**の値を自分で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6b79-111">However, you will need to set the **AutoIncrementStep** and **AutoIncrementSeed** values yourself.</span></span> <span data-ttu-id="f6b79-112">自動インクリメント列の詳細については、「自動[インクリメント列の作成](./dataset-datatable-dataview/creating-autoincrement-columns.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6b79-112">For more information about auto-incrementing columns, see [Creating AutoIncrement Columns](./dataset-datatable-dataview/creating-autoincrement-columns.md).</span></span>  
  
 <span data-ttu-id="f6b79-113">**FillSchema**を使用するか、 **MissingSchemaAction**を**addwithkey**に設定するには、主キー列の情報を決定するためにデータソースで追加の処理が必要です。</span><span class="sxs-lookup"><span data-stu-id="f6b79-113">Using **FillSchema** or setting the **MissingSchemaAction** to **AddWithKey** requires extra processing at the data source to determine primary key column information.</span></span> <span data-ttu-id="f6b79-114">この追加の処理によりパフォーマンスが低下する場合があります。</span><span class="sxs-lookup"><span data-stu-id="f6b79-114">This additional processing can hinder performance.</span></span> <span data-ttu-id="f6b79-115">デザイン時に主キー情報がわかっている場合は、最適のパフォーマンスを得るために主キー列 (複数の場合もある) を明示的に指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f6b79-115">If you know the primary key information at design time, we recommend that you explicitly specify the primary key column or columns in order to achieve optimal performance.</span></span> <span data-ttu-id="f6b79-116">テーブルの主キー情報を明示的に設定する方法については、「[主キーの定義](./dataset-datatable-dataview/defining-primary-keys.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6b79-116">For information about explicitly setting primary key information for a table, see [Defining Primary Keys](./dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
 <span data-ttu-id="f6b79-117">次のコード例では、 **FillSchema**を使用して**データセット**にスキーマ情報を追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f6b79-117">The following code example shows how to add schema information to a **DataSet** using **FillSchema**.</span></span>  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
 <span data-ttu-id="f6b79-118">次のコード例では、 **Fill**メソッドの**MissingSchemaAction**プロパティを使用して、**データセット**にスキーマ情報を追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f6b79-118">The following code example shows how to add schema information to a **DataSet** using the **MissingSchemaAction.AddWithKey** property of the **Fill** method.</span></span>  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="f6b79-119">複数の結果セットの処理</span><span class="sxs-lookup"><span data-stu-id="f6b79-119">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="f6b79-120">データ**アダプター**が**SelectCommand**から返された複数の結果セットを検出すると、**データセット**内に複数のテーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f6b79-120">If the **DataAdapter** encounters multiple result sets returned from the **SelectCommand**, it will create multiple tables in the **DataSet**.</span></span> <span data-ttu-id="f6b79-121">テーブルには、インデックス番号が0から始まる既定の**テーブル** *N*が割り当てられます。この名前は、"Table0" の代わりに**table**で始まります。</span><span class="sxs-lookup"><span data-stu-id="f6b79-121">The tables will be given a zero-based incremental default name of **Table** *N*, starting with **Table** instead of "Table0".</span></span> <span data-ttu-id="f6b79-122">テーブル名が**FillSchema**メソッドに引数として渡された場合、テーブルには、"TableName0" ではなく**Tablename**で始まる**tablename** *N*の0から始まる増分名が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f6b79-122">If a table name is passed as an argument to the **FillSchema** method, the tables will be given a zero-based incremental name of **TableName** *N*, starting with **TableName** instead of "TableName0".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f6b79-123">複数の結果セットを返すコマンドに対して**OleDbDataAdapter**オブジェクトの**FillSchema**メソッドを呼び出すと、最初の結果セットのスキーマ情報のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="f6b79-123">If the **FillSchema** method of the **OleDbDataAdapter** object is called for a command that returns multiple result sets, only the schema information from the first result set is returned.</span></span> <span data-ttu-id="f6b79-124">**OleDbDataAdapter**を使用して複数の結果セットのスキーマ情報を返す場合は、 **addwithkey**の**MissingSchemaAction**を指定し、 **Fill**を呼び出すときにスキーマ情報を取得することをお勧めします。b.</span><span class="sxs-lookup"><span data-stu-id="f6b79-124">When returning schema information for multiple result sets using the **OleDbDataAdapter**, it is recommended that you specify a **MissingSchemaAction** of **AddWithKey** and obtain the schema information when calling the **Fill** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6b79-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6b79-125">See also</span></span>

- [<span data-ttu-id="f6b79-126">DataAdapter と DataReader</span><span class="sxs-lookup"><span data-stu-id="f6b79-126">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="f6b79-127">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="f6b79-127">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)
- [<span data-ttu-id="f6b79-128">ADO.NET でのデータの取得および変更</span><span class="sxs-lookup"><span data-stu-id="f6b79-128">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="f6b79-129">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="f6b79-129">ADO.NET Overview</span></span>](ado-net-overview.md)
