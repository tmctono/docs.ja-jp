---
title: Null 許容値型-Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
ms.openlocfilehash: 1fb8f8d1657b8eab6b15858c2a6607cbde82e542
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732938"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="020ff-102">null 許容値型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="020ff-102">Nullable Value Types (Visual Basic)</span></span>

<span data-ttu-id="020ff-103">場合によっては、特定の状況で値が定義されていない値型を使用することがあります。</span><span class="sxs-lookup"><span data-stu-id="020ff-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="020ff-104">たとえば、データベースのフィールドは、値が割り当てられていない、意味のある値が割り当てられているかを区別する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="020ff-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="020ff-105">値型は、通常の値または null 値を受け取るように拡張できます。</span><span class="sxs-lookup"><span data-stu-id="020ff-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="020ff-106">このような拡張機能は、 *null 許容型*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="020ff-106">Such an extension is called a *nullable type*.</span></span>

<span data-ttu-id="020ff-107">各 null 許容型は、ジェネリック <xref:System.Nullable%601> 構造体から構築されます。</span><span class="sxs-lookup"><span data-stu-id="020ff-107">Each nullable type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="020ff-108">作業に関連するアクティビティを追跡するデータベースについて考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="020ff-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="020ff-109">次の例では、null 許容の `Boolean` 型を構築し、その型の変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="020ff-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="020ff-110">宣言は、次の3つの方法で記述できます。</span><span class="sxs-lookup"><span data-stu-id="020ff-110">You can write the declaration in three ways:</span></span>

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

<span data-ttu-id="020ff-111">変数 `ridesBusToWork` には `True`の値、`False`の値、または値を指定できません。</span><span class="sxs-lookup"><span data-stu-id="020ff-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="020ff-112">初期の既定値はまったく値ではありません。この場合は、このユーザーに対して情報がまだ取得されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="020ff-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="020ff-113">これに対して、`False` 情報が取得されていて、ユーザーがバスを使用できないことを意味する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="020ff-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>

<span data-ttu-id="020ff-114">Null 許容型を使用して変数とプロパティを宣言できます。また、null 許容型の要素を使用して配列を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="020ff-114">You can declare variables and properties with nullable types, and you can declare an array with elements of a nullable type.</span></span> <span data-ttu-id="020ff-115">Null 許容型を持つプロシージャをパラメーターとして宣言し、`Function` プロシージャから null 許容型を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="020ff-115">You can declare procedures with nullable types as parameters, and you can return a nullable type from a `Function` procedure.</span></span>

<span data-ttu-id="020ff-116">配列、`String`、クラスなどの参照型に対して null 許容型を構築することはできません。</span><span class="sxs-lookup"><span data-stu-id="020ff-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="020ff-117">基になる型は、値型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="020ff-117">The underlying type must be a value type.</span></span> <span data-ttu-id="020ff-118">詳細については、「 [Value Types and Reference Types](value-types-and-reference-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="020ff-118">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>

## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="020ff-119">Null 許容型変数の使用</span><span class="sxs-lookup"><span data-stu-id="020ff-119">Using a Nullable Type Variable</span></span>

<span data-ttu-id="020ff-120">Null 許容型の最も重要なメンバーは、その <xref:System.Nullable%601.HasValue%2A> と <xref:System.Nullable%601.Value%2A> のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="020ff-120">The most important members of a nullable type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="020ff-121">Null 許容型の変数の場合、<xref:System.Nullable%601.HasValue%2A> は、変数に定義済みの値が含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="020ff-121">For a variable of a nullable type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="020ff-122"><xref:System.Nullable%601.HasValue%2A> が `True`場合は、<xref:System.Nullable%601.Value%2A>から値を読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="020ff-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="020ff-123"><xref:System.Nullable%601.HasValue%2A> と <xref:System.Nullable%601.Value%2A> はどちらも `ReadOnly` プロパティであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="020ff-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>

### <a name="default-values"></a><span data-ttu-id="020ff-124">既定値</span><span class="sxs-lookup"><span data-stu-id="020ff-124">Default Values</span></span>

<span data-ttu-id="020ff-125">Null 許容型の変数を宣言すると、その <xref:System.Nullable%601.HasValue%2A> プロパティの既定値 `False`が使用されます。</span><span class="sxs-lookup"><span data-stu-id="020ff-125">When you declare a variable with a nullable type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="020ff-126">これは、既定では、基になる値の型の既定値ではなく、変数に定義された値がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="020ff-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="020ff-127">次の例では、`Integer` 型の既定値が0の場合でも、変数 `numberOfChildren` 最初は定義済みの値を持ちません。</span><span class="sxs-lookup"><span data-stu-id="020ff-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

<span data-ttu-id="020ff-128">Null 値は、未定義または不明な値を示すために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="020ff-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="020ff-129">`numberOfChildren` が `Integer`として宣言されている場合、情報が現在使用できないことを示す値は存在しません。</span><span class="sxs-lookup"><span data-stu-id="020ff-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>

### <a name="storing-values"></a><span data-ttu-id="020ff-130">格納 (値を)</span><span class="sxs-lookup"><span data-stu-id="020ff-130">Storing Values</span></span>

<span data-ttu-id="020ff-131">値は、通常の方法で null 許容型の変数またはプロパティに格納します。</span><span class="sxs-lookup"><span data-stu-id="020ff-131">You store a value in a variable or property of a nullable type in the typical way.</span></span> <span data-ttu-id="020ff-132">次の例では、前の例で宣言した `numberOfChildren` 変数に値を代入します。</span><span class="sxs-lookup"><span data-stu-id="020ff-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

<span data-ttu-id="020ff-133">Null 許容型の変数またはプロパティに定義済みの値が含まれている場合は、値が割り当てられていない初期状態に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="020ff-133">If a variable or property of a nullable type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="020ff-134">これを行うには、次の例に示すように、変数またはプロパティを `Nothing`に設定します。</span><span class="sxs-lookup"><span data-stu-id="020ff-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> <span data-ttu-id="020ff-135">`Nothing` を null 許容型の変数に割り当てることはできますが、等号を使用して `Nothing` をテストすることはできません。</span><span class="sxs-lookup"><span data-stu-id="020ff-135">Although you can assign `Nothing` to a variable of a nullable type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="020ff-136">等号 (`someVar = Nothing`) を使用する比較では、常に `Nothing`として評価されます。</span><span class="sxs-lookup"><span data-stu-id="020ff-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="020ff-137">`False`に対して変数の <xref:System.Nullable%601.HasValue%2A> プロパティをテストしたり、`Is` または `IsNot` 演算子を使用してテストしたりできます。</span><span class="sxs-lookup"><span data-stu-id="020ff-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>

### <a name="retrieving-values"></a><span data-ttu-id="020ff-138">取得 (値を)</span><span class="sxs-lookup"><span data-stu-id="020ff-138">Retrieving Values</span></span>

<span data-ttu-id="020ff-139">Null 許容型の変数の値を取得するには、まずその <xref:System.Nullable%601.HasValue%2A> プロパティをテストして、値があることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="020ff-139">To retrieve the value of a variable of a nullable type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="020ff-140"><xref:System.Nullable%601.HasValue%2A> が `False`ときに値を読み込んだ場合、Visual Basic は <xref:System.InvalidOperationException> 例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="020ff-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="020ff-141">次の例は、前の例の変数 `numberOfChildren` を読み取るための推奨される方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="020ff-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a><span data-ttu-id="020ff-142">Null 許容型の比較</span><span class="sxs-lookup"><span data-stu-id="020ff-142">Comparing Nullable Types</span></span>

<span data-ttu-id="020ff-143">Null 値を許容する `Boolean` 変数がブール式で使用される場合、結果は `True`、`False`、または `Nothing`になります。</span><span class="sxs-lookup"><span data-stu-id="020ff-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="020ff-144">`And` と `Or`の真理テーブルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="020ff-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="020ff-145">`b1` と `b2` は3つの値を持つことができるため、評価するのは9つの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="020ff-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>

|<span data-ttu-id="020ff-146">B</span><span class="sxs-lookup"><span data-stu-id="020ff-146">b1</span></span>|<span data-ttu-id="020ff-147">b2</span><span class="sxs-lookup"><span data-stu-id="020ff-147">b2</span></span>|<span data-ttu-id="020ff-148">b1 と b2</span><span class="sxs-lookup"><span data-stu-id="020ff-148">b1 And b2</span></span>|<span data-ttu-id="020ff-149">b1 または b2</span><span class="sxs-lookup"><span data-stu-id="020ff-149">b1 Or b2</span></span>|
|--------|--------|---------------|--------------|
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|
|`Nothing`|`True`|`Nothing`|`True`|
|`Nothing`|`False`|`False`|`Nothing`|
|`True`|`Nothing`|`Nothing`|`True`|
|`True`|`True`|`True`|`True`|
|`True`|`False`|`False`|`True`|
|`False`|`Nothing`|`False`|`Nothing`|
|`False`|`True`|`False`|`True`|
|`False`|`False`|`False`|`False`|

<span data-ttu-id="020ff-150">ブール型の変数または式の値が `Nothing`場合、`true` も `false`もありません。</span><span class="sxs-lookup"><span data-stu-id="020ff-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="020ff-151">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="020ff-151">Consider the following example.</span></span>

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

<span data-ttu-id="020ff-152">この例では、`b1 And b2` が `Nothing`に評価されます。</span><span class="sxs-lookup"><span data-stu-id="020ff-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="020ff-153">その結果、各 `If` ステートメントで `Else` 句が実行され、出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="020ff-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>

`Expression is not true`

`Expression is not false`

> [!NOTE]
> <span data-ttu-id="020ff-154">ショートサーキット評価を使用する `AndAlso` および `OrElse`では、最初のが `Nothing`に評価されるときに、2番目のオペランドを評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="020ff-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>

## <a name="propagation"></a><span data-ttu-id="020ff-155">伝達</span><span class="sxs-lookup"><span data-stu-id="020ff-155">Propagation</span></span>

<span data-ttu-id="020ff-156">算術演算、比較演算子、シフト演算、または型演算のオペランドの一方または両方が null 値を許容する場合、演算の結果も null 値を許容します。</span><span class="sxs-lookup"><span data-stu-id="020ff-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is nullable, the result of the operation is also nullable.</span></span> <span data-ttu-id="020ff-157">両方のオペランドの値が `Nothing`でない場合は、オペランドの基になる値に対して演算が実行されますが、どちらも null 許容型ではありません。</span><span class="sxs-lookup"><span data-stu-id="020ff-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable type.</span></span> <span data-ttu-id="020ff-158">次の例では、変数 `compare1` および `sum1` が暗黙的に型指定されています。</span><span class="sxs-lookup"><span data-stu-id="020ff-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="020ff-159">これらの上にマウスポインターを置くと、その両方の null 許容型がコンパイラによって推論されます。</span><span class="sxs-lookup"><span data-stu-id="020ff-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable types for both of them.</span></span>

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

<span data-ttu-id="020ff-160">一方または両方のオペランドの値が `Nothing`の場合、結果は `Nothing`されます。</span><span class="sxs-lookup"><span data-stu-id="020ff-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a><span data-ttu-id="020ff-161">データでの Null 許容型の使用</span><span class="sxs-lookup"><span data-stu-id="020ff-161">Using Nullable Types with Data</span></span>

<span data-ttu-id="020ff-162">データベースは、null 許容型を使用する最も重要な場所の1つです。</span><span class="sxs-lookup"><span data-stu-id="020ff-162">A database is one of the most important places to use nullable types.</span></span> <span data-ttu-id="020ff-163">現在、すべてのデータベースオブジェクトが null 許容型をサポートしているわけではありませんが、デザイナーによって生成されたテーブルアダプターでは、</span><span class="sxs-lookup"><span data-stu-id="020ff-163">Not all database objects currently support nullable types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="020ff-164">「 [TableAdapter による null 許容型のサポート」を](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types)参照してください。</span><span class="sxs-lookup"><span data-stu-id="020ff-164">See [TableAdapter support for nullable types](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="020ff-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="020ff-165">See also</span></span>

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [<span data-ttu-id="020ff-166">データの種類</span><span class="sxs-lookup"><span data-stu-id="020ff-166">Data Types</span></span>](index.md)
- [<span data-ttu-id="020ff-167">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="020ff-167">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="020ff-168">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="020ff-168">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="020ff-169">TableAdapters を使用してデータセットを入力する</span><span class="sxs-lookup"><span data-stu-id="020ff-169">Fill datasets by using TableAdapters</span></span>](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [<span data-ttu-id="020ff-170">If 演算子</span><span class="sxs-lookup"><span data-stu-id="020ff-170">If Operator</span></span>](../../../language-reference/operators/if-operator.md)
- [<span data-ttu-id="020ff-171">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="020ff-171">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="020ff-172">Is 演算子</span><span class="sxs-lookup"><span data-stu-id="020ff-172">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="020ff-173">IsNot 演算子</span><span class="sxs-lookup"><span data-stu-id="020ff-173">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="020ff-174">Null 許容値型C#()</span><span class="sxs-lookup"><span data-stu-id="020ff-174">Nullable Value Types (C#)</span></span>](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
