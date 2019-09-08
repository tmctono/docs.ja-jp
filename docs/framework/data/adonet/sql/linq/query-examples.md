---
title: クエリの例
ms.date: 03/30/2017
ms.assetid: 137f8677-494c-4d49-95ce-c17742f2d01f
ms.openlocfilehash: 8f86c4aa94dcc70ce79526b0f4a3685cfef3f389
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781139"
---
# <a name="query-examples"></a><span data-ttu-id="45377-102">クエリの例</span><span class="sxs-lookup"><span data-stu-id="45377-102">Query Examples</span></span>
<span data-ttu-id="45377-103">ここでは、一般的C# [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]なクエリの Visual Basic と例について説明します。</span><span class="sxs-lookup"><span data-stu-id="45377-103">This section provides Visual Basic and C# examples of typical [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries.</span></span> <span data-ttu-id="45377-104">Visual Studio を使用する開発者は、「サンプル」セクションで紹介されているサンプルソリューションの多くの例を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="45377-104">Developers using Visual Studio can find many more examples in a sample solution available in the Samples section.</span></span> <span data-ttu-id="45377-105">詳細については、「[サンプル](samples.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45377-105">For more information, see [Samples](samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="45377-106">*db*は、ドキュメントの[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]コード例でよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="45377-106">*db* is often used in code examples in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation.</span></span> <span data-ttu-id="45377-107">*db*は、から<xref:System.Data.Linq.DataContext>継承される*Northwind*クラスのインスタンスであると見なされます。</span><span class="sxs-lookup"><span data-stu-id="45377-107">*db* is assumed to be an instance of a *Northwind* class, which inherits from <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="45377-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="45377-108">In This Section</span></span>  
 [<span data-ttu-id="45377-109">集計クエリ</span><span class="sxs-lookup"><span data-stu-id="45377-109">Aggregate Queries</span></span>](aggregate-queries.md)  
 <span data-ttu-id="45377-110"><xref:System.Linq.Enumerable.Average%2A>、<xref:System.Linq.Enumerable.Count%2A> などの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="45377-110">Describes how to use <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, and so forth.</span></span>  
  
 [<span data-ttu-id="45377-111">シーケンスの最初の要素の取得</span><span class="sxs-lookup"><span data-stu-id="45377-111">Return the First Element in a Sequence</span></span>](return-the-first-element-in-a-sequence.md)  
 <span data-ttu-id="45377-112"><xref:System.Linq.Enumerable.First%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="45377-112">Provides examples of using <xref:System.Linq.Enumerable.First%2A>.</span></span>  
  
 [<span data-ttu-id="45377-113">シーケンスの要素の取得またはスキップ</span><span class="sxs-lookup"><span data-stu-id="45377-113">Return Or Skip Elements in a Sequence</span></span>](return-or-skip-elements-in-a-sequence.md)  
 <span data-ttu-id="45377-114"><xref:System.Linq.Enumerable.Take%2A> および <xref:System.Linq.Enumerable.Skip%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="45377-114">Provides examples of using <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A>.</span></span>  
  
 [<span data-ttu-id="45377-115">シーケンスの要素の並べ替え</span><span class="sxs-lookup"><span data-stu-id="45377-115">Sort Elements in a Sequence</span></span>](sort-elements-in-a-sequence.md)  
 <span data-ttu-id="45377-116"><xref:System.Linq.Enumerable.OrderBy%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="45377-116">Provides examples of using <xref:System.Linq.Enumerable.OrderBy%2A>.</span></span>  
  
 [<span data-ttu-id="45377-117">シーケンスの要素のグループ化</span><span class="sxs-lookup"><span data-stu-id="45377-117">Group Elements in a Sequence</span></span>](group-elements-in-a-sequence.md)  
 <span data-ttu-id="45377-118"><xref:System.Linq.Enumerable.GroupBy%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="45377-118">Provides examples of using <xref:System.Linq.Enumerable.GroupBy%2A>.</span></span>  
  
 [<span data-ttu-id="45377-119">シーケンスからの重複する要素の削除</span><span class="sxs-lookup"><span data-stu-id="45377-119">Eliminate Duplicate Elements from a Sequence</span></span>](eliminate-duplicate-elements-from-a-sequence.md)  
 <span data-ttu-id="45377-120"><xref:System.Linq.Enumerable.Distinct%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="45377-120">Provides examples of using <xref:System.Linq.Enumerable.Distinct%2A>.</span></span>  
  
 [<span data-ttu-id="45377-121">シーケンスのすべての要素が条件を満たしているかどうかの確認</span><span class="sxs-lookup"><span data-stu-id="45377-121">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>](determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition.md)  
 <span data-ttu-id="45377-122"><xref:System.Linq.Enumerable.All%2A> および <xref:System.Linq.Enumerable.Any%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="45377-122">Provides examples of using <xref:System.Linq.Enumerable.All%2A> and <xref:System.Linq.Enumerable.Any%2A>.</span></span>  
  
 [<span data-ttu-id="45377-123">2 つのシーケンスの連結</span><span class="sxs-lookup"><span data-stu-id="45377-123">Concatenate Two Sequences</span></span>](concatenate-two-sequences.md)  
 <span data-ttu-id="45377-124"><xref:System.Linq.Enumerable.Concat%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="45377-124">Provides examples of using <xref:System.Linq.Enumerable.Concat%2A>.</span></span>  
  
 [<span data-ttu-id="45377-125">2 つのシーケンスの差集合の取得</span><span class="sxs-lookup"><span data-stu-id="45377-125">Return the Set Difference Between Two Sequences</span></span>](return-the-set-difference-between-two-sequences.md)  
 <span data-ttu-id="45377-126"><xref:System.Linq.Enumerable.Except%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="45377-126">Provides examples of using <xref:System.Linq.Enumerable.Except%2A>.</span></span>  
  
 [<span data-ttu-id="45377-127">2 つのシーケンスの積集合の取得</span><span class="sxs-lookup"><span data-stu-id="45377-127">Return the Set Intersection of Two Sequences</span></span>](return-the-set-intersection-of-two-sequences.md)  
 <span data-ttu-id="45377-128"><xref:System.Linq.Enumerable.Intersect%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="45377-128">Provides examples of using <xref:System.Linq.Enumerable.Intersect%2A>.</span></span>  
  
 [<span data-ttu-id="45377-129">2 つのシーケンスの和集合の取得</span><span class="sxs-lookup"><span data-stu-id="45377-129">Return the Set Union of Two Sequences</span></span>](return-the-set-union-of-two-sequences.md)  
 <span data-ttu-id="45377-130"><xref:System.Linq.Enumerable.Union%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="45377-130">Provides examples of using <xref:System.Linq.Enumerable.Union%2A>.</span></span>  
  
 [<span data-ttu-id="45377-131">方法 : シーケンスを配列に変換する</span><span class="sxs-lookup"><span data-stu-id="45377-131">Convert a Sequence to an Array</span></span>](convert-a-sequence-to-an-array.md)  
 <span data-ttu-id="45377-132"><xref:System.Linq.Enumerable.ToArray%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="45377-132">Provides examples of using <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>  
  
 [<span data-ttu-id="45377-133">ジェネリック リストへのシーケンスの変換</span><span class="sxs-lookup"><span data-stu-id="45377-133">Convert a Sequence to a Generic List</span></span>](convert-a-sequence-to-a-generic-list.md)  
 <span data-ttu-id="45377-134"><xref:System.Linq.Enumerable.ToList%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="45377-134">Provides examples of using <xref:System.Linq.Enumerable.ToList%2A>.</span></span>  
  
 [<span data-ttu-id="45377-135">汎用 IEnumerable への型の変換</span><span class="sxs-lookup"><span data-stu-id="45377-135">Convert a Type to a Generic IEnumerable</span></span>](convert-a-type-to-a-generic-ienumerable.md)  
 <span data-ttu-id="45377-136"><xref:System.Linq.Enumerable.AsEnumerable%2A> の使用例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="45377-136">Provides examples of using <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span></span>  
  
 [<span data-ttu-id="45377-137">結合およびクロス積クエリの作成</span><span class="sxs-lookup"><span data-stu-id="45377-137">Formulate Joins and Cross-Product Queries</span></span>](formulate-joins-and-cross-product-queries.md)  
 <span data-ttu-id="45377-138">`from` 句、`where` 句、および `select` 句で外部キーを移動する方法の例を示して説明します。</span><span class="sxs-lookup"><span data-stu-id="45377-138">Provides examples of using foreign-key navigation in the `from`, `where`, and `select` clauses.</span></span>  
  
 [<span data-ttu-id="45377-139">射影の作成</span><span class="sxs-lookup"><span data-stu-id="45377-139">Formulate Projections</span></span>](formulate-projections.md)  
 <span data-ttu-id="45377-140">クエリプロジェクションを形成`select`するために、他の機能 (*匿名型*など) と組み合わせて使用する例を示します。</span><span class="sxs-lookup"><span data-stu-id="45377-140">Provides examples of combining `select` with other features (for example, *anonymous types*) to form query projections.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="45377-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="45377-141">Related Sections</span></span>  
 [<span data-ttu-id="45377-142">標準クエリ演算子の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="45377-142">Standard Query Operators Overview (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 <span data-ttu-id="45377-143">を使用C#した標準クエリ演算子の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="45377-143">Explains the concept of standard query operators using C#.</span></span>  
  
 [<span data-ttu-id="45377-144">標準クエリ演算子の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="45377-144">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 <span data-ttu-id="45377-145">Visual Basic を使用した標準クエリ演算子の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="45377-145">Explains the concept of standard query operators using Visual Basic.</span></span>  
  
 [<span data-ttu-id="45377-146">クエリの概念</span><span class="sxs-lookup"><span data-stu-id="45377-146">Query Concepts</span></span>](query-concepts.md)  
 <span data-ttu-id="45377-147">クエリに関する概念が [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] でどのように使用されるかを説明します。</span><span class="sxs-lookup"><span data-stu-id="45377-147">Explains how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uses concepts that apply to queries.</span></span>  
  
 [<span data-ttu-id="45377-148">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="45377-148">Programming Guide</span></span>](programming-guide.md)  
 <span data-ttu-id="45377-149">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] に関連するプログラミングの概念を説明するトピックへのポータルです。</span><span class="sxs-lookup"><span data-stu-id="45377-149">Provides a portal to topics that explain programming concepts related to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
