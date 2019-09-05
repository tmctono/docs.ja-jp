---
title: クエリ式の構文例:グループ化
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d83d7c0-b3be-4c92-a630-25cd1285de31
ms.openlocfilehash: bbb41918e4d3637ff1e04275ad6151510dfa036b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249500"
---
# <a name="query-expression-syntax-examples-grouping"></a><span data-ttu-id="61b61-102">クエリ式の構文例:グループ化</span><span class="sxs-lookup"><span data-stu-id="61b61-102">Query Expression Syntax Examples: Grouping</span></span>
<span data-ttu-id="61b61-103">このトピックの例では、クエリ式の`GroupBy`構文を使用して、メソッドを使用して、 [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples)に対してクエリを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="61b61-103">The examples in this topic demonstrate how to use the `GroupBy` method to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="61b61-104">これらの例で使用されている、AdventureWorks Sales Model は、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルから作成されています。</span><span class="sxs-lookup"><span data-stu-id="61b61-104">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="61b61-105">このトピックの例では、次`using` / `Imports`のステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="61b61-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="61b61-106">例</span><span class="sxs-lookup"><span data-stu-id="61b61-106">Example</span></span>  
 <span data-ttu-id="61b61-107">次の例では、郵便番号でグループ化された `Address` オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="61b61-107">The following example returns `Address` objects grouped by postal code.</span></span> <span data-ttu-id="61b61-108">結果は匿名型に射影されます。</span><span class="sxs-lookup"><span data-stu-id="61b61-108">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3)]
 [!code-vb[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3)]  
  
## <a name="example"></a><span data-ttu-id="61b61-109">例</span><span class="sxs-lookup"><span data-stu-id="61b61-109">Example</span></span>  
 <span data-ttu-id="61b61-110">次の例では、`Contact` オブジェクトを、連絡先の姓の先頭文字でグループ化して返します。</span><span class="sxs-lookup"><span data-stu-id="61b61-110">The following example returns `Contact` objects grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="61b61-111">結果は姓の先頭文字で並べ替えられ、匿名型に射影されます。</span><span class="sxs-lookup"><span data-stu-id="61b61-111">The results are also sorted by the first letter of last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2)]
 [!code-vb[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2)]  
  
## <a name="example"></a><span data-ttu-id="61b61-112">例</span><span class="sxs-lookup"><span data-stu-id="61b61-112">Example</span></span>  
 <span data-ttu-id="61b61-113">次の例では、顧客 ID でグループ化された `SalesOrderHeader` オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="61b61-113">The following example returns `SalesOrderHeader` objects grouped by customer ID.</span></span> <span data-ttu-id="61b61-114">顧客ごとの販売数も返されます。</span><span class="sxs-lookup"><span data-stu-id="61b61-114">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount)]
 [!code-vb[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount)]  
  
## <a name="see-also"></a><span data-ttu-id="61b61-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="61b61-115">See also</span></span>

- [<span data-ttu-id="61b61-116">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="61b61-116">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
