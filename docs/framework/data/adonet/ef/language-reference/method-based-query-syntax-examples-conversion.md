---
title: メソッド ベースのクエリ構文例:変換
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 19f66872-d5ab-49f8-969f-e53f9632a13d
ms.openlocfilehash: a78588cb4bd09f8a8a8ce8ed4a60dd45fce1d386
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397482"
---
# <a name="method-based-query-syntax-examples-conversion"></a><span data-ttu-id="792c1-102">メソッド ベースのクエリ構文例:変換</span><span class="sxs-lookup"><span data-stu-id="792c1-102">Method-Based Query Syntax Examples: Conversion</span></span>
<span data-ttu-id="792c1-103">このトピックの例では、メソッドベースの<xref:System.Linq.Enumerable.ToArray%2A>クエリ構文<xref:System.Linq.Enumerable.ToList%2A>を使用して、 <xref:System.Linq.Enumerable.ToDictionary%2A>メソッド、メソッド、およびメソッドを使用して、 [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)に対してクエリを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="792c1-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> and <xref:System.Linq.Enumerable.ToList%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="792c1-104">これらの例で使用されている、AdventureWorks Sales Model は、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルから作成されています。</span><span class="sxs-lookup"><span data-stu-id="792c1-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="792c1-105">このトピックの例では、次`using` / `Imports`のステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="792c1-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="toarray"></a><span data-ttu-id="792c1-106">ToArray</span><span class="sxs-lookup"><span data-stu-id="792c1-106">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="792c1-107">例</span><span class="sxs-lookup"><span data-stu-id="792c1-107">Example</span></span>  
 <span data-ttu-id="792c1-108">次の例では、<xref:System.Linq.Enumerable.ToArray%2A> メソッドを使用して、シーケンスを配列として即時評価します。</span><span class="sxs-lookup"><span data-stu-id="792c1-108">The following example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToArray](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#toarray)]
 [!code-vb[DP L2E Examples#ToArray](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="792c1-109">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="792c1-109">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="792c1-110">例</span><span class="sxs-lookup"><span data-stu-id="792c1-110">Example</span></span>  
 <span data-ttu-id="792c1-111">次の例では、<xref:System.Linq.Enumerable.ToDictionary%2A> メソッドを使用して、シーケンスおよび関連するキー式をディクショナリとして即時評価します。</span><span class="sxs-lookup"><span data-stu-id="792c1-111">The following example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="792c1-112">ToList</span><span class="sxs-lookup"><span data-stu-id="792c1-112">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="792c1-113">例</span><span class="sxs-lookup"><span data-stu-id="792c1-113">Example</span></span>  
 <span data-ttu-id="792c1-114">次の例では、<xref:System.Linq.Enumerable.ToList%2A> メソッドを使用して、シーケンスを <xref:System.Collections.Generic.List%601> として即時評価します。ここで、`T` は <xref:System.Data.DataRow> 型を表します。</span><span class="sxs-lookup"><span data-stu-id="792c1-114">The following example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToList](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#tolist)]
 [!code-vb[DP L2E Examples#ToList](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="792c1-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="792c1-115">See also</span></span>

- [<span data-ttu-id="792c1-116">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="792c1-116">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
