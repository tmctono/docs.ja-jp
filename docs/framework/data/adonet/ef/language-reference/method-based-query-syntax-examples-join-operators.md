---
title: メソッド ベースのクエリ構文例:結合演算子
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d00f0efa-9084-4c17-843f-54904fcb4204
ms.openlocfilehash: 2f26f937901debd27cb936d1f642e0a5149b167a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250135"
---
# <a name="method-based-query-syntax-examples-join-operators"></a><span data-ttu-id="4b5cc-102">メソッド ベースのクエリ構文例:結合演算子</span><span class="sxs-lookup"><span data-stu-id="4b5cc-102">Method-Based Query Syntax Examples: Join Operators</span></span>
<span data-ttu-id="4b5cc-103">このトピックの例では、メソッドベースの<xref:System.Linq.Enumerable.Join%2A>クエリ<xref:System.Linq.Enumerable.GroupJoin%2A>構文を使用して、メソッドとメソッドを使用して、 [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples)に対してクエリを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4b5cc-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="4b5cc-104">これらの例で使用されている、AdventureWorks Sales Model は、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルから作成されています。</span><span class="sxs-lookup"><span data-stu-id="4b5cc-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="4b5cc-105">このトピックの例では、次`using` / `Imports`のステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b5cc-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="4b5cc-106">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="4b5cc-106">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="4b5cc-107">例</span><span class="sxs-lookup"><span data-stu-id="4b5cc-107">Example</span></span>  
 <span data-ttu-id="4b5cc-108">次の例では、SalesOrderHeader テーブルおよび SalesOrderDetail テーブルに対して <xref:System.Linq.Enumerable.GroupJoin%2A> を実行することによって、顧客ごとの注文数を調べます。</span><span class="sxs-lookup"><span data-stu-id="4b5cc-108">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="4b5cc-109">GroupJoin は、左外部結合に相当します。つまり、1 つ目 (左側) のデータ ソースに存在するすべての要素は、関連する要素がもう一方のデータ ソースに存在するかどうかに関係なく返されます。</span><span class="sxs-lookup"><span data-stu-id="4b5cc-109">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2_mq)]
 [!code-vb[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2_mq)]  
  
### <a name="example"></a><span data-ttu-id="4b5cc-110">例</span><span class="sxs-lookup"><span data-stu-id="4b5cc-110">Example</span></span>  
 <span data-ttu-id="4b5cc-111">次の例では、Contact テーブルおよび SalesOrderHeader テーブルに対して <xref:System.Linq.Enumerable.GroupJoin%2A> を実行して、連絡先ごとの注文数を調べます。</span><span class="sxs-lookup"><span data-stu-id="4b5cc-111">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="4b5cc-112">各連絡先の注文数と ID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b5cc-112">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin_mq)]
 [!code-vb[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin_mq)]  
  
## <a name="join"></a><span data-ttu-id="4b5cc-113">Join</span><span class="sxs-lookup"><span data-stu-id="4b5cc-113">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="4b5cc-114">例</span><span class="sxs-lookup"><span data-stu-id="4b5cc-114">Example</span></span>  
 <span data-ttu-id="4b5cc-115">次の例では、Contact テーブルと SalesOrderHeader テーブルの結合を実行します。</span><span class="sxs-lookup"><span data-stu-id="4b5cc-115">The following example performs a join over the Contact and SalesOrderHeader tables.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a><span data-ttu-id="4b5cc-116">例</span><span class="sxs-lookup"><span data-stu-id="4b5cc-116">Example</span></span>  
 <span data-ttu-id="4b5cc-117">次の例では、Contact テーブルと SalesOrderHeader テーブルを結合し、結果を連絡先 ID でグループ化します。</span><span class="sxs-lookup"><span data-stu-id="4b5cc-117">The following example performs a join over the Contact and SalesOrderHeader tables, grouping the results by contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="4b5cc-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b5cc-118">See also</span></span>

- [<span data-ttu-id="4b5cc-119">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="4b5cc-119">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
