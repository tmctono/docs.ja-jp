---
title: From 句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryFrom
- vb.QueryFromIn
- vb.QueryFromLet
helpviewer_keywords:
- queries [Visual Basic], From
- From clause [Visual Basic]
- From statement [Visual Basic]
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
ms.openlocfilehash: 781902f1bf28bd029c8d9825aee155a6691cbae9
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004780"
---
# <a name="from-clause-visual-basic"></a><span data-ttu-id="6e240-102">From 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e240-102">From Clause (Visual Basic)</span></span>
<span data-ttu-id="6e240-103">1つ以上の範囲変数と、クエリを実行するコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e240-103">Specifies one or more range variables and a collection to query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e240-104">構文</span><span class="sxs-lookup"><span data-stu-id="6e240-104">Syntax</span></span>  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="6e240-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="6e240-105">Parts</span></span>  
  
|<span data-ttu-id="6e240-106">項目</span><span class="sxs-lookup"><span data-stu-id="6e240-106">Term</span></span>|<span data-ttu-id="6e240-107">定義</span><span class="sxs-lookup"><span data-stu-id="6e240-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="6e240-108">必須。</span><span class="sxs-lookup"><span data-stu-id="6e240-108">Required.</span></span> <span data-ttu-id="6e240-109">コレクションの要素を反復処理するために使用する*範囲変数*。</span><span class="sxs-lookup"><span data-stu-id="6e240-109">A *range variable* used to iterate through the elements of the collection.</span></span> <span data-ttu-id="6e240-110">範囲変数は、クエリが `collection` を反復処理するときに、@no__t の各メンバーを参照するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e240-110">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span></span> <span data-ttu-id="6e240-111">列挙可能な型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e240-111">Must be an enumerable type.</span></span>|  
|`type`|<span data-ttu-id="6e240-112">任意。</span><span class="sxs-lookup"><span data-stu-id="6e240-112">Optional.</span></span> <span data-ttu-id="6e240-113">`element` の型。</span><span class="sxs-lookup"><span data-stu-id="6e240-113">The type of `element`.</span></span> <span data-ttu-id="6e240-114">@No__t-0 が指定されていない場合、`element` の型は `collection` から推論されます。</span><span class="sxs-lookup"><span data-stu-id="6e240-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="6e240-115">必須。</span><span class="sxs-lookup"><span data-stu-id="6e240-115">Required.</span></span> <span data-ttu-id="6e240-116">クエリ対象のコレクションを参照します。</span><span class="sxs-lookup"><span data-stu-id="6e240-116">Refers to the collection to be queried.</span></span> <span data-ttu-id="6e240-117">列挙可能な型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e240-117">Must be an enumerable type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e240-118">コメント</span><span class="sxs-lookup"><span data-stu-id="6e240-118">Remarks</span></span>  
 <span data-ttu-id="6e240-119">@No__t-0 句は、クエリのソースデータと、ソースコレクションの要素を参照するために使用される変数を識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e240-119">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span></span> <span data-ttu-id="6e240-120">これらの変数は*範囲変数*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="6e240-120">These variables are called *range variables*.</span></span> <span data-ttu-id="6e240-121">クエリには `From` 句が必要です。ただし、集計結果のみを返すクエリを識別するために `Aggregate` 句を使用する場合を除きます。</span><span class="sxs-lookup"><span data-stu-id="6e240-121">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span></span> <span data-ttu-id="6e240-122">詳細については、「 [Aggregate 句](../../../visual-basic/language-reference/queries/aggregate-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e240-122">For more information, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="6e240-123">複数の `From` 句をクエリで指定すると、結合する複数のコレクションを識別できます。</span><span class="sxs-lookup"><span data-stu-id="6e240-123">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span></span> <span data-ttu-id="6e240-124">複数のコレクションが指定されている場合は、個別に反復処理されるか、または関連付けられている場合は結合できます。</span><span class="sxs-lookup"><span data-stu-id="6e240-124">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span></span> <span data-ttu-id="6e240-125">@No__t-0 句を使用して暗黙的にコレクションを結合することも、`Join` 句または `Group Join` 句を使用して明示的に結合することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e240-125">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span></span> <span data-ttu-id="6e240-126">別の方法として、1つの `From` 句で複数の範囲変数とコレクションを指定し、それぞれに関連する範囲変数とコレクションをコンマで区切って指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e240-126">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span></span> <span data-ttu-id="6e240-127">次のコード例では、`From` 句の両方の構文オプションを示します。</span><span class="sxs-lookup"><span data-stu-id="6e240-127">The following code example shows both syntax options for the `From` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 <span data-ttu-id="6e240-128">@No__t-0 句は、クエリのスコープを定義します。これは、`For` ループのスコープに似ています。</span><span class="sxs-lookup"><span data-stu-id="6e240-128">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span></span> <span data-ttu-id="6e240-129">そのため、クエリのスコープ内の各 @no__t 0 範囲変数には、一意の名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e240-129">Therefore, each `element` range variable in the scope of a query must have a unique name.</span></span> <span data-ttu-id="6e240-130">1つのクエリに対して複数の `From` 句を指定できるので、後続の `From` 句は `From` 句の範囲変数を参照できます。また、前の `From` 句の範囲変数を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e240-130">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span></span> <span data-ttu-id="6e240-131">たとえば、次の例は入れ子になった `From` 句を示しています。2番目の句のコレクションは、最初の句の範囲変数のプロパティに基づいています。</span><span class="sxs-lookup"><span data-stu-id="6e240-131">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 <span data-ttu-id="6e240-132">各 `From` 句の後に、追加のクエリ句の任意の組み合わせを使用して、クエリを絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="6e240-132">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span></span> <span data-ttu-id="6e240-133">クエリは、次の方法で絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="6e240-133">You can refine the query in the following ways:</span></span>  
  
- <span data-ttu-id="6e240-134">@No__t-0 および `Select` 句を使用して、または明示的に `Join` 句または `Group Join` 句を使用して、複数のコレクションを暗黙的に結合します。</span><span class="sxs-lookup"><span data-stu-id="6e240-134">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span></span>  
  
- <span data-ttu-id="6e240-135">クエリ結果をフィルター処理するには、`Where` 句を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e240-135">Use the `Where` clause to filter the query result.</span></span>  
  
- <span data-ttu-id="6e240-136">@No__t-0 句を使用して結果を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="6e240-136">Sort the result by using the `Order By` clause.</span></span>  
  
- <span data-ttu-id="6e240-137">@No__t-0 句を使用して、類似した結果をまとめてグループ化します。</span><span class="sxs-lookup"><span data-stu-id="6e240-137">Group similar results together by using the `Group By` clause.</span></span>  
  
- <span data-ttu-id="6e240-138">@No__t-0 句を使用して、クエリ結果全体に対して評価する集計関数を識別します。</span><span class="sxs-lookup"><span data-stu-id="6e240-138">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span></span>  
  
- <span data-ttu-id="6e240-139">@No__t-0 句を使用して、コレクションではなく式によって値が決定される反復変数を導入します。</span><span class="sxs-lookup"><span data-stu-id="6e240-139">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span></span>  
  
- <span data-ttu-id="6e240-140">@No__t-0 句を使用して、重複するクエリ結果を無視します。</span><span class="sxs-lookup"><span data-stu-id="6e240-140">Use the `Distinct` clause to ignore duplicate query results.</span></span>  
  
- <span data-ttu-id="6e240-141">@No__t-0、`Take`、`Skip While`、および `Take While` の各句を使用して返される結果の部分を識別します。</span><span class="sxs-lookup"><span data-stu-id="6e240-141">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e240-142">例</span><span class="sxs-lookup"><span data-stu-id="6e240-142">Example</span></span>  
 <span data-ttu-id="6e240-143">次のクエリ式では、`From` 句を使用して、`customers` コレクション内の `Customer` オブジェクトごとに範囲変数 `cust` を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="6e240-143">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="6e240-144">@No__t-0 句は範囲変数を使用して、指定された地域の顧客に出力を制限します。</span><span class="sxs-lookup"><span data-stu-id="6e240-144">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="6e240-145">@No__t-0 ループでは、クエリ結果に各顧客の会社名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e240-145">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="6e240-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e240-146">See also</span></span>

- [<span data-ttu-id="6e240-147">クエリ</span><span class="sxs-lookup"><span data-stu-id="6e240-147">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="6e240-148">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="6e240-148">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="6e240-149">For Each...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="6e240-149">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="6e240-150">For...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="6e240-150">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="6e240-151">Select 句</span><span class="sxs-lookup"><span data-stu-id="6e240-151">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="6e240-152">Where 句</span><span class="sxs-lookup"><span data-stu-id="6e240-152">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="6e240-153">Aggregate 句</span><span class="sxs-lookup"><span data-stu-id="6e240-153">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="6e240-154">Distinct 句</span><span class="sxs-lookup"><span data-stu-id="6e240-154">Distinct Clause</span></span>](../../../visual-basic/language-reference/queries/distinct-clause.md)
- [<span data-ttu-id="6e240-155">Join 句</span><span class="sxs-lookup"><span data-stu-id="6e240-155">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)
- [<span data-ttu-id="6e240-156">Group Join 句</span><span class="sxs-lookup"><span data-stu-id="6e240-156">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="6e240-157">Order By 句</span><span class="sxs-lookup"><span data-stu-id="6e240-157">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="6e240-158">Let 句</span><span class="sxs-lookup"><span data-stu-id="6e240-158">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)
- [<span data-ttu-id="6e240-159">Skip 句</span><span class="sxs-lookup"><span data-stu-id="6e240-159">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="6e240-160">Take 句</span><span class="sxs-lookup"><span data-stu-id="6e240-160">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="6e240-161">Skip While 句</span><span class="sxs-lookup"><span data-stu-id="6e240-161">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="6e240-162">Take While 句</span><span class="sxs-lookup"><span data-stu-id="6e240-162">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
