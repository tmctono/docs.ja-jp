---
title: C# 演算子と式 - C# リファレンス
description: C# 演算子と式、演算子の優先順位、および演算子の結合規則について説明します
ms.date: 08/04/2020
f1_keywords:
- cs.operators
helpviewer_keywords:
- operators [C#]
- operator precedence [C#]
- operator associativity [C#]
- expressions [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: 854d7c1278319869104e1758ba91eb3594741126
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063186"
---
# <a name="c-operators-and-expressions-c-reference"></a><span data-ttu-id="d68f2-103">C# 演算子と式 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="d68f2-103">C# operators and expressions (C# reference)</span></span>

<span data-ttu-id="d68f2-104">C# には多数の演算子が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d68f2-104">C# provides a number of operators.</span></span> <span data-ttu-id="d68f2-105">これらの多くは[組み込み型](../builtin-types/built-in-types.md)によってサポートされており、これらの型の値を使用して基本的な操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d68f2-105">Many of them are supported by the [built-in types](../builtin-types/built-in-types.md) and allow you to perform basic operations with values of those types.</span></span> <span data-ttu-id="d68f2-106">これらの演算子には、次のグループが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d68f2-106">Those operators include the following groups:</span></span>

- <span data-ttu-id="d68f2-107">[算術演算子](arithmetic-operators.md)では、数値オペランドを使用して算術演算が実行されます</span><span class="sxs-lookup"><span data-stu-id="d68f2-107">[Arithmetic operators](arithmetic-operators.md) that perform arithmetic operations with numeric operands</span></span>
- <span data-ttu-id="d68f2-108">[比較演算子](comparison-operators.md)では、数値オペランドが比較されます</span><span class="sxs-lookup"><span data-stu-id="d68f2-108">[Comparison operators](comparison-operators.md) that compare numeric operands</span></span>
- <span data-ttu-id="d68f2-109">[ブール論理演算子](boolean-logical-operators.md)では、[`bool`](../builtin-types/bool.md) オペランドに対して論理演算が実行されます</span><span class="sxs-lookup"><span data-stu-id="d68f2-109">[Boolean logical operators](boolean-logical-operators.md) that perform logical operations with [`bool`](../builtin-types/bool.md) operands</span></span>
- <span data-ttu-id="d68f2-110">[ビットごとおよびシフト演算子](bitwise-and-shift-operators.md)では、整数型のオペランドに対してビットごとまたはシフト演算が実行されます</span><span class="sxs-lookup"><span data-stu-id="d68f2-110">[Bitwise and shift operators](bitwise-and-shift-operators.md) that perform bitwise or shift operations with operands of the integral types</span></span>
- <span data-ttu-id="d68f2-111">[等値演算子](equality-operators.md)では、そのオペランドが等しいかどうかが確認されます</span><span class="sxs-lookup"><span data-stu-id="d68f2-111">[Equality operators](equality-operators.md) that check if their operands are equal or not</span></span>

<span data-ttu-id="d68f2-112">通常は、これらの演算子を[オーバーロード](operator-overloading.md)できます。つまり、ユーザー定義型のオペランドに対して演算子の動作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d68f2-112">Typically, you can [overload](operator-overloading.md) those operators, that is, specify the operator behavior for the operands of a user-defined type.</span></span>

<span data-ttu-id="d68f2-113">最も単純な C# 式は、変数のリテラル (たとえば、[整数](../builtin-types/integral-numeric-types.md#integer-literals)と[実数](../builtin-types/floating-point-numeric-types.md#real-literals)の数) と名前です。</span><span class="sxs-lookup"><span data-stu-id="d68f2-113">The simplest C# expressions are literals (for example, [integer](../builtin-types/integral-numeric-types.md#integer-literals) and [real](../builtin-types/floating-point-numeric-types.md#real-literals) numbers) and names of variables.</span></span> <span data-ttu-id="d68f2-114">演算子を使用すると、これらを複雑な式に組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="d68f2-114">You can combine them into complex expressions by using operators.</span></span> <span data-ttu-id="d68f2-115">演算子の[優先順位](#operator-precedence)と[結合規則](#operator-associativity)によって、式の中の操作の実行順序が決まります。</span><span class="sxs-lookup"><span data-stu-id="d68f2-115">Operator [precedence](#operator-precedence) and [associativity](#operator-associativity) determine the order in which the operations in an expression are performed.</span></span> <span data-ttu-id="d68f2-116">かっこを使用すれば、演算子の優先順位と結合規則によって定められた評価の順序を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="d68f2-116">You can use parentheses to change the order of evaluation imposed by operator precedence and associativity.</span></span>

<span data-ttu-id="d68f2-117">次のコードでは、式の例が代入の右側にあります。</span><span class="sxs-lookup"><span data-stu-id="d68f2-117">In the following code, examples of expressions are at the right-hand side of assignments:</span></span>

[!code-csharp[expression examples](snippets/shared/Overview.cs#Expressions)]

<span data-ttu-id="d68f2-118">通常、式によって結果が生成され、別の式に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d68f2-118">Typically, an expression produces a result and can be included in another expression.</span></span> <span data-ttu-id="d68f2-119">[`void`](../builtin-types/void.md) メソッド呼び出しは、結果を生成しない式の例です。</span><span class="sxs-lookup"><span data-stu-id="d68f2-119">A [`void`](../builtin-types/void.md) method call is an example of an expression that doesn't produce a result.</span></span> <span data-ttu-id="d68f2-120">次の例に示すように、これは[ステートメント](../../programming-guide/statements-expressions-operators/statements.md)としてのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d68f2-120">It can be used only as a [statement](../../programming-guide/statements-expressions-operators/statements.md), as the following example shows:</span></span>

```csharp
Console.WriteLine("Hello, world!");
```

<span data-ttu-id="d68f2-121">C# に用意されている他の種類の式を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d68f2-121">Here are some other kinds of expressions that C# provides:</span></span>

- <span data-ttu-id="d68f2-122">[補間された文字列式](../tokens/interpolated.md)では、書式設定された文字列を作成するための便利な構文が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d68f2-122">[Interpolated string expressions](../tokens/interpolated.md) that provide convenient syntax to create formatted strings:</span></span>

  [!code-csharp-interactive[interpolated string](snippets/shared/Overview.cs#InterpolatedString)]

- <span data-ttu-id="d68f2-123">[ラムダ式](lambda-expressions.md)を使用すると、匿名関数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d68f2-123">[Lambda expressions](lambda-expressions.md) that allow you to create anonymous functions:</span></span>

  [!code-csharp-interactive[lambda expression](snippets/shared/Overview.cs#Lambda)]

- <span data-ttu-id="d68f2-124">[クエリ式](../keywords/query-keywords.md)を使用すると、C# でクエリ機能を直接使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d68f2-124">[Query expressions](../keywords/query-keywords.md) that allow you to use query capabilities directly in C#:</span></span>

  [!code-csharp-interactive[query expression](snippets/shared/Overview.cs#Query)]

<span data-ttu-id="d68f2-125">[式本体の定義](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)を使用すると、メソッド、コンストラクター、プロパティ、インデクサー、またはファイナライザーの簡潔な定義を提供できます。</span><span class="sxs-lookup"><span data-stu-id="d68f2-125">You can use an [expression body definition](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) to provide a concise definition for a method, constructor, property, indexer, or finalizer.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="d68f2-126">演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="d68f2-126">Operator precedence</span></span>

<span data-ttu-id="d68f2-127">複数の演算子を含む式では、優先順位の高い方の演算子が優先順位の低い方の演算子よりも先に評価されます。</span><span class="sxs-lookup"><span data-stu-id="d68f2-127">In an expression with multiple operators, the operators with higher precedence are evaluated before the operators with lower precedence.</span></span> <span data-ttu-id="d68f2-128">次の例では、乗算は加算より優先順位が高いため、最初に乗算が実行されます。</span><span class="sxs-lookup"><span data-stu-id="d68f2-128">In the following example, the multiplication is performed first because it has higher precedence than addition:</span></span>

```csharp-interactive
var a = 2 + 2 * 2;
Console.WriteLine(a); //  output: 6
```

<span data-ttu-id="d68f2-129">演算子の優先順位によって定められた評価の順序を変更するには、かっこを使用します。</span><span class="sxs-lookup"><span data-stu-id="d68f2-129">Use parentheses to change the order of evaluation imposed by operator precedence:</span></span>

```csharp-interactive
var a = (2 + 2) * 2;
Console.WriteLine(a); //  output: 8
```

<span data-ttu-id="d68f2-130">次の表は、C# の演算子を優先順位の高い順にまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="d68f2-130">The following table lists the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="d68f2-131">各行内の演算子の優先順位は同じです。</span><span class="sxs-lookup"><span data-stu-id="d68f2-131">The operators within each row have the same precedence.</span></span>

| <span data-ttu-id="d68f2-132">演算子</span><span class="sxs-lookup"><span data-stu-id="d68f2-132">Operators</span></span> | <span data-ttu-id="d68f2-133">カテゴリまたは名前</span><span class="sxs-lookup"><span data-stu-id="d68f2-133">Category or name</span></span> |
| --------- | ---------------- |
| <span data-ttu-id="d68f2-134">[x.y](member-access-operators.md#member-access-expression-)、[f(x)](member-access-operators.md#invocation-expression-)、[a&#91;i&#93;](member-access-operators.md#indexer-operator-)、[`x?.y`](member-access-operators.md#null-conditional-operators--and-)、[`x?[y]`](member-access-operators.md#null-conditional-operators--and-)、[x++](arithmetic-operators.md#increment-operator-)、[x--](arithmetic-operators.md#decrement-operator---)、[x!](null-forgiving.md)、[new](new-operator.md)、[typeof](type-testing-and-cast.md#typeof-operator)、[checked](../keywords/checked.md)、[unchecked](../keywords/unchecked.md)、[default](default.md)、[nameof](nameof.md)、[delegate](delegate-operator.md)、[sizeof](sizeof.md)、[stackalloc](stackalloc.md)、[x->y](pointer-related-operators.md#pointer-member-access-operator--)</span><span class="sxs-lookup"><span data-stu-id="d68f2-134">[x.y](member-access-operators.md#member-access-expression-), [f(x)](member-access-operators.md#invocation-expression-), [a&#91;i&#93;](member-access-operators.md#indexer-operator-), [`x?.y`](member-access-operators.md#null-conditional-operators--and-), [`x?[y]`](member-access-operators.md#null-conditional-operators--and-), [x++](arithmetic-operators.md#increment-operator-), [x--](arithmetic-operators.md#decrement-operator---), [x!](null-forgiving.md), [new](new-operator.md), [typeof](type-testing-and-cast.md#typeof-operator), [checked](../keywords/checked.md), [unchecked](../keywords/unchecked.md), [default](default.md), [nameof](nameof.md), [delegate](delegate-operator.md), [sizeof](sizeof.md), [stackalloc](stackalloc.md), [x->y](pointer-related-operators.md#pointer-member-access-operator--)</span></span> | <span data-ttu-id="d68f2-135">1 次式</span><span class="sxs-lookup"><span data-stu-id="d68f2-135">Primary</span></span> |
| <span data-ttu-id="d68f2-136">[+x](arithmetic-operators.md#unary-plus-and-minus-operators)、[-x](arithmetic-operators.md#unary-plus-and-minus-operators)、[\!x](boolean-logical-operators.md#logical-negation-operator-)、[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-)、[++x](arithmetic-operators.md#increment-operator-)、[--x](arithmetic-operators.md#decrement-operator---)、[^x](member-access-operators.md#index-from-end-operator-)、[(T)x](type-testing-and-cast.md#cast-expression)、[await](await.md)、[&x](pointer-related-operators.md#address-of-operator-)、[\*x](pointer-related-operators.md#pointer-indirection-operator-)、[true and false](true-false-operators.md)</span><span class="sxs-lookup"><span data-stu-id="d68f2-136">[+x](arithmetic-operators.md#unary-plus-and-minus-operators), [-x](arithmetic-operators.md#unary-plus-and-minus-operators), [\!x](boolean-logical-operators.md#logical-negation-operator-), [~x](bitwise-and-shift-operators.md#bitwise-complement-operator-), [++x](arithmetic-operators.md#increment-operator-), [--x](arithmetic-operators.md#decrement-operator---), [^x](member-access-operators.md#index-from-end-operator-), [(T)x](type-testing-and-cast.md#cast-expression), [await](await.md), [&x](pointer-related-operators.md#address-of-operator-), [\*x](pointer-related-operators.md#pointer-indirection-operator-), [true and false](true-false-operators.md)</span></span> | <span data-ttu-id="d68f2-137">単項</span><span class="sxs-lookup"><span data-stu-id="d68f2-137">Unary</span></span> |
| [<span data-ttu-id="d68f2-138">x..y</span><span class="sxs-lookup"><span data-stu-id="d68f2-138">x..y</span></span>](member-access-operators.md#range-operator-) | <span data-ttu-id="d68f2-139">範囲</span><span class="sxs-lookup"><span data-stu-id="d68f2-139">Range</span></span> |
| [<span data-ttu-id="d68f2-140">switch</span><span class="sxs-lookup"><span data-stu-id="d68f2-140">switch</span></span>](switch-expression.md) | <span data-ttu-id="d68f2-141">`switch` 式</span><span class="sxs-lookup"><span data-stu-id="d68f2-141">`switch` expression</span></span> |
| <span data-ttu-id="d68f2-142">[x \* y](arithmetic-operators.md#multiplication-operator-)、[x / y](arithmetic-operators.md#division-operator-)、[x % y](arithmetic-operators.md#remainder-operator-)</span><span class="sxs-lookup"><span data-stu-id="d68f2-142">[x \* y](arithmetic-operators.md#multiplication-operator-), [x / y](arithmetic-operators.md#division-operator-), [x % y](arithmetic-operators.md#remainder-operator-)</span></span> | <span data-ttu-id="d68f2-143">乗法</span><span class="sxs-lookup"><span data-stu-id="d68f2-143">Multiplicative</span></span>|
| <span data-ttu-id="d68f2-144">[x + y](arithmetic-operators.md#addition-operator-)、[x – y](arithmetic-operators.md#subtraction-operator--)</span><span class="sxs-lookup"><span data-stu-id="d68f2-144">[x + y](arithmetic-operators.md#addition-operator-), [x – y](arithmetic-operators.md#subtraction-operator--)</span></span> | <span data-ttu-id="d68f2-145">加法</span><span class="sxs-lookup"><span data-stu-id="d68f2-145">Additive</span></span> |
| <span data-ttu-id="d68f2-146">[x \<\<  y](bitwise-and-shift-operators.md#left-shift-operator-), [x >> y](bitwise-and-shift-operators.md#right-shift-operator-)</span><span class="sxs-lookup"><span data-stu-id="d68f2-146">[x \<\<  y](bitwise-and-shift-operators.md#left-shift-operator-), [x >> y](bitwise-and-shift-operators.md#right-shift-operator-)</span></span> | <span data-ttu-id="d68f2-147">シフト</span><span class="sxs-lookup"><span data-stu-id="d68f2-147">Shift</span></span> |
| <span data-ttu-id="d68f2-148">[x \< y](comparison-operators.md#less-than-operator-), [x > y](comparison-operators.md#greater-than-operator-)、[x \<= y](comparison-operators.md#less-than-or-equal-operator-), [x >= y](comparison-operators.md#greater-than-or-equal-operator-)、[is](type-testing-and-cast.md#is-operator)、[as](type-testing-and-cast.md#as-operator)</span><span class="sxs-lookup"><span data-stu-id="d68f2-148">[x \< y](comparison-operators.md#less-than-operator-), [x > y](comparison-operators.md#greater-than-operator-), [x \<= y](comparison-operators.md#less-than-or-equal-operator-), [x >= y](comparison-operators.md#greater-than-or-equal-operator-), [is](type-testing-and-cast.md#is-operator), [as](type-testing-and-cast.md#as-operator)</span></span> | <span data-ttu-id="d68f2-149">関係式と型検査</span><span class="sxs-lookup"><span data-stu-id="d68f2-149">Relational and type-testing</span></span> |
| <span data-ttu-id="d68f2-150">[x == y](equality-operators.md#equality-operator-), [x != y](equality-operators.md#inequality-operator-)</span><span class="sxs-lookup"><span data-stu-id="d68f2-150">[x == y](equality-operators.md#equality-operator-), [x != y](equality-operators.md#inequality-operator-)</span></span> | <span data-ttu-id="d68f2-151">等価比較</span><span class="sxs-lookup"><span data-stu-id="d68f2-151">Equality</span></span> |
| `x & y` | <span data-ttu-id="d68f2-152">[ブール演算の論理 AND](boolean-logical-operators.md#logical-and-operator-) または[ビット演算の論理 AND](bitwise-and-shift-operators.md#logical-and-operator-)</span><span class="sxs-lookup"><span data-stu-id="d68f2-152">[Boolean logical AND](boolean-logical-operators.md#logical-and-operator-) or [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-)</span></span> |
| `x ^ y` | <span data-ttu-id="d68f2-153">[ブール演算の論理 XOR](boolean-logical-operators.md#logical-exclusive-or-operator-) または[ビット演算の論理 XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-)</span><span class="sxs-lookup"><span data-stu-id="d68f2-153">[Boolean logical XOR](boolean-logical-operators.md#logical-exclusive-or-operator-) or [bitwise logical XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-)</span></span> |
| <code>x &#124; y</code> | <span data-ttu-id="d68f2-154">[ブール演算の論理 OR](boolean-logical-operators.md#logical-or-operator-) または[ビット演算の論理 OR](bitwise-and-shift-operators.md#logical-or-operator-)</span><span class="sxs-lookup"><span data-stu-id="d68f2-154">[Boolean logical OR](boolean-logical-operators.md#logical-or-operator-) or [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-)</span></span> |
| [<span data-ttu-id="d68f2-155">x && y</span><span class="sxs-lookup"><span data-stu-id="d68f2-155">x && y</span></span>](boolean-logical-operators.md#conditional-logical-and-operator-) | <span data-ttu-id="d68f2-156">条件 AND</span><span class="sxs-lookup"><span data-stu-id="d68f2-156">Conditional AND</span></span> |
| [<span data-ttu-id="d68f2-157">x &#124;&#124; y</span><span class="sxs-lookup"><span data-stu-id="d68f2-157">x &#124;&#124; y</span></span>](boolean-logical-operators.md#conditional-logical-or-operator-) | <span data-ttu-id="d68f2-158">条件 OR</span><span class="sxs-lookup"><span data-stu-id="d68f2-158">Conditional OR</span></span> |
| [<span data-ttu-id="d68f2-159">x ?? y</span><span class="sxs-lookup"><span data-stu-id="d68f2-159">x ?? y</span></span>](null-coalescing-operator.md) | <span data-ttu-id="d68f2-160">Null 合体演算子</span><span class="sxs-lookup"><span data-stu-id="d68f2-160">Null-coalescing operator</span></span> |
| [<span data-ttu-id="d68f2-161">c ? t : f</span><span class="sxs-lookup"><span data-stu-id="d68f2-161">c ? t : f</span></span>](conditional-operator.md) | <span data-ttu-id="d68f2-162">条件演算子</span><span class="sxs-lookup"><span data-stu-id="d68f2-162">Conditional operator</span></span> |
| <span data-ttu-id="d68f2-163">[x = y](assignment-operator.md)、[x += y](arithmetic-operators.md#compound-assignment)、[x -= y](arithmetic-operators.md#compound-assignment)、[x \*= y](arithmetic-operators.md#compound-assignment)、[x /= y](arithmetic-operators.md#compound-assignment)、[x %= y](arithmetic-operators.md#compound-assignment)、[x &= y](boolean-logical-operators.md#compound-assignment)、[x &#124;= y](boolean-logical-operators.md#compound-assignment)、[x ^= y](boolean-logical-operators.md#compound-assignment)、[x <<= y](bitwise-and-shift-operators.md#compound-assignment)、[x >>= y](bitwise-and-shift-operators.md#compound-assignment)、[x ??= y](null-coalescing-operator.md)、[=>](lambda-operator.md)</span><span class="sxs-lookup"><span data-stu-id="d68f2-163">[x = y](assignment-operator.md), [x += y](arithmetic-operators.md#compound-assignment), [x -= y](arithmetic-operators.md#compound-assignment), [x \*= y](arithmetic-operators.md#compound-assignment), [x /= y](arithmetic-operators.md#compound-assignment), [x %= y](arithmetic-operators.md#compound-assignment), [x &= y](boolean-logical-operators.md#compound-assignment), [x &#124;= y](boolean-logical-operators.md#compound-assignment), [x ^= y](boolean-logical-operators.md#compound-assignment), [x <<= y](bitwise-and-shift-operators.md#compound-assignment), [x >>= y](bitwise-and-shift-operators.md#compound-assignment), [x ??= y](null-coalescing-operator.md), [=>](lambda-operator.md)</span></span> | <span data-ttu-id="d68f2-164">代入とラムダ宣言</span><span class="sxs-lookup"><span data-stu-id="d68f2-164">Assignment and lambda declaration</span></span> |

## <a name="operator-associativity"></a><span data-ttu-id="d68f2-165">演算子の結合規則</span><span class="sxs-lookup"><span data-stu-id="d68f2-165">Operator associativity</span></span>

<span data-ttu-id="d68f2-166">演算子の優先順位が同じ場合は、演算子の結合規則によって、操作の実行順序が決まります。</span><span class="sxs-lookup"><span data-stu-id="d68f2-166">When operators have the same precedence, associativity of the operators determines the order in which the operations are performed:</span></span>

- <span data-ttu-id="d68f2-167">*結合規則が左から右*の演算子は、左から右に順番に評価されます。</span><span class="sxs-lookup"><span data-stu-id="d68f2-167">*Left-associative* operators are evaluated in order from left to right.</span></span> <span data-ttu-id="d68f2-168">[代入演算子](assignment-operator.md)と [null 合体演算子](null-coalescing-operator.md)を除き、2 項演算子はすべて左からの結合です。</span><span class="sxs-lookup"><span data-stu-id="d68f2-168">Except for the [assignment operators](assignment-operator.md) and the [null-coalescing operators](null-coalescing-operator.md), all binary operators are left-associative.</span></span> <span data-ttu-id="d68f2-169">たとえば、`a + b - c` は `(a + b) - c` と評価されます。</span><span class="sxs-lookup"><span data-stu-id="d68f2-169">For example, `a + b - c` is evaluated as `(a + b) - c`.</span></span>
- <span data-ttu-id="d68f2-170">*結合規則が右から左*の演算子は、右から左に評価されます。</span><span class="sxs-lookup"><span data-stu-id="d68f2-170">*Right-associative* operators are evaluated in order from right to left.</span></span> <span data-ttu-id="d68f2-171">代入演算子、null 合体演算子、および[条件演算子`?:`](conditional-operator.md)は、右からの結合です。</span><span class="sxs-lookup"><span data-stu-id="d68f2-171">The assignment operators, the null-coalescing operators, and the [conditional operator `?:`](conditional-operator.md) are right-associative.</span></span> <span data-ttu-id="d68f2-172">たとえば、`x = y = z` は `x = (y = z)` と評価されます。</span><span class="sxs-lookup"><span data-stu-id="d68f2-172">For example, `x = y = z` is evaluated as `x = (y = z)`.</span></span>

<span data-ttu-id="d68f2-173">演算子の結合規則によって定められた評価の順序を変更するには、かっこを使用します。</span><span class="sxs-lookup"><span data-stu-id="d68f2-173">Use parentheses to change the order of evaluation imposed by operator associativity:</span></span>

```csharp-interactive
int a = 13 / 5 / 2;
int b = 13 / (5 / 2);
Console.WriteLine($"a = {a}, b = {b}");  // output: a = 1, b = 6
```

## <a name="operand-evaluation"></a><span data-ttu-id="d68f2-174">オペランドの評価</span><span class="sxs-lookup"><span data-stu-id="d68f2-174">Operand evaluation</span></span>

<span data-ttu-id="d68f2-175">式内のオペランドは、演算子の優先順位と結合規則に関係なく、左から右に評価されます。</span><span class="sxs-lookup"><span data-stu-id="d68f2-175">Unrelated to operator precedence and associativity, operands in an expression are evaluated from left to right.</span></span> <span data-ttu-id="d68f2-176">次の例では、演算子とオペランドが評価される順序を示しています。</span><span class="sxs-lookup"><span data-stu-id="d68f2-176">The following examples demonstrate the order in which operators and operands are evaluated:</span></span>

| <span data-ttu-id="d68f2-177">正規表現</span><span class="sxs-lookup"><span data-stu-id="d68f2-177">Expression</span></span> | <span data-ttu-id="d68f2-178">評価の順序</span><span class="sxs-lookup"><span data-stu-id="d68f2-178">Order of evaluation</span></span> |
| ---------- | ------------------- |
|`a + b`|<span data-ttu-id="d68f2-179">a、b、+</span><span class="sxs-lookup"><span data-stu-id="d68f2-179">a, b, +</span></span>|
|`a + b * c`|<span data-ttu-id="d68f2-180">a、b、c、\*、+</span><span class="sxs-lookup"><span data-stu-id="d68f2-180">a, b, c, \*, +</span></span>|
|`a / b + c * d`|<span data-ttu-id="d68f2-181">a、b、/、c、d、\*、+</span><span class="sxs-lookup"><span data-stu-id="d68f2-181">a, b, /, c, d, \*, +</span></span>|
|`a / (b + c) * d`|<span data-ttu-id="d68f2-182">a、b、c、+、/、d、\*</span><span class="sxs-lookup"><span data-stu-id="d68f2-182">a, b, c, +, /, d, \*</span></span>|

<span data-ttu-id="d68f2-183">通常、演算子のオペランドはすべて評価されます。</span><span class="sxs-lookup"><span data-stu-id="d68f2-183">Typically, all operator operands are evaluated.</span></span> <span data-ttu-id="d68f2-184">ただし、一部の演算子では、条件付きでオペランドが評価されます。</span><span class="sxs-lookup"><span data-stu-id="d68f2-184">However, some operators evaluate operands conditionally.</span></span> <span data-ttu-id="d68f2-185">つまり、このような演算子では、左端のオペランドの値によって、他の (または、どの) オペランドを評価するかどうかが定義されます。</span><span class="sxs-lookup"><span data-stu-id="d68f2-185">That is, the value of the leftmost operand of such an operator defines if (or which) other operands should be evaluated.</span></span> <span data-ttu-id="d68f2-186">これらの演算子は、条件付き論理 [AND (`&&`)](boolean-logical-operators.md#conditional-logical-and-operator-) および [OR (`||`)](boolean-logical-operators.md#conditional-logical-or-operator-) 演算子、[null 合体演算子 `??` と `??=`](null-coalescing-operator.md)、[null 条件演算子 `?.` と `?[]`](member-access-operators.md#null-conditional-operators--and-)、および[条件演算子 `?:`](conditional-operator.md) です。</span><span class="sxs-lookup"><span data-stu-id="d68f2-186">These operators are the conditional logical [AND (`&&`)](boolean-logical-operators.md#conditional-logical-and-operator-) and [OR (`||`)](boolean-logical-operators.md#conditional-logical-or-operator-) operators, the [null-coalescing operators `??` and `??=`](null-coalescing-operator.md), the [null-conditional operators `?.` and `?[]`](member-access-operators.md#null-conditional-operators--and-), and the [conditional operator `?:`](conditional-operator.md).</span></span> <span data-ttu-id="d68f2-187">詳細については、演算子ごとの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d68f2-187">For more information, see the description of each operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d68f2-188">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="d68f2-188">C# language specification</span></span>

<span data-ttu-id="d68f2-189">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d68f2-189">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="d68f2-190">式</span><span class="sxs-lookup"><span data-stu-id="d68f2-190">Expressions</span></span>](~/_csharplang/spec/expressions.md)
- [<span data-ttu-id="d68f2-191">演算子</span><span class="sxs-lookup"><span data-stu-id="d68f2-191">Operators</span></span>](~/_csharplang/spec/expressions.md#operators)

## <a name="see-also"></a><span data-ttu-id="d68f2-192">関連項目</span><span class="sxs-lookup"><span data-stu-id="d68f2-192">See also</span></span>

- [<span data-ttu-id="d68f2-193">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="d68f2-193">C# reference</span></span>](../index.md)
- [<span data-ttu-id="d68f2-194">演算子のオーバーロード</span><span class="sxs-lookup"><span data-stu-id="d68f2-194">Operator overloading</span></span>](operator-overloading.md)
- [<span data-ttu-id="d68f2-195">式ツリー</span><span class="sxs-lookup"><span data-stu-id="d68f2-195">Expression trees</span></span>](../../programming-guide/concepts/expression-trees/index.md)
