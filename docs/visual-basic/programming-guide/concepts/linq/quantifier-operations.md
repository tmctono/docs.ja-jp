---
title: 量指定子操作
ms.date: 07/20/2015
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
ms.openlocfilehash: f5b98ec09405ca4b8c715dc7da342e66a5d434d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346580"
---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="3dd8a-102">量指定子操作 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3dd8a-102">Quantifier Operations (Visual Basic)</span></span>
<span data-ttu-id="3dd8a-103">量指定子操作は、シーケンス内の要素の一部またはすべてが条件を満たしているかどうかを示す <xref:System.Boolean> 値を返します。</span><span class="sxs-lookup"><span data-stu-id="3dd8a-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="3dd8a-104">次の図は、2 つの異なるソース シーケンスに対する、2 つの異なる量指定子操作を示しています。</span><span class="sxs-lookup"><span data-stu-id="3dd8a-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="3dd8a-105">最初の操作では、1 つ以上の要素が文字 'A' であるかどうかを尋ねていて、その結果は `true` です。</span><span class="sxs-lookup"><span data-stu-id="3dd8a-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="3dd8a-106">2 番目の操作では、すべての要素が文字 'A' であるかどうかを尋ねていて、その結果は `true` です。</span><span class="sxs-lookup"><span data-stu-id="3dd8a-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![LINQ 量指定子操作](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="3dd8a-108">次のセクションでは、量指定子操作を実行する標準クエリ演算子のメソッドの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="3dd8a-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3dd8a-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="3dd8a-109">Methods</span></span>  
  
|<span data-ttu-id="3dd8a-110">メソッド名</span><span class="sxs-lookup"><span data-stu-id="3dd8a-110">Method Name</span></span>|<span data-ttu-id="3dd8a-111">説明</span><span class="sxs-lookup"><span data-stu-id="3dd8a-111">Description</span></span>|<span data-ttu-id="3dd8a-112">Visual Basic クエリ式の構文</span><span class="sxs-lookup"><span data-stu-id="3dd8a-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="3dd8a-113">詳細</span><span class="sxs-lookup"><span data-stu-id="3dd8a-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="3dd8a-114">[すべて]</span><span class="sxs-lookup"><span data-stu-id="3dd8a-114">All</span></span>|<span data-ttu-id="3dd8a-115">シーケンス内のすべての要素が条件を満たしているかどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="3dd8a-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3dd8a-116">任意</span><span class="sxs-lookup"><span data-stu-id="3dd8a-116">Any</span></span>|<span data-ttu-id="3dd8a-117">シーケンス内のいずれかの要素が条件を満たしているかどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="3dd8a-117">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3dd8a-118">次の値を含む</span><span class="sxs-lookup"><span data-stu-id="3dd8a-118">Contains</span></span>|<span data-ttu-id="3dd8a-119">指定した要素がシーケンスに格納されているかどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="3dd8a-119">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="3dd8a-120">該当しない。</span><span class="sxs-lookup"><span data-stu-id="3dd8a-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="3dd8a-121">クエリ式の構文例</span><span class="sxs-lookup"><span data-stu-id="3dd8a-121">Query Expression Syntax Examples</span></span>  
 <span data-ttu-id="3dd8a-122">これらの例では、LINQ クエリのフィルター条件の一部として Visual Basic の `Aggregate` 句を使用します。</span><span class="sxs-lookup"><span data-stu-id="3dd8a-122">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="3dd8a-123">次の例では、`Aggregate` 句と <xref:System.Linq.Enumerable.All%2A> 拡張メソッドを使用して、指定された年齢を超えるペットを持つユーザーをコレクションから返します。</span><span class="sxs-lookup"><span data-stu-id="3dd8a-123">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#1)]  
  
 <span data-ttu-id="3dd8a-124">次の例では、`Aggregate` 句と <xref:System.Linq.Enumerable.Any%2A> 拡張メソッドを使用して、指定した年齢よりも古いペットを1つ以上持つユーザーをコレクションから返します。</span><span class="sxs-lookup"><span data-stu-id="3dd8a-124">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="3dd8a-125">参照</span><span class="sxs-lookup"><span data-stu-id="3dd8a-125">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="3dd8a-126">標準クエリ演算子の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3dd8a-126">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="3dd8a-127">Aggregate 句</span><span class="sxs-lookup"><span data-stu-id="3dd8a-127">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="3dd8a-128">方法: 指定された単語のセットを含む文章を照会する (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3dd8a-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
