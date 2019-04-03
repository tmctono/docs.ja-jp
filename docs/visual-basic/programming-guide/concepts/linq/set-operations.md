---
title: セット操作 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
ms.openlocfilehash: 59ab09607462c762758e6a246ec218a92e01f5de
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825783"
---
# <a name="set-operations-visual-basic"></a><span data-ttu-id="e2477-102">セット操作 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2477-102">Set Operations (Visual Basic)</span></span>
<span data-ttu-id="e2477-103">LINQ のセット操作は、同一または別個のコレクション (またはセット) に等しい要素があるかどうかに基づいて、結果を生成するクエリ操作です。</span><span class="sxs-lookup"><span data-stu-id="e2477-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="e2477-104">次のセクションでは、セット操作を実行する標準クエリ演算子のメソッドの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="e2477-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e2477-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e2477-105">Methods</span></span>  
  
|<span data-ttu-id="e2477-106">メソッド名</span><span class="sxs-lookup"><span data-stu-id="e2477-106">Method Name</span></span>|<span data-ttu-id="e2477-107">説明</span><span class="sxs-lookup"><span data-stu-id="e2477-107">Description</span></span>|<span data-ttu-id="e2477-108">Visual Basic のクエリ式の構文</span><span class="sxs-lookup"><span data-stu-id="e2477-108">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="e2477-109">説明</span><span class="sxs-lookup"><span data-stu-id="e2477-109">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="e2477-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="e2477-110">Distinct</span></span>|<span data-ttu-id="e2477-111">コレクションから重複する値を削除します。</span><span class="sxs-lookup"><span data-stu-id="e2477-111">Removes duplicate values from a collection.</span></span>|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e2477-112">除く</span><span class="sxs-lookup"><span data-stu-id="e2477-112">Except</span></span>|<span data-ttu-id="e2477-113">差集合 (一方のコレクションにだけ存在し、もう一方のコレクションには出現しない要素) を返します。</span><span class="sxs-lookup"><span data-stu-id="e2477-113">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="e2477-114">該当なし。</span><span class="sxs-lookup"><span data-stu-id="e2477-114">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e2477-115">交差</span><span class="sxs-lookup"><span data-stu-id="e2477-115">Intersect</span></span>|<span data-ttu-id="e2477-116">積集合 (2 つのコレクションのそれぞれに出現する要素) を返します。</span><span class="sxs-lookup"><span data-stu-id="e2477-116">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="e2477-117">該当なし。</span><span class="sxs-lookup"><span data-stu-id="e2477-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="e2477-118">和集合</span><span class="sxs-lookup"><span data-stu-id="e2477-118">Union</span></span>|<span data-ttu-id="e2477-119">和集合 (2 つのコレクションのどちらかに出現する一意の要素) を返します。</span><span class="sxs-lookup"><span data-stu-id="e2477-119">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="e2477-120">該当なし。</span><span class="sxs-lookup"><span data-stu-id="e2477-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="e2477-121">セット操作の比較</span><span class="sxs-lookup"><span data-stu-id="e2477-121">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="e2477-122">Distinct</span><span class="sxs-lookup"><span data-stu-id="e2477-122">Distinct</span></span>  
 <span data-ttu-id="e2477-123">次の図は、文字のシーケンスに対する <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> メソッドの動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="e2477-123">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="e2477-124">返されたシーケンスには、入力シーケンスからの一意の要素が格納されています。</span><span class="sxs-lookup"><span data-stu-id="e2477-124">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 ![Distinct の動作を示すグラフィック&#40;&#41;します。](./media/set-operations/distinct-method-behavior.png)  
  
### <a name="except"></a><span data-ttu-id="e2477-126">除く</span><span class="sxs-lookup"><span data-stu-id="e2477-126">Except</span></span>  
 <span data-ttu-id="e2477-127"><xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType> の動作を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="e2477-127">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e2477-128">返されたシーケンスには、1 つ目の入力シーケンスのうち、2 つ目の入力シーケンスには存在しない要素が格納されています。</span><span class="sxs-lookup"><span data-stu-id="e2477-128">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="e2477-129">![除く動作を示すグラフィック&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "除く動作を示します。")</span><span class="sxs-lookup"><span data-stu-id="e2477-129">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>  
  
### <a name="intersect"></a><span data-ttu-id="e2477-130">交差</span><span class="sxs-lookup"><span data-stu-id="e2477-130">Intersect</span></span>  
 <span data-ttu-id="e2477-131"><xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType> の動作を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="e2477-131">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e2477-132">返されたシーケンスには、両方の入力シーケンスに共通する要素が格納されています。</span><span class="sxs-lookup"><span data-stu-id="e2477-132">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 ![2 つのシーケンスの交差部分を示すグラフィック。](./media/set-operations/intersection-two-sequences.png)    
### <a name="union"></a><span data-ttu-id="e2477-134">和集合</span><span class="sxs-lookup"><span data-stu-id="e2477-134">Union</span></span>  
 <span data-ttu-id="e2477-135">次の図は、2 つの文字シーケンスに対する和集合演算を示しています。</span><span class="sxs-lookup"><span data-stu-id="e2477-135">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="e2477-136">返されたシーケンスには、両方の入力シーケンスからの一意の要素が格納されています。</span><span class="sxs-lookup"><span data-stu-id="e2477-136">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 ![2 つのシーケンスの結合を示すグラフィック。](./media/set-operations/union-operation-two-sequences.png)    
## <a name="query-expression-syntax-example"></a><span data-ttu-id="e2477-138">クエリ式の構文例</span><span class="sxs-lookup"><span data-stu-id="e2477-138">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="e2477-139">次の例では、`Distinct`を整数のリストから一意の番号を返す LINQ クエリ内の句。</span><span class="sxs-lookup"><span data-stu-id="e2477-139">The following example uses the `Distinct` clause in a LINQ query to return the unique numbers from a list of integers.</span></span>  
  
 [!code-vb[CsLINQSetOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQSetOps/VB/setops.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e2477-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2477-140">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="e2477-141">標準クエリ演算子の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2477-141">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="e2477-142">Distinct 句</span><span class="sxs-lookup"><span data-stu-id="e2477-142">Distinct Clause</span></span>](../../../../visual-basic/language-reference/queries/distinct-clause.md)
- [<span data-ttu-id="e2477-143">方法: 結合および比較文字列のコレクション (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2477-143">How to: Combine and Compare String Collections (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="e2477-144">方法: 2 つのリスト (LINQ) (Visual Basic) の差集合を見つける</span><span class="sxs-lookup"><span data-stu-id="e2477-144">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
