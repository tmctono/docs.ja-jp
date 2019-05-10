---
title: Mod 演算子 (Visual Basic)
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
ms.openlocfilehash: f1334ff7aa07f49139bfe684746ae9cc3cf8087c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663170"
---
# <a name="mod-operator-visual-basic"></a><span data-ttu-id="49280-102">Mod 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49280-102">Mod operator (Visual Basic)</span></span>
<span data-ttu-id="49280-103">2 つの数値を除算し、残りの部分のみを返します。</span><span class="sxs-lookup"><span data-stu-id="49280-103">Divides two numbers and returns only the remainder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49280-104">構文</span><span class="sxs-lookup"><span data-stu-id="49280-104">Syntax</span></span>  
  
```  
number1 Mod number2  
```  
  
## <a name="parts"></a><span data-ttu-id="49280-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="49280-105">Parts</span></span>  
 `number1`  
 <span data-ttu-id="49280-106">必須。</span><span class="sxs-lookup"><span data-stu-id="49280-106">Required.</span></span> <span data-ttu-id="49280-107">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="49280-107">Any numeric expression.</span></span>  
  
 `number2`  
 <span data-ttu-id="49280-108">必須。</span><span class="sxs-lookup"><span data-stu-id="49280-108">Required.</span></span> <span data-ttu-id="49280-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="49280-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="49280-110">サポートされている型</span><span class="sxs-lookup"><span data-stu-id="49280-110">Supported types</span></span>  
 <span data-ttu-id="49280-111">すべての数値型。</span><span class="sxs-lookup"><span data-stu-id="49280-111">All numeric types.</span></span> <span data-ttu-id="49280-112">これには、符号なしと浮動小数点型が含まれますと`Decimal`します。</span><span class="sxs-lookup"><span data-stu-id="49280-112">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="49280-113">結果</span><span class="sxs-lookup"><span data-stu-id="49280-113">Result</span></span>

<span data-ttu-id="49280-114">結果は、剰余`number1`で除算`number2`します。</span><span class="sxs-lookup"><span data-stu-id="49280-114">The result is the remainder after `number1` is divided by `number2`.</span></span> <span data-ttu-id="49280-115">たとえば、式`14 Mod 4`2 に評価されます。</span><span class="sxs-lookup"><span data-stu-id="49280-115">For example, the expression `14 Mod 4` evaluates to 2.</span></span>  

> [!NOTE]
> <span data-ttu-id="49280-116">間に相違がある*残りの部分*と*剰余*数学では、負の数値ごとに異なる結果にします。</span><span class="sxs-lookup"><span data-stu-id="49280-116">There is a difference between *remainder* and *modulus* in mathematics, with different results for negative numbers.</span></span> <span data-ttu-id="49280-117">`Mod` Visual Basic、.NET Framework で演算子`op_Modulus`演算子、および基になる[rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL 命令が剰余演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="49280-117">The `Mod` operator in Visual Basic, the .NET Framework `op_Modulus` operator, and the underlying [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL instruction all perform a remainder operation.</span></span>

<span data-ttu-id="49280-118">結果、`Mod`操作には、被除数の符号が保持されます`number1`、ため、正または負の値があります。</span><span class="sxs-lookup"><span data-stu-id="49280-118">The result of a `Mod` operation retains the sign of the dividend, `number1`, and so it may be positive or negative.</span></span> <span data-ttu-id="49280-119">結果は常に、範囲内 (-`number2`、 `number2`)、排他的な。</span><span class="sxs-lookup"><span data-stu-id="49280-119">The result is always in the range (-`number2`, `number2`), exclusive.</span></span> <span data-ttu-id="49280-120">例:</span><span class="sxs-lookup"><span data-stu-id="49280-120">For example:</span></span>

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

## <a name="remarks"></a><span data-ttu-id="49280-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="49280-121">Remarks</span></span>  
 <span data-ttu-id="49280-122">いずれか`number1`または`number2`浮動小数点の値は、浮動小数点除算の剰余が返されます。</span><span class="sxs-lookup"><span data-stu-id="49280-122">If either `number1` or `number2` is a floating-point value, the floating-point remainder of the division is returned.</span></span> <span data-ttu-id="49280-123">結果のデータ型のデータ型の除算の結果としてすべての可能な値を保持できる最小のデータ型は、`number1`と`number2`します。</span><span class="sxs-lookup"><span data-stu-id="49280-123">The data type of the result is the smallest data type that can hold all possible values that result from division with the data types of `number1` and `number2`.</span></span>  
  
 <span data-ttu-id="49280-124">場合`number1`または`number2`に評価される[Nothing](../../../visual-basic/language-reference/nothing.md)、0 として扱われます。</span><span class="sxs-lookup"><span data-stu-id="49280-124">If `number1` or `number2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
 <span data-ttu-id="49280-125">関連する演算子を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="49280-125">Related operators include the following:</span></span>  
  
- <span data-ttu-id="49280-126">[\ 演算子 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)除算の商の整数を返します。</span><span class="sxs-lookup"><span data-stu-id="49280-126">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient of a division.</span></span> <span data-ttu-id="49280-127">たとえば、式`14 \ 4`3 に評価されます。</span><span class="sxs-lookup"><span data-stu-id="49280-127">For example, the expression `14 \ 4` evaluates to 3.</span></span>  
  
- <span data-ttu-id="49280-128">[/演算子 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)浮動小数点数として、残りの部分を含む、完全な商を返します。</span><span class="sxs-lookup"><span data-stu-id="49280-128">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, including the remainder, as a floating-point number.</span></span> <span data-ttu-id="49280-129">たとえば、式`14 / 4`3.5 に評価されます。</span><span class="sxs-lookup"><span data-stu-id="49280-129">For example, the expression `14 / 4` evaluates to 3.5.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="49280-130">0 による除算</span><span class="sxs-lookup"><span data-stu-id="49280-130">Attempted division by zero</span></span>  
 <span data-ttu-id="49280-131">場合`number2`の動作を 0 に評価される、`Mod`演算子はオペランドのデータ型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="49280-131">If `number2` evaluates to zero, the behavior of the `Mod` operator depends on the data type of the operands.</span></span> <span data-ttu-id="49280-132">整数の除算をスローする<xref:System.DivideByZeroException>例外。</span><span class="sxs-lookup"><span data-stu-id="49280-132">An integral division throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="49280-133">浮動小数点除算が返されます<xref:System.Double.NaN>します。</span><span class="sxs-lookup"><span data-stu-id="49280-133">A floating-point division returns <xref:System.Double.NaN>.</span></span>  
  
## <a name="equivalent-formula"></a><span data-ttu-id="49280-134">同等の数式</span><span class="sxs-lookup"><span data-stu-id="49280-134">Equivalent formula</span></span>  
 <span data-ttu-id="49280-135">式`a Mod b`は、次の数式のいずれかに相当します。</span><span class="sxs-lookup"><span data-stu-id="49280-135">The expression `a Mod b` is equivalent to either of the following formulas:</span></span>  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## <a name="floating-point-imprecision"></a><span data-ttu-id="49280-136">浮動小数点は誤差</span><span class="sxs-lookup"><span data-stu-id="49280-136">Floating-point imprecision</span></span>  
 <span data-ttu-id="49280-137">浮動小数点数を使用するときに、常がない正確な 10 進表記メモリに注意してください。</span><span class="sxs-lookup"><span data-stu-id="49280-137">When you work with floating-point numbers, remember that they do not always have a precise decimal representation in memory.</span></span> <span data-ttu-id="49280-138">これは、値の比較などの特定の操作から予期しない結果につながりますできますと`Mod`演算子。</span><span class="sxs-lookup"><span data-stu-id="49280-138">This can lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="49280-139">詳細については、次を参照してください。[データ型のトラブルシューティング](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="49280-139">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="49280-140">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="49280-140">Overloading</span></span>  
 <span data-ttu-id="49280-141">`Mod`演算子は、*オーバー ロードされた*、つまり、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="49280-141">The `Mod` operator can be *overloaded*, which means that a class or structure can redefine its behavior.</span></span> <span data-ttu-id="49280-142">コードが適用される場合`Mod`クラスまたはそのようなオーバー ロードを含む構造体のインスタンスに再定義された動作を理解することを確認します。</span><span class="sxs-lookup"><span data-stu-id="49280-142">If your code applies `Mod` to an instance of a class or structure that includes such an overload, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="49280-143">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49280-143">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="49280-144">例</span><span class="sxs-lookup"><span data-stu-id="49280-144">Example</span></span>  
 <span data-ttu-id="49280-145">次の例では、`Mod`演算子を 2 つの数値を除算し、残りの部分のみを返します。</span><span class="sxs-lookup"><span data-stu-id="49280-145">The following example uses the `Mod` operator to divide two numbers and return only the remainder.</span></span> <span data-ttu-id="49280-146">どちらかの数値が浮動小数点数の場合は、残りの部分を表す浮動小数点数になります。</span><span class="sxs-lookup"><span data-stu-id="49280-146">If either number is a floating-point number, the result is a floating-point number that represents the remainder.</span></span>  
  
 [!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]  
  
## <a name="example"></a><span data-ttu-id="49280-147">例</span><span class="sxs-lookup"><span data-stu-id="49280-147">Example</span></span>  
 <span data-ttu-id="49280-148">次の例では、浮動小数点のオペランドの誤差の可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="49280-148">The following example demonstrates the potential imprecision of floating-point operands.</span></span> <span data-ttu-id="49280-149">最初のステートメントでは、オペランドは`Double`0.2 であり、無限に繰り返される 0.20000000000000001 として格納されている値を持つバイナリ小数部分。</span><span class="sxs-lookup"><span data-stu-id="49280-149">In the first statement, the operands are `Double`, and 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="49280-150">2 番目のステートメントでは、リテラルの型文字`D`強制的にオペランドは両方とも`Decimal`0.2 であり、正確に表現します。</span><span class="sxs-lookup"><span data-stu-id="49280-150">In the second statement, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span>  
  
 [!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="49280-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="49280-151">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [<span data-ttu-id="49280-152">算術演算子</span><span class="sxs-lookup"><span data-stu-id="49280-152">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="49280-153">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="49280-153">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="49280-154">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="49280-154">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="49280-155">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="49280-155">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="49280-156">Visual Basic における算術演算子</span><span class="sxs-lookup"><span data-stu-id="49280-156">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="49280-157">\ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49280-157">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
