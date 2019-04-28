---
title: メソッド ベースのクエリ構文例:射影
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 505491fa-5920-43ce-8a96-c25389e125d8
ms.openlocfilehash: a38fce33fe34bf6485d0d5fcef4f194f4c2470b5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760507"
---
# <a name="method-based-query-syntax-examples-projection"></a><span data-ttu-id="bd9cf-102">メソッド ベースのクエリ構文例:射影</span><span class="sxs-lookup"><span data-stu-id="bd9cf-102">Method-Based Query Syntax Examples: Projection</span></span>
<span data-ttu-id="bd9cf-103">このトピックの例では、使用する方法を示します、<xref:System.Linq.Enumerable.Select%2A>と<xref:System.Linq.Enumerable.SelectMany%2A>を照会する方法、 [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples)メソッド ベースのクエリ構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd9cf-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="bd9cf-104">これらの例で使用されている、AdventureWorks Sales Model は、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルから作成されています。</span><span class="sxs-lookup"><span data-stu-id="bd9cf-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="bd9cf-105">このトピックの例では、次を使用して`using` / `Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="bd9cf-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="select"></a><span data-ttu-id="bd9cf-106">選択</span><span class="sxs-lookup"><span data-stu-id="bd9cf-106">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="bd9cf-107">例</span><span class="sxs-lookup"><span data-stu-id="bd9cf-107">Example</span></span>  
 <span data-ttu-id="bd9cf-108">次の例では、<xref:System.Linq.Queryable.Select%2A> メソッドを使用して、`Product.Name` プロパティおよび `Product.ProductID` プロパティを一連の匿名型に射影します。</span><span class="sxs-lookup"><span data-stu-id="bd9cf-108">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to project the `Product.Name` and `Product.ProductID` properties into a sequence of anonymous types.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
### <a name="example"></a><span data-ttu-id="bd9cf-109">例</span><span class="sxs-lookup"><span data-stu-id="bd9cf-109">Example</span></span>  
 <span data-ttu-id="bd9cf-110">次の例では、<xref:System.Linq.Enumerable.Select%2A> メソッドを使用して、一連の製品名だけを取得しています。</span><span class="sxs-lookup"><span data-stu-id="bd9cf-110">The following example uses the <xref:System.Linq.Enumerable.Select%2A> method to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2_mq)]
 [!code-vb[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2_mq)]  
  
## <a name="selectmany"></a><span data-ttu-id="bd9cf-111">SelectMany</span><span class="sxs-lookup"><span data-stu-id="bd9cf-111">SelectMany</span></span>  
  
### <a name="example"></a><span data-ttu-id="bd9cf-112">例</span><span class="sxs-lookup"><span data-stu-id="bd9cf-112">Example</span></span>  
 <span data-ttu-id="bd9cf-113">次の例では、<xref:System.Linq.Enumerable.SelectMany%2A> メソッドを使用して、`TotalDue` が 500.00 に満たないすべての注文を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd9cf-113">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom_mq)]  
  
### <a name="example"></a><span data-ttu-id="bd9cf-114">例</span><span class="sxs-lookup"><span data-stu-id="bd9cf-114">Example</span></span>  
 <span data-ttu-id="bd9cf-115">次の例では、<xref:System.Linq.Enumerable.SelectMany%2A> メソッドを使用して、2002 年 10 月 1 日以降に受けたすべての注文を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd9cf-115">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="bd9cf-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd9cf-116">See also</span></span>

- [<span data-ttu-id="bd9cf-117">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="bd9cf-117">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
