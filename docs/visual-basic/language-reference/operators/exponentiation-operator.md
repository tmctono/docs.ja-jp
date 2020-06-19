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
ms.openlocfilehash: e139becf74ae367266a23513e18d0bdbdd24cdea
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371389"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="913e3-102">^ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="913e3-102">^ Operator (Visual Basic)</span></span>

<span data-ttu-id="913e3-103">一方の数値をもう一方の数値で累乗します。</span><span class="sxs-lookup"><span data-stu-id="913e3-103">Raises a number to the power of another number.</span></span>

## <a name="syntax"></a><span data-ttu-id="913e3-104">構文</span><span class="sxs-lookup"><span data-stu-id="913e3-104">Syntax</span></span>

```vb
number ^ exponent
```

## <a name="parts"></a><span data-ttu-id="913e3-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="913e3-105">Parts</span></span>

`number`\
<span data-ttu-id="913e3-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="913e3-106">Required.</span></span> <span data-ttu-id="913e3-107">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="913e3-107">Any numeric expression.</span></span>

`exponent`\
<span data-ttu-id="913e3-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="913e3-108">Required.</span></span> <span data-ttu-id="913e3-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="913e3-109">Any numeric expression.</span></span>

## <a name="result"></a><span data-ttu-id="913e3-110">結果</span><span class="sxs-lookup"><span data-stu-id="913e3-110">Result</span></span>

<span data-ttu-id="913e3-111">結果は、`number` を `exponent` で累乗したもので、常に `Double` 値になります。</span><span class="sxs-lookup"><span data-stu-id="913e3-111">The result is `number` raised to the power of `exponent`, always as a `Double` value.</span></span>

## <a name="supported-types"></a><span data-ttu-id="913e3-112">サポートされている型</span><span class="sxs-lookup"><span data-stu-id="913e3-112">Supported Types</span></span>

<span data-ttu-id="913e3-113">`Double`。</span><span class="sxs-lookup"><span data-stu-id="913e3-113">`Double`.</span></span> <span data-ttu-id="913e3-114">異なる型のオペランドはすべて `Double` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="913e3-114">Operands of any different type are converted to `Double`.</span></span>

## <a name="remarks"></a><span data-ttu-id="913e3-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="913e3-115">Remarks</span></span>

<span data-ttu-id="913e3-116">Visual Basic では、常に [Double データ型](../data-types/double-data-type.md)で指数演算が実行されます。</span><span class="sxs-lookup"><span data-stu-id="913e3-116">Visual Basic always performs exponentiation in the [Double Data Type](../data-types/double-data-type.md).</span></span>

<span data-ttu-id="913e3-117">`exponent` の値には、小数、負、またはその両方を指定できます。</span><span class="sxs-lookup"><span data-stu-id="913e3-117">The value of `exponent` can be fractional, negative, or both.</span></span>

<span data-ttu-id="913e3-118">1 つの式で複数の累乗が実行される場合、`^` 演算子は左から右の出現順に評価されます。</span><span class="sxs-lookup"><span data-stu-id="913e3-118">When more than one exponentiation is performed in a single expression, the `^` operator is evaluated as it is encountered from left to right.</span></span>

> [!NOTE]
> <span data-ttu-id="913e3-119">`^` 演算子は "*オーバーロード*" できます。つまり、オペランドの型がそのクラスまたは構造体であるとき、そのクラスまたは構造体でその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="913e3-119">The `^` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="913e3-120">コードで、そのようなクラスまたは構造体に対してこの演算子が使用される場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="913e3-120">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="913e3-121">詳細については、「 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="913e3-121">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="example"></a><span data-ttu-id="913e3-122">例</span><span class="sxs-lookup"><span data-stu-id="913e3-122">Example</span></span>

<span data-ttu-id="913e3-123">次の例では、`^` 演算子を使用して数値を指数で累乗します。</span><span class="sxs-lookup"><span data-stu-id="913e3-123">The following example uses the `^` operator to raise a number to the power of an exponent.</span></span> <span data-ttu-id="913e3-124">結果は、最初のオペランドを 2 番目のオペランドで累乗したものになります。</span><span class="sxs-lookup"><span data-stu-id="913e3-124">The result is the first operand raised to the power of the second.</span></span>

[!code-vb[VbVbalrOperators#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#20)]

<span data-ttu-id="913e3-125">前の例を実行すると、次の結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="913e3-125">The preceding example produces the following results:</span></span>

<span data-ttu-id="913e3-126">`exp1` は 4 (2 の 2 乗) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="913e3-126">`exp1` is set to 4 (2 squared).</span></span>

<span data-ttu-id="913e3-127">`exp2` は 19683 (3 を 3 乗してから、その値を 3 乗) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="913e3-127">`exp2` is set to 19683 (3 cubed, then that value cubed).</span></span>

<span data-ttu-id="913e3-128">`exp3` は -125 (-5 の 3 乗) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="913e3-128">`exp3` is set to -125 (-5 cubed).</span></span>

<span data-ttu-id="913e3-129">`exp4` は 625 (-5 の 4 乗) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="913e3-129">`exp4` is set to 625 (-5 to the fourth power).</span></span>

<span data-ttu-id="913e3-130">`exp5` は 2 (8 の立方根) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="913e3-130">`exp5` is set to 2 (cube root of 8).</span></span>

<span data-ttu-id="913e3-131">`exp6` は 0.5 (1.0 を 8 の立方根で除算) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="913e3-131">`exp6` is set to 0.5 (1.0 divided by the cube root of 8).</span></span>

<span data-ttu-id="913e3-132">上の例の式におけるかっこの重要性に注意してください。</span><span class="sxs-lookup"><span data-stu-id="913e3-132">Note the importance of the parentheses in the expressions in the preceding example.</span></span> <span data-ttu-id="913e3-133">"*演算子の優先順位*" のため、Visual Basic では、通常は `^` 演算子が、他の演算子 (単項演算子 `–` であっても) よりも前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="913e3-133">Because of *operator precedence*, Visual Basic normally performs the `^` operator before any others, even the unary `–` operator.</span></span> <span data-ttu-id="913e3-134">`exp4` と `exp6` がかっこなしで計算された場合、次のような結果になります。</span><span class="sxs-lookup"><span data-stu-id="913e3-134">If `exp4` and `exp6` had been calculated without parentheses, they would have produced the following results:</span></span>

<span data-ttu-id="913e3-135">`exp4 = -5 ^ 4` は -(5 の 4 乗) として計算されるため、結果は -625 になります。</span><span class="sxs-lookup"><span data-stu-id="913e3-135">`exp4 = -5 ^ 4` would be calculated as –(5 to the fourth power), which would result in -625.</span></span>

<span data-ttu-id="913e3-136">`exp6 = 8 ^ -1.0 / 3.0` は (8 の -1 乗、つまり 0.125) を 3.0 で除算として計算されるため、結果は 0.041666666666666666666666666666667 になります。</span><span class="sxs-lookup"><span data-stu-id="913e3-136">`exp6 = 8 ^ -1.0 / 3.0` would be calculated as (8 to the –1 power, or 0.125) divided by 3.0, which would result in 0.041666666666666666666666666666667.</span></span>

## <a name="see-also"></a><span data-ttu-id="913e3-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="913e3-137">See also</span></span>

- [<span data-ttu-id="913e3-138">^= 演算子</span><span class="sxs-lookup"><span data-stu-id="913e3-138">^= Operator</span></span>](exponentiation-assignment-operator.md)
- [<span data-ttu-id="913e3-139">算術演算子</span><span class="sxs-lookup"><span data-stu-id="913e3-139">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="913e3-140">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="913e3-140">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="913e3-141">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="913e3-141">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="913e3-142">Visual Basic における算術演算子</span><span class="sxs-lookup"><span data-stu-id="913e3-142">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
