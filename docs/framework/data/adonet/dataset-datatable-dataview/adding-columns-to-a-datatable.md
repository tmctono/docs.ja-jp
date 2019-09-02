---
title: DataTable への列の追加
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
ms.openlocfilehash: 105537a5fccef6de7266407c78cc915f8c5d8678
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204060"
---
# <a name="adding-columns-to-a-datatable"></a><span data-ttu-id="81961-102">DataTable への列の追加</span><span class="sxs-lookup"><span data-stu-id="81961-102">Adding Columns to a DataTable</span></span>
<span data-ttu-id="81961-103">に<xref:System.Data.DataTable>は、テーブルの<xref:System.Data.DataColumn> **Columns**プロパティによって参照されるオブジェクトのコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="81961-103">A <xref:System.Data.DataTable> contains a collection of <xref:System.Data.DataColumn> objects referenced by the **Columns** property of the table.</span></span> <span data-ttu-id="81961-104">この列のコレクションと制約によって、テーブルのスキーマ (構造) が定義されます。</span><span class="sxs-lookup"><span data-stu-id="81961-104">This collection of columns, along with any constraints, defines the schema, or structure, of the table.</span></span>  
  
 <span data-ttu-id="81961-105">テーブル内に**datacolumn**オブジェクトを作成するには、 **datacolumn**コンストラクターを使用するか、テーブル<xref:System.Data.DataColumnCollection>の**Columns**プロパティの**Add**メソッド () を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="81961-105">You create **DataColumn** objects within a table by using the **DataColumn** constructor, or by calling the **Add** method of the **Columns** property of the table, which is a <xref:System.Data.DataColumnCollection>.</span></span> <span data-ttu-id="81961-106">**Add**メソッドは、オプションの**ColumnName**、 **DataType**、および**Expression**引数を受け取り、コレクションのメンバーとして新しい**DataColumn**を作成します。</span><span class="sxs-lookup"><span data-stu-id="81961-106">The **Add** method accepts optional **ColumnName**, **DataType**, and **Expression** arguments and creates a new **DataColumn** as a member of the collection.</span></span> <span data-ttu-id="81961-107">また、既存の**datacolumn**オブジェクトを受け取り、それをコレクションに追加し、要求された場合は追加された**datacolumn**への参照を返します。</span><span class="sxs-lookup"><span data-stu-id="81961-107">It also accepts an existing **DataColumn** object and adds it to the collection, and returns a reference to the added **DataColumn** if requested.</span></span> <span data-ttu-id="81961-108">**DataTable**オブジェクトはどのデータソースにも固有ではないため、 **DataColumn**のデータ型を指定するときに .NET Framework 型が使用されます。</span><span class="sxs-lookup"><span data-stu-id="81961-108">Because **DataTable** objects are not specific to any data source, .NET Framework types are used when specifying the data type of a **DataColumn**.</span></span>  
  
 <span data-ttu-id="81961-109">次の例では、 **DataTable**に4つの列を追加します。</span><span class="sxs-lookup"><span data-stu-id="81961-109">The following example adds four columns to a **DataTable**.</span></span>  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
  
Dim workCol As DataColumn = workTable.Columns.Add( _  
    "CustID", Type.GetType("System.Int32"))  
workCol.AllowDBNull = false  
workCol.Unique = true  
  
workTable.Columns.Add("CustLName", Type.GetType("System.String"))  
workTable.Columns.Add("CustFName", Type.GetType("System.String"))  
workTable.Columns.Add("Purchases", Type.GetType("System.Double"))  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
  
DataColumn workCol = workTable.Columns.Add("CustID", typeof(Int32));  
workCol.AllowDBNull = false;  
workCol.Unique = true;  
  
workTable.Columns.Add("CustLName", typeof(String));  
workTable.Columns.Add("CustFName", typeof(String));  
workTable.Columns.Add("Purchases", typeof(Double));  
```  
  
 <span data-ttu-id="81961-110">この例では、 **CustID**列のプロパティが**DBNull**値を許可しないように設定されていて、値が一意になるように制約されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="81961-110">In the example, notice that the properties for the **CustID** column are set to not allow **DBNull** values and to constrain values to be unique.</span></span> <span data-ttu-id="81961-111">ただし、 **CustID**列をテーブルの主キー列として定義すると、 **allowdbnull**プロパティが自動的に**false**に設定され、 **Unique**プロパティが自動的に**true**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="81961-111">However, if you define the **CustID** column as the primary key column of the table, the **AllowDBNull** property will automatically be set to **false** and the **Unique** property will automatically be set to **true**.</span></span> <span data-ttu-id="81961-112">詳細については、「[主キーの定義](defining-primary-keys.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81961-112">For more information, see [Defining Primary Keys](defining-primary-keys.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="81961-113">列名が列に指定されていない場合、列には、 **DataColumnCollection**に追加されると、"Column1" で始まる列*N*の増分既定名が指定されます。</span><span class="sxs-lookup"><span data-stu-id="81961-113">If a column name is not supplied for a column, the column is given an incremental default name of Column*N,* starting with "Column1", when it is added to the **DataColumnCollection**.</span></span> <span data-ttu-id="81961-114">列名を指定するときは、"Column*N*" の命名規則を使用しないことをお勧めします。これは、指定した名前が**DataColumnCollection**内の既存の既定の列名と競合する可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="81961-114">We recommend that you avoid the naming convention of "Column*N*" when you supply a column name, because the name you supply may conflict with an existing default column name in the **DataColumnCollection**.</span></span> <span data-ttu-id="81961-115">指定した名前が既に存在する場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="81961-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="81961-116"><xref:System.Xml.Linq.XElement> を、<xref:System.Data.DataColumn.DataType%2A> 内の <xref:System.Data.DataColumn> の <xref:System.Data.DataTable> として使用すると、データを読み取るときに XML シリアル化が機能しません。</span><span class="sxs-lookup"><span data-stu-id="81961-116">If you are using <xref:System.Xml.Linq.XElement> as the <xref:System.Data.DataColumn.DataType%2A> of a <xref:System.Data.DataColumn> in the <xref:System.Data.DataTable>, XML serialization will not work when you read in data.</span></span> <span data-ttu-id="81961-117">たとえば、<xref:System.Xml.XmlDocument> メソッドを使用して `DataTable.WriteXml` を書き込むと、XML へのシリアル化で <xref:System.Xml.Linq.XElement> に親ノードが追加されます。</span><span class="sxs-lookup"><span data-stu-id="81961-117">For example, if you write out a <xref:System.Xml.XmlDocument> by using the `DataTable.WriteXml` method, upon serialization to XML there is an additional parent node in the <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="81961-118">この問題に対処するには、<xref:System.Data.SqlTypes.SqlXml> の代わりに <xref:System.Xml.Linq.XElement> 型を使用します。</span><span class="sxs-lookup"><span data-stu-id="81961-118">To work around this problem, use the <xref:System.Data.SqlTypes.SqlXml> type instead of <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="81961-119">`ReadXml` および `WriteXml` は、<xref:System.Data.SqlTypes.SqlXml> で適切に機能します。</span><span class="sxs-lookup"><span data-stu-id="81961-119">`ReadXml` and `WriteXml` work correctly with <xref:System.Data.SqlTypes.SqlXml>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81961-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="81961-120">See also</span></span>

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="81961-121">DataTable スキーマの定義</span><span class="sxs-lookup"><span data-stu-id="81961-121">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="81961-122">DataTables</span><span class="sxs-lookup"><span data-stu-id="81961-122">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="81961-123">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="81961-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
