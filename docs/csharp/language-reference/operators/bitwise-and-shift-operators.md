---
title: ビットごとの演算子とシフト演算子 - C# リファレンス
description: 整数型のオペランドに対してビットごとの論理演算またはシフト演算を実行する C# の演算子について説明します。
ms.date: 04/18/2019
author: pkulikov
f1_keywords:
- ~_CSharpKeyword
- <<_CSharpKeyword
- '>>_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise logical operators [C#]
- shift operators [C#]
- tilde operator [C#]
- one's complement operator [C#]
- bitwise complement operator [C#]
- ~ operator [C#]
- left shift operator [C#]
- << operator [C#]
- right shift operator [C#]
- '>> operator [C#]'
- bitwise logical AND operator [C#]
- ampersand operator [C#]
- '& operator [C#]'
- bitwise logical exclusive OR operator [C#]
- bitwise logical XOR operator [C#]
- ^ operator [C#]
- bitwise logical OR operator [C#]
- '| operator [C#]'
ms.openlocfilehash: bf42a53a89676f457d3d2df8d193a83299c3e4cc
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758368"
---
# <a name="bitwise-and-shift-operators-c-reference"></a><span data-ttu-id="52e73-103">ビットごとの演算子とシフト演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="52e73-103">Bitwise and shift operators (C# Reference)</span></span>

<span data-ttu-id="52e73-104">以下の演算子では、[整数型](../keywords/integral-types-table.md)のオペランドに対してビットごとの演算またはシフト演算が実行されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-104">The following operators perform bitwise or shift operations with operands of the [integral types](../keywords/integral-types-table.md):</span></span>

- <span data-ttu-id="52e73-105">単項 [`~` (ビットごとの補数)](#bitwise-complement-operator-) 演算子</span><span class="sxs-lookup"><span data-stu-id="52e73-105">Unary [`~` (bitwise complement)](#bitwise-complement-operator-) operator</span></span>
- <span data-ttu-id="52e73-106">2 項 [`<<` (左シフト)](#left-shift-operator-) および [`>>` (右シフト)](#right-shift-operator-) シフト演算子</span><span class="sxs-lookup"><span data-stu-id="52e73-106">Binary [`<<` (left shift)](#left-shift-operator-) and [`>>` (right shift)](#right-shift-operator-) shift operators</span></span>
- <span data-ttu-id="52e73-107">2 項 [`&` (論理 AND)](#logical-and-operator-)、[`|` (論理 OR)](#logical-or-operator-)、および [`^` (論理排他的 OR)](#logical-exclusive-or-operator-) 演算子</span><span class="sxs-lookup"><span data-stu-id="52e73-107">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators</span></span>

<span data-ttu-id="52e73-108">これらの演算子は、`int`、`uint`、`long`、`ulong` 型に対して定義されています。</span><span class="sxs-lookup"><span data-stu-id="52e73-108">Those operators are defined for the `int`, `uint`, `long`, and `ulong` types.</span></span> <span data-ttu-id="52e73-109">両方のオペランドが他の整数型 (`sbyte`、`byte`、`short`、`ushort`、`char`) の場合、それらの値は `int` 型に変換され、演算の結果もその型になります。</span><span class="sxs-lookup"><span data-stu-id="52e73-109">When both operands are of other integral types (`sbyte`, `byte`, `short`, `ushort`, or `char`), their values are converted to the `int` type, which is also the result type of an operation.</span></span> <span data-ttu-id="52e73-110">オペランドが異なる整数型の場合、それらの値は最も近い含んでいる整数型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-110">When operands are of different integral types, their values are converted to the closest containing integral type.</span></span> <span data-ttu-id="52e73-111">詳しくは、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の「[数値の上位変換](~/_csharplang/spec/expressions.md#numeric-promotions)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="52e73-111">For more information, see the [Numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="52e73-112">`&`、`|`、`^` の各演算子は、`bool` 型のオペランドに対しても定義されています。</span><span class="sxs-lookup"><span data-stu-id="52e73-112">The `&`, `|`, and `^` operators are also defined for the operands of the `bool` type.</span></span> <span data-ttu-id="52e73-113">詳しくは、「[ブール論理演算子](boolean-logical-operators.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="52e73-113">For more information, see [Boolean logical operators](boolean-logical-operators.md).</span></span>

<span data-ttu-id="52e73-114">ビットごとの演算子およびシフト演算が原因でオーバーフローが発生することはなく、[checked と unchecked](../keywords/checked-and-unchecked.md) のコンテキストで同じ結果が生成されることはありません。</span><span class="sxs-lookup"><span data-stu-id="52e73-114">Bitwise and shift operations never cause overflow and produce the same results in [checked and unchecked](../keywords/checked-and-unchecked.md) contexts.</span></span>

## <a name="bitwise-complement-operator-"></a><span data-ttu-id="52e73-115">ビットごとの補数演算子 ~</span><span class="sxs-lookup"><span data-stu-id="52e73-115">Bitwise complement operator ~</span></span>

<span data-ttu-id="52e73-116">`~` 演算子では、各ビットを反転させることにより、オペランドのビットごとの補数が生成されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-116">The `~` operator produces a bitwise complement of its operand by reversing each bit:</span></span>

[!code-csharp-interactive[bitwise NOT](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseComplement)]

<span data-ttu-id="52e73-117">`~` シンボルはファイナライザーの宣言にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="52e73-117">You can also use the `~` symbol to declare finalizers.</span></span> <span data-ttu-id="52e73-118">詳細については、「[Finalizers](../../programming-guide/classes-and-structs/destructors.md)」 (ファイナライザー) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52e73-118">For more information, see [Finalizers](../../programming-guide/classes-and-structs/destructors.md).</span></span>

## <a name="left-shift-operator-"></a><span data-ttu-id="52e73-119">左シフト演算子 \<\<</span><span class="sxs-lookup"><span data-stu-id="52e73-119">Left-shift operator \<\<</span></span>

<span data-ttu-id="52e73-120">`<<` 演算子では、最初のオペランドが 2 番目のオペランドで定義されたビット数だけ左にシフトされます。</span><span class="sxs-lookup"><span data-stu-id="52e73-120">The `<<` operator shifts its first operand left by the number of bits defined by its second operand.</span></span>

<span data-ttu-id="52e73-121">次の例に示すように、左シフト演算子では、結果の型の範囲外にある上位ビットは破棄され、空の下位ビット位置は、ゼロに設定されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-121">The left-shift operation discards the high-order bits that are outside the range of the result type and sets the low-order empty bit positions to zero, as the following example shows:</span></span>

[!code-csharp-interactive[left shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LeftShift)]

<span data-ttu-id="52e73-122">シフト演算子は `int`、`uint`、`long`、`ulong` 型に対してのみ定義されるので、演算の結果には常に少なくとも 32 ビットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="52e73-122">Because the shift operators are defined only for the `int`, `uint`, `long`, and `ulong` types, the result of an operation always contains at least 32 bits.</span></span> <span data-ttu-id="52e73-123">1 番目のオペランドが別の整数型 (`sbyte`、`byte`、`short`、`ushort`、`char`) の場合、次の例で示すように、その値は `int` 型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-123">If the first operand is of another integral type (`sbyte`, `byte`, `short`, `ushort`, or `char`), its value is converted to the `int` type, as the following example shows:</span></span>

[!code-csharp-interactive[left shift with promotion](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LeftShiftPromoted)]

<span data-ttu-id="52e73-124">`<<` 演算子の 2 番目のオペランドでのシフト数の定義方法については、「[シフト演算子のシフト数](#shift-count-of-the-shift-operators)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="52e73-124">For information about how the second operand of the `<<` operator defines the shift count, see the [Shift count of the shift operators](#shift-count-of-the-shift-operators) section.</span></span>

## <a name="right-shift-operator-"></a><span data-ttu-id="52e73-125">右シフト演算子 >></span><span class="sxs-lookup"><span data-stu-id="52e73-125">Right-shift operator >></span></span>

<span data-ttu-id="52e73-126">`>>` 演算子では、最初のオペランドが 2 番目のオペランドで定義されたビット数だけ右にシフトされます。</span><span class="sxs-lookup"><span data-stu-id="52e73-126">The `>>` operator shifts its first operand right by the number of bits defined by its second operand.</span></span>

<span data-ttu-id="52e73-127">次の例で示すように、右シフト演算では、下位ビットが破棄されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-127">The right-shift operation discards the low-order bits, as the following example shows:</span></span>

[!code-csharp-interactive[right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#RightShift)]

<span data-ttu-id="52e73-128">空の上位ビット位置は、最初のオペランドの型に基づいて次のように設定されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-128">The high-order empty bit positions are set based on the type of the first operand as follows:</span></span>

- <span data-ttu-id="52e73-129">最初のオペランドの型が [int](../keywords/int.md) または [long](../keywords/long.md) である場合、右シフト演算子では、*算術*シフトが実行されます: 最初のオペランドの最上位ビット (符号ビット) の値が空の上位ビット位置に反映されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-129">If the first operand is of type [int](../keywords/int.md) or [long](../keywords/long.md), the right-shift operator performs an *arithmetic* shift: the value of the most significant bit (the sign bit) of the first operand is propagated to the high-order empty bit positions.</span></span> <span data-ttu-id="52e73-130">つまり、最初のオペランドが負でない場合は空の上位ビット位置が 0 に設定され、負の場合は 1 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-130">That is, the high-order empty bit positions are set to zero if the first operand is non-negative and set to one if it's negative.</span></span>

  [!code-csharp-interactive[arithmetic right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#ArithmeticRightShift)]

- <span data-ttu-id="52e73-131">最初のオペランドの型が [uint](../keywords/uint.md) または [ulong](../keywords/ulong.md) である場合、右シフト演算子では、*論理*シフトが実行されます: 空の上位ビット位置は常に 0 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-131">If the first operand is of type [uint](../keywords/uint.md) or [ulong](../keywords/ulong.md), the right-shift operator performs a *logical* shift: the high-order empty bit positions are always set to zero.</span></span>

  [!code-csharp-interactive[logical right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LogicalRightShift)]

<span data-ttu-id="52e73-132">`>>` 演算子の 2 番目のオペランドでのシフト数の定義方法については、「[シフト演算子のシフト数](#shift-count-of-the-shift-operators)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="52e73-132">For information about how the second operand of the `>>` operator defines the shift count, see the [Shift count of the shift operators](#shift-count-of-the-shift-operators) section.</span></span>

## <a name="logical-and-operator-amp"></a><span data-ttu-id="52e73-133">論理 AND 演算子 &amp;</span><span class="sxs-lookup"><span data-stu-id="52e73-133">Logical AND operator &amp;</span></span>

<span data-ttu-id="52e73-134">`&` 演算子では、そのオペランドのビットごとの論理 AND が計算されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-134">The `&` operator computes the bitwise logical AND of its operands:</span></span>

[!code-csharp-interactive[bitwise AND](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseAnd)]

<span data-ttu-id="52e73-135">`bool` 型のオペランドの場合、`&` 演算子ではそのオペランドの[論理 AND](boolean-logical-operators.md#logical-and-operator-) が計算されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-135">For the operands of the `bool` type, the `&` operator computes the [logical AND](boolean-logical-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="52e73-136">単項 `&` 演算子は[アドレス演算子](pointer-related-operators.md#address-of-operator-)です。</span><span class="sxs-lookup"><span data-stu-id="52e73-136">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="52e73-137">論理排他的 OR 演算子: ^</span><span class="sxs-lookup"><span data-stu-id="52e73-137">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="52e73-138">`^` 演算子では、そのオペランドのビットごとの論理排他的 OR (ビットごとの論理 XOR とも呼ばれます) が計算されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-138">The `^` operator computes the bitwise logical exclusive OR, also known as the bitwise logical XOR, of its operands:</span></span>

[!code-csharp-interactive[bitwise XOR](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseXor)]

<span data-ttu-id="52e73-139">`bool` 型のオペランドの場合、`^` 演算子では、そのオペランドの[論理排他的 OR](boolean-logical-operators.md#logical-exclusive-or-operator-) が計算されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-139">For the operands of the `bool` type, the `^` operator computes the [logical exclusive OR](boolean-logical-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="52e73-140">論理 OR 演算子 |</span><span class="sxs-lookup"><span data-stu-id="52e73-140">Logical OR operator |</span></span>

<span data-ttu-id="52e73-141">`|` 演算子では、そのオペランドのビットごとの論理 OR が計算されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-141">The `|` operator computes the bitwise logical OR of its operands:</span></span>

[!code-csharp-interactive[bitwise OR](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseOr)]

<span data-ttu-id="52e73-142">`bool` 型のオペランドの場合、`|` 演算子ではそのオペランドの[論理 OR](boolean-logical-operators.md#logical-or-operator-) が計算されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-142">For the operands of the `bool` type, the `|` operator computes the [logical OR](boolean-logical-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="52e73-143">複合代入。</span><span class="sxs-lookup"><span data-stu-id="52e73-143">Compound assignment</span></span>

<span data-ttu-id="52e73-144">2 項演算子 `op` の場合、フォームの複合代入式</span><span class="sxs-lookup"><span data-stu-id="52e73-144">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="52e73-145">上記の式は、次の式と同じです。</span><span class="sxs-lookup"><span data-stu-id="52e73-145">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="52e73-146">ただし、`x` が評価されるのは 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="52e73-146">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="52e73-147">次の例では、ビットごとの演算子およびシフト演算子を使った複合代入の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="52e73-147">The following example demonstrates the usage of compound assignment with bitwise and shift operators:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#CompoundAssignment)]

<span data-ttu-id="52e73-148">[数値の上位変換](~/_csharplang/spec/expressions.md#numeric-promotions)のため、`op` 演算の結果は、`x` の型 `T` に暗黙的に変換できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="52e73-148">Because of [numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions), the result of the `op` operation might be not implicitly convertible to the type `T` of `x`.</span></span> <span data-ttu-id="52e73-149">そのような場合、`op` が定義済みの演算子であり、演算の結果が `x` の型 `T` に明示的に変換できる場合、`x op= y` の形式の複合代入式は、`x` が 1 回だけ評価される点を除き、`x = (T)(x op y)` と等価です。</span><span class="sxs-lookup"><span data-stu-id="52e73-149">In such a case, if `op` is a predefined operator and the result of the operation is explicitly convertible to the type `T` of `x`, a compound assignment expression of the form `x op= y` is equivalent to `x = (T)(x op y)`, except that `x` is only evaluated once.</span></span> <span data-ttu-id="52e73-150">次の例は、その動作を示します。</span><span class="sxs-lookup"><span data-stu-id="52e73-150">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[compound assignment with cast](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#CompoundAssignmentWithCast)]

## <a name="operator-precedence"></a><span data-ttu-id="52e73-151">演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="52e73-151">Operator precedence</span></span>

<span data-ttu-id="52e73-152">次のビットごとの演算子およびシフト演算子の一覧は、優先度が高い順に並べられています。</span><span class="sxs-lookup"><span data-stu-id="52e73-152">The following list orders bitwise and shift operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="52e73-153">ビットごとの補数演算子 `~`</span><span class="sxs-lookup"><span data-stu-id="52e73-153">Bitwise complement operator `~`</span></span>
- <span data-ttu-id="52e73-154">シフト演算子 `<<` および `>>`</span><span class="sxs-lookup"><span data-stu-id="52e73-154">Shift operators `<<` and `>>`</span></span>
- <span data-ttu-id="52e73-155">論理 AND 演算子 `&`</span><span class="sxs-lookup"><span data-stu-id="52e73-155">Logical AND operator `&`</span></span>
- <span data-ttu-id="52e73-156">論理排他的 OR 演算子 `^`</span><span class="sxs-lookup"><span data-stu-id="52e73-156">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="52e73-157">論理 OR 演算子 `|`</span><span class="sxs-lookup"><span data-stu-id="52e73-157">Logical OR operator `|`</span></span>

<span data-ttu-id="52e73-158">演算子の優先順位によって定められた評価の順序を変更するには、かっこ `()` を使用します。</span><span class="sxs-lookup"><span data-stu-id="52e73-158">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#Precedence)]

<span data-ttu-id="52e73-159">優先度順に並べられた C# 演算子の完全な一覧については、「[C# 演算子](index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52e73-159">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="shift-count-of-the-shift-operators"></a><span data-ttu-id="52e73-160">シフト演算子のシフト数</span><span class="sxs-lookup"><span data-stu-id="52e73-160">Shift count of the shift operators</span></span>

<span data-ttu-id="52e73-161">シフト演算子 `<<` および `>>` の場合、2 番目のオペランドの型は、[int](../keywords/int.md) であるか、または `int` への[事前に定義された暗黙的な数値変換](../keywords/implicit-numeric-conversions-table.md)を持つ型にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="52e73-161">For the shift operators `<<` and `>>`, the type of the second operand must be [int](../keywords/int.md) or a type that has a [predefined implicit numeric conversion](../keywords/implicit-numeric-conversions-table.md) to `int`.</span></span>

<span data-ttu-id="52e73-162">`x << count` および `x >> count` の式では、実際のシフト数は次のように `x` の型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="52e73-162">For the `x << count` and `x >> count` expressions, the actual shift count depends on the type of `x` as follows:</span></span>

- <span data-ttu-id="52e73-163">`x` の型が [int](../keywords/int.md) または [uint](../keywords/uint.md) である場合、シフト数は、2 番目のオペランドの下位 *5* ビットで定義されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-163">If the type of `x` is [int](../keywords/int.md) or [uint](../keywords/uint.md), the shift count is defined by the low-order *five* bits of the second operand.</span></span> <span data-ttu-id="52e73-164">つまり、シフト数は `count & 0x1F` (または `count & 0b_1_1111`) から計算されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-164">That is, the shift count is computed from `count & 0x1F` (or `count & 0b_1_1111`).</span></span>

- <span data-ttu-id="52e73-165">`x` の型が [long](../keywords/long.md) または [ulong](../keywords/ulong.md) である場合、シフト数は、2 番目のオペランドの下位 *6* ビットで定義されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-165">If the type of `x` is [long](../keywords/long.md) or [ulong](../keywords/ulong.md), the shift count is defined by the low-order *six* bits of the second operand.</span></span> <span data-ttu-id="52e73-166">つまり、シフト数は `count & 0x3F` (または `count & 0b_11_1111`) から計算されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-166">That is, the shift count is computed from `count & 0x3F` (or `count & 0b_11_1111`).</span></span>

<span data-ttu-id="52e73-167">次の例は、その動作を示します。</span><span class="sxs-lookup"><span data-stu-id="52e73-167">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[shift count example](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#ShiftCount)]

## <a name="enumeration-logical-operators"></a><span data-ttu-id="52e73-168">列挙論理演算子</span><span class="sxs-lookup"><span data-stu-id="52e73-168">Enumeration logical operators</span></span>

<span data-ttu-id="52e73-169">`~`、`&`、`|`、`^` 演算子は、任意の[列挙](../keywords/enum.md)型に対しても定義されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-169">The `~`, `&`, `|`, and `^` operators are also defined for any [enumeration](../keywords/enum.md) type.</span></span> <span data-ttu-id="52e73-170">オペランドが同じ列挙型の場合、基になっている整数型の対応する値に対して、論理演算が実行されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-170">For the operands of the same enumeration type, a logical operation is performed on the corresponding values of the underlying integral type.</span></span> <span data-ttu-id="52e73-171">たとえば、基になる型が `U` である列挙型 `T` の任意の `x` と `y` に対して、式 `x & y` では式 `(T)((U)x & (U)y)` と同じ結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="52e73-171">For example, for any `x` and `y` of an enumeration type `T` with an underlying type `U`, the `x & y` expression produces the same result as the `(T)((U)x & (U)y)` expression.</span></span>

<span data-ttu-id="52e73-172">通常、ビットごとの論理演算子は、[Flags](xref:System.FlagsAttribute) 属性で定義されている列挙型で使います。</span><span class="sxs-lookup"><span data-stu-id="52e73-172">You typically use bitwise logical operators with an enumeration type which is defined with the [Flags](xref:System.FlagsAttribute) attribute.</span></span> <span data-ttu-id="52e73-173">詳しくは、「[列挙型](../../programming-guide/enumeration-types.md)」記事の「[ビット フラグとしての列挙型](../../programming-guide/enumeration-types.md#enumeration-types-as-bit-flags)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="52e73-173">For more information, see the [Enumeration types as bit flags](../../programming-guide/enumeration-types.md#enumeration-types-as-bit-flags) section of the [Enumeration types](../../programming-guide/enumeration-types.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="52e73-174">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="52e73-174">Operator overloadability</span></span>

<span data-ttu-id="52e73-175">ユーザー定義型では、`~`、`<<`、`>>`、`&`、`|`、`^` の各演算子を[オーバーロード](../keywords/operator.md)できます。</span><span class="sxs-lookup"><span data-stu-id="52e73-175">A user-defined type can [overload](../keywords/operator.md) the `~`, `<<`, `>>`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="52e73-176">2 項演算子をオーバーロードすると、対応する複合代入演算子も暗黙的にオーバーロードされます。</span><span class="sxs-lookup"><span data-stu-id="52e73-176">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="52e73-177">ユーザー定義型は、複合代入演算子を明示的にオーバーロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="52e73-177">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="52e73-178">ユーザー定義型 `T` で `<<` または `>>` 演算子をオーバーロードする場合、1 番目のオペランドの型は `T` である必要があり、2 番目のオペランドの型は `int` である必要があります。</span><span class="sxs-lookup"><span data-stu-id="52e73-178">If a user-defined type `T` overloads the `<<` or `>>` operator, the type of the first operand must be `T` and the type of the second operand must be `int`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="52e73-179">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="52e73-179">C# language specification</span></span>

<span data-ttu-id="52e73-180">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="52e73-180">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="52e73-181">ビットごとの補数演算子</span><span class="sxs-lookup"><span data-stu-id="52e73-181">Bitwise complement operator</span></span>](~/_csharplang/spec/expressions.md#bitwise-complement-operator)
- [<span data-ttu-id="52e73-182">シフト演算子</span><span class="sxs-lookup"><span data-stu-id="52e73-182">Shift operators</span></span>](~/_csharplang/spec/expressions.md#shift-operators)
- [<span data-ttu-id="52e73-183">論理演算子</span><span class="sxs-lookup"><span data-stu-id="52e73-183">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="52e73-184">複合代入</span><span class="sxs-lookup"><span data-stu-id="52e73-184">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)
- [<span data-ttu-id="52e73-185">数値の上位変換</span><span class="sxs-lookup"><span data-stu-id="52e73-185">Numeric promotions</span></span>](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a><span data-ttu-id="52e73-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="52e73-186">See also</span></span>

- [<span data-ttu-id="52e73-187">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="52e73-187">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="52e73-188">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="52e73-188">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="52e73-189">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="52e73-189">C# Operators</span></span>](index.md)
- [<span data-ttu-id="52e73-190">ブール論理演算子</span><span class="sxs-lookup"><span data-stu-id="52e73-190">Boolean logical operators</span></span>](boolean-logical-operators.md)
