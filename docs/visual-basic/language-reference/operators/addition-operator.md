---
title: + 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+
helpviewer_keywords:
- arithmetic operators [Visual Basic], addition
- + operator
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
- sum operator [Visual Basic]
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
ms.openlocfilehash: ab18a7137a31ed8e616f465e7d617305c96d7b10
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943025"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="fd98c-102">+ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd98c-102">+ Operator (Visual Basic)</span></span>
<span data-ttu-id="fd98c-103">2つの数値を加算するか、数値式の正の値を返します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-103">Adds two numbers or returns the positive value of a numeric expression.</span></span> <span data-ttu-id="fd98c-104">は、2つの文字列式を連結するためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="fd98c-104">Can also be used to concatenate two string expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd98c-105">構文</span><span class="sxs-lookup"><span data-stu-id="fd98c-105">Syntax</span></span>  
  
```vb
expression1 + expression2  
- or -  
+ expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="fd98c-106">指定項目</span><span class="sxs-lookup"><span data-stu-id="fd98c-106">Parts</span></span>  
  
|<span data-ttu-id="fd98c-107">用語</span><span class="sxs-lookup"><span data-stu-id="fd98c-107">Term</span></span>|<span data-ttu-id="fd98c-108">定義</span><span class="sxs-lookup"><span data-stu-id="fd98c-108">Definition</span></span>|  
|---|---|  
|`expression1`|<span data-ttu-id="fd98c-109">必須。</span><span class="sxs-lookup"><span data-stu-id="fd98c-109">Required.</span></span> <span data-ttu-id="fd98c-110">任意の数値または文字列式。</span><span class="sxs-lookup"><span data-stu-id="fd98c-110">Any numeric or string expression.</span></span>|  
|`expression2`|<span data-ttu-id="fd98c-111">`+`演算子が負の値を計算する場合を除き、必須です。</span><span class="sxs-lookup"><span data-stu-id="fd98c-111">Required unless the `+` operator is calculating a negative value.</span></span> <span data-ttu-id="fd98c-112">任意の数値または文字列式。</span><span class="sxs-lookup"><span data-stu-id="fd98c-112">Any numeric or string expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="fd98c-113">結果</span><span class="sxs-lookup"><span data-stu-id="fd98c-113">Result</span></span>  
 <span data-ttu-id="fd98c-114">と`expression1`が`expression2`両方とも数値の場合、結果は算術和になります。</span><span class="sxs-lookup"><span data-stu-id="fd98c-114">If `expression1` and `expression2` are both numeric, the result is their arithmetic sum.</span></span>  
  
 <span data-ttu-id="fd98c-115">が`expression2`存在しない場合`+` 、演算子は、式の変更されていない値の*単項*id 演算子です。</span><span class="sxs-lookup"><span data-stu-id="fd98c-115">If `expression2` is absent, the `+` operator is the *unary* identity operator for the unchanged value of an expression.</span></span> <span data-ttu-id="fd98c-116">この意味では、操作はの`expression1`符号を保持することで構成されます。したがって、が負の場合`expression1` 、結果は負になります。</span><span class="sxs-lookup"><span data-stu-id="fd98c-116">In this sense, the operation consists of retaining the sign of `expression1`, so the result is negative if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="fd98c-117">と`expression1`が`expression2`両方とも文字列の場合、結果はそれらの値を連結したものになります。</span><span class="sxs-lookup"><span data-stu-id="fd98c-117">If `expression1` and `expression2` are both strings, the result is the concatenation of their values.</span></span>  
  
 <span data-ttu-id="fd98c-118">と`expression1`の`expression2`型が混在している場合、実行される操作は、その型、内容、および[Option Strict ステートメント](../../../visual-basic/language-reference/statements/option-strict-statement.md)の設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="fd98c-118">If `expression1` and `expression2` are of mixed types, the action taken depends on their types, their contents, and the setting of the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span> <span data-ttu-id="fd98c-119">詳細については、「解説」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd98c-119">For more information, see the tables in "Remarks."</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="fd98c-120">サポートされている型</span><span class="sxs-lookup"><span data-stu-id="fd98c-120">Supported Types</span></span>  
 <span data-ttu-id="fd98c-121">符号なしの型および浮動小数点型`Decimal`、、および`String`を含む、すべての数値型。</span><span class="sxs-lookup"><span data-stu-id="fd98c-121">All numeric types, including the unsigned and floating-point types and `Decimal`, and `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd98c-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="fd98c-122">Remarks</span></span>  
 <span data-ttu-id="fd98c-123">一般に、 `+`は、可能な場合は算術加算を実行し、両方の式が文字列である場合にのみ連結します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-123">In general, `+` performs arithmetic addition when possible, and concatenates only when both expressions are strings.</span></span>  
  
 <span data-ttu-id="fd98c-124">どちらの式`Object`もでない場合、Visual Basic は次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-124">If neither expression is an `Object`, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="fd98c-125">式のデータ型</span><span class="sxs-lookup"><span data-stu-id="fd98c-125">Data types of expressions</span></span>|<span data-ttu-id="fd98c-126">コンパイラによるアクション</span><span class="sxs-lookup"><span data-stu-id="fd98c-126">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="fd98c-127">両方の式は`SByte` 、数値`UInteger`データ型`Byte`(、 `UShort` `Integer` `Short` 、、`Long`、、、、、、 `Double`、または) です。 `ULong` `Decimal` `Single`</span><span class="sxs-lookup"><span data-stu-id="fd98c-127">Both expressions are numeric data types (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`)</span></span>|<span data-ttu-id="fd98c-128">アドイン.</span><span class="sxs-lookup"><span data-stu-id="fd98c-128">Add.</span></span> <span data-ttu-id="fd98c-129">結果のデータ型は、および`expression1` `expression2`のデータ型に適した数値型です。</span><span class="sxs-lookup"><span data-stu-id="fd98c-129">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="fd98c-130">「[演算子の結果のデータ型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)」の「整数演算」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd98c-130">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="fd98c-131">両方の式の型はです。`String`</span><span class="sxs-lookup"><span data-stu-id="fd98c-131">Both expressions are of type `String`</span></span>|<span data-ttu-id="fd98c-132">つなげ.</span><span class="sxs-lookup"><span data-stu-id="fd98c-132">Concatenate.</span></span>|  
|<span data-ttu-id="fd98c-133">一方の式は数値データ型で、もう一方は文字列です。</span><span class="sxs-lookup"><span data-stu-id="fd98c-133">One expression is a numeric data type and the other is a string</span></span>|<span data-ttu-id="fd98c-134">`Option Strict` が`On`の場合は、コンパイラエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-134">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="fd98c-135">が`Option Strict` `String`の場合は、をに暗黙的`Double`に変換し、を追加します。 `Off`</span><span class="sxs-lookup"><span data-stu-id="fd98c-135">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="fd98c-136"><xref:System.InvalidCastException>をに`Double`変換できない場合は、例外をスローします。 `String`</span><span class="sxs-lookup"><span data-stu-id="fd98c-136">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="fd98c-137">1つの式は数値データ型であり、もう一方は[Nothing](../../../visual-basic/language-reference/nothing.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd98c-137">One expression is a numeric data type, and the other is [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|<span data-ttu-id="fd98c-138">を0と`Nothing`して値を追加します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-138">Add, with `Nothing` valued as zero.</span></span>|  
|<span data-ttu-id="fd98c-139">1つの式が文字列で、もう一方は`Nothing`</span><span class="sxs-lookup"><span data-stu-id="fd98c-139">One expression is a string, and the other is `Nothing`</span></span>|<span data-ttu-id="fd98c-140">`Nothing`値を "" として連結します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-140">Concatenate, with `Nothing` valued as "".</span></span>|  
  
 <span data-ttu-id="fd98c-141">1つの式が`Object`式の場合、Visual Basic は次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-141">If one expression is an `Object` expression, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="fd98c-142">式のデータ型</span><span class="sxs-lookup"><span data-stu-id="fd98c-142">Data types of expressions</span></span>|<span data-ttu-id="fd98c-143">コンパイラによるアクション</span><span class="sxs-lookup"><span data-stu-id="fd98c-143">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="fd98c-144">`Object`式は数値を保持し、もう一方は数値データ型です。</span><span class="sxs-lookup"><span data-stu-id="fd98c-144">`Object` expression holds a numeric value and the other is a numeric data type</span></span>|<span data-ttu-id="fd98c-145">`Option Strict` が`On`の場合は、コンパイラエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-145">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="fd98c-146">`Option Strict` が`Off`の場合は、を追加します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-146">If `Option Strict` is `Off`, then add.</span></span>|  
|<span data-ttu-id="fd98c-147">`Object`式は数値を保持し、もう一方は型です。`String`</span><span class="sxs-lookup"><span data-stu-id="fd98c-147">`Object` expression holds a numeric value and the other is of type `String`</span></span>|<span data-ttu-id="fd98c-148">`Option Strict` が`On`の場合は、コンパイラエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-148">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="fd98c-149">が`Option Strict` `String`の場合は、をに暗黙的`Double`に変換し、を追加します。 `Off`</span><span class="sxs-lookup"><span data-stu-id="fd98c-149">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="fd98c-150"><xref:System.InvalidCastException>をに`Double`変換できない場合は、例外をスローします。 `String`</span><span class="sxs-lookup"><span data-stu-id="fd98c-150">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="fd98c-151">`Object`式は文字列を保持し、もう1つは数値データ型です。</span><span class="sxs-lookup"><span data-stu-id="fd98c-151">`Object` expression holds a string and the other is a numeric data type</span></span>|<span data-ttu-id="fd98c-152">`Option Strict` が`On`の場合は、コンパイラエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-152">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="fd98c-153">が`Option Strict` `Object` `Double`の場合は、文字列をに暗黙的に変換し、を追加します。 `Off`</span><span class="sxs-lookup"><span data-stu-id="fd98c-153">If `Option Strict` is `Off`, then implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="fd98c-154">文字列`Object`をに`Double`変換できない場合は、 <xref:System.InvalidCastException>例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="fd98c-154">If the string `Object` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="fd98c-155">`Object`式は文字列を保持し、もう一方は型です。`String`</span><span class="sxs-lookup"><span data-stu-id="fd98c-155">`Object` expression holds a string and the other is of type `String`</span></span>|<span data-ttu-id="fd98c-156">`Option Strict` が`On`の場合は、コンパイラエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-156">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="fd98c-157">が`Option Strict`の場合、はに`Object`暗黙的`String`に変換され、連結さ`Off`れます。</span><span class="sxs-lookup"><span data-stu-id="fd98c-157">If `Option Strict` is `Off`, then implicitly convert `Object` to `String` and concatenate.</span></span>|  
  
 <span data-ttu-id="fd98c-158">両方の式が`Object`式の場合、Visual Basic は次の`Option Strict Off`操作を実行します (のみ)。</span><span class="sxs-lookup"><span data-stu-id="fd98c-158">If both expressions are `Object` expressions, Visual Basic takes the following actions (`Option Strict Off` only).</span></span>  
  
|<span data-ttu-id="fd98c-159">式のデータ型</span><span class="sxs-lookup"><span data-stu-id="fd98c-159">Data types of expressions</span></span>|<span data-ttu-id="fd98c-160">コンパイラによるアクション</span><span class="sxs-lookup"><span data-stu-id="fd98c-160">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="fd98c-161">両方`Object`の式が数値を保持します</span><span class="sxs-lookup"><span data-stu-id="fd98c-161">Both `Object` expressions hold numeric values</span></span>|<span data-ttu-id="fd98c-162">アドイン.</span><span class="sxs-lookup"><span data-stu-id="fd98c-162">Add.</span></span>|  
|<span data-ttu-id="fd98c-163">両方`Object`の式の型はです。`String`</span><span class="sxs-lookup"><span data-stu-id="fd98c-163">Both `Object` expressions are of type `String`</span></span>|<span data-ttu-id="fd98c-164">つなげ.</span><span class="sxs-lookup"><span data-stu-id="fd98c-164">Concatenate.</span></span>|  
|<span data-ttu-id="fd98c-165">一方`Object`の式は数値を保持し、もう一方は文字列を保持します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-165">One `Object` expression holds a numeric value and the other holds a string</span></span>|<span data-ttu-id="fd98c-166">文字列`Object`をに暗黙的に`Double`変換し、を追加します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-166">Implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="fd98c-167">文字列`Object`を数値に変換できない場合は、 <xref:System.InvalidCastException>例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="fd98c-167">If the string `Object` cannot be converted to a numeric value, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
  
 <span data-ttu-id="fd98c-168">いずれか`Object`の式が[Nothing](../../../visual-basic/language-reference/nothing.md)また<xref:System.DBNull>はに`+`評価される場合、 `String`演算子は、値が "" であるとして処理します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-168">If either `Object` expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md) or <xref:System.DBNull>, the `+` operator treats it as a `String` with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd98c-169">`+`演算子を使用すると、加算または文字列の連結が行われるかどうかを判断できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="fd98c-169">When you use the `+` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="fd98c-170">`&`演算子を連結に使用して、あいまいさをなくし、自己記述型のコードを提供します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-170">Use the `&` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="fd98c-171">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="fd98c-171">Overloading</span></span>  
 <span data-ttu-id="fd98c-172">演算子はオーバーロードできます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。 `+`</span><span class="sxs-lookup"><span data-stu-id="fd98c-172">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="fd98c-173">コードでこのようなクラスまたは構造体に対してこの演算子を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fd98c-173">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="fd98c-174">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd98c-174">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd98c-175">例</span><span class="sxs-lookup"><span data-stu-id="fd98c-175">Example</span></span>  
 <span data-ttu-id="fd98c-176">次の例では`+` 、演算子を使用して数値を追加します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-176">The following example uses the `+` operator to add numbers.</span></span> <span data-ttu-id="fd98c-177">オペランドが両方とも数値の場合、Visual Basic 演算結果が計算されます。</span><span class="sxs-lookup"><span data-stu-id="fd98c-177">If the operands are both numeric, Visual Basic computes the arithmetic result.</span></span> <span data-ttu-id="fd98c-178">算術結果は、2つのオペランドの合計を表します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-178">The arithmetic result represents the sum of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 <span data-ttu-id="fd98c-179">また、演算子を使用`+`して文字列を連結することもできます。</span><span class="sxs-lookup"><span data-stu-id="fd98c-179">You can also use the `+` operator to concatenate strings.</span></span> <span data-ttu-id="fd98c-180">オペランドが両方とも文字列の場合は、Visual Basic 連結します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-180">If the operands are both strings, Visual Basic concatenates them.</span></span> <span data-ttu-id="fd98c-181">連結の結果は、2つのオペランドの内容で構成される1つの文字列を表します。</span><span class="sxs-lookup"><span data-stu-id="fd98c-181">The concatenation result represents a single string consisting of the contents of the two operands one after the other.</span></span>  
  
 <span data-ttu-id="fd98c-182">オペランドが混合型の場合、結果は[Option Strict ステートメント](../../../visual-basic/language-reference/statements/option-strict-statement.md)の設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="fd98c-182">If the operands are of mixed types, the result depends on the setting of the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span> <span data-ttu-id="fd98c-183">次の例は、が`Option Strict` `On`の場合の結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="fd98c-183">The following example illustrates the result when `Option Strict` is `On`.</span></span>  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 <span data-ttu-id="fd98c-184">次の例は、が`Option Strict` `Off`の場合の結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="fd98c-184">The following example illustrates the result when `Option Strict` is `Off`.</span></span>  
  
 [!code-vb[VbVbalrOperators#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#54)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#52)]  
  
 <span data-ttu-id="fd98c-185">あいまいさをなくすには、の`&` `+`代わりに演算子を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd98c-185">To eliminate ambiguity, you should use the `&` operator instead of `+` for concatenation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd98c-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd98c-186">See also</span></span>

- [<span data-ttu-id="fd98c-187">& 演算子</span><span class="sxs-lookup"><span data-stu-id="fd98c-187">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [<span data-ttu-id="fd98c-188">連結演算子</span><span class="sxs-lookup"><span data-stu-id="fd98c-188">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="fd98c-189">算術演算子</span><span class="sxs-lookup"><span data-stu-id="fd98c-189">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="fd98c-190">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="fd98c-190">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="fd98c-191">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="fd98c-191">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="fd98c-192">Visual Basic の算術演算子</span><span class="sxs-lookup"><span data-stu-id="fd98c-192">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="fd98c-193">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="fd98c-193">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
