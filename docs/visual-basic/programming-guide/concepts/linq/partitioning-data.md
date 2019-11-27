---
title: データのパーティション分割
ms.date: 07/20/2015
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
ms.openlocfilehash: 2ab4e27ef6d825b9100fc3c15b7a9554ae49e516
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353152"
---
# <a name="partitioning-data-visual-basic"></a><span data-ttu-id="dd87e-102">データのパーティション分割 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd87e-102">Partitioning Data (Visual Basic)</span></span>
<span data-ttu-id="dd87e-103">LINQ におけるパーティション分割とは、要素を並べ替えずに入力シーケンスを 2 つのセクションに分割し、それらのセクションの 1 つを返す操作を指します。</span><span class="sxs-lookup"><span data-stu-id="dd87e-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="dd87e-104">次の図は、文字のシーケンスに対して 3 つの異なるパーティション分割操作を実行した結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="dd87e-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="dd87e-105">最初の操作では、シーケンスの最初の 3 つの要素が返されます。</span><span class="sxs-lookup"><span data-stu-id="dd87e-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="dd87e-106">2 番目の操作では、最初の 3 つの要素がスキップされ、残りの要素が返されます。</span><span class="sxs-lookup"><span data-stu-id="dd87e-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="dd87e-107">3 番目の操作では、シーケンスの最初の 2 つの要素がスキップされ、次の 3 つの要素が返されます。</span><span class="sxs-lookup"><span data-stu-id="dd87e-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 ![LINQ のパーティション操作を示す図。](./media/partitioning-data/linq-partitioning-operations.png)  
  
 <span data-ttu-id="dd87e-109">次のセクションに、シーケンスのパーティション分割を実行する標準クエリ演算子メソッドの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="dd87e-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="dd87e-110">演算子</span><span class="sxs-lookup"><span data-stu-id="dd87e-110">Operators</span></span>  
  
|<span data-ttu-id="dd87e-111">演算子名</span><span class="sxs-lookup"><span data-stu-id="dd87e-111">Operator Name</span></span>|<span data-ttu-id="dd87e-112">説明</span><span class="sxs-lookup"><span data-stu-id="dd87e-112">Description</span></span>|<span data-ttu-id="dd87e-113">Visual Basic クエリ式の構文</span><span class="sxs-lookup"><span data-stu-id="dd87e-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="dd87e-114">詳細</span><span class="sxs-lookup"><span data-stu-id="dd87e-114">More Information</span></span>|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="dd87e-115">スキップ</span><span class="sxs-lookup"><span data-stu-id="dd87e-115">Skip</span></span>|<span data-ttu-id="dd87e-116">シーケンス内の指定した位置まで要素をスキップします。</span><span class="sxs-lookup"><span data-stu-id="dd87e-116">Skips elements up to a specified position in a sequence.</span></span>|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="dd87e-117">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="dd87e-117">SkipWhile</span></span>|<span data-ttu-id="dd87e-118">述語関数に基づき、条件を満たさない要素が出現する位置まで要素をスキップします。</span><span class="sxs-lookup"><span data-stu-id="dd87e-118">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="dd87e-119">Take</span><span class="sxs-lookup"><span data-stu-id="dd87e-119">Take</span></span>|<span data-ttu-id="dd87e-120">シーケンス内の指定した位置までの要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="dd87e-120">Takes elements up to a specified position in a sequence.</span></span>|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="dd87e-121">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="dd87e-121">TakeWhile</span></span>|<span data-ttu-id="dd87e-122">述語関数に基づき、条件を満たさない要素が出現する位置までの要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="dd87e-122">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="dd87e-123">クエリ式の構文例</span><span class="sxs-lookup"><span data-stu-id="dd87e-123">Query Expression Syntax Examples</span></span>  
  
### <a name="skip"></a><span data-ttu-id="dd87e-124">スキップ</span><span class="sxs-lookup"><span data-stu-id="dd87e-124">Skip</span></span>  
 <span data-ttu-id="dd87e-125">次のコード例では、Visual Basic の `Skip` 句を使用して、配列内の残りの文字列を返す前に、文字列の配列内の最初の4つの文字列をスキップします。</span><span class="sxs-lookup"><span data-stu-id="dd87e-125">The following code example uses the `Skip` clause in Visual Basic to skip over the first four strings in an array of strings before returning the remaining strings in the array.</span></span>  
  
 [!code-vb[CsLINQPartitioning#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#1)]  
  
### <a name="skipwhile"></a><span data-ttu-id="dd87e-126">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="dd87e-126">SkipWhile</span></span>  
 <span data-ttu-id="dd87e-127">次のコード例では、Visual Basic の `Skip While` 句を使用して、文字列の最初の文字が "a" であるときに、配列内の文字列をスキップします。</span><span class="sxs-lookup"><span data-stu-id="dd87e-127">The following code example uses the `Skip While` clause in Visual Basic to skip over the strings in an array while the first letter of the string is "a".</span></span> <span data-ttu-id="dd87e-128">配列内の残りの文字列が返されます。</span><span class="sxs-lookup"><span data-stu-id="dd87e-128">The remaining strings in the array are returned.</span></span>  
  
 [!code-vb[CsLINQPartitioning#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#2)]  
  
### <a name="take"></a><span data-ttu-id="dd87e-129">Take</span><span class="sxs-lookup"><span data-stu-id="dd87e-129">Take</span></span>  
 <span data-ttu-id="dd87e-130">次のコード例では、Visual Basic の `Take` 句を使用して、文字列の配列内の最初の2つの文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="dd87e-130">The following code example uses the `Take` clause in Visual Basic to return the first two strings in an array of strings.</span></span>  
  
 [!code-vb[CsLINQPartitioning#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#3)]  
  
### <a name="takewhile"></a><span data-ttu-id="dd87e-131">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="dd87e-131">TakeWhile</span></span>  
 <span data-ttu-id="dd87e-132">次のコード例では、Visual Basic の `Take While` 句を使用して、文字列の長さが5以下の場合に配列から文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="dd87e-132">The following code example uses the `Take While` clause in Visual Basic to return strings from an array while the length of the string is five or less.</span></span>  
  
 [!code-vb[CsLINQPartitioning#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="dd87e-133">参照</span><span class="sxs-lookup"><span data-stu-id="dd87e-133">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="dd87e-134">標準クエリ演算子の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd87e-134">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="dd87e-135">Skip 句</span><span class="sxs-lookup"><span data-stu-id="dd87e-135">Skip Clause</span></span>](../../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="dd87e-136">Skip While 句</span><span class="sxs-lookup"><span data-stu-id="dd87e-136">Skip While Clause</span></span>](../../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="dd87e-137">Take 句</span><span class="sxs-lookup"><span data-stu-id="dd87e-137">Take Clause</span></span>](../../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="dd87e-138">Take While 句</span><span class="sxs-lookup"><span data-stu-id="dd87e-138">Take While Clause</span></span>](../../../../visual-basic/language-reference/queries/take-while-clause.md)
