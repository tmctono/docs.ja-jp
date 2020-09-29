---
title: 算術演算子
ms.date: 07/20/2015
helpviewer_keywords:
- type safety
- operators [Visual Basic], bitwise
- operators [Visual Basic], bit-shift
- bitwise operators [Visual Basic]
- bit-shift operators [Visual Basic]
- zero, division by zero
- operators [Visual Basic], arithmetic
- division [Visual Basic], by zero
- Visual Basic code, operators
- arithmetic operators [Visual Basic], about arithmetic operators
ms.assetid: 325dac7a-ea4f-41d5-8b48-f6e904211569
ms.openlocfilehash: 023e479736285aa2d04509e05f49fe930cb4721d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090080"
---
# <a name="arithmetic-operators-in-visual-basic"></a><span data-ttu-id="62f35-102">Visual Basic における算術演算子</span><span class="sxs-lookup"><span data-stu-id="62f35-102">Arithmetic Operators in Visual Basic</span></span>

<span data-ttu-id="62f35-103">算術演算子は、リテラル、変数、その他の式、関数およびプロパティの呼び出し、および定数によって表される数値の計算に関連する一般的な算術演算の多くを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="62f35-103">Arithmetic operators are used to perform many of the familiar arithmetic operations that involve the calculation of numeric values represented by literals, variables, other expressions, function and property calls, and constants.</span></span> <span data-ttu-id="62f35-104">また、算術演算子で分類されるのはビット シフト演算子です。これは、オペランドの個々のビットのレベルで機能し、ビット パターンを左または右にシフトします。</span><span class="sxs-lookup"><span data-stu-id="62f35-104">Also classified with arithmetic operators are the bit-shift operators, which act at the level of the individual bits of the operands and shift their bit patterns to the left or right.</span></span>  
  
## <a name="arithmetic-operations"></a><span data-ttu-id="62f35-105">算術演算</span><span class="sxs-lookup"><span data-stu-id="62f35-105">Arithmetic Operations</span></span>  

 <span data-ttu-id="62f35-106">次の例に示すように、[+ 演算子](../../../language-reference/operators/addition-operator.md)を使用して式の中の 2 つの値を加算したり、[- 演算子 (Visual Basic)](../../../language-reference/operators/subtraction-operator.md) を使用して 1 つの値を別の値から減算したりできます。</span><span class="sxs-lookup"><span data-stu-id="62f35-106">You can add two values in an expression together with the [+ Operator](../../../language-reference/operators/addition-operator.md), or subtract one from another with the [- Operator (Visual Basic)](../../../language-reference/operators/subtraction-operator.md), as the following example demonstrates.</span></span>  
  
 [!code-vb[VbVbalrOperators#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#57)]  
  
 <span data-ttu-id="62f35-107">また、否定でも [- 演算子 (Visual Basic)](../../../language-reference/operators/subtraction-operator.md) を使用しますが、次の例に示すように、オペランドは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="62f35-107">Negation also uses the [- Operator (Visual Basic)](../../../language-reference/operators/subtraction-operator.md), but with only one operand, as the following example demonstrates.</span></span>  
  
 [!code-vb[VbVbalrOperators#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#58)]  
  
 <span data-ttu-id="62f35-108">乗算と除算では、次の例に示すように、それぞれ [\* 演算子](../../../language-reference/operators/multiplication-operator.md)と [/ 演算子 (Visual Basic)](../../../language-reference/operators/floating-point-division-operator.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="62f35-108">Multiplication and division use the [\* Operator](../../../language-reference/operators/multiplication-operator.md) and [/ Operator (Visual Basic)](../../../language-reference/operators/floating-point-division-operator.md), respectively, as the following example demonstrates.</span></span>  
  
 [!code-vb[VbVbalrOperators#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#59)]  
  
 <span data-ttu-id="62f35-109">指数では、次の例に示すように、[^ 演算子](../../../language-reference/operators/exponentiation-operator.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="62f35-109">Exponentiation uses the [^ Operator](../../../language-reference/operators/exponentiation-operator.md), as the following example demonstrates.</span></span>  
  
 [!code-vb[VbVbalrOperators#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#60)]  
  
 <span data-ttu-id="62f35-110">整数除算は、[\ 演算子 (Visual Basic)](../../../language-reference/operators/integer-division-operator.md) を使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="62f35-110">Integer division is carried out using the [\ Operator (Visual Basic)](../../../language-reference/operators/integer-division-operator.md).</span></span> <span data-ttu-id="62f35-111">整数除算は商を返します。これは、除数が余りを考慮せずに被除数に分割できる回数を表す整数です。</span><span class="sxs-lookup"><span data-stu-id="62f35-111">Integer division returns the quotient, that is, the integer that represents the number of times the divisor can divide into the dividend without consideration of any remainder.</span></span> <span data-ttu-id="62f35-112">除数と被除数は両方とも、この演算子の整数型 (`SByte`、`Byte`、`Short`、`UShort`、`Integer`、`UInteger`、`Long`、および `ULong`) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="62f35-112">Both the divisor and the dividend must be integral types (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, and `ULong`) for this operator.</span></span> <span data-ttu-id="62f35-113">その他のすべての型は、最初に整数型に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62f35-113">All other types must be converted to an integral type first.</span></span> <span data-ttu-id="62f35-114">整数除算の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="62f35-114">The following example demonstrates integer division.</span></span>  
  
 [!code-vb[VbVbalrOperators#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#61)]  
  
 <span data-ttu-id="62f35-115">剰余演算は、[Mod 演算子](../../../language-reference/operators/mod-operator.md)を使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="62f35-115">Modulus arithmetic is performed using the [Mod Operator](../../../language-reference/operators/mod-operator.md).</span></span> <span data-ttu-id="62f35-116">この演算子は、除数を被除数に整数回除算した後の剰余を返します。</span><span class="sxs-lookup"><span data-stu-id="62f35-116">This operator returns the remainder after dividing the divisor into the dividend an integral number of times.</span></span> <span data-ttu-id="62f35-117">除数と被除数の両方が整数型の場合、戻り値は整数です。</span><span class="sxs-lookup"><span data-stu-id="62f35-117">If both divisor and dividend are integral types, the returned value is integral.</span></span> <span data-ttu-id="62f35-118">除数と被除数が浮動小数点型の場合は、戻り値も浮動小数点です。</span><span class="sxs-lookup"><span data-stu-id="62f35-118">If divisor and dividend are floating-point types, the returned value is also floating-point.</span></span> <span data-ttu-id="62f35-119">次の例でその動作を示します。</span><span class="sxs-lookup"><span data-stu-id="62f35-119">The following example demonstrates this behavior.</span></span>  
  
 [!code-vb[VbVbalrOperators#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbalrOperators#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#63)]  
  
### <a name="attempted-division-by-zero"></a><span data-ttu-id="62f35-120">0 による除算を試行</span><span class="sxs-lookup"><span data-stu-id="62f35-120">Attempted Division by Zero</span></span>  

 <span data-ttu-id="62f35-121">0 による除算の結果は、関連するデータ型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="62f35-121">Division by zero has different results depending on the data types involved.</span></span> <span data-ttu-id="62f35-122">整数除算 (`SByte`、`Byte`、`Short`、`UShort`、`Integer`、`UInteger`、`Long`、`ULong`) では、.NET Framework は <xref:System.DivideByZeroException> 例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="62f35-122">In integral divisions (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`), the .NET Framework throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="62f35-123">`Decimal` または `Single` データ型の除算演算では、.NET Framework は <xref:System.DivideByZeroException> 例外もスローします。</span><span class="sxs-lookup"><span data-stu-id="62f35-123">In division operations on the `Decimal` or `Single` data type, the .NET Framework also throws a <xref:System.DivideByZeroException> exception.</span></span>  
  
 <span data-ttu-id="62f35-124">`Double` データ型を含む浮動小数点除算では、例外はスローされず、結果は被除数に応じて <xref:System.Double.NaN>、<xref:System.Double.PositiveInfinity>、または <xref:System.Double.NegativeInfinity> を表すクラス メンバーになります。</span><span class="sxs-lookup"><span data-stu-id="62f35-124">In floating-point divisions involving the `Double` data type, no exception is thrown, and the result is the class member representing <xref:System.Double.NaN>, <xref:System.Double.PositiveInfinity>, or <xref:System.Double.NegativeInfinity>, depending on the dividend.</span></span> <span data-ttu-id="62f35-125">次の表は、`Double` 値を 0 で除算しようとした場合のさまざまな結果をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="62f35-125">The following table summarizes the various results of attempting to divide a `Double` value by zero.</span></span>  
  
|<span data-ttu-id="62f35-126">被除数データ型</span><span class="sxs-lookup"><span data-stu-id="62f35-126">Dividend data type</span></span>|<span data-ttu-id="62f35-127">除数データ型</span><span class="sxs-lookup"><span data-stu-id="62f35-127">Divisor data type</span></span>|<span data-ttu-id="62f35-128">除算される値</span><span class="sxs-lookup"><span data-stu-id="62f35-128">Dividend value</span></span>|<span data-ttu-id="62f35-129">結果</span><span class="sxs-lookup"><span data-stu-id="62f35-129">Result</span></span>|  
|---|---|---|---|  
|`Double`|`Double`|<span data-ttu-id="62f35-130">0</span><span class="sxs-lookup"><span data-stu-id="62f35-130">0</span></span>|<span data-ttu-id="62f35-131"><xref:System.Double.NaN> (数学的に定義された数値ではありません)</span><span class="sxs-lookup"><span data-stu-id="62f35-131"><xref:System.Double.NaN> (not a mathematically defined number)</span></span>|  
|`Double`|`Double`|<span data-ttu-id="62f35-132">> 0</span><span class="sxs-lookup"><span data-stu-id="62f35-132">> 0</span></span>|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|<span data-ttu-id="62f35-133">\< 0</span><span class="sxs-lookup"><span data-stu-id="62f35-133">\< 0</span></span>|<xref:System.Double.NegativeInfinity>|  
  
 <span data-ttu-id="62f35-134"><xref:System.DivideByZeroException> 例外をキャッチした場合は、そのメンバーを使用して処理することができます。</span><span class="sxs-lookup"><span data-stu-id="62f35-134">When you catch a <xref:System.DivideByZeroException> exception, you can use its members to help you handle it.</span></span> <span data-ttu-id="62f35-135">たとえば、<xref:System.Exception.Message%2A> プロパティは、例外のメッセージ テキストを保持します。</span><span class="sxs-lookup"><span data-stu-id="62f35-135">For example, the <xref:System.Exception.Message%2A> property holds the message text for the exception.</span></span> <span data-ttu-id="62f35-136">詳しくは、「[Try...Catch...Finally ステートメント](../../../language-reference/statements/try-catch-finally-statement.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="62f35-136">For more information, see [Try...Catch...Finally Statement](../../../language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="bit-shift-operations"></a><span data-ttu-id="62f35-137">ビット シフト演算</span><span class="sxs-lookup"><span data-stu-id="62f35-137">Bit-Shift Operations</span></span>  

 <span data-ttu-id="62f35-138">ビット シフト演算は、ビット パターンに対して算術左シフトを実行します。</span><span class="sxs-lookup"><span data-stu-id="62f35-138">A bit-shift operation performs an arithmetic shift on a bit pattern.</span></span> <span data-ttu-id="62f35-139">パターンは左側のオペランドに含まれていますが、右側のオペランドは、パターンをシフトする位置の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="62f35-139">The pattern is contained in the operand on the left, while the operand on the right specifies the number of positions to shift the pattern.</span></span> <span data-ttu-id="62f35-140">パターンを右にシフトするには [>> 演算子](../../../language-reference/operators/right-shift-operator.md)を使用し、左にシフトするには [<< 演算子](../../../language-reference/operators/left-shift-operator.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="62f35-140">You can shift the pattern to the right with the [>> Operator](../../../language-reference/operators/right-shift-operator.md) or to the left with the [<< Operator](../../../language-reference/operators/left-shift-operator.md).</span></span>  
  
 <span data-ttu-id="62f35-141">パターンのオペランドのデータ型は、`SByte`、`Byte`、`Short`、`UShort`、`Integer`、`UInteger`、`Long`、または `ULong` である必要があります。</span><span class="sxs-lookup"><span data-stu-id="62f35-141">The data type of the pattern operand must be `SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`.</span></span> <span data-ttu-id="62f35-142">シフト数のオペランドのデータ型は、`Integer` であるか、`Integer` に拡大変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62f35-142">The data type of the shift amount operand must be `Integer` or must widen to `Integer`.</span></span>  
  
 <span data-ttu-id="62f35-143">算術シフトは循環ではありません。つまり、結果の一方の端からシフトされたビットはもう一方の端には再入されません。</span><span class="sxs-lookup"><span data-stu-id="62f35-143">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="62f35-144">シフトによって空いたビット位置は、次のように設定されます。</span><span class="sxs-lookup"><span data-stu-id="62f35-144">The bit positions vacated by a shift are set as follows:</span></span>  
  
- <span data-ttu-id="62f35-145">算術左シフトの場合は 0</span><span class="sxs-lookup"><span data-stu-id="62f35-145">0 for an arithmetic left shift</span></span>  
  
- <span data-ttu-id="62f35-146">正の数の算術右シフトの場合は 0</span><span class="sxs-lookup"><span data-stu-id="62f35-146">0 for an arithmetic right shift of a positive number</span></span>  
  
- <span data-ttu-id="62f35-147">符号なしのデータ型 (`Byte`、`UShort`、`UInteger`、`ULong`) の算術右シフトの場合は 0</span><span class="sxs-lookup"><span data-stu-id="62f35-147">0 for an arithmetic right shift of an unsigned data type (`Byte`, `UShort`, `UInteger`, `ULong`)</span></span>  
  
- <span data-ttu-id="62f35-148">負の数 (`SByte`、`Short`、`Integer`、または `Long`) の算術右シフトの場合は 1</span><span class="sxs-lookup"><span data-stu-id="62f35-148">1 for an arithmetic right shift of a negative number (`SByte`, `Short`, `Integer`, or `Long`)</span></span>  
  
 <span data-ttu-id="62f35-149">次の例では、`Integer` 値を左右にシフトします。</span><span class="sxs-lookup"><span data-stu-id="62f35-149">The following example shifts an `Integer` value both left and right.</span></span>  
  
 [!code-vb[VbVbalrOperators#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#64)]  
  
 <span data-ttu-id="62f35-150">算術シフトではオーバーフロー例外は生成されません。</span><span class="sxs-lookup"><span data-stu-id="62f35-150">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="bitwise-operations"></a><span data-ttu-id="62f35-151">ビットごとの演算</span><span class="sxs-lookup"><span data-stu-id="62f35-151">Bitwise Operations</span></span>  

 <span data-ttu-id="62f35-152">論理演算子に加えて、`Not`、`Or`、`And`、および `Xor` は、数値に対して使用する場合にビットごとの算術演算も実行します。</span><span class="sxs-lookup"><span data-stu-id="62f35-152">In addition to being logical operators, `Not`, `Or`, `And`, and `Xor` also perform bitwise arithmetic when used on numeric values.</span></span> <span data-ttu-id="62f35-153">詳細については、「[Visual Basic の論理演算子とビット処理演算子](logical-and-bitwise-operators.md)」の「ビットごとの演算」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62f35-153">For more information, see "Bitwise Operations" in [Logical and Bitwise Operators in Visual Basic](logical-and-bitwise-operators.md).</span></span>  
  
## <a name="type-safety"></a><span data-ttu-id="62f35-154">タイプ セーフ</span><span class="sxs-lookup"><span data-stu-id="62f35-154">Type Safety</span></span>  

 <span data-ttu-id="62f35-155">通常、オペランドは同じ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="62f35-155">Operands should normally be of the same type.</span></span> <span data-ttu-id="62f35-156">たとえば、`Integer` 変数を使用して加算を行う場合は、それを別の `Integer` 変数に追加し、その結果を `Integer` 型の変数にも代入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62f35-156">For example, if you are doing addition with an `Integer` variable, you should add it to another `Integer` variable, and you should assign the result to a variable of type `Integer` as well.</span></span>  
  
 <span data-ttu-id="62f35-157">タイプセーフなコーディングを確実に行うための 1 つの方法として、[Option Strict ステートメント](../../../language-reference/statements/option-strict-statement.md)を使用する方法があります。</span><span class="sxs-lookup"><span data-stu-id="62f35-157">One way to ensure good type-safe coding practice is to use the [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md).</span></span> <span data-ttu-id="62f35-158">`Option Strict On` を設定すると、Visual Basic では、*タイプセーフな*変換が自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="62f35-158">If you set `Option Strict On`, Visual Basic automatically performs *type-safe* conversions.</span></span> <span data-ttu-id="62f35-159">たとえば、`Double` 変数に `Integer` 変数を追加し、その値を `Double` 変数に代入しようとすると、データを失うことなく `Integer` 値を `Double` に変換できるため、操作は正常に続行されます。</span><span class="sxs-lookup"><span data-stu-id="62f35-159">For example, if you try to add an `Integer` variable to a `Double` variable and assign the value to a `Double` variable, the operation proceeds normally, because an `Integer` value can be converted to `Double` without loss of data.</span></span> <span data-ttu-id="62f35-160">一方、タイプセーフでない変換では、`Option Strict On` でコンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="62f35-160">Type-unsafe conversions, on the other hand, cause a compiler error with `Option Strict On`.</span></span> <span data-ttu-id="62f35-161">たとえば、`Double` 変数に `Integer` 変数を追加し、その値を `Integer` 変数に代入しようとすると、コンパイラ エラーが発生します。これは、`Double` 変数を型 `Integer` に暗黙的に変換できないためです。</span><span class="sxs-lookup"><span data-stu-id="62f35-161">For example, if you try to add an `Integer` variable to a `Double` variable and assign the value to an `Integer` variable, a compiler error results, because a `Double` variable cannot be implicitly converted to type `Integer`.</span></span>  
  
 <span data-ttu-id="62f35-162">ただし、`Option Strict Off` を設定した場合、Visual Basic は暗黙的な縮小変換を行うことができますが、予期しないデータまたは精度の損失が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="62f35-162">If you set `Option Strict Off`, however, Visual Basic allows implicit narrowing conversions to take place, although they can result in the unexpected loss of data or precision.</span></span> <span data-ttu-id="62f35-163">このため、運用コードを記述するときには `Option Strict On` を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="62f35-163">For this reason, we recommend that you use `Option Strict On` when writing production code.</span></span> <span data-ttu-id="62f35-164">詳細については、「 [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62f35-164">For more information, see [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62f35-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="62f35-165">See also</span></span>

- [<span data-ttu-id="62f35-166">算術演算子</span><span class="sxs-lookup"><span data-stu-id="62f35-166">Arithmetic Operators</span></span>](../../../language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="62f35-167">ビット シフト演算子</span><span class="sxs-lookup"><span data-stu-id="62f35-167">Bit Shift Operators</span></span>](../../../language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="62f35-168">Visual Basic における比較演算子</span><span class="sxs-lookup"><span data-stu-id="62f35-168">Comparison Operators in Visual Basic</span></span>](comparison-operators.md)
- [<span data-ttu-id="62f35-169">Visual Basic の連結演算子</span><span class="sxs-lookup"><span data-stu-id="62f35-169">Concatenation Operators in Visual Basic</span></span>](concatenation-operators.md)
- [<span data-ttu-id="62f35-170">Visual Basic の論理演算子とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="62f35-170">Logical and Bitwise Operators in Visual Basic</span></span>](logical-and-bitwise-operators.md)
- [<span data-ttu-id="62f35-171">演算子の効率のよい組み合わせ</span><span class="sxs-lookup"><span data-stu-id="62f35-171">Efficient Combination of Operators</span></span>](efficient-combination-of-operators.md)
