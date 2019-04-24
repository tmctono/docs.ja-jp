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
ms.openlocfilehash: de621b26334bbc9679ba7e48a9d5a0cbaec67eab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59427319"
---
# <a name="boolean-logical-operators-c-reference"></a><span data-ttu-id="f45e3-103">ブール論理演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="f45e3-103">Boolean logical operators (C# Reference)</span></span>

<span data-ttu-id="f45e3-104">次の演算子は、[bool](../keywords/bool.md) オペランドを使用して論理演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="f45e3-104">The following operators perform logical operations with the [bool](../keywords/bool.md) operands:</span></span>

- <span data-ttu-id="f45e3-105">単項 [`!` (論理否定)](#logical-negation-operator-) 演算子。</span><span class="sxs-lookup"><span data-stu-id="f45e3-105">Unary [`!` (logical negation)](#logical-negation-operator-) operator.</span></span>
- <span data-ttu-id="f45e3-106">二項 [`&` (論理 AND)](#logical-and-operator-)、[`|` (論理 OR)](#logical-or-operator-)、および [`^` (論理排他的 OR)](#logical-exclusive-or-operator-) 演算子。</span><span class="sxs-lookup"><span data-stu-id="f45e3-106">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators.</span></span> <span data-ttu-id="f45e3-107">これらの演算子は常に両方のオペランドを評価します。</span><span class="sxs-lookup"><span data-stu-id="f45e3-107">Those operators always evaluate both operands.</span></span>
- <span data-ttu-id="f45e3-108">二項 [`&&` (条件付き論理 AND)](#conditional-logical-and-operator-) および [`||` (条件付き論理 OR)](#conditional-logical-or-operator-) 演算子。</span><span class="sxs-lookup"><span data-stu-id="f45e3-108">Binary [`&&` (conditional logical AND)](#conditional-logical-and-operator-) and [`||` (conditional logical OR)](#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="f45e3-109">これらの演算子は、必要な場合にのみ 2 番目のオペランドを評価します。</span><span class="sxs-lookup"><span data-stu-id="f45e3-109">Those operators evaluate the second operand only if it's necessary.</span></span>

<span data-ttu-id="f45e3-110">[整数](../keywords/integral-types-table.md)型のオペランドの場合、`&`、`|`、および `^` 演算子はビットごとの論理演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="f45e3-110">For the operands of [integral](../keywords/integral-types-table.md) types, the `&`, `|`, and `^` operators perform bitwise logical operations.</span></span>

## <a name="logical-negation-operator-"></a><span data-ttu-id="f45e3-111">論理否定演算子 !</span><span class="sxs-lookup"><span data-stu-id="f45e3-111">Logical negation operator !</span></span>

<span data-ttu-id="f45e3-112">`!` 演算子は、そのオペランドの論理否定を計算します。</span><span class="sxs-lookup"><span data-stu-id="f45e3-112">The `!` operator computes logical negation of its operand.</span></span> <span data-ttu-id="f45e3-113">つまり、オペランドが `false` と評価された場合は `true`、オペランドが `true` と評価された場合は `false` が生成されます。</span><span class="sxs-lookup"><span data-stu-id="f45e3-113">That is, it produces `true`, if the operand evaluates to `false`, and `false`, if the operand evaluates to `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Negation)]

## <a name="logical-and-operator-amp"></a><span data-ttu-id="f45e3-114">論理 AND 演算子 &amp;</span><span class="sxs-lookup"><span data-stu-id="f45e3-114">Logical AND operator &amp;</span></span>

<span data-ttu-id="f45e3-115">`&` 演算子がそのオペランドの論理 AND を計算します。</span><span class="sxs-lookup"><span data-stu-id="f45e3-115">The `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="f45e3-116">`x` と `y` の両方が `true` と評価されれば、`x & y` の結果は `true` です。</span><span class="sxs-lookup"><span data-stu-id="f45e3-116">The result of `x & y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="f45e3-117">それ以外の場合、結果は `false` です。</span><span class="sxs-lookup"><span data-stu-id="f45e3-117">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="f45e3-118">`&` 演算子は最初のオペランドが `false` と評価されても両方のオペランドを評価するため、結果は 2 番目のオペランドの値に関係なく、必ず `false` になります。</span><span class="sxs-lookup"><span data-stu-id="f45e3-118">The `&` operator evaluates both operands even if the first operand evaluates to `false`, so that the result must be `false` regardless of the value of the second operand.</span></span>

<span data-ttu-id="f45e3-119">次の例では、`&` 演算子の 2 番目のオペランドはメソッド呼び出しで、最初のオペランドの値に関係なく実行されます。</span><span class="sxs-lookup"><span data-stu-id="f45e3-119">In the following example, the second operand of the `&` operator is a method call, which is performed regardless of the value of the first operand:</span></span>

[!code-csharp-interactive[logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#And)]

<span data-ttu-id="f45e3-120">[条件付き論理 AND 演算子](#conditional-logical-and-operator-) `&&` もそのオペランドの論理 AND を計算しますが、最初のオペランドが `false` と評価された場合、2 番目のオペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="f45e3-120">The [conditional logical AND operator](#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the second operand if the first operand evaluates to `false`.</span></span>

<span data-ttu-id="f45e3-121">整数型のオペランドの場合、`&` 演算子は、そのオペランドの[ビットごとの論理 AND](and-operator.md#integer-logical-bitwise-and-operator) を計算します。</span><span class="sxs-lookup"><span data-stu-id="f45e3-121">For the operands of integral types, the `&` operator computes [bitwise logical AND](and-operator.md#integer-logical-bitwise-and-operator) of its operands.</span></span> <span data-ttu-id="f45e3-122">単項 `&` 演算子は[アドレス演算子](and-operator.md#unary-address-of-operator)です。</span><span class="sxs-lookup"><span data-stu-id="f45e3-122">The unary `&` operator is the [address-of operator](and-operator.md#unary-address-of-operator).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="f45e3-123">論理排他的 OR 演算子: ^</span><span class="sxs-lookup"><span data-stu-id="f45e3-123">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="f45e3-124">`^` 演算子は、そのオペランドの論理排他的 OR (論理 XOR とも呼ばれます) を計算します。</span><span class="sxs-lookup"><span data-stu-id="f45e3-124">The `^` operator computes the logical exclusive OR, also known as the logical XOR, of its operands.</span></span> <span data-ttu-id="f45e3-125">`x` が `true` に評価され、`y` が `false` に評価された場合、または `x` が `false` に評価され、`y` が `true` に評価された場合、`x ^ y` の結果は `true` です。</span><span class="sxs-lookup"><span data-stu-id="f45e3-125">The result of `x ^ y` is `true` if `x` evaluates to `true` and `y` evaluates to `false`, or `x` evaluates to `false` and `y` evaluates to `true`.</span></span> <span data-ttu-id="f45e3-126">それ以外の場合、結果は `false` です。</span><span class="sxs-lookup"><span data-stu-id="f45e3-126">Otherwise, the result is `false`.</span></span> <span data-ttu-id="f45e3-127">つまり、`bool` オペランドの場合、`^` 演算子は[非等値演算子](equality-operators.md#inequality-operator-) `!=` と同じ結果を計算します。</span><span class="sxs-lookup"><span data-stu-id="f45e3-127">That is, for the `bool` operands, the `^` operator computes the same result as the [inequality operator](equality-operators.md#inequality-operator-) `!=`.</span></span>

[!code-csharp-interactive[logical exclusive OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Xor)]

<span data-ttu-id="f45e3-128">整数型のオペランドの場合、`^` 演算子は、そのオペランドの[ビットごとの論理排他的 OR](xor-operator.md) を計算します。</span><span class="sxs-lookup"><span data-stu-id="f45e3-128">For the operands of integral types, the `^` operator computes [bitwise logical exclusive OR](xor-operator.md) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="f45e3-129">論理 OR 演算子 |</span><span class="sxs-lookup"><span data-stu-id="f45e3-129">Logical OR operator |</span></span>

<span data-ttu-id="f45e3-130">`|` 演算子がそのオペランドの論理 OR を計算します。</span><span class="sxs-lookup"><span data-stu-id="f45e3-130">The `|` operator computes the logical OR of its operands.</span></span> <span data-ttu-id="f45e3-131">`x` または `y` のどちらかが `true` と評価された場合、`x | y` の結果は `true` になります。</span><span class="sxs-lookup"><span data-stu-id="f45e3-131">The result of `x | y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="f45e3-132">それ以外の場合、結果は `false` です。</span><span class="sxs-lookup"><span data-stu-id="f45e3-132">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="f45e3-133">`|` 演算子は最初のオペランドが `true` と評価されても両方のオペランドを評価するため、結果は 2 番目のオペランドの値に関係なく、必ず `true` になります。</span><span class="sxs-lookup"><span data-stu-id="f45e3-133">The `|` operator evaluates both operands even if the first operand evaluates to `true`, so that the result must be `true` regardless of the value of the second operand.</span></span>

<span data-ttu-id="f45e3-134">次の例では、`|` 演算子の 2 番目のオペランドはメソッド呼び出しで、最初のオペランドの値に関係なく実行されます。</span><span class="sxs-lookup"><span data-stu-id="f45e3-134">In the following example, the second operand of the `|` operator is a method call, which is performed regardless of the value of the first operand:</span></span>

[!code-csharp-interactive[logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Or)]

<span data-ttu-id="f45e3-135">[条件付き論理 OR 演算子](#conditional-logical-or-operator-) `||` もそのオペランドの論理 OR を計算しますが、最初のオペランドが `true` と評価された場合、2 番目のオペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="f45e3-135">The [conditional logical OR operator](#conditional-logical-or-operator-) `||` also computes the logical OR of its operands, but doesn't evaluate the second operand if the first operand evaluates to `true`.</span></span>

<span data-ttu-id="f45e3-136">整数型のオペランドの場合、`|` 演算子は、そのオペランドの[ビットごとの論理 OR](or-operator.md) を計算します。</span><span class="sxs-lookup"><span data-stu-id="f45e3-136">For the operands of integral types, the `|` operator computes [bitwise logical OR](or-operator.md) of its operands.</span></span>

## <a name="conditional-logical-and-operator-ampamp"></a><span data-ttu-id="f45e3-137">条件付き論理 AND 演算子 &amp;&amp;</span><span class="sxs-lookup"><span data-stu-id="f45e3-137">Conditional logical AND operator &amp;&amp;</span></span>

<span data-ttu-id="f45e3-138">条件論理 AND 演算子 `&&` は、"短絡" 論理 AND 演算子とも呼ばれ、そのオペランドの論理 AND を計算します。</span><span class="sxs-lookup"><span data-stu-id="f45e3-138">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its operands.</span></span> <span data-ttu-id="f45e3-139">`x` と `y` の両方が `true` と評価されれば、`x && y` の結果は `true` です。</span><span class="sxs-lookup"><span data-stu-id="f45e3-139">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="f45e3-140">それ以外の場合、結果は `false` です。</span><span class="sxs-lookup"><span data-stu-id="f45e3-140">Otherwise, the result is `false`.</span></span> <span data-ttu-id="f45e3-141">最初のオペランドが `false` と評価されると、2 番目のオペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="f45e3-141">If the first operand evaluates to `false`, the second operand is not evaluated.</span></span>

<span data-ttu-id="f45e3-142">次の例では、最初のオペランドが `false` と評価されると、`&&` 演算子の 2 番目のオペランドはメソッド呼び出しで実行されません。</span><span class="sxs-lookup"><span data-stu-id="f45e3-142">In the following example, the second operand of the `&&` operator is a method call, which isn't performed if the first operand evaluates to `false`:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalAnd)]

<span data-ttu-id="f45e3-143">[論理 AND 演算子](#logical-and-operator-) `&` もそのオペランドの論理 AND を計算しますが、常に両方のオペランドを評価します。</span><span class="sxs-lookup"><span data-stu-id="f45e3-143">The [logical AND operator](#logical-and-operator-) `&` also computes the logical AND of its operands, but always evaluates both operands.</span></span>

## <a name="conditional-logical-or-operator-"></a><span data-ttu-id="f45e3-144">条件付き論理 OR 演算子 ||</span><span class="sxs-lookup"><span data-stu-id="f45e3-144">Conditional logical OR operator ||</span></span>

<span data-ttu-id="f45e3-145">条件論理 OR 演算子 `||` は、"短絡" 論理 OR 演算子とも呼ばれ、そのオペランドの論理 OR を計算します。</span><span class="sxs-lookup"><span data-stu-id="f45e3-145">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its operands.</span></span> <span data-ttu-id="f45e3-146">`x` または `y` のどちらかが `true` と評価された場合、`x || y` の結果は `true` になります。</span><span class="sxs-lookup"><span data-stu-id="f45e3-146">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="f45e3-147">それ以外の場合、結果は `false` です。</span><span class="sxs-lookup"><span data-stu-id="f45e3-147">Otherwise, the result is `false`.</span></span> <span data-ttu-id="f45e3-148">最初のオペランドが `true` と評価されると、2 番目のオペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="f45e3-148">If the first operand evaluates to `true`, the second operand is not evaluated.</span></span>

<span data-ttu-id="f45e3-149">次の例では、最初のオペランドが `true` と評価されると、`||` 演算子の 2 番目のオペランドはメソッド呼び出しで実行されません。</span><span class="sxs-lookup"><span data-stu-id="f45e3-149">In the following example, the second operand of the `||` operator is a method call, which isn't performed if the first operand evaluates to `true`:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalOr)]

<span data-ttu-id="f45e3-150">[論理 OR 演算子](#logical-or-operator-) `|` もそのオペランドの論理 OR を計算しますが、常に両方のオペランドを評価します。</span><span class="sxs-lookup"><span data-stu-id="f45e3-150">The [logical OR operator](#logical-or-operator-) `|` also computes the logical OR of its operands, but always evaluates both operands.</span></span>

## <a name="nullable-boolean-logical-operators"></a><span data-ttu-id="f45e3-151">null 許容ブール論理演算子</span><span class="sxs-lookup"><span data-stu-id="f45e3-151">Nullable Boolean logical operators</span></span>

<span data-ttu-id="f45e3-152">`bool?` オペランドの場合、`&` 演算子と `|` 演算子は 3 値ロジックをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f45e3-152">For the `bool?` operands, the `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="f45e3-153">次の表に、これらの演算子のセマンティクスが定義されています。</span><span class="sxs-lookup"><span data-stu-id="f45e3-153">The semantics of these operators is defined by the following table:</span></span>  
  
|<span data-ttu-id="f45e3-154">x</span><span class="sxs-lookup"><span data-stu-id="f45e3-154">x</span></span>|<span data-ttu-id="f45e3-155">Y</span><span class="sxs-lookup"><span data-stu-id="f45e3-155">y</span></span>|<span data-ttu-id="f45e3-156">x&y</span><span class="sxs-lookup"><span data-stu-id="f45e3-156">x&y</span></span>|<span data-ttu-id="f45e3-157">x&#124;y</span><span class="sxs-lookup"><span data-stu-id="f45e3-157">x&#124;y</span></span>|  
|----|----|----|----|  
|<span data-ttu-id="f45e3-158">true</span><span class="sxs-lookup"><span data-stu-id="f45e3-158">true</span></span>|<span data-ttu-id="f45e3-159">true</span><span class="sxs-lookup"><span data-stu-id="f45e3-159">true</span></span>|<span data-ttu-id="f45e3-160">true</span><span class="sxs-lookup"><span data-stu-id="f45e3-160">true</span></span>|<span data-ttu-id="f45e3-161">true</span><span class="sxs-lookup"><span data-stu-id="f45e3-161">true</span></span>|  
|<span data-ttu-id="f45e3-162">TRUE</span><span class="sxs-lookup"><span data-stu-id="f45e3-162">true</span></span>|<span data-ttu-id="f45e3-163">False</span><span class="sxs-lookup"><span data-stu-id="f45e3-163">false</span></span>|<span data-ttu-id="f45e3-164">false</span><span class="sxs-lookup"><span data-stu-id="f45e3-164">false</span></span>|<span data-ttu-id="f45e3-165">true</span><span class="sxs-lookup"><span data-stu-id="f45e3-165">true</span></span>|  
|<span data-ttu-id="f45e3-166">true</span><span class="sxs-lookup"><span data-stu-id="f45e3-166">true</span></span>|<span data-ttu-id="f45e3-167">null</span><span class="sxs-lookup"><span data-stu-id="f45e3-167">null</span></span>|<span data-ttu-id="f45e3-168">null</span><span class="sxs-lookup"><span data-stu-id="f45e3-168">null</span></span>|<span data-ttu-id="f45e3-169">true</span><span class="sxs-lookup"><span data-stu-id="f45e3-169">true</span></span>|  
|<span data-ttu-id="f45e3-170">False</span><span class="sxs-lookup"><span data-stu-id="f45e3-170">false</span></span>|<span data-ttu-id="f45e3-171">true</span><span class="sxs-lookup"><span data-stu-id="f45e3-171">true</span></span>|<span data-ttu-id="f45e3-172">False</span><span class="sxs-lookup"><span data-stu-id="f45e3-172">false</span></span>|<span data-ttu-id="f45e3-173">true</span><span class="sxs-lookup"><span data-stu-id="f45e3-173">true</span></span>|  
|<span data-ttu-id="f45e3-174">False</span><span class="sxs-lookup"><span data-stu-id="f45e3-174">false</span></span>|<span data-ttu-id="f45e3-175">False</span><span class="sxs-lookup"><span data-stu-id="f45e3-175">false</span></span>|<span data-ttu-id="f45e3-176">False</span><span class="sxs-lookup"><span data-stu-id="f45e3-176">false</span></span>|<span data-ttu-id="f45e3-177">False</span><span class="sxs-lookup"><span data-stu-id="f45e3-177">false</span></span>|  
|<span data-ttu-id="f45e3-178">False</span><span class="sxs-lookup"><span data-stu-id="f45e3-178">false</span></span>|<span data-ttu-id="f45e3-179">null</span><span class="sxs-lookup"><span data-stu-id="f45e3-179">null</span></span>|<span data-ttu-id="f45e3-180">False</span><span class="sxs-lookup"><span data-stu-id="f45e3-180">false</span></span>|<span data-ttu-id="f45e3-181">null</span><span class="sxs-lookup"><span data-stu-id="f45e3-181">null</span></span>|  
|<span data-ttu-id="f45e3-182">null</span><span class="sxs-lookup"><span data-stu-id="f45e3-182">null</span></span>|<span data-ttu-id="f45e3-183">true</span><span class="sxs-lookup"><span data-stu-id="f45e3-183">true</span></span>|<span data-ttu-id="f45e3-184">null</span><span class="sxs-lookup"><span data-stu-id="f45e3-184">null</span></span>|<span data-ttu-id="f45e3-185">true</span><span class="sxs-lookup"><span data-stu-id="f45e3-185">true</span></span>|  
|<span data-ttu-id="f45e3-186">null</span><span class="sxs-lookup"><span data-stu-id="f45e3-186">null</span></span>|<span data-ttu-id="f45e3-187">False</span><span class="sxs-lookup"><span data-stu-id="f45e3-187">false</span></span>|<span data-ttu-id="f45e3-188">False</span><span class="sxs-lookup"><span data-stu-id="f45e3-188">false</span></span>|<span data-ttu-id="f45e3-189">null</span><span class="sxs-lookup"><span data-stu-id="f45e3-189">null</span></span>|  
|<span data-ttu-id="f45e3-190">null</span><span class="sxs-lookup"><span data-stu-id="f45e3-190">null</span></span>|<span data-ttu-id="f45e3-191">null</span><span class="sxs-lookup"><span data-stu-id="f45e3-191">null</span></span>|<span data-ttu-id="f45e3-192">null</span><span class="sxs-lookup"><span data-stu-id="f45e3-192">null</span></span>|<span data-ttu-id="f45e3-193">null</span><span class="sxs-lookup"><span data-stu-id="f45e3-193">null</span></span>|  

<span data-ttu-id="f45e3-194">これらの演算子の動作は、null 許容値型の一般的な演算子の動作とは異なります。</span><span class="sxs-lookup"><span data-stu-id="f45e3-194">The behavior of those operators differs from the typical operator behavior with nullable value types.</span></span> <span data-ttu-id="f45e3-195">通常、値型のオペランドに定義されている演算子も、対応する null 値型のオペランドと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="f45e3-195">Typically, an operator which is defined for operands of a value type can be also used with operands of the corresponding nullable value type.</span></span> <span data-ttu-id="f45e3-196">このような演算子は、そのオペランドのいずれかが `null` の場合に `null` を生成します。</span><span class="sxs-lookup"><span data-stu-id="f45e3-196">Such an operator produces `null` if any of its operands is `null`.</span></span> <span data-ttu-id="f45e3-197">ただし、`&` および `|` 演算子は、オペランドの 1 つが `null` の場合でも、null 以外の値を生成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f45e3-197">However, the `&` and `|` operators can produce non-null even if one of the operands is `null`.</span></span> <span data-ttu-id="f45e3-198">null 許容値型の演算子の動作については、「[Null 許容型の使用](../../programming-guide/nullable-types/using-nullable-types.md)」記事の「[演算子](../../programming-guide/nullable-types/using-nullable-types.md#operators)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f45e3-198">For more information about the operator behavior with nullable value types, see the [Operators](../../programming-guide/nullable-types/using-nullable-types.md#operators) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

<span data-ttu-id="f45e3-199">次の例に示すように、`!` 演算子と `^` 演算子を `bool?` オペランドと共に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f45e3-199">You can also use the `!` and `^` operators with the `bool?` operands, as the following example shows:</span></span>

[!code-csharp-interactive[lifted negation and xor](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#WithNullableBoolean)]

<span data-ttu-id="f45e3-200">条件付き論理演算子 `&&` と `||` は `bool?` オペランドをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="f45e3-200">The conditional logical operators `&&` and `||` don't support the `bool?` operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="f45e3-201">複合代入。</span><span class="sxs-lookup"><span data-stu-id="f45e3-201">Compound assignment</span></span>

<span data-ttu-id="f45e3-202">2 項演算子 `op` の場合、フォームの複合代入式</span><span class="sxs-lookup"><span data-stu-id="f45e3-202">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="f45e3-203">上記の式は、次の式と同じです。</span><span class="sxs-lookup"><span data-stu-id="f45e3-203">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="f45e3-204">ただし、`x` が評価されるのは 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="f45e3-204">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="f45e3-205">次の例に示すように、`&`、`|`、および `^` 演算子は複合代入をサポートします。</span><span class="sxs-lookup"><span data-stu-id="f45e3-205">The `&`, `|`, and `^` operators support compound assignment, as the following example shows:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#CompoundAssignment)]

<span data-ttu-id="f45e3-206">条件付き論理演算子 `&&` と `||` は複合代入をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="f45e3-206">The conditional logical operators `&&` and `||` don't support compound assignment.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="f45e3-207">演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="f45e3-207">Operator precedence</span></span>

<span data-ttu-id="f45e3-208">次の論理演算子の一覧は、優先度が高い順に並べられています。</span><span class="sxs-lookup"><span data-stu-id="f45e3-208">The following list orders logical operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="f45e3-209">論理否定演算子 `!`</span><span class="sxs-lookup"><span data-stu-id="f45e3-209">Logical negation operator `!`</span></span>
- <span data-ttu-id="f45e3-210">論理 AND 演算子 `&`</span><span class="sxs-lookup"><span data-stu-id="f45e3-210">Logical AND operator `&`</span></span>
- <span data-ttu-id="f45e3-211">論理排他的 OR 演算子 `^`</span><span class="sxs-lookup"><span data-stu-id="f45e3-211">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="f45e3-212">論理 OR 演算子 `|`</span><span class="sxs-lookup"><span data-stu-id="f45e3-212">Logical OR operator `|`</span></span>
- <span data-ttu-id="f45e3-213">条件付き論理 AND 演算子 `&&`</span><span class="sxs-lookup"><span data-stu-id="f45e3-213">Conditional logical AND operator `&&`</span></span>
- <span data-ttu-id="f45e3-214">条件付き論理 OR 演算子 `||`</span><span class="sxs-lookup"><span data-stu-id="f45e3-214">Conditional logical OR operator `||`</span></span>

<span data-ttu-id="f45e3-215">演算子の優先順位によって定められた評価の順序を変更するには、かっこ `()` を使用します。</span><span class="sxs-lookup"><span data-stu-id="f45e3-215">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Precedence)]

<span data-ttu-id="f45e3-216">優先度順に並べられた C# 演算子の完全な一覧については、「[C# 演算子](index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f45e3-216">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="f45e3-217">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="f45e3-217">Operator overloadability</span></span>

<span data-ttu-id="f45e3-218">ユーザー定義型は、`!`、`&`、`|`、および `^` 演算子を[オーバーロード](../keywords/operator.md)できます。</span><span class="sxs-lookup"><span data-stu-id="f45e3-218">A user-defined type can [overload](../keywords/operator.md) the `!`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="f45e3-219">2 項演算子をオーバーロードすると、対応する複合代入演算子も暗黙的にオーバーロードされます。</span><span class="sxs-lookup"><span data-stu-id="f45e3-219">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="f45e3-220">ユーザー定義型は、複合代入演算子を明示的にオーバーロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f45e3-220">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="f45e3-221">ユーザー定義型は条件付き論理演算子 `&&` と `||` をオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="f45e3-221">A user-defined type cannot overload the conditional logical operators `&&` and `||`.</span></span> <span data-ttu-id="f45e3-222">ただし、ユーザー定義型が [true および false 演算子](../keywords/true-false-operators.md)と `&` または `|` 演算子を特定の方法でオーバーロードしている場合は、その型のオペランドに対してそれぞれ `&&` または `||` 演算の評価が可能になります。</span><span class="sxs-lookup"><span data-stu-id="f45e3-222">However, if a user-defined type overloads the [true and false operators](../keywords/true-false-operators.md) and the `&` or `|` operator in a certain way, the `&&` or `||` operation, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="f45e3-223">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の[ユーザー定義型条件論理演算子](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f45e3-223">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f45e3-224">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="f45e3-224">C# language specification</span></span>

<span data-ttu-id="f45e3-225">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f45e3-225">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="f45e3-226">論理否定演算子</span><span class="sxs-lookup"><span data-stu-id="f45e3-226">Logical negation operator</span></span>](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [<span data-ttu-id="f45e3-227">論理演算子</span><span class="sxs-lookup"><span data-stu-id="f45e3-227">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="f45e3-228">条件論理演算子</span><span class="sxs-lookup"><span data-stu-id="f45e3-228">Conditional logical operators</span></span>](~/_csharplang/spec/expressions.md#conditional-logical-operators)

## <a name="see-also"></a><span data-ttu-id="f45e3-229">関連項目</span><span class="sxs-lookup"><span data-stu-id="f45e3-229">See also</span></span>

- [<span data-ttu-id="f45e3-230">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="f45e3-230">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f45e3-231">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="f45e3-231">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f45e3-232">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="f45e3-232">C# Operators</span></span>](index.md)
