---
title: DataTable への列の追加
description: DataTable には、テーブルの Columns プロパティによって参照される DataColumn オブジェクトが格納されます。 次のコード例を使用して、ADO.NET のテーブルに列を追加します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
ms.openlocfilehash: 9d6d21696acd7a6b63cfd6d2ea7e906ec2acd7c9
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286948"
---
# <a name="adding-columns-to-a-datatable"></a><span data-ttu-id="103c0-104">DataTable への列の追加</span><span class="sxs-lookup"><span data-stu-id="103c0-104">Adding Columns to a DataTable</span></span>
<span data-ttu-id="103c0-105"><xref:System.Data.DataTable> には、テーブルの **Columns** プロパティによって参照される <xref:System.Data.DataColumn> オブジェクトのコレクションが格納されます。</span><span class="sxs-lookup"><span data-stu-id="103c0-105">A <xref:System.Data.DataTable> contains a collection of <xref:System.Data.DataColumn> objects referenced by the **Columns** property of the table.</span></span> <span data-ttu-id="103c0-106">この列のコレクションと制約によって、テーブルのスキーマ (構造) が定義されます。</span><span class="sxs-lookup"><span data-stu-id="103c0-106">This collection of columns, along with any constraints, defines the schema, or structure, of the table.</span></span>  
  
 <span data-ttu-id="103c0-107">テーブル内に **DataColumn** オブジェクトを作成するには、**DataColumn** コンストラクターを使用するか、または <xref:System.Data.DataColumnCollection> であるテーブルの **Columns** プロパティの **Add** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="103c0-107">You create **DataColumn** objects within a table by using the **DataColumn** constructor, or by calling the **Add** method of the **Columns** property of the table, which is a <xref:System.Data.DataColumnCollection>.</span></span> <span data-ttu-id="103c0-108">**Add** メソッドは、オプションの **ColumnName**、**DataType**、**Expression** の各引数を受け取り、新しい **DataColumn** をコレクションのメンバーとして作成します。</span><span class="sxs-lookup"><span data-stu-id="103c0-108">The **Add** method accepts optional **ColumnName**, **DataType**, and **Expression** arguments and creates a new **DataColumn** as a member of the collection.</span></span> <span data-ttu-id="103c0-109">また、このメソッドは既存の **DataColumn** オブジェクトを受け取り、それをコレクションに追加して、要求された場合は、追加された **DataColumn** への参照を返します。</span><span class="sxs-lookup"><span data-stu-id="103c0-109">It also accepts an existing **DataColumn** object and adds it to the collection, and returns a reference to the added **DataColumn** if requested.</span></span> <span data-ttu-id="103c0-110">**DataTable** オブジェクトはデータ ソースに固有ではないため、**DataColumn** のデータ型を指定するときには、.NET Framework 型が使用されます。</span><span class="sxs-lookup"><span data-stu-id="103c0-110">Because **DataTable** objects are not specific to any data source, .NET Framework types are used when specifying the data type of a **DataColumn**.</span></span>  
  
 <span data-ttu-id="103c0-111">**DataTable** に 4 つの列を追加する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="103c0-111">The following example adds four columns to a **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="103c0-112">この例では、**DBNull** 値を許可せずに値を一意の値に制約するように、**CustID** 列のプロパティが設定されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="103c0-112">In the example, notice that the properties for the **CustID** column are set to not allow **DBNull** values and to constrain values to be unique.</span></span> <span data-ttu-id="103c0-113">ただし、**CustID** 列をテーブルの主キー列として定義した場合、**AllowDBNull** プロパティは自動的に **false** に設定され、**Unique** プロパティは自動的に **true** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="103c0-113">However, if you define the **CustID** column as the primary key column of the table, the **AllowDBNull** property will automatically be set to **false** and the **Unique** property will automatically be set to **true**.</span></span> <span data-ttu-id="103c0-114">詳しくは、「[主キーの定義](defining-primary-keys.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="103c0-114">For more information, see [Defining Primary Keys](defining-primary-keys.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="103c0-115">列名が指定されていない列を **DataColumnCollection** に追加する場合、この列には "Column1" から始まって増分される既定名 Column*N* が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="103c0-115">If a column name is not supplied for a column, the column is given an incremental default name of Column*N,* starting with "Column1", when it is added to the **DataColumnCollection**.</span></span> <span data-ttu-id="103c0-116">列名を指定するときには、"Column*N*" の命名規則を使用しないことをお勧めします。これは、指定した名前が **DataColumnCollection** に既に存在する既定の列名と競合しないようにするためです。</span><span class="sxs-lookup"><span data-stu-id="103c0-116">We recommend that you avoid the naming convention of "Column*N*" when you supply a column name, because the name you supply may conflict with an existing default column name in the **DataColumnCollection**.</span></span> <span data-ttu-id="103c0-117">指定した名前が既に存在する場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="103c0-117">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="103c0-118"><xref:System.Xml.Linq.XElement> を、<xref:System.Data.DataColumn.DataType%2A> 内の <xref:System.Data.DataColumn> の <xref:System.Data.DataTable> として使用すると、データを読み取るときに XML シリアル化が機能しません。</span><span class="sxs-lookup"><span data-stu-id="103c0-118">If you are using <xref:System.Xml.Linq.XElement> as the <xref:System.Data.DataColumn.DataType%2A> of a <xref:System.Data.DataColumn> in the <xref:System.Data.DataTable>, XML serialization will not work when you read in data.</span></span> <span data-ttu-id="103c0-119">たとえば、<xref:System.Xml.XmlDocument> メソッドを使用して `DataTable.WriteXml` を書き込むと、XML へのシリアル化で <xref:System.Xml.Linq.XElement> に親ノードが追加されます。</span><span class="sxs-lookup"><span data-stu-id="103c0-119">For example, if you write out a <xref:System.Xml.XmlDocument> by using the `DataTable.WriteXml` method, upon serialization to XML there is an additional parent node in the <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="103c0-120">この問題に対処するには、<xref:System.Data.SqlTypes.SqlXml> の代わりに <xref:System.Xml.Linq.XElement> 型を使用します。</span><span class="sxs-lookup"><span data-stu-id="103c0-120">To work around this problem, use the <xref:System.Data.SqlTypes.SqlXml> type instead of <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="103c0-121">`ReadXml` および `WriteXml` は、<xref:System.Data.SqlTypes.SqlXml> で適切に機能します。</span><span class="sxs-lookup"><span data-stu-id="103c0-121">`ReadXml` and `WriteXml` work correctly with <xref:System.Data.SqlTypes.SqlXml>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="103c0-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="103c0-122">See also</span></span>

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="103c0-123">DataTable スキーマの定義</span><span class="sxs-lookup"><span data-stu-id="103c0-123">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="103c0-124">DataTables</span><span class="sxs-lookup"><span data-stu-id="103c0-124">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="103c0-125">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="103c0-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
