---
title: Group Join 句 (Visual Basic)
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
ms.openlocfilehash: 3da4ca2db299a65b2c0f1fa259bbaabe4f53aa33
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945315"
---
# <a name="group-join-clause-visual-basic"></a><span data-ttu-id="833a7-102">Group Join 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="833a7-102">Group Join Clause (Visual Basic)</span></span>
<span data-ttu-id="833a7-103">2 つのコレクションを、単一の階層コレクションに結合します。</span><span class="sxs-lookup"><span data-stu-id="833a7-103">Combines two collections into a single hierarchical collection.</span></span> <span data-ttu-id="833a7-104">結合操作は、一致するキーに基づきます。</span><span class="sxs-lookup"><span data-stu-id="833a7-104">The join operation is based on matching keys.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="833a7-105">構文</span><span class="sxs-lookup"><span data-stu-id="833a7-105">Syntax</span></span>  
  
```  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## <a name="parts"></a><span data-ttu-id="833a7-106">指定項目</span><span class="sxs-lookup"><span data-stu-id="833a7-106">Parts</span></span>  
  
|<span data-ttu-id="833a7-107">用語</span><span class="sxs-lookup"><span data-stu-id="833a7-107">Term</span></span>|<span data-ttu-id="833a7-108">定義</span><span class="sxs-lookup"><span data-stu-id="833a7-108">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="833a7-109">必須。</span><span class="sxs-lookup"><span data-stu-id="833a7-109">Required.</span></span> <span data-ttu-id="833a7-110">結合するコレクションの制御変数。</span><span class="sxs-lookup"><span data-stu-id="833a7-110">The control variable for the collection being joined.</span></span>|  
|`type`|<span data-ttu-id="833a7-111">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="833a7-111">Optional.</span></span> <span data-ttu-id="833a7-112">`element` の型。</span><span class="sxs-lookup"><span data-stu-id="833a7-112">The type of `element`.</span></span> <span data-ttu-id="833a7-113">ない場合は`type`を指定の種類`element`から推論されます`collection`します。</span><span class="sxs-lookup"><span data-stu-id="833a7-113">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="833a7-114">必須。</span><span class="sxs-lookup"><span data-stu-id="833a7-114">Required.</span></span> <span data-ttu-id="833a7-115">左側にある上にあるコレクションと結合するコレクション、`Group Join`演算子。</span><span class="sxs-lookup"><span data-stu-id="833a7-115">The collection to combine with the collection that is on the left side of the `Group Join` operator.</span></span> <span data-ttu-id="833a7-116">A`Group Join`に句を入れ子にすることができます、`Join`句または別の`Group Join`句。</span><span class="sxs-lookup"><span data-stu-id="833a7-116">A `Group Join` clause can be nested in a `Join` clause or in another `Group Join` clause.</span></span>|  
|<span data-ttu-id="833a7-117">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="833a7-117">`key1` `Equals` `key2`</span></span>|<span data-ttu-id="833a7-118">必須。</span><span class="sxs-lookup"><span data-stu-id="833a7-118">Required.</span></span> <span data-ttu-id="833a7-119">結合するコレクションのキーを識別します。</span><span class="sxs-lookup"><span data-stu-id="833a7-119">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="833a7-120">使用する必要があります、`Equals`結合されているコレクションからキーを比較する演算子。</span><span class="sxs-lookup"><span data-stu-id="833a7-120">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="833a7-121">使用して、結合条件を組み合わせることができます、`And`演算子を複数のキーを識別します。</span><span class="sxs-lookup"><span data-stu-id="833a7-121">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="833a7-122">`key1`の左側にあるコレクションからパラメーターがある必要があります、`Join`演算子。</span><span class="sxs-lookup"><span data-stu-id="833a7-122">The `key1` parameter must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="833a7-123">`key2`の右側にあるコレクションからパラメーターがある必要があります、`Join`演算子。</span><span class="sxs-lookup"><span data-stu-id="833a7-123">The `key2` parameter must be from the collection on the right side of the `Join` operator.</span></span><br /><br /> <span data-ttu-id="833a7-124">結合条件で使用されるキーは、コレクションの 1 つ以上の項目を含む式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="833a7-124">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="833a7-125">ただし、それぞれのキー式では、該当するコレクションの項目のみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="833a7-125">However, each key expression can contain only items from its respective collection.</span></span>|  
|`expressionList`|<span data-ttu-id="833a7-126">必須。</span><span class="sxs-lookup"><span data-stu-id="833a7-126">Required.</span></span> <span data-ttu-id="833a7-127">コレクションから要素のグループの集計方法を識別する 1 つまたは複数の式。</span><span class="sxs-lookup"><span data-stu-id="833a7-127">One or more expressions that identify how the groups of elements from the collection are aggregated.</span></span> <span data-ttu-id="833a7-128">グループ化した結果のメンバー名を識別するために使用して、`Group`キーワード (`<alias> = Group`)。</span><span class="sxs-lookup"><span data-stu-id="833a7-128">To identify a member name for the grouped results, use the `Group` keyword (`<alias> = Group`).</span></span> <span data-ttu-id="833a7-129">グループに適用する集計関数を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="833a7-129">You can also include aggregate functions to apply to the group.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="833a7-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="833a7-130">Remarks</span></span>  
 <span data-ttu-id="833a7-131">`Group Join`句が結合されているコレクションからのキー値と一致する 2 つのコレクションを結合します。</span><span class="sxs-lookup"><span data-stu-id="833a7-131">The `Group Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="833a7-132">結果のコレクションには、最初のコレクションからキー値に一致する 2 番目のコレクションから要素のコレクションを参照するメンバーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="833a7-132">The resulting collection can contain a member that references a collection of elements from the second collection that match the key value from the first collection.</span></span> <span data-ttu-id="833a7-133">2 番目のコレクションのグループ化された要素に適用する集計関数を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="833a7-133">You can also specify aggregate functions to apply to the grouped elements from the second collection.</span></span> <span data-ttu-id="833a7-134">集計関数の詳細については、次を参照してください。 [Aggregate 句](../../../visual-basic/language-reference/queries/aggregate-clause.md)します。</span><span class="sxs-lookup"><span data-stu-id="833a7-134">For information about aggregate functions, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="833a7-135">たとえば、マネージャーのコレクションと、従業員のコレクションに検討してください。</span><span class="sxs-lookup"><span data-stu-id="833a7-135">Consider, for example, a collection of managers and a collection of employees.</span></span> <span data-ttu-id="833a7-136">両方のコレクションから要素では、特定の管理者に報告する従業員を識別する ManagerID プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="833a7-136">Elements from both collections have a ManagerID property that identifies the employees that report to a particular manager.</span></span> <span data-ttu-id="833a7-137">結合操作の結果には、各マネージャーと従業員 ManagerID 値が一致する結果が含まれます。</span><span class="sxs-lookup"><span data-stu-id="833a7-137">The results from a join operation would contain a result for each manager and employee with a matching ManagerID value.</span></span> <span data-ttu-id="833a7-138">結果、`Group Join`操作には、マネージャーの完全な一覧にが含まれます。</span><span class="sxs-lookup"><span data-stu-id="833a7-138">The results from a `Group Join` operation would contain the complete list of managers.</span></span> <span data-ttu-id="833a7-139">各管理者の結果は、特定のマネージャーと一致する従業員の一覧を参照したメンバーになります。</span><span class="sxs-lookup"><span data-stu-id="833a7-139">Each manager result would have a member that referenced the list of employees that were a match for the specific manager.</span></span>  
  
 <span data-ttu-id="833a7-140">結果のコレクションを`Group Join`操作がで識別されるコレクションからの値の任意の組み合わせを含めることができます、`From`句と、式で識別される、`Into`の句、`Group Join`句。</span><span class="sxs-lookup"><span data-stu-id="833a7-140">The collection resulting from a `Group Join` operation can contain any combination of values from the collection identified in the `From` clause and the expressions identified in the `Into` clause of the `Group Join` clause.</span></span> <span data-ttu-id="833a7-141">有効な式の詳細については、`Into`句を参照してください[Aggregate 句](../../../visual-basic/language-reference/queries/aggregate-clause.md)します。</span><span class="sxs-lookup"><span data-stu-id="833a7-141">For more information about valid expressions for the `Into` clause, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="833a7-142">A`Group Join`操作ではすべての結果を返しますの左側にある特定のコレクションから、`Group Join`演算子。</span><span class="sxs-lookup"><span data-stu-id="833a7-142">A `Group Join` operation will return all results from the collection identified on the left side of the `Group Join` operator.</span></span> <span data-ttu-id="833a7-143">これは、結合するコレクション内の一致がない場合でも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="833a7-143">This is true even if there are no matches in the collection being joined.</span></span> <span data-ttu-id="833a7-144">これは似ています、 `LEFT OUTER JOIN` sql です。</span><span class="sxs-lookup"><span data-stu-id="833a7-144">This is like a `LEFT OUTER JOIN` in SQL.</span></span>  
  
 <span data-ttu-id="833a7-145">使用することができます、`Join`句を 1 つのコレクションをコレクションに結合します。</span><span class="sxs-lookup"><span data-stu-id="833a7-145">You can use the `Join` clause to combine collections into a single collection.</span></span> <span data-ttu-id="833a7-146">これに相当する`INNER JOIN`sql です。</span><span class="sxs-lookup"><span data-stu-id="833a7-146">This is equivalent to an `INNER JOIN` in SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="833a7-147">例</span><span class="sxs-lookup"><span data-stu-id="833a7-147">Example</span></span>  
 <span data-ttu-id="833a7-148">次のコード例では、2 つのコレクションを結合を使用して、`Group Join`句。</span><span class="sxs-lookup"><span data-stu-id="833a7-148">The following code example joins two collections by using the `Group Join` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="833a7-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="833a7-149">See also</span></span>

- [<span data-ttu-id="833a7-150">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="833a7-150">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="833a7-151">クエリ</span><span class="sxs-lookup"><span data-stu-id="833a7-151">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="833a7-152">Select 句</span><span class="sxs-lookup"><span data-stu-id="833a7-152">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="833a7-153">From 句</span><span class="sxs-lookup"><span data-stu-id="833a7-153">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="833a7-154">Join 句</span><span class="sxs-lookup"><span data-stu-id="833a7-154">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)
- [<span data-ttu-id="833a7-155">Where 句</span><span class="sxs-lookup"><span data-stu-id="833a7-155">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="833a7-156">Group By 句</span><span class="sxs-lookup"><span data-stu-id="833a7-156">Group By Clause</span></span>](../../../visual-basic/language-reference/queries/group-by-clause.md)
