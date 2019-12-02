---
title: ブール論理演算子 - C# リファレンス
description: ブール オペランドを使用した論理否定演算、論理積演算 (AND)、および包含的および排他的論理和演算 (OR) を実行する C# 演算子について説明します。
ms.date: 09/27/2019
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
ms.openlocfilehash: e4efb283c835a703ec64b6ec5995b821c995dc60
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552491"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="e52be-103">ブール論理演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="e52be-103">Boolean logical operators (C# reference)</span></span>

<span data-ttu-id="e52be-104">次の演算子は、[bool](../builtin-types/bool.md) オペランドを使用して論理演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="e52be-104">The following operators perform logical operations with [bool](../builtin-types/bool.md) operands:</span></span>

- <span data-ttu-id="e52be-105">単項 [`!` (論理否定)](#logical-negation-operator-) 演算子。</span><span class="sxs-lookup"><span data-stu-id="e52be-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="e52be-106">二項 [`&` (論理 AND)](#logical-and-operator-)、[`|` (論理 OR)](#logical-or-operator-)、および [`^` (論理排他的 OR)](#logical-exclusive-or-operator-) 演算子。</span><span class="sxs-lookup"><span data-stu-id="e52be-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="e52be-107">これらの演算子は常に両方のオペランドを評価します。</span><span class="sxs-lookup"><span data-stu-id="e52be-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="e52be-108">二項 [`&&` (条件付き論理 AND)](#conditional-logical-and-operator-) および [`||` (条件付き論理 OR)](#conditional-logical-or-operator-) 演算子。</span><span class="sxs-lookup"><span data-stu-id="e52be-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="e52be-109">これらの演算子では、必要な場合にのみ右側のオペランドが評価されます。</span><span class="sxs-lookup"><span data-stu-id="e52be-109">Those operators evaluate the right-hand operand only if it's necessary.</span></span>

<span data-ttu-id="e52be-110">[整数の数値型](../builtin-types/integral-numeric-types.md)のオペランドの場合、`&`、`|`、`^` 演算子でビットごとの論理演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="e52be-110">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span> <span data-ttu-id="e52be-111">詳しくは、「[ビットごとの演算子とシフト演算子](bitwise-and-shift-operators.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e52be-111">For more information, see [Bitwise and shift operators](bitwise-and-shift-operators.md).</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="e52be-112">論理否定演算子 !</span><span class="sxs-lookup"><span data-stu-id="e52be-112">Logical negation operator !</span></span>

<span data-ttu-id="e52be-113">単項の接頭辞 `!` 演算子では、そのオペランドの論理否定が計算されます。</span><span class="sxs-lookup"><span data-stu-id="e52be-113">The unary prefix `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="e52be-114">つまり、オペランドが `false` と評価された場合は `true`、オペランドが `true` と評価された場合は `false` が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e52be-114">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Negation)]

<span data-ttu-id="e52be-115">C# 8.0 以降では、単項後置の `!` 演算子は [null 免除演算子](null-forgiving.md)です。</span><span class="sxs-lookup"><span data-stu-id="e52be-115">Beginning with C# 8.0, the unary postfix `!` operator is the [null-forgiving operator](null-forgiving.md).</span></span>

## <a name="logical-and-operator-"></a> <span data-ttu-id="e52be-116">論理 AND 演算子 &amp;</span><span class="sxs-lookup"><span data-stu-id="e52be-116">Logical AND operator &amp;</span></span>

<span data-ttu-id="e52be-117">`&` 演算子がそのオペランドの論理 AND を計算します。</span><span class="sxs-lookup"><span data-stu-id="e52be-117">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="e52be-118">`x` と `y` の両方が `true` と評価されれば、`x & y` の結果は `true` です。</span><span class="sxs-lookup"><span data-stu-id="e52be-118">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="e52be-119">それ以外の場合、結果は `false` です。</span><span class="sxs-lookup"><span data-stu-id="e52be-119">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="e52be-120">`&` 演算子は、左側のオペランドが `false` と評価されても両方のオペランドを評価するため、操作結果は右側のオペランドの値に関係なく、`false` になります。</span><span class="sxs-lookup"><span data-stu-id="e52be-120">The `&` operator evaluates both operands even if the left-hand operand evaluates to `false`, so that the operation result is `false` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="e52be-121">次の例では、`&` 演算子の右側のオペランドはメソッド呼び出しで、左側のオペランドの値に関係なく実行されます。</span><span class="sxs-lookup"><span data-stu-id="e52be-121">In the following example, the right-hand operand of the `&` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#And)]

<span data-ttu-id="e52be-122">[条件付き論理 AND 演算子](#conditional-logical-and-operator-) `&&` もそのオペランドの論理 AND を計算しますが、左側のオペランドが `false` と評価された場合、右側のオペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="e52be-122">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `false`.</span></span>

<span data-ttu-id="e52be-123">[整数の数値型](../builtin-types/integral-numeric-types.md)のオペランドの場合、`&` 演算子でそのオペランドの[ビットごとの論理 AND](bitwise-and-shift-operators.md#logical-and-operator-) を計算します。</span><span class="sxs-lookup"><span data-stu-id="e52be-123">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `&` operator computes the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="e52be-124">単項 `&` 演算子は[アドレス演算子](pointer-related-operators.md#address-of-operator-)です。</span><span class="sxs-lookup"><span data-stu-id="e52be-124">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="e52be-125">論理排他的 OR 演算子: ^</span><span class="sxs-lookup"><span data-stu-id="e52be-125">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="e52be-126">`^` 演算子は、そのオペランドの論理排他的 OR (論理 XOR とも呼ばれます) を計算します。</span><span class="sxs-lookup"><span data-stu-id="e52be-126">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="e52be-127">`x` が `true` に評価され、`y` が `false` に評価された場合、または `x` が `false` に評価され、`y` が `true` に評価された場合、`x ^ y` の結果は `true` です。</span><span class="sxs-lookup"><span data-stu-id="e52be-127">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="e52be-128">それ以外の場合、結果は `false` です。</span><span class="sxs-lookup"><span data-stu-id="e52be-128">Otherwise, the result is `false`.</span></span> <span data-ttu-id="e52be-129">つまり、`bool` オペランドの場合、`^` 演算子は[非等値演算子](equality-operators.md#inequality-operator-) `!=` と同じ結果を計算します。</span><span class="sxs-lookup"><span data-stu-id="e52be-129">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Xor)]

<span data-ttu-id="e52be-130">[整数の数値型](../builtin-types/integral-numeric-types.md)のオペランドの場合、`^` 演算子でそのオペランドの[ビットごとの論理排他的 OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) を計算します。</span><span class="sxs-lookup"><span data-stu-id="e52be-130">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `^` operator computes the [bitwise logical exclusive OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="e52be-131">論理 OR 演算子 |</span><span class="sxs-lookup"><span data-stu-id="e52be-131">Logical OR operator |</span></span>

<span data-ttu-id="e52be-132">`|` 演算子がそのオペランドの論理 OR を計算します。</span><span class="sxs-lookup"><span data-stu-id="e52be-132">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="e52be-133">`x` または `y` のどちらかが `true` と評価された場合、`x | y` の結果は `true` になります。</span><span class="sxs-lookup"><span data-stu-id="e52be-133">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="e52be-134">それ以外の場合、結果は `false` です。</span><span class="sxs-lookup"><span data-stu-id="e52be-134">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="e52be-135">`|` 演算子は、左側のオペランドが `true` と評価されても両方のオペランドを評価するため、操作結果は右側のオペランドの値に関係なく、`true` になります。</span><span class="sxs-lookup"><span data-stu-id="e52be-135">The `|` operator evaluates both operands even if the left-hand operand evaluates to `true`, so that the operation result is `true` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="e52be-136">次の例では、`|` 演算子の右側のオペランドはメソッド呼び出しで、左側のオペランドの値に関係なく実行されます。</span><span class="sxs-lookup"><span data-stu-id="e52be-136">In the following example, the right-hand operand of the `|` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Or)]

<span data-ttu-id="e52be-137">[条件付き論理 OR 演算子](#conditional-logical-or-operator-) `||` もそのオペランドの論理 OR を計算しますが、左側のオペランドが `true` と評価された場合、右側のオペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="e52be-137">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `true`.</span></span>

<span data-ttu-id="e52be-138">[整数の数値型](../builtin-types/integral-numeric-types.md)のオペランドの場合、`|` 演算子でそのオペランドの[ビットごとの論理 OR](bitwise-and-shift-operators.md#logical-or-operator-) を計算します。</span><span class="sxs-lookup"><span data-stu-id="e52be-138">For operands of the [integral numeric types](../builtin-types/integral-numeric-types.md), the `|` operator computes the [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="conditional-logical-and-operator-"></a> <span data-ttu-id="e52be-139">条件付き論理 AND 演算子 &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="e52be-139">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="e52be-140">条件論理 AND 演算子 `&&` は、"短絡" 論理 AND 演算子とも呼ばれ、そのオペランドの論理 AND を計算します。</span><span class="sxs-lookup"><span data-stu-id="e52be-140">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="e52be-141">`x` と `y` の両方が `true` と評価されれば、`x && y` の結果は `true` です。</span><span class="sxs-lookup"><span data-stu-id="e52be-141">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="e52be-142">それ以外の場合、結果は `false` です。</span><span class="sxs-lookup"><span data-stu-id="e52be-142">Otherwise, the result is `false`.</span></span> <span data-ttu-id="e52be-143">`x` が `false` に評価される場合、`y` は評価されません。</span><span class="sxs-lookup"><span data-stu-id="e52be-143">If `x` evaluates to `false`, `y` is not evaluated.</span></span>

<span data-ttu-id="e52be-144">次の例では、`&&` 演算子の右側のオペランドはメソッド呼び出しで、左側のオペランドが `false` と評価されると実行されません。</span><span class="sxs-lookup"><span data-stu-id="e52be-144">In the following example, the right-hand operand of the `&&` operator is a method call, which isn't performed if the left-hand operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="e52be-145">[論理 AND 演算子](#logical-and-operator-) `&` もそのオペランドの論理 AND を計算しますが、常に両方のオペランドを評価します。</span><span class="sxs-lookup"><span data-stu-id="e52be-145">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="e52be-146">条件付き論理 OR 演算子 ||</span><span class="sxs-lookup"><span data-stu-id="e52be-146">Conditional logical OR operator ||</span></span>

<span data-ttu-id="e52be-147">条件論理 OR 演算子 `||` は、"短絡" 論理 OR 演算子とも呼ばれ、そのオペランドの論理 OR を計算します。</span><span class="sxs-lookup"><span data-stu-id="e52be-147">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="e52be-148">`x` または `y` のどちらかが `true` と評価された場合、`x || y` の結果は `true` になります。</span><span class="sxs-lookup"><span data-stu-id="e52be-148">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="e52be-149">それ以外の場合、結果は `false` です。</span><span class="sxs-lookup"><span data-stu-id="e52be-149">Otherwise, the result is `false`.</span></span> <span data-ttu-id="e52be-150">`x` が `true` に評価される場合、`y` は評価されません。</span><span class="sxs-lookup"><span data-stu-id="e52be-150">If `x` evaluates to `true`, `y` is not evaluated.</span></span>

<span data-ttu-id="e52be-151">次の例では、`||` 演算子の右側のオペランドはメソッド呼び出しで、左側のオペランドが `true` と評価されると実行されません。</span><span class="sxs-lookup"><span data-stu-id="e52be-151">In the following example, the right-hand operand of the `||` operator is a method call, which isn't performed if the left-hand operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="e52be-152">[論理 OR 演算子](#logical-or-operator-) `|` もそのオペランドの論理 OR を計算しますが、常に両方のオペランドを評価します。</span><span class="sxs-lookup"><span data-stu-id="e52be-152">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="e52be-153">null 許容ブール論理演算子</span><span class="sxs-lookup"><span data-stu-id="e52be-153">Nullable Boolean logical operators</span></span>

<span data-ttu-id="e52be-154">`bool?` オペランドの場合、`&` 演算子と `|` 演算子では 3 値ロジックをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e52be-154">For `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="e52be-155">次の表に、これらの演算子のセマンティクスが定義されています。</span><span class="sxs-lookup"><span data-stu-id="e52be-155">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="e52be-156">x</span><span class="sxs-lookup"><span data-stu-id="e52be-156">x</span></span>|<span data-ttu-id="e52be-157">Y</span><span class="sxs-lookup"><span data-stu-id="e52be-157">y</span></span>|<span data-ttu-id="e52be-158">x&y</span><span class="sxs-lookup"><span data-stu-id="e52be-158">x&y</span></span>|<span data-ttu-id="e52be-159">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="e52be-159">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="e52be-160">true</span><span class="sxs-lookup"><span data-stu-id="e52be-160">true</span></span>|<span data-ttu-id="e52be-161">true</span><span class="sxs-lookup"><span data-stu-id="e52be-161">true</span></span>|<span data-ttu-id="e52be-162">true</span><span class="sxs-lookup"><span data-stu-id="e52be-162">true</span></span>|<span data-ttu-id="e52be-163">true</span><span class="sxs-lookup"><span data-stu-id="e52be-163">true</span></span>|  
|<span data-ttu-id="e52be-164">TRUE</span><span class="sxs-lookup"><span data-stu-id="e52be-164">true</span></span>|<span data-ttu-id="e52be-165">False</span><span class="sxs-lookup"><span data-stu-id="e52be-165">false</span></span>|<span data-ttu-id="e52be-166">false</span><span class="sxs-lookup"><span data-stu-id="e52be-166">false</span></span>|<span data-ttu-id="e52be-167">true</span><span class="sxs-lookup"><span data-stu-id="e52be-167">true</span></span>|  
|<span data-ttu-id="e52be-168">true</span><span class="sxs-lookup"><span data-stu-id="e52be-168">true</span></span>|<span data-ttu-id="e52be-169">null</span><span class="sxs-lookup"><span data-stu-id="e52be-169">null</span></span>|<span data-ttu-id="e52be-170">null</span><span class="sxs-lookup"><span data-stu-id="e52be-170">null</span></span>|<span data-ttu-id="e52be-171">true</span><span class="sxs-lookup"><span data-stu-id="e52be-171">true</span></span>|  
|<span data-ttu-id="e52be-172">False</span><span class="sxs-lookup"><span data-stu-id="e52be-172">false</span></span>|<span data-ttu-id="e52be-173">true</span><span class="sxs-lookup"><span data-stu-id="e52be-173">true</span></span>|<span data-ttu-id="e52be-174">False</span><span class="sxs-lookup"><span data-stu-id="e52be-174">false</span></span>|<span data-ttu-id="e52be-175">true</span><span class="sxs-lookup"><span data-stu-id="e52be-175">true</span></span>|  
|<span data-ttu-id="e52be-176">False</span><span class="sxs-lookup"><span data-stu-id="e52be-176">false</span></span>|<span data-ttu-id="e52be-177">False</span><span class="sxs-lookup"><span data-stu-id="e52be-177">false</span></span>|<span data-ttu-id="e52be-178">False</span><span class="sxs-lookup"><span data-stu-id="e52be-178">false</span></span>|<span data-ttu-id="e52be-179">False</span><span class="sxs-lookup"><span data-stu-id="e52be-179">false</span></span>|  
|<span data-ttu-id="e52be-180">False</span><span class="sxs-lookup"><span data-stu-id="e52be-180">false</span></span>|<span data-ttu-id="e52be-181">null</span><span class="sxs-lookup"><span data-stu-id="e52be-181">null</span></span>|<span data-ttu-id="e52be-182">False</span><span class="sxs-lookup"><span data-stu-id="e52be-182">false</span></span>|<span data-ttu-id="e52be-183">null</span><span class="sxs-lookup"><span data-stu-id="e52be-183">null</span></span>|  
|<span data-ttu-id="e52be-184">null</span><span class="sxs-lookup"><span data-stu-id="e52be-184">null</span></span>|<span data-ttu-id="e52be-185">true</span><span class="sxs-lookup"><span data-stu-id="e52be-185">true</span></span>|<span data-ttu-id="e52be-186">null</span><span class="sxs-lookup"><span data-stu-id="e52be-186">null</span></span>|<span data-ttu-id="e52be-187">true</span><span class="sxs-lookup"><span data-stu-id="e52be-187">true</span></span>|  
|<span data-ttu-id="e52be-188">null</span><span class="sxs-lookup"><span data-stu-id="e52be-188">null</span></span>|<span data-ttu-id="e52be-189">False</span><span class="sxs-lookup"><span data-stu-id="e52be-189">false</span></span>|<span data-ttu-id="e52be-190">False</span><span class="sxs-lookup"><span data-stu-id="e52be-190">false</span></span>|<span data-ttu-id="e52be-191">null</span><span class="sxs-lookup"><span data-stu-id="e52be-191">null</span></span>|  
|<span data-ttu-id="e52be-192">null</span><span class="sxs-lookup"><span data-stu-id="e52be-192">null</span></span>|<span data-ttu-id="e52be-193">null</span><span class="sxs-lookup"><span data-stu-id="e52be-193">null</span></span>|<span data-ttu-id="e52be-194">null</span><span class="sxs-lookup"><span data-stu-id="e52be-194">null</span></span>|<span data-ttu-id="e52be-195">null</span><span class="sxs-lookup"><span data-stu-id="e52be-195">null</span></span>|  

<span data-ttu-id="e52be-196">これらの演算子の動作は、null 許容値型の一般的な演算子の動作とは異なります。</span><span class="sxs-lookup"><span data-stu-id="e52be-196">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="e52be-197">通常、値型のオペランドに定義されている演算子も、対応する null 値型のオペランドと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="e52be-197">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="e52be-198">このような演算子では、そのオペランドのいずれかが `null` として評価される場合に `null` を生成します。</span><span class="sxs-lookup"><span data-stu-id="e52be-198">Such an operator produces `null` if any of its operands evaluates to `null`.</span></span> <span data-ttu-id="e52be-199">しかし、`&` および `|` 演算子は、オペランドの 1 つが `null` として評価される場合でも、null 以外の値を生成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e52be-199">However, the `&` and `|` operators can produce non-null even if one of the operands evaluates to `null`.</span></span> <span data-ttu-id="e52be-200">null 許容値型の演算子の動作については、[null 許容値型](../builtin-types/nullable-value-types.md)に関する記事の「[リフト演算子](../builtin-types/nullable-value-types.md#lifted-operators)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e52be-200">For more information about the operator behavior with nullable value types, see the [Lifted operators](../builtin-types/nullable-value-types.md#lifted-operators) section of the [Nullable value types](../builtin-types/nullable-value-types.md) article.</span></span>

<span data-ttu-id="e52be-201">次の例に示すように、`!` 演算子と `^` 演算子を `bool?` オペランドと共に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e52be-201">You can also use the `!` and `^` operators with `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="e52be-202">条件付き論理演算子 `&&` と `||` では、`bool?` オペランドをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="e52be-202">The conditional logical operators `&&` and `||` don't support `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="e52be-203">複合代入。</span><span class="sxs-lookup"><span data-stu-id="e52be-203">Compound assignment</span></span>

<span data-ttu-id="e52be-204">2 項演算子 `op` の場合、フォームの複合代入式</span><span class="sxs-lookup"><span data-stu-id="e52be-204">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="e52be-205">上記の式は、次の式と同じです。</span><span class="sxs-lookup"><span data-stu-id="e52be-205">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="e52be-206">ただし、`x` が評価されるのは 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="e52be-206">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="e52be-207">次の例に示すように、`&`、`|`、および `^` 演算子は複合代入をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e52be-207">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#CompoundAssignment)]

<span data-ttu-id="e52be-208">条件付き論理演算子 `&&` と `||` は複合代入をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="e52be-208">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="e52be-209">演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="e52be-209">Operator precedence</span></span>

<span data-ttu-id="e52be-210">次の論理演算子の一覧は、優先度が高い順に並べられています。</span><span class="sxs-lookup"><span data-stu-id="e52be-210">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="e52be-211">論理否定演算子 `!`</span><span class="sxs-lookup"><span data-stu-id="e52be-211">Logical negation operator `!`</span></span>
- <span data-ttu-id="e52be-212">論理 AND 演算子 `&`</span><span class="sxs-lookup"><span data-stu-id="e52be-212">Logical AND operator `&`</span></span>
- <span data-ttu-id="e52be-213">論理排他的 OR 演算子 `^`</span><span class="sxs-lookup"><span data-stu-id="e52be-213">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="e52be-214">論理 OR 演算子 `|`</span><span class="sxs-lookup"><span data-stu-id="e52be-214">Logical OR operator `|`</span></span>
- <span data-ttu-id="e52be-215">条件付き論理 AND 演算子 `&&`</span><span class="sxs-lookup"><span data-stu-id="e52be-215">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="e52be-216">条件付き論理 OR 演算子 `||`</span><span class="sxs-lookup"><span data-stu-id="e52be-216">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="e52be-217">演算子の優先順位によって定められた評価の順序を変更するには、かっこ `()` を使用します。</span><span class="sxs-lookup"><span data-stu-id="e52be-217">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Precedence)]

<span data-ttu-id="e52be-218">優先度順に並べられた C# 演算子の完全な一覧については、[C# 演算子](index.md)に関する記事の「[演算子の優先順位](index.md#operator-precedence)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e52be-218">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="e52be-219">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="e52be-219">Operator overloadability</span></span>

<span data-ttu-id="e52be-220">ユーザー定義型は、`!`、`&`、`|`、および `^` 演算子を[オーバーロード](operator-overloading.md)できます。</span><span class="sxs-lookup"><span data-stu-id="e52be-220">A user-defined type can [overload](operator-overloading.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="e52be-221">2 項演算子をオーバーロードすると、対応する複合代入演算子も暗黙的にオーバーロードされます。</span><span class="sxs-lookup"><span data-stu-id="e52be-221">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="e52be-222">ユーザー定義型は、複合代入演算子を明示的にオーバーロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e52be-222">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="e52be-223">ユーザー定義型は条件付き論理演算子 `&&` と `||` をオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="e52be-223">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="e52be-224">ただし、ユーザー定義型が [true および false 演算子](true-false-operators.md)と `&` または `|` 演算子を特定の方法でオーバーロードしている場合は、その型のオペランドに対してそれぞれ `&&` または `||` 演算の評価が可能になります。</span><span class="sxs-lookup"><span data-stu-id="e52be-224">However, if a user-defined type overloads the [true and false operators](true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="e52be-225">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の[ユーザー定義型条件論理演算子](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e52be-225">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e52be-226">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="e52be-226">C# language specification</span></span>

<span data-ttu-id="e52be-227">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e52be-227">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="e52be-228">論理否定演算子</span><span class="sxs-lookup"><span data-stu-id="e52be-228">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="e52be-229">論理演算子</span><span class="sxs-lookup"><span data-stu-id="e52be-229">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="e52be-230">条件論理演算子</span><span class="sxs-lookup"><span data-stu-id="e52be-230">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [<span data-ttu-id="e52be-231">複合代入</span><span class="sxs-lookup"><span data-stu-id="e52be-231">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a><span data-ttu-id="e52be-232">関連項目</span><span class="sxs-lookup"><span data-stu-id="e52be-232">See also</span></span>

- [<span data-ttu-id="e52be-233">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="e52be-233">C# reference</span></span>](../index.md)
- [<span data-ttu-id="e52be-234">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="e52be-234">C# operators</span></span>](index.md)
- [<span data-ttu-id="e52be-235">ビットごとの演算子とシフト演算子</span><span class="sxs-lookup"><span data-stu-id="e52be-235">Bitwise and shift operators</span></span>](bitwise-and-shift-operators.md)
