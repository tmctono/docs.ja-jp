---
title: メソッド ベースのクエリ構文例:結合演算子
description: これらの例を活用することにより、Join メソッドと GroupJoin メソッドを使用して、LINQ to Entities のメソッドベースのクエリ構文でモデルに対してクエリを実行する方法を学習できます。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d00f0efa-9084-4c17-843f-54904fcb4204
ms.openlocfilehash: 7f02379f4ececb75981ab262f22ebdeb510739ed
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191959"
---
# <a name="method-based-query-syntax-examples-join-operators"></a><span data-ttu-id="384a1-103">メソッド ベースのクエリ構文例:結合演算子</span><span class="sxs-lookup"><span data-stu-id="384a1-103">Method-Based Query Syntax Examples: Join Operators</span></span>

<span data-ttu-id="384a1-104">このトピックでは、メソッド ベースのクエリ構文で、<xref:System.Linq.Enumerable.Join%2A> メソッドと <xref:System.Linq.Enumerable.GroupJoin%2A> メソッドを使用して、[AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) を照会する例を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="384a1-104">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="384a1-105">これらの例で使用されている、AdventureWorks Sales Model は、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルから作成されています。</span><span class="sxs-lookup"><span data-stu-id="384a1-105">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="384a1-106">このトピックの例には、次の `using`/`Imports` ステートメントが使用されています。</span><span class="sxs-lookup"><span data-stu-id="384a1-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="384a1-107">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="384a1-107">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="384a1-108">例</span><span class="sxs-lookup"><span data-stu-id="384a1-108">Example</span></span>  

 <span data-ttu-id="384a1-109">次の例では、SalesOrderHeader テーブルおよび SalesOrderDetail テーブルに対して <xref:System.Linq.Enumerable.GroupJoin%2A> を実行することによって、顧客ごとの注文数を調べます。</span><span class="sxs-lookup"><span data-stu-id="384a1-109">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="384a1-110">GroupJoin は、左外部結合に相当します。つまり、1 つ目 (左側) のデータ ソースに存在するすべての要素は、関連する要素がもう一方のデータ ソースに存在するかどうかに関係なく返されます。</span><span class="sxs-lookup"><span data-stu-id="384a1-110">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2_mq)]
 [!code-vb[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2_mq)]  
  
### <a name="example"></a><span data-ttu-id="384a1-111">例</span><span class="sxs-lookup"><span data-stu-id="384a1-111">Example</span></span>  

 <span data-ttu-id="384a1-112">次の例では、Contact テーブルおよび SalesOrderHeader テーブルに対して <xref:System.Linq.Enumerable.GroupJoin%2A> を実行して、連絡先ごとの注文数を調べます。</span><span class="sxs-lookup"><span data-stu-id="384a1-112">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="384a1-113">各連絡先の注文数と ID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="384a1-113">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin_mq)]
 [!code-vb[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin_mq)]  
  
## <a name="join"></a><span data-ttu-id="384a1-114">Join</span><span class="sxs-lookup"><span data-stu-id="384a1-114">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="384a1-115">例</span><span class="sxs-lookup"><span data-stu-id="384a1-115">Example</span></span>  

 <span data-ttu-id="384a1-116">次の例では、Contact テーブルと SalesOrderHeader テーブルの結合を実行します。</span><span class="sxs-lookup"><span data-stu-id="384a1-116">The following example performs a join over the Contact and SalesOrderHeader tables.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a><span data-ttu-id="384a1-117">例</span><span class="sxs-lookup"><span data-stu-id="384a1-117">Example</span></span>  

 <span data-ttu-id="384a1-118">次の例では、Contact テーブルと SalesOrderHeader テーブルを結合し、結果を連絡先 ID でグループ化します。</span><span class="sxs-lookup"><span data-stu-id="384a1-118">The following example performs a join over the Contact and SalesOrderHeader tables, grouping the results by contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="384a1-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="384a1-119">See also</span></span>

- [<span data-ttu-id="384a1-120">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="384a1-120">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
