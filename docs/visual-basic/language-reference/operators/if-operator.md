---
title: If 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.IfOperator
- IfOperator
helpviewer_keywords:
- ternary operators [Visual Basic]
- conditional execution
- If expressions [Visual Basic]
- conditional operator [Visual Basic]
- If Operator [Visual Basic]
ms.assetid: dd56c9df-7cd4-442c-9ba6-20c70ee44c8f
ms.openlocfilehash: 9ab01755d75c91ce87acf83e7f406b26c466aef6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663506"
---
# <a name="if-operator-visual-basic"></a><span data-ttu-id="d33b1-102">If 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d33b1-102">If Operator (Visual Basic)</span></span>
<span data-ttu-id="d33b1-103">ショート サーキット評価の条件付きで 2 つの値のいずれかを返すを使用します。</span><span class="sxs-lookup"><span data-stu-id="d33b1-103">Uses short-circuit evaluation to conditionally return one of two values.</span></span> <span data-ttu-id="d33b1-104">`If`演算子は、3 つの引数と 2 つの引数に呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="d33b1-104">The `If` operator can be called with three arguments or with two arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d33b1-105">構文</span><span class="sxs-lookup"><span data-stu-id="d33b1-105">Syntax</span></span>  
  
```  
If( [argument1,] argument2, argument3 )  
```  
  
## <a name="if-operator-called-with-three-arguments"></a><span data-ttu-id="d33b1-106">演算子は、3 つの引数で呼び出された場合</span><span class="sxs-lookup"><span data-stu-id="d33b1-106">If Operator Called with Three Arguments</span></span>  
 <span data-ttu-id="d33b1-107">ときに`If`呼びますとしてキャスト可能な値に 3 つの引数を使用すると、最初の引数を評価する必要があります、`Boolean`します。</span><span class="sxs-lookup"><span data-stu-id="d33b1-107">When `If` is called by using three arguments, the first argument must evaluate to a value that can be cast as a `Boolean`.</span></span> <span data-ttu-id="d33b1-108">ある`Boolean`が評価され、返されるその他の 2 つの引数の値が決定されます。</span><span class="sxs-lookup"><span data-stu-id="d33b1-108">That `Boolean` value will determine which of the other two arguments is evaluated and returned.</span></span> <span data-ttu-id="d33b1-109">次の一覧に適用される場合にのみ、`If`演算子が 3 つの引数を使用して呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="d33b1-109">The following list applies only when the `If` operator is called by using three arguments.</span></span>  
  
## <a name="parts"></a><span data-ttu-id="d33b1-110">指定項目</span><span class="sxs-lookup"><span data-stu-id="d33b1-110">Parts</span></span>  
  
|<span data-ttu-id="d33b1-111">用語</span><span class="sxs-lookup"><span data-stu-id="d33b1-111">Term</span></span>|<span data-ttu-id="d33b1-112">定義</span><span class="sxs-lookup"><span data-stu-id="d33b1-112">Definition</span></span>|  
|---|---|  
|`argument1`|<span data-ttu-id="d33b1-113">必須。</span><span class="sxs-lookup"><span data-stu-id="d33b1-113">Required.</span></span> <span data-ttu-id="d33b1-114">`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="d33b1-114">`Boolean`.</span></span> <span data-ttu-id="d33b1-115">評価し、返すその他の引数のどちらを決定します。</span><span class="sxs-lookup"><span data-stu-id="d33b1-115">Determines which of the other arguments to evaluate and return.</span></span>|  
|`argument2`|<span data-ttu-id="d33b1-116">必須。</span><span class="sxs-lookup"><span data-stu-id="d33b1-116">Required.</span></span> <span data-ttu-id="d33b1-117">`Object`。</span><span class="sxs-lookup"><span data-stu-id="d33b1-117">`Object`.</span></span> <span data-ttu-id="d33b1-118">評価され、返された場合`argument1`に評価される`True`します。</span><span class="sxs-lookup"><span data-stu-id="d33b1-118">Evaluated and returned if `argument1` evaluates to `True`.</span></span>|  
|`argument3`|<span data-ttu-id="d33b1-119">必須。</span><span class="sxs-lookup"><span data-stu-id="d33b1-119">Required.</span></span> <span data-ttu-id="d33b1-120">`Object`。</span><span class="sxs-lookup"><span data-stu-id="d33b1-120">`Object`.</span></span> <span data-ttu-id="d33b1-121">評価され、返された場合`argument1`に評価される`False`場合`argument1`は、 [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean`に評価される変数[Nothing](../../../visual-basic/language-reference/nothing.md)します。</span><span class="sxs-lookup"><span data-stu-id="d33b1-121">Evaluated and returned if `argument1` evaluates to `False` or if `argument1` is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span>|  
  
 <span data-ttu-id="d33b1-122">`If`のように 3 つの引数で呼び出される演算子の動作、`IIf`関数を使用するショート サーキット評価します。</span><span class="sxs-lookup"><span data-stu-id="d33b1-122">An `If` operator that is called with three arguments works like an `IIf` function except that it uses short-circuit evaluation.</span></span> <span data-ttu-id="d33b1-123">`IIf`関数は、引数の 3 つすべてを常に評価は、`If`を 3 つの引数を持つ演算子が 2 つのみを評価します。</span><span class="sxs-lookup"><span data-stu-id="d33b1-123">An `IIf` function always evaluates all three of its arguments, whereas an `If` operator that has three arguments evaluates only two of them.</span></span> <span data-ttu-id="d33b1-124">最初の`If`引数が評価され、結果としてキャスト、`Boolean`値、`True`または`False`します。</span><span class="sxs-lookup"><span data-stu-id="d33b1-124">The first `If` argument is evaluated and the result is cast as a `Boolean` value, `True` or `False`.</span></span> <span data-ttu-id="d33b1-125">値が場合`True`、`argument2`が評価され、その値が返されますが、`argument3`は評価されません。</span><span class="sxs-lookup"><span data-stu-id="d33b1-125">If the value is `True`, `argument2` is evaluated and its value is returned, but `argument3` is not evaluated.</span></span> <span data-ttu-id="d33b1-126">場合の値、`Boolean`式が`False`、`argument3`が評価され、その値が返されますが、`argument2`は評価されません。</span><span class="sxs-lookup"><span data-stu-id="d33b1-126">If the value of the `Boolean` expression is `False`, `argument3` is evaluated and its value is returned, but `argument2` is not evaluated.</span></span> <span data-ttu-id="d33b1-127">次の例の使用方法を示します`If`3 つの引数を使用する場合。</span><span class="sxs-lookup"><span data-stu-id="d33b1-127">The following examples illustrate the use of `If` when three arguments are used:</span></span>  
  
 [!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]  
  
 <span data-ttu-id="d33b1-128">次の例では、値のショート サーキット評価します。</span><span class="sxs-lookup"><span data-stu-id="d33b1-128">The following example illustrates the value of short-circuit evaluation.</span></span> <span data-ttu-id="d33b1-129">変数を分割しようと 2 つの例を示します`number`変数によって`divisor`する場合を除く`divisor`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="d33b1-129">The example shows two attempts to divide variable `number` by variable `divisor` except when `divisor` is zero.</span></span> <span data-ttu-id="d33b1-130">その場合は、0 が返され、実行時エラーになるために、除算を実行する試行は行われません。</span><span class="sxs-lookup"><span data-stu-id="d33b1-130">In that case, a 0 should be returned, and no attempt should be made to perform the division because a run-time error would result.</span></span> <span data-ttu-id="d33b1-131">`If`ショート サーキット評価の式の使用、2 番目または 3 番目の引数の最初の引数の値に応じてのいずれかが評価されます。</span><span class="sxs-lookup"><span data-stu-id="d33b1-131">Because the `If` expression uses short-circuit evaluation, it evaluates either the second or the third argument, depending on the value of the first argument.</span></span> <span data-ttu-id="d33b1-132">最初の引数が true の場合除数 0 ではないと、2 番目の引数を評価し、除算を実行しても安全です。</span><span class="sxs-lookup"><span data-stu-id="d33b1-132">If the first argument is true, the divisor is not zero and it is safe to evaluate the second argument and perform the division.</span></span> <span data-ttu-id="d33b1-133">最初の引数が false の場合は、3 番目の引数のみが評価され、0 が返されます。</span><span class="sxs-lookup"><span data-stu-id="d33b1-133">If the first argument is false, only the third argument is evaluated and a 0 is returned.</span></span> <span data-ttu-id="d33b1-134">そのため、除数が 0 の場合は行われません、除算およびエラー結果を実行します。</span><span class="sxs-lookup"><span data-stu-id="d33b1-134">Therefore, when the divisor is 0, no attempt is made to perform the division and no error results.</span></span> <span data-ttu-id="d33b1-135">ただし、ため`IIf`は使いませんショート サーキット評価、最初の引数が false の場合も、2 番目の引数が評価されます。</span><span class="sxs-lookup"><span data-stu-id="d33b1-135">However, because `IIf` does not use short-circuit evaluation, the second argument is evaluated even when the first argument is false.</span></span> <span data-ttu-id="d33b1-136">これにより、実行時の 0 除算エラーです。</span><span class="sxs-lookup"><span data-stu-id="d33b1-136">This causes a run-time divide-by-zero error.</span></span>  
  
 [!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]  
  
## <a name="if-operator-called-with-two-arguments"></a><span data-ttu-id="d33b1-137">演算子は、2 つの引数で呼び出された場合</span><span class="sxs-lookup"><span data-stu-id="d33b1-137">If Operator Called with Two Arguments</span></span>  
 <span data-ttu-id="d33b1-138">最初の引数`If`を省略できます。</span><span class="sxs-lookup"><span data-stu-id="d33b1-138">The first argument to `If` can be omitted.</span></span> <span data-ttu-id="d33b1-139">これにより、オペレーターにのみ 2 つの引数を使用して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="d33b1-139">This enables the operator to be called by using only two arguments.</span></span> <span data-ttu-id="d33b1-140">次の一覧に適用される場合にのみ、`If`演算子が 2 つの引数と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d33b1-140">The following list applies only when the `If` operator is called with two arguments.</span></span>  
  
## <a name="parts"></a><span data-ttu-id="d33b1-141">指定項目</span><span class="sxs-lookup"><span data-stu-id="d33b1-141">Parts</span></span>  
  
|<span data-ttu-id="d33b1-142">用語</span><span class="sxs-lookup"><span data-stu-id="d33b1-142">Term</span></span>|<span data-ttu-id="d33b1-143">定義</span><span class="sxs-lookup"><span data-stu-id="d33b1-143">Definition</span></span>|  
|---|---|  
|`argument2`|<span data-ttu-id="d33b1-144">必須。</span><span class="sxs-lookup"><span data-stu-id="d33b1-144">Required.</span></span> <span data-ttu-id="d33b1-145">`Object`。</span><span class="sxs-lookup"><span data-stu-id="d33b1-145">`Object`.</span></span> <span data-ttu-id="d33b1-146">参照または null 許容型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d33b1-146">Must be a reference or nullable type.</span></span> <span data-ttu-id="d33b1-147">評価され、以外の値に評価するときに返される`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="d33b1-147">Evaluated and returned when it evaluates to anything other than `Nothing`.</span></span>|  
|`argument3`|<span data-ttu-id="d33b1-148">必須。</span><span class="sxs-lookup"><span data-stu-id="d33b1-148">Required.</span></span> <span data-ttu-id="d33b1-149">`Object`。</span><span class="sxs-lookup"><span data-stu-id="d33b1-149">`Object`.</span></span> <span data-ttu-id="d33b1-150">評価され、返された場合`argument2`に評価される`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="d33b1-150">Evaluated and returned if `argument2` evaluates to `Nothing`.</span></span>|  
  
 <span data-ttu-id="d33b1-151">ときに、`Boolean`引数を省略すると、最初の引数が参照または null 許容型にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d33b1-151">When the `Boolean` argument is omitted, the first argument must be a reference or nullable type.</span></span> <span data-ttu-id="d33b1-152">最初の引数が評価された場合`Nothing`、2 番目の引数の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="d33b1-152">If the first argument evaluates to `Nothing`, the value of the second argument is returned.</span></span> <span data-ttu-id="d33b1-153">その他のすべてのケースでは、最初の引数の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="d33b1-153">In all other cases, the value of the first argument is returned.</span></span> <span data-ttu-id="d33b1-154">次の例では、この評価のしくみを示しています。</span><span class="sxs-lookup"><span data-stu-id="d33b1-154">The following example illustrates how this evaluation works.</span></span>  
  
 [!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="d33b1-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="d33b1-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [<span data-ttu-id="d33b1-156">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="d33b1-156">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="d33b1-157">Nothing</span><span class="sxs-lookup"><span data-stu-id="d33b1-157">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
