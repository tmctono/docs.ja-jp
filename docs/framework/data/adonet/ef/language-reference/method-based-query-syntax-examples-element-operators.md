---
title: メソッド ベースのクエリ構文例:要素演算子
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
ms.openlocfilehash: 7add62a2792a0fc82346851b7dd835aad5082742
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397461"
---
# <a name="method-based-query-syntax-examples-element-operators"></a><span data-ttu-id="17fdf-102">メソッド ベースのクエリ構文例:要素演算子</span><span class="sxs-lookup"><span data-stu-id="17fdf-102">Method-Based Query Syntax Examples: Element Operators</span></span>
<span data-ttu-id="17fdf-103">このトピックの例では、メソッドを使用<xref:System.Linq.Enumerable.First%2A>してメソッドベースのクエリ構文を使用し、 [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)を照会する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="17fdf-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="17fdf-104">これらの例で使用されている、AdventureWorks Sales Model は、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルから作成されています。</span><span class="sxs-lookup"><span data-stu-id="17fdf-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="17fdf-105">このトピックの例では、次`using` / `Imports`のステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="17fdf-105">The example in this topic uses the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="17fdf-106">First</span><span class="sxs-lookup"><span data-stu-id="17fdf-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="17fdf-107">例</span><span class="sxs-lookup"><span data-stu-id="17fdf-107">Example</span></span>  
 <span data-ttu-id="17fdf-108">次の例では<xref:System.Linq.Enumerable.First%2A> 、メソッドを使用して、"caroline" で始まる最初の電子メールアドレスを検索します。</span><span class="sxs-lookup"><span data-stu-id="17fdf-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to find the first email address that starts with 'caroline'.</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="17fdf-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="17fdf-109">See also</span></span>

- [<span data-ttu-id="17fdf-110">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="17fdf-110">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
