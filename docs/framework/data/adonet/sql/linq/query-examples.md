---
title: クエリの例
ms.date: 03/30/2017
ms.assetid: 137f8677-494c-4d49-95ce-c17742f2d01f
ms.openlocfilehash: f3f135850fb5f40b3b8882f72f5cc24512f21084
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147555"
---
# <a name="query-examples"></a><span data-ttu-id="1e0cc-102">クエリの例</span><span class="sxs-lookup"><span data-stu-id="1e0cc-102">Query Examples</span></span>

<span data-ttu-id="1e0cc-103">このセクションでは、Visual Basic および C# で一般的な [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] クエリの例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-103">This section provides Visual Basic and C# examples of typical [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries.</span></span> <span data-ttu-id="1e0cc-104">Visual Studio を使用している場合は、「サンプル」セクションに多数のサンプル ソリューションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-104">Developers using Visual Studio can find many more examples in a sample solution available in the Samples section.</span></span> <span data-ttu-id="1e0cc-105">詳細については、「[サンプル](samples.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-105">For more information, see [Samples](samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1e0cc-106">*db* は、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ドキュメントのコード サンプルでよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-106">*db* is often used in code examples in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation.</span></span> <span data-ttu-id="1e0cc-107">*db* は、*Northwind* クラスのインスタンスであることが前提です。このクラスは、<xref:System.Data.Linq.DataContext> から継承されます。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-107">*db* is assumed to be an instance of a *Northwind* class, which inherits from <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1e0cc-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1e0cc-108">In This Section</span></span>  

 [<span data-ttu-id="1e0cc-109">集計クエリ</span><span class="sxs-lookup"><span data-stu-id="1e0cc-109">Aggregate Queries</span></span>](aggregate-queries.md)  
 <span data-ttu-id="1e0cc-110"><xref:System.Linq.Enumerable.Average%2A>、<xref:System.Linq.Enumerable.Count%2A> などの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-110">Describes how to use <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, and so forth.</span></span>  
  
 [<span data-ttu-id="1e0cc-111">シーケンスの最初の要素の取得</span><span class="sxs-lookup"><span data-stu-id="1e0cc-111">Return the First Element in a Sequence</span></span>](return-the-first-element-in-a-sequence.md)  
 <span data-ttu-id="1e0cc-112"><xref:System.Linq.Enumerable.First%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-112">Provides examples of using <xref:System.Linq.Enumerable.First%2A>.</span></span>  
  
 [<span data-ttu-id="1e0cc-113">シーケンスの要素の取得またはスキップ</span><span class="sxs-lookup"><span data-stu-id="1e0cc-113">Return Or Skip Elements in a Sequence</span></span>](return-or-skip-elements-in-a-sequence.md)  
 <span data-ttu-id="1e0cc-114"><xref:System.Linq.Enumerable.Take%2A> および <xref:System.Linq.Enumerable.Skip%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-114">Provides examples of using <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A>.</span></span>  
  
 [<span data-ttu-id="1e0cc-115">シーケンスの要素の並べ替え</span><span class="sxs-lookup"><span data-stu-id="1e0cc-115">Sort Elements in a Sequence</span></span>](sort-elements-in-a-sequence.md)  
 <span data-ttu-id="1e0cc-116"><xref:System.Linq.Enumerable.OrderBy%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-116">Provides examples of using <xref:System.Linq.Enumerable.OrderBy%2A>.</span></span>  
  
 [<span data-ttu-id="1e0cc-117">シーケンスの要素のグループ化</span><span class="sxs-lookup"><span data-stu-id="1e0cc-117">Group Elements in a Sequence</span></span>](group-elements-in-a-sequence.md)  
 <span data-ttu-id="1e0cc-118"><xref:System.Linq.Enumerable.GroupBy%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-118">Provides examples of using <xref:System.Linq.Enumerable.GroupBy%2A>.</span></span>  
  
 [<span data-ttu-id="1e0cc-119">シーケンスからの重複する要素の削除</span><span class="sxs-lookup"><span data-stu-id="1e0cc-119">Eliminate Duplicate Elements from a Sequence</span></span>](eliminate-duplicate-elements-from-a-sequence.md)  
 <span data-ttu-id="1e0cc-120"><xref:System.Linq.Enumerable.Distinct%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-120">Provides examples of using <xref:System.Linq.Enumerable.Distinct%2A>.</span></span>  
  
 [<span data-ttu-id="1e0cc-121">シーケンスのすべての要素が条件を満たしているかどうかの確認</span><span class="sxs-lookup"><span data-stu-id="1e0cc-121">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>](determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition.md)  
 <span data-ttu-id="1e0cc-122"><xref:System.Linq.Enumerable.All%2A> および <xref:System.Linq.Enumerable.Any%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-122">Provides examples of using <xref:System.Linq.Enumerable.All%2A> and <xref:System.Linq.Enumerable.Any%2A>.</span></span>  
  
 [<span data-ttu-id="1e0cc-123">2 つのシーケンスの連結</span><span class="sxs-lookup"><span data-stu-id="1e0cc-123">Concatenate Two Sequences</span></span>](concatenate-two-sequences.md)  
 <span data-ttu-id="1e0cc-124"><xref:System.Linq.Enumerable.Concat%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-124">Provides examples of using <xref:System.Linq.Enumerable.Concat%2A>.</span></span>  
  
 [<span data-ttu-id="1e0cc-125">2 つのシーケンスの差集合の取得</span><span class="sxs-lookup"><span data-stu-id="1e0cc-125">Return the Set Difference Between Two Sequences</span></span>](return-the-set-difference-between-two-sequences.md)  
 <span data-ttu-id="1e0cc-126"><xref:System.Linq.Enumerable.Except%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-126">Provides examples of using <xref:System.Linq.Enumerable.Except%2A>.</span></span>  
  
 [<span data-ttu-id="1e0cc-127">2 つのシーケンスの積集合の取得</span><span class="sxs-lookup"><span data-stu-id="1e0cc-127">Return the Set Intersection of Two Sequences</span></span>](return-the-set-intersection-of-two-sequences.md)  
 <span data-ttu-id="1e0cc-128"><xref:System.Linq.Enumerable.Intersect%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-128">Provides examples of using <xref:System.Linq.Enumerable.Intersect%2A>.</span></span>  
  
 [<span data-ttu-id="1e0cc-129">2 つのシーケンスの和集合の取得</span><span class="sxs-lookup"><span data-stu-id="1e0cc-129">Return the Set Union of Two Sequences</span></span>](return-the-set-union-of-two-sequences.md)  
 <span data-ttu-id="1e0cc-130"><xref:System.Linq.Enumerable.Union%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-130">Provides examples of using <xref:System.Linq.Enumerable.Union%2A>.</span></span>  
  
 [<span data-ttu-id="1e0cc-131">方法 : シーケンスを配列に変換する</span><span class="sxs-lookup"><span data-stu-id="1e0cc-131">Convert a Sequence to an Array</span></span>](convert-a-sequence-to-an-array.md)  
 <span data-ttu-id="1e0cc-132"><xref:System.Linq.Enumerable.ToArray%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-132">Provides examples of using <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>  
  
 [<span data-ttu-id="1e0cc-133">ジェネリック リストへのシーケンスの変換</span><span class="sxs-lookup"><span data-stu-id="1e0cc-133">Convert a Sequence to a Generic List</span></span>](convert-a-sequence-to-a-generic-list.md)  
 <span data-ttu-id="1e0cc-134"><xref:System.Linq.Enumerable.ToList%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-134">Provides examples of using <xref:System.Linq.Enumerable.ToList%2A>.</span></span>  
  
 [<span data-ttu-id="1e0cc-135">汎用 IEnumerable への型の変換</span><span class="sxs-lookup"><span data-stu-id="1e0cc-135">Convert a Type to a Generic IEnumerable</span></span>](convert-a-type-to-a-generic-ienumerable.md)  
 <span data-ttu-id="1e0cc-136"><xref:System.Linq.Enumerable.AsEnumerable%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-136">Provides examples of using <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span></span>  
  
 [<span data-ttu-id="1e0cc-137">結合およびクロス積クエリの作成</span><span class="sxs-lookup"><span data-stu-id="1e0cc-137">Formulate Joins and Cross-Product Queries</span></span>](formulate-joins-and-cross-product-queries.md)  
 <span data-ttu-id="1e0cc-138">`from` 句、`where` 句、および `select` 句で外部キーを移動する方法の例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-138">Provides examples of using foreign-key navigation in the `from`, `where`, and `select` clauses.</span></span>  
  
 [<span data-ttu-id="1e0cc-139">射影の作成</span><span class="sxs-lookup"><span data-stu-id="1e0cc-139">Formulate Projections</span></span>](formulate-projections.md)  
 <span data-ttu-id="1e0cc-140">`select` と他の機能 (*匿名型*など) を組み合わせてクエリ射影を作成する方法の例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-140">Provides examples of combining `select` with other features (for example, *anonymous types*) to form query projections.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1e0cc-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e0cc-141">Related Sections</span></span>  

 [<span data-ttu-id="1e0cc-142">標準クエリ演算子の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="1e0cc-142">Standard Query Operators Overview (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 <span data-ttu-id="1e0cc-143">C# を使用した標準クエリ演算子の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-143">Explains the concept of standard query operators using C#.</span></span>  
  
 [<span data-ttu-id="1e0cc-144">標準クエリ演算子の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e0cc-144">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 <span data-ttu-id="1e0cc-145">Visual Basic を使用した標準クエリ演算子の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-145">Explains the concept of standard query operators using Visual Basic.</span></span>  
  
 [<span data-ttu-id="1e0cc-146">クエリの概念</span><span class="sxs-lookup"><span data-stu-id="1e0cc-146">Query Concepts</span></span>](query-concepts.md)  
 <span data-ttu-id="1e0cc-147">クエリに関する概念が [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] でどのように使用されるかを説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-147">Explains how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uses concepts that apply to queries.</span></span>  
  
 [<span data-ttu-id="1e0cc-148">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="1e0cc-148">Programming Guide</span></span>](programming-guide.md)  
 <span data-ttu-id="1e0cc-149">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] に関連するプログラミングの概念を説明するトピックへのポータルです。</span><span class="sxs-lookup"><span data-stu-id="1e0cc-149">Provides a portal to topics that explain programming concepts related to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
