---
title: If 演算子
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
ms.openlocfilehash: 3b45a5afe331bd00c2b92f8c305351b77bc319cf
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249488"
---
# <a name="if-operator-visual-basic"></a><span data-ttu-id="3b9e6-102">If 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b9e6-102">If Operator (Visual Basic)</span></span>

<span data-ttu-id="3b9e6-103">短絡評価を使用して、条件的に 2 つの値のいずれかを返します。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-103">Uses short-circuit evaluation to conditionally return one of two values.</span></span> <span data-ttu-id="3b9e6-104">演算子`If`は、3 つの引数または 2 つの引数を使用して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-104">The `If` operator can be called with three arguments or with two arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="3b9e6-105">構文</span><span class="sxs-lookup"><span data-stu-id="3b9e6-105">Syntax</span></span>

```vb
If( [argument1,] argument2, argument3 )
```

## <a name="if-operator-called-with-three-arguments"></a><span data-ttu-id="3b9e6-106">演算子が 3 つの引数で呼び出された場合</span><span class="sxs-lookup"><span data-stu-id="3b9e6-106">If operator called with three arguments</span></span>

<span data-ttu-id="3b9e6-107">3`If`つの引数を使用して呼び出された場合、最初の引数は`Boolean`、 としてキャストできる値に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-107">When `If` is called by using three arguments, the first argument must evaluate to a value that can be cast as a `Boolean`.</span></span> <span data-ttu-id="3b9e6-108">この`Boolean`値によって、他の 2 つの引数のうち、評価されて返される引数が決まります。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-108">That `Boolean` value will determine which of the other two arguments is evaluated and returned.</span></span> <span data-ttu-id="3b9e6-109">次のリストは、演算子が`If`3 つの引数を使用して呼び出された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-109">The following list applies only when the `If` operator is called by using three arguments.</span></span>

### <a name="parts"></a><span data-ttu-id="3b9e6-110">要素</span><span class="sxs-lookup"><span data-stu-id="3b9e6-110">Parts</span></span>

|<span data-ttu-id="3b9e6-111">期間</span><span class="sxs-lookup"><span data-stu-id="3b9e6-111">Term</span></span>|<span data-ttu-id="3b9e6-112">定義</span><span class="sxs-lookup"><span data-stu-id="3b9e6-112">Definition</span></span>|
|---|---|
|`argument1`|<span data-ttu-id="3b9e6-113">必須。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-113">Required.</span></span> <span data-ttu-id="3b9e6-114">`Boolean`.</span><span class="sxs-lookup"><span data-stu-id="3b9e6-114">`Boolean`.</span></span> <span data-ttu-id="3b9e6-115">評価して返す他の引数を決定します。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-115">Determines which of the other arguments to evaluate and return.</span></span>|
|`argument2`|<span data-ttu-id="3b9e6-116">必須。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-116">Required.</span></span> <span data-ttu-id="3b9e6-117">`Object`.</span><span class="sxs-lookup"><span data-stu-id="3b9e6-117">`Object`.</span></span> <span data-ttu-id="3b9e6-118">評価され、評価`argument1`された場合に`True`返されます。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-118">Evaluated and returned if `argument1` evaluates to `True`.</span></span>|
|`argument3`|<span data-ttu-id="3b9e6-119">必須。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-119">Required.</span></span> <span data-ttu-id="3b9e6-120">`Object`.</span><span class="sxs-lookup"><span data-stu-id="3b9e6-120">`Object`.</span></span> <span data-ttu-id="3b9e6-121">評価され、評価`argument1`された場合、`False`または`argument1`Nothing[に評価](../../../visual-basic/language-reference/nothing.md)される[Null 許容](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean`変数かどうかが返されます。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-121">Evaluated and returned if `argument1` evaluates to `False` or if `argument1` is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span>|

<span data-ttu-id="3b9e6-122">3`If`つの引数を指定して呼び出される`IIf`演算子は、短絡評価を使用する点を除いて関数と同様に機能します。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-122">An `If` operator that is called with three arguments works like an `IIf` function except that it uses short-circuit evaluation.</span></span> <span data-ttu-id="3b9e6-123">関数`IIf`は常に 3 つの引数すべてを評価しますが`If`、3 つの引数を持つ演算子では 2 つの引数のみが評価されます。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-123">An `IIf` function always evaluates all three of its arguments, whereas an `If` operator that has three arguments evaluates only two of them.</span></span> <span data-ttu-id="3b9e6-124">最初`If`の引数が評価され、結果が`Boolean`値としてキャスト`True`されます。 `False`</span><span class="sxs-lookup"><span data-stu-id="3b9e6-124">The first `If` argument is evaluated and the result is cast as a `Boolean` value, `True` or `False`.</span></span> <span data-ttu-id="3b9e6-125">値が`True`の`argument2`場合は、評価され、その値は返`argument3`されますが、評価されません。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-125">If the value is `True`, `argument2` is evaluated and its value is returned, but `argument3` is not evaluated.</span></span> <span data-ttu-id="3b9e6-126">`Boolean`式の値が の`argument3`場合`False`は、評価され、その値は返されますが`argument2`、評価されません。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-126">If the value of the `Boolean` expression is `False`, `argument3` is evaluated and its value is returned, but `argument2` is not evaluated.</span></span> <span data-ttu-id="3b9e6-127">次の例は、3`If`つの引数を使用する場合の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-127">The following examples illustrate the use of `If` when three arguments are used:</span></span>

[!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]

<span data-ttu-id="3b9e6-128">次の例は、短絡評価の値を示しています。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-128">The following example illustrates the value of short-circuit evaluation.</span></span> <span data-ttu-id="3b9e6-129">この例では、変数で`number``divisor``divisor`変数を除いて変数を除いて変数を除く 2 つの試みが示されています。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-129">The example shows two attempts to divide variable `number` by variable `divisor` except when `divisor` is zero.</span></span> <span data-ttu-id="3b9e6-130">この場合は、0 を返す必要があり、ランタイム エラーが発生するため、除算を実行する試行は行いません。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-130">In that case, a 0 should be returned, and no attempt should be made to perform the division because a run-time error would result.</span></span> <span data-ttu-id="3b9e6-131">式は`If`短絡評価を使用するため、最初の引数の値に応じて、2 番目または 3 番目の引数を評価します。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-131">Because the `If` expression uses short-circuit evaluation, it evaluates either the second or the third argument, depending on the value of the first argument.</span></span> <span data-ttu-id="3b9e6-132">最初の引数が true の場合、除数はゼロではなく、2 番目の引数を評価して除算を実行しても安全です。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-132">If the first argument is true, the divisor is not zero and it is safe to evaluate the second argument and perform the division.</span></span> <span data-ttu-id="3b9e6-133">最初の引数が false の場合、3 番目の引数のみが評価され、0 が返されます。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-133">If the first argument is false, only the third argument is evaluated and a 0 is returned.</span></span> <span data-ttu-id="3b9e6-134">したがって、除数が 0 の場合、除算の実行は試行されず、エラー結果も発生しません。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-134">Therefore, when the divisor is 0, no attempt is made to perform the division and no error results.</span></span> <span data-ttu-id="3b9e6-135">ただし、短`IIf`絡評価を使用しないため、最初の引数が false の場合でも 2 番目の引数が評価されます。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-135">However, because `IIf` does not use short-circuit evaluation, the second argument is evaluated even when the first argument is false.</span></span> <span data-ttu-id="3b9e6-136">これにより、実行時の 0 除算エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-136">This causes a run-time divide-by-zero error.</span></span>

[!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]

## <a name="if-operator-called-with-two-arguments"></a><span data-ttu-id="3b9e6-137">演算子が 2 つの引数で呼び出された場合</span><span class="sxs-lookup"><span data-stu-id="3b9e6-137">If operator called with two arguments</span></span>

<span data-ttu-id="3b9e6-138">最初の引数は`If`省略できます。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-138">The first argument to `If` can be omitted.</span></span> <span data-ttu-id="3b9e6-139">これにより、演算子は 2 つの引数のみを使用して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-139">This enables the operator to be called by using only two arguments.</span></span> <span data-ttu-id="3b9e6-140">次のリストは、演算子が`If`2 つの引数で呼び出された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-140">The following list applies only when the `If` operator is called with two arguments.</span></span>

### <a name="parts"></a><span data-ttu-id="3b9e6-141">要素</span><span class="sxs-lookup"><span data-stu-id="3b9e6-141">Parts</span></span>

|<span data-ttu-id="3b9e6-142">期間</span><span class="sxs-lookup"><span data-stu-id="3b9e6-142">Term</span></span>|<span data-ttu-id="3b9e6-143">定義</span><span class="sxs-lookup"><span data-stu-id="3b9e6-143">Definition</span></span>|
|---|---|
|`argument2`|<span data-ttu-id="3b9e6-144">必須。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-144">Required.</span></span> <span data-ttu-id="3b9e6-145">`Object`.</span><span class="sxs-lookup"><span data-stu-id="3b9e6-145">`Object`.</span></span> <span data-ttu-id="3b9e6-146">参照または null 許容値型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-146">Must be a reference or nullable value type.</span></span> <span data-ttu-id="3b9e6-147">評価され、 以外`Nothing`の値に評価されると返されます。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-147">Evaluated and returned when it evaluates to anything other than `Nothing`.</span></span>|
|`argument3`|<span data-ttu-id="3b9e6-148">必須。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-148">Required.</span></span> <span data-ttu-id="3b9e6-149">`Object`.</span><span class="sxs-lookup"><span data-stu-id="3b9e6-149">`Object`.</span></span> <span data-ttu-id="3b9e6-150">評価され、評価`argument2`された場合に`Nothing`返されます。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-150">Evaluated and returned if `argument2` evaluates to `Nothing`.</span></span>|

<span data-ttu-id="3b9e6-151">引数を`Boolean`省略する場合、最初の引数は参照または null 許容値型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-151">When the `Boolean` argument is omitted, the first argument must be a reference or nullable value type.</span></span> <span data-ttu-id="3b9e6-152">最初の引数が`Nothing`に評価された場合、2 番目の引数の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-152">If the first argument evaluates to `Nothing`, the value of the second argument is returned.</span></span> <span data-ttu-id="3b9e6-153">それ以外の場合は、最初の引数の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-153">In all other cases, the value of the first argument is returned.</span></span> <span data-ttu-id="3b9e6-154">次の例は、この評価のしくみを示しています。</span><span class="sxs-lookup"><span data-stu-id="3b9e6-154">The following example illustrates how this evaluation works:</span></span>

[!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]

## <a name="see-also"></a><span data-ttu-id="3b9e6-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b9e6-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [<span data-ttu-id="3b9e6-156">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="3b9e6-156">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="3b9e6-157">Nothing</span><span class="sxs-lookup"><span data-stu-id="3b9e6-157">Nothing</span></span>](../nothing.md)
