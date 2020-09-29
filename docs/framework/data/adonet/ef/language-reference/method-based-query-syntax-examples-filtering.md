---
title: メソッド ベースのクエリ構文例:フィルター処理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e40e314c-eb30-4f44-a054-41e511e35832
ms.openlocfilehash: 392181f201c7b18b1b38f62f5f35c5657cbbe601
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191997"
---
# <a name="method-based-query-syntax-examples-filtering"></a><span data-ttu-id="8e4a4-102">メソッド ベースのクエリ構文例:フィルター処理</span><span class="sxs-lookup"><span data-stu-id="8e4a4-102">Method-Based Query Syntax Examples: Filtering</span></span>

<span data-ttu-id="8e4a4-103">このトピックでは、メソッド ベースのクエリ構文で、`Where` メソッドと `Where…Contains` メソッドを使用して、[AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) を照会する例を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="8e4a4-103">The examples in this topic demonstrate how to use the `Where` and `Where…Contains` methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="8e4a4-104">Where…`Contains`</span><span class="sxs-lookup"><span data-stu-id="8e4a4-104">Note, Where…`Contains`</span></span> <span data-ttu-id="8e4a4-105">を[コンパイル済みクエリ](compiled-queries-linq-to-entities.md)の一部として使用することはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8e4a4-105">cannot be used as a part of a [compiled query](compiled-queries-linq-to-entities.md).</span></span>  
  
 <span data-ttu-id="8e4a4-106">これらの例で使用されている、AdventureWorks Sales Model は、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルから作成されています。</span><span class="sxs-lookup"><span data-stu-id="8e4a4-106">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="8e4a4-107">このトピックの例には、次の `using`/`Imports` ステートメントが使用されています。</span><span class="sxs-lookup"><span data-stu-id="8e4a4-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="where"></a><span data-ttu-id="8e4a4-108">Where</span><span class="sxs-lookup"><span data-stu-id="8e4a4-108">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="8e4a4-109">例</span><span class="sxs-lookup"><span data-stu-id="8e4a4-109">Example</span></span>  

 <span data-ttu-id="8e4a4-110">次の例では、すべてのオンライン注文が返されます。</span><span class="sxs-lookup"><span data-stu-id="8e4a4-110">The following example returns all online orders.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where1_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where1_mq)]
 [!code-vb[DP L2E Examples#Where1_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where1_mq)]  
  
### <a name="example"></a><span data-ttu-id="8e4a4-111">例</span><span class="sxs-lookup"><span data-stu-id="8e4a4-111">Example</span></span>  

 <span data-ttu-id="8e4a4-112">次の例では、注文数量が 3 個以上で 5 個以下の注文が返されます。</span><span class="sxs-lookup"><span data-stu-id="8e4a4-112">The following example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where2_mq)]
 [!code-vb[DP L2E Examples#Where2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where2_mq)]  
  
### <a name="example"></a><span data-ttu-id="8e4a4-113">例</span><span class="sxs-lookup"><span data-stu-id="8e4a4-113">Example</span></span>  

 <span data-ttu-id="8e4a4-114">次の例では、色が赤の製品がすべて返されます。</span><span class="sxs-lookup"><span data-stu-id="8e4a4-114">The following example returns all red colored products.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where3_mq)]
 [!code-vb[DP L2E Examples#Where3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where3_mq)]  
  
### <a name="example"></a><span data-ttu-id="8e4a4-115">例</span><span class="sxs-lookup"><span data-stu-id="8e4a4-115">Example</span></span>  

 <span data-ttu-id="8e4a4-116">次の例では、`Where` メソッドを使用して、2003 年 12 月 1 日以降に受けた注文を検索します。次に、`order.SalesOrderDetail` ナビゲーション プロパティを使用して、各注文の詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="8e4a4-116">The following example uses the `Where` method to find orders that were made after December 1, 2003 and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty_mq)]
 [!code-vb[DP L2E Examples#WhereNavProperty_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty_mq)]  
  
## <a name="wherecontains"></a><span data-ttu-id="8e4a4-117">Where…Contains</span><span class="sxs-lookup"><span data-stu-id="8e4a4-117">Where…Contains</span></span>  
  
### <a name="example"></a><span data-ttu-id="8e4a4-118">例</span><span class="sxs-lookup"><span data-stu-id="8e4a4-118">Example</span></span>  

 <span data-ttu-id="8e4a4-119">次の例では、配列を `Where…Contains` 句の一部として使用し、その配列内の値と一致する `ProductModelID` を持つすべての製品を検出します。</span><span class="sxs-lookup"><span data-stu-id="8e4a4-119">The following example uses an array as part of a `Where…Contains` clause to find all products that have a `ProductModelID` that matches a value in the array.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#3)]
 [!code-vb[DP L2E ArraysAndListsInQueries#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#3)]  
  
> [!NOTE]
> <span data-ttu-id="8e4a4-120">`Where…Contains` 句の述語として、<xref:System.Array>、<xref:System.Collections.Generic.List%601>、または <xref:System.Collections.Generic.IEnumerable%601> インターフェイスを実装する任意の型のコレクションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8e4a4-120">As part of the predicate in a `Where…Contains` clause, you can use an <xref:System.Array>, a <xref:System.Collections.Generic.List%601>, or a collection of any type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="8e4a4-121">さらに、LINQ to Entities クエリ内でコレクションを宣言および初期化できます。</span><span class="sxs-lookup"><span data-stu-id="8e4a4-121">You can also declare and initialize a collection within a LINQ to Entities query.</span></span> <span data-ttu-id="8e4a4-122">詳細については、次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e4a4-122">See the next example for more information.</span></span>  
  
### <a name="example"></a><span data-ttu-id="8e4a4-123">例</span><span class="sxs-lookup"><span data-stu-id="8e4a4-123">Example</span></span>  

 <span data-ttu-id="8e4a4-124">次の例では、`Where…Contains` 句で配列を宣言および初期化し、その配列内の値と一致する `ProductModelID` または `Size` を持つすべての製品を検出します。</span><span class="sxs-lookup"><span data-stu-id="8e4a4-124">The following example declares and initializes arrays in a `Where…Contains` clause to find all products that have a `ProductModelID` or a `Size` that matches a value in the arrays.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#4)]
 [!code-vb[DP L2E ArraysAndListsInQueries#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="8e4a4-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e4a4-125">See also</span></span>

- [<span data-ttu-id="8e4a4-126">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="8e4a4-126">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
