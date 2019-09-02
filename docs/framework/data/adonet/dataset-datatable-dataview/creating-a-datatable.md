---
title: DataTable の作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: 64ba7a8e6bd6361e14d1f16576e377575b088bbe
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205142"
---
# <a name="creating-a-datatable"></a><span data-ttu-id="69c84-102">DataTable の作成</span><span class="sxs-lookup"><span data-stu-id="69c84-102">Creating a DataTable</span></span>
<span data-ttu-id="69c84-103"><xref:System.Data.DataTable> は 1 つのインメモリ リレーショナル データのテーブルを表します。DataTable は単独で作成および使用することも、他の .NET Framework オブジェクトから <xref:System.Data.DataSet> のメンバーとして使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="69c84-103">A <xref:System.Data.DataTable>, which represents one table of in-memory relational data, can be created and used independently, or can be used by other .NET Framework objects, most commonly as a member of a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="69c84-104">**Datatable**オブジェクトを作成するには、適切な**datatable**コンストラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="69c84-104">You can create a **DataTable** object by using the appropriate **DataTable** constructor.</span></span> <span data-ttu-id="69c84-105">これを**DataSet**に追加するには、 **add**メソッドを使用してそれを**DataTable**オブジェクトの**Tables**コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="69c84-105">You can add it to the **DataSet** by using the **Add** method to add it to the **DataTable** object's **Tables** collection.</span></span>  
  
 <span data-ttu-id="69c84-106">**データセット**内に**DataTable**オブジェクトを作成するには、 **DataAdapter**オブジェクトの**Fill**メソッドまたは**FillSchema**メソッドを使用するか、または、 **ReadXml**, readxmlschema を使用して、定義済みまたは推論された XML スキーマから作成することもできます。**データセット**の、、または**InferXmlSchema**メソッド。</span><span class="sxs-lookup"><span data-stu-id="69c84-106">You can also create **DataTable** objects within a **DataSet** by using the **Fill** or **FillSchema** methods of the **DataAdapter** object, or from a predefined or inferred XML schema using the **ReadXml**, **ReadXmlSchema**, or **InferXmlSchema** methods of the **DataSet**.</span></span> <span data-ttu-id="69c84-107">DataTable を1つの**データセット**の**tables**コレクションのメンバーとして追加した後は、その**DataTable**を他の**データセット**のテーブルのコレクションに追加することはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="69c84-107">Note that after you have added a **DataTable** as a member of the **Tables** collection of one **DataSet**, you cannot add it to the collection of tables of any other **DataSet**.</span></span>  
  
 <span data-ttu-id="69c84-108">最初に**DataTable**を作成するときには、スキーマ (つまり構造体) はありません。</span><span class="sxs-lookup"><span data-stu-id="69c84-108">When you first create a **DataTable**, it does not have a schema (that is, a structure).</span></span> <span data-ttu-id="69c84-109">テーブルのスキーマを定義するには、テーブルの**Columns**コレクション<xref:System.Data.DataColumn>にオブジェクトを作成し、追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69c84-109">To define the schema of the table, you must create and add <xref:System.Data.DataColumn> objects to the **Columns** collection of the table.</span></span> <span data-ttu-id="69c84-110">テーブルの主キー列を定義し、テーブルの**制約**コレクションに**制約**オブジェクトを作成して追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="69c84-110">You can also define a primary key column for the table, and create and add **Constraint** objects to the **Constraints** collection of the table.</span></span> <span data-ttu-id="69c84-111">**DataTable**のスキーマを定義した後は、 **DataRow**オブジェクトをテーブルの**rows**コレクションに追加することによって、データ行をテーブルに追加できます。</span><span class="sxs-lookup"><span data-stu-id="69c84-111">After you have defined the schema for a **DataTable**, you can add rows of data to the table by adding **DataRow** objects to the **Rows** collection of the table.</span></span>  
  
 <span data-ttu-id="69c84-112"><xref:System.Data.DataTable.TableName%2A> **DataTable**を作成するときにプロパティの値を指定する必要はありません。プロパティを別の時点で指定することも、空のままにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="69c84-112">You are not required to supply a value for the <xref:System.Data.DataTable.TableName%2A> property when you create a **DataTable**; you can specify the property at another time, or you can leave it empty.</span></span> <span data-ttu-id="69c84-113">ただし、 **TableName**値を持たないテーブルを**データセット**に追加すると、テーブルには、Table0 の "Table" で始まるテーブル*N*の増分既定の名前が与えられます。</span><span class="sxs-lookup"><span data-stu-id="69c84-113">However, when you add a table without a **TableName** value to a **DataSet**, the table will be given an incremental default name of Table*N*, starting with "Table" for Table0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69c84-114">**TableName**値を指定するときは、"Table*N*" という名前付け規則を使用しないことをお勧めします。これは、指定した名前が**データセット**内の既存の既定のテーブル名と競合する可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="69c84-114">We recommend that you avoid the "Table*N*" naming convention when you supply a **TableName** value, because the name you supply may conflict with an existing default table name in the **DataSet**.</span></span> <span data-ttu-id="69c84-115">指定した名前が既に存在する場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="69c84-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="69c84-116">次の例では、 **DataTable**オブジェクトのインスタンスを作成し、"Customers" という名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="69c84-116">The following example creates an instance of a **DataTable** object and assigns it the name "Customers."</span></span>  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 <span data-ttu-id="69c84-117">次の例では、**データセット**の**Tables**コレクションに追加することによって、 **DataTable**のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="69c84-117">The following example creates an instance of a **DataTable** by adding it to the **Tables** collection of a **DataSet**.</span></span>  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a><span data-ttu-id="69c84-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="69c84-118">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataTableCollection>
- [<span data-ttu-id="69c84-119">DataTables</span><span class="sxs-lookup"><span data-stu-id="69c84-119">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="69c84-120">DataAdapter からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="69c84-120">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="69c84-121">XML からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="69c84-121">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="69c84-122">XML の DataSet スキーマ情報の読み込み</span><span class="sxs-lookup"><span data-stu-id="69c84-122">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="69c84-123">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="69c84-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
