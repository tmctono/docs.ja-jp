---
title: クエリ式の構文例:要素演算子
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 32268fe2-de18-4065-8060-f250def83837
ms.openlocfilehash: 5736828a629368a5b9abea9e63f7df2d2de3ca8d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249523"
---
# <a name="query-expression-syntax-examples-element-operators"></a><span data-ttu-id="53f0a-102">クエリ式の構文例:要素演算子</span><span class="sxs-lookup"><span data-stu-id="53f0a-102">Query Expression Syntax Examples: Element Operators</span></span>
<span data-ttu-id="53f0a-103">このトピックの例では、クエリ式の<xref:System.Linq.Enumerable.First%2A>構文を使用して、メソッドを使用して、 [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples)に対してクエリを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="53f0a-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using the query expression syntax.</span></span> <span data-ttu-id="53f0a-104">これらの例で使用されている、AdventureWorks Sales Model は、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルから作成されています。</span><span class="sxs-lookup"><span data-stu-id="53f0a-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="53f0a-105">このトピックの例では、次`using` / `Imports`のステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="53f0a-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="53f0a-106">First</span><span class="sxs-lookup"><span data-stu-id="53f0a-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="53f0a-107">例</span><span class="sxs-lookup"><span data-stu-id="53f0a-107">Example</span></span>  
 <span data-ttu-id="53f0a-108">次の例では、<xref:System.Linq.Enumerable.First%2A> メソッドを使用して、名が "Brooke" である最初の連絡先を取得します。</span><span class="sxs-lookup"><span data-stu-id="53f0a-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is "Brooke".</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="53f0a-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="53f0a-109">See also</span></span>

- [<span data-ttu-id="53f0a-110">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="53f0a-110">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
