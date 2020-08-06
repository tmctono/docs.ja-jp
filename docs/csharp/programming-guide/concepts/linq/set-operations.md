---
title: セット操作 (C#)
description: セット操作について、および C# の LINQ でセット操作を実行する標準クエリ演算子メソッドについて説明します。
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: ab2608b267113ad5d47a33e64cd9a5e21496f668
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302374"
---
# <a name="set-operations-c"></a><span data-ttu-id="2d1d6-103">セット操作 (C#)</span><span class="sxs-lookup"><span data-stu-id="2d1d6-103">Set Operations (C#)</span></span>
<span data-ttu-id="2d1d6-104">LINQ のセット操作は、同一または別個のコレクション (またはセット) に等しい要素があるかどうかに基づいて、結果を生成するクエリ操作です。</span><span class="sxs-lookup"><span data-stu-id="2d1d6-104">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="2d1d6-105">次のセクションでは、セット操作を実行する標準クエリ演算子のメソッドの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="2d1d6-105">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2d1d6-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="2d1d6-106">Methods</span></span>  
  
|<span data-ttu-id="2d1d6-107">メソッド名</span><span class="sxs-lookup"><span data-stu-id="2d1d6-107">Method Name</span></span>|<span data-ttu-id="2d1d6-108">説明</span><span class="sxs-lookup"><span data-stu-id="2d1d6-108">Description</span></span>|<span data-ttu-id="2d1d6-109">C# のクエリ式の構文</span><span class="sxs-lookup"><span data-stu-id="2d1d6-109">C# Query Expression Syntax</span></span>|<span data-ttu-id="2d1d6-110">説明</span><span class="sxs-lookup"><span data-stu-id="2d1d6-110">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="2d1d6-111">Distinct</span><span class="sxs-lookup"><span data-stu-id="2d1d6-111">Distinct</span></span>|<span data-ttu-id="2d1d6-112">コレクションから重複する値を削除します。</span><span class="sxs-lookup"><span data-stu-id="2d1d6-112">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="2d1d6-113">該当なし。</span><span class="sxs-lookup"><span data-stu-id="2d1d6-113">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="2d1d6-114">除く</span><span class="sxs-lookup"><span data-stu-id="2d1d6-114">Except</span></span>|<span data-ttu-id="2d1d6-115">差集合 (一方のコレクションにだけ存在し、もう一方のコレクションには出現しない要素) を返します。</span><span class="sxs-lookup"><span data-stu-id="2d1d6-115">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="2d1d6-116">該当なし。</span><span class="sxs-lookup"><span data-stu-id="2d1d6-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="2d1d6-117">交差</span><span class="sxs-lookup"><span data-stu-id="2d1d6-117">Intersect</span></span>|<span data-ttu-id="2d1d6-118">積集合 (2 つのコレクションのそれぞれに出現する要素) を返します。</span><span class="sxs-lookup"><span data-stu-id="2d1d6-118">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="2d1d6-119">該当なし。</span><span class="sxs-lookup"><span data-stu-id="2d1d6-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="2d1d6-120">和集合</span><span class="sxs-lookup"><span data-stu-id="2d1d6-120">Union</span></span>|<span data-ttu-id="2d1d6-121">和集合 (2 つのコレクションのどちらかに出現する一意の要素) を返します。</span><span class="sxs-lookup"><span data-stu-id="2d1d6-121">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="2d1d6-122">該当なし。</span><span class="sxs-lookup"><span data-stu-id="2d1d6-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="2d1d6-123">セット操作の比較</span><span class="sxs-lookup"><span data-stu-id="2d1d6-123">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="2d1d6-124">Distinct</span><span class="sxs-lookup"><span data-stu-id="2d1d6-124">Distinct</span></span>  
 <span data-ttu-id="2d1d6-125">次の例は、文字のシーケンスに対する <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> メソッドの動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="2d1d6-125">The following example depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="2d1d6-126">返されたシーケンスには、入力シーケンスからの一意の要素が格納されています。</span><span class="sxs-lookup"><span data-stu-id="2d1d6-126">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 ![Distinct&#40;&#41; の動作を示すグラフィック。](./media/set-operations/distinct-method-behavior.png)  

 [!code-csharp-interactive[Distinct](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#1)]
  
### <a name="except"></a><span data-ttu-id="2d1d6-128">除く</span><span class="sxs-lookup"><span data-stu-id="2d1d6-128">Except</span></span>  
 <span data-ttu-id="2d1d6-129">次の例で、<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType> の動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="2d1d6-129">The following example depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2d1d6-130">返されたシーケンスには、1 つ目の入力シーケンスのうち、2 つ目の入力シーケンスには存在しない要素が格納されています。</span><span class="sxs-lookup"><span data-stu-id="2d1d6-130">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="2d1d6-131">![Except&#40;&#41; のアクションを示すグラフィック。](./media/set-operations/except-behavior-graphic.png "Except の動作を示します。")</span><span class="sxs-lookup"><span data-stu-id="2d1d6-131">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>  
  
[!code-csharp-interactive[Except](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#2)]

### <a name="intersect"></a><span data-ttu-id="2d1d6-132">交差</span><span class="sxs-lookup"><span data-stu-id="2d1d6-132">Intersect</span></span>  
 <span data-ttu-id="2d1d6-133">次の例で、<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType> の動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="2d1d6-133">The following example depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2d1d6-134">返されたシーケンスには、両方の入力シーケンスに共通する要素が格納されています。</span><span class="sxs-lookup"><span data-stu-id="2d1d6-134">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 ![2 つのシーケンスの交差部分を示すグラフィック。](./media/set-operations/intersection-two-sequences.png)  

[!code-csharp-interactive[Intersect](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#3)]

### <a name="union"></a><span data-ttu-id="2d1d6-136">和集合</span><span class="sxs-lookup"><span data-stu-id="2d1d6-136">Union</span></span>  
 <span data-ttu-id="2d1d6-137">次の例は、2 つの文字シーケンスに対する和集合演算を示しています。</span><span class="sxs-lookup"><span data-stu-id="2d1d6-137">The following example depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="2d1d6-138">返されたシーケンスには、両方の入力シーケンスからの一意の要素が格納されています。</span><span class="sxs-lookup"><span data-stu-id="2d1d6-138">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 ![2 つのシーケンスの結合を示すグラフィック。](./media/set-operations/union-operation-two-sequences.png)  

[!code-csharp-interactive[Union](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#4)]

## <a name="see-also"></a><span data-ttu-id="2d1d6-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d1d6-140">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="2d1d6-141">標準クエリ演算子の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="2d1d6-141">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="2d1d6-142">文字列コレクションを結合および比較する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="2d1d6-142">How to combine and compare string collections (LINQ) (C#)</span></span>](./how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="2d1d6-143">2 つのリストの差集合を見つける方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="2d1d6-143">How to find the set difference between two lists (LINQ) (C#)</span></span>](./how-to-find-the-set-difference-between-two-lists-linq.md)
