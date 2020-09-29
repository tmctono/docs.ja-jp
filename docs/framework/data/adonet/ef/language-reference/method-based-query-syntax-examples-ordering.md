---
title: メソッド ベースのクエリ構文例:順序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5d21b178-d731-471a-8534-1f8184a2ef06
ms.openlocfilehash: 02889fb4172d24634cdcb1c8384a804b2ce1a0e8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191932"
---
# <a name="method-based-query-syntax-examples-ordering"></a><span data-ttu-id="3f3dd-102">メソッド ベースのクエリ構文例:順序</span><span class="sxs-lookup"><span data-stu-id="3f3dd-102">Method-Based Query Syntax Examples: Ordering</span></span>

<span data-ttu-id="3f3dd-103">このトピックでは、メソッド ベースのクエリ構文で、<xref:System.Linq.Enumerable.ThenBy%2A> メソッドを使用して、[AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) を照会する例を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="3f3dd-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ThenBy%2A> method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="3f3dd-104">これらの例で使用されている、AdventureWorks Sales Model は、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルから作成されています。</span><span class="sxs-lookup"><span data-stu-id="3f3dd-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="3f3dd-105">このトピックの例には、次の `using`/`Imports` ステートメントが使用されています。</span><span class="sxs-lookup"><span data-stu-id="3f3dd-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="thenby"></a><span data-ttu-id="3f3dd-106">ThenBy</span><span class="sxs-lookup"><span data-stu-id="3f3dd-106">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="3f3dd-107">例</span><span class="sxs-lookup"><span data-stu-id="3f3dd-107">Example</span></span>  

 <span data-ttu-id="3f3dd-108">次の例では、メソッド ベースのクエリ構文で <xref:System.Linq.Queryable.OrderBy%2A> と <xref:System.Linq.Queryable.ThenBy%2A> を使用し、姓の順、次に名の順に並べ替えられた連絡先の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="3f3dd-108">The following example in method-based query syntax uses <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenBy%2A> to return a list of contacts ordered by last name and then by first name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby_mq)]
 [!code-vb[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby_mq)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="3f3dd-109">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="3f3dd-109">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="3f3dd-110">例</span><span class="sxs-lookup"><span data-stu-id="3f3dd-110">Example</span></span>  

 <span data-ttu-id="3f3dd-111">次の例では、<xref:System.Linq.Queryable.OrderBy%2A> メソッドおよび <xref:System.Linq.Queryable.ThenByDescending%2A> メソッドを使用し、最初に表示価格で並べ替えた後、製品名の降順で並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="3f3dd-111">The following example uses the <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenByDescending%2A> methods to first sort by list price, and then perform a descending sort of the product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescending_mq)]
 [!code-vb[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescending_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="3f3dd-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f3dd-112">See also</span></span>

- [<span data-ttu-id="3f3dd-113">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="3f3dd-113">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
