---
title: ^ 演算子
ms.date: 07/20/2015
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponentiation
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
ms.openlocfilehash: b9860b7b6e076fc9c0288818aa9e4f2c0fc4c356
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331105"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="7b07f-102">^ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b07f-102">^ Operator (Visual Basic)</span></span>

<span data-ttu-id="7b07f-103">数値を別の数値のべき乗で累乗します。</span><span class="sxs-lookup"><span data-stu-id="7b07f-103">Raises a number to the power of another number.</span></span>

## <a name="syntax"></a><span data-ttu-id="7b07f-104">構文</span><span class="sxs-lookup"><span data-stu-id="7b07f-104">Syntax</span></span>

```vb
number ^ exponent
```

## <a name="parts"></a><span data-ttu-id="7b07f-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="7b07f-105">Parts</span></span>

`number`\
<span data-ttu-id="7b07f-106">必須。</span><span class="sxs-lookup"><span data-stu-id="7b07f-106">Required.</span></span> <span data-ttu-id="7b07f-107">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="7b07f-107">Any numeric expression.</span></span>

`exponent`\
<span data-ttu-id="7b07f-108">必須。</span><span class="sxs-lookup"><span data-stu-id="7b07f-108">Required.</span></span> <span data-ttu-id="7b07f-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="7b07f-109">Any numeric expression.</span></span>

## <a name="result"></a><span data-ttu-id="7b07f-110">結果</span><span class="sxs-lookup"><span data-stu-id="7b07f-110">Result</span></span>

<span data-ttu-id="7b07f-111">結果は、`exponent`の累乗に `number`、常に `Double` 値として生成されます。</span><span class="sxs-lookup"><span data-stu-id="7b07f-111">The result is `number` raised to the power of `exponent`, always as a `Double` value.</span></span>

## <a name="supported-types"></a><span data-ttu-id="7b07f-112">サポートされている型</span><span class="sxs-lookup"><span data-stu-id="7b07f-112">Supported Types</span></span>

<span data-ttu-id="7b07f-113">`Double` で初期化します。</span><span class="sxs-lookup"><span data-stu-id="7b07f-113">`Double`.</span></span> <span data-ttu-id="7b07f-114">異なる型のオペランドは `Double`に変換されます。</span><span class="sxs-lookup"><span data-stu-id="7b07f-114">Operands of any different type are converted to `Double`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7b07f-115">コメント</span><span class="sxs-lookup"><span data-stu-id="7b07f-115">Remarks</span></span>

<span data-ttu-id="7b07f-116">Visual Basic は、常に[Double データ型](../../../visual-basic/language-reference/data-types/double-data-type.md)の指数演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="7b07f-116">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span>

<span data-ttu-id="7b07f-117">`exponent` の値には、小数、負、またはその両方を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7b07f-117">The value of `exponent` can be fractional, negative, or both.</span></span>

<span data-ttu-id="7b07f-118">1つの式で複数の指数演算が実行された場合、`^` 演算子は左から右に出現するように評価されます。</span><span class="sxs-lookup"><span data-stu-id="7b07f-118">When more than one exponentiation is performed in a single expression, the `^` operator is evaluated as it is encountered from left to right.</span></span>

> [!NOTE]
> <span data-ttu-id="7b07f-119">`^` 演算子は*オーバーロード*することができます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="7b07f-119">The `^` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="7b07f-120">コードでこのようなクラスまたは構造体に対してこの演算子を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7b07f-120">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="7b07f-121">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b07f-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="example"></a><span data-ttu-id="7b07f-122">例</span><span class="sxs-lookup"><span data-stu-id="7b07f-122">Example</span></span>

<span data-ttu-id="7b07f-123">次の例では、`^` 演算子を使用して指数の指数部に数値を累乗します。</span><span class="sxs-lookup"><span data-stu-id="7b07f-123">The following example uses the `^` operator to raise a number to the power of an exponent.</span></span> <span data-ttu-id="7b07f-124">結果は、2番目のオペランドの累乗になります。</span><span class="sxs-lookup"><span data-stu-id="7b07f-124">The result is the first operand raised to the power of the second.</span></span>

[!code-vb[VbVbalrOperators#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#20)]

<span data-ttu-id="7b07f-125">前の例では、次の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="7b07f-125">The preceding example produces the following results:</span></span>

<span data-ttu-id="7b07f-126">`exp1` が 4 (2 乗) に設定されています。</span><span class="sxs-lookup"><span data-stu-id="7b07f-126">`exp1` is set to 4 (2 squared).</span></span>

<span data-ttu-id="7b07f-127">`exp2` は 19683 (3 キューブ、そのキューブ) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="7b07f-127">`exp2` is set to 19683 (3 cubed, then that value cubed).</span></span>

<span data-ttu-id="7b07f-128">`exp3` が-125 (-5 キューブ) に設定されています。</span><span class="sxs-lookup"><span data-stu-id="7b07f-128">`exp3` is set to -125 (-5 cubed).</span></span>

<span data-ttu-id="7b07f-129">`exp4` は 625 (-5 ~ 4 乗) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="7b07f-129">`exp4` is set to 625 (-5 to the fourth power).</span></span>

<span data-ttu-id="7b07f-130">`exp5` が 2 (キューブルート 8) に設定されています。</span><span class="sxs-lookup"><span data-stu-id="7b07f-130">`exp5` is set to 2 (cube root of 8).</span></span>

<span data-ttu-id="7b07f-131">`exp6` は0.5 に設定されます (1.0 の8のルートで割った値)。</span><span class="sxs-lookup"><span data-stu-id="7b07f-131">`exp6` is set to 0.5 (1.0 divided by the cube root of 8).</span></span>

<span data-ttu-id="7b07f-132">前の例の式では、かっこの重要性に注意してください。</span><span class="sxs-lookup"><span data-stu-id="7b07f-132">Note the importance of the parentheses in the expressions in the preceding example.</span></span> <span data-ttu-id="7b07f-133">演算子の*優先順位*により、Visual Basic は通常、単項 `–` 演算子も含めて、`^` 演算子を実行します。</span><span class="sxs-lookup"><span data-stu-id="7b07f-133">Because of *operator precedence*, Visual Basic normally performs the `^` operator before any others, even the unary `–` operator.</span></span> <span data-ttu-id="7b07f-134">`exp4` と `exp6` がかっこなしで計算された場合、次の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="7b07f-134">If `exp4` and `exp6` had been calculated without parentheses, they would have produced the following results:</span></span>

<span data-ttu-id="7b07f-135">`exp4 = -5 ^ 4` は– (5 ~ 4 乗) として計算されます。この場合、-625 となります。</span><span class="sxs-lookup"><span data-stu-id="7b07f-135">`exp4 = -5 ^ 4` would be calculated as –(5 to the fourth power), which would result in -625.</span></span>

<span data-ttu-id="7b07f-136">`exp6 = 8 ^ -1.0 / 3.0` は、(8 から–1の累乗、または 0.125) を3.0 で割った値として計算され、0.041666666666666666666666666666667 になります。</span><span class="sxs-lookup"><span data-stu-id="7b07f-136">`exp6 = 8 ^ -1.0 / 3.0` would be calculated as (8 to the –1 power, or 0.125) divided by 3.0, which would result in 0.041666666666666666666666666666667.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b07f-137">参照</span><span class="sxs-lookup"><span data-stu-id="7b07f-137">See also</span></span>

- [<span data-ttu-id="7b07f-138">^= 演算子</span><span class="sxs-lookup"><span data-stu-id="7b07f-138">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [<span data-ttu-id="7b07f-139">算術演算子</span><span class="sxs-lookup"><span data-stu-id="7b07f-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="7b07f-140">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="7b07f-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="7b07f-141">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="7b07f-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="7b07f-142">Visual Basic の算術演算子</span><span class="sxs-lookup"><span data-stu-id="7b07f-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
