---
title: DataAdapter DataTable と DataColumn のマップ
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 6380dd0512bd7834f50b87f90f445cb01b7a8b95
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151560"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a><span data-ttu-id="c0d98-102">DataAdapter DataTable と DataColumn のマップ</span><span class="sxs-lookup"><span data-stu-id="c0d98-102">DataAdapter DataTable and DataColumn Mappings</span></span>
<span data-ttu-id="c0d98-103">**データ アダプター**には、その<xref:System.Data.Common.DataTableMapping>**TableMappings**プロパティに 0 個以上のオブジェクトのコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c0d98-103">A **DataAdapter** contains a collection of zero or more <xref:System.Data.Common.DataTableMapping> objects in its **TableMappings** property.</span></span> <span data-ttu-id="c0d98-104">**DataTableMapping**は、クエリから返されたデータとデータ ソースとの間のマスター マッピング<xref:System.Data.DataTable>を提供します。</span><span class="sxs-lookup"><span data-stu-id="c0d98-104">A **DataTableMapping** provides a master mapping between the data returned from a query against a data source, and a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="c0d98-105">**名前**は **、データ**テーブル名の代わりにデータ**アダプター**の**Fill**メソッドに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="c0d98-105">The **DataTableMapping** name can be passed in place of the **DataTable** name to the **Fill** method of the **DataAdapter**.</span></span> <span data-ttu-id="c0d98-106">次の例では、Authors テーブルの**AuthorsMapping**という名前の**データテーブル**マッピングを**作成**します。</span><span class="sxs-lookup"><span data-stu-id="c0d98-106">The following example creates a **DataTableMapping** named **AuthorsMapping** for the **Authors** table.</span></span>  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 <span data-ttu-id="c0d98-107">**データ テーブル マッピング**を使用すると、データベース内の列とは異なる列名をデータ**テーブル**で使用できます。</span><span class="sxs-lookup"><span data-stu-id="c0d98-107">A **DataTableMapping** enables you to use column names in a **DataTable** that are different from those in the database.</span></span> <span data-ttu-id="c0d98-108">**DataAdapter は**、テーブルが更新されたときに、列を一致させるためにマッピングを使用します。</span><span class="sxs-lookup"><span data-stu-id="c0d98-108">The **DataAdapter** uses the mapping to match the columns when the table is updated.</span></span>  
  
 <span data-ttu-id="c0d98-109">**データアダプタ**の**Fill**メソッドまたは**Update**メソッドを呼び出すときに**テーブル名**または**データ テーブル マッピング**名を指定しない場合、**データアダプター**は "テーブル" という名前の**データ テーブル マッピング**を検索します。</span><span class="sxs-lookup"><span data-stu-id="c0d98-109">If you do not specify a **TableName** or a **DataTableMapping** name when calling the **Fill** or **Update** method of the **DataAdapter**, the **DataAdapter** looks for a **DataTableMapping** named "Table".</span></span> <span data-ttu-id="c0d98-110">その**データ テーブル マッピング**が存在しない場合、データ**テーブル**の**テーブル名**は "テーブル" です。</span><span class="sxs-lookup"><span data-stu-id="c0d98-110">If that **DataTableMapping** does not exist, the **TableName** of the **DataTable** is "Table".</span></span> <span data-ttu-id="c0d98-111">"テーブル" という名前の**データ**テーブル**マッピング**を作成することで、既定のデータ テーブル マッピングを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c0d98-111">You can specify a default **DataTableMapping** by creating a **DataTableMapping** with the name of "Table".</span></span>  
  
 <span data-ttu-id="c0d98-112">次のコード例では、<xref:System.Data.Common>名前空間から**DataTableMapping**を作成し、"テーブル" という名前を付けて指定した**DataAdapter**の既定のマッピングにします。</span><span class="sxs-lookup"><span data-stu-id="c0d98-112">The following code example creates a **DataTableMapping** (from the <xref:System.Data.Common> namespace) and makes it the default mapping for the specified **DataAdapter** by naming it "Table".</span></span> <span data-ttu-id="c0d98-113">次に、クエリ結果の最初のテーブル **(Northwind**データベースの**Customers**テーブル) の列を、 の**Northwind Customers**テーブル内のわかりやすい名前のセット<xref:System.Data.DataSet>にマップします。</span><span class="sxs-lookup"><span data-stu-id="c0d98-113">The example then maps the columns from the first table in the query result (the **Customers** table of the **Northwind** database) to a set of more user-friendly names in the **Northwind Customers** table in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="c0d98-114">割り当てられない列には、データ ソースの列名が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c0d98-114">For columns that are not mapped, the name of the column from the data source is used.</span></span>  
  
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
  
 <span data-ttu-id="c0d98-115">より高度な状況では、同じ**DataAdapter**で異なるマッピングを持つ異なるテーブルの読み込みをサポートするように設定できます。</span><span class="sxs-lookup"><span data-stu-id="c0d98-115">In more advanced situations, you may decide that you want the same **DataAdapter** to support loading different tables with different mappings.</span></span> <span data-ttu-id="c0d98-116">これを行うには、単に追加**のデータテーブルマッピングオブジェクトを**追加します。</span><span class="sxs-lookup"><span data-stu-id="c0d98-116">To do this, simply add additional **DataTableMapping** objects.</span></span>  
  
 <span data-ttu-id="c0d98-117">**Fill**メソッドに**DataSet**のインスタンスと**DataTableMapping**名が渡されると、その名前のマッピングが使用されます。それ以外の場合は、その名前の**DataTable**が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c0d98-117">When the **Fill** method is passed an instance of a **DataSet** and a **DataTableMapping** name, if a mapping with that name exists it is used; otherwise, a **DataTable** with that name is used.</span></span>  
  
 <span data-ttu-id="c0d98-118">次の例では、**顧客**の名前と**BizTalkSchema**の**データ テーブル**名を使用してデータ テーブル**マッピング**を作成します。</span><span class="sxs-lookup"><span data-stu-id="c0d98-118">The following examples create a **DataTableMapping** with a name of **Customers** and a **DataTable** name of **BizTalkSchema**.</span></span> <span data-ttu-id="c0d98-119">次に、SELECT ステートメントによって返された行を**BizTalk スキーマ\*\*\*\*データ テーブル**にマップします。</span><span class="sxs-lookup"><span data-stu-id="c0d98-119">The example then maps the rows returned by the SELECT statement to the **BizTalkSchema** **DataTable**.</span></span>  
  
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
> <span data-ttu-id="c0d98-120">列マップにソースの列名を指定しなかった場合、またはテーブル マップにソース テーブル名を指定しなかった場合は、自動的に既定の名前が生成されます。</span><span class="sxs-lookup"><span data-stu-id="c0d98-120">If a source column name is not supplied for a column mapping or a source table name is not supplied for a table mapping, default names will be automatically generated.</span></span> <span data-ttu-id="c0d98-121">列マッピングにソース列が指定されていない場合、列マッピングには、ソース**列 1**から始まる増分デフォルト名の**SourceColumn** *N*が付けられます。</span><span class="sxs-lookup"><span data-stu-id="c0d98-121">If no source column is supplied for a column mapping, the column mapping is given an incremental default name of **SourceColumn** *N,* starting with **SourceColumn1**.</span></span> <span data-ttu-id="c0d98-122">テーブル マッピングにソース テーブル名が指定されていない場合、テーブル マッピングには **、SourceTable** *N*の増分デフォルト名が**SourceTable1**から始まります。</span><span class="sxs-lookup"><span data-stu-id="c0d98-122">If no source table name is supplied for a table mapping, the table mapping is given an incremental default name of **SourceTable** *N*, starting with **SourceTable1**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c0d98-123">指定する名前は**ColumnMappingCollection**の既存の既定の列マッピング名または**DataTableMappingCollection**のテーブル マッピング名と競合する可能性があるため、列マッピングの場合は**SourceColumn** *N、* テーブル マッピングの**SourceTable** *N*という名前付け規則を使用しないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c0d98-123">We recommend that you avoid the naming convention of **SourceColumn** *N* for a column mapping, or **SourceTable** *N* for a table mapping, because the name you supply may conflict with an existing default column mapping name in the **ColumnMappingCollection** or table mapping name in the **DataTableMappingCollection**.</span></span> <span data-ttu-id="c0d98-124">指定した名前が既に存在する場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c0d98-124">If the supplied name already exists, an exception will be thrown.</span></span>  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="c0d98-125">複数の結果セットの処理</span><span class="sxs-lookup"><span data-stu-id="c0d98-125">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="c0d98-126">**SelectCommand が**複数のテーブルを返す場合 **、Fill**は指定されたテーブル名から始まり、TableNameN という形式で**続\*\**N*く**DataSet**のテーブルの増分値を持**TableName1\*\*つテーブル名を自動的に生成します。</span><span class="sxs-lookup"><span data-stu-id="c0d98-126">If your **SelectCommand** returns multiple tables, **Fill** automatically generates table names with incremental values for the tables in the **DataSet**, starting with the specified table name and continuing on in the form **TableName** *N*, starting with **TableName1**.</span></span> <span data-ttu-id="c0d98-127">テーブル マッピングを使用して、自動的に生成されたテーブル名を**DataSet**内のテーブルに指定する名前にマップできます。</span><span class="sxs-lookup"><span data-stu-id="c0d98-127">You can use table mappings to map the automatically generated table name to a name you want specified for the table in the **DataSet**.</span></span> <span data-ttu-id="c0d98-128">たとえば **、"得意先"** と **"受注"** という 2 つのテーブルを返す**SelectCommand**の場合は、次の呼び出しを**Fill**に発行します。</span><span class="sxs-lookup"><span data-stu-id="c0d98-128">For example, for a **SelectCommand** that returns two tables, **Customers** and **Orders**, issue the following call to **Fill**.</span></span>  
  
```vb  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.Fill(customersDataSet, "Customers");  
```  

 <span data-ttu-id="c0d98-129">2 つのテーブルが**データセット**に作成されます:**顧客**と**得意先1**。</span><span class="sxs-lookup"><span data-stu-id="c0d98-129">Two tables are created in the **DataSet**: **Customers** and **Customers1**.</span></span> <span data-ttu-id="c0d98-130">テーブル マッピングを使用して、2 番目のテーブルが**Customers1**ではなく**Orders**という名前であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c0d98-130">You can use table mappings to ensure that the second table is named **Orders** instead of **Customers1**.</span></span> <span data-ttu-id="c0d98-131">これを行うには、次の例に示すように **、Customers1**のソース テーブルを**DataSet**テーブル**Orders**にマップします。</span><span class="sxs-lookup"><span data-stu-id="c0d98-131">To do this, map the source table of **Customers1** to the **DataSet** table **Orders**, as shown in the following example.</span></span>  
  
```vb  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.TableMappings.Add("Customers1", "Orders");  
adapter.Fill(customersDataSet, "Customers");  
```
  
## <a name="see-also"></a><span data-ttu-id="c0d98-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0d98-132">See also</span></span>

- [<span data-ttu-id="c0d98-133">DataAdapter と DataReader</span><span class="sxs-lookup"><span data-stu-id="c0d98-133">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="c0d98-134">ADO.NET でのデータの取得および変更</span><span class="sxs-lookup"><span data-stu-id="c0d98-134">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="c0d98-135">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="c0d98-135">ADO.NET Overview</span></span>](ado-net-overview.md)
