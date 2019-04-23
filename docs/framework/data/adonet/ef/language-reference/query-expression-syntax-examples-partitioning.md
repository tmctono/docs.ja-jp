---
title: クエリ式の構文例:パーティション分割
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e41aed0-3be9-4f75-98de-860a85552a3c
ms.openlocfilehash: e205a50b70a29d056af23ba64eb630b50e304ecb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165283"
---
# <a name="query-expression-syntax-examples-partitioning"></a><span data-ttu-id="26ce2-102">クエリ式の構文例:パーティション分割</span><span class="sxs-lookup"><span data-stu-id="26ce2-102">Query Expression Syntax Examples: Partitioning</span></span>
<span data-ttu-id="26ce2-103">このトピックの例では、使用する方法を示します、<xref:System.Linq.Enumerable.Skip%2A>と<xref:System.Linq.Enumerable.Take%2A>を照会する方法、 [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples)クエリ式構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="26ce2-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="26ce2-104">これらの例で使用されている、AdventureWorks Sales Model は、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルから作成されています。</span><span class="sxs-lookup"><span data-stu-id="26ce2-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="26ce2-105">このトピックの例では、次を使用して`using` / `Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="26ce2-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="skip"></a><span data-ttu-id="26ce2-106">Skip</span><span class="sxs-lookup"><span data-stu-id="26ce2-106">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="26ce2-107">例</span><span class="sxs-lookup"><span data-stu-id="26ce2-107">Example</span></span>  
 <span data-ttu-id="26ce2-108">次の例では、Seattle から最初の 2 つを除くすべての住所を、<xref:System.Linq.Enumerable.Skip%2A> メソッドを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="26ce2-108">The following example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#SkipNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP L2E Examples#SkipNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipnested)]  
  
## <a name="take"></a><span data-ttu-id="26ce2-109">Take</span><span class="sxs-lookup"><span data-stu-id="26ce2-109">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="26ce2-110">例</span><span class="sxs-lookup"><span data-stu-id="26ce2-110">Example</span></span>  
 <span data-ttu-id="26ce2-111">次の例では、Seattle から最初の 3 つの住所を、<xref:System.Linq.Enumerable.Take%2A> メソッドを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="26ce2-111">The following example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#TakeNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takenested)]
 [!code-vb[DP L2E Examples#TakeNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takenested)]  
  
## <a name="see-also"></a><span data-ttu-id="26ce2-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="26ce2-112">See also</span></span>

- [<span data-ttu-id="26ce2-113">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="26ce2-113">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
