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
ms.openlocfilehash: 483b58dd9c79c716fdc3d272cf699e33dec9c671
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799016"
---
# <a name="if-operator-visual-basic"></a><span data-ttu-id="0b2de-102">If 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b2de-102">If Operator (Visual Basic)</span></span>

<span data-ttu-id="0b2de-103">は、ショートサーキット評価を使用して、条件に応じて2つの値のいずれかを返します。</span><span class="sxs-lookup"><span data-stu-id="0b2de-103">Uses short-circuit evaluation to conditionally return one of two values.</span></span> <span data-ttu-id="0b2de-104">`If` 演算子は、3つの引数または2つの引数を指定して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="0b2de-104">The `If` operator can be called with three arguments or with two arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="0b2de-105">構文</span><span class="sxs-lookup"><span data-stu-id="0b2de-105">Syntax</span></span>

```vb
If( [argument1,] argument2, argument3 )
```

## <a name="if-operator-called-with-three-arguments"></a><span data-ttu-id="0b2de-106">3つの引数を指定して演算子が呼び出された場合</span><span class="sxs-lookup"><span data-stu-id="0b2de-106">If operator called with three arguments</span></span>

<span data-ttu-id="0b2de-107">3つの引数を使用して `If` が呼び出された場合、最初の引数は `Boolean`としてキャストできる値に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b2de-107">When `If` is called by using three arguments, the first argument must evaluate to a value that can be cast as a `Boolean`.</span></span> <span data-ttu-id="0b2de-108">この `Boolean` 値によって、他の2つの引数のどちらが評価され、返されるかが決まります。</span><span class="sxs-lookup"><span data-stu-id="0b2de-108">That `Boolean` value will determine which of the other two arguments is evaluated and returned.</span></span> <span data-ttu-id="0b2de-109">次の一覧は、3つの引数を使用して `If` 演算子が呼び出された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="0b2de-109">The following list applies only when the `If` operator is called by using three arguments.</span></span>

### <a name="parts"></a><span data-ttu-id="0b2de-110">指定項目</span><span class="sxs-lookup"><span data-stu-id="0b2de-110">Parts</span></span>

|<span data-ttu-id="0b2de-111">用語</span><span class="sxs-lookup"><span data-stu-id="0b2de-111">Term</span></span>|<span data-ttu-id="0b2de-112">定義</span><span class="sxs-lookup"><span data-stu-id="0b2de-112">Definition</span></span>|
|---|---|
|`argument1`|<span data-ttu-id="0b2de-113">必須です。</span><span class="sxs-lookup"><span data-stu-id="0b2de-113">Required.</span></span> <span data-ttu-id="0b2de-114">`Boolean`.</span><span class="sxs-lookup"><span data-stu-id="0b2de-114">`Boolean`.</span></span> <span data-ttu-id="0b2de-115">他のどの引数を評価して返すかを決定します。</span><span class="sxs-lookup"><span data-stu-id="0b2de-115">Determines which of the other arguments to evaluate and return.</span></span>|
|`argument2`|<span data-ttu-id="0b2de-116">必須です。</span><span class="sxs-lookup"><span data-stu-id="0b2de-116">Required.</span></span> <span data-ttu-id="0b2de-117">`Object`.</span><span class="sxs-lookup"><span data-stu-id="0b2de-117">`Object`.</span></span> <span data-ttu-id="0b2de-118">評価され、`argument1` が `True`に評価される場合に返されます。</span><span class="sxs-lookup"><span data-stu-id="0b2de-118">Evaluated and returned if `argument1` evaluates to `True`.</span></span>|
|`argument3`|<span data-ttu-id="0b2de-119">必須です。</span><span class="sxs-lookup"><span data-stu-id="0b2de-119">Required.</span></span> <span data-ttu-id="0b2de-120">`Object`.</span><span class="sxs-lookup"><span data-stu-id="0b2de-120">`Object`.</span></span> <span data-ttu-id="0b2de-121">`argument1` が `False` と評価された場合、または `argument1` が[Nothing](../../../visual-basic/language-reference/nothing.md)に評価される[null 許容](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)の`Boolean` 変数である場合に評価され、返されます。</span><span class="sxs-lookup"><span data-stu-id="0b2de-121">Evaluated and returned if `argument1` evaluates to `False` or if `argument1` is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span>|

<span data-ttu-id="0b2de-122">3つの引数を指定して呼び出される `If` 演算子は、ショートサーキット評価を使用する点を除いて、`IIf` 関数と同様に機能します。</span><span class="sxs-lookup"><span data-stu-id="0b2de-122">An `If` operator that is called with three arguments works like an `IIf` function except that it uses short-circuit evaluation.</span></span> <span data-ttu-id="0b2de-123">`IIf` 関数は、常に3つの引数をすべて評価します。一方、3つの引数を持つ `If` 演算子は、そのうち2つだけを評価します。</span><span class="sxs-lookup"><span data-stu-id="0b2de-123">An `IIf` function always evaluates all three of its arguments, whereas an `If` operator that has three arguments evaluates only two of them.</span></span> <span data-ttu-id="0b2de-124">最初の `If` 引数が評価され、結果は `Boolean` 値、`True`、または `False`としてキャストされます。</span><span class="sxs-lookup"><span data-stu-id="0b2de-124">The first `If` argument is evaluated and the result is cast as a `Boolean` value, `True` or `False`.</span></span> <span data-ttu-id="0b2de-125">値が `True`場合、`argument2` が評価され、その値が返されますが、`argument3` は評価されません。</span><span class="sxs-lookup"><span data-stu-id="0b2de-125">If the value is `True`, `argument2` is evaluated and its value is returned, but `argument3` is not evaluated.</span></span> <span data-ttu-id="0b2de-126">`Boolean` 式の値が `False`場合、`argument3` が評価され、その値が返されますが、`argument2` は評価されません。</span><span class="sxs-lookup"><span data-stu-id="0b2de-126">If the value of the `Boolean` expression is `False`, `argument3` is evaluated and its value is returned, but `argument2` is not evaluated.</span></span> <span data-ttu-id="0b2de-127">次の例は、3つの引数を使用する場合の `If` の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0b2de-127">The following examples illustrate the use of `If` when three arguments are used:</span></span>

[!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]

<span data-ttu-id="0b2de-128">次の例は、ショートサーキット評価の値を示しています。</span><span class="sxs-lookup"><span data-stu-id="0b2de-128">The following example illustrates the value of short-circuit evaluation.</span></span> <span data-ttu-id="0b2de-129">この例では、`divisor` がゼロの場合を除き、変数 `divisor` によって変数 `number` を分割する2回の試行を示しています。</span><span class="sxs-lookup"><span data-stu-id="0b2de-129">The example shows two attempts to divide variable `number` by variable `divisor` except when `divisor` is zero.</span></span> <span data-ttu-id="0b2de-130">この場合、0が返されます。実行時エラーが発生するため、除算を行わないでください。</span><span class="sxs-lookup"><span data-stu-id="0b2de-130">In that case, a 0 should be returned, and no attempt should be made to perform the division because a run-time error would result.</span></span> <span data-ttu-id="0b2de-131">`If` 式ではショートサーキット評価が使用されるため、最初の引数の値に応じて、2番目または3番目の引数のいずれかが評価されます。</span><span class="sxs-lookup"><span data-stu-id="0b2de-131">Because the `If` expression uses short-circuit evaluation, it evaluates either the second or the third argument, depending on the value of the first argument.</span></span> <span data-ttu-id="0b2de-132">最初の引数が true の場合、除数はゼロではなく、2番目の引数を評価して除算を実行しても安全です。</span><span class="sxs-lookup"><span data-stu-id="0b2de-132">If the first argument is true, the divisor is not zero and it is safe to evaluate the second argument and perform the division.</span></span> <span data-ttu-id="0b2de-133">最初の引数が false の場合は、3番目の引数のみが評価され、0が返されます。</span><span class="sxs-lookup"><span data-stu-id="0b2de-133">If the first argument is false, only the third argument is evaluated and a 0 is returned.</span></span> <span data-ttu-id="0b2de-134">したがって、除数が0の場合、除算は実行されず、エラーも発生しません。</span><span class="sxs-lookup"><span data-stu-id="0b2de-134">Therefore, when the divisor is 0, no attempt is made to perform the division and no error results.</span></span> <span data-ttu-id="0b2de-135">ただし、`IIf` ではショートサーキット評価を使用しないため、最初の引数が false の場合でも2番目の引数が評価されます。</span><span class="sxs-lookup"><span data-stu-id="0b2de-135">However, because `IIf` does not use short-circuit evaluation, the second argument is evaluated even when the first argument is false.</span></span> <span data-ttu-id="0b2de-136">これにより、実行時の0除算エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="0b2de-136">This causes a run-time divide-by-zero error.</span></span>

[!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]

## <a name="if-operator-called-with-two-arguments"></a><span data-ttu-id="0b2de-137">2つの引数を指定して演算子が呼び出された場合</span><span class="sxs-lookup"><span data-stu-id="0b2de-137">If operator called with two arguments</span></span>

<span data-ttu-id="0b2de-138">`If` の最初の引数は省略できます。</span><span class="sxs-lookup"><span data-stu-id="0b2de-138">The first argument to `If` can be omitted.</span></span> <span data-ttu-id="0b2de-139">これにより、2つの引数のみを使用して演算子を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="0b2de-139">This enables the operator to be called by using only two arguments.</span></span> <span data-ttu-id="0b2de-140">次の一覧は、`If` 演算子が2つの引数を指定して呼び出された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="0b2de-140">The following list applies only when the `If` operator is called with two arguments.</span></span>

### <a name="parts"></a><span data-ttu-id="0b2de-141">指定項目</span><span class="sxs-lookup"><span data-stu-id="0b2de-141">Parts</span></span>

|<span data-ttu-id="0b2de-142">用語</span><span class="sxs-lookup"><span data-stu-id="0b2de-142">Term</span></span>|<span data-ttu-id="0b2de-143">定義</span><span class="sxs-lookup"><span data-stu-id="0b2de-143">Definition</span></span>|
|---|---|
|`argument2`|<span data-ttu-id="0b2de-144">必須です。</span><span class="sxs-lookup"><span data-stu-id="0b2de-144">Required.</span></span> <span data-ttu-id="0b2de-145">`Object`.</span><span class="sxs-lookup"><span data-stu-id="0b2de-145">`Object`.</span></span> <span data-ttu-id="0b2de-146">参照または null 許容型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b2de-146">Must be a reference or nullable type.</span></span> <span data-ttu-id="0b2de-147">評価され、`Nothing`以外のものに評価された場合に返されます。</span><span class="sxs-lookup"><span data-stu-id="0b2de-147">Evaluated and returned when it evaluates to anything other than `Nothing`.</span></span>|
|`argument3`|<span data-ttu-id="0b2de-148">必須です。</span><span class="sxs-lookup"><span data-stu-id="0b2de-148">Required.</span></span> <span data-ttu-id="0b2de-149">`Object`.</span><span class="sxs-lookup"><span data-stu-id="0b2de-149">`Object`.</span></span> <span data-ttu-id="0b2de-150">評価され、`argument2` が `Nothing`に評価される場合に返されます。</span><span class="sxs-lookup"><span data-stu-id="0b2de-150">Evaluated and returned if `argument2` evaluates to `Nothing`.</span></span>|

<span data-ttu-id="0b2de-151">`Boolean` 引数を省略した場合、最初の引数は参照または null 許容型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b2de-151">When the `Boolean` argument is omitted, the first argument must be a reference or nullable type.</span></span> <span data-ttu-id="0b2de-152">最初の引数が `Nothing`に評価された場合、2番目の引数の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="0b2de-152">If the first argument evaluates to `Nothing`, the value of the second argument is returned.</span></span> <span data-ttu-id="0b2de-153">それ以外の場合は、最初の引数の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="0b2de-153">In all other cases, the value of the first argument is returned.</span></span> <span data-ttu-id="0b2de-154">次の例は、この評価のしくみを示しています。</span><span class="sxs-lookup"><span data-stu-id="0b2de-154">The following example illustrates how this evaluation works:</span></span>

[!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]

## <a name="see-also"></a><span data-ttu-id="0b2de-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b2de-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [<span data-ttu-id="0b2de-156">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="0b2de-156">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="0b2de-157">Nothing</span><span class="sxs-lookup"><span data-stu-id="0b2de-157">Nothing</span></span>](../nothing.md)
