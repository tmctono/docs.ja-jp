---
title: DataSet への DataTable の追加
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 556d29a3-8fc9-4e38-b3ee-c188f7e7b155
ms.openlocfilehash: a1249718d1e1e1e64fd6fa6ee9ee8157545b5e0b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786635"
---
# <a name="adding-a-datatable-to-a-dataset"></a><span data-ttu-id="07b04-102">DataSet への DataTable の追加</span><span class="sxs-lookup"><span data-stu-id="07b04-102">Adding a DataTable to a DataSet</span></span>
<span data-ttu-id="07b04-103">ADO.NET を使用して <xref:System.Data.DataTable> オブジェクトを作成し、そのオブジェクトを既存の <xref:System.Data.DataSet> に追加できます。</span><span class="sxs-lookup"><span data-stu-id="07b04-103">ADO.NET enables you to create <xref:System.Data.DataTable> objects and add them to an existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="07b04-104"><xref:System.Data.DataTable> プロパティと <xref:System.Data.DataTable.PrimaryKey%2A> プロパティを使用することで、<xref:System.Data.DataColumn.Unique%2A> の制約情報を設定できます。</span><span class="sxs-lookup"><span data-stu-id="07b04-104">You can set constraint information for a <xref:System.Data.DataTable> by using the <xref:System.Data.DataTable.PrimaryKey%2A> and <xref:System.Data.DataColumn.Unique%2A> properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07b04-105">例</span><span class="sxs-lookup"><span data-stu-id="07b04-105">Example</span></span>  
 <span data-ttu-id="07b04-106"><xref:System.Data.DataSet> を構築し、<xref:System.Data.DataTable> に新しい <xref:System.Data.DataSet> オブジェクトを追加してから、3 つの <xref:System.Data.DataColumn> オブジェクトをそのテーブルに追加する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="07b04-106">The following example constructs a <xref:System.Data.DataSet>, adds a new <xref:System.Data.DataTable> object to the <xref:System.Data.DataSet>, and then adds three <xref:System.Data.DataColumn> objects to the table.</span></span> <span data-ttu-id="07b04-107">コードの最後では、1 つの列が主キーの列として設定されています。</span><span class="sxs-lookup"><span data-stu-id="07b04-107">Finally, the code sets one column as the primary key column.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/VB/source.vb#1)]  
  
## <a name="case-sensitivity"></a><span data-ttu-id="07b04-108">大文字と小文字の区別</span><span class="sxs-lookup"><span data-stu-id="07b04-108">Case Sensitivity</span></span>  
 <span data-ttu-id="07b04-109">大文字と小文字の区別が異なれば、<xref:System.Data.DataSet> に存在する 2 つ以上のテーブルまたはリレーションが同じ名前を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="07b04-109">Two or more tables or relations with the same name, but different casing, can exist in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="07b04-110">この場合、名前を使用してテーブルとリレーションを参照する際に大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="07b04-110">In such cases, references by name to tables and relations are case sensitive.</span></span> <span data-ttu-id="07b04-111">たとえば、**データセット**に<xref:System.Data.DataSet> **table1**と**table1**のテーブルが含まれている場合、 **table1**を名前で dataset として参照します。 **tables ["table1"]** , **table1** as **dataset. tables ["table1"]** となります。</span><span class="sxs-lookup"><span data-stu-id="07b04-111">For example, if the <xref:System.Data.DataSet> **dataSet** contains tables **Table1** and **table1**, you would reference **Table1** by name as **dataSet.Tables["Table1"]**, and **table1** as **dataSet.Tables["table1"]**.</span></span> <span data-ttu-id="07b04-112">テーブルのいずれかを DataSet として参照しようとして**います。テーブル ["TABLE1"]** は例外を生成します。</span><span class="sxs-lookup"><span data-stu-id="07b04-112">Attempting to reference either of the tables as **dataSet.Tables["TABLE1"]** would generate an exception.</span></span>  
  
 <span data-ttu-id="07b04-113">特定の名前を持つテーブルまたはリレーションが 1 つのみの場合、大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="07b04-113">The case-sensitivity behavior does not apply if only one table or relation has a particular name.</span></span> <span data-ttu-id="07b04-114">たとえば、に<xref:System.Data.DataSet> **Table1**しかない場合、データセットを使用して参照でき**ます。 Tables ["Table1"]** を使用します。</span><span class="sxs-lookup"><span data-stu-id="07b04-114">For example, if the <xref:System.Data.DataSet> has only **Table1**, you can reference it using **dataSet.Tables["TABLE1"]**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="07b04-115">この動作は <xref:System.Data.DataSet.CaseSensitive%2A> の <xref:System.Data.DataSet> プロパティの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="07b04-115">The <xref:System.Data.DataSet.CaseSensitive%2A> property of the <xref:System.Data.DataSet> does not affect this behavior.</span></span> <span data-ttu-id="07b04-116"><xref:System.Data.DataSet.CaseSensitive%2A> プロパティは、<xref:System.Data.DataSet> 内のデータに適用され、並べ替え、検索、フィルター処理、制約の適用などに影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="07b04-116">The <xref:System.Data.DataSet.CaseSensitive%2A> property applies to the data in the <xref:System.Data.DataSet> and affects sorting, searching, filtering, enforcing constraints, and so on.</span></span>  
  
## <a name="namespace-support"></a><span data-ttu-id="07b04-117">名前空間のサポート</span><span class="sxs-lookup"><span data-stu-id="07b04-117">Namespace Support</span></span>  
 <span data-ttu-id="07b04-118">2\.0 より前のバージョンの ADO.NET では、異なる名前空間に存在しているテーブルであっても、2 つのテーブルが同じ名前を持つことはできませんでした。</span><span class="sxs-lookup"><span data-stu-id="07b04-118">In versions of ADO.NET earlier than 2.0, two tables could not have the same name, even if they were in different namespaces.</span></span> <span data-ttu-id="07b04-119">ADO.NET 2.0 には、この制限はありません。</span><span class="sxs-lookup"><span data-stu-id="07b04-119">This limitation was removed in ADO.NET 2.0.</span></span> <span data-ttu-id="07b04-120">したがって、<xref:System.Data.DataSet> に、<xref:System.Data.DataTable.TableName%2A> プロパティ値が異なり、<xref:System.Data.DataTable.Namespace%2A> プロパティ値が一致する 2 つのテーブルが存在しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="07b04-120">A <xref:System.Data.DataSet> can contain two tables that have the same <xref:System.Data.DataTable.TableName%2A> property value but different <xref:System.Data.DataTable.Namespace%2A> property values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07b04-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="07b04-121">See also</span></span>

- [<span data-ttu-id="07b04-122">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="07b04-122">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="07b04-123">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="07b04-123">ADO.NET Overview</span></span>](../ado-net-overview.md)
