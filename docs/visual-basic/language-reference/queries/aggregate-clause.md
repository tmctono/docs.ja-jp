---
title: Aggregate 句 (Visual Basic)
ms.date: 08/28/2018
f1_keywords:
- vb.QueryAggregateIn
- vb.QueryAggregate
- vb.QueryAggregateInto
helpviewer_keywords:
- Aggregate clause [Visual Basic]
- Aggregate statement [Visual Basic]
- queries [Visual Basic], Aggregate
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
ms.openlocfilehash: 50a53cd45cc428541c90fbf82089518be2212fae
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004809"
---
# <a name="aggregate-clause-visual-basic"></a><span data-ttu-id="f0778-102">Aggregate 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0778-102">Aggregate Clause (Visual Basic)</span></span>
<span data-ttu-id="f0778-103">1つまたは複数の集計関数をコレクションに適用します。</span><span class="sxs-lookup"><span data-stu-id="f0778-103">Applies one or more aggregate functions to a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0778-104">構文</span><span class="sxs-lookup"><span data-stu-id="f0778-104">Syntax</span></span>  
  
```vb  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a><span data-ttu-id="f0778-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="f0778-105">Parts</span></span>  
  
|<span data-ttu-id="f0778-106">項目</span><span class="sxs-lookup"><span data-stu-id="f0778-106">Term</span></span>|<span data-ttu-id="f0778-107">定義</span><span class="sxs-lookup"><span data-stu-id="f0778-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="f0778-108">必須。</span><span class="sxs-lookup"><span data-stu-id="f0778-108">Required.</span></span> <span data-ttu-id="f0778-109">コレクションの要素を反復処理するために使用される変数。</span><span class="sxs-lookup"><span data-stu-id="f0778-109">Variable used to iterate through the elements of the collection.</span></span>|  
|`type`|<span data-ttu-id="f0778-110">任意。</span><span class="sxs-lookup"><span data-stu-id="f0778-110">Optional.</span></span> <span data-ttu-id="f0778-111">`element` の型。</span><span class="sxs-lookup"><span data-stu-id="f0778-111">The type of `element`.</span></span> <span data-ttu-id="f0778-112">型が指定されていない場合、`element` の型は `collection` から推論されます。</span><span class="sxs-lookup"><span data-stu-id="f0778-112">If no type is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="f0778-113">必須。</span><span class="sxs-lookup"><span data-stu-id="f0778-113">Required.</span></span> <span data-ttu-id="f0778-114">操作対象のコレクションを参照します。</span><span class="sxs-lookup"><span data-stu-id="f0778-114">Refers to the collection to operate on.</span></span>|  
|`clause`|<span data-ttu-id="f0778-115">任意。</span><span class="sxs-lookup"><span data-stu-id="f0778-115">Optional.</span></span> <span data-ttu-id="f0778-116">集計句または句をに適用するためにクエリ結果を絞り込むための、`Where` 句などの1つ以上のクエリ句。</span><span class="sxs-lookup"><span data-stu-id="f0778-116">One or more query clauses, such as a `Where` clause, to refine the query result to apply the aggregate clause or clauses to.</span></span>|  
|`expressionList`|<span data-ttu-id="f0778-117">必須。</span><span class="sxs-lookup"><span data-stu-id="f0778-117">Required.</span></span> <span data-ttu-id="f0778-118">コレクションに適用する集計関数を識別する1つ以上のコンマ区切りの式。</span><span class="sxs-lookup"><span data-stu-id="f0778-118">One or more comma-delimited expressions that identify an aggregate function to apply to the collection.</span></span> <span data-ttu-id="f0778-119">集計関数に別名を適用して、クエリ結果のメンバー名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f0778-119">You can apply an alias to an aggregate function to specify a member name for the query result.</span></span> <span data-ttu-id="f0778-120">別名が指定されていない場合は、集計関数の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f0778-120">If no alias is supplied, the name of the aggregate function is used.</span></span> <span data-ttu-id="f0778-121">例については、このトピックで後述する「集計関数について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0778-121">For examples, see the section about aggregate functions later in this topic.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0778-122">コメント</span><span class="sxs-lookup"><span data-stu-id="f0778-122">Remarks</span></span>  
 <span data-ttu-id="f0778-123">@No__t-0 句を使用すると、クエリに集計関数を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f0778-123">The `Aggregate` clause can be used to include aggregate functions in your queries.</span></span> <span data-ttu-id="f0778-124">集計関数は、一連の値に対してチェックと計算を実行し、1つの値を返します。</span><span class="sxs-lookup"><span data-stu-id="f0778-124">Aggregate functions perform checks and computations over a set of values and return a single value.</span></span> <span data-ttu-id="f0778-125">クエリ結果の型のメンバーを使用すると、計算された値にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f0778-125">You can access the computed value by using a member of the query result type.</span></span> <span data-ttu-id="f0778-126">使用できる標準の集計関数は、@no__t 0、`Any`、`Average`、`Count`、@no__t 4、`Max`、`Min`、および `Sum` 関数です。</span><span class="sxs-lookup"><span data-stu-id="f0778-126">The standard aggregate functions that you can use are the `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, and `Sum` functions.</span></span> <span data-ttu-id="f0778-127">これらの関数は、SQL の集計に精通している開発者にとってはよく知られています。</span><span class="sxs-lookup"><span data-stu-id="f0778-127">These functions are familiar to developers who are familiar with aggregates in SQL.</span></span> <span data-ttu-id="f0778-128">これらの詳細については、このトピックの次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="f0778-128">They are described in the following section of this topic.</span></span>  
  
 <span data-ttu-id="f0778-129">集計関数の結果は、クエリ結果の型のフィールドとしてクエリ結果に含まれます。</span><span class="sxs-lookup"><span data-stu-id="f0778-129">The result of an aggregate function is included in the query result as a field of the query result type.</span></span> <span data-ttu-id="f0778-130">集計関数の結果に別名を指定して、集計値を保持するクエリ結果の型のメンバーの名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f0778-130">You can supply an alias for the aggregate function result to specify the name of the member of the query result type that will hold the aggregate value.</span></span> <span data-ttu-id="f0778-131">別名が指定されていない場合は、集計関数の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f0778-131">If no alias is supplied, the name of the aggregate function is used.</span></span>  
  
 <span data-ttu-id="f0778-132">@No__t-0 句は、クエリを開始するか、クエリに追加の句として含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f0778-132">The `Aggregate` clause can begin a query, or it can be included as an additional clause in a query.</span></span> <span data-ttu-id="f0778-133">@No__t-0 句によってクエリが開始された場合、結果は、`Into` 句に指定された集計関数の結果である単一の値になります。</span><span class="sxs-lookup"><span data-stu-id="f0778-133">If the `Aggregate` clause begins a query, the result is a single value that is the result of the aggregate function specified in the `Into` clause.</span></span> <span data-ttu-id="f0778-134">@No__t-0 句に複数の集計関数が指定されている場合、クエリは、`Into` 句の各集計関数の結果を参照する個別のプロパティを持つ1つの型を返します。</span><span class="sxs-lookup"><span data-stu-id="f0778-134">If more than one aggregate function is specified in the `Into` clause, the query returns a single type with a separate property to reference the result of each aggregate function in the `Into` clause.</span></span> <span data-ttu-id="f0778-135">@No__t-0 句がクエリに追加の句として含まれている場合、クエリコレクションで返される型には、`Into` 句の各集計関数の結果を参照する個別のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="f0778-135">If the `Aggregate` clause is included as an additional clause in a query, the type returned in the query collection will have a separate property to reference the result of each aggregate function in the `Into` clause.</span></span>  
  
## <a name="aggregate-functions"></a><span data-ttu-id="f0778-136">集計関数</span><span class="sxs-lookup"><span data-stu-id="f0778-136">Aggregate Functions</span></span>

<span data-ttu-id="f0778-137">次に示すのは、`Aggregate` 句と共に使用できる標準の集計関数です。</span><span class="sxs-lookup"><span data-stu-id="f0778-137">The following are the standard aggregate functions that can be used with the `Aggregate` clause.</span></span>  
  
### <a name="all"></a><span data-ttu-id="f0778-138">All</span><span class="sxs-lookup"><span data-stu-id="f0778-138">All</span></span>

<span data-ttu-id="f0778-139">コレクション内のすべての要素が指定された条件を満たす場合は `true` を返します。それ以外の場合は `false` を返します。</span><span class="sxs-lookup"><span data-stu-id="f0778-139">Returns `true` if all elements in the collection satisfy a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="f0778-140">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f0778-140">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#5)]

### <a name="any"></a><span data-ttu-id="f0778-141">Any</span><span class="sxs-lookup"><span data-stu-id="f0778-141">Any</span></span>

<span data-ttu-id="f0778-142">コレクション内のいずれかの要素が指定された条件を満たす場合は `true` を返します。それ以外の場合は `false` を返します。</span><span class="sxs-lookup"><span data-stu-id="f0778-142">Returns `true` if any element in the collection satisfies a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="f0778-143">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f0778-143">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#6)]

### <a name="average"></a><span data-ttu-id="f0778-144">平均</span><span class="sxs-lookup"><span data-stu-id="f0778-144">Average</span></span>

<span data-ttu-id="f0778-145">コレクション内のすべての要素の平均値を計算するか、コレクション内のすべての要素に対して指定された式を計算します。</span><span class="sxs-lookup"><span data-stu-id="f0778-145">Computes the average of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="f0778-146">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f0778-146">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#7)]

### <a name="count"></a><span data-ttu-id="f0778-147">Count</span><span class="sxs-lookup"><span data-stu-id="f0778-147">Count</span></span>

<span data-ttu-id="f0778-148">コレクション内の要素の数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="f0778-148">Counts the number of elements in the collection.</span></span> <span data-ttu-id="f0778-149">条件を満たすコレクション内の要素の数のみをカウントするように、オプションの `Boolean` 式を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="f0778-149">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="f0778-150">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f0778-150">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#8)]

### <a name="group"></a><span data-ttu-id="f0778-151">グループ</span><span class="sxs-lookup"><span data-stu-id="f0778-151">Group</span></span>

<span data-ttu-id="f0778-152">@No__t-0 または `Group Join` 句の結果としてグループ化されたクエリ結果を参照します。</span><span class="sxs-lookup"><span data-stu-id="f0778-152">Refers to query results that are grouped as a result of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="f0778-153">@No__t-0 関数は、`Group By` または `Group Join` 句の `Into` 句でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="f0778-153">The `Group` function is valid only in the `Into` clause of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="f0778-154">詳細と例については、「 [Group By 句](../../../visual-basic/language-reference/queries/group-by-clause.md)と[group Join 句](../../../visual-basic/language-reference/queries/group-join-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0778-154">For more information and examples, see [Group By Clause](../../../visual-basic/language-reference/queries/group-by-clause.md) and [Group Join Clause](../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>

### <a name="longcount"></a><span data-ttu-id="f0778-155">LongCount</span><span class="sxs-lookup"><span data-stu-id="f0778-155">LongCount</span></span>

<span data-ttu-id="f0778-156">コレクション内の要素の数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="f0778-156">Counts the number of elements in the collection.</span></span> <span data-ttu-id="f0778-157">条件を満たすコレクション内の要素の数のみをカウントするように、オプションの `Boolean` 式を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="f0778-157">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="f0778-158">結果を @no__t 0 として返します。</span><span class="sxs-lookup"><span data-stu-id="f0778-158">Returns the result as a `Long`.</span></span> <span data-ttu-id="f0778-159">例については、「`Count` 集計関数」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0778-159">For an example, see the `Count` aggregate function.</span></span>

### <a name="max"></a><span data-ttu-id="f0778-160">Max</span><span class="sxs-lookup"><span data-stu-id="f0778-160">Max</span></span>

<span data-ttu-id="f0778-161">コレクションから最大値を計算するか、コレクション内のすべての要素に対して指定された式を計算します。</span><span class="sxs-lookup"><span data-stu-id="f0778-161">Computes the maximum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="f0778-162">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f0778-162">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#9)]

### <a name="min"></a><span data-ttu-id="f0778-163">Min</span><span class="sxs-lookup"><span data-stu-id="f0778-163">Min</span></span>

<span data-ttu-id="f0778-164">コレクションから最小値を計算するか、コレクション内のすべての要素に対して指定された式を計算します。</span><span class="sxs-lookup"><span data-stu-id="f0778-164">Computes the minimum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="f0778-165">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f0778-165">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#10)]

### <a name="sum"></a><span data-ttu-id="f0778-166">Sum</span><span class="sxs-lookup"><span data-stu-id="f0778-166">Sum</span></span>

<span data-ttu-id="f0778-167">コレクション内のすべての要素の合計を計算するか、コレクション内のすべての要素に対して指定された式を計算します。</span><span class="sxs-lookup"><span data-stu-id="f0778-167">Computes the sum of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="f0778-168">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f0778-168">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#15)]

## <a name="example"></a><span data-ttu-id="f0778-169">例</span><span class="sxs-lookup"><span data-stu-id="f0778-169">Example</span></span>  

<span data-ttu-id="f0778-170">次の例では、`Aggregate` 句を使用して、クエリ結果に集計関数を適用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f0778-170">The following example shows how to use the `Aggregate` clause to apply aggregate functions to a query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#4)]  
  
## <a name="creating-user-defined-aggregate-functions"></a><span data-ttu-id="f0778-171">ユーザー定義集計関数の作成</span><span class="sxs-lookup"><span data-stu-id="f0778-171">Creating User-Defined Aggregate Functions</span></span>

 <span data-ttu-id="f0778-172">@No__t-0 型に拡張メソッドを追加することで、独自のカスタム集計関数をクエリ式に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f0778-172">You can include your own custom aggregate functions in a query expression by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> type.</span></span> <span data-ttu-id="f0778-173">カスタムメソッドは、集計関数を参照した列挙可能なコレクションに対して計算または操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f0778-173">Your custom method can then perform a calculation or operation on the enumerable collection that has referenced your aggregate function.</span></span> <span data-ttu-id="f0778-174">拡張メソッドについて詳しくは、「[拡張メソッド](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f0778-174">For more information about extension methods, see [Extension Methods](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
 <span data-ttu-id="f0778-175">たとえば、次の例は、数値のコレクションの中央値を計算するカスタム集計関数を示しています。</span><span class="sxs-lookup"><span data-stu-id="f0778-175">For example, the following example shows a custom aggregate function that calculates the median value of a collection of numbers.</span></span> <span data-ttu-id="f0778-176">@No__t-0 拡張メソッドの2つのオーバーロードがあります。</span><span class="sxs-lookup"><span data-stu-id="f0778-176">There are two overloads of the `Median` extension method.</span></span> <span data-ttu-id="f0778-177">1つ目のオーバーロードは、入力として `IEnumerable(Of Double)` 型のコレクションを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="f0778-177">The first overload accepts, as input, a collection of type `IEnumerable(Of Double)`.</span></span> <span data-ttu-id="f0778-178">@No__t-0 集計関数が @no__t 型のクエリフィールドに対して呼び出されると、このメソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f0778-178">If the `Median` aggregate function is called for a query field of type `Double`, this method will be called.</span></span> <span data-ttu-id="f0778-179">@No__t-0 メソッドの2番目のオーバーロードには、任意のジェネリック型を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="f0778-179">The second overload of the `Median` method can be passed any generic type.</span></span> <span data-ttu-id="f0778-180">@No__t-0 メソッドの汎用的なオーバーロードは、`Func(Of T, Double)` ラムダ式を参照する2番目のパラメーターを受け取ります。このパラメーターは、コレクションの型の値を、型 `Double` の対応する値として射影します。</span><span class="sxs-lookup"><span data-stu-id="f0778-180">The generic overload of the `Median` method takes a second parameter that references the `Func(Of T, Double)` lambda expression to project a value for a type (from a collection) as the corresponding value of type `Double`.</span></span> <span data-ttu-id="f0778-181">次に、中央値の計算を `Median` メソッドの他のオーバーロードにデリゲートします。</span><span class="sxs-lookup"><span data-stu-id="f0778-181">It then delegates the calculation of the median value to the other overload of the `Median` method.</span></span> <span data-ttu-id="f0778-182">ラムダ式について詳しくは、「[ラムダ式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f0778-182">For more information about lambda expressions, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#18)]  
  
 <span data-ttu-id="f0778-183">次の例では、型が @no__t のコレクションに対して `Median` 集計関数を呼び出すサンプルクエリと、`Double` 型のコレクションを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f0778-183">The following example shows sample queries that call the `Median` aggregate function on a collection of type `Integer`, and a collection of type `Double`.</span></span> <span data-ttu-id="f0778-184">型 `Double` のコレクションで `Median` 集計関数を呼び出すクエリは、型 `Double` のコレクションを入力として受け入れる、`Median` メソッドのオーバーロードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f0778-184">The query that calls the `Median` aggregate function on the collection of type `Double` calls the overload of the `Median` method that accepts, as input, a collection of type `Double`.</span></span> <span data-ttu-id="f0778-185">型 `Integer` のコレクションに対して `Median` 集計関数を呼び出すクエリは、`Median` メソッドのジェネリックオーバーロードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f0778-185">The query that calls the `Median` aggregate function on the collection of type `Integer` calls the generic overload of the `Median` method.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="f0778-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0778-186">See also</span></span>

- [<span data-ttu-id="f0778-187">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="f0778-187">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="f0778-188">クエリ</span><span class="sxs-lookup"><span data-stu-id="f0778-188">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="f0778-189">Select 句</span><span class="sxs-lookup"><span data-stu-id="f0778-189">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="f0778-190">From 句</span><span class="sxs-lookup"><span data-stu-id="f0778-190">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="f0778-191">Where 句</span><span class="sxs-lookup"><span data-stu-id="f0778-191">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="f0778-192">Group By 句</span><span class="sxs-lookup"><span data-stu-id="f0778-192">Group By Clause</span></span>](../../../visual-basic/language-reference/queries/group-by-clause.md)
