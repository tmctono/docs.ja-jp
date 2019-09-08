---
title: 複数テーブルにまたがるクエリ (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6819a16f-8656-41af-a54d-dfec0cb66366
ms.openlocfilehash: 4ab8eb9988995b4a142b1c02e82476f45285c3b8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785616"
---
# <a name="cross-table-queries-linq-to-dataset"></a><span data-ttu-id="139e4-102">複数テーブルにまたがるクエリ (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="139e4-102">Cross-Table Queries (LINQ to DataSet)</span></span>
<span data-ttu-id="139e4-103">1つのテーブルに対してクエリを実行するだけでなく、LINQ to DataSet でクロステーブルクエリを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="139e4-103">In addition to querying a single table, you can also perform cross-table queries in LINQ to DataSet.</span></span> <span data-ttu-id="139e4-104">これを行うには、*結合*を使用します。</span><span class="sxs-lookup"><span data-stu-id="139e4-104">This is done by using a *join*.</span></span> <span data-ttu-id="139e4-105">結合とは、あるデータ ソース内のオブジェクトを、他方のデータ ソース内で共通の属性 (たとえば製品や連絡先 ID) を持つオブジェクトと関連付けることです。</span><span class="sxs-lookup"><span data-stu-id="139e4-105">A join is the association of objects in one data source with objects that share a common attribute in another data source, such as a product or contact ID.</span></span> <span data-ttu-id="139e4-106">オブジェクト指向プログラミングでは、それぞれのオブジェクトは別のオブジェクトを参照するメンバーを持つため、オブジェクト間のリレーションシップのナビゲーションは比較的簡単です。</span><span class="sxs-lookup"><span data-stu-id="139e4-106">In object-oriented programming, relationships between objects are relatively easy to navigate because each object has a member that references another object.</span></span> <span data-ttu-id="139e4-107">ただし、外部データベース テーブル内でのリレーションシップのナビゲーションは単純ではありません。</span><span class="sxs-lookup"><span data-stu-id="139e4-107">In external database tables, however, navigating relationships is not as straightforward.</span></span> <span data-ttu-id="139e4-108">データベース テーブルは、組み込みのリレーションシップを持ちません。</span><span class="sxs-lookup"><span data-stu-id="139e4-108">Database tables do not contain built-in relationships.</span></span> <span data-ttu-id="139e4-109">このようなケースでは、結合操作を使用して、互いのソースの要素を対応付けることができます。</span><span class="sxs-lookup"><span data-stu-id="139e4-109">In these cases, the join operation can be used to match elements from each source.</span></span> <span data-ttu-id="139e4-110">たとえば、製品情報と売上情報が 2 つのテーブルに格納されている場合、結合操作を使用して、同じ販売注文の売上情報と製品を対応付けることができます。</span><span class="sxs-lookup"><span data-stu-id="139e4-110">For example, given two tables that contain product information and sales information, you could use a join operation to match sales information and products for the same sales order.</span></span>  
  
 <span data-ttu-id="139e4-111">フレームワーク[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]には、とと<xref:System.Linq.Enumerable.GroupJoin%2A>いう<xref:System.Linq.Enumerable.Join%2A> 2 つの結合演算子が用意されています。</span><span class="sxs-lookup"><span data-stu-id="139e4-111">The [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] framework provides two join operators, <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A>.</span></span> <span data-ttu-id="139e4-112">これらの演算子は、*等結合*を実行します。つまり、2つのデータソースに一致する結合は、キーが等しい場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="139e4-112">These operators perform *equi-joins*: that is, joins that match two data sources only when their keys are equal.</span></span> <span data-ttu-id="139e4-113">これに対して、transact-sql では、 `equals` `less than`演算子など、以外の結合演算子もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="139e4-113">(By contrast, Transact-SQL supports join operators other than `equals`, such as the `less than` operator.)</span></span>  
  
 <span data-ttu-id="139e4-114">リレーショナル データベース用語では、<xref:System.Linq.Enumerable.Join%2A> は内部結合を実行します。</span><span class="sxs-lookup"><span data-stu-id="139e4-114">In relational database terms, <xref:System.Linq.Enumerable.Join%2A> implements an inner join.</span></span> <span data-ttu-id="139e4-115">内部結合とは、対応するデータセット内で一致するオブジェクトがあるオブジェクトのみが返される結合です。</span><span class="sxs-lookup"><span data-stu-id="139e4-115">An inner join is a type of join in which only those objects that have a match in the opposite data set are returned.</span></span>  
  
 <span data-ttu-id="139e4-116">これら<xref:System.Linq.Enumerable.GroupJoin%2A>の演算子は、リレーショナルデータベースの用語に直接相当するものではなく、内部結合と左外部結合のスーパーセットを実装します。</span><span class="sxs-lookup"><span data-stu-id="139e4-116">The <xref:System.Linq.Enumerable.GroupJoin%2A> operators have no direct equivalent in relational database terms; they implement a superset of inner joins and left outer joins.</span></span> <span data-ttu-id="139e4-117">左外部結合は、2番目のコレクションに相関要素がない場合でも、最初 (左側) のコレクションの各要素を返す結合です。</span><span class="sxs-lookup"><span data-stu-id="139e4-117">A left outer join is a join that returns each element of the first (left) collection, even if it has no correlated elements in the second collection.</span></span>  
  
 <span data-ttu-id="139e4-118">結合の詳細については、「 [Join 操作](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397908(v=vs.120))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="139e4-118">For more information about joins, see [Join Operations](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397908(v=vs.120)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="139e4-119">例</span><span class="sxs-lookup"><span data-stu-id="139e4-119">Example</span></span>  
 <span data-ttu-id="139e4-120">次の例では、AdventureWorks サンプル データベースの `SalesOrderHeader` テーブルと `SalesOrderDetail` テーブルを従来の方法で結合し、8 月以降のオンラインでの注文を取得します。</span><span class="sxs-lookup"><span data-stu-id="139e4-120">The following example performs a traditional join of the `SalesOrderHeader` and `SalesOrderDetail` tables from the AdventureWorks sample database to obtain online orders from the month of August.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a><span data-ttu-id="139e4-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="139e4-121">See also</span></span>

- [<span data-ttu-id="139e4-122">DataSet のクエリ</span><span class="sxs-lookup"><span data-stu-id="139e4-122">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="139e4-123">単一テーブルのクエリ</span><span class="sxs-lookup"><span data-stu-id="139e4-123">Single-Table Queries</span></span>](single-table-queries-linq-to-dataset.md)
- [<span data-ttu-id="139e4-124">型指定された DataSet のクエリ</span><span class="sxs-lookup"><span data-stu-id="139e4-124">Querying Typed DataSets</span></span>](querying-typed-datasets.md)
- <span data-ttu-id="139e4-125">[結合演算](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397908(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="139e4-125">[Join Operations](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397908(v=vs.120))</span></span>
- [<span data-ttu-id="139e4-126">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="139e4-126">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
