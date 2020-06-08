---
title: CString
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
ms.openlocfilehash: 5c0cfae01da02222d0827e81ec1ed35ce353ead1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415376"
---
# <a name="type-conversion-functions-visual-basic"></a><span data-ttu-id="cdd64-102">データ型変換関数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cdd64-102">Type Conversion Functions (Visual Basic)</span></span>

<span data-ttu-id="cdd64-103">これらの関数は、インラインでコンパイルされます。つまり、変換コードは、式を評価するコードに含まれます。</span><span class="sxs-lookup"><span data-stu-id="cdd64-103">These functions are compiled inline, meaning the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="cdd64-104">変換を実行するためのプロシージャの呼び出しがないことがありますが、これにより、パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="cdd64-104">Sometimes there is no call to a procedure to accomplish the conversion, which improves performance.</span></span> <span data-ttu-id="cdd64-105">各関数では、式を特定のデータ型に強制的に変換します。</span><span class="sxs-lookup"><span data-stu-id="cdd64-105">Each function coerces an expression to a specific data type.</span></span>

## <a name="syntax"></a><span data-ttu-id="cdd64-106">構文</span><span class="sxs-lookup"><span data-stu-id="cdd64-106">Syntax</span></span>

```vb
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

## <a name="part"></a><span data-ttu-id="cdd64-107">パーツ</span><span class="sxs-lookup"><span data-stu-id="cdd64-107">Part</span></span>

`expression`  
<span data-ttu-id="cdd64-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="cdd64-108">Required.</span></span> <span data-ttu-id="cdd64-109">ソース データ型の任意の式。</span><span class="sxs-lookup"><span data-stu-id="cdd64-109">Any expression of the source data type.</span></span>

## <a name="return-value-data-type"></a><span data-ttu-id="cdd64-110">戻り値のデータ型</span><span class="sxs-lookup"><span data-stu-id="cdd64-110">Return Value Data Type</span></span>

<span data-ttu-id="cdd64-111">次の表に示すように、関数名によって、それが返す値のデータ型が決まります。</span><span class="sxs-lookup"><span data-stu-id="cdd64-111">The function name determines the data type of the value it returns, as shown in the following table.</span></span>

|<span data-ttu-id="cdd64-112">関数名</span><span class="sxs-lookup"><span data-stu-id="cdd64-112">Function name</span></span>|<span data-ttu-id="cdd64-113">戻り値のデータ型</span><span class="sxs-lookup"><span data-stu-id="cdd64-113">Return data type</span></span>|<span data-ttu-id="cdd64-114">`expression` 引数の範囲</span><span class="sxs-lookup"><span data-stu-id="cdd64-114">Range for `expression` argument</span></span>|
|-------------------|----------------------|-------------------------------------|
|`CBool`|[<span data-ttu-id="cdd64-115">Boolean データ型</span><span class="sxs-lookup"><span data-stu-id="cdd64-115">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)|<span data-ttu-id="cdd64-116">任意の有効な `Char` または `String` または数値式。</span><span class="sxs-lookup"><span data-stu-id="cdd64-116">Any valid `Char` or `String` or numeric expression.</span></span>|
|`CByte`|[<span data-ttu-id="cdd64-117">Byte データ型</span><span class="sxs-lookup"><span data-stu-id="cdd64-117">Byte Data Type</span></span>](../data-types/byte-data-type.md)|<span data-ttu-id="cdd64-118"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) から <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (符号なし)。小数部は丸められます。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cdd64-118"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) through <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="cdd64-119">Visual Basic 15.8 以降、Visual Basic では、`CByte` 関数による浮動小数点からバイトへの変換のパフォーマンスが最適化されます。詳細については、「[解説](#remarks)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd64-119">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to byte conversion with the `CByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="cdd64-120">例については、「[CInt の例](#cint-example)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd64-120">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CChar`|[<span data-ttu-id="cdd64-121">Char データ型</span><span class="sxs-lookup"><span data-stu-id="cdd64-121">Char Data Type</span></span>](../data-types/char-data-type.md)|<span data-ttu-id="cdd64-122">任意の有効な `Char` または `String` 式。`String` の最初の文字のみが変換されます。値には 0 から 65535 (符号なし) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="cdd64-122">Any valid `Char` or `String` expression; only first character of a `String` is converted; value can be 0 through 65535 (unsigned).</span></span>|
|`CDate`|[<span data-ttu-id="cdd64-123">Date データ型</span><span class="sxs-lookup"><span data-stu-id="cdd64-123">Date Data Type</span></span>](../data-types/date-data-type.md)|<span data-ttu-id="cdd64-124">日付と時刻の任意の有効な表現。</span><span class="sxs-lookup"><span data-stu-id="cdd64-124">Any valid representation of a date and time.</span></span>|
|`CDbl`|[<span data-ttu-id="cdd64-125">Double 型</span><span class="sxs-lookup"><span data-stu-id="cdd64-125">Double Data Type</span></span>](../data-types/double-data-type.md)|<span data-ttu-id="cdd64-126">負の値の場合は -1.79769313486231570E+308 から -4.94065645841246544E-324 for negative values。正の値の場合は 4.94065645841246544E-324 から 1.79769313486231570E+308。</span><span class="sxs-lookup"><span data-stu-id="cdd64-126">-1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values; 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span>|
|`CDec`|[<span data-ttu-id="cdd64-127">Decimal データ型</span><span class="sxs-lookup"><span data-stu-id="cdd64-127">Decimal Data Type</span></span>](../data-types/decimal-data-type.md)|<span data-ttu-id="cdd64-128">ゼロスケールの数値 (つまり、小数点以下を含まない数値) の場合は +/-79,228,162,514,264,337,593,543,950,335。</span><span class="sxs-lookup"><span data-stu-id="cdd64-128">+/-79,228,162,514,264,337,593,543,950,335 for zero-scaled numbers, that is, numbers with no decimal places.</span></span> <span data-ttu-id="cdd64-129">小数点以下 28 桁の数値の場合の範囲は +/-7.9228162514264337593543950335 です。</span><span class="sxs-lookup"><span data-stu-id="cdd64-129">For numbers with 28 decimal places, the range is +/-7.9228162514264337593543950335.</span></span> <span data-ttu-id="cdd64-130">0 以外の最小値は 0.0000000000000000000000000001 (+/-1E-28) です。</span><span class="sxs-lookup"><span data-stu-id="cdd64-130">The smallest possible non-zero number is 0.0000000000000000000000000001 (+/-1E-28).</span></span>|
|`CInt`|[<span data-ttu-id="cdd64-131">Integer データ型</span><span class="sxs-lookup"><span data-stu-id="cdd64-131">Integer Data Type</span></span>](../data-types/integer-data-type.md)|<span data-ttu-id="cdd64-132"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2147483648) から <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2147483647)。小数部は丸められます。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cdd64-132"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2,147,483,648) through <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2,147,483,647); fractional parts are rounded.<sup>1</sup></span></span> <br/><br/><span data-ttu-id="cdd64-133">Visual Basic 15.8 以降、Visual Basic では、`CInt` 関数による浮動小数点から整数への変換のパフォーマンスが最適化されます。詳細については、「[解説](#remarks)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd64-133">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to integer conversion with the `CInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="cdd64-134">例については、「[CInt の例](#cint-example)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd64-134">See the [CInt Example](#cint-example) section for an example.</span></span> |
|`CLng`|[<span data-ttu-id="cdd64-135">Long データ型</span><span class="sxs-lookup"><span data-stu-id="cdd64-135">Long Data Type</span></span>](../data-types/long-data-type.md)|<span data-ttu-id="cdd64-136"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9,223,372,036,854,775,808) から <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9,223,372,036,854,775,807)。小数部は丸められます。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cdd64-136"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9,223,372,036,854,775,808) through <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9,223,372,036,854,775,807); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="cdd64-137">Visual Basic 15.8 以降、Visual Basic では、`CLng` 関数による浮動小数点から 64 ビット整数への変換のパフォーマンスが最適化されます。詳細については、「[解説](#remarks)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd64-137">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 64-bit integer conversion with the `CLng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="cdd64-138">例については、「[CInt の例](#cint-example)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd64-138">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CObj`|[<span data-ttu-id="cdd64-139">Object 型</span><span class="sxs-lookup"><span data-stu-id="cdd64-139">Object Data Type</span></span>](../data-types/object-data-type.md)|<span data-ttu-id="cdd64-140">任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="cdd64-140">Any valid expression.</span></span>|
|`CSByte`|[<span data-ttu-id="cdd64-141">SByte データ型</span><span class="sxs-lookup"><span data-stu-id="cdd64-141">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)|<span data-ttu-id="cdd64-142"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) から <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127)。小数部は丸められます。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cdd64-142"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) through <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="cdd64-143">Visual Basic 15.8 以降、Visual Basic では、`CSByte` 関数による浮動小数点から符号付きバイトへの変換のパフォーマンスが最適化されます。詳細については、「[解説](#remarks)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd64-143">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to signed byte conversion with the `CSByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="cdd64-144">例については、「[CInt の例](#cint-example)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd64-144">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CShort`|[<span data-ttu-id="cdd64-145">Short データ型</span><span class="sxs-lookup"><span data-stu-id="cdd64-145">Short Data Type</span></span>](../data-types/short-data-type.md)|<span data-ttu-id="cdd64-146"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32,768) から <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32,767)。小数部は丸められます。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cdd64-146"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32,768) through <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32,767); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="cdd64-147">Visual Basic 15.8 以降、Visual Basic では、`CShort` 関数による浮動小数点から 16 ビット整数への変換のパフォーマンスが最適化されます。詳細については、「[解説](#remarks)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd64-147">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 16-bit integer conversion with the `CShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="cdd64-148">例については、「[CInt の例](#cint-example)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd64-148">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CSng`|[<span data-ttu-id="cdd64-149">Single データ型</span><span class="sxs-lookup"><span data-stu-id="cdd64-149">Single Data Type</span></span>](../data-types/single-data-type.md)|<span data-ttu-id="cdd64-150">負の値の場合は、-3.402823E+38 から -1.401298E-45。正の値の場合は、1.401298E-45 から 3.402823E+38。</span><span class="sxs-lookup"><span data-stu-id="cdd64-150">-3.402823E+38 through -1.401298E-45 for negative values; 1.401298E-45 through 3.402823E+38 for positive values.</span></span>|
|`CStr`|[<span data-ttu-id="cdd64-151">String データ型</span><span class="sxs-lookup"><span data-stu-id="cdd64-151">String Data Type</span></span>](../data-types/string-data-type.md)|<span data-ttu-id="cdd64-152">`CStr` の戻り値は、`expression` 引数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="cdd64-152">Returns for `CStr` depend on the `expression` argument.</span></span> <span data-ttu-id="cdd64-153">「[CStr 関数の戻り値](return-values-for-the-cstr-function.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd64-153">See [Return Values for the CStr Function](return-values-for-the-cstr-function.md).</span></span>|
|`CUInt`|[<span data-ttu-id="cdd64-154">UInteger データ型</span><span class="sxs-lookup"><span data-stu-id="cdd64-154">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)|<span data-ttu-id="cdd64-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) から <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4,294,967,295)。小数部は丸められます。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cdd64-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4,294,967,295) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="cdd64-156">Visual Basic 15.8 以降、Visual Basic では、`CUInt` 関数による浮動小数点から符号なし整数への変換のパフォーマンスが最適化されます。詳細については、「[解説](#remarks)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd64-156">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned integer conversion with the `CUInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="cdd64-157">例については、「[CInt の例](#cint-example)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd64-157">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CULng`|[<span data-ttu-id="cdd64-158">ULong データ型</span><span class="sxs-lookup"><span data-stu-id="cdd64-158">ULong Data Type</span></span>](../data-types/ulong-data-type.md)|<span data-ttu-id="cdd64-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) から <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18,446,744,073,709,551,615)。小数部は丸められます。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cdd64-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18,446,744,073,709,551,615) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="cdd64-160">Visual Basic 15.8 以降、Visual Basic では、`CULng` 関数による浮動小数点から符号なし長整数への変換のパフォーマンスが最適化されます。詳細については、「[解説](#remarks)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd64-160">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned long integer conversion with the `CULng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="cdd64-161">例については、「[CInt の例](#cint-example)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd64-161">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CUShort`|[<span data-ttu-id="cdd64-162">UShort データ型</span><span class="sxs-lookup"><span data-stu-id="cdd64-162">UShort Data Type</span></span>](../data-types/ushort-data-type.md)|<span data-ttu-id="cdd64-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) から <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65,535) (符号なし)。小数部は丸められます。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cdd64-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65,535) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="cdd64-164">Visual Basic 15.8 以降、Visual Basic では、`CUShort` 関数による浮動小数点から符号なし 16 ビット整数への変換のパフォーマンスが最適化されます。詳細については、「[解説](#remarks)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd64-164">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned 16-bit integer conversion with the `CUShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="cdd64-165">例については、「[CInt の例](#cint-example)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd64-165">See the [CInt Example](#cint-example) section for an example.</span></span>|

<span data-ttu-id="cdd64-166"><sup>1</sup> 小数部は、*銀行型丸め*と呼ばれる特殊な種類の丸めの対象となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cdd64-166"><sup>1</sup> Fractional parts can be subject to a special type of rounding called *banker's rounding*.</span></span> <span data-ttu-id="cdd64-167">詳細については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd64-167">See "Remarks" for more information.</span></span>

## <a name="remarks"></a><span data-ttu-id="cdd64-168">Remarks</span><span class="sxs-lookup"><span data-stu-id="cdd64-168">Remarks</span></span>

<span data-ttu-id="cdd64-169">原則として、<xref:System.Convert> クラスで、または個々の型の構造体またはクラスで、`ToString()` などの .NET Framework メソッドに優先して、Visual Basic の型変換関数を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdd64-169">As a rule, you should use the Visual Basic type conversion functions in preference to the .NET Framework methods such as `ToString()`, either on the <xref:System.Convert> class or on an individual type structure or class.</span></span> <span data-ttu-id="cdd64-170">Visual Basic 関数は、Visual Basic コードとの最適な相互作用のために設計されており、さらにそれらによって、ソースコードが短くなり、読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="cdd64-170">The Visual Basic functions are designed for optimal interaction with Visual Basic code, and they also make your source code shorter and easier to read.</span></span> <span data-ttu-id="cdd64-171">また、.NET Framework 変換メソッドでは、常に Visual Basic 関数と同じ結果が生成されるとは限りません。たとえば、`Boolean` を `Integer` に変換する場合などです。</span><span class="sxs-lookup"><span data-stu-id="cdd64-171">In addition, the .NET Framework conversion methods do not always produce the same results as the Visual Basic functions, for example when converting `Boolean` to `Integer`.</span></span> <span data-ttu-id="cdd64-172">詳細については、「[データ型のトラブルシューティング](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd64-172">For more information, see [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

<span data-ttu-id="cdd64-173">Visual Basic 15.8 以降、次のメソッドによって返される <xref:System.Single> または <xref:System.Double> 値を、整数変換関数 (`CByte`、`CShort`、`CInt`、`CLng`、`CSByte`、`CUShort`、`CUInt`、`CULng`) のいずれかに渡す場合に、浮動小数点から整数への変換のパフォーマンスが最適化されます。</span><span class="sxs-lookup"><span data-stu-id="cdd64-173">Starting with Visual Basic 15.8, the performance of floating-point-to-integer conversion is optimized when you pass the <xref:System.Single> or <xref:System.Double> value returned by the following methods to one of the integer conversion functions (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span></span>

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

<span data-ttu-id="cdd64-174">この最適化によって、大量の整数変換を行うコードで、実行が最大 2 倍速くなります。</span><span class="sxs-lookup"><span data-stu-id="cdd64-174">This optimization allows code that does a large number of integer conversions to run up to twice as fast.</span></span> <span data-ttu-id="cdd64-175">次の例では、それらの最適化された浮動小数点から整数への変換を示しています。</span><span class="sxs-lookup"><span data-stu-id="cdd64-175">The following example illustrates these optimized floating-point-to-integer conversions:</span></span>

```vb
Dim s As Single = 173.7619
Dim d As Double = s

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

## <a name="behavior"></a><span data-ttu-id="cdd64-176">動作</span><span class="sxs-lookup"><span data-stu-id="cdd64-176">Behavior</span></span>

- <span data-ttu-id="cdd64-177">**強制型変換。**</span><span class="sxs-lookup"><span data-stu-id="cdd64-177">**Coercion.**</span></span> <span data-ttu-id="cdd64-178">一般に、データ型変換関数を使用すると、操作の結果を、既定のデータ型ではなく、特定のデータ型に強制的に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="cdd64-178">In general, you can use the data type conversion functions to coerce the result of an operation to a particular data type rather than the default data type.</span></span> <span data-ttu-id="cdd64-179">たとえば、単精度、倍精度、または整数の算術演算が通常行われるところで、`CDec` を使用して、10 進数の算術演算を強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="cdd64-179">For example, use `CDec` to force decimal arithmetic in cases where single-precision, double-precision, or integer arithmetic would normally take place.</span></span>

- <span data-ttu-id="cdd64-180">**変換の失敗。**</span><span class="sxs-lookup"><span data-stu-id="cdd64-180">**Failed Conversions.**</span></span> <span data-ttu-id="cdd64-181">関数に渡された `expression` が、変換先のデータ型の範囲外である場合、<xref:System.OverflowException> が発生します。</span><span class="sxs-lookup"><span data-stu-id="cdd64-181">If the `expression` passed to the function is outside the range of the data type to which it is to be converted, an <xref:System.OverflowException> occurs.</span></span>

- <span data-ttu-id="cdd64-182">**小数部。**</span><span class="sxs-lookup"><span data-stu-id="cdd64-182">**Fractional Parts.**</span></span> <span data-ttu-id="cdd64-183">非整数値を整数型に変換する場合、整数変換関数 (`CByte`、`CInt`、`CLng`、`CSByte`、`CShort`、`CUInt`、`CULng`、および `CUShort`) で、小数部を削除し、値を最も近い整数に丸めます。</span><span class="sxs-lookup"><span data-stu-id="cdd64-183">When you convert a nonintegral value to an integral type, the integer conversion functions (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, and `CUShort`) remove the fractional part and round the value to the closest integer.</span></span>

     <span data-ttu-id="cdd64-184">小数部がちょうど 0.5 の場合、整数変換関数では、最も近い偶数の整数に丸められます。</span><span class="sxs-lookup"><span data-stu-id="cdd64-184">If the fractional part is exactly 0.5, the integer conversion functions round it to the nearest even integer.</span></span> <span data-ttu-id="cdd64-185">たとえば、0.5 は 0 に丸められ、1.5 と 2.5 は両方とも 2 に丸められます。</span><span class="sxs-lookup"><span data-stu-id="cdd64-185">For example, 0.5 rounds to 0, and 1.5 and 2.5 both round to 2.</span></span> <span data-ttu-id="cdd64-186">これは、*銀行型丸め*と呼ばれることもあり、その目的は、そのような多数の数値を加算するときに累積する可能性があるバイアスを補正することです。</span><span class="sxs-lookup"><span data-stu-id="cdd64-186">This is sometimes called *banker's rounding*, and its purpose is to compensate for a bias that could accumulate when adding many such numbers together.</span></span>

     <span data-ttu-id="cdd64-187">`CInt` と `CLng` は、<xref:Microsoft.VisualBasic.Conversion.Int%2A> 関数や <xref:Microsoft.VisualBasic.Conversion.Fix%2A> 関数とは異なり、数値の小数部を丸めるのではなく、切り捨てます。</span><span class="sxs-lookup"><span data-stu-id="cdd64-187">`CInt` and `CLng` differ from the <xref:Microsoft.VisualBasic.Conversion.Int%2A> and <xref:Microsoft.VisualBasic.Conversion.Fix%2A> functions, which truncate, rather than round, the fractional part of a number.</span></span> <span data-ttu-id="cdd64-188">さらに、`Fix` と `Int` は常に、渡された同じデータ型の値を返します。</span><span class="sxs-lookup"><span data-stu-id="cdd64-188">Also, `Fix` and `Int` always return a value of the same data type as you pass in.</span></span>

- <span data-ttu-id="cdd64-189">**日付/時刻の変換。**</span><span class="sxs-lookup"><span data-stu-id="cdd64-189">**Date/Time Conversions.**</span></span> <span data-ttu-id="cdd64-190"><xref:Microsoft.VisualBasic.Information.IsDate%2A> 関数を使用して、値を日付と時刻に変換できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="cdd64-190">Use the <xref:Microsoft.VisualBasic.Information.IsDate%2A> function to determine if a value can be converted to a date and time.</span></span> <span data-ttu-id="cdd64-191">`CDate` は、日付リテラルと時刻リテラルを認識しますが、数値は認識しません。</span><span class="sxs-lookup"><span data-stu-id="cdd64-191">`CDate` recognizes date literals and time literals but not numeric values.</span></span> <span data-ttu-id="cdd64-192">Visual Basic 6.0 の `Date` 値を Visual Basic 2005 以降のバージョンの `Date` 値に変換するには、<xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cdd64-192">To convert a Visual Basic 6.0 `Date` value to a `Date` value in Visual Basic 2005 or later versions, you can use the <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> method.</span></span>

- <span data-ttu-id="cdd64-193">**ニュートラル日付/時刻値。**</span><span class="sxs-lookup"><span data-stu-id="cdd64-193">**Neutral Date/Time Values.**</span></span> <span data-ttu-id="cdd64-194">[Date データ型](../data-types/date-data-type.md)には、常に日付と時刻の両方の情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="cdd64-194">The [Date Data Type](../data-types/date-data-type.md) always contains both date and time information.</span></span> <span data-ttu-id="cdd64-195">型変換の目的で、Visual Basic では、1/1/0001 (1 年の 1 月 1 日) を日付の*ニュートラル値*、00:00:00 (午前 0 時) を時刻のニュートラル値と見なします。</span><span class="sxs-lookup"><span data-stu-id="cdd64-195">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="cdd64-196">`Date` 値を文字列に変換する場合、`CStr` では、結果の文字列にニュートラル値が含まれません。</span><span class="sxs-lookup"><span data-stu-id="cdd64-196">If you convert a `Date` value to a string, `CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="cdd64-197">たとえば、`#January 1, 0001 9:30:00#` を文字列に変換した場合、結果は "9:30:00 AM" になります。日付情報は含まれません。</span><span class="sxs-lookup"><span data-stu-id="cdd64-197">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="cdd64-198">ただし、日付情報は元の `Date` 値には引き続き存在しているため、<xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> 関数などの関数を使用して回復できます。</span><span class="sxs-lookup"><span data-stu-id="cdd64-198">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span></span>

- <span data-ttu-id="cdd64-199">**カルチャの感度。**</span><span class="sxs-lookup"><span data-stu-id="cdd64-199">**Culture Sensitivity.**</span></span> <span data-ttu-id="cdd64-200">文字列に関連する型変換関数では、アプリケーションの現在のカルチャ設定に基づいて変換が実行されます。</span><span class="sxs-lookup"><span data-stu-id="cdd64-200">The type conversion functions involving strings perform conversions based on the current culture settings for the application.</span></span> <span data-ttu-id="cdd64-201">たとえば、`CDate` では、システムのロケール設定に従って日付形式が認識されます。</span><span class="sxs-lookup"><span data-stu-id="cdd64-201">For example, `CDate` recognizes date formats according to the locale setting of your system.</span></span> <span data-ttu-id="cdd64-202">ロケールの正しい順序で日、月、年を指定する必要があります。そうしないと、日付が正しく解釈されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="cdd64-202">You must provide the day, month, and year in the correct order for your locale, or the date might not be interpreted correctly.</span></span> <span data-ttu-id="cdd64-203">"Wednesday" など、曜日の文字列が含まれている場合、長い日付形式は認識されません。</span><span class="sxs-lookup"><span data-stu-id="cdd64-203">A long date format is not recognized if it contains a day-of-the-week string, such as "Wednesday".</span></span>

     <span data-ttu-id="cdd64-204">ロケールによって指定された形式以外の形式で、値の文字列表現の変換を行う必要がある場合は、Visual Basic 型変換関数を使用できません。</span><span class="sxs-lookup"><span data-stu-id="cdd64-204">If you need to convert to or from a string representation of a value in a format other than the one specified by your locale, you cannot use the Visual Basic type conversion functions.</span></span> <span data-ttu-id="cdd64-205">これを行うには、その値の型の `ToString(IFormatProvider)` および `Parse(String, IFormatProvider)` メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="cdd64-205">To do this, use the `ToString(IFormatProvider)` and `Parse(String, IFormatProvider)` methods of that value's type.</span></span> <span data-ttu-id="cdd64-206">たとえば、文字列を `Double` に変換する場合は <xref:System.Double.Parse%2A?displayProperty=nameWithType> を使用し、`Double` 型の値を文字列に変換する場合は <xref:System.Double.ToString%2A?displayProperty=nameWithType> を使用します。</span><span class="sxs-lookup"><span data-stu-id="cdd64-206">For example, use <xref:System.Double.Parse%2A?displayProperty=nameWithType> when converting a string to a `Double`, and use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a string.</span></span>

## <a name="ctype-function"></a><span data-ttu-id="cdd64-207">CType Function</span><span class="sxs-lookup"><span data-stu-id="cdd64-207">CType Function</span></span>

<span data-ttu-id="cdd64-208">[CType 関数](ctype-function.md)は、2 つ目の引数 `typename` を受け取り、`expression` を `typename` に強制的に変換します。ここで `typename` は、それに対して有効な変換が存在する任意のデータ型、構造体、クラス、またはインターフェイスなどです。</span><span class="sxs-lookup"><span data-stu-id="cdd64-208">The [CType Function](ctype-function.md) takes a second argument, `typename`, and coerces `expression` to `typename`, where `typename` can be any data type, structure, class, or interface to which there exists a valid conversion.</span></span>

<span data-ttu-id="cdd64-209">`CType` と他の型変換キーワードとの比較については、「[DirectCast 演算子](../operators/directcast-operator.md)」と「[TryCast 演算子](../operators/trycast-operator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd64-209">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../operators/directcast-operator.md) and [TryCast Operator](../operators/trycast-operator.md).</span></span>

## <a name="cbool-example"></a><span data-ttu-id="cdd64-210">CBool の例</span><span class="sxs-lookup"><span data-stu-id="cdd64-210">CBool Example</span></span>

<span data-ttu-id="cdd64-211">次の例では、`CBool` 関数を使用して、式を `Boolean` 値に変換しています。</span><span class="sxs-lookup"><span data-stu-id="cdd64-211">The following example uses the `CBool` function to convert expressions to `Boolean` values.</span></span> <span data-ttu-id="cdd64-212">式が 0 以外の値に評価される場合、`CBool` では `True` が返されます。それ以外の場合は `False` が返されます。</span><span class="sxs-lookup"><span data-stu-id="cdd64-212">If an expression evaluates to a nonzero value, `CBool` returns `True`; otherwise, it returns `False`.</span></span>

[!code-vb[VbVbalrFunctions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#1)]

## <a name="cbyte-example"></a><span data-ttu-id="cdd64-213">CByte の例</span><span class="sxs-lookup"><span data-stu-id="cdd64-213">CByte Example</span></span>

<span data-ttu-id="cdd64-214">次の例では、`CByte` 関数を使用して、式を `Byte` に変換しています。</span><span class="sxs-lookup"><span data-stu-id="cdd64-214">The following example uses the `CByte` function to convert an expression to a `Byte`.</span></span>

[!code-vb[VbVbalrFunctions#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#2)]

## <a name="cchar-example"></a><span data-ttu-id="cdd64-215">CChar の例</span><span class="sxs-lookup"><span data-stu-id="cdd64-215">CChar Example</span></span>

<span data-ttu-id="cdd64-216">次の例では、`CChar` 関数を使用して、`String` 式の最初の文字を `Char` 型に変換しています。</span><span class="sxs-lookup"><span data-stu-id="cdd64-216">The following example uses the `CChar` function to convert the first character of a `String` expression to a `Char` type.</span></span>

[!code-vb[VbVbalrFunctions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#3)]

<span data-ttu-id="cdd64-217">`CChar` の入力引数は、`Char` または `String` データ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdd64-217">The input argument to `CChar` must be of data type `Char` or `String`.</span></span> <span data-ttu-id="cdd64-218">`CChar` を使用して数値を文字に変換することはできません。これは `CChar` では数値データ型を受け入れないためです。</span><span class="sxs-lookup"><span data-stu-id="cdd64-218">You cannot use `CChar` to convert a number to a character, because `CChar` cannot accept a numeric data type.</span></span> <span data-ttu-id="cdd64-219">次の例では、コード ポイント (文字コード) を表す数値を取得し、それを対応する文字に変換しています。</span><span class="sxs-lookup"><span data-stu-id="cdd64-219">The following example obtains a number representing a code point (character code) and converts it to the corresponding character.</span></span> <span data-ttu-id="cdd64-220"><xref:Microsoft.VisualBasic.Interaction.InputBox%2A> 関数を使用して、数字の文字列を取得し、`CInt` を使用して、文字列を `Integer` 型に変換し、`ChrW` を使用して、数値を `Char` 型に変換しています。</span><span class="sxs-lookup"><span data-stu-id="cdd64-220">It uses the <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> function to obtain the string of digits, `CInt` to convert the string to type `Integer`, and `ChrW` to convert the number to type `Char`.</span></span>

[!code-vb[VbVbalrFunctions#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#4)]

## <a name="cdate-example"></a><span data-ttu-id="cdd64-221">CDate の例</span><span class="sxs-lookup"><span data-stu-id="cdd64-221">CDate Example</span></span>

<span data-ttu-id="cdd64-222">次の例では、`CDate` 関数を使用して、文字列を `Date` 値に変換しています。</span><span class="sxs-lookup"><span data-stu-id="cdd64-222">The following example uses the `CDate` function to convert strings to `Date` values.</span></span> <span data-ttu-id="cdd64-223">一般に、日付と時刻を文字列としてハードコーディングする (この例に示すように) ことは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="cdd64-223">In general, hard-coding dates and times as strings (as shown in this example) is not recommended.</span></span> <span data-ttu-id="cdd64-224">代わりに、#Feb 12、1969#、#4:45:23 PM# などの日付リテラルと時刻リテラルを使用します。</span><span class="sxs-lookup"><span data-stu-id="cdd64-224">Use date literals and time literals, such as #Feb 12, 1969# and #4:45:23 PM#, instead.</span></span>

[!code-vb[VbVbalrFunctions#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#5)]

## <a name="cdbl-example"></a><span data-ttu-id="cdd64-225">CDbl の例</span><span class="sxs-lookup"><span data-stu-id="cdd64-225">CDbl Example</span></span>

[!code-vb[VbVbalrFunctions#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#6)]

## <a name="cdec-example"></a><span data-ttu-id="cdd64-226">CDec の例</span><span class="sxs-lookup"><span data-stu-id="cdd64-226">CDec Example</span></span>

<span data-ttu-id="cdd64-227">次の例では、`CDec` 関数を使用して、数値を `Decimal` に変換しています。</span><span class="sxs-lookup"><span data-stu-id="cdd64-227">The following example uses the `CDec` function to convert a numeric value to `Decimal`.</span></span>

[!code-vb[VbVbalrFunctions#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#7)]

## <a name="cint-example"></a><span data-ttu-id="cdd64-228">CInt の例</span><span class="sxs-lookup"><span data-stu-id="cdd64-228">CInt Example</span></span>

<span data-ttu-id="cdd64-229">次の例では、`CInt` 関数を使用して、値を `Integer` に変換しています。</span><span class="sxs-lookup"><span data-stu-id="cdd64-229">The following example uses the `CInt` function to convert a value to `Integer`.</span></span>

[!code-vb[VbVbalrFunctions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#8)]

## <a name="clng-example"></a><span data-ttu-id="cdd64-230">CLng の例</span><span class="sxs-lookup"><span data-stu-id="cdd64-230">CLng Example</span></span>

<span data-ttu-id="cdd64-231">次の例では、`CLng` 関数を使用して、値を `Long` に変換しています。</span><span class="sxs-lookup"><span data-stu-id="cdd64-231">The following example uses the `CLng` function to convert values to `Long`.</span></span>

[!code-vb[VbVbalrFunctions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#9)]

## <a name="cobj-example"></a><span data-ttu-id="cdd64-232">CObj の例</span><span class="sxs-lookup"><span data-stu-id="cdd64-232">CObj Example</span></span>

<span data-ttu-id="cdd64-233">次の例では、`CObj` 関数を使用して、数値を `Object` に変換しています。</span><span class="sxs-lookup"><span data-stu-id="cdd64-233">The following example uses the `CObj` function to convert a numeric value to `Object`.</span></span> <span data-ttu-id="cdd64-234">`Object` 変数自体には、それに代入される `Double` 値を指す 4 バイトのポインターのみが格納されます。</span><span class="sxs-lookup"><span data-stu-id="cdd64-234">The `Object` variable itself contains only a four-byte pointer, which points to the `Double` value assigned to it.</span></span>

[!code-vb[VbVbalrFunctions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#10)]

## <a name="csbyte-example"></a><span data-ttu-id="cdd64-235">CSByte の例</span><span class="sxs-lookup"><span data-stu-id="cdd64-235">CSByte Example</span></span>

<span data-ttu-id="cdd64-236">次の例では、`CSByte` 関数を使用して、数値を `SByte` に変換しています。</span><span class="sxs-lookup"><span data-stu-id="cdd64-236">The following example uses the `CSByte` function to convert a numeric value to `SByte`.</span></span>

[!code-vb[VbVbalrFunctions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#11)]

## <a name="cshort-example"></a><span data-ttu-id="cdd64-237">CShort の例</span><span class="sxs-lookup"><span data-stu-id="cdd64-237">CShort Example</span></span>

<span data-ttu-id="cdd64-238">次の例では、`CShort` 関数を使用して、数値を `Short` に変換しています。</span><span class="sxs-lookup"><span data-stu-id="cdd64-238">The following example uses the `CShort` function to convert a numeric value to `Short`.</span></span>

[!code-vb[VbVbalrFunctions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#12)]

## <a name="csng-example"></a><span data-ttu-id="cdd64-239">CSng の例</span><span class="sxs-lookup"><span data-stu-id="cdd64-239">CSng Example</span></span>

<span data-ttu-id="cdd64-240">次の例では、`CSng` 関数を使用して、値を `Single` に変換しています。</span><span class="sxs-lookup"><span data-stu-id="cdd64-240">The following example uses the `CSng` function to convert values to `Single`.</span></span>

[!code-vb[VbVbalrFunctions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#13)]

## <a name="cstr-example"></a><span data-ttu-id="cdd64-241">CStr の例</span><span class="sxs-lookup"><span data-stu-id="cdd64-241">CStr Example</span></span>

<span data-ttu-id="cdd64-242">次の例では、`CStr` 関数を使用して、数値を `String` に変換しています。</span><span class="sxs-lookup"><span data-stu-id="cdd64-242">The following example uses the `CStr` function to convert a numeric value to `String`.</span></span>

[!code-vb[VbVbalrFunctions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#14)]

<span data-ttu-id="cdd64-243">次の例では、`CStr` 関数を使用して、 `Date` 値を `String` 値に変換しています。</span><span class="sxs-lookup"><span data-stu-id="cdd64-243">The following example uses the `CStr` function to convert `Date` values to `String` values.</span></span>

[!code-vb[VbVbalrFunctions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#15)]

<span data-ttu-id="cdd64-244">`CStr` では常に、現在のロケールの標準の短い形式 ("6/15/2003 4:35:47 PM" など) で `Date` 値がレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="cdd64-244">`CStr` always renders a `Date` value in the standard short format for the current locale, for example, "6/15/2003 4:35:47 PM".</span></span> <span data-ttu-id="cdd64-245">ただし `CStr` では、日付の 1/1/0001 と時刻の 00:00:00 の*ニュートラル値*が含まれません。</span><span class="sxs-lookup"><span data-stu-id="cdd64-245">However, `CStr` suppresses the *neutral values* of 1/1/0001 for the date and 00:00:00 for the time.</span></span>

<span data-ttu-id="cdd64-246">`CStr` によって返される値の詳細については、「[CStr 関数の戻り値](return-values-for-the-cstr-function.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdd64-246">For more detail on the values returned by `CStr`, see [Return Values for the CStr Function](return-values-for-the-cstr-function.md).</span></span>

## <a name="cuint-example"></a><span data-ttu-id="cdd64-247">CUInt の例</span><span class="sxs-lookup"><span data-stu-id="cdd64-247">CUInt Example</span></span>

<span data-ttu-id="cdd64-248">次の例では、`CUInt` 関数を使用して、数値を `UInteger` に変換しています。</span><span class="sxs-lookup"><span data-stu-id="cdd64-248">The following example uses the `CUInt` function to convert a numeric value to `UInteger`.</span></span>

[!code-vb[VbVbalrFunctions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#16)]

## <a name="culng-example"></a><span data-ttu-id="cdd64-249">CULng の例</span><span class="sxs-lookup"><span data-stu-id="cdd64-249">CULng Example</span></span>

<span data-ttu-id="cdd64-250">次の例では、`CULng` 関数を使用して、数値を `ULong` に変換しています。</span><span class="sxs-lookup"><span data-stu-id="cdd64-250">The following example uses the `CULng` function to convert a numeric value to `ULong`.</span></span>

[!code-vb[VbVbalrFunctions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#17)]

## <a name="cushort-example"></a><span data-ttu-id="cdd64-251">CUShort の例</span><span class="sxs-lookup"><span data-stu-id="cdd64-251">CUShort Example</span></span>

<span data-ttu-id="cdd64-252">次の例では、`CUShort` 関数を使用して、数値を `UShort` に変換しています。</span><span class="sxs-lookup"><span data-stu-id="cdd64-252">The following example uses the `CUShort` function to convert a numeric value to `UShort`.</span></span>

[!code-vb[VbVbalrFunctions#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#18)]

## <a name="see-also"></a><span data-ttu-id="cdd64-253">関連項目</span><span class="sxs-lookup"><span data-stu-id="cdd64-253">See also</span></span>

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
- [<span data-ttu-id="cdd64-254">変換関数</span><span class="sxs-lookup"><span data-stu-id="cdd64-254">Conversion Functions</span></span>](conversion-functions.md)
- [<span data-ttu-id="cdd64-255">Visual Basic における型変換</span><span class="sxs-lookup"><span data-stu-id="cdd64-255">Type Conversions in Visual Basic</span></span>](../../programming-guide/language-features/data-types/type-conversions.md)
