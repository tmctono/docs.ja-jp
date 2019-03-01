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
ms.openlocfilehash: 448ca9d52d820029464b75a616dc032a7cc41f59
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979646"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="844c4-102">+ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="844c4-102">+ Operator (Visual Basic)</span></span>
<span data-ttu-id="844c4-103">2 つの数値を追加します。 または、数値式の正の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="844c4-103">Adds two numbers or returns the positive value of a numeric expression.</span></span> <span data-ttu-id="844c4-104">2 つの文字列式を連結することも使用できます。</span><span class="sxs-lookup"><span data-stu-id="844c4-104">Can also be used to concatenate two string expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="844c4-105">構文</span><span class="sxs-lookup"><span data-stu-id="844c4-105">Syntax</span></span>  
  
```vb
expression1 + expression2  
- or -  
+ expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="844c4-106">指定項目</span><span class="sxs-lookup"><span data-stu-id="844c4-106">Parts</span></span>  
  
|<span data-ttu-id="844c4-107">用語</span><span class="sxs-lookup"><span data-stu-id="844c4-107">Term</span></span>|<span data-ttu-id="844c4-108">定義</span><span class="sxs-lookup"><span data-stu-id="844c4-108">Definition</span></span>|  
|---|---|  
|`expression1`|<span data-ttu-id="844c4-109">必須。</span><span class="sxs-lookup"><span data-stu-id="844c4-109">Required.</span></span> <span data-ttu-id="844c4-110">任意の数値または文字列式。</span><span class="sxs-lookup"><span data-stu-id="844c4-110">Any numeric or string expression.</span></span>|  
|`expression2`|<span data-ttu-id="844c4-111">ために必要な場合を除き、`+`演算子が負の値を計算します。</span><span class="sxs-lookup"><span data-stu-id="844c4-111">Required unless the `+` operator is calculating a negative value.</span></span> <span data-ttu-id="844c4-112">任意の数値または文字列式。</span><span class="sxs-lookup"><span data-stu-id="844c4-112">Any numeric or string expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="844c4-113">結果</span><span class="sxs-lookup"><span data-stu-id="844c4-113">Result</span></span>  
 <span data-ttu-id="844c4-114">場合`expression1`と`expression2`はどちらも数値では、その算術の合計になります。</span><span class="sxs-lookup"><span data-stu-id="844c4-114">If `expression1` and `expression2` are both numeric, the result is their arithmetic sum.</span></span>  
  
 <span data-ttu-id="844c4-115">場合`expression2`、存在しない場合は、`+`演算子は、*単項*id 演算子式の値は変わりません。</span><span class="sxs-lookup"><span data-stu-id="844c4-115">If `expression2` is absent, the `+` operator is the *unary* identity operator for the unchanged value of an expression.</span></span> <span data-ttu-id="844c4-116">操作は、この意味での符号を保持することで構成されます`expression1`で結果が負の値であるため、場合`expression1`が負の値。</span><span class="sxs-lookup"><span data-stu-id="844c4-116">In this sense, the operation consists of retaining the sign of `expression1`, so the result is negative if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="844c4-117">場合`expression1`と`expression2`、両方の文字列をその値を連結したものになります。</span><span class="sxs-lookup"><span data-stu-id="844c4-117">If `expression1` and `expression2` are both strings, the result is the concatenation of their values.</span></span>  
  
 <span data-ttu-id="844c4-118">場合`expression1`と`expression2`は、混合型の実行されるアクションは、その型の内容、およびの設定に依存、 [Option Strict ステートメント](../../../visual-basic/language-reference/statements/option-strict-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="844c4-118">If `expression1` and `expression2` are of mixed types, the action taken depends on their types, their contents, and the setting of the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span> <span data-ttu-id="844c4-119">詳細については、します。「解説」表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="844c4-119">For more information, see the tables in "Remarks."</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="844c4-120">サポートされている型</span><span class="sxs-lookup"><span data-stu-id="844c4-120">Supported Types</span></span>  
 <span data-ttu-id="844c4-121">符号なしと浮動小数点型を含め、すべての数値型と`Decimal`、および`String`します。</span><span class="sxs-lookup"><span data-stu-id="844c4-121">All numeric types, including the unsigned and floating-point types and `Decimal`, and `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="844c4-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="844c4-122">Remarks</span></span>  
 <span data-ttu-id="844c4-123">一般に、`+`可能であれば、算術加算を実行し、両方の式が文字列が場合にのみを連結します。</span><span class="sxs-lookup"><span data-stu-id="844c4-123">In general, `+` performs arithmetic addition when possible, and concatenates only when both expressions are strings.</span></span>  
  
 <span data-ttu-id="844c4-124">どちらの式がある場合、 `Object`、Visual Basic は、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="844c4-124">If neither expression is an `Object`, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="844c4-125">式のデータ型</span><span class="sxs-lookup"><span data-stu-id="844c4-125">Data types of expressions</span></span>|<span data-ttu-id="844c4-126">コンパイラによる処理</span><span class="sxs-lookup"><span data-stu-id="844c4-126">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="844c4-127">両方の式が数値データ型 (`SByte`、 `Byte`、 `Short`、 `UShort`、 `Integer`、 `UInteger`、 `Long`、 `ULong`、 `Decimal`、 `Single`、または`Double`)</span><span class="sxs-lookup"><span data-stu-id="844c4-127">Both expressions are numeric data types (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`)</span></span>|<span data-ttu-id="844c4-128">追加します。</span><span class="sxs-lookup"><span data-stu-id="844c4-128">Add.</span></span> <span data-ttu-id="844c4-129">結果のデータ型が数値型のデータ型に適した`expression1`と`expression2`します。</span><span class="sxs-lookup"><span data-stu-id="844c4-129">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="844c4-130">「整数の算術演算による」のテーブルを参照してください。[演算子結果のデータ型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="844c4-130">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="844c4-131">両方の式は型 `String`</span><span class="sxs-lookup"><span data-stu-id="844c4-131">Both expressions are of type `String`</span></span>|<span data-ttu-id="844c4-132">連結します。</span><span class="sxs-lookup"><span data-stu-id="844c4-132">Concatenate.</span></span>|  
|<span data-ttu-id="844c4-133">1 つの式が数値データ型で、他の文字列</span><span class="sxs-lookup"><span data-stu-id="844c4-133">One expression is a numeric data type and the other is a string</span></span>|<span data-ttu-id="844c4-134">場合`Option Strict`は`On`、コンパイラ エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="844c4-134">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="844c4-135">場合`Option Strict`は`Off`、暗黙的に変換、`String`に`Double`を追加します。</span><span class="sxs-lookup"><span data-stu-id="844c4-135">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="844c4-136">場合、`String`に変換できない`Double`、スローし、<xref:System.InvalidCastException>例外。</span><span class="sxs-lookup"><span data-stu-id="844c4-136">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="844c4-137">1 つの式が数値データ型、もう一方は[Nothing](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="844c4-137">One expression is a numeric data type, and the other is [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|<span data-ttu-id="844c4-138">追加すると`Nothing`値 0 にします。</span><span class="sxs-lookup"><span data-stu-id="844c4-138">Add, with `Nothing` valued as zero.</span></span>|  
|<span data-ttu-id="844c4-139">1 つの式が文字列、もう一方は `Nothing`</span><span class="sxs-lookup"><span data-stu-id="844c4-139">One expression is a string, and the other is `Nothing`</span></span>|<span data-ttu-id="844c4-140">使用した、連結`Nothing`として値を持つ""です。</span><span class="sxs-lookup"><span data-stu-id="844c4-140">Concatenate, with `Nothing` valued as "".</span></span>|  
  
 <span data-ttu-id="844c4-141">1 つの式がある場合、`Object`式では、Visual Basic は、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="844c4-141">If one expression is an `Object` expression, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="844c4-142">式のデータ型</span><span class="sxs-lookup"><span data-stu-id="844c4-142">Data types of expressions</span></span>|<span data-ttu-id="844c4-143">コンパイラによる処理</span><span class="sxs-lookup"><span data-stu-id="844c4-143">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="844c4-144">`Object` 式は、数値の値を保持し、もう一方の数値データ型</span><span class="sxs-lookup"><span data-stu-id="844c4-144">`Object` expression holds a numeric value and the other is a numeric data type</span></span>|<span data-ttu-id="844c4-145">場合`Option Strict`は`On`、コンパイラ エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="844c4-145">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="844c4-146">場合`Option Strict`は`Off`、しを追加します。</span><span class="sxs-lookup"><span data-stu-id="844c4-146">If `Option Strict` is `Off`, then add.</span></span>|  
|<span data-ttu-id="844c4-147">`Object` 式が数値の値を保持して、他の種類 `String`</span><span class="sxs-lookup"><span data-stu-id="844c4-147">`Object` expression holds a numeric value and the other is of type `String`</span></span>|<span data-ttu-id="844c4-148">場合`Option Strict`は`On`、コンパイラ エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="844c4-148">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="844c4-149">場合`Option Strict`は`Off`、暗黙的に変換、`String`に`Double`を追加します。</span><span class="sxs-lookup"><span data-stu-id="844c4-149">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="844c4-150">場合、`String`に変換できない`Double`、スローし、<xref:System.InvalidCastException>例外。</span><span class="sxs-lookup"><span data-stu-id="844c4-150">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="844c4-151">`Object` 式が文字列を保持し、もう一方の数値データ型</span><span class="sxs-lookup"><span data-stu-id="844c4-151">`Object` expression holds a string and the other is a numeric data type</span></span>|<span data-ttu-id="844c4-152">場合`Option Strict`は`On`、コンパイラ エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="844c4-152">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="844c4-153">場合`Option Strict`は`Off`、文字列を暗黙的に変換`Object`に`Double`を追加します。</span><span class="sxs-lookup"><span data-stu-id="844c4-153">If `Option Strict` is `Off`, then implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="844c4-154">場合、文字列`Object`に変換できない`Double`、スローし、<xref:System.InvalidCastException>例外。</span><span class="sxs-lookup"><span data-stu-id="844c4-154">If the string `Object` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="844c4-155">`Object` 式文字列を保持する、他の種類 `String`</span><span class="sxs-lookup"><span data-stu-id="844c4-155">`Object` expression holds a string and the other is of type `String`</span></span>|<span data-ttu-id="844c4-156">場合`Option Strict`は`On`、コンパイラ エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="844c4-156">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="844c4-157">場合`Option Strict`は`Off`、暗黙的に変換`Object`に`String`と連結します。</span><span class="sxs-lookup"><span data-stu-id="844c4-157">If `Option Strict` is `Off`, then implicitly convert `Object` to `String` and concatenate.</span></span>|  
  
 <span data-ttu-id="844c4-158">両方の式が場合`Object`式では、Visual Basic は、次の操作 (`Option Strict Off`のみ)。</span><span class="sxs-lookup"><span data-stu-id="844c4-158">If both expressions are `Object` expressions, Visual Basic takes the following actions (`Option Strict Off` only).</span></span>  
  
|<span data-ttu-id="844c4-159">式のデータ型</span><span class="sxs-lookup"><span data-stu-id="844c4-159">Data types of expressions</span></span>|<span data-ttu-id="844c4-160">コンパイラによる処理</span><span class="sxs-lookup"><span data-stu-id="844c4-160">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="844c4-161">どちらも`Object`式が数値の値を保持</span><span class="sxs-lookup"><span data-stu-id="844c4-161">Both `Object` expressions hold numeric values</span></span>|<span data-ttu-id="844c4-162">追加します。</span><span class="sxs-lookup"><span data-stu-id="844c4-162">Add.</span></span>|  
|<span data-ttu-id="844c4-163">どちらも`Object`型の式は、 `String`</span><span class="sxs-lookup"><span data-stu-id="844c4-163">Both `Object` expressions are of type `String`</span></span>|<span data-ttu-id="844c4-164">連結します。</span><span class="sxs-lookup"><span data-stu-id="844c4-164">Concatenate.</span></span>|  
|<span data-ttu-id="844c4-165">1 つ`Object`式には、数値の値が保持しているし、その他の文字列を保持</span><span class="sxs-lookup"><span data-stu-id="844c4-165">One `Object` expression holds a numeric value and the other holds a string</span></span>|<span data-ttu-id="844c4-166">文字列に暗黙的に変換`Object`に`Double`を追加します。</span><span class="sxs-lookup"><span data-stu-id="844c4-166">Implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="844c4-167">場合、文字列`Object`値を数値に変換することはできませんし、スロー、<xref:System.InvalidCastException>例外。</span><span class="sxs-lookup"><span data-stu-id="844c4-167">If the string `Object` cannot be converted to a numeric value, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
  
 <span data-ttu-id="844c4-168">いずれか`Object`式に評価される[Nothing](../../../visual-basic/language-reference/nothing.md)または<xref:System.DBNull>、`+`演算子として処理、`String`の値を持つ""。</span><span class="sxs-lookup"><span data-stu-id="844c4-168">If either `Object` expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md) or <xref:System.DBNull>, the `+` operator treats it as a `String` with a value of "".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="844c4-169">使用すると、`+`演算子、する可能性を追加または文字列の連結が発生するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="844c4-169">When you use the `+` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="844c4-170">使用して、`&`演算子の連結のあいまいさを排除し、自己文書化コードを提供します。</span><span class="sxs-lookup"><span data-stu-id="844c4-170">Use the `&` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="844c4-171">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="844c4-171">Overloading</span></span>  
 <span data-ttu-id="844c4-172">`+`演算子は、*オーバー ロードされた*、つまり、ことクラスまたは構造体を再定義できますその動作はそのクラスまたは構造体の型。</span><span class="sxs-lookup"><span data-stu-id="844c4-172">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="844c4-173">コードは、このようなクラスまたは構造体に、この演算子を使用する場合は、再定義された動作を確認ください。</span><span class="sxs-lookup"><span data-stu-id="844c4-173">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="844c4-174">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="844c4-174">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="844c4-175">例</span><span class="sxs-lookup"><span data-stu-id="844c4-175">Example</span></span>  
 <span data-ttu-id="844c4-176">次の例では、`+`番号を追加する演算子。</span><span class="sxs-lookup"><span data-stu-id="844c4-176">The following example uses the `+` operator to add numbers.</span></span> <span data-ttu-id="844c4-177">オペランドが両方の数値の場合は、Visual Basic は、算術演算の結果を計算します。</span><span class="sxs-lookup"><span data-stu-id="844c4-177">If the operands are both numeric, Visual Basic computes the arithmetic result.</span></span> <span data-ttu-id="844c4-178">算術演算の結果は、2 つのオペランドの合計を表します。</span><span class="sxs-lookup"><span data-stu-id="844c4-178">The arithmetic result represents the sum of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 <span data-ttu-id="844c4-179">使用することも、`+`文字列を連結する演算子。</span><span class="sxs-lookup"><span data-stu-id="844c4-179">You can also use the `+` operator to concatenate strings.</span></span> <span data-ttu-id="844c4-180">オペランドが両方の文字列の場合は、Visual Basic はそれらを連結します。</span><span class="sxs-lookup"><span data-stu-id="844c4-180">If the operands are both strings, Visual Basic concatenates them.</span></span> <span data-ttu-id="844c4-181">文字列連結の結果は、他の後に、2 つのオペランドの内容で構成される 1 つの文字列を表します。</span><span class="sxs-lookup"><span data-stu-id="844c4-181">The concatenation result represents a single string consisting of the contents of the two operands one after the other.</span></span>  
  
 <span data-ttu-id="844c4-182">結果は異なりますの設定は、オペランドが混合型である場合、 [Option Strict ステートメント](../../../visual-basic/language-reference/statements/option-strict-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="844c4-182">If the operands are of mixed types, the result depends on the setting of the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span> <span data-ttu-id="844c4-183">次の例は、結果を示しています。 ときに`Option Strict`は`On`します。</span><span class="sxs-lookup"><span data-stu-id="844c4-183">The following example illustrates the result when `Option Strict` is `On`.</span></span>  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 <span data-ttu-id="844c4-184">次の例は、結果を示しています。 ときに`Option Strict`は`Off`します。</span><span class="sxs-lookup"><span data-stu-id="844c4-184">The following example illustrates the result when `Option Strict` is `Off`.</span></span>  
  
 [!code-vb[VbVbalrOperators#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#54)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#52)]  
  
 <span data-ttu-id="844c4-185">あいまいさを排除するために使用する必要があります、`&`演算子の代わりに`+`連結します。</span><span class="sxs-lookup"><span data-stu-id="844c4-185">To eliminate ambiguity, you should use the `&` operator instead of `+` for concatenation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="844c4-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="844c4-186">See also</span></span>
- [<span data-ttu-id="844c4-187">& 演算子</span><span class="sxs-lookup"><span data-stu-id="844c4-187">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [<span data-ttu-id="844c4-188">連結演算子</span><span class="sxs-lookup"><span data-stu-id="844c4-188">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="844c4-189">算術演算子</span><span class="sxs-lookup"><span data-stu-id="844c4-189">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="844c4-190">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="844c4-190">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="844c4-191">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="844c4-191">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="844c4-192">Visual Basic における算術演算子</span><span class="sxs-lookup"><span data-stu-id="844c4-192">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="844c4-193">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="844c4-193">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
