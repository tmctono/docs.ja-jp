---
title: Visual Basic の演算子で実行される一般的な演算
ms.date: 07/20/2015
helpviewer_keywords:
- operators [Visual Basic], logical
- operators [Visual Basic], string concatenation
- operators [Visual Basic], bitwise
- operators [Visual Basic], bit-shift
- operators [Visual Basic], arithmetic
- operators [Visual Basic], string comparison
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- operators [Visual Basic], comparison
- operators [Visual Basic], short-circuiting logical
ms.assetid: d181afe5-fafa-460f-a13b-81203f6f4587
ms.openlocfilehash: a8a8d7898e52077fef47b91172e34ad50d7f54e7
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075214"
---
# <a name="common-tasks-performed-with-visual-basic-operators"></a><span data-ttu-id="c1081-102">Visual Basic の演算子で実行される一般的な演算</span><span class="sxs-lookup"><span data-stu-id="c1081-102">Common Tasks Performed with Visual Basic Operators</span></span>

<span data-ttu-id="c1081-103">演算子によって、"*オペランド*" と呼ばれる 1 つ以上の式を含む多くの一般的なタスクが実行されます。</span><span class="sxs-lookup"><span data-stu-id="c1081-103">Operators perform many common tasks involving one or more expressions called *operands*.</span></span>  
  
## <a name="arithmetic-and-bit-shift-tasks"></a><span data-ttu-id="c1081-104">算術とビットシフト タスク</span><span class="sxs-lookup"><span data-stu-id="c1081-104">Arithmetic and Bit-shift Tasks</span></span>  

 <span data-ttu-id="c1081-105">次の表は、使用できる算術演算とビットシフト演算をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="c1081-105">The following table summarizes the available arithmetic and bit-shift operations.</span></span>  
  
|<span data-ttu-id="c1081-106">終了</span><span class="sxs-lookup"><span data-stu-id="c1081-106">To</span></span>|<span data-ttu-id="c1081-107">解決方法については、</span><span class="sxs-lookup"><span data-stu-id="c1081-107">See</span></span>|  
|---|---|  
|<span data-ttu-id="c1081-108">ある数値をもう 1 つの数値に加算します</span><span class="sxs-lookup"><span data-stu-id="c1081-108">Add one numeric value to another</span></span>|[<span data-ttu-id="c1081-109">+ 演算子</span><span class="sxs-lookup"><span data-stu-id="c1081-109">+ Operator</span></span>](../../../language-reference/operators/addition-operator.md)|  
|<span data-ttu-id="c1081-110">ある数値からもう 1 つの数値を減算します</span><span class="sxs-lookup"><span data-stu-id="c1081-110">Subtract one numeric value from another</span></span>|[<span data-ttu-id="c1081-111">- 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1081-111">- Operator (Visual Basic)</span></span>](../../../language-reference/operators/subtraction-operator.md)|  
|<span data-ttu-id="c1081-112">ある数値の符号を反転します</span><span class="sxs-lookup"><span data-stu-id="c1081-112">Reverse the sign of a numeric value</span></span>|[<span data-ttu-id="c1081-113">- 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1081-113">- Operator (Visual Basic)</span></span>](../../../language-reference/operators/subtraction-operator.md)|  
|<span data-ttu-id="c1081-114">ある数値にもう 1 つの数値を乗算します</span><span class="sxs-lookup"><span data-stu-id="c1081-114">Multiply one numeric value by another</span></span>|[<span data-ttu-id="c1081-115">\* 演算子</span><span class="sxs-lookup"><span data-stu-id="c1081-115">\* Operator</span></span>](../../../language-reference/operators/multiplication-operator.md)|  
|<span data-ttu-id="c1081-116">ある数値をもう 1 つの数値に除算します</span><span class="sxs-lookup"><span data-stu-id="c1081-116">Divide one numeric value into another</span></span>|[<span data-ttu-id="c1081-117">/ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1081-117">/ Operator (Visual Basic)</span></span>](../../../language-reference/operators/floating-point-division-operator.md)|  
|<span data-ttu-id="c1081-118">ある数値をもう 1 つの数値で除算した商を求めます (剰余なし)</span><span class="sxs-lookup"><span data-stu-id="c1081-118">Find the quotient of one numeric value divided by another (without the remainder)</span></span>|[<span data-ttu-id="c1081-119">\ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1081-119">\ Operator (Visual Basic)</span></span>](../../../language-reference/operators/integer-division-operator.md)|  
|<span data-ttu-id="c1081-120">ある数値をもう 1 つの数値で除算した剰余を求めます (商なし)</span><span class="sxs-lookup"><span data-stu-id="c1081-120">Find the remainder of one numeric value divided by another (without the quotient)</span></span>|[<span data-ttu-id="c1081-121">Mod 演算子</span><span class="sxs-lookup"><span data-stu-id="c1081-121">Mod Operator</span></span>](../../../language-reference/operators/mod-operator.md)|  
|<span data-ttu-id="c1081-122">ある数値をもう 1 つの数値のべき乗にします</span><span class="sxs-lookup"><span data-stu-id="c1081-122">Raise one numeric value to the power of another</span></span>|[<span data-ttu-id="c1081-123">^ 演算子</span><span class="sxs-lookup"><span data-stu-id="c1081-123">^ Operator</span></span>](../../../language-reference/operators/exponentiation-operator.md)|  
|<span data-ttu-id="c1081-124">数値のビット パターンを左にシフトします</span><span class="sxs-lookup"><span data-stu-id="c1081-124">Shift the bit pattern of a numeric value to the left</span></span>|[<span data-ttu-id="c1081-125"><\< 演算子</span><span class="sxs-lookup"><span data-stu-id="c1081-125"><\< Operator</span></span>](../../../language-reference/operators/left-shift-operator.md)|  
|<span data-ttu-id="c1081-126">数値のビット パターンを右にシフトします</span><span class="sxs-lookup"><span data-stu-id="c1081-126">Shift the bit pattern of a numeric value to the right</span></span>|[<span data-ttu-id="c1081-127">>> 演算子</span><span class="sxs-lookup"><span data-stu-id="c1081-127">>> Operator</span></span>](../../../language-reference/operators/right-shift-operator.md)|  
  
## <a name="comparison-tasks"></a><span data-ttu-id="c1081-128">比較タスク</span><span class="sxs-lookup"><span data-stu-id="c1081-128">Comparison Tasks</span></span>  

 <span data-ttu-id="c1081-129">次の表は、使用できる比較演算をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="c1081-129">The following table summarizes the available comparison operations.</span></span>  
  
|<span data-ttu-id="c1081-130">終了</span><span class="sxs-lookup"><span data-stu-id="c1081-130">To</span></span>|<span data-ttu-id="c1081-131">解決方法については、</span><span class="sxs-lookup"><span data-stu-id="c1081-131">See</span></span>|  
|---|---|  
|<span data-ttu-id="c1081-132">2 つの値が等しいかどうかを判断します</span><span class="sxs-lookup"><span data-stu-id="c1081-132">Determine whether two values are equal</span></span>|<span data-ttu-id="c1081-133">`=` 演算子 ([Visual Basic の比較演算子](comparison-operators.md))</span><span class="sxs-lookup"><span data-stu-id="c1081-133">`=` Operator ([Comparison Operators in Visual Basic](comparison-operators.md))</span></span>|  
|<span data-ttu-id="c1081-134">2 つの値が等しくないかどうかを判断します</span><span class="sxs-lookup"><span data-stu-id="c1081-134">Determine whether two values are unequal</span></span>|<span data-ttu-id="c1081-135">`<>` 演算子 ([Visual Basic の比較演算子](comparison-operators.md))</span><span class="sxs-lookup"><span data-stu-id="c1081-135">`<>` Operator ([Comparison Operators in Visual Basic](comparison-operators.md))</span></span>|  
|<span data-ttu-id="c1081-136">ある値がもう 1 つの値より小さいかどうかを判断します</span><span class="sxs-lookup"><span data-stu-id="c1081-136">Determine whether one value is less than another</span></span>|<span data-ttu-id="c1081-137">`<` 演算子 ([Visual Basic の比較演算子](comparison-operators.md))</span><span class="sxs-lookup"><span data-stu-id="c1081-137">`<` Operator ([Comparison Operators in Visual Basic](comparison-operators.md))</span></span>|  
|<span data-ttu-id="c1081-138">ある値がもう 1 つの値より大きいかどうかを判断します</span><span class="sxs-lookup"><span data-stu-id="c1081-138">Determine whether one value is greater than another</span></span>|<span data-ttu-id="c1081-139">`>` 演算子 ([Visual Basic の比較演算子](comparison-operators.md))</span><span class="sxs-lookup"><span data-stu-id="c1081-139">`>` Operator ([Comparison Operators in Visual Basic](comparison-operators.md))</span></span>|  
|<span data-ttu-id="c1081-140">ある値がもう 1 つの値以下かどうかを判断します</span><span class="sxs-lookup"><span data-stu-id="c1081-140">Determine whether one value is less than or equal to another</span></span>|<span data-ttu-id="c1081-141">`<=` 演算子 ([Visual Basic の比較演算子](comparison-operators.md))</span><span class="sxs-lookup"><span data-stu-id="c1081-141">`<=` Operator ([Comparison Operators in Visual Basic](comparison-operators.md))</span></span>|  
|<span data-ttu-id="c1081-142">ある値がもう 1 つの値以上かどうかを判断します</span><span class="sxs-lookup"><span data-stu-id="c1081-142">Determine whether one value is greater than or equal to another</span></span>|<span data-ttu-id="c1081-143">`>=` 演算子 ([Visual Basic の比較演算子](comparison-operators.md))</span><span class="sxs-lookup"><span data-stu-id="c1081-143">`>=` Operator ([Comparison Operators in Visual Basic](comparison-operators.md))</span></span>|  
|<span data-ttu-id="c1081-144">2 つのオブジェクト変数が同じオブジェクト インスタンスを参照しているかどうかを判断します</span><span class="sxs-lookup"><span data-stu-id="c1081-144">Determine whether two object variables refer to the same object instance</span></span>|[<span data-ttu-id="c1081-145">Is 演算子</span><span class="sxs-lookup"><span data-stu-id="c1081-145">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)|  
|<span data-ttu-id="c1081-146">2 つのオブジェクト変数が異なるオブジェクト インスタンスを参照しているかどうかを判断します</span><span class="sxs-lookup"><span data-stu-id="c1081-146">Determine whether two object variables refer to different object instances</span></span>|[<span data-ttu-id="c1081-147">IsNot 演算子</span><span class="sxs-lookup"><span data-stu-id="c1081-147">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)|  
|<span data-ttu-id="c1081-148">オブジェクトが特定の型であるかどうかを判断します</span><span class="sxs-lookup"><span data-stu-id="c1081-148">Determine whether an object is of a specific type</span></span>|[<span data-ttu-id="c1081-149">TypeOf 演算子</span><span class="sxs-lookup"><span data-stu-id="c1081-149">TypeOf Operator</span></span>](../../../language-reference/operators/typeof-operator.md)|  
  
## <a name="concatenation-tasks"></a><span data-ttu-id="c1081-150">連結タスク</span><span class="sxs-lookup"><span data-stu-id="c1081-150">Concatenation Tasks</span></span>  

 <span data-ttu-id="c1081-151">次の表は、使用できる連結演算をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="c1081-151">The following table summarizes the available concatenation operations.</span></span>  
  
|<span data-ttu-id="c1081-152">終了</span><span class="sxs-lookup"><span data-stu-id="c1081-152">To</span></span>|<span data-ttu-id="c1081-153">解決方法については、</span><span class="sxs-lookup"><span data-stu-id="c1081-153">See</span></span>|  
|---|---|  
|<span data-ttu-id="c1081-154">複数の文字列を 1 つの文字列に結合します</span><span class="sxs-lookup"><span data-stu-id="c1081-154">Join multiple strings into a single string</span></span>|<span data-ttu-id="c1081-155">`&` 演算子 ([Visual Basic の連結演算子](concatenation-operators.md))</span><span class="sxs-lookup"><span data-stu-id="c1081-155">`&` Operator ([Concatenation Operators in Visual Basic](concatenation-operators.md))</span></span>|  
|<span data-ttu-id="c1081-156">数値と文字列値を結合します</span><span class="sxs-lookup"><span data-stu-id="c1081-156">Join numeric values with string values</span></span>|<span data-ttu-id="c1081-157">`+` 演算子 ([Visual Basic の連結演算子](concatenation-operators.md))</span><span class="sxs-lookup"><span data-stu-id="c1081-157">`+` Operator ([Concatenation Operators in Visual Basic](concatenation-operators.md))</span></span>|  
  
## <a name="logical-and-bitwise-tasks"></a><span data-ttu-id="c1081-158">論理タスクとビットごとのタスク</span><span class="sxs-lookup"><span data-stu-id="c1081-158">Logical and Bitwise Tasks</span></span>  

 <span data-ttu-id="c1081-159">次の表は、使用できる論理演算とビットごとの演算をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="c1081-159">The following table summarizes the available logical and bitwise operations.</span></span>  
  
|<span data-ttu-id="c1081-160">終了</span><span class="sxs-lookup"><span data-stu-id="c1081-160">To</span></span>|<span data-ttu-id="c1081-161">解決方法については、</span><span class="sxs-lookup"><span data-stu-id="c1081-161">See</span></span>|  
|---|---|  
|<span data-ttu-id="c1081-162">ブール値に対して論理否定を実行します</span><span class="sxs-lookup"><span data-stu-id="c1081-162">Perform logical negation on a Boolean value</span></span>|[<span data-ttu-id="c1081-163">Not 演算子</span><span class="sxs-lookup"><span data-stu-id="c1081-163">Not Operator</span></span>](../../../language-reference/operators/not-operator.md)|  
|<span data-ttu-id="c1081-164">2 つのブール値に対して論理積を実行します</span><span class="sxs-lookup"><span data-stu-id="c1081-164">Perform logical conjunction on two Boolean values</span></span>|[<span data-ttu-id="c1081-165">And 演算子</span><span class="sxs-lookup"><span data-stu-id="c1081-165">And Operator</span></span>](../../../language-reference/operators/and-operator.md)|  
|<span data-ttu-id="c1081-166">2 つのブール値に対して包括的論理和演算を実行します</span><span class="sxs-lookup"><span data-stu-id="c1081-166">Perform inclusive logical disjunction on two Boolean values</span></span>|[<span data-ttu-id="c1081-167">Or 演算子</span><span class="sxs-lookup"><span data-stu-id="c1081-167">Or Operator</span></span>](../../../language-reference/operators/or-operator.md)|  
|<span data-ttu-id="c1081-168">2 つのブール値に対して排他的論理和演算を実行します</span><span class="sxs-lookup"><span data-stu-id="c1081-168">Perform exclusive logical disjunction on two Boolean values</span></span>|[<span data-ttu-id="c1081-169">Xor 演算子</span><span class="sxs-lookup"><span data-stu-id="c1081-169">Xor Operator</span></span>](../../../language-reference/operators/xor-operator.md)|  
|<span data-ttu-id="c1081-170">2 つのブール値に対して短絡論理積を実行します</span><span class="sxs-lookup"><span data-stu-id="c1081-170">Perform short-circuited logical conjunction on two Boolean values</span></span>|[<span data-ttu-id="c1081-171">AndAlso 演算子</span><span class="sxs-lookup"><span data-stu-id="c1081-171">AndAlso Operator</span></span>](../../../language-reference/operators/andalso-operator.md)|  
|<span data-ttu-id="c1081-172">2 つのブール値に対して短絡包括的論理和演算を実行します</span><span class="sxs-lookup"><span data-stu-id="c1081-172">Perform short-circuited inclusive logical disjunction on two Boolean values</span></span>|[<span data-ttu-id="c1081-173">OrElse 演算子</span><span class="sxs-lookup"><span data-stu-id="c1081-173">OrElse Operator</span></span>](../../../language-reference/operators/orelse-operator.md)|  
|<span data-ttu-id="c1081-174">2 つの整数値に対してビット単位の論理積を実行します</span><span class="sxs-lookup"><span data-stu-id="c1081-174">Perform bit-by-bit logical conjunction on two integral values</span></span>|[<span data-ttu-id="c1081-175">And 演算子</span><span class="sxs-lookup"><span data-stu-id="c1081-175">And Operator</span></span>](../../../language-reference/operators/and-operator.md)|  
|<span data-ttu-id="c1081-176">2 つの整数値に対してビット単位の包括的論理和演算を実行します</span><span class="sxs-lookup"><span data-stu-id="c1081-176">Perform bit-by-bit inclusive logical disjunction on two integral values</span></span>|[<span data-ttu-id="c1081-177">Or 演算子</span><span class="sxs-lookup"><span data-stu-id="c1081-177">Or Operator</span></span>](../../../language-reference/operators/or-operator.md)|  
|<span data-ttu-id="c1081-178">2 つの整数値に対してビット単位の排他的論理和演算を実行します</span><span class="sxs-lookup"><span data-stu-id="c1081-178">Perform bit-by-bit exclusive logical disjunction on two integral values</span></span>|[<span data-ttu-id="c1081-179">Xor 演算子</span><span class="sxs-lookup"><span data-stu-id="c1081-179">Xor Operator</span></span>](../../../language-reference/operators/xor-operator.md)|  
|<span data-ttu-id="c1081-180">整数値に対してビット単位の論理否定を実行します</span><span class="sxs-lookup"><span data-stu-id="c1081-180">Perform bit-by-bit logical negation on an integral value</span></span>|[<span data-ttu-id="c1081-181">Not 演算子</span><span class="sxs-lookup"><span data-stu-id="c1081-181">Not Operator</span></span>](../../../language-reference/operators/not-operator.md)|  
  
## <a name="see-also"></a><span data-ttu-id="c1081-182">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1081-182">See also</span></span>

- [<span data-ttu-id="c1081-183">演算子および式</span><span class="sxs-lookup"><span data-stu-id="c1081-183">Operators and Expressions</span></span>](index.md)
- [<span data-ttu-id="c1081-184">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="c1081-184">Operators Listed by Functionality</span></span>](../../../language-reference/operators/operators-listed-by-functionality.md)
