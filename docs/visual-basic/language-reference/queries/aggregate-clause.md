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
ms.openlocfilehash: 21781db637c71abbbe9366bc95b6ee4c89ac2246
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981960"
---
# <a name="aggregate-clause-visual-basic"></a><span data-ttu-id="de9ec-102">Aggregate 句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de9ec-102">Aggregate Clause (Visual Basic)</span></span>
<span data-ttu-id="de9ec-103">1 つまたは複数の集計関数をコレクションに適用します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-103">Applies one or more aggregate functions to a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de9ec-104">構文</span><span class="sxs-lookup"><span data-stu-id="de9ec-104">Syntax</span></span>  
  
```  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a><span data-ttu-id="de9ec-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="de9ec-105">Parts</span></span>  
  
|<span data-ttu-id="de9ec-106">用語</span><span class="sxs-lookup"><span data-stu-id="de9ec-106">Term</span></span>|<span data-ttu-id="de9ec-107">定義</span><span class="sxs-lookup"><span data-stu-id="de9ec-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="de9ec-108">必須。</span><span class="sxs-lookup"><span data-stu-id="de9ec-108">Required.</span></span> <span data-ttu-id="de9ec-109">変数なコレクションの要素を反復処理するために使用します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-109">Variable used to iterate through the elements of the collection.</span></span>|  
|`type`|<span data-ttu-id="de9ec-110">任意。</span><span class="sxs-lookup"><span data-stu-id="de9ec-110">Optional.</span></span> <span data-ttu-id="de9ec-111">`element` の型。</span><span class="sxs-lookup"><span data-stu-id="de9ec-111">The type of `element`.</span></span> <span data-ttu-id="de9ec-112">型が指定されていない場合の種類`element`から推論されます`collection`します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-112">If no type is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="de9ec-113">必須。</span><span class="sxs-lookup"><span data-stu-id="de9ec-113">Required.</span></span> <span data-ttu-id="de9ec-114">操作対象のコレクションを参照します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-114">Refers to the collection to operate on.</span></span>|  
|`clause`|<span data-ttu-id="de9ec-115">任意。</span><span class="sxs-lookup"><span data-stu-id="de9ec-115">Optional.</span></span> <span data-ttu-id="de9ec-116">1 つまたは複数の句がクエリなど、`Where`集計句に適用するクエリの結果を絞り込むの句。</span><span class="sxs-lookup"><span data-stu-id="de9ec-116">One or more query clauses, such as a `Where` clause, to refine the query result to apply the aggregate clause or clauses to.</span></span>|  
|`expressionList`|<span data-ttu-id="de9ec-117">必須。</span><span class="sxs-lookup"><span data-stu-id="de9ec-117">Required.</span></span> <span data-ttu-id="de9ec-118">1 つまたは複数コンマで区切られた式のコレクションに適用する集計関数を識別します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-118">One or more comma-delimited expressions that identify an aggregate function to apply to the collection.</span></span> <span data-ttu-id="de9ec-119">エイリアスは、クエリ結果のメンバー名を指定する集計関数を適用できます。</span><span class="sxs-lookup"><span data-stu-id="de9ec-119">You can apply an alias to an aggregate function to specify a member name for the query result.</span></span> <span data-ttu-id="de9ec-120">エイリアスが指定されていない場合は、集計関数の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="de9ec-120">If no alias is supplied, the name of the aggregate function is used.</span></span> <span data-ttu-id="de9ec-121">例については、このトピックの後半の集計関数に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="de9ec-121">For examples, see the section about aggregate functions later in this topic.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de9ec-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="de9ec-122">Remarks</span></span>  
 <span data-ttu-id="de9ec-123">`Aggregate`に集計関数をクエリに含める句を使用できます。</span><span class="sxs-lookup"><span data-stu-id="de9ec-123">The `Aggregate` clause can be used to include aggregate functions in your queries.</span></span> <span data-ttu-id="de9ec-124">集計関数は、値のセットをチェックし、計算を実行し、1 つの値を返します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-124">Aggregate functions perform checks and computations over a set of values and return a single value.</span></span> <span data-ttu-id="de9ec-125">計算された値は、クエリ結果の型のメンバーを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="de9ec-125">You can access the computed value by using a member of the query result type.</span></span> <span data-ttu-id="de9ec-126">使用できる標準の集計関数は、 `All`、 `Any`、 `Average`、 `Count`、 `LongCount`、 `Max`、 `Min`、および`Sum`関数。</span><span class="sxs-lookup"><span data-stu-id="de9ec-126">The standard aggregate functions that you can use are the `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, and `Sum` functions.</span></span> <span data-ttu-id="de9ec-127">これらの関数は SQL での集計に精通している開発者にとって馴染みのあります。</span><span class="sxs-lookup"><span data-stu-id="de9ec-127">These functions are familiar to developers who are familiar with aggregates in SQL.</span></span> <span data-ttu-id="de9ec-128">このトピックの次のセクションに記述されています。</span><span class="sxs-lookup"><span data-stu-id="de9ec-128">They are described in the following section of this topic.</span></span>  
  
 <span data-ttu-id="de9ec-129">クエリ結果の型のフィールドとしてクエリ結果の集計関数の結果が含まれます。</span><span class="sxs-lookup"><span data-stu-id="de9ec-129">The result of an aggregate function is included in the query result as a field of the query result type.</span></span> <span data-ttu-id="de9ec-130">集計値を保持するクエリ結果の型のメンバーの名前を指定する集計関数の結果のエイリアスを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="de9ec-130">You can supply an alias for the aggregate function result to specify the name of the member of the query result type that will hold the aggregate value.</span></span> <span data-ttu-id="de9ec-131">エイリアスが指定されていない場合は、集計関数の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="de9ec-131">If no alias is supplied, the name of the aggregate function is used.</span></span>  
  
 <span data-ttu-id="de9ec-132">`Aggregate`句は、クエリを開始できるかは、クエリで追加の句として追加できます。</span><span class="sxs-lookup"><span data-stu-id="de9ec-132">The `Aggregate` clause can begin a query, or it can be included as an additional clause in a query.</span></span> <span data-ttu-id="de9ec-133">場合、`Aggregate`句がクエリを開始すると、結果は、1 つの値で指定された集計関数の結果では、`Into`句。</span><span class="sxs-lookup"><span data-stu-id="de9ec-133">If the `Aggregate` clause begins a query, the result is a single value that is the result of the aggregate function specified in the `Into` clause.</span></span> <span data-ttu-id="de9ec-134">複数の集計関数が指定されている場合、`Into`句内の各集計関数の結果を参照する個別のプロパティを 1 つの型を返します、クエリ、`Into`句。</span><span class="sxs-lookup"><span data-stu-id="de9ec-134">If more than one aggregate function is specified in the `Into` clause, the query returns a single type with a separate property to reference the result of each aggregate function in the `Into` clause.</span></span> <span data-ttu-id="de9ec-135">場合、`Aggregate`句をクエリで追加の句として含めると、クエリのコレクションに返される型の各集計関数の結果を参照する個別のプロパティになります、`Into`句。</span><span class="sxs-lookup"><span data-stu-id="de9ec-135">If the `Aggregate` clause is included as an additional clause in a query, the type returned in the query collection will have a separate property to reference the result of each aggregate function in the `Into` clause.</span></span>  
  
## <a name="aggregate-functions"></a><span data-ttu-id="de9ec-136">集計関数</span><span class="sxs-lookup"><span data-stu-id="de9ec-136">Aggregate Functions</span></span>

<span data-ttu-id="de9ec-137">使用できる標準の集計関数を次に、`Aggregate`句。</span><span class="sxs-lookup"><span data-stu-id="de9ec-137">The following are the standard aggregate functions that can be used with the `Aggregate` clause.</span></span>  
  
### <a name="all"></a><span data-ttu-id="de9ec-138">すべて</span><span class="sxs-lookup"><span data-stu-id="de9ec-138">All</span></span>

<span data-ttu-id="de9ec-139">返します`true`返しますそれ以外の場合、コレクション内のすべての要素。 指定された条件を満たす場合`false`します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-139">Returns `true` if all elements in the collection satisfy a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="de9ec-140">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-140">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#5)]

### <a name="any"></a><span data-ttu-id="de9ec-141">どれでも可</span><span class="sxs-lookup"><span data-stu-id="de9ec-141">Any</span></span>

<span data-ttu-id="de9ec-142">返します`true`返しますそれ以外の場合、コレクション内の任意の要素が; 指定された条件を満たす場合`false`します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-142">Returns `true` if any element in the collection satisfies a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="de9ec-143">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-143">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#6)]

### <a name="average"></a><span data-ttu-id="de9ec-144">平均</span><span class="sxs-lookup"><span data-stu-id="de9ec-144">Average</span></span>

<span data-ttu-id="de9ec-145">コレクション内のすべての要素の平均を計算するか、またはコレクション内のすべての要素に対して指定された式を計算します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-145">Computes the average of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="de9ec-146">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-146">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#7)]

### <a name="count"></a><span data-ttu-id="de9ec-147">カウント</span><span class="sxs-lookup"><span data-stu-id="de9ec-147">Count</span></span>

<span data-ttu-id="de9ec-148">コレクション内の要素の数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="de9ec-148">Counts the number of elements in the collection.</span></span> <span data-ttu-id="de9ec-149">省略可能なを指定する`Boolean`式、条件を満たすコレクション内の要素の数のみをカウントします。</span><span class="sxs-lookup"><span data-stu-id="de9ec-149">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="de9ec-150">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-150">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#8)]

### <a name="group"></a><span data-ttu-id="de9ec-151">グループ化</span><span class="sxs-lookup"><span data-stu-id="de9ec-151">Group</span></span>

<span data-ttu-id="de9ec-152">結果としてグループ化されているクエリの結果を指す、`Group By`または`Group Join`句。</span><span class="sxs-lookup"><span data-stu-id="de9ec-152">Refers to query results that are grouped as a result of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="de9ec-153">`Group`関数はでのみ有効ですが、`Into`の句、`Group By`または`Group Join`句。</span><span class="sxs-lookup"><span data-stu-id="de9ec-153">The `Group` function is valid only in the `Into` clause of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="de9ec-154">詳細と例については、次を参照してください。 [By 句のグループ](../../../visual-basic/language-reference/queries/group-by-clause.md)と[Group Join 句](../../../visual-basic/language-reference/queries/group-join-clause.md)します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-154">For more information and examples, see [Group By Clause](../../../visual-basic/language-reference/queries/group-by-clause.md) and [Group Join Clause](../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>

### <a name="longcount"></a><span data-ttu-id="de9ec-155">LongCount</span><span class="sxs-lookup"><span data-stu-id="de9ec-155">LongCount</span></span>

<span data-ttu-id="de9ec-156">コレクション内の要素の数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="de9ec-156">Counts the number of elements in the collection.</span></span> <span data-ttu-id="de9ec-157">省略可能なを指定する`Boolean`式、条件を満たすコレクション内の要素の数のみをカウントします。</span><span class="sxs-lookup"><span data-stu-id="de9ec-157">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="de9ec-158">結果として返します、`Long`します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-158">Returns the result as a `Long`.</span></span> <span data-ttu-id="de9ec-159">例については、次を参照してください。、`Count`集計関数。</span><span class="sxs-lookup"><span data-stu-id="de9ec-159">For an example, see the `Count` aggregate function.</span></span>

### <a name="max"></a><span data-ttu-id="de9ec-160">最大</span><span class="sxs-lookup"><span data-stu-id="de9ec-160">Max</span></span>

<span data-ttu-id="de9ec-161">コレクションから最大値を計算またはコレクション内のすべての要素に対して指定された式を計算します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-161">Computes the maximum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="de9ec-162">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-162">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#9)]

### <a name="min"></a><span data-ttu-id="de9ec-163">最小</span><span class="sxs-lookup"><span data-stu-id="de9ec-163">Min</span></span>

<span data-ttu-id="de9ec-164">コレクションから最小値を計算またはコレクション内のすべての要素に対して指定された式を計算します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-164">Computes the minimum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="de9ec-165">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-165">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#10)]

### <a name="sum"></a><span data-ttu-id="de9ec-166">Sum</span><span class="sxs-lookup"><span data-stu-id="de9ec-166">Sum</span></span>

<span data-ttu-id="de9ec-167">コレクション内のすべての要素の合計を計算するか、またはコレクション内のすべての要素に対して指定された式を計算します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-167">Computes the sum of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="de9ec-168">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-168">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#15)]

## <a name="example"></a><span data-ttu-id="de9ec-169">例</span><span class="sxs-lookup"><span data-stu-id="de9ec-169">Example</span></span>  

<span data-ttu-id="de9ec-170">次の例は、使用する方法を示します、`Aggregate`句をクエリ結果に集計関数を適用します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-170">The following example shows how to use the `Aggregate` clause to apply aggregate functions to a query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#4)]  
  
## <a name="creating-user-defined-aggregate-functions"></a><span data-ttu-id="de9ec-171">ユーザー定義集計関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-171">Creating User-Defined Aggregate Functions</span></span>

 <span data-ttu-id="de9ec-172">拡張メソッドを追加することによって、クエリ式で、独自のカスタム集計関数を含めることができます、<xref:System.Collections.Generic.IEnumerable%601>型。</span><span class="sxs-lookup"><span data-stu-id="de9ec-172">You can include your own custom aggregate functions in a query expression by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> type.</span></span> <span data-ttu-id="de9ec-173">カスタム メソッドを計算または集計関数が参照する列挙可能なコレクションに対して操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="de9ec-173">Your custom method can then perform a calculation or operation on the enumerable collection that has referenced your aggregate function.</span></span> <span data-ttu-id="de9ec-174">拡張メソッドについて詳しくは、「[拡張メソッド](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="de9ec-174">For more information about extension methods, see [Extension Methods](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
 <span data-ttu-id="de9ec-175">たとえば、次の例は、数値のコレクションの中央値を計算するカスタムの集計関数を示します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-175">For example, the following example shows a custom aggregate function that calculates the median value of a collection of numbers.</span></span> <span data-ttu-id="de9ec-176">2 つのオーバー ロードがあります、`Median`拡張メソッド。</span><span class="sxs-lookup"><span data-stu-id="de9ec-176">There are two overloads of the `Median` extension method.</span></span> <span data-ttu-id="de9ec-177">最初のオーバー ロードを受け入れると、入力として、型のコレクション`IEnumerable(Of Double)`します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-177">The first overload accepts, as input, a collection of type `IEnumerable(Of Double)`.</span></span> <span data-ttu-id="de9ec-178">場合、`Median`型のクエリ フィールドの集計関数が呼び出されます`Double`、このメソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="de9ec-178">If the `Median` aggregate function is called for a query field of type `Double`, this method will be called.</span></span> <span data-ttu-id="de9ec-179">2 番目のオーバー ロード、`Median`任意のジェネリック型をメソッドに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="de9ec-179">The second overload of the `Median` method can be passed any generic type.</span></span> <span data-ttu-id="de9ec-180">ジェネリック オーバー ロード、`Median`メソッドが参照する 2 番目のパラメーターを受け取り、`Func(Of T, Double)`型の対応する値として (コレクション) からの型の値を射影するラムダ式`Double`します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-180">The generic overload of the `Median` method takes a second parameter that references the `Func(Of T, Double)` lambda expression to project a value for a type (from a collection) as the corresponding value of type `Double`.</span></span> <span data-ttu-id="de9ec-181">その他のオーバー ロードに中央値の計算をデリゲートして、`Median`メソッド。</span><span class="sxs-lookup"><span data-stu-id="de9ec-181">It then delegates the calculation of the median value to the other overload of the `Median` method.</span></span> <span data-ttu-id="de9ec-182">ラムダ式について詳しくは、「[ラムダ式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="de9ec-182">For more information about lambda expressions, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#18)]  
  
 <span data-ttu-id="de9ec-183">次の例では、サンプル クエリを呼び出す、`Median`集計関数の型のコレクション`Integer`、型のコレクションと`Double`します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-183">The following example shows sample queries that call the `Median` aggregate function on a collection of type `Integer`, and a collection of type `Double`.</span></span> <span data-ttu-id="de9ec-184">呼び出すクエリ、`Median`集計関数の種類のコレクションで`Double`のオーバー ロードを呼び出し、`Median`型のコレクションを入力として受け取るメソッドを`Double`します。</span><span class="sxs-lookup"><span data-stu-id="de9ec-184">The query that calls the `Median` aggregate function on the collection of type `Double` calls the overload of the `Median` method that accepts, as input, a collection of type `Double`.</span></span> <span data-ttu-id="de9ec-185">呼び出すクエリ、`Median`集計関数の種類のコレクションで`Integer`のジェネリック オーバー ロードを呼び出し、`Median`メソッド。</span><span class="sxs-lookup"><span data-stu-id="de9ec-185">The query that calls the `Median` aggregate function on the collection of type `Integer` calls the generic overload of the `Median` method.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="de9ec-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="de9ec-186">See also</span></span>

- [<span data-ttu-id="de9ec-187">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="de9ec-187">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="de9ec-188">クエリ</span><span class="sxs-lookup"><span data-stu-id="de9ec-188">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="de9ec-189">Select 句</span><span class="sxs-lookup"><span data-stu-id="de9ec-189">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="de9ec-190">From 句</span><span class="sxs-lookup"><span data-stu-id="de9ec-190">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="de9ec-191">Where 句</span><span class="sxs-lookup"><span data-stu-id="de9ec-191">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="de9ec-192">Group By 句</span><span class="sxs-lookup"><span data-stu-id="de9ec-192">Group By Clause</span></span>](../../../visual-basic/language-reference/queries/group-by-clause.md)
