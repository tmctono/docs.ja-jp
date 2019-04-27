---
title: データ型変換関数 (Visual Basic)
ms.date: 10/24/2018
f1_keywords:
- vb.CUShort
- vb.csng
- vb.CDate
- CByte
- CSng
- vb.CDec
- CBool
- CStr
- vb.CULng
- CDec
- CVErr
- CDbl
- CShort
- vb.CObj
- vb.CVErr
- CULng
- vb.cdbl
- vb.cbool
- CObj
- CDate
- CLng
- vb.cstr
- vb.cbyte
- vb.clng
- vb.CChar
- CUShort
- vb.CUInt
- vb.cint
- vb.CShort
- CInt
- CUInt
- CChar
helpviewer_keywords:
- CDate function
- CByte function
- Integer data type [Visual Basic], converting
- string conversion [Visual Basic], conversion functions
- fractions
- data types [Visual Basic], converting
- text, converting
- CDec function
- Char data type [Visual Basic], converting
- type conversion [Visual Basic], functions for
- Single data type [Visual Basic], converting
- numbers [Visual Basic], rounding
- rounding numbers [Visual Basic], type conversion
- CUShort function
- Long data type [Visual Basic], converting
- return values [Visual Basic], data types
- single-precision numbers [Visual Basic], converting
- data type conversion [Visual Basic], functions for
- CStr function
- times [Visual Basic], converting
- CSng function
- conversions [Visual Basic], type conversion functions
- CBool function
- CDbl function
- CUInt function
- Currency data type [Visual Basic], conversion functions
- numbers [Visual Basic], converting
- Double data type [Visual Basic], converting
- CLng function
- CSByte function
- double-precision numbers
- Decimal data type [Visual Basic], converting
- Boolean data type [Visual Basic], converting
- integers [Visual Basic], type conversion functions
- dates [Visual Basic], converting
- CULng function
- CInt function
- Date data type [Visual Basic], converting
- Byte data type [Visual Basic], converting
- String data type [Visual Basic], converting
- CChar function
- banker's rounding
- Short data type [Visual Basic], converting
- rounding numbers [Visual Basic], banker's rounding
- type conversion [Visual Basic], Visual Basic vs. .NET Framework
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
ms.openlocfilehash: 56dad921b2900061dbe2db0d8f1faaf759641f87
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802298"
---
# <a name="type-conversion-functions-visual-basic"></a><span data-ttu-id="2b527-102">データ型変換関数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b527-102">Type Conversion Functions (Visual Basic)</span></span>
<span data-ttu-id="2b527-103">これらの関数は、インラインでのコンパイル、つまり、変換コード式を評価するコードの一部です。</span><span class="sxs-lookup"><span data-stu-id="2b527-103">These functions are compiled inline, meaning the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="2b527-104">場合によってパフォーマンスを向上させると、変換を実行するプロシージャの呼び出しではありません。</span><span class="sxs-lookup"><span data-stu-id="2b527-104">Sometimes there is no call to a procedure to accomplish the conversion, which improves performance.</span></span> <span data-ttu-id="2b527-105">各関数は、特定のデータ型に式を変換します。</span><span class="sxs-lookup"><span data-stu-id="2b527-105">Each function coerces an expression to a specific data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b527-106">構文</span><span class="sxs-lookup"><span data-stu-id="2b527-106">Syntax</span></span>  
  
```  
CBool(expression)  
CByte(expression)  
CChar(expression)  
CDate(expression)  
CDbl(expression)  
CDec(expression)  
CInt(expression)  
CLng(expression)  
CObj(expression)  
CSByte(expression)  
CShort(expression)  
CSng(expression)  
CStr(expression)  
CUInt(expression)  
CULng(expression)  
CUShort(expression)  
```  
  
## <a name="part"></a><span data-ttu-id="2b527-107">パーツ</span><span class="sxs-lookup"><span data-stu-id="2b527-107">Part</span></span>  
 `expression`  
 <span data-ttu-id="2b527-108">必須。</span><span class="sxs-lookup"><span data-stu-id="2b527-108">Required.</span></span> <span data-ttu-id="2b527-109">ソースのデータ型の任意の式。</span><span class="sxs-lookup"><span data-stu-id="2b527-109">Any expression of the source data type.</span></span>  
  
## <a name="return-value-data-type"></a><span data-ttu-id="2b527-110">戻り値のデータ型</span><span class="sxs-lookup"><span data-stu-id="2b527-110">Return Value Data Type</span></span>  
 <span data-ttu-id="2b527-111">関数名は、次の表に示すように、返す値のデータ型を決定します。</span><span class="sxs-lookup"><span data-stu-id="2b527-111">The function name determines the data type of the value it returns, as shown in the following table.</span></span>  
  
|<span data-ttu-id="2b527-112">関数名</span><span class="sxs-lookup"><span data-stu-id="2b527-112">Function name</span></span>|<span data-ttu-id="2b527-113">戻り値のデータ型</span><span class="sxs-lookup"><span data-stu-id="2b527-113">Return data type</span></span>|<span data-ttu-id="2b527-114">範囲を指定`expression`引数</span><span class="sxs-lookup"><span data-stu-id="2b527-114">Range for `expression` argument</span></span>|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[<span data-ttu-id="2b527-115">Boolean データ型</span><span class="sxs-lookup"><span data-stu-id="2b527-115">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="2b527-116">任意の有効な`Char`または`String`または数値式です。</span><span class="sxs-lookup"><span data-stu-id="2b527-116">Any valid `Char` or `String` or numeric expression.</span></span>|  
|`CByte`|[<span data-ttu-id="2b527-117">Byte データ型</span><span class="sxs-lookup"><span data-stu-id="2b527-117">Byte Data Type</span></span>](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="2b527-118"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) を通じて<xref:System.Byte.MaxValue?displayProperty=nameWithType>(255) (未署名) 小数部は丸められます。<sup> 。1</sup></span><span class="sxs-lookup"><span data-stu-id="2b527-118"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) through <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="2b527-119">Visual Basic 15.8 以降、Visual Basic で浮動小数点数バイトを使用する変換からのパフォーマンスを最適化、`CByte`関数です。 はを参照してください、[解説](#remarks)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="2b527-119">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to byte conversion with the `CByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="2b527-120">参照してください、 [CInt 例](#cint-example)例については、セクション。</span><span class="sxs-lookup"><span data-stu-id="2b527-120">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CChar`|[<span data-ttu-id="2b527-121">Char データ型</span><span class="sxs-lookup"><span data-stu-id="2b527-121">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="2b527-122">任意の有効な`Char`または`String`式。 の最初の文字のみを`String`変換されます。 値は 0 ~ 65535 (符号なし) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2b527-122">Any valid `Char` or `String` expression; only first character of a `String` is converted; value can be 0 through 65535 (unsigned).</span></span>|  
|`CDate`|[<span data-ttu-id="2b527-123">Date データ型</span><span class="sxs-lookup"><span data-stu-id="2b527-123">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="2b527-124">任意の有効な日付と時刻の表現。</span><span class="sxs-lookup"><span data-stu-id="2b527-124">Any valid representation of a date and time.</span></span>|  
|`CDbl`|[<span data-ttu-id="2b527-125">Double 型</span><span class="sxs-lookup"><span data-stu-id="2b527-125">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="2b527-126">-- を 4.94065645841246544E-(負の値)。4.94065645841246544E-324 正の値の 1.79769313486231570 e + 308 ~。</span><span class="sxs-lookup"><span data-stu-id="2b527-126">-1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values; 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span>|  
|`CDec`|[<span data-ttu-id="2b527-127">Decimal データ型</span><span class="sxs-lookup"><span data-stu-id="2b527-127">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="2b527-128">数字の 0 の 79,228,162,514,264,337,593,543,950,335、+/-小数点以下の桁数は、番号します。</span><span class="sxs-lookup"><span data-stu-id="2b527-128">+/-79,228,162,514,264,337,593,543,950,335 for zero-scaled numbers, that is, numbers with no decimal places.</span></span> <span data-ttu-id="2b527-129">数値の小数点以下桁数が 28 場合、範囲は、7.9228162514264337593543950335 です。</span><span class="sxs-lookup"><span data-stu-id="2b527-129">For numbers with 28 decimal places, the range is +/-7.9228162514264337593543950335.</span></span> <span data-ttu-id="2b527-130">最小の可能な 0 以外の数値は、(1 e ~ 28) +/-0.0000000000000000000000000001 です。</span><span class="sxs-lookup"><span data-stu-id="2b527-130">The smallest possible non-zero number is 0.0000000000000000000000000001 (+/-1E-28).</span></span>|  
|`CInt`|[<span data-ttu-id="2b527-131">Integer データ型</span><span class="sxs-lookup"><span data-stu-id="2b527-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="2b527-132"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2,147,483,648) を通じて<xref:System.Int32.MaxValue?displayProperty=nameWithType>(2,147, 483,647) です小数部は丸められます。<sup> 。1</sup></span><span class="sxs-lookup"><span data-stu-id="2b527-132"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2,147,483,648) through <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2,147,483,647); fractional parts are rounded.<sup>1</sup></span></span> <br/><br/><span data-ttu-id="2b527-133">Visual Basic 15.8 以降、Visual Basic で浮動小数点数に整数型の変換からのパフォーマンスを最適化、`CInt`関数です。 はを参照してください、[解説](#remarks)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="2b527-133">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to integer conversion with the `CInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="2b527-134">参照してください、 [CInt 例](#cint-example)例については、セクション。</span><span class="sxs-lookup"><span data-stu-id="2b527-134">See the [CInt Example](#cint-example) section for an example.</span></span> |  
|`CLng`|[<span data-ttu-id="2b527-135">Long データ型</span><span class="sxs-lookup"><span data-stu-id="2b527-135">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="2b527-136"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9,223,372,036,854,775,808) を通じて<xref:System.Int64.MaxValue?displayProperty=nameWithType>(9,223,372,036,854,775,807) 小数部は丸められます。<sup> 。1</sup></span><span class="sxs-lookup"><span data-stu-id="2b527-136"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9,223,372,036,854,775,808) through <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9,223,372,036,854,775,807); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="2b527-137">Visual Basic 15.8 以降、Visual Basic で浮動小数点数に 64 ビット整数の変換からのパフォーマンスを最適化、`CLng`関数です。 はを参照してください、[解説](#remarks)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="2b527-137">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 64-bit integer conversion with the `CLng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="2b527-138">参照してください、 [CInt 例](#cint-example)例については、セクション。</span><span class="sxs-lookup"><span data-stu-id="2b527-138">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CObj`|[<span data-ttu-id="2b527-139">Object 型</span><span class="sxs-lookup"><span data-stu-id="2b527-139">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="2b527-140">任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="2b527-140">Any valid expression.</span></span>|  
|`CSByte`|[<span data-ttu-id="2b527-141">SByte データ型</span><span class="sxs-lookup"><span data-stu-id="2b527-141">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="2b527-142"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) を通じて<xref:System.SByte.MaxValue?displayProperty=nameWithType>(127) 小数部は丸められます。<sup> 。1</sup></span><span class="sxs-lookup"><span data-stu-id="2b527-142"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) through <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="2b527-143">Visual Basic 15.8 以降、Visual Basic で浮動小数点数を使用する符号付きバイト変換からのパフォーマンスを最適化、`CSByte`関数です。 はを参照してください、[解説](#remarks)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="2b527-143">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to signed byte conversion with the `CSByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="2b527-144">参照してください、 [CInt 例](#cint-example)例については、セクション。</span><span class="sxs-lookup"><span data-stu-id="2b527-144">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CShort`|[<span data-ttu-id="2b527-145">Short データ型</span><span class="sxs-lookup"><span data-stu-id="2b527-145">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="2b527-146"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32,768) を通じて<xref:System.Int16.MaxValue?displayProperty=nameWithType>(32,767) 小数部は丸められます。<sup> 。1</sup></span><span class="sxs-lookup"><span data-stu-id="2b527-146"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32,768) through <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32,767); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="2b527-147">Visual Basic 15.8 以降、Visual Basic で浮動小数点数 16 ビット整数を使用する変換からのパフォーマンスを最適化、`CShort`関数です。 はを参照してください、[解説](#remarks)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="2b527-147">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 16-bit integer conversion with the `CShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="2b527-148">参照してください、 [CInt 例](#cint-example)例については、セクション。</span><span class="sxs-lookup"><span data-stu-id="2b527-148">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CSng`|[<span data-ttu-id="2b527-149">Single データ型</span><span class="sxs-lookup"><span data-stu-id="2b527-149">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="2b527-150">-3.402823 e + 38 ~ - 1.401298E-45 の負の値。1.401298E-45 ~ 3.402823 e + 38 の正の値。</span><span class="sxs-lookup"><span data-stu-id="2b527-150">-3.402823E+38 through -1.401298E-45 for negative values; 1.401298E-45 through 3.402823E+38 for positive values.</span></span>|  
|`CStr`|[<span data-ttu-id="2b527-151">String データ型</span><span class="sxs-lookup"><span data-stu-id="2b527-151">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="2b527-152">返します`CStr`に依存、`expression`引数。</span><span class="sxs-lookup"><span data-stu-id="2b527-152">Returns for `CStr` depend on the `expression` argument.</span></span> <span data-ttu-id="2b527-153">参照してください[CStr 関数の戻り値](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md)します。</span><span class="sxs-lookup"><span data-stu-id="2b527-153">See [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>|  
|`CUInt`|[<span data-ttu-id="2b527-154">UInteger データ型</span><span class="sxs-lookup"><span data-stu-id="2b527-154">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="2b527-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) を通じて<xref:System.UInt32.MaxValue?displayProperty=nameWithType>(4,294,967,295) (未署名) 小数部は丸められます。<sup> 。1</sup></span><span class="sxs-lookup"><span data-stu-id="2b527-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4,294,967,295) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="2b527-156">Visual Basic 15.8 以降、Visual Basic で浮動小数点数の符号なし整数型の変換からのパフォーマンスを最適化、`CUInt`関数です。 はを参照してください、[解説](#remarks)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="2b527-156">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned integer conversion with the `CUInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="2b527-157">参照してください、 [CInt 例](#cint-example)例については、セクション。</span><span class="sxs-lookup"><span data-stu-id="2b527-157">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CULng`|[<span data-ttu-id="2b527-158">ULong データ型</span><span class="sxs-lookup"><span data-stu-id="2b527-158">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="2b527-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) を通じて<xref:System.UInt64.MaxValue?displayProperty=nameWithType>(18,446,744,073,709,551,615) (未署名) 小数部は丸められます。<sup> 。1</sup></span><span class="sxs-lookup"><span data-stu-id="2b527-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18,446,744,073,709,551,615) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="2b527-160">Visual Basic 15.8 以降、Visual Basic での符号なし長整数に変換する浮動小数点のパフォーマンスを最適化、`CULng`関数です。 はを参照してください、[解説](#remarks)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="2b527-160">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned long integer conversion with the `CULng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="2b527-161">参照してください、 [CInt 例](#cint-example)例については、セクション。</span><span class="sxs-lookup"><span data-stu-id="2b527-161">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CUShort`|[<span data-ttu-id="2b527-162">UShort データ型</span><span class="sxs-lookup"><span data-stu-id="2b527-162">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="2b527-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) を通じて<xref:System.UInt16.MaxValue?displayProperty=nameWithType>(65,535) (未署名) 小数部は丸められます。<sup> 。1</sup></span><span class="sxs-lookup"><span data-stu-id="2b527-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65,535) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="2b527-164">Visual Basic 15.8 以降、Visual Basic で浮動小数点数 16 ビット符号なし整数を使用する変換からのパフォーマンスを最適化、`CUShort`関数です。 はを参照してください、[解説](#remarks)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="2b527-164">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned 16-bit integer conversion with the `CUShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="2b527-165">参照してください、 [CInt 例](#cint-example)例については、セクション。</span><span class="sxs-lookup"><span data-stu-id="2b527-165">See the [CInt Example](#cint-example) section for an example.</span></span>|  
  
 <span data-ttu-id="2b527-166"><sup>1</sup>小数部分は、特殊な種類と呼ばれる丸め処理を行うを受けることができます*銀行型丸め*します。</span><span class="sxs-lookup"><span data-stu-id="2b527-166"><sup>1</sup> Fractional parts can be subject to a special type of rounding called *banker's rounding*.</span></span> <span data-ttu-id="2b527-167">詳細については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b527-167">See "Remarks" for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b527-168">Remarks</span><span class="sxs-lookup"><span data-stu-id="2b527-168">Remarks</span></span>  
 <span data-ttu-id="2b527-169">原則として、する必要がありますを使用する方が優先的 .NET Framework のメソッドは、Visual Basic の型変換関数など`ToString()`、いずれかで、<xref:System.Convert>クラスまたは個々 の型の構造体またはクラスにします。</span><span class="sxs-lookup"><span data-stu-id="2b527-169">As a rule, you should use the Visual Basic type conversion functions in preference to the .NET Framework methods such as `ToString()`, either on the <xref:System.Convert> class or on an individual type structure or class.</span></span> <span data-ttu-id="2b527-170">Visual Basic の関数は、Visual Basic コードの最適な対話のために設計されていて、ソース コードを短く読みやすくすることも、します。</span><span class="sxs-lookup"><span data-stu-id="2b527-170">The Visual Basic functions are designed for optimal interaction with Visual Basic code, and they also make your source code shorter and easier to read.</span></span> <span data-ttu-id="2b527-171">さらに、.NET Framework の変換メソッドは常に結果を生成しない、同じ例では変換するときに、Visual Basic の関数として`Boolean`に`Integer`します。</span><span class="sxs-lookup"><span data-stu-id="2b527-171">In addition, the .NET Framework conversion methods do not always produce the same results as the Visual Basic functions, for example when converting `Boolean` to `Integer`.</span></span> <span data-ttu-id="2b527-172">詳細については、次を参照してください。[データ型のトラブルシューティング](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="2b527-172">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  

<span data-ttu-id="2b527-173">Visual Basic 15.8 から始めてに渡すときに、浮動-小数点からに整数型の変換のパフォーマンスは最適化された、<xref:System.Single>または<xref:System.Double>整数変換関数のいずれかに、次のメソッドによって返される値 (`CByte`、 `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span><span class="sxs-lookup"><span data-stu-id="2b527-173">Starting with Visual Basic 15.8, the performance of floating-point-to-integer conversion is optimized when you pass the <xref:System.Single> or <xref:System.Double> value returned by the following methods to one of the integer conversion functions (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Single)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Single)?displayProperty=nameWithType>
- <xref:System.Math.Ceiling(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Floor(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Round(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Truncate(System.Double)?displayProperty=nameWithType>

<span data-ttu-id="2b527-174">この最適化を行うコードを 2 回ほど高速に実行する整数の変換の数が多い。</span><span class="sxs-lookup"><span data-stu-id="2b527-174">This optimization allows code that does a large number of integer conversions to run up to twice as fast.</span></span> <span data-ttu-id="2b527-175">次の例は、最適化された浮動-小数点 integer 型変換を示しています。</span><span class="sxs-lookup"><span data-stu-id="2b527-175">The following example illustrates these optimized floating-point-to-integer conversions:</span></span>

```vb
Dim s As Single = 173.7619
Dim d As Double = s 

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

## <a name="behavior"></a><span data-ttu-id="2b527-176">動作</span><span class="sxs-lookup"><span data-stu-id="2b527-176">Behavior</span></span>  
  
-   <span data-ttu-id="2b527-177">**強制型変換。**</span><span class="sxs-lookup"><span data-stu-id="2b527-177">**Coercion.**</span></span> <span data-ttu-id="2b527-178">一般に、既定のデータ型ではなく、特定のデータ型を操作の結果を強制的にデータ型の変換関数を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2b527-178">In general, you can use the data type conversion functions to coerce the result of an operation to a particular data type rather than the default data type.</span></span> <span data-ttu-id="2b527-179">たとえば、使用して`CDec`単精度、倍精度、または整数演算が通常行う場所の場合の 10 進数の演算を強制的にします。</span><span class="sxs-lookup"><span data-stu-id="2b527-179">For example, use `CDec` to force decimal arithmetic in cases where single-precision, double-precision, or integer arithmetic would normally take place.</span></span>  
  
-   <span data-ttu-id="2b527-180">**変換の失敗。**</span><span class="sxs-lookup"><span data-stu-id="2b527-180">**Failed Conversions.**</span></span> <span data-ttu-id="2b527-181">場合、`expression`先は、変換されるデータ型の範囲外は、関数に渡される、<xref:System.OverflowException>に発生します。</span><span class="sxs-lookup"><span data-stu-id="2b527-181">If the `expression` passed to the function is outside the range of the data type to which it is to be converted, an <xref:System.OverflowException> occurs.</span></span>  
  
-   <span data-ttu-id="2b527-182">**小数部分。**</span><span class="sxs-lookup"><span data-stu-id="2b527-182">**Fractional Parts.**</span></span> <span data-ttu-id="2b527-183">整数以外の値を整数に変換すると、型、整数の変換関数 (`CByte`、 `CInt`、 `CLng`、 `CSByte`、 `CShort`、 `CUInt`、 `CULng`、および`CUShort`) を削除します小数部し、を最も近い整数値に切り上げられます。</span><span class="sxs-lookup"><span data-stu-id="2b527-183">When you convert a nonintegral value to an integral type, the integer conversion functions (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, and `CUShort`) remove the fractional part and round the value to the closest integer.</span></span>  
  
     <span data-ttu-id="2b527-184">小数部が正確に場合は 0.5、整数の変換関数に丸める、近い偶数の整数。</span><span class="sxs-lookup"><span data-stu-id="2b527-184">If the fractional part is exactly 0.5, the integer conversion functions round it to the nearest even integer.</span></span> <span data-ttu-id="2b527-185">たとえば、0.5 は、0、および 1.5 および 2.5 は 2 にどちらに丸められます。</span><span class="sxs-lookup"><span data-stu-id="2b527-185">For example, 0.5 rounds to 0, and 1.5 and 2.5 both round to 2.</span></span> <span data-ttu-id="2b527-186">これと呼ぶことが*銀行型丸め*目的は、このような多くの数値を一緒に追加するときに蓄積する偏りを補正するためにします。</span><span class="sxs-lookup"><span data-stu-id="2b527-186">This is sometimes called *banker's rounding*, and its purpose is to compensate for a bias that could accumulate when adding many such numbers together.</span></span>  
  
     <span data-ttu-id="2b527-187">`CInt` `CLng`とは異なる、<xref:Microsoft.VisualBasic.Conversion.Int%2A>と<xref:Microsoft.VisualBasic.Conversion.Fix%2A>切り上げるには、数値の小数部ではなく、切り捨て関数。</span><span class="sxs-lookup"><span data-stu-id="2b527-187">`CInt` and `CLng` differ from the <xref:Microsoft.VisualBasic.Conversion.Int%2A> and <xref:Microsoft.VisualBasic.Conversion.Fix%2A> functions, which truncate, rather than round, the fractional part of a number.</span></span> <span data-ttu-id="2b527-188">また、`Fix`と`Int`内を通過すると常に同じデータ型の値を返します。</span><span class="sxs-lookup"><span data-stu-id="2b527-188">Also, `Fix` and `Int` always return a value of the same data type as you pass in.</span></span>  
  
-   <span data-ttu-id="2b527-189">**日付/時刻の変換。**</span><span class="sxs-lookup"><span data-stu-id="2b527-189">**Date/Time Conversions.**</span></span> <span data-ttu-id="2b527-190">使用して、<xref:Microsoft.VisualBasic.Information.IsDate%2A>値を日付と時刻に変換できるかどうかを判断する関数。</span><span class="sxs-lookup"><span data-stu-id="2b527-190">Use the <xref:Microsoft.VisualBasic.Information.IsDate%2A> function to determine if a value can be converted to a date and time.</span></span> <span data-ttu-id="2b527-191">`CDate` リテラルの日付と時刻リテラルが数値以外の値を認識します。</span><span class="sxs-lookup"><span data-stu-id="2b527-191">`CDate` recognizes date literals and time literals but not numeric values.</span></span> <span data-ttu-id="2b527-192">Visual Basic 6.0 を変換する`Date`値を`Date`Visual Basic 2005 での値、または以降のバージョンを使用できます、<xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="2b527-192">To convert a Visual Basic 6.0 `Date` value to a `Date` value in Visual Basic 2005 or later versions, you can use the <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="2b527-193">**中立的な日付/時刻値。**</span><span class="sxs-lookup"><span data-stu-id="2b527-193">**Neutral Date/Time Values.**</span></span> <span data-ttu-id="2b527-194">[Date データ型](../../../visual-basic/language-reference/data-types/date-data-type.md)常に 日付と時刻の両方の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b527-194">The [Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md) always contains both date and time information.</span></span> <span data-ttu-id="2b527-195">型変換のために、Visual Basic であると見なす 1/1/0001 (年 1 月 1日年 1 月)、*ニュートラル値*を時間のニュートラル値の日付、および 00時 00分: 00 (午前 0 時)。</span><span class="sxs-lookup"><span data-stu-id="2b527-195">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="2b527-196">変換する場合、`Date`値を文字列では、`CStr`結果の文字列に基準値を含めません。</span><span class="sxs-lookup"><span data-stu-id="2b527-196">If you convert a `Date` value to a string, `CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="2b527-197">たとえば、変換する`#January 1, 0001 9:30:00#`結果は"9時 30分: 00 AM"を文字列には、日付情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="2b527-197">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="2b527-198">ただし、日付情報は、元に引き続き存在`Date`値し、などの関数で回復できる<xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>関数。</span><span class="sxs-lookup"><span data-stu-id="2b527-198">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span></span>  
  
-   <span data-ttu-id="2b527-199">**カルチャの区別。**</span><span class="sxs-lookup"><span data-stu-id="2b527-199">**Culture Sensitivity.**</span></span> <span data-ttu-id="2b527-200">文字列に関係する型変換関数は、アプリケーションの現在のカルチャ設定に基づいて変換を実行します。</span><span class="sxs-lookup"><span data-stu-id="2b527-200">The type conversion functions involving strings perform conversions based on the current culture settings for the application.</span></span> <span data-ttu-id="2b527-201">たとえば、`CDate`システムのロケール設定に従って日付形式を認識します。</span><span class="sxs-lookup"><span data-stu-id="2b527-201">For example, `CDate` recognizes date formats according to the locale setting of your system.</span></span> <span data-ttu-id="2b527-202">日、月、および使用されるロケールの正しい順序で年を指定するか、日付が正しく解釈されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2b527-202">You must provide the day, month, and year in the correct order for your locale, or the date might not be interpreted correctly.</span></span> <span data-ttu-id="2b527-203">長い日付形式は、"Wednesday"などの曜日の文字列が含まれている場合は認識されません。</span><span class="sxs-lookup"><span data-stu-id="2b527-203">A long date format is not recognized if it contains a day-of-the-week string, such as "Wednesday".</span></span>  
  
     <span data-ttu-id="2b527-204">または現在のロケールで指定した以外の形式で値の文字列形式からに変換する必要がある場合は、Visual Basic の型変換関数を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="2b527-204">If you need to convert to or from a string representation of a value in a format other than the one specified by your locale, you cannot use the Visual Basic type conversion functions.</span></span> <span data-ttu-id="2b527-205">これを行うには、使用、`ToString(IFormatProvider)`と`Parse(String, IFormatProvider)`値の型のメソッド。</span><span class="sxs-lookup"><span data-stu-id="2b527-205">To do this, use the `ToString(IFormatProvider)` and `Parse(String, IFormatProvider)` methods of that value's type.</span></span> <span data-ttu-id="2b527-206">などを使用して、<xref:System.Double.Parse%2A?displayProperty=nameWithType>を文字列に変換するときに、`Double`を使用して<xref:System.Double.ToString%2A?displayProperty=nameWithType>型の値を変換するときに`Double`文字列にします。</span><span class="sxs-lookup"><span data-stu-id="2b527-206">For example, use <xref:System.Double.Parse%2A?displayProperty=nameWithType> when converting a string to a `Double`, and use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a string.</span></span>  
  
## <a name="ctype-function"></a><span data-ttu-id="2b527-207">CType Function</span><span class="sxs-lookup"><span data-stu-id="2b527-207">CType Function</span></span>  
 <span data-ttu-id="2b527-208">[CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) 2 番目の引数を受け取り`typename`、型に変換および`expression`に`typename`ここで、`typename`任意のデータ型、構造体、クラス、またはインターフェイスの有効な変換が存在することができます。</span><span class="sxs-lookup"><span data-stu-id="2b527-208">The [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) takes a second argument, `typename`, and coerces `expression` to `typename`, where `typename` can be any data type, structure, class, or interface to which there exists a valid conversion.</span></span>  
  
 <span data-ttu-id="2b527-209">比較について`CType`他の型変換キーワードで、次を参照してください。 [DirectCast 演算子](../../../visual-basic/language-reference/operators/directcast-operator.md)と[TryCast 演算子](../../../visual-basic/language-reference/operators/trycast-operator.md)します。</span><span class="sxs-lookup"><span data-stu-id="2b527-209">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>  
  
## <a name="cbool-example"></a><span data-ttu-id="2b527-210">CBool 例</span><span class="sxs-lookup"><span data-stu-id="2b527-210">CBool Example</span></span>  
 <span data-ttu-id="2b527-211">次の例では、`CBool`関数を式に変換する`Boolean`値。</span><span class="sxs-lookup"><span data-stu-id="2b527-211">The following example uses the `CBool` function to convert expressions to `Boolean` values.</span></span> <span data-ttu-id="2b527-212">式が 0 以外の値に評価される場合`CBool`返します`True`。 それ以外を返します`False`します。</span><span class="sxs-lookup"><span data-stu-id="2b527-212">If an expression evaluates to a nonzero value, `CBool` returns `True`; otherwise, it returns `False`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#1)]  
  
## <a name="cbyte-example"></a><span data-ttu-id="2b527-213">CByte 例</span><span class="sxs-lookup"><span data-stu-id="2b527-213">CByte Example</span></span>  
 <span data-ttu-id="2b527-214">次の例では、`CByte`関数を式に変換する、`Byte`します。</span><span class="sxs-lookup"><span data-stu-id="2b527-214">The following example uses the `CByte` function to convert an expression to a `Byte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#2)]  
  
## <a name="cchar-example"></a><span data-ttu-id="2b527-215">Cchar 関数の例</span><span class="sxs-lookup"><span data-stu-id="2b527-215">CChar Example</span></span>  
 <span data-ttu-id="2b527-216">次の例では、`CChar`関数の最初の文字に変換する、`String`に式を`Char`型。</span><span class="sxs-lookup"><span data-stu-id="2b527-216">The following example uses the `CChar` function to convert the first character of a `String` expression to a `Char` type.</span></span>  
  
 [!code-vb[VbVbalrFunctions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#3)]  
  
 <span data-ttu-id="2b527-217">入力引数`CChar`データ型でなければなりません`Char`または`String`します。</span><span class="sxs-lookup"><span data-stu-id="2b527-217">The input argument to `CChar` must be of data type `Char` or `String`.</span></span> <span data-ttu-id="2b527-218">使用することはできません`CChar`ため文字に数値を変換する`CChar`数値データ型を受け入れることはできません。</span><span class="sxs-lookup"><span data-stu-id="2b527-218">You cannot use `CChar` to convert a number to a character, because `CChar` cannot accept a numeric data type.</span></span> <span data-ttu-id="2b527-219">次の例では、コード ポイント (文字コード) を表す数値を取得し、対応する文字に変換します。</span><span class="sxs-lookup"><span data-stu-id="2b527-219">The following example obtains a number representing a code point (character code) and converts it to the corresponding character.</span></span> <span data-ttu-id="2b527-220">使用して、<xref:Microsoft.VisualBasic.Interaction.InputBox%2A>桁の数字の文字列を取得する関数`CInt`入力文字列に変換する`Integer`、および`ChrW`入力数に変換する`Char`します。</span><span class="sxs-lookup"><span data-stu-id="2b527-220">It uses the <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> function to obtain the string of digits, `CInt` to convert the string to type `Integer`, and `ChrW` to convert the number to type `Char`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#4)]  
  
## <a name="cdate-example"></a><span data-ttu-id="2b527-221">Cdate 関数の例</span><span class="sxs-lookup"><span data-stu-id="2b527-221">CDate Example</span></span>  
 <span data-ttu-id="2b527-222">次の例では、`CDate`に文字列を変換する関数`Date`値。</span><span class="sxs-lookup"><span data-stu-id="2b527-222">The following example uses the `CDate` function to convert strings to `Date` values.</span></span> <span data-ttu-id="2b527-223">一般に、ハードコーディングされた日付と時刻を (この例で示す) のように文字列としては推奨されません。</span><span class="sxs-lookup"><span data-stu-id="2b527-223">In general, hard-coding dates and times as strings (as shown in this example) is not recommended.</span></span> <span data-ttu-id="2b527-224">日付リテラルと #Feb 12、1969 # などの時刻のリテラルを使用し、# 4時 45分: 23 PM #、代わりにします。</span><span class="sxs-lookup"><span data-stu-id="2b527-224">Use date literals and time literals, such as #Feb 12, 1969# and #4:45:23 PM#, instead.</span></span>  
  
 [!code-vb[VbVbalrFunctions#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#5)]  
  
## <a name="cdbl-example"></a><span data-ttu-id="2b527-225">Cdbl 関数の例</span><span class="sxs-lookup"><span data-stu-id="2b527-225">CDbl Example</span></span>  
 [!code-vb[VbVbalrFunctions#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#6)]  
  
## <a name="cdec-example"></a><span data-ttu-id="2b527-226">CDec 例</span><span class="sxs-lookup"><span data-stu-id="2b527-226">CDec Example</span></span>  
 <span data-ttu-id="2b527-227">次の例では、`CDec`関数を数値に変換する`Decimal`します。</span><span class="sxs-lookup"><span data-stu-id="2b527-227">The following example uses the `CDec` function to convert a numeric value to `Decimal`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#7)]  
  
## <a name="cint-example"></a><span data-ttu-id="2b527-228">CInt 例</span><span class="sxs-lookup"><span data-stu-id="2b527-228">CInt Example</span></span>  
 <span data-ttu-id="2b527-229">次の例では、`CInt`値を変換する関数`Integer`します。</span><span class="sxs-lookup"><span data-stu-id="2b527-229">The following example uses the `CInt` function to convert a value to `Integer`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#8)]  

## <a name="clng-example"></a><span data-ttu-id="2b527-230">CLng 例</span><span class="sxs-lookup"><span data-stu-id="2b527-230">CLng Example</span></span>
 <span data-ttu-id="2b527-231">次の例では、`CLng`値に変換する関数`Long`します。</span><span class="sxs-lookup"><span data-stu-id="2b527-231">The following example uses the `CLng` function to convert values to `Long`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#9)]  
  
## <a name="cobj-example"></a><span data-ttu-id="2b527-232">CObj 例</span><span class="sxs-lookup"><span data-stu-id="2b527-232">CObj Example</span></span>  
 <span data-ttu-id="2b527-233">次の例では、`CObj`関数を数値に変換する`Object`します。</span><span class="sxs-lookup"><span data-stu-id="2b527-233">The following example uses the `CObj` function to convert a numeric value to `Object`.</span></span> <span data-ttu-id="2b527-234">`Object`変数自体を指す 4 バイト ポインターのみが含まれています、`Double`に割り当てられた値。</span><span class="sxs-lookup"><span data-stu-id="2b527-234">The `Object` variable itself contains only a four-byte pointer, which points to the `Double` value assigned to it.</span></span>  
  
 [!code-vb[VbVbalrFunctions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#10)]  
  
## <a name="csbyte-example"></a><span data-ttu-id="2b527-235">CSByte 例</span><span class="sxs-lookup"><span data-stu-id="2b527-235">CSByte Example</span></span>  
 <span data-ttu-id="2b527-236">次の例では、`CSByte`関数を数値に変換する`SByte`します。</span><span class="sxs-lookup"><span data-stu-id="2b527-236">The following example uses the `CSByte` function to convert a numeric value to `SByte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#11)]  
  
## <a name="cshort-example"></a><span data-ttu-id="2b527-237">CShort 例</span><span class="sxs-lookup"><span data-stu-id="2b527-237">CShort Example</span></span>  
 <span data-ttu-id="2b527-238">次の例では、`CShort`関数を数値に変換する`Short`します。</span><span class="sxs-lookup"><span data-stu-id="2b527-238">The following example uses the `CShort` function to convert a numeric value to `Short`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#12)]  
  
## <a name="csng-example"></a><span data-ttu-id="2b527-239">CSng 例</span><span class="sxs-lookup"><span data-stu-id="2b527-239">CSng Example</span></span>  
 <span data-ttu-id="2b527-240">次の例では、`CSng`値に変換する関数`Single`します。</span><span class="sxs-lookup"><span data-stu-id="2b527-240">The following example uses the `CSng` function to convert values to `Single`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#13)]  
  
## <a name="cstr-example"></a><span data-ttu-id="2b527-241">Cstr 関数の例</span><span class="sxs-lookup"><span data-stu-id="2b527-241">CStr Example</span></span>  
 <span data-ttu-id="2b527-242">次の例では、`CStr`関数を数値に変換する`String`します。</span><span class="sxs-lookup"><span data-stu-id="2b527-242">The following example uses the `CStr` function to convert a numeric value to `String`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#14)]  
  
 <span data-ttu-id="2b527-243">次の例では、`CStr`関数に変換する`Date`値`String`値。</span><span class="sxs-lookup"><span data-stu-id="2b527-243">The following example uses the `CStr` function to convert `Date` values to `String` values.</span></span>  
  
 [!code-vb[VbVbalrFunctions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#15)]  
  
 <span data-ttu-id="2b527-244">`CStr` 常に表示します、`Date`の現在のロケールの標準の短い形式で値"2003 年 6 月 15 4時 35分: 47 PM"です。</span><span class="sxs-lookup"><span data-stu-id="2b527-244">`CStr` always renders a `Date` value in the standard short format for the current locale, for example, "6/15/2003 4:35:47 PM".</span></span> <span data-ttu-id="2b527-245">ただし、`CStr`抑制、*ニュートラル値*1/1/0001 から、日付と時刻の 00時 00分: 00 の。</span><span class="sxs-lookup"><span data-stu-id="2b527-245">However, `CStr` suppresses the *neutral values* of 1/1/0001 for the date and 00:00:00 for the time.</span></span>  
  
 <span data-ttu-id="2b527-246">によって返される値の詳細については`CStr`を参照してください[CStr 関数の戻り値](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md)します。</span><span class="sxs-lookup"><span data-stu-id="2b527-246">For more detail on the values returned by `CStr`, see [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>  
  
## <a name="cuint-example"></a><span data-ttu-id="2b527-247">CUInt 例</span><span class="sxs-lookup"><span data-stu-id="2b527-247">CUInt Example</span></span>  
 <span data-ttu-id="2b527-248">次の例では、`CUInt`関数を数値に変換する`UInteger`します。</span><span class="sxs-lookup"><span data-stu-id="2b527-248">The following example uses the `CUInt` function to convert a numeric value to `UInteger`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#16)]  
  
## <a name="culng-example"></a><span data-ttu-id="2b527-249">CULng 例</span><span class="sxs-lookup"><span data-stu-id="2b527-249">CULng Example</span></span>  
 <span data-ttu-id="2b527-250">次の例では、`CULng`関数を数値に変換する`ULong`します。</span><span class="sxs-lookup"><span data-stu-id="2b527-250">The following example uses the `CULng` function to convert a numeric value to `ULong`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#17)]  
  
## <a name="cushort-example"></a><span data-ttu-id="2b527-251">CUShort 例</span><span class="sxs-lookup"><span data-stu-id="2b527-251">CUShort Example</span></span>  
 <span data-ttu-id="2b527-252">次の例では、`CUShort`関数を数値に変換する`UShort`します。</span><span class="sxs-lookup"><span data-stu-id="2b527-252">The following example uses the `CUShort` function to convert a numeric value to `UShort`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#18)]  
  
## <a name="see-also"></a><span data-ttu-id="2b527-253">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b527-253">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- <xref:Microsoft.VisualBasic.Strings.Format%2A>
- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:Microsoft.VisualBasic.Conversion.Oct%2A>
- <xref:Microsoft.VisualBasic.Conversion.Str%2A>
- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="2b527-254">変換関数</span><span class="sxs-lookup"><span data-stu-id="2b527-254">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [<span data-ttu-id="2b527-255">Visual Basic における型変換</span><span class="sxs-lookup"><span data-stu-id="2b527-255">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
