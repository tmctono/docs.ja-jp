---
title: セット操作 (C#)
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: 170316b36705eaed51a9a17f8f79333a29e8c315
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346513"
---
# <a name="set-operations-c"></a><span data-ttu-id="d5a0c-102">セット操作 (C#)</span><span class="sxs-lookup"><span data-stu-id="d5a0c-102">Set Operations (C#)</span></span>
<span data-ttu-id="d5a0c-103">LINQ のセット操作は、同一または別個のコレクション (またはセット) に等しい要素があるかどうかに基づいて、結果を生成するクエリ操作です。</span><span class="sxs-lookup"><span data-stu-id="d5a0c-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="d5a0c-104">次のセクションでは、セット操作を実行する標準クエリ演算子のメソッドの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="d5a0c-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d5a0c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d5a0c-105">Methods</span></span>  
  
|<span data-ttu-id="d5a0c-106">メソッド名</span><span class="sxs-lookup"><span data-stu-id="d5a0c-106">Method Name</span></span>|<span data-ttu-id="d5a0c-107">説明</span><span class="sxs-lookup"><span data-stu-id="d5a0c-107">Description</span></span>|<span data-ttu-id="d5a0c-108">C# のクエリ式の構文</span><span class="sxs-lookup"><span data-stu-id="d5a0c-108">C# Query Expression Syntax</span></span>|<span data-ttu-id="d5a0c-109">説明</span><span class="sxs-lookup"><span data-stu-id="d5a0c-109">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="d5a0c-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="d5a0c-110">Distinct</span></span>|<span data-ttu-id="d5a0c-111">コレクションから重複する値を削除します。</span><span class="sxs-lookup"><span data-stu-id="d5a0c-111">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="d5a0c-112">該当なし。</span><span class="sxs-lookup"><span data-stu-id="d5a0c-112">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d5a0c-113">除く</span><span class="sxs-lookup"><span data-stu-id="d5a0c-113">Except</span></span>|<span data-ttu-id="d5a0c-114">差集合 (一方のコレクションにだけ存在し、もう一方のコレクションには出現しない要素) を返します。</span><span class="sxs-lookup"><span data-stu-id="d5a0c-114">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="d5a0c-115">該当なし。</span><span class="sxs-lookup"><span data-stu-id="d5a0c-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d5a0c-116">交差</span><span class="sxs-lookup"><span data-stu-id="d5a0c-116">Intersect</span></span>|<span data-ttu-id="d5a0c-117">積集合 (2 つのコレクションのそれぞれに出現する要素) を返します。</span><span class="sxs-lookup"><span data-stu-id="d5a0c-117">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="d5a0c-118">該当なし。</span><span class="sxs-lookup"><span data-stu-id="d5a0c-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d5a0c-119">和集合</span><span class="sxs-lookup"><span data-stu-id="d5a0c-119">Union</span></span>|<span data-ttu-id="d5a0c-120">和集合 (2 つのコレクションのどちらかに出現する一意の要素) を返します。</span><span class="sxs-lookup"><span data-stu-id="d5a0c-120">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="d5a0c-121">該当なし。</span><span class="sxs-lookup"><span data-stu-id="d5a0c-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="d5a0c-122">セット操作の比較</span><span class="sxs-lookup"><span data-stu-id="d5a0c-122">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="d5a0c-123">Distinct</span><span class="sxs-lookup"><span data-stu-id="d5a0c-123">Distinct</span></span>  
 <span data-ttu-id="d5a0c-124">次の例は、文字のシーケンスに対する <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> メソッドの動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="d5a0c-124">The following example depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="d5a0c-125">返されたシーケンスには、入力シーケンスからの一意の要素が格納されています。</span><span class="sxs-lookup"><span data-stu-id="d5a0c-125">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 ![Distinct&#40;&#41; の動作を示すグラフィック。](./media/set-operations/distinct-method-behavior.png)  
 
 [!code-csharp-interactive[Distinct](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#1)]
  
### <a name="except"></a><span data-ttu-id="d5a0c-127">除く</span><span class="sxs-lookup"><span data-stu-id="d5a0c-127">Except</span></span>  
 <span data-ttu-id="d5a0c-128">次の例で、<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType> の動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="d5a0c-128">The following example depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d5a0c-129">返されたシーケンスには、1 つ目の入力シーケンスのうち、2 つ目の入力シーケンスには存在しない要素が格納されています。</span><span class="sxs-lookup"><span data-stu-id="d5a0c-129">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="d5a0c-130">![Except&#40;&#41; のアクションを示すグラフィック。](./media/set-operations/except-behavior-graphic.png "Except の動作を示します。")</span><span class="sxs-lookup"><span data-stu-id="d5a0c-130">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>  
  
[!code-csharp-interactive[Except](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#2)]

### <a name="intersect"></a><span data-ttu-id="d5a0c-131">交差</span><span class="sxs-lookup"><span data-stu-id="d5a0c-131">Intersect</span></span>  
 <span data-ttu-id="d5a0c-132">次の例で、<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType> の動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="d5a0c-132">The following example depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d5a0c-133">返されたシーケンスには、両方の入力シーケンスに共通する要素が格納されています。</span><span class="sxs-lookup"><span data-stu-id="d5a0c-133">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 ![2 つのシーケンスの交差部分を示すグラフィック。](./media/set-operations/intersection-two-sequences.png)  
 
[!code-csharp-interactive[Intersect](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#3)]

### <a name="union"></a><span data-ttu-id="d5a0c-135">和集合</span><span class="sxs-lookup"><span data-stu-id="d5a0c-135">Union</span></span>  
 <span data-ttu-id="d5a0c-136">次の例は、2 つの文字シーケンスに対する和集合演算を示しています。</span><span class="sxs-lookup"><span data-stu-id="d5a0c-136">The following example depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="d5a0c-137">返されたシーケンスには、両方の入力シーケンスからの一意の要素が格納されています。</span><span class="sxs-lookup"><span data-stu-id="d5a0c-137">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 ![2 つのシーケンスの結合を示すグラフィック。](./media/set-operations/union-operation-two-sequences.png)  

[!code-csharp-interactive[Union](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#4)]
 
## <a name="see-also"></a><span data-ttu-id="d5a0c-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5a0c-139">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="d5a0c-140">標準クエリ演算子の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="d5a0c-140">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="d5a0c-141">文字列コレクションを結合および比較する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="d5a0c-141">How to combine and compare string collections (LINQ) (C#)</span></span>](./how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="d5a0c-142">2 つのリストの差集合を見つける方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="d5a0c-142">How to find the set difference between two lists (LINQ) (C#)</span></span>](./how-to-find-the-set-difference-between-two-lists-linq.md)
