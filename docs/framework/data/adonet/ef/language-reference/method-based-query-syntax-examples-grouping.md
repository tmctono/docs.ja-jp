---
title: メソッド ベースのクエリ構文例:グループ化
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb23c25c-1075-4cc3-a8ff-4db72e536c0d
ms.openlocfilehash: 8f09983aa90be666cc13ae4eba018db2ae706daa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760598"
---
# <a name="method-based-query-syntax-examples-grouping"></a><span data-ttu-id="cdee0-102">メソッド ベースのクエリ構文例:グループ化</span><span class="sxs-lookup"><span data-stu-id="cdee0-102">Method-Based Query Syntax Examples: Grouping</span></span>
<span data-ttu-id="cdee0-103">このトピックの例では、使用する方法を表示、`GroupBy`メソッド クエリを[AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples)メソッド ベースのクエリ構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="cdee0-103">The examples in this topic show you how to use the `GroupBy` method to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="cdee0-104">これらの例で使用されている、AdventureWorks Sales Model は、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルから作成されています。</span><span class="sxs-lookup"><span data-stu-id="cdee0-104">The AdventureWorks Sales Model that is used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="cdee0-105">このトピックの例では、次を使用して`using` / `Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="cdee0-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="cdee0-106">例</span><span class="sxs-lookup"><span data-stu-id="cdee0-106">Example</span></span>  
 <span data-ttu-id="cdee0-107">次の例では、`GroupBy` メソッドを使用して、郵便番号でグループ化されている `Address` オブジェクトを返しています。</span><span class="sxs-lookup"><span data-stu-id="cdee0-107">The following example uses the `GroupBy` method to return `Address` objects that are grouped by postal code.</span></span> <span data-ttu-id="cdee0-108">結果は匿名型に射影されます。</span><span class="sxs-lookup"><span data-stu-id="cdee0-108">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3_mq)]  
  
## <a name="example"></a><span data-ttu-id="cdee0-109">例</span><span class="sxs-lookup"><span data-stu-id="cdee0-109">Example</span></span>  
 <span data-ttu-id="cdee0-110">次の例では、`GroupBy` メソッドを使用して、連絡先の姓の先頭文字でグループ化した `Contact` オブジェクトを返しています。</span><span class="sxs-lookup"><span data-stu-id="cdee0-110">The following example uses the `GroupBy` method to return `Contact` objects that are grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="cdee0-111">結果は姓の先頭文字で並べ替えられ、匿名型に投影されます。</span><span class="sxs-lookup"><span data-stu-id="cdee0-111">The results are also sorted by the first letter of the last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2_mq)]  
  
## <a name="example"></a><span data-ttu-id="cdee0-112">例</span><span class="sxs-lookup"><span data-stu-id="cdee0-112">Example</span></span>  
 <span data-ttu-id="cdee0-113">次の例では、`GroupBy` メソッドを使用して、顧客 ID でグループ化されている `SalesOrderHeader` オブジェクトを返しています。</span><span class="sxs-lookup"><span data-stu-id="cdee0-113">The following example uses the `GroupBy` method to return `SalesOrderHeader` objects that are grouped by customer ID.</span></span> <span data-ttu-id="cdee0-114">顧客ごとの販売数も返されます。</span><span class="sxs-lookup"><span data-stu-id="cdee0-114">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount_mq)]
 [!code-vb[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="cdee0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="cdee0-115">See also</span></span>

- [<span data-ttu-id="cdee0-116">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="cdee0-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
