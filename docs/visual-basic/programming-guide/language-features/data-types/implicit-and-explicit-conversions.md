---
title: 暗黙の型変換と明示的な型変換
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [Visual Basic], type
- variables [Visual Basic], changing data type
- casting
- conversions [Visual Basic], data type
- type conversion [Visual Basic], implicit conversions
- CType function [Visual Basic], conversions
- casting, data types
- data type conversion [Visual Basic], explicit
- type conversion [Visual Basic], explicit conversions
- data types [Visual Basic], casting
- conversions [Visual Basic], implicit
- explicit data type conversions [Visual Basic]
- conversions [Visual Basic]
- changing data types [Visual Basic]
- conversions [Visual Basic], explicit
- data type conversion [Visual Basic], implicit
- implicit data type conversions [Visual Basic]
ms.assetid: 77de1659-af8a-492c-967e-e7ef60ccce66
ms.openlocfilehash: b7215933cec89b7023f08e8996a283b39b3a3c83
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346371"
---
# <a name="implicit-and-explicit-conversions-visual-basic"></a><span data-ttu-id="646ae-102">暗黙の型変換と明示的な型変換 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="646ae-102">Implicit and Explicit Conversions (Visual Basic)</span></span>

<span data-ttu-id="646ae-103">暗黙の型*変換*では、ソースコードに特別な構文は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="646ae-103">An *implicit conversion* does not require any special syntax in the source code.</span></span> <span data-ttu-id="646ae-104">次の例では、Visual Basic を `q`に割り当てる前に、`k` の値を単精度浮動小数点値に暗黙的に変換します。</span><span class="sxs-lookup"><span data-stu-id="646ae-104">In the following example, Visual Basic implicitly converts the value of `k` to a single-precision floating-point value before assigning it to `q`.</span></span>

```vb
Dim k As Integer
Dim q As Double
' Integer widens to Double, so you can do this with Option Strict On.
k = 432
q = k
```

<span data-ttu-id="646ae-105">*明示的な変換*では、型変換キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="646ae-105">An *explicit conversion* uses a type conversion keyword.</span></span> <span data-ttu-id="646ae-106">Visual Basic には、かっこ内の式を目的のデータ型に強制的に変換するいくつかのキーワードが用意されています。</span><span class="sxs-lookup"><span data-stu-id="646ae-106">Visual Basic provides several such keywords, which coerce an expression in parentheses to the desired data type.</span></span> <span data-ttu-id="646ae-107">これらのキーワードは関数と同様に機能しますが、コンパイラによってインラインでコードが生成されるため、関数呼び出しの場合よりも実行速度が若干速くなります。</span><span class="sxs-lookup"><span data-stu-id="646ae-107">These keywords act like functions, but the compiler generates the code inline, so execution is slightly faster than with a function call.</span></span>

<span data-ttu-id="646ae-108">前の例の次の拡張機能では、`CInt` キーワードは、`q` の値を `k`に割り当てる前に、整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="646ae-108">In the following extension of the preceding example, the `CInt` keyword converts the value of `q` back to an integer before assigning it to `k`.</span></span>

```vb
' q had been assigned the value 432 from k.
q = Math.Sqrt(q)
k = CInt(q)
' k now has the value 21 (rounded square root of 432).
```

## <a name="conversion-keywords"></a><span data-ttu-id="646ae-109">変換キーワード</span><span class="sxs-lookup"><span data-stu-id="646ae-109">Conversion Keywords</span></span>

<span data-ttu-id="646ae-110">次の表は、使用可能な変換キーワードを示しています。</span><span class="sxs-lookup"><span data-stu-id="646ae-110">The following table shows the available conversion keywords.</span></span>

|<span data-ttu-id="646ae-111">型変換キーワード</span><span class="sxs-lookup"><span data-stu-id="646ae-111">Type conversion keyword</span></span>|<span data-ttu-id="646ae-112">式をデータ型に変換します。</span><span class="sxs-lookup"><span data-stu-id="646ae-112">Converts an expression to data type</span></span>|<span data-ttu-id="646ae-113">変換する式の許容データ型</span><span class="sxs-lookup"><span data-stu-id="646ae-113">Allowable data types of expression to be converted</span></span>|
|---|---|---|
|`CBool`|[<span data-ttu-id="646ae-114">Boolean データ型</span><span class="sxs-lookup"><span data-stu-id="646ae-114">Boolean Data Type</span></span>](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="646ae-115">任意の数値型 (`Byte`、`SByte`、列挙型など)、`String`、`Object`</span><span class="sxs-lookup"><span data-stu-id="646ae-115">Any numeric type (including `Byte`, `SByte`, and enumerated types), `String`, `Object`</span></span>|
|`CByte`|[<span data-ttu-id="646ae-116">Byte データ型</span><span class="sxs-lookup"><span data-stu-id="646ae-116">Byte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="646ae-117">任意の数値型 (`SByte` と列挙型を含む)、`Boolean`、`String`、`Object`</span><span class="sxs-lookup"><span data-stu-id="646ae-117">Any numeric type (including `SByte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CChar`|[<span data-ttu-id="646ae-118">Char データ型</span><span class="sxs-lookup"><span data-stu-id="646ae-118">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="646ae-119">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="646ae-119">`String`, `Object`</span></span>|
|`CDate`|[<span data-ttu-id="646ae-120">Date データ型</span><span class="sxs-lookup"><span data-stu-id="646ae-120">Date Data Type</span></span>](../../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="646ae-121">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="646ae-121">`String`, `Object`</span></span>|
|`CDbl`|[<span data-ttu-id="646ae-122">Double 型</span><span class="sxs-lookup"><span data-stu-id="646ae-122">Double Data Type</span></span>](../../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="646ae-123">任意の数値型 (`Byte`、`SByte`、列挙型など)、`Boolean`、`String`、`Object`</span><span class="sxs-lookup"><span data-stu-id="646ae-123">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CDec`|[<span data-ttu-id="646ae-124">Decimal データ型</span><span class="sxs-lookup"><span data-stu-id="646ae-124">Decimal Data Type</span></span>](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="646ae-125">任意の数値型 (`Byte`、`SByte`、列挙型など)、`Boolean`、`String`、`Object`</span><span class="sxs-lookup"><span data-stu-id="646ae-125">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CInt`|[<span data-ttu-id="646ae-126">Integer データ型</span><span class="sxs-lookup"><span data-stu-id="646ae-126">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="646ae-127">任意の数値型 (`Byte`、`SByte`、列挙型など)、`Boolean`、`String`、`Object`</span><span class="sxs-lookup"><span data-stu-id="646ae-127">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CLng`|[<span data-ttu-id="646ae-128">Long データ型</span><span class="sxs-lookup"><span data-stu-id="646ae-128">Long Data Type</span></span>](../../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="646ae-129">任意の数値型 (`Byte`、`SByte`、列挙型など)、`Boolean`、`String`、`Object`</span><span class="sxs-lookup"><span data-stu-id="646ae-129">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CObj`|[<span data-ttu-id="646ae-130">Object データ型</span><span class="sxs-lookup"><span data-stu-id="646ae-130">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="646ae-131">任意の型</span><span class="sxs-lookup"><span data-stu-id="646ae-131">Any type</span></span>|
|`CSByte`|[<span data-ttu-id="646ae-132">SByte データ型</span><span class="sxs-lookup"><span data-stu-id="646ae-132">SByte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="646ae-133">任意の数値型 (`Byte` と列挙型を含む)、`Boolean`、`String`、`Object`</span><span class="sxs-lookup"><span data-stu-id="646ae-133">Any numeric type (including `Byte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CShort`|[<span data-ttu-id="646ae-134">Short データ型</span><span class="sxs-lookup"><span data-stu-id="646ae-134">Short Data Type</span></span>](../../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="646ae-135">任意の数値型 (`Byte`、`SByte`、列挙型など)、`Boolean`、`String`、`Object`</span><span class="sxs-lookup"><span data-stu-id="646ae-135">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CSng`|[<span data-ttu-id="646ae-136">Single データ型</span><span class="sxs-lookup"><span data-stu-id="646ae-136">Single Data Type</span></span>](../../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="646ae-137">任意の数値型 (`Byte`、`SByte`、列挙型など)、`Boolean`、`String`、`Object`</span><span class="sxs-lookup"><span data-stu-id="646ae-137">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CStr`|[<span data-ttu-id="646ae-138">String データ型</span><span class="sxs-lookup"><span data-stu-id="646ae-138">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="646ae-139">任意の数値型 (`Byte`、`SByte`、列挙型など)、`Boolean`、`Char`、`Char` 配列、`Date`、`Object`</span><span class="sxs-lookup"><span data-stu-id="646ae-139">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `Char`, `Char` array, `Date`, `Object`</span></span>|
|`CType`|<span data-ttu-id="646ae-140">コンマの後に指定された型 (`,`)</span><span class="sxs-lookup"><span data-stu-id="646ae-140">Type specified following the comma (`,`)</span></span>|<span data-ttu-id="646ae-141">基本*データ型*(基本型の配列を含む) に変換する場合、対応する conversion キーワードで許可されているものと同じ型です。</span><span class="sxs-lookup"><span data-stu-id="646ae-141">When converting to an *elementary data type* (including an array of an elementary type), the same types as allowed for the corresponding conversion keyword</span></span><br /><br /> <span data-ttu-id="646ae-142">*複合データ型*に変換する場合、それが実装するインターフェイスと継承元のクラス</span><span class="sxs-lookup"><span data-stu-id="646ae-142">When converting to a *composite data type*, the interfaces it implements and the classes from which it inherits</span></span><br /><br /> <span data-ttu-id="646ae-143">`CType`オーバーロードされたクラスまたは構造体に変換する場合は、そのクラスまたは構造体</span><span class="sxs-lookup"><span data-stu-id="646ae-143">When converting to a class or structure on which you have overloaded `CType`, that class or structure</span></span>|
|`CUInt`|[<span data-ttu-id="646ae-144">UInteger データ型</span><span class="sxs-lookup"><span data-stu-id="646ae-144">UInteger Data Type</span></span>](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="646ae-145">任意の数値型 (`Byte`、`SByte`、列挙型など)、`Boolean`、`String`、`Object`</span><span class="sxs-lookup"><span data-stu-id="646ae-145">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CULng`|[<span data-ttu-id="646ae-146">ULong データ型</span><span class="sxs-lookup"><span data-stu-id="646ae-146">ULong Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="646ae-147">任意の数値型 (`Byte`、`SByte`、列挙型など)、`Boolean`、`String`、`Object`</span><span class="sxs-lookup"><span data-stu-id="646ae-147">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CUShort`|[<span data-ttu-id="646ae-148">UShort データ型</span><span class="sxs-lookup"><span data-stu-id="646ae-148">UShort Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="646ae-149">任意の数値型 (`Byte`、`SByte`、列挙型など)、`Boolean`、`String`、`Object`</span><span class="sxs-lookup"><span data-stu-id="646ae-149">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|

## <a name="the-ctype-function"></a><span data-ttu-id="646ae-150">CType 関数</span><span class="sxs-lookup"><span data-stu-id="646ae-150">The CType Function</span></span>

<span data-ttu-id="646ae-151">[CType 関数](../../../../visual-basic/language-reference/functions/ctype-function.md)は、2つの引数を操作します。</span><span class="sxs-lookup"><span data-stu-id="646ae-151">The [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) operates on two arguments.</span></span> <span data-ttu-id="646ae-152">1つ目は変換される式で、2番目は変換先のデータ型またはオブジェクトクラスです。</span><span class="sxs-lookup"><span data-stu-id="646ae-152">The first is the expression to be converted, and the second is the destination data type or object class.</span></span> <span data-ttu-id="646ae-153">最初の引数は型ではなく、式である必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="646ae-153">Note that the first argument must be an expression, not a type.</span></span>

<span data-ttu-id="646ae-154">`CType` は*インライン関数*です。つまり、コンパイルされたコードは、多くの場合、関数呼び出しを生成せずに変換を行います。</span><span class="sxs-lookup"><span data-stu-id="646ae-154">`CType` is an *inline function*, meaning the compiled code makes the conversion, often without generating a function call.</span></span> <span data-ttu-id="646ae-155">これにより、パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="646ae-155">This improves performance.</span></span>

<span data-ttu-id="646ae-156">他の型変換キーワードと `CType` の比較については、「[DirectCast 演算子](../../../../visual-basic/language-reference/operators/directcast-operator.md)」および「[TryCast 演算子](../../../../visual-basic/language-reference/operators/trycast-operator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="646ae-156">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>

### <a name="elementary-types"></a><span data-ttu-id="646ae-157">基本型</span><span class="sxs-lookup"><span data-stu-id="646ae-157">Elementary Types</span></span>

<span data-ttu-id="646ae-158">次の例は、`CType` の使い方を示しています。</span><span class="sxs-lookup"><span data-stu-id="646ae-158">The following example demonstrates the use of `CType`.</span></span>

```vb
k = CType(q, Integer)
' The following statement coerces w to the specific object class Label.
f = CType(w, Label)
```

### <a name="composite-types"></a><span data-ttu-id="646ae-159">複合型</span><span class="sxs-lookup"><span data-stu-id="646ae-159">Composite Types</span></span>

<span data-ttu-id="646ae-160">`CType` を使用すると、値を複合データ型だけでなく基本型にも変換できます。</span><span class="sxs-lookup"><span data-stu-id="646ae-160">You can use `CType` to convert values to composite data types as well as to elementary types.</span></span> <span data-ttu-id="646ae-161">また、次の例のように、このメソッドを使用して、オブジェクトクラスをそのインターフェイスの1つの型に強制的に変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="646ae-161">You can also use it to coerce an object class to the type of one of its interfaces, as in the following example.</span></span>

```vb
' Assume class cZone implements interface iZone.
Dim h As Object
' The first argument to CType must be an expression, not a type.
Dim cZ As cZone
' The following statement coerces a cZone object to its interface iZone.
h = CType(cZ, iZone)
```

### <a name="array-types"></a><span data-ttu-id="646ae-162">配列型</span><span class="sxs-lookup"><span data-stu-id="646ae-162">Array Types</span></span>

<span data-ttu-id="646ae-163">次の例のように、`CType` 配列のデータ型を変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="646ae-163">`CType` can also convert array data types, as in the following example.</span></span>

```vb
Dim v() As classV
Dim obArray() As Object
' Assume some object array has been assigned to obArray.
' Check for run-time type compatibility.
If TypeOf obArray Is classV()
    ' obArray can be converted to classV.
    v = CType(obArray, classV())
End If
```

<span data-ttu-id="646ae-164">詳細と例については、「[配列の変換](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="646ae-164">For more information and an example, see [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).</span></span>

### <a name="types-defining-ctype"></a><span data-ttu-id="646ae-165">CType を定義する型</span><span class="sxs-lookup"><span data-stu-id="646ae-165">Types Defining CType</span></span>

<span data-ttu-id="646ae-166">定義したクラスまたは構造体で `CType` を定義できます。</span><span class="sxs-lookup"><span data-stu-id="646ae-166">You can define `CType` on a class or structure you have defined.</span></span> <span data-ttu-id="646ae-167">これにより、クラスまたは構造体の型との間で値を変換できます。</span><span class="sxs-lookup"><span data-stu-id="646ae-167">This allows you to convert values to and from the type of your class or structure.</span></span> <span data-ttu-id="646ae-168">詳細と例については、「[方法: 変換演算子を定義する](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="646ae-168">For more information and an example, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>

> [!NOTE]
> <span data-ttu-id="646ae-169">変換キーワードと共に使用する値は、変換先のデータ型に対して有効でなければなりません。または、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="646ae-169">Values used with a conversion keyword must be valid for the destination data type, or an error occurs.</span></span> <span data-ttu-id="646ae-170">たとえば、`Long` を `Integer`に変換しようとした場合、`Long` の値は、`Integer` データ型の有効な範囲内である必要があります。</span><span class="sxs-lookup"><span data-stu-id="646ae-170">For example, if you attempt to convert a `Long` to an `Integer`, the value of the `Long` must be within the valid range for the `Integer` data type.</span></span>

> [!CAUTION]
> <span data-ttu-id="646ae-171">ソース型が変換先の型から派生していない場合、あるクラス型から別の型に変換する `CType` の指定は実行時に失敗します。</span><span class="sxs-lookup"><span data-stu-id="646ae-171">Specifying `CType` to convert from one class type to another fails at run time if the source type does not derive from the destination type.</span></span> <span data-ttu-id="646ae-172">このようなエラーが発生すると、<xref:System.InvalidCastException> 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="646ae-172">Such a failure throws an <xref:System.InvalidCastException> exception.</span></span>

<span data-ttu-id="646ae-173">ただし、型のいずれかが定義した構造体またはクラスであり、その構造体またはクラスに `CType` が定義されている場合、`CType` の要件を満たすと変換が成功する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="646ae-173">However, if one of the types is a structure or class you have defined, and if you have defined `CType` on that structure or class, a conversion can succeed if it satisfies the requirements of your `CType`.</span></span> <span data-ttu-id="646ae-174">「[方法: 変換演算子を定義する](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="646ae-174">See [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>

<span data-ttu-id="646ae-175">明示的な変換を実行することは、特定のデータ型またはオブジェクトクラスに式を*キャスト*することとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="646ae-175">Performing an explicit conversion is also known as *casting* an expression to a given data type or object class.</span></span>

## <a name="see-also"></a><span data-ttu-id="646ae-176">参照</span><span class="sxs-lookup"><span data-stu-id="646ae-176">See also</span></span>

- [<span data-ttu-id="646ae-177">Visual Basic における型変換</span><span class="sxs-lookup"><span data-stu-id="646ae-177">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="646ae-178">文字列とその他の型との変換</span><span class="sxs-lookup"><span data-stu-id="646ae-178">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="646ae-179">方法: Visual Basic でオブジェクトを別の型に変換する</span><span class="sxs-lookup"><span data-stu-id="646ae-179">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="646ae-180">構造体</span><span class="sxs-lookup"><span data-stu-id="646ae-180">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="646ae-181">データの種類</span><span class="sxs-lookup"><span data-stu-id="646ae-181">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="646ae-182">CString</span><span class="sxs-lookup"><span data-stu-id="646ae-182">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="646ae-183">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="646ae-183">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
