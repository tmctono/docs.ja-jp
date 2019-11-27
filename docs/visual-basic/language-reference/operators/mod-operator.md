---
title: Mod 演算子
ms.date: 04/24/2018
f1_keywords:
- vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
ms.openlocfilehash: b7552550d4b0496d6ad7ee76a7327054d544b874
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350915"
---
# <a name="mod-operator-visual-basic"></a><span data-ttu-id="1a1b3-102">Mod 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a1b3-102">Mod operator (Visual Basic)</span></span>

<span data-ttu-id="1a1b3-103">2つの数値を除算し、剰余だけを返します。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-103">Divides two numbers and returns only the remainder.</span></span>

## <a name="syntax"></a><span data-ttu-id="1a1b3-104">構文</span><span class="sxs-lookup"><span data-stu-id="1a1b3-104">Syntax</span></span>

```vb
result = number1 Mod number2
```

## <a name="parts"></a><span data-ttu-id="1a1b3-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="1a1b3-105">Parts</span></span>

`result` \
<span data-ttu-id="1a1b3-106">必須。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-106">Required.</span></span> <span data-ttu-id="1a1b3-107">任意の数値変数またはプロパティ。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-107">Any numeric variable or property.</span></span>

`number1` \
<span data-ttu-id="1a1b3-108">必須。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-108">Required.</span></span> <span data-ttu-id="1a1b3-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-109">Any numeric expression.</span></span>

`number2` \
<span data-ttu-id="1a1b3-110">必須。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-110">Required.</span></span> <span data-ttu-id="1a1b3-111">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-111">Any numeric expression.</span></span>

## <a name="supported-types"></a><span data-ttu-id="1a1b3-112">サポートされている型</span><span class="sxs-lookup"><span data-stu-id="1a1b3-112">Supported types</span></span>

<span data-ttu-id="1a1b3-113">すべての数値型。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-113">All numeric types.</span></span> <span data-ttu-id="1a1b3-114">これには、符号なしおよび浮動小数点型と `Decimal`が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-114">This includes the unsigned and floating-point types and `Decimal`.</span></span>

## <a name="result"></a><span data-ttu-id="1a1b3-115">結果</span><span class="sxs-lookup"><span data-stu-id="1a1b3-115">Result</span></span>

<span data-ttu-id="1a1b3-116">結果は、`number1` が `number2`で除算された後の剰余になります。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-116">The result is the remainder after `number1` is divided by `number2`.</span></span> <span data-ttu-id="1a1b3-117">たとえば、式 `14 Mod 4` は2に評価されます。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-117">For example, the expression `14 Mod 4` evaluates to 2.</span></span>

> [!NOTE]
> <span data-ttu-id="1a1b3-118">算術の*剰余*と*剰余*の違いはありますが、負の数値の結果は異なります。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-118">There is a difference between *remainder* and *modulus* in mathematics, with different results for negative numbers.</span></span> <span data-ttu-id="1a1b3-119">Visual Basic の `Mod` 演算子、.NET Framework `op_Modulus` 演算子、および基になる[rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL 命令はすべて、剰余演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-119">The `Mod` operator in Visual Basic, the .NET Framework `op_Modulus` operator, and the underlying [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL instruction all perform a remainder operation.</span></span>

<span data-ttu-id="1a1b3-120">`Mod` 操作の結果では、被除数の符号 (`number1`) が保持されるため、正または負のどちらの場合でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-120">The result of a `Mod` operation retains the sign of the dividend, `number1`, and so it may be positive or negative.</span></span> <span data-ttu-id="1a1b3-121">結果は常に (-`number2`、`number2`) の範囲内にあります。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-121">The result is always in the range (-`number2`, `number2`), exclusive.</span></span> <span data-ttu-id="1a1b3-122">例 :</span><span class="sxs-lookup"><span data-stu-id="1a1b3-122">For example:</span></span>

```vb
Public Module Example
   Public Sub Main()
      Console.WriteLine($" 8 Mod  3 = {8 Mod 3}")
      Console.WriteLine($"-8 Mod  3 = {-8 Mod 3}")
      Console.WriteLine($" 8 Mod -3 = {8 Mod -3}")
      Console.WriteLine($"-8 Mod -3 = {-8 Mod -3}")
   End Sub
End Module
' The example displays the following output:
'       8 Mod  3 = 2
'      -8 Mod  3 = -2
'       8 Mod -3 = 2
'      -8 Mod -3 = -2
```

## <a name="remarks"></a><span data-ttu-id="1a1b3-123">コメント</span><span class="sxs-lookup"><span data-stu-id="1a1b3-123">Remarks</span></span>

<span data-ttu-id="1a1b3-124">`number1` または `number2` のいずれかが浮動小数点値の場合は、除算の浮動小数点の剰余が返されます。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-124">If either `number1` or `number2` is a floating-point value, the floating-point remainder of the division is returned.</span></span> <span data-ttu-id="1a1b3-125">結果のデータ型は、`number1` および `number2`のデータ型との除算によって得られるすべての値を保持できる最小のデータ型です。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-125">The data type of the result is the smallest data type that can hold all possible values that result from division with the data types of `number1` and `number2`.</span></span>

<span data-ttu-id="1a1b3-126">`number1` または `number2` が[Nothing](../../../visual-basic/language-reference/nothing.md)と評価された場合、0として扱われます。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-126">If `number1` or `number2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>

<span data-ttu-id="1a1b3-127">関連する演算子は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-127">Related operators include the following:</span></span>

- <span data-ttu-id="1a1b3-128">[\ 演算子 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)は、除算の整数の商を返します。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-128">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient of a division.</span></span> <span data-ttu-id="1a1b3-129">たとえば、式 `14 \ 4` は3に評価されます。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-129">For example, the expression `14 \ 4` evaluates to 3.</span></span>

- <span data-ttu-id="1a1b3-130">[/演算子 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)は、剰余を含む完全な商を浮動小数点数として返します。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-130">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, including the remainder, as a floating-point number.</span></span> <span data-ttu-id="1a1b3-131">たとえば、式 `14 / 4` は3.5 に評価されます。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-131">For example, the expression `14 / 4` evaluates to 3.5.</span></span>

## <a name="attempted-division-by-zero"></a><span data-ttu-id="1a1b3-132">0による除算を試行しました</span><span class="sxs-lookup"><span data-stu-id="1a1b3-132">Attempted division by zero</span></span>

<span data-ttu-id="1a1b3-133">`number2` が0に評価される場合、`Mod` 演算子の動作は、オペランドのデータ型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-133">If `number2` evaluates to zero, the behavior of the `Mod` operator depends on the data type of the operands:</span></span>

- <span data-ttu-id="1a1b3-134">コンパイル時に `number2` を特定できず、コンパイル時にゼロに評価され `number2` た場合 `BC30542 Division by zero occurred while evaluating this expression` コンパイル時エラーを生成する場合、整数除算は <xref:System.DivideByZeroException> 例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-134">An integral division throws a <xref:System.DivideByZeroException> exception if `number2` cannot be determined in compile-time and generates a compile-time error `BC30542 Division by zero occurred while evaluating this expression` if `number2` is evaluated to zero at compile-time.</span></span>
- <span data-ttu-id="1a1b3-135">浮動小数点除算は <xref:System.Double.NaN?displayProperty=nameWithType>を返します。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-135">A floating-point division returns <xref:System.Double.NaN?displayProperty=nameWithType>.</span></span>

## <a name="equivalent-formula"></a><span data-ttu-id="1a1b3-136">同等の式</span><span class="sxs-lookup"><span data-stu-id="1a1b3-136">Equivalent formula</span></span>

<span data-ttu-id="1a1b3-137">`a Mod b` 式は、次の数式のいずれかに相当します。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-137">The expression `a Mod b` is equivalent to either of the following formulas:</span></span>

`a - (b * (a \ b))`

`a - (b * Fix(a / b))`

## <a name="floating-point-imprecision"></a><span data-ttu-id="1a1b3-138">浮動小数点おける誤差</span><span class="sxs-lookup"><span data-stu-id="1a1b3-138">Floating-point imprecision</span></span>

<span data-ttu-id="1a1b3-139">浮動小数点数を使用する場合は、メモリ内で常に正確な10進表現が使用されるわけではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-139">When you work with floating-point numbers, remember that they do not always have a precise decimal representation in memory.</span></span> <span data-ttu-id="1a1b3-140">これにより、値の比較や `Mod` 演算子など、特定の操作によって予期しない結果が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-140">This can lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="1a1b3-141">詳細については、「[データ型のトラブルシューティング](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-141">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

## <a name="overloading"></a><span data-ttu-id="1a1b3-142">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="1a1b3-142">Overloading</span></span>

<span data-ttu-id="1a1b3-143">`Mod` 演算子は*オーバーロード*することができます。つまり、クラスまたは構造体で動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-143">The `Mod` operator can be *overloaded*, which means that a class or structure can redefine its behavior.</span></span> <span data-ttu-id="1a1b3-144">コードが、そのようなオーバーロードを含むクラスまたは構造体のインスタンスに `Mod` 適用される場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-144">If your code applies `Mod` to an instance of a class or structure that includes such an overload, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="1a1b3-145">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-145">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="example"></a><span data-ttu-id="1a1b3-146">例</span><span class="sxs-lookup"><span data-stu-id="1a1b3-146">Example</span></span>

<span data-ttu-id="1a1b3-147">次の例では、`Mod` 演算子を使用して2つの数値を除算し、剰余だけを返します。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-147">The following example uses the `Mod` operator to divide two numbers and return only the remainder.</span></span> <span data-ttu-id="1a1b3-148">どちらかの数値が浮動小数点数の場合、結果は剰余を表す浮動小数点数になります。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-148">If either number is a floating-point number, the result is a floating-point number that represents the remainder.</span></span>

[!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]

## <a name="example"></a><span data-ttu-id="1a1b3-149">例</span><span class="sxs-lookup"><span data-stu-id="1a1b3-149">Example</span></span>

<span data-ttu-id="1a1b3-150">次の例は、浮動小数点オペランドのおける誤差の可能性を示しています。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-150">The following example demonstrates the potential imprecision of floating-point operands.</span></span> <span data-ttu-id="1a1b3-151">最初のステートメントでは、オペランドが `Double`、0.2 は0.20000000000000001 の値が格納された無限の連続するバイナリ部分です。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-151">In the first statement, the operands are `Double`, and 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="1a1b3-152">2番目のステートメントでは、リテラル型文字 `D` は両方のオペランドを強制的に `Decimal`し、0.2 には正確な表現が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1a1b3-152">In the second statement, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span>

[!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]

## <a name="see-also"></a><span data-ttu-id="1a1b3-153">参照</span><span class="sxs-lookup"><span data-stu-id="1a1b3-153">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [<span data-ttu-id="1a1b3-154">算術演算子</span><span class="sxs-lookup"><span data-stu-id="1a1b3-154">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="1a1b3-155">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="1a1b3-155">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="1a1b3-156">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="1a1b3-156">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="1a1b3-157">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="1a1b3-157">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="1a1b3-158">Visual Basic の算術演算子</span><span class="sxs-lookup"><span data-stu-id="1a1b3-158">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="1a1b3-159">\ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a1b3-159">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
