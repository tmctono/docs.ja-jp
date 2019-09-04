---
title: クエリ式の構文例:射影
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 079926c5-e6b5-4fb9-b4cf-9c63886dd626
ms.openlocfilehash: 52681a4035ef55133c6191e7eac2cab7ed36c8fb
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249346"
---
# <a name="query-expression-syntax-examples-projection"></a><span data-ttu-id="79a04-102">クエリ式の構文例:射影</span><span class="sxs-lookup"><span data-stu-id="79a04-102">Query Expression Syntax Examples: Projection</span></span>
<span data-ttu-id="79a04-103">このトピックの例では、クエリ式の`Select`構文を使用`From … From …`して、メソッドとキーワードを使用して、 [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples)に対してクエリを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="79a04-103">The examples in this topic demonstrate how to use the `Select` method and the `From … From …` keywords to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="79a04-104">`From … From …` は、メソッドは、`SelectMany` メソッドのクエリ ベース版に相当します。</span><span class="sxs-lookup"><span data-stu-id="79a04-104">`From … From …` is the query based equivalent of the `SelectMany` method.</span></span> <span data-ttu-id="79a04-105">これらの例で使用されている、AdventureWorks Sales Model は、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルから作成されています。</span><span class="sxs-lookup"><span data-stu-id="79a04-105">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="79a04-106">このトピックの例では、次`using` / `Imports`のステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="79a04-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="select"></a><span data-ttu-id="79a04-107">Select</span><span class="sxs-lookup"><span data-stu-id="79a04-107">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="79a04-108">例</span><span class="sxs-lookup"><span data-stu-id="79a04-108">Example</span></span>  
 <span data-ttu-id="79a04-109">次の例では、<xref:System.Linq.Enumerable.Select%2A> メソッドを使用して `Product` テーブルからすべての行を取得し、製品名を表示しています。</span><span class="sxs-lookup"><span data-stu-id="79a04-109">The following example uses the <xref:System.Linq.Enumerable.Select%2A> method to return all the rows from the `Product` table and display the product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP L2E Examples#SelectSimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple1)]  
  
### <a name="example"></a><span data-ttu-id="79a04-110">例</span><span class="sxs-lookup"><span data-stu-id="79a04-110">Example</span></span>  
 <span data-ttu-id="79a04-111">次の例では、<xref:System.Linq.Enumerable.Select%2A> を使用して、一連の製品名だけを取得しています。</span><span class="sxs-lookup"><span data-stu-id="79a04-111">The following example uses <xref:System.Linq.Enumerable.Select%2A> to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2)]
 [!code-vb[DP L2E Examples#SelectSimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2)]  
  
### <a name="example"></a><span data-ttu-id="79a04-112">例</span><span class="sxs-lookup"><span data-stu-id="79a04-112">Example</span></span>  
 <span data-ttu-id="79a04-113">次の例では、<xref:System.Linq.Queryable.Select%2A> メソッドを使用して、`Product.Name` プロパティおよび `Product.ProductID` プロパティを一連の匿名型に射影します。</span><span class="sxs-lookup"><span data-stu-id="79a04-113">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to project the `Product.Name` and `Product.ProductID` properties into a sequence of anonymous types.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes)]  
  
## <a name="from--from--selectmany"></a><span data-ttu-id="79a04-114">差出人。</span><span class="sxs-lookup"><span data-stu-id="79a04-114">From …</span></span> <span data-ttu-id="79a04-115">差出人。</span><span class="sxs-lookup"><span data-stu-id="79a04-115">From …</span></span> <span data-ttu-id="79a04-116">SelectMany</span><span class="sxs-lookup"><span data-stu-id="79a04-116">(SelectMany)</span></span>  
  
### <a name="example"></a><span data-ttu-id="79a04-117">例</span><span class="sxs-lookup"><span data-stu-id="79a04-117">Example</span></span>  
 <span data-ttu-id="79a04-118">次の例では、`From … From …` (<xref:System.Linq.Enumerable.SelectMany%2A> メソッドと等価) を使用して、`TotalDue` が 500.00 に満たないすべての注文を選択します。</span><span class="sxs-lookup"><span data-stu-id="79a04-118">The following example uses `From … From …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom)]  
  
### <a name="example"></a><span data-ttu-id="79a04-119">例</span><span class="sxs-lookup"><span data-stu-id="79a04-119">Example</span></span>  
 <span data-ttu-id="79a04-120">次の例では、`From … From …` (<xref:System.Linq.Enumerable.SelectMany%2A> メソッドと等価) を使用して、2002 年 10 月 1 日以降に受けたすべての注文を選択します。</span><span class="sxs-lookup"><span data-stu-id="79a04-120">The following example uses `From … From …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2)]  
  
### <a name="example"></a><span data-ttu-id="79a04-121">例</span><span class="sxs-lookup"><span data-stu-id="79a04-121">Example</span></span>  
 <span data-ttu-id="79a04-122">次の例では、`From … From …` (<xref:System.Linq.Enumerable.SelectMany%2A> メソッドと等価) を使用して、注文の合計が 10000.00 を超えるすべての注文を選択します。このとき、`From` 割り当てを使用して、合計を 2 回要求しないようにしています。</span><span class="sxs-lookup"><span data-stu-id="79a04-122">The following example uses a `From … From …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order total is greater than 10000.00 and uses `From` assignment to avoid requesting the total twice.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyFromAssignment](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanyfromassignment)]
 [!code-vb[DP L2E Examples#SelectManyFromAssignment](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanyfromassignment)]  
  
## <a name="see-also"></a><span data-ttu-id="79a04-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="79a04-123">See also</span></span>

- [<span data-ttu-id="79a04-124">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="79a04-124">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
