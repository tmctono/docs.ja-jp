---
title: DataAdapter DataTable と DataColumn のマップ
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: eb6841dd24c4c7587cc2424cc1e606194da34585
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944063"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a><span data-ttu-id="78505-102">DataAdapter DataTable と DataColumn のマップ</span><span class="sxs-lookup"><span data-stu-id="78505-102">DataAdapter DataTable and DataColumn Mappings</span></span>
<span data-ttu-id="78505-103">**DataAdapter**には、その**TableMappings**プロパティ内の<xref:System.Data.Common.DataTableMapping> 0 個以上のオブジェクトのコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="78505-103">A **DataAdapter** contains a collection of zero or more <xref:System.Data.Common.DataTableMapping> objects in its **TableMappings** property.</span></span> <span data-ttu-id="78505-104">**DataTableMapping**は、データソースに対するクエリから返されたデータとの<xref:System.Data.DataTable>間のマスターマッピングを提供します。</span><span class="sxs-lookup"><span data-stu-id="78505-104">A **DataTableMapping** provides a master mapping between the data returned from a query against a data source, and a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="78505-105">**DataTableMapping**名は、 **DataAdapter**の**Fill**メソッドに**DataTable**名の代わりに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="78505-105">The **DataTableMapping** name can be passed in place of the **DataTable** name to the **Fill** method of the **DataAdapter**.</span></span> <span data-ttu-id="78505-106">次の例では 、 **authorsmapping**という名前の**Authors**テーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="78505-106">The following example creates a **DataTableMapping** named **AuthorsMapping** for the **Authors** table.</span></span>  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 <span data-ttu-id="78505-107">**DataTableMapping**を使用すると、データベース内の列名とは異なる列名を**DataTable**で使用できます。</span><span class="sxs-lookup"><span data-stu-id="78505-107">A **DataTableMapping** enables you to use column names in a **DataTable** that are different from those in the database.</span></span> <span data-ttu-id="78505-108">**DataAdapter**は、テーブルが更新されたときに、マッピングを使用して列を照合します。</span><span class="sxs-lookup"><span data-stu-id="78505-108">The **DataAdapter** uses the mapping to match the columns when the table is updated.</span></span>  
  
 <span data-ttu-id="78505-109">**Dataadapter**の**Fill**または**Update**メソッドを呼び出すときに**TableName**または**DataTableMapping**名を指定しない場合、 **dataadapter**は "Table" という名前の**DataTableMapping**を検索します。</span><span class="sxs-lookup"><span data-stu-id="78505-109">If you do not specify a **TableName** or a **DataTableMapping** name when calling the **Fill** or **Update** method of the **DataAdapter**, the **DataAdapter** looks for a **DataTableMapping** named "Table".</span></span> <span data-ttu-id="78505-110">この**DataTableMapping**が存在しない場合、 **DataTable**の**TableName**は "Table" になります。</span><span class="sxs-lookup"><span data-stu-id="78505-110">If that **DataTableMapping** does not exist, the **TableName** of the **DataTable** is "Table".</span></span> <span data-ttu-id="78505-111">既定の**DataTableMapping**を指定するには、"Table" という名前の**DataTableMapping**を作成します。</span><span class="sxs-lookup"><span data-stu-id="78505-111">You can specify a default **DataTableMapping** by creating a **DataTableMapping** with the name of "Table".</span></span>  
  
 <span data-ttu-id="78505-112">次のコード例では 、( <xref:System.Data.Common>名前空間から) DataTableMapping を作成し、"Table" という名前を付けて、指定した**DataAdapter**の既定のマッピングにします。</span><span class="sxs-lookup"><span data-stu-id="78505-112">The following code example creates a **DataTableMapping** (from the <xref:System.Data.Common> namespace) and makes it the default mapping for the specified **DataAdapter** by naming it "Table".</span></span> <span data-ttu-id="78505-113">この例では、クエリ結果の最初のテーブル ( **northwind**データベースの**Customers**テーブル) の列を、の<xref:System.Data.DataSet> **northwind Customers**テーブルのユーザーフレンドリ名のセットにマップします。</span><span class="sxs-lookup"><span data-stu-id="78505-113">The example then maps the columns from the first table in the query result (the **Customers** table of the **Northwind** database) to a set of more user-friendly names in the **Northwind Customers** table in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="78505-114">割り当てられない列には、データ ソースの列名が使用されます。</span><span class="sxs-lookup"><span data-stu-id="78505-114">For columns that are not mapped, the name of the column from the data source is used.</span></span>  
  
```vb  
Dim mapping As DataTableMapping = _  
  adapter.TableMappings.Add("Table", "NorthwindCustomers")  
mapping.ColumnMappings.Add("CompanyName", "Company")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode")  
  
adapter.Fill(custDS)  
```  
  
```csharp  
DataTableMapping mapping =   
  adapter.TableMappings.Add("Table", "NorthwindCustomers");  
mapping.ColumnMappings.Add("CompanyName", "Company");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode");  
  
adapter.Fill(custDS);  
```  
  
 <span data-ttu-id="78505-115">より高度な状況では、同じ**DataAdapter**で異なるマッピングを持つ異なるテーブルの読み込みをサポートするように設定できます。</span><span class="sxs-lookup"><span data-stu-id="78505-115">In more advanced situations, you may decide that you want the same **DataAdapter** to support loading different tables with different mappings.</span></span> <span data-ttu-id="78505-116">これを行うには、単に追加の**DataTableMapping**オブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="78505-116">To do this, simply add additional **DataTableMapping** objects.</span></span>  
  
 <span data-ttu-id="78505-117">**Fill**メソッドに**DataSet**のインスタンスと**DataTableMapping**名が渡されたときに、その名前を持つマッピングが存在する場合は、その名前が使用されます。それ以外の場合は、その名前の**DataTable**が使用されます。</span><span class="sxs-lookup"><span data-stu-id="78505-117">When the **Fill** method is passed an instance of a **DataSet** and a **DataTableMapping** name, if a mapping with that name exists it is used; otherwise, a **DataTable** with that name is used.</span></span>  
  
 <span data-ttu-id="78505-118">次の例では、 **customers**という名前の**DataTableMapping**と、**スキーマ**の**DataTable**名を作成します。</span><span class="sxs-lookup"><span data-stu-id="78505-118">The following examples create a **DataTableMapping** with a name of **Customers** and a **DataTable** name of **BizTalkSchema**.</span></span> <span data-ttu-id="78505-119">次に、SELECT ステートメントによって返された行を 、**データテーブル**にマップします。</span><span class="sxs-lookup"><span data-stu-id="78505-119">The example then maps the rows returned by the SELECT statement to the **BizTalkSchema** **DataTable**.</span></span>  
  
```vb  
Dim mapping As ITableMapping = _  
  adapter.TableMappings.Add("Customers", "BizTalkSchema")  
mapping.ColumnMappings.Add("CustomerID", "ClientID")  
mapping.ColumnMappings.Add("CompanyName", "ClientName")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIP")  
  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
ITableMapping mapping =   
  adapter.TableMappings.Add("Customers", "BizTalkSchema");  
mapping.ColumnMappings.Add("CustomerID", "ClientID");  
mapping.ColumnMappings.Add("CompanyName", "ClientName");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIP");  
  
adapter.Fill(custDS, "Customers");  
```  
  
> [!NOTE]
> <span data-ttu-id="78505-120">列マップにソースの列名を指定しなかった場合、またはテーブル マップにソース テーブル名を指定しなかった場合は、自動的に既定の名前が生成されます。</span><span class="sxs-lookup"><span data-stu-id="78505-120">If a source column name is not supplied for a column mapping or a source table name is not supplied for a table mapping, default names will be automatically generated.</span></span> <span data-ttu-id="78505-121">列マッピングにソース列が指定されていない場合、列マッピングには**SourceColumn1**で始まる**SourceColumn** *N*という増分の既定の名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="78505-121">If no source column is supplied for a column mapping, the column mapping is given an incremental default name of **SourceColumn** *N,* starting with **SourceColumn1**.</span></span> <span data-ttu-id="78505-122">テーブルマッピングにソーステーブル名が指定されていない場合、テーブルマッピングには、 **SourceTable1**で始まる**SourceTable** *N*という増分の既定の名前が与えられます。</span><span class="sxs-lookup"><span data-stu-id="78505-122">If no source table name is supplied for a table mapping, the table mapping is given an incremental default name of **SourceTable** *N*, starting with **SourceTable1**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="78505-123">列マッピングの場合は、 **SourceColumn** *n*の名前付け規則を使用しないことをお勧めします。また、指定した名前がの **既存の既定の列マッピング名と競合する可能性があるため、テーブルマッピングの場合は SourceTable n を使用することをお勧めします。使用の ColumnMappingCollection**またはテーブルマッピング名。</span><span class="sxs-lookup"><span data-stu-id="78505-123">We recommend that you avoid the naming convention of **SourceColumn** *N* for a column mapping, or **SourceTable** *N* for a table mapping, because the name you supply may conflict with an existing default column mapping name in the **ColumnMappingCollection** or table mapping name in the **DataTableMappingCollection**.</span></span> <span data-ttu-id="78505-124">指定した名前が既に存在する場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="78505-124">If the supplied name already exists, an exception will be thrown.</span></span>  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="78505-125">複数の結果セットの処理</span><span class="sxs-lookup"><span data-stu-id="78505-125">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="78505-126">**SelectCommand**が複数のテーブルを返す場合、 **Fill**は、**データセット**内のテーブルの増分値を使用してテーブル名を自動的に生成します。指定されたテーブル名から始まり、その後に**TableName**という形式で続きます。*N*、 **TableName1**で始まります。</span><span class="sxs-lookup"><span data-stu-id="78505-126">If your **SelectCommand** returns multiple tables, **Fill** automatically generates table names with incremental values for the tables in the **DataSet**, starting with the specified table name and continuing on in the form **TableName** *N*, starting with **TableName1**.</span></span> <span data-ttu-id="78505-127">テーブルマッピングを使用すると、自動的に生成されたテーブル名を、**データセット**内のテーブルに対して指定した名前にマップできます。</span><span class="sxs-lookup"><span data-stu-id="78505-127">You can use table mappings to map the automatically generated table name to a name you want specified for the table in the **DataSet**.</span></span> <span data-ttu-id="78505-128">たとえば、 **Customers**および**Orders**という2つのテーブルを返す**SelectCommand**の場合、 **Fill**の次の呼び出しを発行します。</span><span class="sxs-lookup"><span data-stu-id="78505-128">For example, for a **SelectCommand** that returns two tables, **Customers** and **Orders**, issue the following call to **Fill**.</span></span>  
  
```  
adapter.Fill(customersDataSet, "Customers")  
```  
  
 <span data-ttu-id="78505-129">**データセット**には、次の2つのテーブルが作成されます。**お客様**と**Customers1**。</span><span class="sxs-lookup"><span data-stu-id="78505-129">Two tables are created in the **DataSet**: **Customers** and **Customers1**.</span></span> <span data-ttu-id="78505-130">テーブルマッピングを使用すると、2番目のテーブルに**Customers1**の代わりに**Orders**という名前が付けられるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="78505-130">You can use table mappings to ensure that the second table is named **Orders** instead of **Customers1**.</span></span> <span data-ttu-id="78505-131">これを行うには、次の例に示すように、 **Customers1**のソーステーブルを**データセット**テーブルの**Orders**にマップします。</span><span class="sxs-lookup"><span data-stu-id="78505-131">To do this, map the source table of **Customers1** to the **DataSet** table **Orders**, as shown in the following example.</span></span>  
  
```  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  
  
## <a name="see-also"></a><span data-ttu-id="78505-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="78505-132">See also</span></span>

- [<span data-ttu-id="78505-133">DataAdapter と DataReader</span><span class="sxs-lookup"><span data-stu-id="78505-133">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="78505-134">ADO.NET でのデータの取得および変更</span><span class="sxs-lookup"><span data-stu-id="78505-134">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="78505-135">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="78505-135">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
