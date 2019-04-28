---
title: ^ 演算子 (Visual Basic)
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
ms.openlocfilehash: 54de9c91d4e166b8ca1733952dfa9c98ebf11ffe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778496"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="b69e0-102">^ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b69e0-102">^ Operator (Visual Basic)</span></span>

<span data-ttu-id="b69e0-103">数値のべき乗する数値を生成します。</span><span class="sxs-lookup"><span data-stu-id="b69e0-103">Raises a number to the power of another number.</span></span>

## <a name="syntax"></a><span data-ttu-id="b69e0-104">構文</span><span class="sxs-lookup"><span data-stu-id="b69e0-104">Syntax</span></span>

```
number ^ exponent
```

## <a name="parts"></a><span data-ttu-id="b69e0-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="b69e0-105">Parts</span></span>

`number`\
<span data-ttu-id="b69e0-106">必須。</span><span class="sxs-lookup"><span data-stu-id="b69e0-106">Required.</span></span> <span data-ttu-id="b69e0-107">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="b69e0-107">Any numeric expression.</span></span>

`exponent`\
<span data-ttu-id="b69e0-108">必須。</span><span class="sxs-lookup"><span data-stu-id="b69e0-108">Required.</span></span> <span data-ttu-id="b69e0-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="b69e0-109">Any numeric expression.</span></span>

## <a name="result"></a><span data-ttu-id="b69e0-110">結果</span><span class="sxs-lookup"><span data-stu-id="b69e0-110">Result</span></span>

<span data-ttu-id="b69e0-111">結果は`number`の累乗`exponent`、として常に、`Double`値。</span><span class="sxs-lookup"><span data-stu-id="b69e0-111">The result is `number` raised to the power of `exponent`, always as a `Double` value.</span></span>

## <a name="supported-types"></a><span data-ttu-id="b69e0-112">サポートされている型</span><span class="sxs-lookup"><span data-stu-id="b69e0-112">Supported Types</span></span>

<span data-ttu-id="b69e0-113">`Double`。</span><span class="sxs-lookup"><span data-stu-id="b69e0-113">`Double`.</span></span> <span data-ttu-id="b69e0-114">さまざまな型のオペランドが変換されます`Double`します。</span><span class="sxs-lookup"><span data-stu-id="b69e0-114">Operands of any different type are converted to `Double`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b69e0-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="b69e0-115">Remarks</span></span>

<span data-ttu-id="b69e0-116">Visual Basic の指数演算を常に実行する、 [Double データ型](../../../visual-basic/language-reference/data-types/double-data-type.md)します。</span><span class="sxs-lookup"><span data-stu-id="b69e0-116">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span>

<span data-ttu-id="b69e0-117">値`exponent`、小数部は、負の値、またはその両方です。</span><span class="sxs-lookup"><span data-stu-id="b69e0-117">The value of `exponent` can be fractional, negative, or both.</span></span>

<span data-ttu-id="b69e0-118">1 つの式で複数の指数演算を実行すると、`^`左から右にした、演算子が評価されます。</span><span class="sxs-lookup"><span data-stu-id="b69e0-118">When more than one exponentiation is performed in a single expression, the `^` operator is evaluated as it is encountered from left to right.</span></span>

> [!NOTE]
> <span data-ttu-id="b69e0-119">`^`演算子は、*オーバー ロードされた*、つまり、ことクラスまたは構造体を再定義できますその動作はそのクラスまたは構造体の型。</span><span class="sxs-lookup"><span data-stu-id="b69e0-119">The `^` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="b69e0-120">コードは、このようなクラスまたは構造体に、この演算子を使用する場合は、再定義された動作を確認ください。</span><span class="sxs-lookup"><span data-stu-id="b69e0-120">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="b69e0-121">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b69e0-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="example"></a><span data-ttu-id="b69e0-122">例</span><span class="sxs-lookup"><span data-stu-id="b69e0-122">Example</span></span>

<span data-ttu-id="b69e0-123">次の例では、`^`演算子を使って数値の指数。</span><span class="sxs-lookup"><span data-stu-id="b69e0-123">The following example uses the `^` operator to raise a number to the power of an exponent.</span></span> <span data-ttu-id="b69e0-124">最初のオペランドが 2 番目の累乗になります。</span><span class="sxs-lookup"><span data-stu-id="b69e0-124">The result is the first operand raised to the power of the second.</span></span>

[!code-vb[VbVbalrOperators#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#20)]

<span data-ttu-id="b69e0-125">前の例では、次の結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="b69e0-125">The preceding example produces the following results:</span></span>

<span data-ttu-id="b69e0-126">`exp1` 4 (2 乗) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="b69e0-126">`exp1` is set to 4 (2 squared).</span></span>

<span data-ttu-id="b69e0-127">`exp2` 19683 (3 乗を 2 乗し、その値) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="b69e0-127">`exp2` is set to 19683 (3 cubed, then that value cubed).</span></span>

<span data-ttu-id="b69e0-128">`exp3` -125 (アイス -5) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="b69e0-128">`exp3` is set to -125 (-5 cubed).</span></span>

<span data-ttu-id="b69e0-129">`exp4` 625 (4 番目の電源を-5) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="b69e0-129">`exp4` is set to 625 (-5 to the fourth power).</span></span>

<span data-ttu-id="b69e0-130">`exp5` 2 (8 の立方根) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="b69e0-130">`exp5` is set to 2 (cube root of 8).</span></span>

<span data-ttu-id="b69e0-131">`exp6` 0.5 (8 の立方根で割った値 1.0) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="b69e0-131">`exp6` is set to 0.5 (1.0 divided by the cube root of 8).</span></span>

<span data-ttu-id="b69e0-132">上記の例の式のかっこの中の重要性に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b69e0-132">Note the importance of the parentheses in the expressions in the preceding example.</span></span> <span data-ttu-id="b69e0-133">ため*演算子の優先順位*、Visual Basic が通常は、`^`する前に、他の演算子も、単項`–`演算子。</span><span class="sxs-lookup"><span data-stu-id="b69e0-133">Because of *operator precedence*, Visual Basic normally performs the `^` operator before any others, even the unary `–` operator.</span></span> <span data-ttu-id="b69e0-134">場合`exp4`と`exp6`が計算されたかっこがない場合、次の結果を作成した場合します。</span><span class="sxs-lookup"><span data-stu-id="b69e0-134">If `exp4` and `exp6` had been calculated without parentheses, they would have produced the following results:</span></span>

<span data-ttu-id="b69e0-135">`exp4 = -5 ^ 4` -(4 番目の電源を 5) として計算されます-625 されると、します。</span><span class="sxs-lookup"><span data-stu-id="b69e0-135">`exp4 = -5 ^ 4` would be calculated as –(5 to the fourth power), which would result in -625.</span></span>

<span data-ttu-id="b69e0-136">`exp6 = 8 ^ -1.0 / 3.0` (– 1 の電源または 0.125 8) として計算は 3.0 では、0.041666666666666666666666666666667 なりますで割った値します。</span><span class="sxs-lookup"><span data-stu-id="b69e0-136">`exp6 = 8 ^ -1.0 / 3.0` would be calculated as (8 to the –1 power, or 0.125) divided by 3.0, which would result in 0.041666666666666666666666666666667.</span></span>

## <a name="see-also"></a><span data-ttu-id="b69e0-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="b69e0-137">See also</span></span>

- [<span data-ttu-id="b69e0-138">^= 演算子</span><span class="sxs-lookup"><span data-stu-id="b69e0-138">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [<span data-ttu-id="b69e0-139">算術演算子</span><span class="sxs-lookup"><span data-stu-id="b69e0-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="b69e0-140">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="b69e0-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="b69e0-141">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="b69e0-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="b69e0-142">Visual Basic における算術演算子</span><span class="sxs-lookup"><span data-stu-id="b69e0-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
