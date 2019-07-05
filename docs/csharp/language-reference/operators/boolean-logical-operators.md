---
title: ブール論理演算子 - C# リファレンス
description: ブール オペランドを使用した論理否定演算、論理積演算 (AND)、および包含的および排他的論理和演算 (OR) を実行する C# 演算子について説明します。
ms.date: 04/08/2019
author: pkulikov
f1_keywords:
- '!_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
- '&&_CSharpKeyword'
- '||_CSharpKeyword'
helpviewer_keywords:
- logical operators [C#]
- short-circuiting operators [C#]
- logical negation operator [C#]
- NOT operator [C#]
- '! operator [C#]'
- AND operator [C#]
- ampersand operator [C#]
- conjunction operator [C#]
- '& operator [C#]'
- exclusive OR operator [C#]
- XOR operator [C#]
- ^ operator [C#]
- OR operator [C#]
- disjunction operator [C#]
- '| operator [C#]'
- conditional AND operator [C#]
- short-circuiting AND operator [C#]
- '&& operator [C#]'
- conditional OR operator [C#]
- short-circuiting OR operator [C#]
- '|| operator [C#]'
ms.openlocfilehash: 60907eb1bbfeb1daa9d9a74733387c4771accb45
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423975"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="1f39b-103">ブール論理演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="1f39b-103">Boolean logical operators (C# reference)</span></span>

<span data-ttu-id="1f39b-104">次の演算子は、[bool](../keywords/bool.md) オペランドを使用して論理演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="1f39b-104">The following operators perform logical operations with the [bool](../keywords/bool.md) operands:</span></span>

- <span data-ttu-id="1f39b-105">単項 [`!` (論理否定)](#logical-negation-operator-) 演算子。</span><span class="sxs-lookup"><span data-stu-id="1f39b-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="1f39b-106">二項 [`&` (論理 AND)](#logical-and-operator-)、[`|` (論理 OR)](#logical-or-operator-)、および [`^` (論理排他的 OR)](#logical-exclusive-or-operator-) 演算子。</span><span class="sxs-lookup"><span data-stu-id="1f39b-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="1f39b-107">これらの演算子は常に両方のオペランドを評価します。</span><span class="sxs-lookup"><span data-stu-id="1f39b-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="1f39b-108">二項 [`&&` (条件付き論理 AND)](#conditional-logical-and-operator-) および [`||` (条件付き論理 OR)](#conditional-logical-or-operator-) 演算子。</span><span class="sxs-lookup"><span data-stu-id="1f39b-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="1f39b-109">これらの演算子では、必要な場合にのみ右側のオペランドが評価されます。</span><span class="sxs-lookup"><span data-stu-id="1f39b-109">Those operators evaluate the right-hand operand only if it's necessary.</span></span>

<span data-ttu-id="1f39b-110">[整数](../builtin-types/integral-numeric-types.md)型のオペランドの場合、`&`、`|`、および `^` 演算子はビットごとの論理演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="1f39b-110">For the operands of the [integral](../builtin-types/integral-numeric-types.md) types, the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span> <span data-ttu-id="1f39b-111">詳しくは、「[ビットごとの演算子とシフト演算子](bitwise-and-shift-operators.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1f39b-111">For more information, see [Bitwise and shift operators](bitwise-and-shift-operators.md).</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="1f39b-112">論理否定演算子 !</span><span class="sxs-lookup"><span data-stu-id="1f39b-112">Logical negation operator !</span></span>

<span data-ttu-id="1f39b-113">`!` 演算子は、そのオペランドの論理否定を計算します。</span><span class="sxs-lookup"><span data-stu-id="1f39b-113">The `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="1f39b-114">つまり、オペランドが `false` と評価された場合は `true`、オペランドが `true` と評価された場合は `false` が生成されます。</span><span class="sxs-lookup"><span data-stu-id="1f39b-114">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Negation)]

## <a name="logical-and-operator-"></a> <span data-ttu-id="1f39b-115">論理 AND 演算子 &amp;</span><span class="sxs-lookup"><span data-stu-id="1f39b-115">Logical AND operator &amp;</span></span>

<span data-ttu-id="1f39b-116">`&` 演算子がそのオペランドの論理 AND を計算します。</span><span class="sxs-lookup"><span data-stu-id="1f39b-116">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="1f39b-117">`x` と `y` の両方が `true` と評価されれば、`x & y` の結果は `true` です。</span><span class="sxs-lookup"><span data-stu-id="1f39b-117">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="1f39b-118">それ以外の場合、結果は `false` です。</span><span class="sxs-lookup"><span data-stu-id="1f39b-118">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="1f39b-119">`&` 演算子は、左側のオペランドが `false` と評価されても両方のオペランドを評価するため、結果は右側のオペランドの値に関係なく、必ず `false` になります。</span><span class="sxs-lookup"><span data-stu-id="1f39b-119">The `&` operator evaluates both operands even if the left-hand operand evaluates to `false`, so that the result must be `false` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="1f39b-120">次の例では、`&` 演算子の右側のオペランドはメソッド呼び出しで、左側のオペランドの値に関係なく実行されます。</span><span class="sxs-lookup"><span data-stu-id="1f39b-120">In the following example, the right-hand operand of the `&` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#And)]

<span data-ttu-id="1f39b-121">[条件付き論理 AND 演算子](#conditional-logical-and-operator-) `&&` もそのオペランドの論理 AND を計算しますが、左側のオペランドが `false` と評価された場合、右側のオペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="1f39b-121">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `false`.</span></span>

<span data-ttu-id="1f39b-122">整数型のオペランドの場合、`&` 演算子は、そのオペランドの[ビットごとの論理 AND](bitwise-and-shift-operators.md#logical-and-operator-) を計算します。</span><span class="sxs-lookup"><span data-stu-id="1f39b-122">For the operands of the integral types, the `&` operator computes the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="1f39b-123">単項 `&` 演算子は[アドレス演算子](pointer-related-operators.md#address-of-operator-)です。</span><span class="sxs-lookup"><span data-stu-id="1f39b-123">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="1f39b-124">論理排他的 OR 演算子: ^</span><span class="sxs-lookup"><span data-stu-id="1f39b-124">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="1f39b-125">`^` 演算子は、そのオペランドの論理排他的 OR (論理 XOR とも呼ばれます) を計算します。</span><span class="sxs-lookup"><span data-stu-id="1f39b-125">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="1f39b-126">`x` が `true` に評価され、`y` が `false` に評価された場合、または `x` が `false` に評価され、`y` が `true` に評価された場合、`x ^ y` の結果は `true` です。</span><span class="sxs-lookup"><span data-stu-id="1f39b-126">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="1f39b-127">それ以外の場合、結果は `false` です。</span><span class="sxs-lookup"><span data-stu-id="1f39b-127">Otherwise, the result is `false`.</span></span> <span data-ttu-id="1f39b-128">つまり、`bool` オペランドの場合、`^` 演算子は[非等値演算子](equality-operators.md#inequality-operator-) `!=` と同じ結果を計算します。</span><span class="sxs-lookup"><span data-stu-id="1f39b-128">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Xor)]

<span data-ttu-id="1f39b-129">整数型のオペランドの場合、`^` 演算子は、そのオペランドの[ビットごとの論理排他的 OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) を計算します。</span><span class="sxs-lookup"><span data-stu-id="1f39b-129">For the operands of the integral types, the `^` operator computes the [bitwise logical exclusive OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="1f39b-130">論理 OR 演算子 |</span><span class="sxs-lookup"><span data-stu-id="1f39b-130">Logical OR operator |</span></span>

<span data-ttu-id="1f39b-131">`|` 演算子がそのオペランドの論理 OR を計算します。</span><span class="sxs-lookup"><span data-stu-id="1f39b-131">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="1f39b-132">`x` または `y` のどちらかが `true` と評価された場合、`x | y` の結果は `true` になります。</span><span class="sxs-lookup"><span data-stu-id="1f39b-132">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="1f39b-133">それ以外の場合、結果は `false` です。</span><span class="sxs-lookup"><span data-stu-id="1f39b-133">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="1f39b-134">`|` 演算子は、左側のオペランドが `true` と評価されても両方のオペランドを評価するため、結果は右側のオペランドの値に関係なく、必ず `true` になります。</span><span class="sxs-lookup"><span data-stu-id="1f39b-134">The `|` operator evaluates both operands even if the left-hand operand evaluates to `true`, so that the result must be `true` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="1f39b-135">次の例では、`|` 演算子の右側のオペランドはメソッド呼び出しで、左側のオペランドの値に関係なく実行されます。</span><span class="sxs-lookup"><span data-stu-id="1f39b-135">In the following example, the right-hand operand of the `|` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Or)]

<span data-ttu-id="1f39b-136">[条件付き論理 OR 演算子](#conditional-logical-or-operator-) `||` もそのオペランドの論理 OR を計算しますが、左側のオペランドが `true` と評価された場合、右側のオペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="1f39b-136">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `true`.</span></span>

<span data-ttu-id="1f39b-137">整数型のオペランドの場合、`|` 演算子は、そのオペランドの[ビットごとの論理 OR](bitwise-and-shift-operators.md#logical-or-operator-) を計算します。</span><span class="sxs-lookup"><span data-stu-id="1f39b-137">For the operands of the integral types, the `|` operator computes the [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="conditional-logical-and-operator-"></a> <span data-ttu-id="1f39b-138">条件付き論理 AND 演算子 &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="1f39b-138">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="1f39b-139">条件論理 AND 演算子 `&&` は、"短絡" 論理 AND 演算子とも呼ばれ、そのオペランドの論理 AND を計算します。</span><span class="sxs-lookup"><span data-stu-id="1f39b-139">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="1f39b-140">`x` と `y` の両方が `true` と評価されれば、`x && y` の結果は `true` です。</span><span class="sxs-lookup"><span data-stu-id="1f39b-140">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="1f39b-141">それ以外の場合、結果は `false` です。</span><span class="sxs-lookup"><span data-stu-id="1f39b-141">Otherwise, the result is `false`.</span></span> <span data-ttu-id="1f39b-142">`x` が `false` に評価される場合、`y` は評価されません。</span><span class="sxs-lookup"><span data-stu-id="1f39b-142">If `x` evaluates to `false`, `y` is not evaluated.</span></span>

<span data-ttu-id="1f39b-143">次の例では、`&&` 演算子の右側のオペランドはメソッド呼び出しで、左側のオペランドが `false` と評価されると実行されません。</span><span class="sxs-lookup"><span data-stu-id="1f39b-143">In the following example, the right-hand operand of the `&&` operator is a method call, which isn't performed if the left-hand operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="1f39b-144">[論理 AND 演算子](#logical-and-operator-) `&` もそのオペランドの論理 AND を計算しますが、常に両方のオペランドを評価します。</span><span class="sxs-lookup"><span data-stu-id="1f39b-144">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="1f39b-145">条件付き論理 OR 演算子 ||</span><span class="sxs-lookup"><span data-stu-id="1f39b-145">Conditional logical OR operator ||</span></span>

<span data-ttu-id="1f39b-146">条件論理 OR 演算子 `||` は、"短絡" 論理 OR 演算子とも呼ばれ、そのオペランドの論理 OR を計算します。</span><span class="sxs-lookup"><span data-stu-id="1f39b-146">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="1f39b-147">`x` または `y` のどちらかが `true` と評価された場合、`x || y` の結果は `true` になります。</span><span class="sxs-lookup"><span data-stu-id="1f39b-147">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="1f39b-148">それ以外の場合、結果は `false` です。</span><span class="sxs-lookup"><span data-stu-id="1f39b-148">Otherwise, the result is `false`.</span></span> <span data-ttu-id="1f39b-149">`x` が `true` に評価される場合、`y` は評価されません。</span><span class="sxs-lookup"><span data-stu-id="1f39b-149">If `x` evaluates to `true`, `y` is not evaluated.</span></span>

<span data-ttu-id="1f39b-150">次の例では、`||` 演算子の右側のオペランドはメソッド呼び出しで、左側のオペランドが `true` と評価されると実行されません。</span><span class="sxs-lookup"><span data-stu-id="1f39b-150">In the following example, the right-hand operand of the `||` operator is a method call, which isn't performed if the left-hand operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="1f39b-151">[論理 OR 演算子](#logical-or-operator-) `|` もそのオペランドの論理 OR を計算しますが、常に両方のオペランドを評価します。</span><span class="sxs-lookup"><span data-stu-id="1f39b-151">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="1f39b-152">null 許容ブール論理演算子</span><span class="sxs-lookup"><span data-stu-id="1f39b-152">Nullable Boolean logical operators</span></span>

<span data-ttu-id="1f39b-153">`bool?` オペランドの場合、`&` 演算子と `|` 演算子は 3 値ロジックをサポートします。</span><span class="sxs-lookup"><span data-stu-id="1f39b-153">For the `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="1f39b-154">次の表に、これらの演算子のセマンティクスが定義されています。</span><span class="sxs-lookup"><span data-stu-id="1f39b-154">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="1f39b-155">x</span><span class="sxs-lookup"><span data-stu-id="1f39b-155">x</span></span>|<span data-ttu-id="1f39b-156">Y</span><span class="sxs-lookup"><span data-stu-id="1f39b-156">y</span></span>|<span data-ttu-id="1f39b-157">x&y</span><span class="sxs-lookup"><span data-stu-id="1f39b-157">x&y</span></span>|<span data-ttu-id="1f39b-158">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="1f39b-158">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="1f39b-159">true</span><span class="sxs-lookup"><span data-stu-id="1f39b-159">true</span></span>|<span data-ttu-id="1f39b-160">true</span><span class="sxs-lookup"><span data-stu-id="1f39b-160">true</span></span>|<span data-ttu-id="1f39b-161">true</span><span class="sxs-lookup"><span data-stu-id="1f39b-161">true</span></span>|<span data-ttu-id="1f39b-162">true</span><span class="sxs-lookup"><span data-stu-id="1f39b-162">true</span></span>|  
|<span data-ttu-id="1f39b-163">TRUE</span><span class="sxs-lookup"><span data-stu-id="1f39b-163">true</span></span>|<span data-ttu-id="1f39b-164">False</span><span class="sxs-lookup"><span data-stu-id="1f39b-164">false</span></span>|<span data-ttu-id="1f39b-165">false</span><span class="sxs-lookup"><span data-stu-id="1f39b-165">false</span></span>|<span data-ttu-id="1f39b-166">true</span><span class="sxs-lookup"><span data-stu-id="1f39b-166">true</span></span>|  
|<span data-ttu-id="1f39b-167">true</span><span class="sxs-lookup"><span data-stu-id="1f39b-167">true</span></span>|<span data-ttu-id="1f39b-168">null</span><span class="sxs-lookup"><span data-stu-id="1f39b-168">null</span></span>|<span data-ttu-id="1f39b-169">null</span><span class="sxs-lookup"><span data-stu-id="1f39b-169">null</span></span>|<span data-ttu-id="1f39b-170">true</span><span class="sxs-lookup"><span data-stu-id="1f39b-170">true</span></span>|  
|<span data-ttu-id="1f39b-171">False</span><span class="sxs-lookup"><span data-stu-id="1f39b-171">false</span></span>|<span data-ttu-id="1f39b-172">true</span><span class="sxs-lookup"><span data-stu-id="1f39b-172">true</span></span>|<span data-ttu-id="1f39b-173">False</span><span class="sxs-lookup"><span data-stu-id="1f39b-173">false</span></span>|<span data-ttu-id="1f39b-174">true</span><span class="sxs-lookup"><span data-stu-id="1f39b-174">true</span></span>|  
|<span data-ttu-id="1f39b-175">False</span><span class="sxs-lookup"><span data-stu-id="1f39b-175">false</span></span>|<span data-ttu-id="1f39b-176">False</span><span class="sxs-lookup"><span data-stu-id="1f39b-176">false</span></span>|<span data-ttu-id="1f39b-177">False</span><span class="sxs-lookup"><span data-stu-id="1f39b-177">false</span></span>|<span data-ttu-id="1f39b-178">False</span><span class="sxs-lookup"><span data-stu-id="1f39b-178">false</span></span>|  
|<span data-ttu-id="1f39b-179">False</span><span class="sxs-lookup"><span data-stu-id="1f39b-179">false</span></span>|<span data-ttu-id="1f39b-180">null</span><span class="sxs-lookup"><span data-stu-id="1f39b-180">null</span></span>|<span data-ttu-id="1f39b-181">False</span><span class="sxs-lookup"><span data-stu-id="1f39b-181">false</span></span>|<span data-ttu-id="1f39b-182">null</span><span class="sxs-lookup"><span data-stu-id="1f39b-182">null</span></span>|  
|<span data-ttu-id="1f39b-183">null</span><span class="sxs-lookup"><span data-stu-id="1f39b-183">null</span></span>|<span data-ttu-id="1f39b-184">true</span><span class="sxs-lookup"><span data-stu-id="1f39b-184">true</span></span>|<span data-ttu-id="1f39b-185">null</span><span class="sxs-lookup"><span data-stu-id="1f39b-185">null</span></span>|<span data-ttu-id="1f39b-186">true</span><span class="sxs-lookup"><span data-stu-id="1f39b-186">true</span></span>|  
|<span data-ttu-id="1f39b-187">null</span><span class="sxs-lookup"><span data-stu-id="1f39b-187">null</span></span>|<span data-ttu-id="1f39b-188">False</span><span class="sxs-lookup"><span data-stu-id="1f39b-188">false</span></span>|<span data-ttu-id="1f39b-189">False</span><span class="sxs-lookup"><span data-stu-id="1f39b-189">false</span></span>|<span data-ttu-id="1f39b-190">null</span><span class="sxs-lookup"><span data-stu-id="1f39b-190">null</span></span>|  
|<span data-ttu-id="1f39b-191">null</span><span class="sxs-lookup"><span data-stu-id="1f39b-191">null</span></span>|<span data-ttu-id="1f39b-192">null</span><span class="sxs-lookup"><span data-stu-id="1f39b-192">null</span></span>|<span data-ttu-id="1f39b-193">null</span><span class="sxs-lookup"><span data-stu-id="1f39b-193">null</span></span>|<span data-ttu-id="1f39b-194">null</span><span class="sxs-lookup"><span data-stu-id="1f39b-194">null</span></span>|  

<span data-ttu-id="1f39b-195">これらの演算子の動作は、null 許容値型の一般的な演算子の動作とは異なります。</span><span class="sxs-lookup"><span data-stu-id="1f39b-195">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="1f39b-196">通常、値型のオペランドに定義されている演算子も、対応する null 値型のオペランドと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="1f39b-196">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="1f39b-197">このような演算子は、そのオペランドのいずれかが `null` の場合に `null` を生成します。</span><span class="sxs-lookup"><span data-stu-id="1f39b-197">Such an operator produces `null` if any of its operands is `null`.</span></span> <span data-ttu-id="1f39b-198">ただし、`&` および `|` 演算子は、オペランドの 1 つが `null` の場合でも、null 以外の値を生成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1f39b-198">However, the `&` and `|` operators can produce non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="1f39b-199">null 許容値型の演算子の動作については、「[Null 許容型の使用](../../programming-guide/nullable-types/using-nullable-types.md)」記事の「[演算子](../../programming-guide/nullable-types/using-nullable-types.md#operators)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f39b-199">For more information about the operator behavior with nullable value types, see the [Operators](../../programming-guide/nullable-types/using-nullable-types.md#operators) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

<span data-ttu-id="1f39b-200">次の例に示すように、`!` 演算子と `^` 演算子を `bool?` オペランドと共に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="1f39b-200">You can also use the `!` and `^` operators with the `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="1f39b-201">条件付き論理演算子 `&&` と `||` は `bool?` オペランドをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="1f39b-201">The conditional logical operators `&&` and `||` don't support the `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="1f39b-202">複合代入。</span><span class="sxs-lookup"><span data-stu-id="1f39b-202">Compound assignment</span></span>

<span data-ttu-id="1f39b-203">2 項演算子 `op` の場合、フォームの複合代入式</span><span class="sxs-lookup"><span data-stu-id="1f39b-203">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="1f39b-204">上記の式は、次の式と同じです。</span><span class="sxs-lookup"><span data-stu-id="1f39b-204">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="1f39b-205">ただし、`x` が評価されるのは 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="1f39b-205">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="1f39b-206">次の例に示すように、`&`、`|`、および `^` 演算子は複合代入をサポートします。</span><span class="sxs-lookup"><span data-stu-id="1f39b-206">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#CompoundAssignment)]

<span data-ttu-id="1f39b-207">条件付き論理演算子 `&&` と `||` は複合代入をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="1f39b-207">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="1f39b-208">演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="1f39b-208">Operator precedence</span></span>

<span data-ttu-id="1f39b-209">次の論理演算子の一覧は、優先度が高い順に並べられています。</span><span class="sxs-lookup"><span data-stu-id="1f39b-209">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="1f39b-210">論理否定演算子 `!`</span><span class="sxs-lookup"><span data-stu-id="1f39b-210">Logical negation operator `!`</span></span>
- <span data-ttu-id="1f39b-211">論理 AND 演算子 `&`</span><span class="sxs-lookup"><span data-stu-id="1f39b-211">Logical AND operator `&`</span></span>
- <span data-ttu-id="1f39b-212">論理排他的 OR 演算子 `^`</span><span class="sxs-lookup"><span data-stu-id="1f39b-212">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="1f39b-213">論理 OR 演算子 `|`</span><span class="sxs-lookup"><span data-stu-id="1f39b-213">Logical OR operator `|`</span></span>
- <span data-ttu-id="1f39b-214">条件付き論理 AND 演算子 `&&`</span><span class="sxs-lookup"><span data-stu-id="1f39b-214">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="1f39b-215">条件付き論理 OR 演算子 `||`</span><span class="sxs-lookup"><span data-stu-id="1f39b-215">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="1f39b-216">演算子の優先順位によって定められた評価の順序を変更するには、かっこ `()` を使用します。</span><span class="sxs-lookup"><span data-stu-id="1f39b-216">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Precedence)]

<span data-ttu-id="1f39b-217">優先度順に並べられた C# 演算子の完全な一覧については、「[C# 演算子](index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f39b-217">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="1f39b-218">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="1f39b-218">Operator overloadability</span></span>

<span data-ttu-id="1f39b-219">ユーザー定義型は、`!`、`&`、`|`、および `^` 演算子を[オーバーロード](../keywords/operator.md)できます。</span><span class="sxs-lookup"><span data-stu-id="1f39b-219">A user-defined type can [overload](../keywords/operator.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="1f39b-220">2 項演算子をオーバーロードすると、対応する複合代入演算子も暗黙的にオーバーロードされます。</span><span class="sxs-lookup"><span data-stu-id="1f39b-220">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="1f39b-221">ユーザー定義型は、複合代入演算子を明示的にオーバーロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1f39b-221">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="1f39b-222">ユーザー定義型は条件付き論理演算子 `&&` と `||` をオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="1f39b-222">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="1f39b-223">ただし、ユーザー定義型が [true および false 演算子](true-false-operators.md)と `&` または `|` 演算子を特定の方法でオーバーロードしている場合は、その型のオペランドに対してそれぞれ `&&` または `||` 演算の評価が可能になります。</span><span class="sxs-lookup"><span data-stu-id="1f39b-223">However, if a user-defined type overloads the [true and false operators](true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="1f39b-224">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の[ユーザー定義型条件論理演算子](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f39b-224">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1f39b-225">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="1f39b-225">C# language specification</span></span>

<span data-ttu-id="1f39b-226">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f39b-226">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="1f39b-227">論理否定演算子</span><span class="sxs-lookup"><span data-stu-id="1f39b-227">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="1f39b-228">論理演算子</span><span class="sxs-lookup"><span data-stu-id="1f39b-228">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="1f39b-229">条件論理演算子</span><span class="sxs-lookup"><span data-stu-id="1f39b-229">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [<span data-ttu-id="1f39b-230">複合代入</span><span class="sxs-lookup"><span data-stu-id="1f39b-230">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a><span data-ttu-id="1f39b-231">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f39b-231">See also</span></span>

- [<span data-ttu-id="1f39b-232">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="1f39b-232">C# reference</span></span>](../index.md)
- [<span data-ttu-id="1f39b-233">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="1f39b-233">C# operators</span></span>](index.md)
- [<span data-ttu-id="1f39b-234">ビットごとの演算子とシフト演算子</span><span class="sxs-lookup"><span data-stu-id="1f39b-234">Bitwise and shift operators</span></span>](bitwise-and-shift-operators.md)
