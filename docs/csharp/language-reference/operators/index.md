---
title: 'C# 演算子'
ms.date: 04/04/2018
f1_keywords:
  - cs.operators
helpviewer_keywords:
  - 'boolean operators [C#]'
  - 'expressions [C#], operators'
  - 'logical operators [C#]'
  - 'operators [C#]'
  - 'Visual C#, operators'
  - 'indirection operators [C#]'
  - 'assignment operators [C#]'
  - 'shift operators [C#]'
  - 'relational operators [C#]'
  - 'bitwise operators [C#]'
  - 'address operators [C#]'
  - 'keywords [C#], operators'
  - 'arithmetic operators [C#]'
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
---
# <a name="c-operators"></a><span data-ttu-id="39259-102">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="39259-102">C# operators</span></span>

<span data-ttu-id="39259-103">C# には、多くの演算子が用意されています。演算子とは、式で実行する演算 (数値演算、インデックス作成、関数呼び出しなど) を指定する記号のことです。</span><span class="sxs-lookup"><span data-stu-id="39259-103">C# provides many operators, which are symbols that specify which operations (math, indexing, function call, etc.) to perform in an expression.</span></span> <span data-ttu-id="39259-104">多くの演算子は、ユーザー定義型に適用する際に[オーバーロード](../../programming-guide/statements-expressions-operators/overloadable-operators.md)して、その意味を変更できます。</span><span class="sxs-lookup"><span data-stu-id="39259-104">You can [overload](../../programming-guide/statements-expressions-operators/overloadable-operators.md) many operators to change their meaning when applied to a user-defined type.</span></span>

<span data-ttu-id="39259-105">整数型に対する演算 (`==`、`!=`、`<`、`>`、`&`、`|`) は、通常、列挙型 (`enum`) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="39259-105">Operations on integral types (such as `==`, `!=`, `<`, `>`, `&`, `|`) are generally allowed on enumeration (`enum`) types.</span></span>

<span data-ttu-id="39259-106">ここでは、C# の演算子を優先順位の高い順に示します。</span><span class="sxs-lookup"><span data-stu-id="39259-106">The sections below list the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="39259-107">各セクションの演算子の優先順位は同じです。</span><span class="sxs-lookup"><span data-stu-id="39259-107">The operators within each section share the same precedence level.</span></span>

## <a name="primary-operators"></a><span data-ttu-id="39259-108">主な演算子</span><span class="sxs-lookup"><span data-stu-id="39259-108">Primary operators</span></span>

<span data-ttu-id="39259-109">優先順位が最も高い演算子です。</span><span class="sxs-lookup"><span data-stu-id="39259-109">These are the highest precedence operators.</span></span>

<span data-ttu-id="39259-110">[x.y](member-access-operator.md) – メンバー アクセス。</span><span class="sxs-lookup"><span data-stu-id="39259-110">[x.y](member-access-operator.md) – member access.</span></span>

<span data-ttu-id="39259-111">[x?.y](null-conditional-operators.md) – null 条件付きのメンバー アクセス。</span><span class="sxs-lookup"><span data-stu-id="39259-111">[x?.y](null-conditional-operators.md) – null conditional member access.</span></span> <span data-ttu-id="39259-112">左側のオペランドが `null` に評価される場合に `null` を返します。</span><span class="sxs-lookup"><span data-stu-id="39259-112">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="39259-113">[x?[y]](null-conditional-operators.md) - null 条件付きのインデックス アクセス。</span><span class="sxs-lookup"><span data-stu-id="39259-113">[x?[y]](null-conditional-operators.md) - null conditional index access.</span></span> <span data-ttu-id="39259-114">左側のオペランドが `null` に評価される場合に `null` を返します。</span><span class="sxs-lookup"><span data-stu-id="39259-114">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="39259-115">[f(x)](invocation-operator.md) – 関数の呼び出し。</span><span class="sxs-lookup"><span data-stu-id="39259-115">[f(x)](invocation-operator.md) – function invocation.</span></span>

<span data-ttu-id="39259-116">[a&#91;x&#93;](index-operator.md) – 集約オブジェクトのインデックス作成。</span><span class="sxs-lookup"><span data-stu-id="39259-116">[a&#91;x&#93;](index-operator.md) – aggregate object indexing.</span></span>

<span data-ttu-id="39259-117">[x++](arithmetic-operators.md#increment-operator-) – 後置インクリメント。</span><span class="sxs-lookup"><span data-stu-id="39259-117">[x++](arithmetic-operators.md#increment-operator-) – postfix increment.</span></span> <span data-ttu-id="39259-118">x の値を返した後、1 大きくなった (通常は整数 1 が加算された) x の値で格納場所を更新します。</span><span class="sxs-lookup"><span data-stu-id="39259-118">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="39259-119">[x--](arithmetic-operators.md#decrement-operator---) – 後置デクリメント。</span><span class="sxs-lookup"><span data-stu-id="39259-119">[x--](arithmetic-operators.md#decrement-operator---) –  postfix decrement.</span></span> <span data-ttu-id="39259-120">x の値を返した後、1 小さくなった (通常は整数 1 が減算された) x の値で格納場所を更新します。</span><span class="sxs-lookup"><span data-stu-id="39259-120">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="39259-121">[new](../keywords/new-operator.md) – 型のインスタンス化。</span><span class="sxs-lookup"><span data-stu-id="39259-121">[new](../keywords/new-operator.md) – type instantiation.</span></span>

<span data-ttu-id="39259-122">[typeof](../keywords/typeof.md) – オペランドを表す <xref:System.Type> オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="39259-122">[typeof](../keywords/typeof.md) – returns the <xref:System.Type> object representing the operand.</span></span>

<span data-ttu-id="39259-123">[checked](../keywords/checked.md) – 整数演算のオーバーフロー チェックを有効にします。</span><span class="sxs-lookup"><span data-stu-id="39259-123">[checked](../keywords/checked.md) – enables overflow checking for integer operations.</span></span>

<span data-ttu-id="39259-124">[unchecked](../keywords/unchecked.md) – 整数演算のオーバーフロー チェックを無効にします。</span><span class="sxs-lookup"><span data-stu-id="39259-124">[unchecked](../keywords/unchecked.md) – disables overflow checking for integer operations.</span></span> <span data-ttu-id="39259-125">これがコンパイラの既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="39259-125">This is the default compiler behavior.</span></span>

<span data-ttu-id="39259-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – 型 T の既定の値を生成します。</span><span class="sxs-lookup"><span data-stu-id="39259-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – produces the default value of type T.</span></span>

<span data-ttu-id="39259-127">[Delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – delegate インスタンスを宣言して返します。</span><span class="sxs-lookup"><span data-stu-id="39259-127">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – declares and returns a delegate instance.</span></span>

<span data-ttu-id="39259-128">[sizeof](../keywords/sizeof.md) – 型オペランドのサイズをバイト単位で返します。</span><span class="sxs-lookup"><span data-stu-id="39259-128">[sizeof](../keywords/sizeof.md) – returns the size in bytes of the type operand.</span></span>

<span data-ttu-id="39259-129">[->](dereference-operator.md) – メンバー アクセスと組み合わせてポインターを逆参照します。</span><span class="sxs-lookup"><span data-stu-id="39259-129">[->](dereference-operator.md) – pointer dereferencing combined with member access.</span></span>

## <a name="unary-operators"></a><span data-ttu-id="39259-130">単項演算子</span><span class="sxs-lookup"><span data-stu-id="39259-130">Unary operators</span></span>

<span data-ttu-id="39259-131">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="39259-131">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="39259-132">[+x](addition-operator.md) – x の値を返します。</span><span class="sxs-lookup"><span data-stu-id="39259-132">[+x](addition-operator.md) – returns the value of x.</span></span>

<span data-ttu-id="39259-133">[-x](subtraction-operator.md) – 数値の否定。</span><span class="sxs-lookup"><span data-stu-id="39259-133">[-x](subtraction-operator.md) – numeric negation.</span></span>

<span data-ttu-id="39259-134">[\!x](logical-negation-operator.md) – 論理否定。</span><span class="sxs-lookup"><span data-stu-id="39259-134">[\!x](logical-negation-operator.md) – logical negation.</span></span>

<span data-ttu-id="39259-135">[~x](bitwise-complement-operator.md) – ビットごとの補数。</span><span class="sxs-lookup"><span data-stu-id="39259-135">[~x](bitwise-complement-operator.md) – bitwise complement.</span></span>

<span data-ttu-id="39259-136">[++x](arithmetic-operators.md#increment-operator-) – 前置インクリメント。</span><span class="sxs-lookup"><span data-stu-id="39259-136">[++x](arithmetic-operators.md#increment-operator-) – prefix increment.</span></span> <span data-ttu-id="39259-137">1 大きくなった (通常は整数 1 が加算された) x の値で格納場所を更新した後に x の値を返します。</span><span class="sxs-lookup"><span data-stu-id="39259-137">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="39259-138">[--x](arithmetic-operators.md#decrement-operator---) – 前置デクリメント。</span><span class="sxs-lookup"><span data-stu-id="39259-138">[--x](arithmetic-operators.md#decrement-operator---) – prefix decrement.</span></span> <span data-ttu-id="39259-139">1 小さくなった (通常は整数 1 が減算された) x の値で格納場所を更新した後に x の値を返します。</span><span class="sxs-lookup"><span data-stu-id="39259-139">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="39259-140">[(T)x](invocation-operator.md) – 型キャスト。</span><span class="sxs-lookup"><span data-stu-id="39259-140">[(T)x](invocation-operator.md) – type casting.</span></span>

<span data-ttu-id="39259-141">[await](../keywords/await.md) – `Task` を待機します。</span><span class="sxs-lookup"><span data-stu-id="39259-141">[await](../keywords/await.md) – awaits a `Task`.</span></span>

<span data-ttu-id="39259-142">[&x](and-operator.md) – アドレス。</span><span class="sxs-lookup"><span data-stu-id="39259-142">[&x](and-operator.md) – address of.</span></span>

<span data-ttu-id="39259-143">[\*x](multiplication-operator.md) – 逆参照。</span><span class="sxs-lookup"><span data-stu-id="39259-143">[\*x](multiplication-operator.md) – dereferencing.</span></span>

## <a name="multiplicative-operators"></a><span data-ttu-id="39259-144">乗算演算子</span><span class="sxs-lookup"><span data-stu-id="39259-144">Multiplicative operators</span></span>

<span data-ttu-id="39259-145">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="39259-145">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="39259-146">[x \* y](arithmetic-operators.md#multiplication-operator-) – 乗算。</span><span class="sxs-lookup"><span data-stu-id="39259-146">[x \* y](arithmetic-operators.md#multiplication-operator-) – multiplication.</span></span>

<span data-ttu-id="39259-147">[x / y](arithmetic-operators.md#division-operator-) – 除算。</span><span class="sxs-lookup"><span data-stu-id="39259-147">[x / y](arithmetic-operators.md#division-operator-) – division.</span></span> <span data-ttu-id="39259-148">オペランドが整数の場合、結果は 0 に近い整数になるように切り捨てられます (例: `-7 / 2 is -3`)。</span><span class="sxs-lookup"><span data-stu-id="39259-148">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>

<span data-ttu-id="39259-149">[x % y](arithmetic-operators.md#remainder-operator-) – 剰余。</span><span class="sxs-lookup"><span data-stu-id="39259-149">[x % y](arithmetic-operators.md#remainder-operator-) – remainder.</span></span> <span data-ttu-id="39259-150">オペランドが整数の場合、x を y で除算した剰余を返します。</span><span class="sxs-lookup"><span data-stu-id="39259-150">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="39259-151">`q = x / y` で `r = x % y` の場合、`x = q * y + r` になります。</span><span class="sxs-lookup"><span data-stu-id="39259-151">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>

## <a name="additive-operators"></a><span data-ttu-id="39259-152">加法演算子</span><span class="sxs-lookup"><span data-stu-id="39259-152">Additive operators</span></span>

<span data-ttu-id="39259-153">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="39259-153">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="39259-154">[x + y](arithmetic-operators.md#addition-operator-) – 加算。</span><span class="sxs-lookup"><span data-stu-id="39259-154">[x + y](arithmetic-operators.md#addition-operator-) – addition.</span></span>

<span data-ttu-id="39259-155">[x – y](arithmetic-operators.md#subtraction-operator--) – 減算。</span><span class="sxs-lookup"><span data-stu-id="39259-155">[x – y](arithmetic-operators.md#subtraction-operator--) – subtraction.</span></span>

## <a name="shift-operators"></a><span data-ttu-id="39259-156">シフト演算子</span><span class="sxs-lookup"><span data-stu-id="39259-156">Shift operators</span></span>

<span data-ttu-id="39259-157">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="39259-157">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="39259-158">[x <\<  y](left-shift-operator.md) – ビットを左へシフトし、右側には 0 を格納します。</span><span class="sxs-lookup"><span data-stu-id="39259-158">[x <\<  y](left-shift-operator.md) – shift bits left and fill with zero on the right.</span></span>

<span data-ttu-id="39259-159">[x >> y](right-shift-operator.md) – ビットを右へシフトします。</span><span class="sxs-lookup"><span data-stu-id="39259-159">[x >> y](right-shift-operator.md) – shift bits right.</span></span> <span data-ttu-id="39259-160">左側のオペランドが `int` または `long` の場合、左側のビットには符号ビットが格納されます。</span><span class="sxs-lookup"><span data-stu-id="39259-160">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span> <span data-ttu-id="39259-161">左側のオペランドが `uint` または `ulong` の場合、左側のビットには 0 が格納されます。</span><span class="sxs-lookup"><span data-stu-id="39259-161">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>

## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="39259-162">関係演算子と型検査演算子</span><span class="sxs-lookup"><span data-stu-id="39259-162">Relational and type-testing operators</span></span>

<span data-ttu-id="39259-163">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="39259-163">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="39259-164">[x \< y](less-than-operator.md) – より小さい (x が y より小さい場合は true)。</span><span class="sxs-lookup"><span data-stu-id="39259-164">[x \< y](less-than-operator.md) – less than (true if x is less than y).</span></span>

<span data-ttu-id="39259-165">[x > y](greater-than-operator.md) – より大きい (x が y より大きい場合は true)。</span><span class="sxs-lookup"><span data-stu-id="39259-165">[x > y](greater-than-operator.md) – greater than (true if x is greater than y).</span></span>

<span data-ttu-id="39259-166">[x \<= y](less-than-equal-operator.md) – 以下。</span><span class="sxs-lookup"><span data-stu-id="39259-166">[x \<= y](less-than-equal-operator.md) – less than or equal to.</span></span>

<span data-ttu-id="39259-167">[x >= y](greater-than-equal-operator.md) – 以上。</span><span class="sxs-lookup"><span data-stu-id="39259-167">[x >= y](greater-than-equal-operator.md) – greater than or equal to.</span></span>

<span data-ttu-id="39259-168">[is](../keywords/is.md) – 型の互換性。</span><span class="sxs-lookup"><span data-stu-id="39259-168">[is](../keywords/is.md) – type compatibility.</span></span> <span data-ttu-id="39259-169">評価される左側のオペランドを右側のオペランドで指定された型 (静的な型) にキャストできる場合は、true を返します。</span><span class="sxs-lookup"><span data-stu-id="39259-169">Returns true if the evaluated left operand can be cast to the type specified in the right operand (a static type).</span></span>

<span data-ttu-id="39259-170">[as](../keywords/as.md) – 型変換。</span><span class="sxs-lookup"><span data-stu-id="39259-170">[as](../keywords/as.md) – type conversion.</span></span> <span data-ttu-id="39259-171">左側のオペランドを右側のオペランドで指定された型 (静的な型) にキャストして返します。ただし、`(T)x` が例外をスローした場合、`as` は `null` を返します。</span><span class="sxs-lookup"><span data-stu-id="39259-171">Returns the left operand cast to the type specified by the right operand (a static type), but `as` returns `null` where `(T)x` would throw an exception.</span></span>

## <a name="equality-operators"></a><span data-ttu-id="39259-172">等値演算子</span><span class="sxs-lookup"><span data-stu-id="39259-172">Equality operators</span></span>

<span data-ttu-id="39259-173">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="39259-173">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="39259-174">[x == y](equality-operators.md#equality-operator-) – 等価比較。</span><span class="sxs-lookup"><span data-stu-id="39259-174">[x == y](equality-operators.md#equality-operator-) – equality.</span></span> <span data-ttu-id="39259-175">既定では、`string` 以外の参照型の場合、参照の等価性を返します (等価テスト)。</span><span class="sxs-lookup"><span data-stu-id="39259-175">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span> <span data-ttu-id="39259-176">ただし、型は `==` をオーバーロードできるため、同一性のテストが目的の場合は `object` で `ReferenceEquals` メソッドを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="39259-176">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>

<span data-ttu-id="39259-177">[x != y](equality-operators.md#inequality-operator-) – 等しくない。</span><span class="sxs-lookup"><span data-stu-id="39259-177">[x != y](equality-operators.md#inequality-operator-) – not equal.</span></span> <span data-ttu-id="39259-178">`==` のコメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="39259-178">See comment for `==`.</span></span> <span data-ttu-id="39259-179">型が `==` をオーバーロードする場合は、`!=` をオーバーロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="39259-179">If a type overloads `==`, then it must overload `!=`.</span></span>

## <a name="logical-and-operator"></a><span data-ttu-id="39259-180">論理 AND 演算子</span><span class="sxs-lookup"><span data-stu-id="39259-180">Logical AND operator</span></span>

<span data-ttu-id="39259-181">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="39259-181">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="39259-182">[x & y](and-operator.md) – 論理またはビットごとの AND。</span><span class="sxs-lookup"><span data-stu-id="39259-182">[x & y](and-operator.md) – logical or bitwise AND.</span></span> <span data-ttu-id="39259-183">通常、整数型と `enum` 型で使用できます。</span><span class="sxs-lookup"><span data-stu-id="39259-183">You can generally use this with integer types and `enum` types.</span></span>

## <a name="logical-xor-operator"></a><span data-ttu-id="39259-184">論理 XOR 演算子</span><span class="sxs-lookup"><span data-stu-id="39259-184">Logical XOR operator</span></span>

<span data-ttu-id="39259-185">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="39259-185">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="39259-186">[x ^ y](xor-operator.md) – 論理またはビットごとの XOR。</span><span class="sxs-lookup"><span data-stu-id="39259-186">[x ^ y](xor-operator.md) – logical or bitwise XOR.</span></span> <span data-ttu-id="39259-187">通常、整数型と `enum` 型で使用できます。</span><span class="sxs-lookup"><span data-stu-id="39259-187">You can generally use this with integer types and `enum` types.</span></span>

## <a name="logical-or-operator"></a><span data-ttu-id="39259-188">論理演算子 OR</span><span class="sxs-lookup"><span data-stu-id="39259-188">Logical OR operator</span></span>

<span data-ttu-id="39259-189">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="39259-189">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="39259-190">[x &#124; y](or-operator.md) – 論理またはビットごとの OR。</span><span class="sxs-lookup"><span data-stu-id="39259-190">[x &#124; y](or-operator.md) – logical or bitwise OR.</span></span> <span data-ttu-id="39259-191">通常、整数型と `enum` 型で使用できます。</span><span class="sxs-lookup"><span data-stu-id="39259-191">You can generally use this with integer types and `enum` types.</span></span>

## <a name="conditional-and-operator"></a><span data-ttu-id="39259-192">条件 AND 演算子</span><span class="sxs-lookup"><span data-stu-id="39259-192">Conditional AND operator</span></span>

<span data-ttu-id="39259-193">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="39259-193">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="39259-194">[x && y](conditional-and-operator.md) – 論理 AND。</span><span class="sxs-lookup"><span data-stu-id="39259-194">[x && y](conditional-and-operator.md) – logical AND.</span></span> <span data-ttu-id="39259-195">最初のオペランドが false に評価される場合、C# では 2 番目のオペランドが評価されません。</span><span class="sxs-lookup"><span data-stu-id="39259-195">If the first operand evaluates to false, then C# does not evaluate the second operand.</span></span>

## <a name="conditional-or-operator"></a><span data-ttu-id="39259-196">条件 OR 演算子</span><span class="sxs-lookup"><span data-stu-id="39259-196">Conditional OR operator</span></span>

<span data-ttu-id="39259-197">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="39259-197">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="39259-198">[x &#124;&#124; y](conditional-or-operator.md) – 論理 OR。</span><span class="sxs-lookup"><span data-stu-id="39259-198">[x &#124;&#124; y](conditional-or-operator.md) – logical OR.</span></span> <span data-ttu-id="39259-199">最初のオペランドが true に評価される場合、C# では 2 番目のオペランドが評価されません。</span><span class="sxs-lookup"><span data-stu-id="39259-199">If the first operand evaluates to true, then C# does not evaluate the second operand.</span></span>

## <a name="null-coalescing-operator"></a><span data-ttu-id="39259-200">Null 合体演算子</span><span class="sxs-lookup"><span data-stu-id="39259-200">Null-coalescing operator</span></span>

<span data-ttu-id="39259-201">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="39259-201">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="39259-202">[x ?? y](null-coalescing-operator.md) – `x` が `null` 以外の場合は x を返します。null の場合は `y` を返します。</span><span class="sxs-lookup"><span data-stu-id="39259-202">[x ?? y](null-coalescing-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>

## <a name="conditional-operator"></a><span data-ttu-id="39259-203">条件演算子</span><span class="sxs-lookup"><span data-stu-id="39259-203">Conditional operator</span></span>

<span data-ttu-id="39259-204">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="39259-204">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="39259-205">[t ? x : y](conditional-operator.md) – テスト `t` が true に評価される場合は `x` を評価して返します。それ以外の場合は `y` を評価して返します。</span><span class="sxs-lookup"><span data-stu-id="39259-205">[t ? x : y](conditional-operator.md) – if test `t` evaluates to true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>

## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="39259-206">代入演算子とラムダ演算子</span><span class="sxs-lookup"><span data-stu-id="39259-206">Assignment and Lambda operators</span></span>

<span data-ttu-id="39259-207">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="39259-207">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="39259-208">[x = y](assignment-operator.md) – 代入。</span><span class="sxs-lookup"><span data-stu-id="39259-208">[x = y](assignment-operator.md) – assignment.</span></span>

<span data-ttu-id="39259-209">[x += y](addition-assignment-operator.md) – インクリメント。</span><span class="sxs-lookup"><span data-stu-id="39259-209">[x += y](addition-assignment-operator.md) – increment.</span></span> <span data-ttu-id="39259-210">`y` の値を `x` の値に加算した結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="39259-210">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="39259-211">`x` が `event` を指定した場合、`y` は、C# によってイベント ハンドラーとして追加される適切な関数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="39259-211">If `x` designates an `event`, then `y` must be an appropriate function that C# adds as an event handler.</span></span>

<span data-ttu-id="39259-212">[x -= y](subtraction-assignment-operator.md) – デクリメント。</span><span class="sxs-lookup"><span data-stu-id="39259-212">[x -= y](subtraction-assignment-operator.md) – decrement.</span></span> <span data-ttu-id="39259-213">`y` の値を `x` の値から減算した結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="39259-213">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="39259-214">`x` が `event` を指定した場合、`y` は、C# によってイベント ハンドラーとして削除される適切な関数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="39259-214">If `x` designates an `event`, then `y` must be an appropriate function that C# removes as an event handler</span></span>

<span data-ttu-id="39259-215">[x \*= y](multiplication-assignment-operator.md) – 乗算代入。</span><span class="sxs-lookup"><span data-stu-id="39259-215">[x \*= y](multiplication-assignment-operator.md) – multiplication assignment.</span></span> <span data-ttu-id="39259-216">`y` の値を `x` の値に乗算した結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="39259-216">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="39259-217">[x /= y](arithmetic-operators.md#compound-assignment) – 除算代入。</span><span class="sxs-lookup"><span data-stu-id="39259-217">[x /= y](arithmetic-operators.md#compound-assignment) – division assignment.</span></span> <span data-ttu-id="39259-218">`x` の値を `y` の値で除算した結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="39259-218">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="39259-219">[x %= y](arithmetic-operators.md#compound-assignment) – 剰余代入。</span><span class="sxs-lookup"><span data-stu-id="39259-219">[x %= y](arithmetic-operators.md#compound-assignment) – remainder assignment.</span></span> <span data-ttu-id="39259-220">`x` の値を `y` の値で除算した剰余を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="39259-220">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>

<span data-ttu-id="39259-221">[x &= y](and-assignment-operator.md) – AND 代入。</span><span class="sxs-lookup"><span data-stu-id="39259-221">[x &= y](and-assignment-operator.md) – AND assignment.</span></span> <span data-ttu-id="39259-222">`y` の値と `x` の値の AND 演算を行った結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="39259-222">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="39259-223">[x &#124;= y](or-assignment-operator.md) – OR 代入。</span><span class="sxs-lookup"><span data-stu-id="39259-223">[x &#124;= y](or-assignment-operator.md) – OR assignment.</span></span> <span data-ttu-id="39259-224">`y` の値と `x` の値の OR 演算を行った結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="39259-224">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="39259-225">[x ^= y](xor-assignment-operator.md) – XOR 代入。</span><span class="sxs-lookup"><span data-stu-id="39259-225">[x ^= y](xor-assignment-operator.md) – XOR assignment.</span></span> <span data-ttu-id="39259-226">`y` の値と `x` の値の XOR 演算を行った結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="39259-226">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="39259-227">[x <<= y](left-shift-assignment-operator.md) – 左シフト代入。</span><span class="sxs-lookup"><span data-stu-id="39259-227">[x <<= y](left-shift-assignment-operator.md) – left-shift assignment.</span></span> <span data-ttu-id="39259-228">`x` の値を `y` で指定した分だけ左へシフトした結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="39259-228">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="39259-229">[x >>= y](right-shift-assignment-operator.md) – 右シフト代入。</span><span class="sxs-lookup"><span data-stu-id="39259-229">[x >>= y](right-shift-assignment-operator.md) – right-shift assignment.</span></span> <span data-ttu-id="39259-230">`x` の値を `y` で指定した分だけ右へシフトした結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="39259-230">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="39259-231">[=>](lambda-operator.md) – ラムダ宣言。</span><span class="sxs-lookup"><span data-stu-id="39259-231">[=>](lambda-operator.md) – lambda declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="39259-232">関連項目</span><span class="sxs-lookup"><span data-stu-id="39259-232">See also</span></span>

- [<span data-ttu-id="39259-233">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="39259-233">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="39259-234">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="39259-234">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="39259-235">C#</span><span class="sxs-lookup"><span data-stu-id="39259-235">C#</span></span>](../../index.md)
- [<span data-ttu-id="39259-236">オーバーロードされた演算子</span><span class="sxs-lookup"><span data-stu-id="39259-236">Overloadable Operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="39259-237">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="39259-237">C# Keywords</span></span>](../keywords/index.md)