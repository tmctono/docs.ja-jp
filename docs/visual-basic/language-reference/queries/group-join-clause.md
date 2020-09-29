---
title: Group Join 句
ms.date: 07/20/2015
f1_keywords:
- vb.QueryGroupJoinIn
- vb.QueryGroupJoinOn
- vb.QueryGroupJoin
- vb.QueryGroupJoinInto
helpviewer_keywords:
- Group Join clause [Visual Basic]
- Group Join statement [Visual Basic]
- queries [Visual Basic], Group Join
ms.assetid: 37dbf79c-7b5c-421b-bbb7-dadfd2b92a1c
ms.openlocfilehash: 8d5f3ec80cb39825a3a283907d614b9be28e6e91
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869910"
---
# <a name="group-join-clause-visual-basic"></a><span data-ttu-id="7a47c-102">Group Join 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a47c-102">Group Join Clause (Visual Basic)</span></span>

<span data-ttu-id="7a47c-103">2 つのコレクションを、単一の階層コレクションに結合します。</span><span class="sxs-lookup"><span data-stu-id="7a47c-103">Combines two collections into a single hierarchical collection.</span></span> <span data-ttu-id="7a47c-104">結合操作は、一致するキーに基づきます。</span><span class="sxs-lookup"><span data-stu-id="7a47c-104">The join operation is based on matching keys.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a47c-105">構文</span><span class="sxs-lookup"><span data-stu-id="7a47c-105">Syntax</span></span>  
  
```vb  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## <a name="parts"></a><span data-ttu-id="7a47c-106">指定項目</span><span class="sxs-lookup"><span data-stu-id="7a47c-106">Parts</span></span>  
  
|<span data-ttu-id="7a47c-107">用語</span><span class="sxs-lookup"><span data-stu-id="7a47c-107">Term</span></span>|<span data-ttu-id="7a47c-108">定義</span><span class="sxs-lookup"><span data-stu-id="7a47c-108">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="7a47c-109">必須です。</span><span class="sxs-lookup"><span data-stu-id="7a47c-109">Required.</span></span> <span data-ttu-id="7a47c-110">結合されるコレクションの制御変数。</span><span class="sxs-lookup"><span data-stu-id="7a47c-110">The control variable for the collection being joined.</span></span>|  
|`type`|<span data-ttu-id="7a47c-111">任意。</span><span class="sxs-lookup"><span data-stu-id="7a47c-111">Optional.</span></span> <span data-ttu-id="7a47c-112">`element` の型。</span><span class="sxs-lookup"><span data-stu-id="7a47c-112">The type of `element`.</span></span> <span data-ttu-id="7a47c-113">`type` が指定されていない場合、`element` の型は `collection` から推論されます。</span><span class="sxs-lookup"><span data-stu-id="7a47c-113">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="7a47c-114">必須です。</span><span class="sxs-lookup"><span data-stu-id="7a47c-114">Required.</span></span> <span data-ttu-id="7a47c-115">`Group Join` 演算子の左側にあるコレクションと結合するコレクション。</span><span class="sxs-lookup"><span data-stu-id="7a47c-115">The collection to combine with the collection that is on the left side of the `Group Join` operator.</span></span> <span data-ttu-id="7a47c-116">`Group Join` 句は、`Join` 句、または別の `Group Join` 句で入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7a47c-116">A `Group Join` clause can be nested in a `Join` clause or in another `Group Join` clause.</span></span>|  
|<span data-ttu-id="7a47c-117">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="7a47c-117">`key1` `Equals` `key2`</span></span>|<span data-ttu-id="7a47c-118">必須です。</span><span class="sxs-lookup"><span data-stu-id="7a47c-118">Required.</span></span> <span data-ttu-id="7a47c-119">結合されるコレクションのキーを識別します。</span><span class="sxs-lookup"><span data-stu-id="7a47c-119">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="7a47c-120">`Equals` 演算子を使用して、結合されるコレクションのキーを比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a47c-120">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="7a47c-121">結合条件を組み合わせるには、複数のキーを識別するために、`And` 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="7a47c-121">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="7a47c-122">`key1` パラメーターは、`Join` 演算子の左側にあるコレクションからのものである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a47c-122">The `key1` parameter must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="7a47c-123">`key2` パラメーターは、`Join` 演算子の右側にあるコレクションからのものである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a47c-123">The `key2` parameter must be from the collection on the right side of the `Join` operator.</span></span><br /><br /> <span data-ttu-id="7a47c-124">結合条件で使用されるキーは、コレクションからの複数の項目を含む式にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7a47c-124">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="7a47c-125">ただし、各キー式には、それぞれのコレクションからの項目のみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="7a47c-125">However, each key expression can contain only items from its respective collection.</span></span>|  
|`expressionList`|<span data-ttu-id="7a47c-126">必須です。</span><span class="sxs-lookup"><span data-stu-id="7a47c-126">Required.</span></span> <span data-ttu-id="7a47c-127">コレクションの要素のグループを集計する方法を示す 1 つ以上の式です。</span><span class="sxs-lookup"><span data-stu-id="7a47c-127">One or more expressions that identify how the groups of elements from the collection are aggregated.</span></span> <span data-ttu-id="7a47c-128">グループ化された結果のメンバー名を特定するには、`Group` キーワード (`<alias> = Group`) を使用します。</span><span class="sxs-lookup"><span data-stu-id="7a47c-128">To identify a member name for the grouped results, use the `Group` keyword (`<alias> = Group`).</span></span> <span data-ttu-id="7a47c-129">グループに適用する集計関数を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="7a47c-129">You can also include aggregate functions to apply to the group.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a47c-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="7a47c-130">Remarks</span></span>  

 <span data-ttu-id="7a47c-131">`Group Join` 句は、結合されるコレクションからの一致するキー値に基づいて、2 つのコレクションを組み合わせます。</span><span class="sxs-lookup"><span data-stu-id="7a47c-131">The `Group Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="7a47c-132">結果のコレクションには、最初のコレクションのキー値に一致する 2 つ目のコレクションの要素のコレクションを参照するメンバーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="7a47c-132">The resulting collection can contain a member that references a collection of elements from the second collection that match the key value from the first collection.</span></span> <span data-ttu-id="7a47c-133">さらに、2 つ目のコレクションのグループ化された要素に適用する集計関数を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="7a47c-133">You can also specify aggregate functions to apply to the grouped elements from the second collection.</span></span> <span data-ttu-id="7a47c-134">集計関数の詳細については、「[Aggregate 句 ](aggregate-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a47c-134">For information about aggregate functions, see [Aggregate Clause](aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="7a47c-135">たとえば、マネージャーのコレクションと従業員のコレクションを考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="7a47c-135">Consider, for example, a collection of managers and a collection of employees.</span></span> <span data-ttu-id="7a47c-136">両方のコレクションの要素には、特定のマネージャーに報告する従業員を識別する ManagerID プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="7a47c-136">Elements from both collections have a ManagerID property that identifies the employees that report to a particular manager.</span></span> <span data-ttu-id="7a47c-137">結合操作の結果には、一致する ManagerID 値を持つ各マネージャーと従業員の結果が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7a47c-137">The results from a join operation would contain a result for each manager and employee with a matching ManagerID value.</span></span> <span data-ttu-id="7a47c-138">`Group Join` 操作の結果には、マネージャーの完全な一覧が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7a47c-138">The results from a `Group Join` operation would contain the complete list of managers.</span></span> <span data-ttu-id="7a47c-139">各マネージャーの結果には、特定のマネージャーに一致した従業員の一覧を参照したメンバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7a47c-139">Each manager result would have a member that referenced the list of employees that were a match for the specific manager.</span></span>  
  
 <span data-ttu-id="7a47c-140">`Group Join` 操作の結果のコレクションには、`From` 句に指定されたコレクションと `Group Join` 句の `Into` 句に指定された式からの値の任意の組み合わせが含まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7a47c-140">The collection resulting from a `Group Join` operation can contain any combination of values from the collection identified in the `From` clause and the expressions identified in the `Into` clause of the `Group Join` clause.</span></span> <span data-ttu-id="7a47c-141">`Into` 句の有効な式の詳細については、「[Aggregate 句](aggregate-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a47c-141">For more information about valid expressions for the `Into` clause, see [Aggregate Clause](aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="7a47c-142">`Group Join` 操作では、`Group Join` 演算子の左側に指定されたコレクションからのすべての結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="7a47c-142">A `Group Join` operation will return all results from the collection identified on the left side of the `Group Join` operator.</span></span> <span data-ttu-id="7a47c-143">これは、結合されているコレクションに一致するものがない場合でも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="7a47c-143">This is true even if there are no matches in the collection being joined.</span></span> <span data-ttu-id="7a47c-144">これは、SQL の `LEFT OUTER JOIN` に似ています。</span><span class="sxs-lookup"><span data-stu-id="7a47c-144">This is like a `LEFT OUTER JOIN` in SQL.</span></span>  
  
 <span data-ttu-id="7a47c-145">`Join` 句を使用して、コレクションを単一のコレクションに結合することができます。</span><span class="sxs-lookup"><span data-stu-id="7a47c-145">You can use the `Join` clause to combine collections into a single collection.</span></span> <span data-ttu-id="7a47c-146">これは、SQL の `INNER JOIN` と同じです。</span><span class="sxs-lookup"><span data-stu-id="7a47c-146">This is equivalent to an `INNER JOIN` in SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a47c-147">例</span><span class="sxs-lookup"><span data-stu-id="7a47c-147">Example</span></span>  

 <span data-ttu-id="7a47c-148">次のコード例では、`Group Join` 句を使用して 2 つのコレクションを結合しています。</span><span class="sxs-lookup"><span data-stu-id="7a47c-148">The following code example joins two collections by using the `Group Join` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="7a47c-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a47c-149">See also</span></span>

- [<span data-ttu-id="7a47c-150">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="7a47c-150">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="7a47c-151">クエリ</span><span class="sxs-lookup"><span data-stu-id="7a47c-151">Queries</span></span>](index.md)
- [<span data-ttu-id="7a47c-152">Select 句</span><span class="sxs-lookup"><span data-stu-id="7a47c-152">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="7a47c-153">From 句</span><span class="sxs-lookup"><span data-stu-id="7a47c-153">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="7a47c-154">Join 句</span><span class="sxs-lookup"><span data-stu-id="7a47c-154">Join Clause</span></span>](join-clause.md)
- [<span data-ttu-id="7a47c-155">WHERE 句</span><span class="sxs-lookup"><span data-stu-id="7a47c-155">Where Clause</span></span>](where-clause.md)
- [<span data-ttu-id="7a47c-156">Group By 句</span><span class="sxs-lookup"><span data-stu-id="7a47c-156">Group By Clause</span></span>](group-by-clause.md)
