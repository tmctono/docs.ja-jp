---
title: メソッド ベースのクエリ構文例:要素演算子
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
ms.openlocfilehash: 96d393a34af69935e75582ef1954ddd661a355f0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192049"
---
# <a name="method-based-query-syntax-examples-element-operators"></a><span data-ttu-id="cd576-102">メソッド ベースのクエリ構文例:要素演算子</span><span class="sxs-lookup"><span data-stu-id="cd576-102">Method-Based Query Syntax Examples: Element Operators</span></span>

<span data-ttu-id="cd576-103">このトピックでは、メソッド ベースのクエリ構文で、<xref:System.Linq.Enumerable.First%2A> メソッドを使用して、[AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) を照会する例を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="cd576-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="cd576-104">これらの例で使用されている、AdventureWorks Sales Model は、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルから作成されています。</span><span class="sxs-lookup"><span data-stu-id="cd576-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="cd576-105">このトピックの例には、次の `using`/`Imports` ステートメントが使用されています。</span><span class="sxs-lookup"><span data-stu-id="cd576-105">The example in this topic uses the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="cd576-106">First</span><span class="sxs-lookup"><span data-stu-id="cd576-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="cd576-107">例</span><span class="sxs-lookup"><span data-stu-id="cd576-107">Example</span></span>  

 <span data-ttu-id="cd576-108">次の例では、<xref:System.Linq.Enumerable.First%2A> メソッドを使用して、'caroline' で始まる最初の電子メール アドレスを検索します。</span><span class="sxs-lookup"><span data-stu-id="cd576-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to find the first email address that starts with 'caroline'.</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="cd576-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd576-109">See also</span></span>

- [<span data-ttu-id="cd576-110">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="cd576-110">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
