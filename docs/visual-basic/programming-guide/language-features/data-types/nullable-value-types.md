---
title: null 許容値型
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
ms.openlocfilehash: beed8262c50dc68330b8f03aa3d864ed2f8df0d5
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249683"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="2fd3c-102">null 許容値型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2fd3c-102">Nullable Value Types (Visual Basic)</span></span>

<span data-ttu-id="2fd3c-103">特定の状況で定義された値を持たない値型を使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="2fd3c-104">たとえば、データベース内のフィールドでは、意味のある値を割り当てることと、値が割り当てられていないかどうかを区別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="2fd3c-105">値型は、通常の値または null 値を使用するように拡張できます。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="2fd3c-106">このような拡張は *、null 許容型*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-106">Such an extension is called a *nullable type*.</span></span>

<span data-ttu-id="2fd3c-107">各 null 許容値型は、ジェネリック<xref:System.Nullable%601>構造体から構築されます。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-107">Each nullable value type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="2fd3c-108">作業関連のアクティビティを追跡するデータベースを考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="2fd3c-109">次の例では、null 許容`Boolean`型を作成し、その型の変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="2fd3c-110">宣言は、次の 3 つの方法で記述できます。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-110">You can write the declaration in three ways:</span></span>

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

<span data-ttu-id="2fd3c-111">変数`ridesBusToWork`は、 の`True`値を保持するか`False`、値をまったく保持しません。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="2fd3c-112">初期値は全く値ではなく、この場合、このユーザーに関する情報がまだ取得されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="2fd3c-113">対照的に`False`、情報が得られ、その人が仕事にバスに乗っていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>

<span data-ttu-id="2fd3c-114">変数とプロパティを null 許容値型で宣言したり、null 許容値型の要素を持つ配列を宣言したりできます。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-114">You can declare variables and properties with nullable value types, and you can declare an array with elements of a nullable value type.</span></span> <span data-ttu-id="2fd3c-115">null 許容値型をパラメーターとしてプロシージャを宣言したり、プロシージャから null 許容値型を`Function`返したりできます。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-115">You can declare procedures with nullable value types as parameters, and you can return a nullable value type from a `Function` procedure.</span></span>

<span data-ttu-id="2fd3c-116">配列、、クラスなどの参照型に null 許容型を`String`作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="2fd3c-117">基になる型は値型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-117">The underlying type must be a value type.</span></span> <span data-ttu-id="2fd3c-118">詳細については、「[値型と参照型](value-types-and-reference-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-118">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>

## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="2fd3c-119">Null 許容型変数の使用</span><span class="sxs-lookup"><span data-stu-id="2fd3c-119">Using a Nullable Type Variable</span></span>

<span data-ttu-id="2fd3c-120">null 許容値型の最も重要なメンバーは<xref:System.Nullable%601.HasValue%2A>、<xref:System.Nullable%601.Value%2A>そのとプロパティです。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-120">The most important members of a nullable value type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="2fd3c-121">null 許容値型の変数の場合、<xref:System.Nullable%601.HasValue%2A>変数に定義された値が含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-121">For a variable of a nullable value type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="2fd3c-122">が<xref:System.Nullable%601.HasValue%2A>`True`の場合は、 から<xref:System.Nullable%601.Value%2A>値を読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="2fd3c-123">両方<xref:System.Nullable%601.HasValue%2A>がプロパティ<xref:System.Nullable%601.Value%2A>であることに`ReadOnly`注意してください。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>

### <a name="default-values"></a><span data-ttu-id="2fd3c-124">既定値</span><span class="sxs-lookup"><span data-stu-id="2fd3c-124">Default Values</span></span>

<span data-ttu-id="2fd3c-125">null 許容値型で変数を宣言すると、その<xref:System.Nullable%601.HasValue%2A>プロパティの既定値は`False`です。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-125">When you declare a variable with a nullable value type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="2fd3c-126">つまり、デフォルトでは、変数には、基になる値型の既定値ではなく、定義済みの値がありません。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="2fd3c-127">次の例では、型の`numberOfChildren`既定値が 0 であっても、変数には最初に値が`Integer`定義されていません。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

<span data-ttu-id="2fd3c-128">null 値は、未定義または不明な値を示すのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="2fd3c-129">として`numberOfChildren``Integer`宣言されている場合、情報が現在利用できない可能性のある値はありません。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>

### <a name="storing-values"></a><span data-ttu-id="2fd3c-130">値の格納</span><span class="sxs-lookup"><span data-stu-id="2fd3c-130">Storing Values</span></span>

<span data-ttu-id="2fd3c-131">値は、一般的な方法で null 許容値型の変数またはプロパティに格納します。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-131">You store a value in a variable or property of a nullable value type in the typical way.</span></span> <span data-ttu-id="2fd3c-132">次の例では、前の例で宣言`numberOfChildren`した変数に値を代入します。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

<span data-ttu-id="2fd3c-133">null 許容値型の変数またはプロパティに定義値が含まれている場合、値が割り当てられていないという初期状態に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-133">If a variable or property of a nullable value type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="2fd3c-134">これは、次の例に示すように、変数`Nothing`またはプロパティを に設定して行います。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> <span data-ttu-id="2fd3c-135">null 許容値`Nothing`型の変数に代入することはできますが、等号を使用`Nothing`して変数をテストすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-135">Although you can assign `Nothing` to a variable of a nullable value type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="2fd3c-136">等号を使用する比較、`someVar = Nothing`は常に`Nothing`に評価されます。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="2fd3c-137"><xref:System.Nullable%601.HasValue%2A>の変数のプロパティ`False`をテストするか、`Is`演算子を`IsNot`使用してテストできます。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>

### <a name="retrieving-values"></a><span data-ttu-id="2fd3c-138">値の取得</span><span class="sxs-lookup"><span data-stu-id="2fd3c-138">Retrieving Values</span></span>

<span data-ttu-id="2fd3c-139">null 許容値型の変数の値を取得するには、まずそのプロパティを<xref:System.Nullable%601.HasValue%2A>テストして値が設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-139">To retrieve the value of a variable of a nullable value type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="2fd3c-140">のときに<xref:System.Nullable%601.HasValue%2A>値を読み取ろうとすると`False`、例外がスローされます<xref:System.InvalidOperationException>。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="2fd3c-141">次の例は、前の例の変数`numberOfChildren`を読み取る推奨方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a><span data-ttu-id="2fd3c-142">Null 許容型の比較</span><span class="sxs-lookup"><span data-stu-id="2fd3c-142">Comparing Nullable Types</span></span>

<span data-ttu-id="2fd3c-143">ブール式で`Boolean`null 許容変数を使用する場合、結果`True`は`False`、 `Nothing`、または になります。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="2fd3c-144">以下は、 と`And``Or`の真の表です。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="2fd3c-145">3 つの値が設定されているため`b1`、評価する組み合わせは 9 つあります。 `b2`</span><span class="sxs-lookup"><span data-stu-id="2fd3c-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>

|<span data-ttu-id="2fd3c-146">b1</span><span class="sxs-lookup"><span data-stu-id="2fd3c-146">b1</span></span>|<span data-ttu-id="2fd3c-147">B2</span><span class="sxs-lookup"><span data-stu-id="2fd3c-147">b2</span></span>|<span data-ttu-id="2fd3c-148">b1 と b2</span><span class="sxs-lookup"><span data-stu-id="2fd3c-148">b1 And b2</span></span>|<span data-ttu-id="2fd3c-149">b1 または b2</span><span class="sxs-lookup"><span data-stu-id="2fd3c-149">b1 Or b2</span></span>|
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

<span data-ttu-id="2fd3c-150">ブール変数または式の値が`Nothing`の場合、値は`true`で`false`もなく、 でもありません。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="2fd3c-151">各データ メンバー フィールドが JSON オブジェクトにマップされ、フィールド名がオブジェクトの "key" 部分にマップされ、"value" 部分がオブジェクトの値の部分に再帰的にマップされます。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-151">Consider the following example.</span></span>

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

<span data-ttu-id="2fd3c-152">この例では、`b1 And b2`に評価`Nothing`されます。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="2fd3c-153">その結果、文は`Else`各`If`文で実行され、出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>

`Expression is not true`

`Expression is not false`

> [!NOTE]
> <span data-ttu-id="2fd3c-154">`AndAlso`と`OrElse`は、短絡評価を使用して、最初のオペランドが に評価されたときに、2`Nothing`番目のオペランドを評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>

## <a name="propagation"></a><span data-ttu-id="2fd3c-155">伝達</span><span class="sxs-lookup"><span data-stu-id="2fd3c-155">Propagation</span></span>

<span data-ttu-id="2fd3c-156">算術演算、比較演算、シフト演算、または型演算のオペランドの一方または両方が NULL 許容値型である場合、演算の結果も NULL 許容値型になります。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is a nullable value type, the result of the operation is also a nullable value type.</span></span> <span data-ttu-id="2fd3c-157">両方のオペランドにはない`Nothing`値がある場合、演算は、どちらも null 許容値型ではないかのように、オペランドの基になる値に対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable value type.</span></span> <span data-ttu-id="2fd3c-158">次の例では、変数`compare1`と`sum1`暗黙的に型指定されます。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="2fd3c-159">マウス ポインターを上に置くと、コンパイラは両方の null 許容値型を推論します。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable value types for both of them.</span></span>

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

<span data-ttu-id="2fd3c-160">一方または両方の`Nothing`オペランドの値が の場合、結果は`Nothing`になります。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a><span data-ttu-id="2fd3c-161">Null 許容型をデータで使用する</span><span class="sxs-lookup"><span data-stu-id="2fd3c-161">Using Nullable Types with Data</span></span>

<span data-ttu-id="2fd3c-162">データベースは、null 許容値型を使用する最も重要な場所の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-162">A database is one of the most important places to use nullable value types.</span></span> <span data-ttu-id="2fd3c-163">現在、すべてのデータベース オブジェクトが null 許容値型をサポートしているわけではありませんが、デザイナによって生成されたテーブル アダプタはサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-163">Not all database objects currently support nullable value types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="2fd3c-164">[Null 許容型のテーブルアダプターのサポート](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fd3c-164">See [TableAdapter support for nullable types](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="2fd3c-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="2fd3c-165">See also</span></span>

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [<span data-ttu-id="2fd3c-166">データ型</span><span class="sxs-lookup"><span data-stu-id="2fd3c-166">Data Types</span></span>](index.md)
- [<span data-ttu-id="2fd3c-167">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="2fd3c-167">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="2fd3c-168">データ型のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2fd3c-168">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="2fd3c-169">TableAdapters を使用してデータセットを入力する</span><span class="sxs-lookup"><span data-stu-id="2fd3c-169">Fill datasets by using TableAdapters</span></span>](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [<span data-ttu-id="2fd3c-170">If 演算子</span><span class="sxs-lookup"><span data-stu-id="2fd3c-170">If Operator</span></span>](../../../language-reference/operators/if-operator.md)
- [<span data-ttu-id="2fd3c-171">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="2fd3c-171">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="2fd3c-172">Is 演算子</span><span class="sxs-lookup"><span data-stu-id="2fd3c-172">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="2fd3c-173">IsNot 演算子</span><span class="sxs-lookup"><span data-stu-id="2fd3c-173">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="2fd3c-174">Null 許容値型 (C#)</span><span class="sxs-lookup"><span data-stu-id="2fd3c-174">Nullable Value Types (C#)</span></span>](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
