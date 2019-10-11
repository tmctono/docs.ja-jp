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
ms.openlocfilehash: cc25d4bfd444dc0acb30fc1c6e6c3c9918af537c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698678"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="c4ac3-103">ブール論理演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="c4ac3-103">Boolean logical operators (C# reference)</span></span>

<span data-ttu-id="c4ac3-104">次の演算子は、[bool](../keywords/bool.md) オペランドを使用して論理演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-104">The following operators perform logical operations with the [bool](../keywords/bool.md) operands:</span></span>

- <span data-ttu-id="c4ac3-105">単項 [`!` (論理否定)](#logical-negation-operator-) 演算子。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="c4ac3-106">二項 [`&` (論理 AND)](#logical-and-operator-)、[`|` (論理 OR)](#logical-or-operator-)、および [`^` (論理排他的 OR)](#logical-exclusive-or-operator-) 演算子。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="c4ac3-107">これらの演算子は常に両方のオペランドを評価します。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="c4ac3-108">二項 [`&&` (条件付き論理 AND)](#conditional-logical-and-operator-) および [`||` (条件付き論理 OR)](#conditional-logical-or-operator-) 演算子。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="c4ac3-109">これらの演算子では、必要な場合にのみ右側のオペランドが評価されます。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-109">Those operators evaluate the right-hand operand only if it's necessary.</span></span>

<span data-ttu-id="c4ac3-110">[整数](../builtin-types/integral-numeric-types.md)型のオペランドの場合、`&`、`|`、および `^` 演算子はビットごとの論理演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-110">For the operands of the [integral](../builtin-types/integral-numeric-types.md) types, the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span> <span data-ttu-id="c4ac3-111">詳しくは、「[ビットごとの演算子とシフト演算子](bitwise-and-shift-operators.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-111">For more information, see [Bitwise and shift operators](bitwise-and-shift-operators.md).</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="c4ac3-112">論理否定演算子 !</span><span class="sxs-lookup"><span data-stu-id="c4ac3-112">Logical negation operator !</span></span>

<span data-ttu-id="c4ac3-113">`!` 演算子は、そのオペランドの論理否定を計算します。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-113">The `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="c4ac3-114">つまり、オペランドが `false` と評価された場合は `true`、オペランドが `true` と評価された場合は `false` が生成されます。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-114">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Negation)]

<span data-ttu-id="c4ac3-115">C# 8.0 以降では、単項後置の `!` 演算子は null 免除演算子です。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-115">Starting with C# 8.0, the unary postfix `!` operator is a null-forgiving operator.</span></span> <span data-ttu-id="c4ac3-116">有効な null 許容注釈コンテキストでは、それを使用して、null 許容参照型の式 `x` が null ではないことを宣言します (`x!`)。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-116">In an enabled nullable annotation context, you use it to declare that expression `x` of a nullable reference type isn't null: `x!`.</span></span> <span data-ttu-id="c4ac3-117">詳細については、「[null 許容参照型](../../nullable-references.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-117">For more information, see [Nullable reference types](../../nullable-references.md).</span></span>

## <a name="logical-and-operator-"></a> <span data-ttu-id="c4ac3-118">論理 AND 演算子 &amp;</span><span class="sxs-lookup"><span data-stu-id="c4ac3-118">Logical AND operator &amp;</span></span>

<span data-ttu-id="c4ac3-119">`&` 演算子がそのオペランドの論理 AND を計算します。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-119">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="c4ac3-120">`x` と `y` の両方が `true` と評価されれば、`x & y` の結果は `true` です。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-120">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="c4ac3-121">それ以外の場合、結果は `false` です。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-121">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="c4ac3-122">`&` 演算子は、左側のオペランドが `false` と評価されても両方のオペランドを評価するため、結果は右側のオペランドの値に関係なく、必ず `false` になります。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-122">The `&` operator evaluates both operands even if the left-hand operand evaluates to `false`, so that the result must be `false` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="c4ac3-123">次の例では、`&` 演算子の右側のオペランドはメソッド呼び出しで、左側のオペランドの値に関係なく実行されます。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-123">In the following example, the right-hand operand of the `&` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#And)]

<span data-ttu-id="c4ac3-124">[条件付き論理 AND 演算子](#conditional-logical-and-operator-) `&&` もそのオペランドの論理 AND を計算しますが、左側のオペランドが `false` と評価された場合、右側のオペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-124">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `false`.</span></span>

<span data-ttu-id="c4ac3-125">整数型のオペランドの場合、`&` 演算子は、そのオペランドの[ビットごとの論理 AND](bitwise-and-shift-operators.md#logical-and-operator-) を計算します。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-125">For the operands of the integral types, the `&` operator computes the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="c4ac3-126">単項 `&` 演算子は[アドレス演算子](pointer-related-operators.md#address-of-operator-)です。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-126">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="c4ac3-127">論理排他的 OR 演算子: ^</span><span class="sxs-lookup"><span data-stu-id="c4ac3-127">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="c4ac3-128">`^` 演算子は、そのオペランドの論理排他的 OR (論理 XOR とも呼ばれます) を計算します。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-128">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="c4ac3-129">`x` が `true` に評価され、`y` が `false` に評価された場合、または `x` が `false` に評価され、`y` が `true` に評価された場合、`x ^ y` の結果は `true` です。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-129">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="c4ac3-130">それ以外の場合、結果は `false` です。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-130">Otherwise, the result is `false`.</span></span> <span data-ttu-id="c4ac3-131">つまり、`bool` オペランドの場合、`^` 演算子は[非等値演算子](equality-operators.md#inequality-operator-) `!=` と同じ結果を計算します。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-131">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Xor)]

<span data-ttu-id="c4ac3-132">整数型のオペランドの場合、`^` 演算子は、そのオペランドの[ビットごとの論理排他的 OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) を計算します。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-132">For the operands of the integral types, the `^` operator computes the [bitwise logical exclusive OR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="c4ac3-133">論理 OR 演算子 |</span><span class="sxs-lookup"><span data-stu-id="c4ac3-133">Logical OR operator |</span></span>

<span data-ttu-id="c4ac3-134">`|` 演算子がそのオペランドの論理 OR を計算します。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-134">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="c4ac3-135">`x` または `y` のどちらかが `true` と評価された場合、`x | y` の結果は `true` になります。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-135">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="c4ac3-136">それ以外の場合、結果は `false` です。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-136">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="c4ac3-137">`|` 演算子は、左側のオペランドが `true` と評価されても両方のオペランドを評価するため、結果は右側のオペランドの値に関係なく、必ず `true` になります。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-137">The `|` operator evaluates both operands even if the left-hand operand evaluates to `true`, so that the result must be `true` regardless of the value of the right-hand operand.</span></span>

<span data-ttu-id="c4ac3-138">次の例では、`|` 演算子の右側のオペランドはメソッド呼び出しで、左側のオペランドの値に関係なく実行されます。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-138">In the following example, the right-hand operand of the `|` operator is a method call, which is performed regardless of the value of the left-hand operand:</span></span>

[!code-csharp-interactive[logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Or)]

<span data-ttu-id="c4ac3-139">[条件付き論理 OR 演算子](#conditional-logical-or-operator-) `||` もそのオペランドの論理 OR を計算しますが、左側のオペランドが `true` と評価された場合、右側のオペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-139">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the right-hand operand if the left-hand operand evaluates to `true`.</span></span>

<span data-ttu-id="c4ac3-140">整数型のオペランドの場合、`|` 演算子は、そのオペランドの[ビットごとの論理 OR](bitwise-and-shift-operators.md#logical-or-operator-) を計算します。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-140">For the operands of the integral types, the `|` operator computes the [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="conditional-logical-and-operator-"></a> <span data-ttu-id="c4ac3-141">条件付き論理 AND 演算子 &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="c4ac3-141">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="c4ac3-142">条件論理 AND 演算子 `&&` は、"短絡" 論理 AND 演算子とも呼ばれ、そのオペランドの論理 AND を計算します。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-142">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="c4ac3-143">`x` と `y` の両方が `true` と評価されれば、`x && y` の結果は `true` です。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-143">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="c4ac3-144">それ以外の場合、結果は `false` です。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-144">Otherwise, the result is `false`.</span></span> <span data-ttu-id="c4ac3-145">`x` が `false` に評価される場合、`y` は評価されません。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-145">If `x` evaluates to `false`, `y` is not evaluated.</span></span>

<span data-ttu-id="c4ac3-146">次の例では、`&&` 演算子の右側のオペランドはメソッド呼び出しで、左側のオペランドが `false` と評価されると実行されません。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-146">In the following example, the right-hand operand of the `&&` operator is a method call, which isn't performed if the left-hand operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="c4ac3-147">[論理 AND 演算子](#logical-and-operator-) `&` もそのオペランドの論理 AND を計算しますが、常に両方のオペランドを評価します。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-147">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="c4ac3-148">条件付き論理 OR 演算子 ||</span><span class="sxs-lookup"><span data-stu-id="c4ac3-148">Conditional logical OR operator ||</span></span>

<span data-ttu-id="c4ac3-149">条件論理 OR 演算子 `||` は、"短絡" 論理 OR 演算子とも呼ばれ、そのオペランドの論理 OR を計算します。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-149">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="c4ac3-150">`x` または `y` のどちらかが `true` と評価された場合、`x || y` の結果は `true` になります。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-150">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="c4ac3-151">それ以外の場合、結果は `false` です。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-151">Otherwise, the result is `false`.</span></span> <span data-ttu-id="c4ac3-152">`x` が `true` に評価される場合、`y` は評価されません。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-152">If `x` evaluates to `true`, `y` is not evaluated.</span></span>

<span data-ttu-id="c4ac3-153">次の例では、`||` 演算子の右側のオペランドはメソッド呼び出しで、左側のオペランドが `true` と評価されると実行されません。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-153">In the following example, the right-hand operand of the `||` operator is a method call, which isn't performed if the left-hand operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="c4ac3-154">[論理 OR 演算子](#logical-or-operator-) `|` もそのオペランドの論理 OR を計算しますが、常に両方のオペランドを評価します。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-154">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="c4ac3-155">null 許容ブール論理演算子</span><span class="sxs-lookup"><span data-stu-id="c4ac3-155">Nullable Boolean logical operators</span></span>

<span data-ttu-id="c4ac3-156">`bool?` オペランドの場合、`&` 演算子と `|` 演算子は 3 値ロジックをサポートします。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-156">For the `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="c4ac3-157">次の表に、これらの演算子のセマンティクスが定義されています。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-157">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="c4ac3-158">x</span><span class="sxs-lookup"><span data-stu-id="c4ac3-158">x</span></span>|<span data-ttu-id="c4ac3-159">Y</span><span class="sxs-lookup"><span data-stu-id="c4ac3-159">y</span></span>|<span data-ttu-id="c4ac3-160">x&y</span><span class="sxs-lookup"><span data-stu-id="c4ac3-160">x&y</span></span>|<span data-ttu-id="c4ac3-161">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="c4ac3-161">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="c4ac3-162">true</span><span class="sxs-lookup"><span data-stu-id="c4ac3-162">true</span></span>|<span data-ttu-id="c4ac3-163">true</span><span class="sxs-lookup"><span data-stu-id="c4ac3-163">true</span></span>|<span data-ttu-id="c4ac3-164">true</span><span class="sxs-lookup"><span data-stu-id="c4ac3-164">true</span></span>|<span data-ttu-id="c4ac3-165">true</span><span class="sxs-lookup"><span data-stu-id="c4ac3-165">true</span></span>|  
|<span data-ttu-id="c4ac3-166">TRUE</span><span class="sxs-lookup"><span data-stu-id="c4ac3-166">true</span></span>|<span data-ttu-id="c4ac3-167">False</span><span class="sxs-lookup"><span data-stu-id="c4ac3-167">false</span></span>|<span data-ttu-id="c4ac3-168">false</span><span class="sxs-lookup"><span data-stu-id="c4ac3-168">false</span></span>|<span data-ttu-id="c4ac3-169">true</span><span class="sxs-lookup"><span data-stu-id="c4ac3-169">true</span></span>|  
|<span data-ttu-id="c4ac3-170">true</span><span class="sxs-lookup"><span data-stu-id="c4ac3-170">true</span></span>|<span data-ttu-id="c4ac3-171">null</span><span class="sxs-lookup"><span data-stu-id="c4ac3-171">null</span></span>|<span data-ttu-id="c4ac3-172">null</span><span class="sxs-lookup"><span data-stu-id="c4ac3-172">null</span></span>|<span data-ttu-id="c4ac3-173">true</span><span class="sxs-lookup"><span data-stu-id="c4ac3-173">true</span></span>|  
|<span data-ttu-id="c4ac3-174">False</span><span class="sxs-lookup"><span data-stu-id="c4ac3-174">false</span></span>|<span data-ttu-id="c4ac3-175">true</span><span class="sxs-lookup"><span data-stu-id="c4ac3-175">true</span></span>|<span data-ttu-id="c4ac3-176">False</span><span class="sxs-lookup"><span data-stu-id="c4ac3-176">false</span></span>|<span data-ttu-id="c4ac3-177">true</span><span class="sxs-lookup"><span data-stu-id="c4ac3-177">true</span></span>|  
|<span data-ttu-id="c4ac3-178">False</span><span class="sxs-lookup"><span data-stu-id="c4ac3-178">false</span></span>|<span data-ttu-id="c4ac3-179">False</span><span class="sxs-lookup"><span data-stu-id="c4ac3-179">false</span></span>|<span data-ttu-id="c4ac3-180">False</span><span class="sxs-lookup"><span data-stu-id="c4ac3-180">false</span></span>|<span data-ttu-id="c4ac3-181">False</span><span class="sxs-lookup"><span data-stu-id="c4ac3-181">false</span></span>|  
|<span data-ttu-id="c4ac3-182">False</span><span class="sxs-lookup"><span data-stu-id="c4ac3-182">false</span></span>|<span data-ttu-id="c4ac3-183">null</span><span class="sxs-lookup"><span data-stu-id="c4ac3-183">null</span></span>|<span data-ttu-id="c4ac3-184">False</span><span class="sxs-lookup"><span data-stu-id="c4ac3-184">false</span></span>|<span data-ttu-id="c4ac3-185">null</span><span class="sxs-lookup"><span data-stu-id="c4ac3-185">null</span></span>|  
|<span data-ttu-id="c4ac3-186">null</span><span class="sxs-lookup"><span data-stu-id="c4ac3-186">null</span></span>|<span data-ttu-id="c4ac3-187">true</span><span class="sxs-lookup"><span data-stu-id="c4ac3-187">true</span></span>|<span data-ttu-id="c4ac3-188">null</span><span class="sxs-lookup"><span data-stu-id="c4ac3-188">null</span></span>|<span data-ttu-id="c4ac3-189">true</span><span class="sxs-lookup"><span data-stu-id="c4ac3-189">true</span></span>|  
|<span data-ttu-id="c4ac3-190">null</span><span class="sxs-lookup"><span data-stu-id="c4ac3-190">null</span></span>|<span data-ttu-id="c4ac3-191">False</span><span class="sxs-lookup"><span data-stu-id="c4ac3-191">false</span></span>|<span data-ttu-id="c4ac3-192">False</span><span class="sxs-lookup"><span data-stu-id="c4ac3-192">false</span></span>|<span data-ttu-id="c4ac3-193">null</span><span class="sxs-lookup"><span data-stu-id="c4ac3-193">null</span></span>|  
|<span data-ttu-id="c4ac3-194">null</span><span class="sxs-lookup"><span data-stu-id="c4ac3-194">null</span></span>|<span data-ttu-id="c4ac3-195">null</span><span class="sxs-lookup"><span data-stu-id="c4ac3-195">null</span></span>|<span data-ttu-id="c4ac3-196">null</span><span class="sxs-lookup"><span data-stu-id="c4ac3-196">null</span></span>|<span data-ttu-id="c4ac3-197">null</span><span class="sxs-lookup"><span data-stu-id="c4ac3-197">null</span></span>|  

<span data-ttu-id="c4ac3-198">これらの演算子の動作は、null 許容値型の一般的な演算子の動作とは異なります。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-198">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="c4ac3-199">通常、値型のオペランドに定義されている演算子も、対応する null 値型のオペランドと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-199">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="c4ac3-200">このような演算子は、そのオペランドのいずれかが `null` の場合に `null` を生成します。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-200">Such an operator produces `null` if any of its operands is `null`.</span></span> <span data-ttu-id="c4ac3-201">ただし、`&` および `|` 演算子は、オペランドの 1 つが `null` の場合でも、null 以外の値を生成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-201">However, the `&` and `|` operators can produce non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="c4ac3-202">null 許容値型の演算子の動作については、[null 許容値型の使用](../../programming-guide/nullable-types/using-nullable-types.md)に関する記事の「[演算子](../../programming-guide/nullable-types/using-nullable-types.md#operators)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-202">For more information about the operator behavior with nullable value types, see the [Operators](../../programming-guide/nullable-types/using-nullable-types.md#operators) section of the [Using nullable value types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

<span data-ttu-id="c4ac3-203">次の例に示すように、`!` 演算子と `^` 演算子を `bool?` オペランドと共に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-203">You can also use the `!` and `^` operators with the `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="c4ac3-204">条件付き論理演算子 `&&` と `||` は `bool?` オペランドをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-204">The conditional logical operators `&&` and `||` don't support the `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="c4ac3-205">複合代入。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-205">Compound assignment</span></span>

<span data-ttu-id="c4ac3-206">2 項演算子 `op` の場合、フォームの複合代入式</span><span class="sxs-lookup"><span data-stu-id="c4ac3-206">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="c4ac3-207">上記の式は、次の式と同じです。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-207">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="c4ac3-208">ただし、`x` が評価されるのは 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-208">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="c4ac3-209">次の例に示すように、`&`、`|`、および `^` 演算子は複合代入をサポートします。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-209">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#CompoundAssignment)]

<span data-ttu-id="c4ac3-210">条件付き論理演算子 `&&` と `||` は複合代入をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-210">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="c4ac3-211">演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="c4ac3-211">Operator precedence</span></span>

<span data-ttu-id="c4ac3-212">次の論理演算子の一覧は、優先度が高い順に並べられています。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-212">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="c4ac3-213">論理否定演算子 `!`</span><span class="sxs-lookup"><span data-stu-id="c4ac3-213">Logical negation operator `!`</span></span>
- <span data-ttu-id="c4ac3-214">論理 AND 演算子 `&`</span><span class="sxs-lookup"><span data-stu-id="c4ac3-214">Logical AND operator `&`</span></span>
- <span data-ttu-id="c4ac3-215">論理排他的 OR 演算子 `^`</span><span class="sxs-lookup"><span data-stu-id="c4ac3-215">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="c4ac3-216">論理 OR 演算子 `|`</span><span class="sxs-lookup"><span data-stu-id="c4ac3-216">Logical OR operator `|`</span></span>
- <span data-ttu-id="c4ac3-217">条件付き論理 AND 演算子 `&&`</span><span class="sxs-lookup"><span data-stu-id="c4ac3-217">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="c4ac3-218">条件付き論理 OR 演算子 `||`</span><span class="sxs-lookup"><span data-stu-id="c4ac3-218">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="c4ac3-219">演算子の優先順位によって定められた評価の順序を変更するには、かっこ `()` を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-219">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/csharp/language-reference/operators/BooleanLogicalOperators.cs#Precedence)]

<span data-ttu-id="c4ac3-220">優先度順に並べられた C# 演算子の完全な一覧については、「[C# 演算子](index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-220">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="c4ac3-221">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="c4ac3-221">Operator overloadability</span></span>

<span data-ttu-id="c4ac3-222">ユーザー定義型は、`!`、`&`、`|`、および `^` 演算子を[オーバーロード](operator-overloading.md)できます。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-222">A user-defined type can [overload](operator-overloading.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="c4ac3-223">2 項演算子をオーバーロードすると、対応する複合代入演算子も暗黙的にオーバーロードされます。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-223">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="c4ac3-224">ユーザー定義型は、複合代入演算子を明示的にオーバーロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-224">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="c4ac3-225">ユーザー定義型は条件付き論理演算子 `&&` と `||` をオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-225">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="c4ac3-226">ただし、ユーザー定義型が [true および false 演算子](true-false-operators.md)と `&` または `|` 演算子を特定の方法でオーバーロードしている場合は、その型のオペランドに対してそれぞれ `&&` または `||` 演算の評価が可能になります。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-226">However, if a user-defined type overloads the [true and false operators](true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="c4ac3-227">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の[ユーザー定義型条件論理演算子](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-227">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c4ac3-228">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="c4ac3-228">C# language specification</span></span>

<span data-ttu-id="c4ac3-229">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4ac3-229">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="c4ac3-230">論理否定演算子</span><span class="sxs-lookup"><span data-stu-id="c4ac3-230">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="c4ac3-231">論理演算子</span><span class="sxs-lookup"><span data-stu-id="c4ac3-231">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="c4ac3-232">条件論理演算子</span><span class="sxs-lookup"><span data-stu-id="c4ac3-232">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [<span data-ttu-id="c4ac3-233">複合代入</span><span class="sxs-lookup"><span data-stu-id="c4ac3-233">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a><span data-ttu-id="c4ac3-234">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4ac3-234">See also</span></span>

- [<span data-ttu-id="c4ac3-235">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="c4ac3-235">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c4ac3-236">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="c4ac3-236">C# operators</span></span>](index.md)
- [<span data-ttu-id="c4ac3-237">ビットごとの演算子とシフト演算子</span><span class="sxs-lookup"><span data-stu-id="c4ac3-237">Bitwise and shift operators</span></span>](bitwise-and-shift-operators.md)
