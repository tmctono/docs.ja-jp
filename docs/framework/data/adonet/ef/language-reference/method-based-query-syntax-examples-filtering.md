---
title: メソッド ベースのクエリ構文例:フィルター
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e40e314c-eb30-4f44-a054-41e511e35832
ms.openlocfilehash: e0eb29b750c474c277ef54c343726b338fbf5dbe
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250229"
---
# <a name="method-based-query-syntax-examples-filtering"></a><span data-ttu-id="f556c-102">メソッド ベースのクエリ構文例:フィルター</span><span class="sxs-lookup"><span data-stu-id="f556c-102">Method-Based Query Syntax Examples: Filtering</span></span>
<span data-ttu-id="f556c-103">このトピックの例では、メソッドベースの`Where`クエリ`Where…Contains`構文を使用して、メソッドとメソッドを使用して、 [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples)に対してクエリを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f556c-103">The examples in this topic demonstrate how to use the `Where` and `Where…Contains` methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="f556c-104">注意:`Contains`</span><span class="sxs-lookup"><span data-stu-id="f556c-104">Note, Where…`Contains`</span></span> <span data-ttu-id="f556c-105">は、[コンパイル済みクエリ](compiled-queries-linq-to-entities.md)の一部として使用できません。</span><span class="sxs-lookup"><span data-stu-id="f556c-105">cannot be used as a part of a [compiled query](compiled-queries-linq-to-entities.md).</span></span>  
  
 <span data-ttu-id="f556c-106">これらの例で使用されている、AdventureWorks Sales Model は、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルから作成されています。</span><span class="sxs-lookup"><span data-stu-id="f556c-106">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="f556c-107">このトピックの例では、次`using` / `Imports`のステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="f556c-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="where"></a><span data-ttu-id="f556c-108">場所</span><span class="sxs-lookup"><span data-stu-id="f556c-108">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="f556c-109">例</span><span class="sxs-lookup"><span data-stu-id="f556c-109">Example</span></span>  
 <span data-ttu-id="f556c-110">次の例では、すべてのオンライン注文が返されます。</span><span class="sxs-lookup"><span data-stu-id="f556c-110">The following example returns all online orders.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where1_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where1_mq)]
 [!code-vb[DP L2E Examples#Where1_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where1_mq)]  
  
### <a name="example"></a><span data-ttu-id="f556c-111">例</span><span class="sxs-lookup"><span data-stu-id="f556c-111">Example</span></span>  
 <span data-ttu-id="f556c-112">次の例では、注文数量が 3 個以上で 5 個以下の注文が返されます。</span><span class="sxs-lookup"><span data-stu-id="f556c-112">The following example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where2_mq)]
 [!code-vb[DP L2E Examples#Where2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where2_mq)]  
  
### <a name="example"></a><span data-ttu-id="f556c-113">例</span><span class="sxs-lookup"><span data-stu-id="f556c-113">Example</span></span>  
 <span data-ttu-id="f556c-114">次の例では、色が赤の製品がすべて返されます。</span><span class="sxs-lookup"><span data-stu-id="f556c-114">The following example returns all red colored products.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where3_mq)]
 [!code-vb[DP L2E Examples#Where3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where3_mq)]  
  
### <a name="example"></a><span data-ttu-id="f556c-115">例</span><span class="sxs-lookup"><span data-stu-id="f556c-115">Example</span></span>  
 <span data-ttu-id="f556c-116">次の例では、`Where` メソッドを使用して、2003 年 12 月 1 日以降に受けた注文を検索します。次に、`order.SalesOrderDetail` ナビゲーション プロパティを使用して、各注文の詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="f556c-116">The following example uses the `Where` method to find orders that were made after December 1, 2003 and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty_mq)]
 [!code-vb[DP L2E Examples#WhereNavProperty_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty_mq)]  
  
## <a name="wherecontains"></a><span data-ttu-id="f556c-117">Where…Contains</span><span class="sxs-lookup"><span data-stu-id="f556c-117">Where…Contains</span></span>  
  
### <a name="example"></a><span data-ttu-id="f556c-118">例</span><span class="sxs-lookup"><span data-stu-id="f556c-118">Example</span></span>  
 <span data-ttu-id="f556c-119">次の例では、配列を `Where…Contains` 句の一部として使用し、その配列内の値と一致する `ProductModelID` を持つすべての製品を検出します。</span><span class="sxs-lookup"><span data-stu-id="f556c-119">The following example uses an array as part of a `Where…Contains` clause to find all products that have a `ProductModelID` that matches a value in the array.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#3)]
 [!code-vb[DP L2E ArraysAndListsInQueries#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#3)]  
  
> [!NOTE]
> <span data-ttu-id="f556c-120">`Where…Contains` 句の述語として、<xref:System.Array>、<xref:System.Collections.Generic.List%601>、または <xref:System.Collections.Generic.IEnumerable%601> インターフェイスを実装する任意の型のコレクションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f556c-120">As part of the predicate in a `Where…Contains` clause, you can use an <xref:System.Array>, a <xref:System.Collections.Generic.List%601>, or a collection of any type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="f556c-121">さらに、LINQ to Entities クエリ内でコレクションを宣言および初期化できます。</span><span class="sxs-lookup"><span data-stu-id="f556c-121">You can also declare and initialize a collection within a LINQ to Entities query.</span></span> <span data-ttu-id="f556c-122">詳細については、次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f556c-122">See the next example for more information.</span></span>  
  
### <a name="example"></a><span data-ttu-id="f556c-123">例</span><span class="sxs-lookup"><span data-stu-id="f556c-123">Example</span></span>  
 <span data-ttu-id="f556c-124">次の例では、`Where…Contains` 句で配列を宣言および初期化し、その配列内の値と一致する `ProductModelID` または `Size` を持つすべての製品を検出します。</span><span class="sxs-lookup"><span data-stu-id="f556c-124">The following example declares and initializes arrays in a `Where…Contains` clause to find all products that have a `ProductModelID` or a `Size` that matches a value in the arrays.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#4)]
 [!code-vb[DP L2E ArraysAndListsInQueries#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="f556c-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="f556c-125">See also</span></span>

- [<span data-ttu-id="f556c-126">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="f556c-126">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
