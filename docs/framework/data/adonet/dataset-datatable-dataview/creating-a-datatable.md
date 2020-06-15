---
title: DataTable の作成
description: ADO.NET で DataTable を作成する方法について説明します。これは、インメモリ リレーショナル データの 1 つのテーブルを表し、単独で使用することも、他の .NET Framework オブジェクトで使用することもできます。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: 335137eeef02e590539c6d83e46cb39901a1e03f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286922"
---
# <a name="creating-a-datatable"></a><span data-ttu-id="0d716-103">DataTable の作成</span><span class="sxs-lookup"><span data-stu-id="0d716-103">Creating a DataTable</span></span>
<span data-ttu-id="0d716-104"><xref:System.Data.DataTable> は 1 つのインメモリ リレーショナル データのテーブルを表します。DataTable は単独で作成および使用することも、他の .NET Framework オブジェクトから <xref:System.Data.DataSet> のメンバーとして使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="0d716-104">A <xref:System.Data.DataTable>, which represents one table of in-memory relational data, can be created and used independently, or can be used by other .NET Framework objects, most commonly as a member of a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="0d716-105">**DataTable** オブジェクトは、適切な **DataTable** コンストラクターを使用することにより作成できます。</span><span class="sxs-lookup"><span data-stu-id="0d716-105">You can create a **DataTable** object by using the appropriate **DataTable** constructor.</span></span> <span data-ttu-id="0d716-106">このオブジェクトを **DataSet** に追加するには、**Add** メソッドを使用して、**DataTable** オブジェクトの **Tables** コレクションにオブジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="0d716-106">You can add it to the **DataSet** by using the **Add** method to add it to the **DataTable** object's **Tables** collection.</span></span>  
  
 <span data-ttu-id="0d716-107">**DataSet** 内に **DataTable** オブジェクトを作成する場合は、**DataAdapter** オブジェクトの **Fill** メソッドまたは **FillSchema** メソッドを使用するか、**DataSet** の **ReadXml**、**ReadXmlSchema**、または **InferXmlSchema** メソッドを使用して定義済みまたは推論による XML スキーマから作成することができます。</span><span class="sxs-lookup"><span data-stu-id="0d716-107">You can also create **DataTable** objects within a **DataSet** by using the **Fill** or **FillSchema** methods of the **DataAdapter** object, or from a predefined or inferred XML schema using the **ReadXml**, **ReadXmlSchema**, or **InferXmlSchema** methods of the **DataSet**.</span></span> <span data-ttu-id="0d716-108">ある **DataSet** の **Tables** コレクションのメンバーとして追加した **DataTable** を、その後で他の **DataSet** のテーブルのコレクションに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="0d716-108">Note that after you have added a **DataTable** as a member of the **Tables** collection of one **DataSet**, you cannot add it to the collection of tables of any other **DataSet**.</span></span>  
  
 <span data-ttu-id="0d716-109">最初に作成した時点では、**DataTable** にはスキーマ (構造) がありません。</span><span class="sxs-lookup"><span data-stu-id="0d716-109">When you first create a **DataTable**, it does not have a schema (that is, a structure).</span></span> <span data-ttu-id="0d716-110">テーブルのスキーマを定義するには、<xref:System.Data.DataColumn> オブジェクトを作成し、テーブルの **Columns** コレクションに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d716-110">To define the schema of the table, you must create and add <xref:System.Data.DataColumn> objects to the **Columns** collection of the table.</span></span> <span data-ttu-id="0d716-111">テーブルの主キー列を定義したり、**Constraint** オブジェクトを作成してテーブルの **Constraints** コレクションに追加したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0d716-111">You can also define a primary key column for the table, and create and add **Constraint** objects to the **Constraints** collection of the table.</span></span> <span data-ttu-id="0d716-112">**DataTable** のスキーマを定義した後で、**DataRow** オブジェクトをテーブルの **Rows** コレクションに追加することにより、データ行をテーブルに追加できます。</span><span class="sxs-lookup"><span data-stu-id="0d716-112">After you have defined the schema for a **DataTable**, you can add rows of data to the table by adding **DataRow** objects to the **Rows** collection of the table.</span></span>  
  
 <span data-ttu-id="0d716-113">**DataTable** を作成するときに <xref:System.Data.DataTable.TableName%2A> プロパティの値を指定する必要はありません。このプロパティは、後から指定することも、空のままにしておくこともできます。</span><span class="sxs-lookup"><span data-stu-id="0d716-113">You are not required to supply a value for the <xref:System.Data.DataTable.TableName%2A> property when you create a **DataTable**; you can specify the property at another time, or you can leave it empty.</span></span> <span data-ttu-id="0d716-114">ただし、**TableName** 値のないテーブルを **DataSet** に追加した場合、そのテーブルの名前は既定のテーブル名 Table*N* になります。この既定名は Table0 に相当する "Table" から始まり、連続する番号が割り当てられていきます。</span><span class="sxs-lookup"><span data-stu-id="0d716-114">However, when you add a table without a **TableName** value to a **DataSet**, the table will be given an incremental default name of Table*N*, starting with "Table" for Table0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0d716-115">**TableName** の値を指定するときは、"Table*N*" の命名規則を使用しないことをお勧めします。これは、指定した名前が **DataSet** に既に存在する既定のテーブル名と競合しないようにするためです。</span><span class="sxs-lookup"><span data-stu-id="0d716-115">We recommend that you avoid the "Table*N*" naming convention when you supply a **TableName** value, because the name you supply may conflict with an existing default table name in the **DataSet**.</span></span> <span data-ttu-id="0d716-116">指定した名前が既に存在する場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="0d716-116">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="0d716-117">次の例では、**DataTable** オブジェクトのインスタンスを作成し、"Customers" という名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0d716-117">The following example creates an instance of a **DataTable** object and assigns it the name "Customers."</span></span>  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 <span data-ttu-id="0d716-118">次の例では、**DataTable** のインスタンスを作成し、**DataSet** の **Tables** コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="0d716-118">The following example creates an instance of a **DataTable** by adding it to the **Tables** collection of a **DataSet**.</span></span>  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d716-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d716-119">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataTableCollection>
- [<span data-ttu-id="0d716-120">DataTables</span><span class="sxs-lookup"><span data-stu-id="0d716-120">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="0d716-121">DataAdapter からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="0d716-121">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="0d716-122">XML からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="0d716-122">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="0d716-123">XML の DataSet スキーマ情報の読み込み</span><span class="sxs-lookup"><span data-stu-id="0d716-123">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="0d716-124">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="0d716-124">ADO.NET Overview</span></span>](../ado-net-overview.md)
