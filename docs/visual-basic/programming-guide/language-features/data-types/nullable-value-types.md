---
title: Null 許容値型の Visual Basic
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
ms.openlocfilehash: 46564d2c509fe2b53b9662ee441ab8b85fccc693
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642134"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="911e7-102">null 許容値型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="911e7-102">Nullable Value Types (Visual Basic)</span></span>

<span data-ttu-id="911e7-103">特定の状況で定義されている値を含まない値の型を操作することがあります。</span><span class="sxs-lookup"><span data-stu-id="911e7-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="911e7-104">たとえば、データベース内のフィールドは、意味のある割り当てられた値を持つと、値が割り当てられる必要があるとを区別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="911e7-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="911e7-105">値の型は、通常の値または null 値のいずれかを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="911e7-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="911e7-106">このような拡張機能が呼び出された、 *null 許容型*します。</span><span class="sxs-lookup"><span data-stu-id="911e7-106">Such an extension is called a *nullable type*.</span></span>

<span data-ttu-id="911e7-107">各 null 許容型がジェネリックから構築された<xref:System.Nullable%601>構造体。</span><span class="sxs-lookup"><span data-stu-id="911e7-107">Each nullable type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="911e7-108">作業に関連するアクティビティを追跡するデータベースを検討してください。</span><span class="sxs-lookup"><span data-stu-id="911e7-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="911e7-109">次の例を構築する null 許容`Boolean`を入力し、その型の変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="911e7-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="911e7-110">次の 3 つの方法では、宣言を記述できます。</span><span class="sxs-lookup"><span data-stu-id="911e7-110">You can write the declaration in three ways:</span></span>

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

<span data-ttu-id="911e7-111">変数`ridesBusToWork`の値を保持できる`True`、@property `False`、またはすべてに値がありません。</span><span class="sxs-lookup"><span data-stu-id="911e7-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="911e7-112">初期の既定値はありません値、ここで可能性があることについては、いないまだに対して取得されたこの人。</span><span class="sxs-lookup"><span data-stu-id="911e7-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="911e7-113">これに対し、`False`情報が取得され、ユーザーが仕事のバスをオーバーライドしていないことを意味する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="911e7-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>

<span data-ttu-id="911e7-114">Null 許容型変数とプロパティを宣言することができ、null 許容型の要素を含む配列を宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="911e7-114">You can declare variables and properties with nullable types, and you can declare an array with elements of a nullable type.</span></span> <span data-ttu-id="911e7-115">プロシージャを宣言するには、パラメーターとして null 許容型とから null 許容型を返すことができます、`Function`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="911e7-115">You can declare procedures with nullable types as parameters, and you can return a nullable type from a `Function` procedure.</span></span>

<span data-ttu-id="911e7-116">など、配列参照型で null 許容型を構築することはできません、 `String`、またはクラス。</span><span class="sxs-lookup"><span data-stu-id="911e7-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="911e7-117">基になる型は、値型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="911e7-117">The underlying type must be a value type.</span></span> <span data-ttu-id="911e7-118">詳細については、「 [Value Types and Reference Types](value-types-and-reference-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="911e7-118">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>

## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="911e7-119">Null 許容型の変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="911e7-119">Using a Nullable Type Variable</span></span>

<span data-ttu-id="911e7-120">Null 許容型の最も重要なメンバーは、その<xref:System.Nullable%601.HasValue%2A>と<xref:System.Nullable%601.Value%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="911e7-120">The most important members of a nullable type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="911e7-121">Null 許容型では、変数の<xref:System.Nullable%601.HasValue%2A>変数が定義されている値を格納するかどうかがわかります。</span><span class="sxs-lookup"><span data-stu-id="911e7-121">For a variable of a nullable type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="911e7-122">場合<xref:System.Nullable%601.HasValue%2A>は`True`から値を読み取ることができます<xref:System.Nullable%601.Value%2A>します。</span><span class="sxs-lookup"><span data-stu-id="911e7-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="911e7-123">なお両方<xref:System.Nullable%601.HasValue%2A>と<xref:System.Nullable%601.Value%2A>は`ReadOnly`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="911e7-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>

### <a name="default-values"></a><span data-ttu-id="911e7-124">既定値</span><span class="sxs-lookup"><span data-stu-id="911e7-124">Default Values</span></span>

<span data-ttu-id="911e7-125">Null 許容型を持つ変数を宣言するときにその<xref:System.Nullable%601.HasValue%2A>プロパティの既定値を持つ`False`します。</span><span class="sxs-lookup"><span data-stu-id="911e7-125">When you declare a variable with a nullable type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="911e7-126">つまり、既定では変数がない、基になる値型の既定値ではなく、定義済みの値。</span><span class="sxs-lookup"><span data-stu-id="911e7-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="911e7-127">次の例では、変数`numberOfChildren`最初に定義されていない値、場合でも、既定値の`Integer`型は 0 です。</span><span class="sxs-lookup"><span data-stu-id="911e7-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

<span data-ttu-id="911e7-128">Null 値は、定義されていないか不明な値を示すために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="911e7-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="911e7-129">場合`numberOfChildren`として宣言されていた`Integer`情報が現在使用できないことを示す可能性のある値がなくなる。</span><span class="sxs-lookup"><span data-stu-id="911e7-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>

### <a name="storing-values"></a><span data-ttu-id="911e7-130">値を格納します。</span><span class="sxs-lookup"><span data-stu-id="911e7-130">Storing Values</span></span>

<span data-ttu-id="911e7-131">通常の方法で変数または null 許容型のプロパティ値を格納します。</span><span class="sxs-lookup"><span data-stu-id="911e7-131">You store a value in a variable or property of a nullable type in the typical way.</span></span> <span data-ttu-id="911e7-132">次の例では、変数に値を代入`numberOfChildren`前の例で宣言します。</span><span class="sxs-lookup"><span data-stu-id="911e7-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

<span data-ttu-id="911e7-133">変数または null 許容型のプロパティ値が定義されている場合、値を割り当てる必要があるの初期状態に戻すことが発生することができます。</span><span class="sxs-lookup"><span data-stu-id="911e7-133">If a variable or property of a nullable type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="911e7-134">変数またはプロパティを設定して、これを行う`Nothing`、次の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="911e7-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> <span data-ttu-id="911e7-135">割り当てることができます`Nothing`、null 許容型の変数にテストできない`Nothing`等号 (=) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="911e7-135">Although you can assign `Nothing` to a variable of a nullable type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="911e7-136">等号を使用する比較`someVar = Nothing`、常に評価`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="911e7-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="911e7-137">変数をテストする<xref:System.Nullable%601.HasValue%2A>プロパティ`False`、またはテストを使用して、`Is`または`IsNot`演算子。</span><span class="sxs-lookup"><span data-stu-id="911e7-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>

### <a name="retrieving-values"></a><span data-ttu-id="911e7-138">値を取得します。</span><span class="sxs-lookup"><span data-stu-id="911e7-138">Retrieving Values</span></span>

<span data-ttu-id="911e7-139">Null 許容型の変数の値を取得する必要があります初めてテストしたその<xref:System.Nullable%601.HasValue%2A>プロパティに値があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="911e7-139">To retrieve the value of a variable of a nullable type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="911e7-140">値を読み取るしようとする場合と<xref:System.Nullable%601.HasValue%2A>は`False`、Visual Basic をスロー、<xref:System.InvalidOperationException>例外。</span><span class="sxs-lookup"><span data-stu-id="911e7-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="911e7-141">次の例は、変数を読み取り、推奨される方法を示しています。`numberOfChildren`前の例です。</span><span class="sxs-lookup"><span data-stu-id="911e7-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a><span data-ttu-id="911e7-142">Null 許容型を比較します。</span><span class="sxs-lookup"><span data-stu-id="911e7-142">Comparing Nullable Types</span></span>

<span data-ttu-id="911e7-143">Null 許容と`Boolean`の変数のブール式で使用、結果があります`True`、 `False`、または`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="911e7-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="911e7-144">次に、真理値表の`And`と`Or`します。</span><span class="sxs-lookup"><span data-stu-id="911e7-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="911e7-145">`b1`と`b2`これで 3 つの値がある 9 つの組み合わせを評価します。</span><span class="sxs-lookup"><span data-stu-id="911e7-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>

|<span data-ttu-id="911e7-146">B1</span><span class="sxs-lookup"><span data-stu-id="911e7-146">b1</span></span>|<span data-ttu-id="911e7-147">B2</span><span class="sxs-lookup"><span data-stu-id="911e7-147">b2</span></span>|<span data-ttu-id="911e7-148">b1 および b2</span><span class="sxs-lookup"><span data-stu-id="911e7-148">b1 And b2</span></span>|<span data-ttu-id="911e7-149">b1 または b2</span><span class="sxs-lookup"><span data-stu-id="911e7-149">b1 Or b2</span></span>|
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

<span data-ttu-id="911e7-150">ブール値変数または式の値が`Nothing`はどちらも`true`も`false`します。</span><span class="sxs-lookup"><span data-stu-id="911e7-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="911e7-151">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="911e7-151">Consider the following example.</span></span>

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

<span data-ttu-id="911e7-152">この例で`b1 And b2`に評価される`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="911e7-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="911e7-153">結果として、`Else`句が各実行`If`ステートメントと、出力は次のように。</span><span class="sxs-lookup"><span data-stu-id="911e7-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>

`Expression is not true`

`Expression is not false`

> [!NOTE]
> <span data-ttu-id="911e7-154">`AndAlso` `OrElse`、最初の評価が、2 番目のオペランドを評価する必要がありますショート サーキット評価を使用する`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="911e7-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>

## <a name="propagation"></a><span data-ttu-id="911e7-155">伝達</span><span class="sxs-lookup"><span data-stu-id="911e7-155">Propagation</span></span>

<span data-ttu-id="911e7-156">算術演算子、比較、shift キー、または型の操作のオペランドの一方または両方が null 許容の場合は、操作の結果も null 値には。</span><span class="sxs-lookup"><span data-stu-id="911e7-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is nullable, the result of the operation is also nullable.</span></span> <span data-ttu-id="911e7-157">両方のオペランドが値ではない`Nothing`の場合も同じように、オペランドの基になる値で、操作を実行、null 許容型。</span><span class="sxs-lookup"><span data-stu-id="911e7-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable type.</span></span> <span data-ttu-id="911e7-158">次の例では、変数`compare1`と`sum1`は暗黙的に型指定されます。</span><span class="sxs-lookup"><span data-stu-id="911e7-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="911e7-159">上にマウス ポインターを置くと場合、コンパイラがその両方の null 許容型を推論することが表示されます。</span><span class="sxs-lookup"><span data-stu-id="911e7-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable types for both of them.</span></span>

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

<span data-ttu-id="911e7-160">1 つまたは両方のオペランドの値がある場合`Nothing`、結果になります`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="911e7-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a><span data-ttu-id="911e7-161">Null 許容型のデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="911e7-161">Using Nullable Types with Data</span></span>

<span data-ttu-id="911e7-162">データベースは、null 許容型を使用する最も重要な場所の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="911e7-162">A database is one of the most important places to use nullable types.</span></span> <span data-ttu-id="911e7-163">すべてのデータベース オブジェクトが現在 null 許容型をサポートしますが、デザイナーで生成されたテーブル アダプターの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="911e7-163">Not all database objects currently support nullable types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="911e7-164">参照してください[null 許容型のサポートを TableAdapter](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types)します。</span><span class="sxs-lookup"><span data-stu-id="911e7-164">See [TableAdapter support for nullable types](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="911e7-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="911e7-165">See also</span></span>

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [<span data-ttu-id="911e7-166">Null 許容型の使用</span><span class="sxs-lookup"><span data-stu-id="911e7-166">Using Nullable Types</span></span>](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)
- [<span data-ttu-id="911e7-167">データの種類</span><span class="sxs-lookup"><span data-stu-id="911e7-167">Data Types</span></span>](index.md)
- [<span data-ttu-id="911e7-168">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="911e7-168">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="911e7-169">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="911e7-169">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="911e7-170">TableAdapters を使用してデータセットを入力する</span><span class="sxs-lookup"><span data-stu-id="911e7-170">Fill datasets by using TableAdapters</span></span>](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [<span data-ttu-id="911e7-171">If 演算子</span><span class="sxs-lookup"><span data-stu-id="911e7-171">If Operator</span></span>](../../../language-reference/operators/if-operator.md)
- [<span data-ttu-id="911e7-172">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="911e7-172">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="911e7-173">Is 演算子</span><span class="sxs-lookup"><span data-stu-id="911e7-173">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="911e7-174">IsNot 演算子</span><span class="sxs-lookup"><span data-stu-id="911e7-174">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)
