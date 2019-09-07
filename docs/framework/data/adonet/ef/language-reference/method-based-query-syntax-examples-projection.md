---
title: メソッド ベースのクエリ構文例:射影
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 505491fa-5920-43ce-8a96-c25389e125d8
ms.openlocfilehash: 3a9203a51bbb61b32300919656084d7d95ddfa79
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397321"
---
# <a name="method-based-query-syntax-examples-projection"></a><span data-ttu-id="1e124-102">メソッド ベースのクエリ構文例:射影</span><span class="sxs-lookup"><span data-stu-id="1e124-102">Method-Based Query Syntax Examples: Projection</span></span>
<span data-ttu-id="1e124-103">このトピックの例では、メソッドベースの<xref:System.Linq.Enumerable.Select%2A>クエリ<xref:System.Linq.Enumerable.SelectMany%2A>構文を使用して、メソッドとメソッドを使用して、 [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)に対してクエリを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1e124-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="1e124-104">これらの例で使用されている、AdventureWorks Sales Model は、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルから作成されています。</span><span class="sxs-lookup"><span data-stu-id="1e124-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="1e124-105">このトピックの例では、次`using` / `Imports`のステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="1e124-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="select"></a><span data-ttu-id="1e124-106">Select</span><span class="sxs-lookup"><span data-stu-id="1e124-106">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="1e124-107">例</span><span class="sxs-lookup"><span data-stu-id="1e124-107">Example</span></span>  
 <span data-ttu-id="1e124-108">次の例では、<xref:System.Linq.Queryable.Select%2A> メソッドを使用して、`Product.Name` プロパティおよび `Product.ProductID` プロパティを一連の匿名型に射影します。</span><span class="sxs-lookup"><span data-stu-id="1e124-108">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to project the `Product.Name` and `Product.ProductID` properties into a sequence of anonymous types.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
### <a name="example"></a><span data-ttu-id="1e124-109">例</span><span class="sxs-lookup"><span data-stu-id="1e124-109">Example</span></span>  
 <span data-ttu-id="1e124-110">次の例では、<xref:System.Linq.Enumerable.Select%2A> メソッドを使用して、一連の製品名だけを取得しています。</span><span class="sxs-lookup"><span data-stu-id="1e124-110">The following example uses the <xref:System.Linq.Enumerable.Select%2A> method to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2_mq)]
 [!code-vb[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2_mq)]  
  
## <a name="selectmany"></a><span data-ttu-id="1e124-111">SelectMany</span><span class="sxs-lookup"><span data-stu-id="1e124-111">SelectMany</span></span>  
  
### <a name="example"></a><span data-ttu-id="1e124-112">例</span><span class="sxs-lookup"><span data-stu-id="1e124-112">Example</span></span>  
 <span data-ttu-id="1e124-113">次の例では、<xref:System.Linq.Enumerable.SelectMany%2A> メソッドを使用して、`TotalDue` が 500.00 に満たないすべての注文を選択します。</span><span class="sxs-lookup"><span data-stu-id="1e124-113">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom_mq)]  
  
### <a name="example"></a><span data-ttu-id="1e124-114">例</span><span class="sxs-lookup"><span data-stu-id="1e124-114">Example</span></span>  
 <span data-ttu-id="1e124-115">次の例では、<xref:System.Linq.Enumerable.SelectMany%2A> メソッドを使用して、2002 年 10 月 1 日以降に受けたすべての注文を選択します。</span><span class="sxs-lookup"><span data-stu-id="1e124-115">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="1e124-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e124-116">See also</span></span>

- [<span data-ttu-id="1e124-117">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="1e124-117">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
