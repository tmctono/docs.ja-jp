---
title: + 演算子
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
ms.openlocfilehash: 6ae3feae6ecb63b82426f2aa69359625bbffcec8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372117"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="5a1e2-102">+ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a1e2-102">+ Operator (Visual Basic)</span></span>
<span data-ttu-id="5a1e2-103">2 つの数値を加算するか、数値式の正の値を返します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-103">Adds two numbers or returns the positive value of a numeric expression.</span></span> <span data-ttu-id="5a1e2-104">2 つの文字列式の連結にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-104">Can also be used to concatenate two string expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a1e2-105">構文</span><span class="sxs-lookup"><span data-stu-id="5a1e2-105">Syntax</span></span>  
  
```vb
expression1 + expression2
```
  
<span data-ttu-id="5a1e2-106">or</span><span class="sxs-lookup"><span data-stu-id="5a1e2-106">or</span></span>

```vb  
+expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="5a1e2-107">指定項目</span><span class="sxs-lookup"><span data-stu-id="5a1e2-107">Parts</span></span>  
  
|<span data-ttu-id="5a1e2-108">用語</span><span class="sxs-lookup"><span data-stu-id="5a1e2-108">Term</span></span>|<span data-ttu-id="5a1e2-109">定義</span><span class="sxs-lookup"><span data-stu-id="5a1e2-109">Definition</span></span>|  
|---|---|  
|`expression1`|<span data-ttu-id="5a1e2-110">必須です。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-110">Required.</span></span> <span data-ttu-id="5a1e2-111">任意の数値または文字列の式。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-111">Any numeric or string expression.</span></span>|  
|`expression2`|<span data-ttu-id="5a1e2-112">`+` 演算子が負の値を計算する場合を除き、必須です。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-112">Required unless the `+` operator is calculating a negative value.</span></span> <span data-ttu-id="5a1e2-113">任意の数値または文字列の式。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-113">Any numeric or string expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="5a1e2-114">結果</span><span class="sxs-lookup"><span data-stu-id="5a1e2-114">Result</span></span>  
 <span data-ttu-id="5a1e2-115">`expression1` と `expression2` が両方とも数値の場合、結果はそれらの算術和になります。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-115">If `expression1` and `expression2` are both numeric, the result is their arithmetic sum.</span></span>  
  
 <span data-ttu-id="5a1e2-116">`expression2` がない場合、`+` 演算子は、変更されていない式の値の "*単項*" 恒等演算子です。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-116">If `expression2` is absent, the `+` operator is the *unary* identity operator for the unchanged value of an expression.</span></span> <span data-ttu-id="5a1e2-117">この意味では、この演算は `expression1` の符号を維持するため、`expression1` が負の場合は、結果が負になります。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-117">In this sense, the operation consists of retaining the sign of `expression1`, so the result is negative if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="5a1e2-118">`expression1` と `expression2` が両方とも文字列の場合、結果はそれらの値の連結です。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-118">If `expression1` and `expression2` are both strings, the result is the concatenation of their values.</span></span>  
  
 <span data-ttu-id="5a1e2-119">`expression1` と `expression2` の型が混在している場合、実行される処理は、その型、内容、および [Option Strict ステートメント](../statements/option-strict-statement.md)の設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-119">If `expression1` and `expression2` are of mixed types, the action taken depends on their types, their contents, and the setting of the [Option Strict Statement](../statements/option-strict-statement.md).</span></span> <span data-ttu-id="5a1e2-120">詳細については、「Remarks」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-120">For more information, see the tables in "Remarks."</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="5a1e2-121">サポートされている型</span><span class="sxs-lookup"><span data-stu-id="5a1e2-121">Supported Types</span></span>  
 <span data-ttu-id="5a1e2-122">すべての数値型。これには、符号なしおよび浮動小数点の型、`Decimal`、`String` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-122">All numeric types, including the unsigned and floating-point types and `Decimal`, and `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a1e2-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="5a1e2-123">Remarks</span></span>  
 <span data-ttu-id="5a1e2-124">一般に、`+` は可能な場合は算術加算を実行し、両方の式が文字列である場合にのみ連結します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-124">In general, `+` performs arithmetic addition when possible, and concatenates only when both expressions are strings.</span></span>  
  
 <span data-ttu-id="5a1e2-125">どちらの式も `Object` でない場合、Visual Basic では次の処理が実行されます。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-125">If neither expression is an `Object`, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="5a1e2-126">式のデータ型</span><span class="sxs-lookup"><span data-stu-id="5a1e2-126">Data types of expressions</span></span>|<span data-ttu-id="5a1e2-127">コンパイラによる処理</span><span class="sxs-lookup"><span data-stu-id="5a1e2-127">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="5a1e2-128">両方の式が数値データ型 (`SByte`、`Byte`、`Short`、`UShort`、`Integer`、`UInteger`、`Long`、`ULong`、`Decimal`、`Single`、または `Double`) である</span><span class="sxs-lookup"><span data-stu-id="5a1e2-128">Both expressions are numeric data types (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`)</span></span>|<span data-ttu-id="5a1e2-129">加算します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-129">Add.</span></span> <span data-ttu-id="5a1e2-130">結果のデータ型は、`expression1` および `expression2` のデータ型に適した数値型です。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-130">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="5a1e2-131">「[演算子の結果のデータ型](data-types-of-operator-results.md)」の「整数の算術演算」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-131">See the "Integer Arithmetic" tables in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="5a1e2-132">両方の式の型が `String` である</span><span class="sxs-lookup"><span data-stu-id="5a1e2-132">Both expressions are of type `String`</span></span>|<span data-ttu-id="5a1e2-133">連結します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-133">Concatenate.</span></span>|  
|<span data-ttu-id="5a1e2-134">一方の式は数値データ型であり、もう一方は文字列である</span><span class="sxs-lookup"><span data-stu-id="5a1e2-134">One expression is a numeric data type and the other is a string</span></span>|<span data-ttu-id="5a1e2-135">`Option Strict` が `On` である場合は、コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-135">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="5a1e2-136">`Option Strict` が `Off` である場合は、`String` を `Double` に暗黙的に変換して、加算します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-136">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="5a1e2-137">`String` を `Double` に変換できない場合は、<xref:System.InvalidCastException> 例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-137">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="5a1e2-138">一方の式は数値データ型であり、もう一方は [Nothing](../nothing.md) である</span><span class="sxs-lookup"><span data-stu-id="5a1e2-138">One expression is a numeric data type, and the other is [Nothing](../nothing.md)</span></span>|<span data-ttu-id="5a1e2-139">`Nothing` を 0 と評価して加算します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-139">Add, with `Nothing` valued as zero.</span></span>|  
|<span data-ttu-id="5a1e2-140">一方の式は文字列であり、もう一方は `Nothing` である</span><span class="sxs-lookup"><span data-stu-id="5a1e2-140">One expression is a string, and the other is `Nothing`</span></span>|<span data-ttu-id="5a1e2-141">`Nothing` を "" と評価して連結します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-141">Concatenate, with `Nothing` valued as "".</span></span>|  
  
 <span data-ttu-id="5a1e2-142">一方の式が `Object` 式の場合、Visual Basic では次の処理が実行されます。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-142">If one expression is an `Object` expression, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="5a1e2-143">式のデータ型</span><span class="sxs-lookup"><span data-stu-id="5a1e2-143">Data types of expressions</span></span>|<span data-ttu-id="5a1e2-144">コンパイラによる処理</span><span class="sxs-lookup"><span data-stu-id="5a1e2-144">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="5a1e2-145">`Object` 式は数値を保持し、もう一方は数値データ型である</span><span class="sxs-lookup"><span data-stu-id="5a1e2-145">`Object` expression holds a numeric value and the other is a numeric data type</span></span>|<span data-ttu-id="5a1e2-146">`Option Strict` が `On` である場合は、コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-146">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="5a1e2-147">`Option Strict` が `Off` である場合は、加算します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-147">If `Option Strict` is `Off`, then add.</span></span>|  
|<span data-ttu-id="5a1e2-148">`Object` 式は数値を保持し、もう一方は `String` 型である</span><span class="sxs-lookup"><span data-stu-id="5a1e2-148">`Object` expression holds a numeric value and the other is of type `String`</span></span>|<span data-ttu-id="5a1e2-149">`Option Strict` が `On` である場合は、コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-149">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="5a1e2-150">`Option Strict` が `Off` である場合は、`String` を `Double` に暗黙的に変換して、加算します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-150">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="5a1e2-151">`String` を `Double` に変換できない場合は、<xref:System.InvalidCastException> 例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-151">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="5a1e2-152">`Object` 式は文字列を保持し、もう一方は数値データ型である</span><span class="sxs-lookup"><span data-stu-id="5a1e2-152">`Object` expression holds a string and the other is a numeric data type</span></span>|<span data-ttu-id="5a1e2-153">`Option Strict` が `On` である場合は、コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-153">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="5a1e2-154">`Option Strict` が `Off` である場合は、文字列 `Object` を `Double` に暗黙的に変換して、加算します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-154">If `Option Strict` is `Off`, then implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="5a1e2-155">文字列 `Object` を `Double` に変換できない場合は、<xref:System.InvalidCastException> 例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-155">If the string `Object` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="5a1e2-156">`Object` 式は文字列を保持し、もう一方は `String` 型である</span><span class="sxs-lookup"><span data-stu-id="5a1e2-156">`Object` expression holds a string and the other is of type `String`</span></span>|<span data-ttu-id="5a1e2-157">`Option Strict` が `On` である場合は、コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-157">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="5a1e2-158">`Option Strict` が `Off` である場合、`Object` を `String` に暗黙的に変換して、連結します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-158">If `Option Strict` is `Off`, then implicitly convert `Object` to `String` and concatenate.</span></span>|  
  
 <span data-ttu-id="5a1e2-159">両方の式が `Object` 式の場合、Visual Basic は次の処理を実行します (`Option Strict Off` のみ)。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-159">If both expressions are `Object` expressions, Visual Basic takes the following actions (`Option Strict Off` only).</span></span>  
  
|<span data-ttu-id="5a1e2-160">式のデータ型</span><span class="sxs-lookup"><span data-stu-id="5a1e2-160">Data types of expressions</span></span>|<span data-ttu-id="5a1e2-161">コンパイラによる処理</span><span class="sxs-lookup"><span data-stu-id="5a1e2-161">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="5a1e2-162">両方の `Object` 式が数値を保持している</span><span class="sxs-lookup"><span data-stu-id="5a1e2-162">Both `Object` expressions hold numeric values</span></span>|<span data-ttu-id="5a1e2-163">加算します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-163">Add.</span></span>|  
|<span data-ttu-id="5a1e2-164">両方の `Object` 式の型が `String` である</span><span class="sxs-lookup"><span data-stu-id="5a1e2-164">Both `Object` expressions are of type `String`</span></span>|<span data-ttu-id="5a1e2-165">連結します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-165">Concatenate.</span></span>|  
|<span data-ttu-id="5a1e2-166">一方の `Object` 式は数値を保持し、もう一方は文字列を保持している</span><span class="sxs-lookup"><span data-stu-id="5a1e2-166">One `Object` expression holds a numeric value and the other holds a string</span></span>|<span data-ttu-id="5a1e2-167">文字列 `Object` を `Double` に暗黙的に変換して、加算します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-167">Implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="5a1e2-168">文字列 `Object` を数値に変換できない場合は、<xref:System.InvalidCastException> 例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-168">If the string `Object` cannot be converted to a numeric value, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
  
 <span data-ttu-id="5a1e2-169">いずれかの`Object` 式が [Nothing](../nothing.md) または <xref:System.DBNull> と評価される場合、 `+` 演算子はそれを値が "" である `String` として扱います。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-169">If either `Object` expression evaluates to [Nothing](../nothing.md) or <xref:System.DBNull>, the `+` operator treats it as a `String` with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5a1e2-170">`+` 演算子を使用すると、加算と文字列連結のどちらが発生するか判断できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-170">When you use the `+` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="5a1e2-171">連結には `&` 演算子を使用してあいまいさをなくし、自己文書化コードを実現してください。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-171">Use the `&` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="5a1e2-172">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="5a1e2-172">Overloading</span></span>  
 <span data-ttu-id="5a1e2-173">`+` 演算子は "*オーバーロード*" できます。つまり、オペランドがクラスまたは構造体の型を持っているときに、クラスまたは構造体はその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-173">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="5a1e2-174">コードで、そのようなクラスまたは構造体に対してこの演算子が使用される場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-174">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="5a1e2-175">詳細については、「 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-175">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a1e2-176">例</span><span class="sxs-lookup"><span data-stu-id="5a1e2-176">Example</span></span>  
 <span data-ttu-id="5a1e2-177">次の例では、`+` 演算子を使用して数値を加算します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-177">The following example uses the `+` operator to add numbers.</span></span> <span data-ttu-id="5a1e2-178">オペランドが両方とも数値の場合、Visual Basic は演算結果を計算します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-178">If the operands are both numeric, Visual Basic computes the arithmetic result.</span></span> <span data-ttu-id="5a1e2-179">算術結果は、2 つのオペランドの和を表します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-179">The arithmetic result represents the sum of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 <span data-ttu-id="5a1e2-180">`+` 演算子を使用して、文字列を連結することもできます。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-180">You can also use the `+` operator to concatenate strings.</span></span> <span data-ttu-id="5a1e2-181">オペランドが両方とも文字列の場合は、Visual Basic はそれらを連結します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-181">If the operands are both strings, Visual Basic concatenates them.</span></span> <span data-ttu-id="5a1e2-182">連結の結果は、2 つのオペランドがその順番どおりの内容で構成されている 1 つの文字列を表します。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-182">The concatenation result represents a single string consisting of the contents of the two operands one after the other.</span></span>  
  
 <span data-ttu-id="5a1e2-183">オペランドの型が混在する場合、結果は [Option Strict ステートメント](../statements/option-strict-statement.md)の設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-183">If the operands are of mixed types, the result depends on the setting of the [Option Strict Statement](../statements/option-strict-statement.md).</span></span> <span data-ttu-id="5a1e2-184">次の例は、`Option Strict` が `On` である場合の結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-184">The following example illustrates the result when `Option Strict` is `On`.</span></span>  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 <span data-ttu-id="5a1e2-185">次の例は、`Option Strict` が `Off` である場合の結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-185">The following example illustrates the result when `Option Strict` is `Off`.</span></span>  
  
 [!code-vb[VbVbalrOperators#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#54)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#52)]  
  
 <span data-ttu-id="5a1e2-186">あいまいさをなくすために、連結には、`+` の代わりに `&` 演算子を使用してください。</span><span class="sxs-lookup"><span data-stu-id="5a1e2-186">To eliminate ambiguity, you should use the `&` operator instead of `+` for concatenation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a1e2-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a1e2-187">See also</span></span>

- [<span data-ttu-id="5a1e2-188">& 演算子</span><span class="sxs-lookup"><span data-stu-id="5a1e2-188">& Operator</span></span>](concatenation-operator.md)
- [<span data-ttu-id="5a1e2-189">連結演算子</span><span class="sxs-lookup"><span data-stu-id="5a1e2-189">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="5a1e2-190">算術演算子</span><span class="sxs-lookup"><span data-stu-id="5a1e2-190">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="5a1e2-191">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="5a1e2-191">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="5a1e2-192">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="5a1e2-192">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="5a1e2-193">Visual Basic における算術演算子</span><span class="sxs-lookup"><span data-stu-id="5a1e2-193">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="5a1e2-194">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="5a1e2-194">Option Strict Statement</span></span>](../statements/option-strict-statement.md)
