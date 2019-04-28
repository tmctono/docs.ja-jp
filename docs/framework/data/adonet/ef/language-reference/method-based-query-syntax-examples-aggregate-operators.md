---
title: メソッド ベースのクエリ構文例:集計演算子
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0e306067-5720-4782-9719-2286570a7e47
ms.openlocfilehash: 06609ce14edeb7e9306816b8a8d58d2212b61751
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760611"
---
# <a name="method-based-query-syntax-examples-aggregate-operators"></a><span data-ttu-id="25761-102">メソッド ベースのクエリ構文例:集計演算子</span><span class="sxs-lookup"><span data-stu-id="25761-102">Method-Based Query Syntax Examples: Aggregate Operators</span></span>
<span data-ttu-id="25761-103">このトピックの例では、使用する方法を示します、 <xref:System.Linq.Enumerable.Aggregate%2A>、 <xref:System.Linq.Enumerable.Average%2A>、 <xref:System.Linq.Enumerable.Count%2A>、 <xref:System.Linq.Enumerable.LongCount%2A>、 <xref:System.Linq.Enumerable.Max%2A>、 <xref:System.Linq.Enumerable.Min%2A>、および<xref:System.Linq.Enumerable.Sum%2A>を照会する方法、 [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples)メソッド ベースのクエリ構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="25761-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="25761-104">これらの例で使用されている、AdventureWorks Sales Model は、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルから作成されています。</span><span class="sxs-lookup"><span data-stu-id="25761-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="25761-105">このトピックの例では、次を使用して`using` / `Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="25761-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="average"></a><span data-ttu-id="25761-106">平均</span><span class="sxs-lookup"><span data-stu-id="25761-106">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="25761-107">例</span><span class="sxs-lookup"><span data-stu-id="25761-107">Example</span></span>  
 <span data-ttu-id="25761-108">次の例では、<xref:System.Linq.Enumerable.Average%2A> メソッドを使用して、製品の平均表示価格を取得します。</span><span class="sxs-lookup"><span data-stu-id="25761-108">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average_mq)]
 [!code-vb[DP L2E Examples#Average_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average_mq)]  
  
### <a name="example"></a><span data-ttu-id="25761-109">例</span><span class="sxs-lookup"><span data-stu-id="25761-109">Example</span></span>  
 <span data-ttu-id="25761-110">次の例では、<xref:System.Linq.Enumerable.Average%2A> メソッドを使用して、各スタイルの製品の平均表示価格を取得します。</span><span class="sxs-lookup"><span data-stu-id="25761-110">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="25761-111">例</span><span class="sxs-lookup"><span data-stu-id="25761-111">Example</span></span>  
 <span data-ttu-id="25761-112">次の例では、<xref:System.Linq.Enumerable.Average%2A> メソッドを使用して、平均合計支払額を取得します。</span><span class="sxs-lookup"><span data-stu-id="25761-112">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average total due.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageprojection_mq)]
 [!code-vb[DP L2E Examples#AverageProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="25761-113">例</span><span class="sxs-lookup"><span data-stu-id="25761-113">Example</span></span>  
 <span data-ttu-id="25761-114">次の例では、<xref:System.Linq.Enumerable.Average%2A> メソッドを使用して、それぞれの連絡先 ID について平均合計支払額を取得します。</span><span class="sxs-lookup"><span data-stu-id="25761-114">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="25761-115">例</span><span class="sxs-lookup"><span data-stu-id="25761-115">Example</span></span>  
 <span data-ttu-id="25761-116">次の例では、<xref:System.Linq.Enumerable.Average%2A> メソッドを使用して、それぞれの連絡先について合計支払額が平均値の注文を取得します。</span><span class="sxs-lookup"><span data-stu-id="25761-116">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the orders with the average total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="25761-117">カウント</span><span class="sxs-lookup"><span data-stu-id="25761-117">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="25761-118">例</span><span class="sxs-lookup"><span data-stu-id="25761-118">Example</span></span>  
 <span data-ttu-id="25761-119">次の例では、<xref:System.Linq.Enumerable.Count%2A> メソッドを使用して、Product テーブル内の製品の数を返します。</span><span class="sxs-lookup"><span data-stu-id="25761-119">The following example uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in the Product table.</span></span>  
  
 [!code-csharp[DP L2E Examples#Count](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#count)]
 [!code-vb[DP L2E Examples#Count](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#count)]  
  
### <a name="example"></a><span data-ttu-id="25761-120">例</span><span class="sxs-lookup"><span data-stu-id="25761-120">Example</span></span>  
 <span data-ttu-id="25761-121">次の例では、<xref:System.Linq.Enumerable.Count%2A> メソッドを使用して、連絡先 ID の一覧と、それぞれの注文数を返します。</span><span class="sxs-lookup"><span data-stu-id="25761-121">The following example uses the <xref:System.Linq.Enumerable.Count%2A> method to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countnested)]
 [!code-vb[DP L2E Examples#CountNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="25761-122">例</span><span class="sxs-lookup"><span data-stu-id="25761-122">Example</span></span>  
 <span data-ttu-id="25761-123">次の例では、製品を色でグループ分けし、<xref:System.Linq.Enumerable.Count%2A> メソッドを使用してそれぞれの色グループに含まれる製品の数を返します。</span><span class="sxs-lookup"><span data-stu-id="25761-123">The following example groups products by color and uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="longcount"></a><span data-ttu-id="25761-124">LongCount</span><span class="sxs-lookup"><span data-stu-id="25761-124">LongCount</span></span>  
  
### <a name="example"></a><span data-ttu-id="25761-125">例</span><span class="sxs-lookup"><span data-stu-id="25761-125">Example</span></span>  
 <span data-ttu-id="25761-126">次の例では、連絡先の数を長整数として取得します。</span><span class="sxs-lookup"><span data-stu-id="25761-126">The following example gets the contact count as a long integer.</span></span>  
  
 [!code-csharp[DP L2E Examples#LongCountSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#longcountsimple)]
 [!code-vb[DP L2E Examples#LongCountSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#longcountsimple)]  
  
## <a name="max"></a><span data-ttu-id="25761-127">最大</span><span class="sxs-lookup"><span data-stu-id="25761-127">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="25761-128">例</span><span class="sxs-lookup"><span data-stu-id="25761-128">Example</span></span>  
 <span data-ttu-id="25761-129">次の例では、<xref:System.Linq.Enumerable.Max%2A> メソッドを使用して、最大合計支払額を取得します。</span><span class="sxs-lookup"><span data-stu-id="25761-129">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxprojection_mq)]
 [!code-vb[DP L2E Examples#MaxProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="25761-130">例</span><span class="sxs-lookup"><span data-stu-id="25761-130">Example</span></span>  
 <span data-ttu-id="25761-131">次の例では、<xref:System.Linq.Enumerable.Max%2A> メソッドを使用して、それぞれの連絡先 ID について最大合計支払額を取得します。</span><span class="sxs-lookup"><span data-stu-id="25761-131">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="25761-132">例</span><span class="sxs-lookup"><span data-stu-id="25761-132">Example</span></span>  
 <span data-ttu-id="25761-133">次の例では、<xref:System.Linq.Enumerable.Max%2A> メソッドを使用して、それぞれの連絡先 ID について合計支払額が最大の注文を取得します。</span><span class="sxs-lookup"><span data-stu-id="25761-133">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="25761-134">最小</span><span class="sxs-lookup"><span data-stu-id="25761-134">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="25761-135">例</span><span class="sxs-lookup"><span data-stu-id="25761-135">Example</span></span>  
 <span data-ttu-id="25761-136">次の例では、<xref:System.Linq.Enumerable.Min%2A> メソッドを使用して、最小合計支払額を取得します。</span><span class="sxs-lookup"><span data-stu-id="25761-136">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minprojection_mq)]
 [!code-vb[DP L2E Examples#MinProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="25761-137">例</span><span class="sxs-lookup"><span data-stu-id="25761-137">Example</span></span>  
 <span data-ttu-id="25761-138">次の例では、<xref:System.Linq.Enumerable.Min%2A> メソッドを使用して、それぞれの連絡先 ID について最小合計支払額を取得します。</span><span class="sxs-lookup"><span data-stu-id="25761-138">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="25761-139">例</span><span class="sxs-lookup"><span data-stu-id="25761-139">Example</span></span>  
 <span data-ttu-id="25761-140">次の例では、<xref:System.Linq.Enumerable.Min%2A> メソッドを使用して、それぞれの連絡先について合計支払額が最小の注文を取得します。</span><span class="sxs-lookup"><span data-stu-id="25761-140">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="25761-141">Sum</span><span class="sxs-lookup"><span data-stu-id="25761-141">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="25761-142">例</span><span class="sxs-lookup"><span data-stu-id="25761-142">Example</span></span>  
 <span data-ttu-id="25761-143">次の例では、<xref:System.Linq.Enumerable.Sum%2A> メソッドを使用して、SalesOrderDetail テーブル内の注文数量の合計を取得します。</span><span class="sxs-lookup"><span data-stu-id="25761-143">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total number of order quantities in the SalesOrderDetail table.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumprojection_mq)]
 [!code-vb[DP L2E Examples#SumProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="25761-144">例</span><span class="sxs-lookup"><span data-stu-id="25761-144">Example</span></span>  
 <span data-ttu-id="25761-145">次の例では、<xref:System.Linq.Enumerable.Sum%2A> メソッドを使用して、それぞれの連絡先 ID について合計支払額を取得します。</span><span class="sxs-lookup"><span data-stu-id="25761-145">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="25761-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="25761-146">See also</span></span>

- [<span data-ttu-id="25761-147">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="25761-147">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
