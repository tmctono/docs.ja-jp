---
title: C# 演算子
ms.date: 04/30/2019
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
ms.openlocfilehash: c1f891314a2490d6dbf22977ea5a5f69533b330d
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300322"
---
# <a name="c-operators"></a><span data-ttu-id="451a1-102">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="451a1-102">C# operators</span></span>

<span data-ttu-id="451a1-103">C# は組み込み型でサポートされている定義済みの演算子を多数提供します。</span><span class="sxs-lookup"><span data-stu-id="451a1-103">C# provides a number of predefined operators supported by the built-in types.</span></span> <span data-ttu-id="451a1-104">たとえば、[算術演算子](arithmetic-operators.md)は組み込み数値型のオペランドの算術演算を実行し、[ブール論理演算子](boolean-logical-operators.md)は [bool](../keywords/bool.md) オペランドの論理演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="451a1-104">For example, [arithmetic operators](arithmetic-operators.md) perform arithmetic operations with operands of built-in numeric types and [Boolean logical operators](boolean-logical-operators.md) perform logical operations with the [bool](../keywords/bool.md) operands.</span></span>

<span data-ttu-id="451a1-105">ユーザー定義型は、その型のオペランドに対応する動作を定義する特定の演算子をオーバーロードできます。</span><span class="sxs-lookup"><span data-stu-id="451a1-105">A user-defined type can overload certain operators to define the corresponding behavior for the operands of that type.</span></span> <span data-ttu-id="451a1-106">詳細については、[operator](../keywords/operator.md) キーワードの記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="451a1-106">For more information, see the [operator](../keywords/operator.md) keyword article.</span></span>

<span data-ttu-id="451a1-107">次のセクションは、C# の演算子を優先順位の高い順に示しています。</span><span class="sxs-lookup"><span data-stu-id="451a1-107">The following sections list the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="451a1-108">各セクションの演算子の優先順位は同じです。</span><span class="sxs-lookup"><span data-stu-id="451a1-108">The operators within each section share the same precedence level.</span></span>

## <a name="primary-operators"></a><span data-ttu-id="451a1-109">主な演算子</span><span class="sxs-lookup"><span data-stu-id="451a1-109">Primary operators</span></span>

<span data-ttu-id="451a1-110">優先順位が最も高い演算子です。</span><span class="sxs-lookup"><span data-stu-id="451a1-110">These are the highest precedence operators.</span></span>

<span data-ttu-id="451a1-111">[x.y](member-access-operators.md#member-access-operator-) – メンバー アクセス。</span><span class="sxs-lookup"><span data-stu-id="451a1-111">[x.y](member-access-operators.md#member-access-operator-) – member access.</span></span>

<span data-ttu-id="451a1-112">[x?.y](member-access-operators.md#null-conditional-operators--and-) – null 条件付きのメンバー アクセス。</span><span class="sxs-lookup"><span data-stu-id="451a1-112">[x?.y](member-access-operators.md#null-conditional-operators--and-) – null conditional member access.</span></span> <span data-ttu-id="451a1-113">左側のオペランドが `null` に評価される場合に `null` を返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-113">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="451a1-114">[x?[y]](member-access-operators.md#null-conditional-operators--and-) - null 条件付き配列要素または型インデクサーのアクセス。</span><span class="sxs-lookup"><span data-stu-id="451a1-114">[x?[y]](member-access-operators.md#null-conditional-operators--and-) - null conditional array element or type indexer access.</span></span> <span data-ttu-id="451a1-115">左側のオペランドが `null` に評価される場合に `null` を返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-115">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="451a1-116">[f(x)](member-access-operators.md#invocation-operator-) – メソッドの呼び出しまたはデリゲートの呼び出し。</span><span class="sxs-lookup"><span data-stu-id="451a1-116">[f(x)](member-access-operators.md#invocation-operator-) – method call or delegate invocation.</span></span>

<span data-ttu-id="451a1-117">[a&#91;x&#93;](member-access-operators.md#indexer-operator-) – 配列要素または型インデクサーのアクセス。</span><span class="sxs-lookup"><span data-stu-id="451a1-117">[a&#91;x&#93;](member-access-operators.md#indexer-operator-) – array element or type indexer access.</span></span>

<span data-ttu-id="451a1-118">[x++](arithmetic-operators.md#increment-operator-) – 後置インクリメント。</span><span class="sxs-lookup"><span data-stu-id="451a1-118">[x++](arithmetic-operators.md#increment-operator-) – postfix increment.</span></span> <span data-ttu-id="451a1-119">x の値を返した後、1 大きくなった (通常は整数 1 が加算された) x の値で格納場所を更新します。</span><span class="sxs-lookup"><span data-stu-id="451a1-119">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="451a1-120">[x--](arithmetic-operators.md#decrement-operator---) – 後置デクリメント。</span><span class="sxs-lookup"><span data-stu-id="451a1-120">[x--](arithmetic-operators.md#decrement-operator---) –  postfix decrement.</span></span> <span data-ttu-id="451a1-121">x の値を返した後、1 小さくなった (通常は整数 1 が減算された) x の値で格納場所を更新します。</span><span class="sxs-lookup"><span data-stu-id="451a1-121">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="451a1-122">[new](../keywords/new-operator.md) – 型のインスタンス化。</span><span class="sxs-lookup"><span data-stu-id="451a1-122">[new](../keywords/new-operator.md) – type instantiation.</span></span>

<span data-ttu-id="451a1-123">[typeof](../keywords/typeof.md) – オペランドを表す <xref:System.Type> オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-123">[typeof](../keywords/typeof.md) – returns the <xref:System.Type> object representing the operand.</span></span>

<span data-ttu-id="451a1-124">[checked](../keywords/checked.md) – 整数演算のオーバーフロー チェックを有効にします。</span><span class="sxs-lookup"><span data-stu-id="451a1-124">[checked](../keywords/checked.md) – enables overflow checking for integer operations.</span></span>

<span data-ttu-id="451a1-125">[unchecked](../keywords/unchecked.md) – 整数演算のオーバーフロー チェックを無効にします。</span><span class="sxs-lookup"><span data-stu-id="451a1-125">[unchecked](../keywords/unchecked.md) – disables overflow checking for integer operations.</span></span> <span data-ttu-id="451a1-126">これがコンパイラの既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="451a1-126">This is the default compiler behavior.</span></span>

<span data-ttu-id="451a1-127">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – 型 T の既定の値を生成します。</span><span class="sxs-lookup"><span data-stu-id="451a1-127">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – produces the default value of type T.</span></span>

<span data-ttu-id="451a1-128">[nameof](../keywords/nameof.md) – 変数、型、またはメンバーの単純な (修飾されていない) 名前を定数文字列として取得します。</span><span class="sxs-lookup"><span data-stu-id="451a1-128">[nameof](../keywords/nameof.md) - obtains the simple (unqualified) name of a variable, type, or member as a constant string.</span></span>

<span data-ttu-id="451a1-129">[Delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – delegate インスタンスを宣言して返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-129">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – declares and returns a delegate instance.</span></span>

<span data-ttu-id="451a1-130">[sizeof](../keywords/sizeof.md) – 型オペランドのサイズをバイト単位で返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-130">[sizeof](../keywords/sizeof.md) – returns the size in bytes of the type operand.</span></span>

<span data-ttu-id="451a1-131">[stackalloc](../keywords/stackalloc.md) – スタックにメモリ ブロックを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="451a1-131">[stackalloc](../keywords/stackalloc.md) - allocates a block of memory on the stack.</span></span>

<span data-ttu-id="451a1-132">[->](pointer-related-operators.md#pointer-member-access-operator--) – メンバー アクセスと組み合わせてポインターを間接参照します。</span><span class="sxs-lookup"><span data-stu-id="451a1-132">[->](pointer-related-operators.md#pointer-member-access-operator--) – pointer indirection combined with member access.</span></span>

## <a name="unary-operators"></a><span data-ttu-id="451a1-133">単項演算子</span><span class="sxs-lookup"><span data-stu-id="451a1-133">Unary operators</span></span>

<span data-ttu-id="451a1-134">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="451a1-134">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="451a1-135">[+x](addition-operator.md) – x の値を返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-135">[+x](addition-operator.md) – returns the value of x.</span></span>

<span data-ttu-id="451a1-136">[-x](subtraction-operator.md) – 数値の否定。</span><span class="sxs-lookup"><span data-stu-id="451a1-136">[-x](subtraction-operator.md) – numeric negation.</span></span>

<span data-ttu-id="451a1-137">[\!x](boolean-logical-operators.md#logical-negation-operator-) – 論理否定。</span><span class="sxs-lookup"><span data-stu-id="451a1-137">[\!x](boolean-logical-operators.md#logical-negation-operator-) – logical negation.</span></span>

<span data-ttu-id="451a1-138">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-) – ビットごとの補数。</span><span class="sxs-lookup"><span data-stu-id="451a1-138">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-) – bitwise complement.</span></span>

<span data-ttu-id="451a1-139">[++x](arithmetic-operators.md#increment-operator-) – 前置インクリメント。</span><span class="sxs-lookup"><span data-stu-id="451a1-139">[++x](arithmetic-operators.md#increment-operator-) – prefix increment.</span></span> <span data-ttu-id="451a1-140">1 大きくなった (通常は整数 1 が加算された) x の値で格納場所を更新した後に x の値を返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-140">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="451a1-141">[--x](arithmetic-operators.md#decrement-operator---) – 前置デクリメント。</span><span class="sxs-lookup"><span data-stu-id="451a1-141">[--x](arithmetic-operators.md#decrement-operator---) – prefix decrement.</span></span> <span data-ttu-id="451a1-142">1 小さくなった (通常は整数 1 が減算された) x の値で格納場所を更新した後に x の値を返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-142">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="451a1-143">[(T)x](invocation-operator.md) – 型キャスト。</span><span class="sxs-lookup"><span data-stu-id="451a1-143">[(T)x](invocation-operator.md) – type casting.</span></span>

<span data-ttu-id="451a1-144">[await](../keywords/await.md) – `Task` を待機します。</span><span class="sxs-lookup"><span data-stu-id="451a1-144">[await](../keywords/await.md) – awaits a `Task`.</span></span>

<span data-ttu-id="451a1-145">[&x](pointer-related-operators.md#address-of-operator-) – 変数のアドレス。</span><span class="sxs-lookup"><span data-stu-id="451a1-145">[&x](pointer-related-operators.md#address-of-operator-) – address of a variable.</span></span>

<span data-ttu-id="451a1-146">[\* x](pointer-related-operators.md#pointer-indirection-operator-) – ポインターの間接参照、または逆参照。</span><span class="sxs-lookup"><span data-stu-id="451a1-146">[\*x](pointer-related-operators.md#pointer-indirection-operator-) – pointer indirection, or dereference.</span></span>

<span data-ttu-id="451a1-147">[true 演算子](true-false-operators.md) - オペランドが確実に true であることを示す[ブール](../keywords/bool.md)値 `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-147">[true operator](true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely true.</span></span>

<span data-ttu-id="451a1-148">[false 演算子](true-false-operators.md) - オペランドが確実に false であることを示す[ブール](../keywords/bool.md)値 `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-148">[false operator](true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely false.</span></span>

## <a name="multiplicative-operators"></a><span data-ttu-id="451a1-149">乗算演算子</span><span class="sxs-lookup"><span data-stu-id="451a1-149">Multiplicative operators</span></span>

<span data-ttu-id="451a1-150">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="451a1-150">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="451a1-151">[x \* y](arithmetic-operators.md#multiplication-operator-) – 乗算。</span><span class="sxs-lookup"><span data-stu-id="451a1-151">[x \* y](arithmetic-operators.md#multiplication-operator-) – multiplication.</span></span>

<span data-ttu-id="451a1-152">[x / y](arithmetic-operators.md#division-operator-) – 除算。</span><span class="sxs-lookup"><span data-stu-id="451a1-152">[x / y](arithmetic-operators.md#division-operator-) – division.</span></span> <span data-ttu-id="451a1-153">オペランドが整数の場合、結果は 0 に近い整数になるように切り捨てられます (例: `-7 / 2 is -3`)。</span><span class="sxs-lookup"><span data-stu-id="451a1-153">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>

<span data-ttu-id="451a1-154">[x % y](arithmetic-operators.md#remainder-operator-) – 剰余。</span><span class="sxs-lookup"><span data-stu-id="451a1-154">[x % y](arithmetic-operators.md#remainder-operator-) – remainder.</span></span> <span data-ttu-id="451a1-155">オペランドが整数の場合、x を y で除算した剰余を返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-155">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="451a1-156">`q = x / y` で `r = x % y` の場合、`x = q * y + r` になります。</span><span class="sxs-lookup"><span data-stu-id="451a1-156">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>

## <a name="additive-operators"></a><span data-ttu-id="451a1-157">加法演算子</span><span class="sxs-lookup"><span data-stu-id="451a1-157">Additive operators</span></span>

<span data-ttu-id="451a1-158">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="451a1-158">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="451a1-159">[x + y](arithmetic-operators.md#addition-operator-) – 加算。</span><span class="sxs-lookup"><span data-stu-id="451a1-159">[x + y](arithmetic-operators.md#addition-operator-) – addition.</span></span>

<span data-ttu-id="451a1-160">[x – y](arithmetic-operators.md#subtraction-operator--) – 減算。</span><span class="sxs-lookup"><span data-stu-id="451a1-160">[x – y](arithmetic-operators.md#subtraction-operator--) – subtraction.</span></span>

## <a name="shift-operators"></a><span data-ttu-id="451a1-161">シフト演算子</span><span class="sxs-lookup"><span data-stu-id="451a1-161">Shift operators</span></span>

<span data-ttu-id="451a1-162">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="451a1-162">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="451a1-163">[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-) – ビットを左へシフトし、右側には 0 を格納します。</span><span class="sxs-lookup"><span data-stu-id="451a1-163">[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-) – shift bits left and fill with zero on the right.</span></span>

<span data-ttu-id="451a1-164">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) – ビットを右へシフトします。</span><span class="sxs-lookup"><span data-stu-id="451a1-164">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) – shift bits right.</span></span> <span data-ttu-id="451a1-165">左側のオペランドが `int` または `long` の場合、左側のビットには符号ビットが格納されます。</span><span class="sxs-lookup"><span data-stu-id="451a1-165">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span> <span data-ttu-id="451a1-166">左側のオペランドが `uint` または `ulong` の場合、左側のビットには 0 が格納されます。</span><span class="sxs-lookup"><span data-stu-id="451a1-166">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>

## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="451a1-167">関係演算子と型検査演算子</span><span class="sxs-lookup"><span data-stu-id="451a1-167">Relational and type-testing operators</span></span>

<span data-ttu-id="451a1-168">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="451a1-168">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="451a1-169">[x \< y](comparison-operators.md#less-than-operator-) – より小さい (x が y より小さい場合は true)。</span><span class="sxs-lookup"><span data-stu-id="451a1-169">[x \< y](comparison-operators.md#less-than-operator-) – less than (true if x is less than y).</span></span>

<span data-ttu-id="451a1-170">[x > y](comparison-operators.md#greater-than-operator-) – より大きい (x が y より大きい場合は true)。</span><span class="sxs-lookup"><span data-stu-id="451a1-170">[x > y](comparison-operators.md#greater-than-operator-) – greater than (true if x is greater than y).</span></span>

<span data-ttu-id="451a1-171">[x \<= y](comparison-operators.md#less-than-or-equal-operator-) – 以下。</span><span class="sxs-lookup"><span data-stu-id="451a1-171">[x \<= y](comparison-operators.md#less-than-or-equal-operator-) – less than or equal to.</span></span>

<span data-ttu-id="451a1-172">[x >= y](comparison-operators.md#greater-than-or-equal-operator-) – 以上。</span><span class="sxs-lookup"><span data-stu-id="451a1-172">[x >= y](comparison-operators.md#greater-than-or-equal-operator-) – greater than or equal to.</span></span>

<span data-ttu-id="451a1-173">[is](../keywords/is.md) – 型の互換性。</span><span class="sxs-lookup"><span data-stu-id="451a1-173">[is](../keywords/is.md) – type compatibility.</span></span> <span data-ttu-id="451a1-174">評価される左側のオペランドを右側のオペランドで指定された型 (静的な型) にキャストできる場合は、true を返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-174">Returns true if the evaluated left operand can be cast to the type specified in the right operand (a static type).</span></span>

<span data-ttu-id="451a1-175">[as](../keywords/as.md) – 型変換。</span><span class="sxs-lookup"><span data-stu-id="451a1-175">[as](../keywords/as.md) – type conversion.</span></span> <span data-ttu-id="451a1-176">左側のオペランドを右側のオペランドで指定された型 (静的な型) にキャストして返します。ただし、`(T)x` が例外をスローした場合、`as` は `null` を返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-176">Returns the left operand cast to the type specified by the right operand (a static type), but `as` returns `null` where `(T)x` would throw an exception.</span></span>

## <a name="equality-operators"></a><span data-ttu-id="451a1-177">等値演算子</span><span class="sxs-lookup"><span data-stu-id="451a1-177">Equality operators</span></span>

<span data-ttu-id="451a1-178">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="451a1-178">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="451a1-179">[x == y](equality-operators.md#equality-operator-) – 等価比較。</span><span class="sxs-lookup"><span data-stu-id="451a1-179">[x == y](equality-operators.md#equality-operator-) – equality.</span></span> <span data-ttu-id="451a1-180">既定では、`string` 以外の参照型の場合、参照の等価性を返します (等価テスト)。</span><span class="sxs-lookup"><span data-stu-id="451a1-180">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span> <span data-ttu-id="451a1-181">ただし、型は `==` をオーバーロードできるため、同一性のテストが目的の場合は `object` で `ReferenceEquals` メソッドを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="451a1-181">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>

<span data-ttu-id="451a1-182">[x != y](equality-operators.md#inequality-operator-) – 等しくない。</span><span class="sxs-lookup"><span data-stu-id="451a1-182">[x != y](equality-operators.md#inequality-operator-) – not equal.</span></span> <span data-ttu-id="451a1-183">`==` のコメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="451a1-183">See comment for `==`.</span></span> <span data-ttu-id="451a1-184">型が `==` をオーバーロードする場合は、`!=` をオーバーロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="451a1-184">If a type overloads `==`, then it must overload `!=`.</span></span>

## <a name="logical-and-operator"></a><span data-ttu-id="451a1-185">論理 AND 演算子</span><span class="sxs-lookup"><span data-stu-id="451a1-185">Logical AND operator</span></span>

<span data-ttu-id="451a1-186">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="451a1-186">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="451a1-187">`x & y` – `bool` オペランドの場合は[論理 AND](boolean-logical-operators.md#logical-and-operator-)、整数型のオペランドの場合は[ビットごとの論理 AND](bitwise-and-shift-operators.md#logical-and-operator-)。</span><span class="sxs-lookup"><span data-stu-id="451a1-187">`x & y` – [logical AND](boolean-logical-operators.md#logical-and-operator-) for the `bool` operands or [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) for the operands of the integral types.</span></span>

## <a name="logical-xor-operator"></a><span data-ttu-id="451a1-188">論理 XOR 演算子</span><span class="sxs-lookup"><span data-stu-id="451a1-188">Logical XOR operator</span></span>

<span data-ttu-id="451a1-189">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="451a1-189">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="451a1-190">`x ^ y` – `bool` オペランドの場合は[論理 XOR](boolean-logical-operators.md#logical-exclusive-or-operator-)、整数型のオペランドの場合は[ビットごとの論理 XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-)。</span><span class="sxs-lookup"><span data-stu-id="451a1-190">`x ^ y` – [logical XOR](boolean-logical-operators.md#logical-exclusive-or-operator-) for the `bool` operands or [bitwise logical XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) for the operands of the integral types.</span></span>

## <a name="logical-or-operator"></a><span data-ttu-id="451a1-191">論理演算子 OR</span><span class="sxs-lookup"><span data-stu-id="451a1-191">Logical OR operator</span></span>

<span data-ttu-id="451a1-192">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="451a1-192">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="451a1-193">`x | y` – `bool` オペランドの場合は[論理 OR](boolean-logical-operators.md#logical-or-operator-)、整数型のオペランドの場合は[ビットごとの論理 OR](bitwise-and-shift-operators.md#logical-or-operator-)。</span><span class="sxs-lookup"><span data-stu-id="451a1-193">`x | y` – [logical OR](boolean-logical-operators.md#logical-or-operator-) for the `bool` operands or [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) for the operands of the integral types.</span></span>

## <a name="conditional-and-operator"></a><span data-ttu-id="451a1-194">条件 AND 演算子</span><span class="sxs-lookup"><span data-stu-id="451a1-194">Conditional AND operator</span></span>

<span data-ttu-id="451a1-195">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="451a1-195">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="451a1-196">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) – 論理 AND。</span><span class="sxs-lookup"><span data-stu-id="451a1-196">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) – logical AND.</span></span> <span data-ttu-id="451a1-197">最初のオペランドが false に評価される場合、C# では 2 番目のオペランドが評価されません。</span><span class="sxs-lookup"><span data-stu-id="451a1-197">If the first operand evaluates to false, then C# does not evaluate the second operand.</span></span>

## <a name="conditional-or-operator"></a><span data-ttu-id="451a1-198">条件 OR 演算子</span><span class="sxs-lookup"><span data-stu-id="451a1-198">Conditional OR operator</span></span>

<span data-ttu-id="451a1-199">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="451a1-199">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="451a1-200">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) – 論理 OR。</span><span class="sxs-lookup"><span data-stu-id="451a1-200">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) – logical OR.</span></span> <span data-ttu-id="451a1-201">最初のオペランドが true に評価される場合、C# では 2 番目のオペランドが評価されません。</span><span class="sxs-lookup"><span data-stu-id="451a1-201">If the first operand evaluates to true, then C# does not evaluate the second operand.</span></span>

## <a name="null-coalescing-operator"></a><span data-ttu-id="451a1-202">Null 合体演算子</span><span class="sxs-lookup"><span data-stu-id="451a1-202">Null-coalescing operator</span></span>

<span data-ttu-id="451a1-203">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="451a1-203">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="451a1-204">[x ?? y](null-coalescing-operator.md) – `x` が `null` 以外の場合は x を返します。null の場合は `y` を返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-204">[x ?? y](null-coalescing-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>

## <a name="conditional-operator"></a><span data-ttu-id="451a1-205">条件演算子</span><span class="sxs-lookup"><span data-stu-id="451a1-205">Conditional operator</span></span>

<span data-ttu-id="451a1-206">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="451a1-206">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="451a1-207">[t ? x : y](conditional-operator.md) – テスト `t` が true に評価される場合は `x` を評価して返します。それ以外の場合は `y` を評価して返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-207">[t ? x : y](conditional-operator.md) – if test `t` evaluates to true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>

## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="451a1-208">代入演算子とラムダ演算子</span><span class="sxs-lookup"><span data-stu-id="451a1-208">Assignment and lambda operators</span></span>

<span data-ttu-id="451a1-209">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="451a1-209">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="451a1-210">[x = y](assignment-operator.md) – 代入。</span><span class="sxs-lookup"><span data-stu-id="451a1-210">[x = y](assignment-operator.md) – assignment.</span></span>

<span data-ttu-id="451a1-211">[x += y](arithmetic-operators.md#compound-assignment) – インクリメント。</span><span class="sxs-lookup"><span data-stu-id="451a1-211">[x += y](arithmetic-operators.md#compound-assignment) – increment.</span></span> <span data-ttu-id="451a1-212">`y` の値を `x` の値に加算した結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-212">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="451a1-213">`x` が[イベント](../keywords/event.md)を指定した場合、`y` は、C# によってイベント ハンドラーとして追加される適切なメソッドである必要があります。</span><span class="sxs-lookup"><span data-stu-id="451a1-213">If `x` designates an [event](../keywords/event.md), then `y` must be an appropriate method that C# adds as an event handler.</span></span>

<span data-ttu-id="451a1-214">[x -= y](arithmetic-operators.md#compound-assignment) – デクリメント。</span><span class="sxs-lookup"><span data-stu-id="451a1-214">[x -= y](arithmetic-operators.md#compound-assignment) – decrement.</span></span> <span data-ttu-id="451a1-215">`y` の値を `x` の値から減算した結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-215">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="451a1-216">`x` で[イベント](../keywords/event.md)を指定する場合、`y` は C# によってイベント ハンドラーとして削除される適切なメソッドである必要があります。</span><span class="sxs-lookup"><span data-stu-id="451a1-216">If `x` designates an [event](../keywords/event.md), then `y` must be an appropriate method that C# removes as an event handler.</span></span>

<span data-ttu-id="451a1-217">[x \*= y](arithmetic-operators.md#compound-assignment) – 乗算代入。</span><span class="sxs-lookup"><span data-stu-id="451a1-217">[x \*= y](arithmetic-operators.md#compound-assignment) – multiplication assignment.</span></span> <span data-ttu-id="451a1-218">`y` の値を `x` の値に乗算した結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-218">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="451a1-219">[x /= y](arithmetic-operators.md#compound-assignment) – 除算代入。</span><span class="sxs-lookup"><span data-stu-id="451a1-219">[x /= y](arithmetic-operators.md#compound-assignment) – division assignment.</span></span> <span data-ttu-id="451a1-220">`x` の値を `y` の値で除算した結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-220">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="451a1-221">[x %= y](arithmetic-operators.md#compound-assignment) – 剰余代入。</span><span class="sxs-lookup"><span data-stu-id="451a1-221">[x %= y](arithmetic-operators.md#compound-assignment) – remainder assignment.</span></span> <span data-ttu-id="451a1-222">`x` の値を `y` の値で除算した剰余を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-222">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>

<span data-ttu-id="451a1-223">[x &= y](boolean-logical-operators.md#compound-assignment) – AND 代入。</span><span class="sxs-lookup"><span data-stu-id="451a1-223">[x &= y](boolean-logical-operators.md#compound-assignment) – AND assignment.</span></span> <span data-ttu-id="451a1-224">`y` の値と `x` の値の AND 演算を行った結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-224">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="451a1-225">[x &#124;= y](boolean-logical-operators.md#compound-assignment) – OR 代入。</span><span class="sxs-lookup"><span data-stu-id="451a1-225">[x &#124;= y](boolean-logical-operators.md#compound-assignment) – OR assignment.</span></span> <span data-ttu-id="451a1-226">`y` の値と `x` の値の OR 演算を行った結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-226">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="451a1-227">[x ^= y](boolean-logical-operators.md#compound-assignment) – XOR 代入。</span><span class="sxs-lookup"><span data-stu-id="451a1-227">[x ^= y](boolean-logical-operators.md#compound-assignment) – XOR assignment.</span></span> <span data-ttu-id="451a1-228">`y` の値と `x` の値の XOR 演算を行った結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-228">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="451a1-229">[x <<= y](bitwise-and-shift-operators.md#compound-assignment) – 左シフト代入。</span><span class="sxs-lookup"><span data-stu-id="451a1-229">[x <<= y](bitwise-and-shift-operators.md#compound-assignment) – left-shift assignment.</span></span> <span data-ttu-id="451a1-230">`x` の値を `y` で指定した分だけ左へシフトした結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-230">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="451a1-231">[x >>= y](bitwise-and-shift-operators.md#compound-assignment) – 右シフト代入。</span><span class="sxs-lookup"><span data-stu-id="451a1-231">[x >>= y](bitwise-and-shift-operators.md#compound-assignment) – right-shift assignment.</span></span> <span data-ttu-id="451a1-232">`x` の値を `y` で指定した分だけ右へシフトした結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="451a1-232">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="451a1-233">[=>](lambda-operator.md) – ラムダ宣言。</span><span class="sxs-lookup"><span data-stu-id="451a1-233">[=>](lambda-operator.md) – lambda declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="451a1-234">関連項目</span><span class="sxs-lookup"><span data-stu-id="451a1-234">See also</span></span>

- [<span data-ttu-id="451a1-235">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="451a1-235">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="451a1-236">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="451a1-236">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="451a1-237">C#</span><span class="sxs-lookup"><span data-stu-id="451a1-237">C#</span></span>](../../index.md)
- [<span data-ttu-id="451a1-238">オーバーロード可能な演算子</span><span class="sxs-lookup"><span data-stu-id="451a1-238">Overloadable operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="451a1-239">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="451a1-239">C# Keywords</span></span>](../keywords/index.md)
