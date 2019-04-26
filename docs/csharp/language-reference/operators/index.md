---
title: C# 演算子
ms.date: 04/04/2018
f1_keywords:
- cs.operators
helpviewer_keywords:
- boolean operators [C#]
- expressions [C#], operators
- logical operators [C#]
- operators [C#]
- Visual C#, operators
- indirection operators [C#]
- assignment operators [C#]
- shift operators [C#]
- relational operators [C#]
- bitwise operators [C#]
- address operators [C#]
- keywords [C#], operators
- arithmetic operators [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: f4267caeb6301950b9f6a8b9545a47b9f48e7920
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61689815"
---
# <a name="c-operators"></a><span data-ttu-id="1527a-102">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="1527a-102">C# operators</span></span>

<span data-ttu-id="1527a-103">C# には、多くの演算子が用意されています。演算子とは、式で実行する演算 (数値演算、インデックス作成、関数呼び出しなど) を指定する記号のことです。</span><span class="sxs-lookup"><span data-stu-id="1527a-103">C# provides many operators, which are symbols that specify which operations (math, indexing, function call, etc.) to perform in an expression.</span></span> <span data-ttu-id="1527a-104">多くの演算子は、ユーザー定義型に適用する際に[オーバーロード](../../programming-guide/statements-expressions-operators/overloadable-operators.md)して、その意味を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1527a-104">You can [overload](../../programming-guide/statements-expressions-operators/overloadable-operators.md) many operators to change their meaning when applied to a user-defined type.</span></span>

<span data-ttu-id="1527a-105">整数型に対する演算 (`==`、`!=`、`<`、`>`、`&`、`|`) は、通常、列挙型 (`enum`) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="1527a-105">Operations on integral types (such as `==`, `!=`, `<`, `>`, `&`, `|`) are generally allowed on enumeration (`enum`) types.</span></span>

<span data-ttu-id="1527a-106">ここでは、C# の演算子を優先順位の高い順に示します。</span><span class="sxs-lookup"><span data-stu-id="1527a-106">The sections below list the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="1527a-107">各セクションの演算子の優先順位は同じです。</span><span class="sxs-lookup"><span data-stu-id="1527a-107">The operators within each section share the same precedence level.</span></span>

## <a name="primary-operators"></a><span data-ttu-id="1527a-108">主な演算子</span><span class="sxs-lookup"><span data-stu-id="1527a-108">Primary operators</span></span>

<span data-ttu-id="1527a-109">優先順位が最も高い演算子です。</span><span class="sxs-lookup"><span data-stu-id="1527a-109">These are the highest precedence operators.</span></span>

<span data-ttu-id="1527a-110">[x.y](member-access-operator.md) – メンバー アクセス。</span><span class="sxs-lookup"><span data-stu-id="1527a-110">[x.y](member-access-operator.md) – member access.</span></span>

<span data-ttu-id="1527a-111">[x?.y](null-conditional-operators.md) – null 条件付きのメンバー アクセス。</span><span class="sxs-lookup"><span data-stu-id="1527a-111">[x?.y](null-conditional-operators.md) – null conditional member access.</span></span> <span data-ttu-id="1527a-112">左側のオペランドが `null` に評価される場合に `null` を返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-112">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="1527a-113">[x?[y]](null-conditional-operators.md) - null 条件付きのインデックス アクセス。</span><span class="sxs-lookup"><span data-stu-id="1527a-113">[x?[y]](null-conditional-operators.md) - null conditional index access.</span></span> <span data-ttu-id="1527a-114">左側のオペランドが `null` に評価される場合に `null` を返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-114">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="1527a-115">[f(x)](invocation-operator.md) – 関数の呼び出し。</span><span class="sxs-lookup"><span data-stu-id="1527a-115">[f(x)](invocation-operator.md) – function invocation.</span></span>

<span data-ttu-id="1527a-116">[a&#91;x&#93;](index-operator.md) – 集約オブジェクトのインデックス作成。</span><span class="sxs-lookup"><span data-stu-id="1527a-116">[a&#91;x&#93;](index-operator.md) – aggregate object indexing.</span></span>

<span data-ttu-id="1527a-117">[x++](arithmetic-operators.md#increment-operator-) – 後置インクリメント。</span><span class="sxs-lookup"><span data-stu-id="1527a-117">[x++](arithmetic-operators.md#increment-operator-) – postfix increment.</span></span> <span data-ttu-id="1527a-118">x の値を返した後、1 大きくなった (通常は整数 1 が加算された) x の値で格納場所を更新します。</span><span class="sxs-lookup"><span data-stu-id="1527a-118">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="1527a-119">[x--](arithmetic-operators.md#decrement-operator---) – 後置デクリメント。</span><span class="sxs-lookup"><span data-stu-id="1527a-119">[x--](arithmetic-operators.md#decrement-operator---) –  postfix decrement.</span></span> <span data-ttu-id="1527a-120">x の値を返した後、1 小さくなった (通常は整数 1 が減算された) x の値で格納場所を更新します。</span><span class="sxs-lookup"><span data-stu-id="1527a-120">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="1527a-121">[new](../keywords/new-operator.md) – 型のインスタンス化。</span><span class="sxs-lookup"><span data-stu-id="1527a-121">[new](../keywords/new-operator.md) – type instantiation.</span></span>

<span data-ttu-id="1527a-122">[typeof](../keywords/typeof.md) – オペランドを表す <xref:System.Type> オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-122">[typeof](../keywords/typeof.md) – returns the <xref:System.Type> object representing the operand.</span></span>

<span data-ttu-id="1527a-123">[checked](../keywords/checked.md) – 整数演算のオーバーフロー チェックを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1527a-123">[checked](../keywords/checked.md) – enables overflow checking for integer operations.</span></span>

<span data-ttu-id="1527a-124">[unchecked](../keywords/unchecked.md) – 整数演算のオーバーフロー チェックを無効にします。</span><span class="sxs-lookup"><span data-stu-id="1527a-124">[unchecked](../keywords/unchecked.md) – disables overflow checking for integer operations.</span></span> <span data-ttu-id="1527a-125">これがコンパイラの既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="1527a-125">This is the default compiler behavior.</span></span>

<span data-ttu-id="1527a-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – 型 T の既定の値を生成します。</span><span class="sxs-lookup"><span data-stu-id="1527a-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – produces the default value of type T.</span></span>

<span data-ttu-id="1527a-127">[Delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – delegate インスタンスを宣言して返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-127">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – declares and returns a delegate instance.</span></span>

<span data-ttu-id="1527a-128">[sizeof](../keywords/sizeof.md) – 型オペランドのサイズをバイト単位で返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-128">[sizeof](../keywords/sizeof.md) – returns the size in bytes of the type operand.</span></span>

<span data-ttu-id="1527a-129">[->](dereference-operator.md) – メンバー アクセスと組み合わせてポインターを逆参照します。</span><span class="sxs-lookup"><span data-stu-id="1527a-129">[->](dereference-operator.md) – pointer dereferencing combined with member access.</span></span>

## <a name="unary-operators"></a><span data-ttu-id="1527a-130">単項演算子</span><span class="sxs-lookup"><span data-stu-id="1527a-130">Unary operators</span></span>

<span data-ttu-id="1527a-131">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="1527a-131">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="1527a-132">[+x](addition-operator.md) – x の値を返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-132">[+x](addition-operator.md) – returns the value of x.</span></span>

<span data-ttu-id="1527a-133">[-x](subtraction-operator.md) – 数値の否定。</span><span class="sxs-lookup"><span data-stu-id="1527a-133">[-x](subtraction-operator.md) – numeric negation.</span></span>

<span data-ttu-id="1527a-134">[\!x](boolean-logical-operators.md#logical-negation-operator-) – 論理否定。</span><span class="sxs-lookup"><span data-stu-id="1527a-134">[\!x](boolean-logical-operators.md#logical-negation-operator-) – logical negation.</span></span>

<span data-ttu-id="1527a-135">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-) – ビットごとの補数。</span><span class="sxs-lookup"><span data-stu-id="1527a-135">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-) – bitwise complement.</span></span>

<span data-ttu-id="1527a-136">[++x](arithmetic-operators.md#increment-operator-) – 前置インクリメント。</span><span class="sxs-lookup"><span data-stu-id="1527a-136">[++x](arithmetic-operators.md#increment-operator-) – prefix increment.</span></span> <span data-ttu-id="1527a-137">1 大きくなった (通常は整数 1 が加算された) x の値で格納場所を更新した後に x の値を返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-137">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="1527a-138">[--x](arithmetic-operators.md#decrement-operator---) – 前置デクリメント。</span><span class="sxs-lookup"><span data-stu-id="1527a-138">[--x](arithmetic-operators.md#decrement-operator---) – prefix decrement.</span></span> <span data-ttu-id="1527a-139">1 小さくなった (通常は整数 1 が減算された) x の値で格納場所を更新した後に x の値を返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-139">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="1527a-140">[(T)x](invocation-operator.md) – 型キャスト。</span><span class="sxs-lookup"><span data-stu-id="1527a-140">[(T)x](invocation-operator.md) – type casting.</span></span>

<span data-ttu-id="1527a-141">[await](../keywords/await.md) – `Task` を待機します。</span><span class="sxs-lookup"><span data-stu-id="1527a-141">[await](../keywords/await.md) – awaits a `Task`.</span></span>

<span data-ttu-id="1527a-142">[&x](and-operator.md) – アドレス。</span><span class="sxs-lookup"><span data-stu-id="1527a-142">[&x](and-operator.md) – address of.</span></span>

<span data-ttu-id="1527a-143">[\*x](multiplication-operator.md) – 逆参照。</span><span class="sxs-lookup"><span data-stu-id="1527a-143">[\*x](multiplication-operator.md) – dereferencing.</span></span>

<span data-ttu-id="1527a-144">[true 演算子](../keywords/true-false-operators.md) - オペランドが確実に true であることを示す[ブール](../keywords/bool.md)値 `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-144">[true operator](../keywords/true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely true.</span></span>

<span data-ttu-id="1527a-145">[false 演算子](../keywords/true-false-operators.md) - オペランドが確実に false であることを示す[ブール](../keywords/bool.md)値 `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-145">[false operator](../keywords/true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely false.</span></span>

## <a name="multiplicative-operators"></a><span data-ttu-id="1527a-146">乗算演算子</span><span class="sxs-lookup"><span data-stu-id="1527a-146">Multiplicative operators</span></span>

<span data-ttu-id="1527a-147">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="1527a-147">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="1527a-148">[x \* y](arithmetic-operators.md#multiplication-operator-) – 乗算。</span><span class="sxs-lookup"><span data-stu-id="1527a-148">[x \* y](arithmetic-operators.md#multiplication-operator-) – multiplication.</span></span>

<span data-ttu-id="1527a-149">[x / y](arithmetic-operators.md#division-operator-) – 除算。</span><span class="sxs-lookup"><span data-stu-id="1527a-149">[x / y](arithmetic-operators.md#division-operator-) – division.</span></span> <span data-ttu-id="1527a-150">オペランドが整数の場合、結果は 0 に近い整数になるように切り捨てられます (例: `-7 / 2 is -3`)。</span><span class="sxs-lookup"><span data-stu-id="1527a-150">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>

<span data-ttu-id="1527a-151">[x % y](arithmetic-operators.md#remainder-operator-) – 剰余。</span><span class="sxs-lookup"><span data-stu-id="1527a-151">[x % y](arithmetic-operators.md#remainder-operator-) – remainder.</span></span> <span data-ttu-id="1527a-152">オペランドが整数の場合、x を y で除算した剰余を返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-152">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="1527a-153">`q = x / y` で `r = x % y` の場合、`x = q * y + r` になります。</span><span class="sxs-lookup"><span data-stu-id="1527a-153">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>

## <a name="additive-operators"></a><span data-ttu-id="1527a-154">加法演算子</span><span class="sxs-lookup"><span data-stu-id="1527a-154">Additive operators</span></span>

<span data-ttu-id="1527a-155">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="1527a-155">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="1527a-156">[x + y](arithmetic-operators.md#addition-operator-) – 加算。</span><span class="sxs-lookup"><span data-stu-id="1527a-156">[x + y](arithmetic-operators.md#addition-operator-) – addition.</span></span>

<span data-ttu-id="1527a-157">[x – y](arithmetic-operators.md#subtraction-operator--) – 減算。</span><span class="sxs-lookup"><span data-stu-id="1527a-157">[x – y](arithmetic-operators.md#subtraction-operator--) – subtraction.</span></span>

## <a name="shift-operators"></a><span data-ttu-id="1527a-158">シフト演算子</span><span class="sxs-lookup"><span data-stu-id="1527a-158">Shift operators</span></span>

<span data-ttu-id="1527a-159">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="1527a-159">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="1527a-160">[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-) – ビットを左へシフトし、右側には 0 を格納します。</span><span class="sxs-lookup"><span data-stu-id="1527a-160">[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-) – shift bits left and fill with zero on the right.</span></span>

<span data-ttu-id="1527a-161">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) – ビットを右へシフトします。</span><span class="sxs-lookup"><span data-stu-id="1527a-161">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) – shift bits right.</span></span> <span data-ttu-id="1527a-162">左側のオペランドが `int` または `long` の場合、左側のビットには符号ビットが格納されます。</span><span class="sxs-lookup"><span data-stu-id="1527a-162">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span> <span data-ttu-id="1527a-163">左側のオペランドが `uint` または `ulong` の場合、左側のビットには 0 が格納されます。</span><span class="sxs-lookup"><span data-stu-id="1527a-163">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>

## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="1527a-164">関係演算子と型検査演算子</span><span class="sxs-lookup"><span data-stu-id="1527a-164">Relational and type-testing operators</span></span>

<span data-ttu-id="1527a-165">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="1527a-165">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="1527a-166">[x \< y](less-than-operator.md) – より小さい (x が y より小さい場合は true)。</span><span class="sxs-lookup"><span data-stu-id="1527a-166">[x \< y](less-than-operator.md) – less than (true if x is less than y).</span></span>

<span data-ttu-id="1527a-167">[x > y](greater-than-operator.md) – より大きい (x が y より大きい場合は true)。</span><span class="sxs-lookup"><span data-stu-id="1527a-167">[x > y](greater-than-operator.md) – greater than (true if x is greater than y).</span></span>

<span data-ttu-id="1527a-168">[x \<= y](less-than-equal-operator.md) – 以下。</span><span class="sxs-lookup"><span data-stu-id="1527a-168">[x \<= y](less-than-equal-operator.md) – less than or equal to.</span></span>

<span data-ttu-id="1527a-169">[x >= y](greater-than-equal-operator.md) – 以上。</span><span class="sxs-lookup"><span data-stu-id="1527a-169">[x >= y](greater-than-equal-operator.md) – greater than or equal to.</span></span>

<span data-ttu-id="1527a-170">[is](../keywords/is.md) – 型の互換性。</span><span class="sxs-lookup"><span data-stu-id="1527a-170">[is](../keywords/is.md) – type compatibility.</span></span> <span data-ttu-id="1527a-171">評価される左側のオペランドを右側のオペランドで指定された型 (静的な型) にキャストできる場合は、true を返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-171">Returns true if the evaluated left operand can be cast to the type specified in the right operand (a static type).</span></span>

<span data-ttu-id="1527a-172">[as](../keywords/as.md) – 型変換。</span><span class="sxs-lookup"><span data-stu-id="1527a-172">[as](../keywords/as.md) – type conversion.</span></span> <span data-ttu-id="1527a-173">左側のオペランドを右側のオペランドで指定された型 (静的な型) にキャストして返します。ただし、`(T)x` が例外をスローした場合、`as` は `null` を返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-173">Returns the left operand cast to the type specified by the right operand (a static type), but `as` returns `null` where `(T)x` would throw an exception.</span></span>

## <a name="equality-operators"></a><span data-ttu-id="1527a-174">等値演算子</span><span class="sxs-lookup"><span data-stu-id="1527a-174">Equality operators</span></span>

<span data-ttu-id="1527a-175">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="1527a-175">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="1527a-176">[x == y](equality-operators.md#equality-operator-) – 等価比較。</span><span class="sxs-lookup"><span data-stu-id="1527a-176">[x == y](equality-operators.md#equality-operator-) – equality.</span></span> <span data-ttu-id="1527a-177">既定では、`string` 以外の参照型の場合、参照の等価性を返します (等価テスト)。</span><span class="sxs-lookup"><span data-stu-id="1527a-177">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span> <span data-ttu-id="1527a-178">ただし、型は `==` をオーバーロードできるため、同一性のテストが目的の場合は `object` で `ReferenceEquals` メソッドを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1527a-178">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>

<span data-ttu-id="1527a-179">[x != y](equality-operators.md#inequality-operator-) – 等しくない。</span><span class="sxs-lookup"><span data-stu-id="1527a-179">[x != y](equality-operators.md#inequality-operator-) – not equal.</span></span> <span data-ttu-id="1527a-180">`==` のコメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1527a-180">See comment for `==`.</span></span> <span data-ttu-id="1527a-181">型が `==` をオーバーロードする場合は、`!=` をオーバーロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1527a-181">If a type overloads `==`, then it must overload `!=`.</span></span>

## <a name="logical-and-operator"></a><span data-ttu-id="1527a-182">論理 AND 演算子</span><span class="sxs-lookup"><span data-stu-id="1527a-182">Logical AND operator</span></span>

<span data-ttu-id="1527a-183">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="1527a-183">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="1527a-184">`x & y` – `bool` オペランドの場合は[論理 AND](boolean-logical-operators.md#logical-and-operator-)、整数型のオペランドの場合は[ビットごとの論理 AND](bitwise-and-shift-operators.md#logical-and-operator-)。</span><span class="sxs-lookup"><span data-stu-id="1527a-184">`x & y` – [logical AND](boolean-logical-operators.md#logical-and-operator-) for the `bool` operands or [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) for the operands of the integral types.</span></span>

## <a name="logical-xor-operator"></a><span data-ttu-id="1527a-185">論理 XOR 演算子</span><span class="sxs-lookup"><span data-stu-id="1527a-185">Logical XOR operator</span></span>

<span data-ttu-id="1527a-186">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="1527a-186">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="1527a-187">`x ^ y` – `bool` オペランドの場合は[論理 XOR](boolean-logical-operators.md#logical-exclusive-or-operator-)、整数型のオペランドの場合は[ビットごとの論理 XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-)。</span><span class="sxs-lookup"><span data-stu-id="1527a-187">`x ^ y` – [logical XOR](boolean-logical-operators.md#logical-exclusive-or-operator-) for the `bool` operands or [bitwise logical XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) for the operands of the integral types.</span></span>

## <a name="logical-or-operator"></a><span data-ttu-id="1527a-188">論理演算子 OR</span><span class="sxs-lookup"><span data-stu-id="1527a-188">Logical OR operator</span></span>

<span data-ttu-id="1527a-189">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="1527a-189">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="1527a-190">`x | y` – `bool` オペランドの場合は[論理 OR](boolean-logical-operators.md#logical-or-operator-)、整数型のオペランドの場合は[ビットごとの論理 OR](bitwise-and-shift-operators.md#logical-or-operator-)。</span><span class="sxs-lookup"><span data-stu-id="1527a-190">`x | y` – [logical OR](boolean-logical-operators.md#logical-or-operator-) for the `bool` operands or [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) for the operands of the integral types.</span></span>

## <a name="conditional-and-operator"></a><span data-ttu-id="1527a-191">条件 AND 演算子</span><span class="sxs-lookup"><span data-stu-id="1527a-191">Conditional AND operator</span></span>

<span data-ttu-id="1527a-192">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="1527a-192">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="1527a-193">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) – 論理 AND。</span><span class="sxs-lookup"><span data-stu-id="1527a-193">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) – logical AND.</span></span> <span data-ttu-id="1527a-194">最初のオペランドが false に評価される場合、C# では 2 番目のオペランドが評価されません。</span><span class="sxs-lookup"><span data-stu-id="1527a-194">If the first operand evaluates to false, then C# does not evaluate the second operand.</span></span>

## <a name="conditional-or-operator"></a><span data-ttu-id="1527a-195">条件 OR 演算子</span><span class="sxs-lookup"><span data-stu-id="1527a-195">Conditional OR operator</span></span>

<span data-ttu-id="1527a-196">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="1527a-196">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="1527a-197">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) – 論理 OR。</span><span class="sxs-lookup"><span data-stu-id="1527a-197">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) – logical OR.</span></span> <span data-ttu-id="1527a-198">最初のオペランドが true に評価される場合、C# では 2 番目のオペランドが評価されません。</span><span class="sxs-lookup"><span data-stu-id="1527a-198">If the first operand evaluates to true, then C# does not evaluate the second operand.</span></span>

## <a name="null-coalescing-operator"></a><span data-ttu-id="1527a-199">Null 合体演算子</span><span class="sxs-lookup"><span data-stu-id="1527a-199">Null-coalescing operator</span></span>

<span data-ttu-id="1527a-200">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="1527a-200">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="1527a-201">[x ?? y](null-coalescing-operator.md) – `x` が `null` 以外の場合は x を返します。null の場合は `y` を返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-201">[x ?? y](null-coalescing-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>

## <a name="conditional-operator"></a><span data-ttu-id="1527a-202">条件演算子</span><span class="sxs-lookup"><span data-stu-id="1527a-202">Conditional operator</span></span>

<span data-ttu-id="1527a-203">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="1527a-203">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="1527a-204">[t ? x : y](conditional-operator.md) – テスト `t` が true に評価される場合は `x` を評価して返します。それ以外の場合は `y` を評価して返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-204">[t ? x : y](conditional-operator.md) – if test `t` evaluates to true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>

## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="1527a-205">代入演算子とラムダ演算子</span><span class="sxs-lookup"><span data-stu-id="1527a-205">Assignment and Lambda operators</span></span>

<span data-ttu-id="1527a-206">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="1527a-206">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="1527a-207">[x = y](assignment-operator.md) – 代入。</span><span class="sxs-lookup"><span data-stu-id="1527a-207">[x = y](assignment-operator.md) – assignment.</span></span>

<span data-ttu-id="1527a-208">[x += y](addition-assignment-operator.md) – インクリメント。</span><span class="sxs-lookup"><span data-stu-id="1527a-208">[x += y](addition-assignment-operator.md) – increment.</span></span> <span data-ttu-id="1527a-209">`y` の値を `x` の値に加算した結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-209">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="1527a-210">`x` が `event` を指定した場合、`y` は、C# によってイベント ハンドラーとして追加される適切な関数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1527a-210">If `x` designates an `event`, then `y` must be an appropriate function that C# adds as an event handler.</span></span>

<span data-ttu-id="1527a-211">[x -= y](subtraction-assignment-operator.md) – デクリメント。</span><span class="sxs-lookup"><span data-stu-id="1527a-211">[x -= y](subtraction-assignment-operator.md) – decrement.</span></span> <span data-ttu-id="1527a-212">`y` の値を `x` の値から減算した結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-212">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="1527a-213">`x` で `event` を指定する場合、`y` は C# によってイベント ハンドラーとして削除される適切な関数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1527a-213">If `x` designates an `event`, then `y` must be an appropriate function that C# removes as an event handler.</span></span>

<span data-ttu-id="1527a-214">[x \*= y](arithmetic-operators.md#compound-assignment) – 乗算代入。</span><span class="sxs-lookup"><span data-stu-id="1527a-214">[x \*= y](arithmetic-operators.md#compound-assignment) – multiplication assignment.</span></span> <span data-ttu-id="1527a-215">`y` の値を `x` の値に乗算した結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-215">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="1527a-216">[x /= y](arithmetic-operators.md#compound-assignment) – 除算代入。</span><span class="sxs-lookup"><span data-stu-id="1527a-216">[x /= y](arithmetic-operators.md#compound-assignment) – division assignment.</span></span> <span data-ttu-id="1527a-217">`x` の値を `y` の値で除算した結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-217">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="1527a-218">[x %= y](arithmetic-operators.md#compound-assignment) – 剰余代入。</span><span class="sxs-lookup"><span data-stu-id="1527a-218">[x %= y](arithmetic-operators.md#compound-assignment) – remainder assignment.</span></span> <span data-ttu-id="1527a-219">`x` の値を `y` の値で除算した剰余を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-219">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>

<span data-ttu-id="1527a-220">[x &= y](boolean-logical-operators.md#compound-assignment) – AND 代入。</span><span class="sxs-lookup"><span data-stu-id="1527a-220">[x &= y](boolean-logical-operators.md#compound-assignment) – AND assignment.</span></span> <span data-ttu-id="1527a-221">`y` の値と `x` の値の AND 演算を行った結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-221">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="1527a-222">[x &#124;= y](boolean-logical-operators.md#compound-assignment) – OR 代入。</span><span class="sxs-lookup"><span data-stu-id="1527a-222">[x &#124;= y](boolean-logical-operators.md#compound-assignment) – OR assignment.</span></span> <span data-ttu-id="1527a-223">`y` の値と `x` の値の OR 演算を行った結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-223">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="1527a-224">[x ^= y](boolean-logical-operators.md#compound-assignment) – XOR 代入。</span><span class="sxs-lookup"><span data-stu-id="1527a-224">[x ^= y](boolean-logical-operators.md#compound-assignment) – XOR assignment.</span></span> <span data-ttu-id="1527a-225">`y` の値と `x` の値の XOR 演算を行った結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-225">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="1527a-226">[x <<= y](bitwise-and-shift-operators.md#compound-assignment) – 左シフト代入。</span><span class="sxs-lookup"><span data-stu-id="1527a-226">[x <<= y](bitwise-and-shift-operators.md#compound-assignment) – left-shift assignment.</span></span> <span data-ttu-id="1527a-227">`x` の値を `y` で指定した分だけ左へシフトした結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-227">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="1527a-228">[x >>= y](bitwise-and-shift-operators.md#compound-assignment) – 右シフト代入。</span><span class="sxs-lookup"><span data-stu-id="1527a-228">[x >>= y](bitwise-and-shift-operators.md#compound-assignment) – right-shift assignment.</span></span> <span data-ttu-id="1527a-229">`x` の値を `y` で指定した分だけ右へシフトした結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="1527a-229">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="1527a-230">[=>](lambda-operator.md) – ラムダ宣言。</span><span class="sxs-lookup"><span data-stu-id="1527a-230">[=>](lambda-operator.md) – lambda declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="1527a-231">関連項目</span><span class="sxs-lookup"><span data-stu-id="1527a-231">See also</span></span>

- [<span data-ttu-id="1527a-232">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="1527a-232">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1527a-233">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="1527a-233">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1527a-234">C#</span><span class="sxs-lookup"><span data-stu-id="1527a-234">C#</span></span>](../../index.md)
- [<span data-ttu-id="1527a-235">オーバーロード可能な演算子</span><span class="sxs-lookup"><span data-stu-id="1527a-235">Overloadable operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="1527a-236">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="1527a-236">C# Keywords</span></span>](../keywords/index.md)
