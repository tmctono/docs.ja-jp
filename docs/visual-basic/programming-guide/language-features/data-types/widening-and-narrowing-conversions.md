---
title: Widening and Narrowing Conversions
ms.date: 07/20/2015
helpviewer_keywords:
- widening conversions [Visual Basic]
- narrowing conversions [Visual Basic]
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- conversions [Visual Basic], exceptions during conversion
- type conversion [Visual Basic], exceptions during conversion
- conversions [Visual Basic], data type
- conversions [Visual Basic], narrowing
- type conversion [Visual Basic], narrowing
- data type conversion [Visual Basic], widening
- data type conversion [Visual Basic], narrowing
- changing data types [Visual Basic]
- type conversion [Visual Basic], widening
- data type conversion [Visual Basic], exceptions during conversion
- conversions [Visual Basic], widening
ms.assetid: 058c3152-6c28-4268-af44-2209e774f0bd
ms.openlocfilehash: 72cc1a2179db4f057c45cd2ff4de82a6437d6b58
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348686"
---
# <a name="widening-and-narrowing-conversions-visual-basic"></a><span data-ttu-id="53bad-102">拡大変換と縮小変換 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53bad-102">Widening and Narrowing Conversions (Visual Basic)</span></span>
<span data-ttu-id="53bad-103">型変換に関する重要な考慮事項は、変換の結果が変換先のデータ型の範囲内にあるかどうかです。</span><span class="sxs-lookup"><span data-stu-id="53bad-103">An important consideration with a type conversion is whether the result of the conversion is within the range of the destination data type.</span></span>  
  
 <span data-ttu-id="53bad-104">*拡大変換*では、元のデータの任意の値を使用できるデータ型に値が変更されます。</span><span class="sxs-lookup"><span data-stu-id="53bad-104">A *widening conversion* changes a value to a data type that can allow for any possible value of the original data.</span></span>  <span data-ttu-id="53bad-105">拡大変換ではソース値が保持されますが、その表現を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="53bad-105">Widening conversions preserve the source value but can change its representation.</span></span> <span data-ttu-id="53bad-106">このエラーは、整数型から `Decimal`に変換した場合、または `Char` から `String`に変換した場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="53bad-106">This occurs if you convert from an integral type to `Decimal`, or from `Char` to `String`.</span></span>  
  
 <span data-ttu-id="53bad-107">*縮小変換* により、有効値の一部を保持できない可能性のあるデータ型に値が変更されます。</span><span class="sxs-lookup"><span data-stu-id="53bad-107">A *narrowing conversion* changes a value to a data type that might not be able to hold some of the possible values.</span></span> <span data-ttu-id="53bad-108">たとえば、小数値を整数型に変換すると丸められ、`Boolean` に変換される数値型は `True` または `False`に縮小されます。</span><span class="sxs-lookup"><span data-stu-id="53bad-108">For example, a fractional value is rounded when it is converted to an integral type, and a numeric type being converted to `Boolean` is reduced to either `True` or `False`.</span></span>  
  
## <a name="widening-conversions"></a><span data-ttu-id="53bad-109">拡大変換</span><span class="sxs-lookup"><span data-stu-id="53bad-109">Widening Conversions</span></span>  
 <span data-ttu-id="53bad-110">次の表は、標準の拡大変換を示しています。</span><span class="sxs-lookup"><span data-stu-id="53bad-110">The following table shows the standard widening conversions.</span></span>  
  
|<span data-ttu-id="53bad-111">データ型</span><span class="sxs-lookup"><span data-stu-id="53bad-111">Data type</span></span>|<span data-ttu-id="53bad-112">データ型への拡大変換<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="53bad-112">Widens to data types <sup>1</sup></span></span>|  
|---|---|  
|[<span data-ttu-id="53bad-113">SByte</span><span class="sxs-lookup"><span data-stu-id="53bad-113">SByte</span></span>](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="53bad-114">`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="53bad-114">`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="53bad-115">Byte</span><span class="sxs-lookup"><span data-stu-id="53bad-115">Byte</span></span>](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="53bad-116">`Byte`、`Short`、`UShort`、`Integer`、`UInteger`、`Long`、`ULong`、`Decimal`、`Single`、`Double`</span><span class="sxs-lookup"><span data-stu-id="53bad-116">`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="53bad-117">Short</span><span class="sxs-lookup"><span data-stu-id="53bad-117">Short</span></span>](../../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="53bad-118">`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="53bad-118">`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="53bad-119">UShort</span><span class="sxs-lookup"><span data-stu-id="53bad-119">UShort</span></span>](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="53bad-120">`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="53bad-120">`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="53bad-121">Integer</span><span class="sxs-lookup"><span data-stu-id="53bad-121">Integer</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="53bad-122">`Integer`、`Long`、`Decimal`、`Single`、`Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="53bad-122">`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="53bad-123">UInteger</span><span class="sxs-lookup"><span data-stu-id="53bad-123">UInteger</span></span>](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="53bad-124">`UInteger`、`Long`、`ULong`、`Decimal`、`Single`、`Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="53bad-124">`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="53bad-125">Long</span><span class="sxs-lookup"><span data-stu-id="53bad-125">Long</span></span>](../../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="53bad-126">`Long`、`Decimal`、`Single`、`Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="53bad-126">`Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="53bad-127">ULong</span><span class="sxs-lookup"><span data-stu-id="53bad-127">ULong</span></span>](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="53bad-128">`ULong`、`Decimal`、`Single`、`Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="53bad-128">`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="53bad-129">Decimal</span><span class="sxs-lookup"><span data-stu-id="53bad-129">Decimal</span></span>](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="53bad-130">`Decimal`、`Single`、`Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="53bad-130">`Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="53bad-131">Single</span><span class="sxs-lookup"><span data-stu-id="53bad-131">Single</span></span>](../../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="53bad-132">`Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="53bad-132">`Single`, `Double`</span></span>|  
|[<span data-ttu-id="53bad-133">Double</span><span class="sxs-lookup"><span data-stu-id="53bad-133">Double</span></span>](../../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
|<span data-ttu-id="53bad-134">任意の列挙型 ([列挙](../../../../visual-basic/language-reference/statements/enum-statement.md)型)</span><span class="sxs-lookup"><span data-stu-id="53bad-134">Any enumerated type ([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md))</span></span>|<span data-ttu-id="53bad-135">基になる整数型と、基になる型が拡大変換される任意の型。</span><span class="sxs-lookup"><span data-stu-id="53bad-135">Its underlying integral type and any type to which the underlying type widens.</span></span>|  
|[<span data-ttu-id="53bad-136">Char</span><span class="sxs-lookup"><span data-stu-id="53bad-136">Char</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="53bad-137">`Char`, `String`</span><span class="sxs-lookup"><span data-stu-id="53bad-137">`Char`, `String`</span></span>|  
|<span data-ttu-id="53bad-138">`Char` 配列</span><span class="sxs-lookup"><span data-stu-id="53bad-138">`Char` array</span></span>|<span data-ttu-id="53bad-139">`Char` 配列、`String`</span><span class="sxs-lookup"><span data-stu-id="53bad-139">`Char` array, `String`</span></span>|  
|<span data-ttu-id="53bad-140">任意の型</span><span class="sxs-lookup"><span data-stu-id="53bad-140">Any type</span></span>|[<span data-ttu-id="53bad-141">オブジェクト</span><span class="sxs-lookup"><span data-stu-id="53bad-141">Object</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|<span data-ttu-id="53bad-142">任意の派生型</span><span class="sxs-lookup"><span data-stu-id="53bad-142">Any derived type</span></span>|<span data-ttu-id="53bad-143">派生された<sup>3</sup>の基本型。</span><span class="sxs-lookup"><span data-stu-id="53bad-143">Any base type from which it is derived <sup>3</sup>.</span></span>|  
|<span data-ttu-id="53bad-144">任意の型</span><span class="sxs-lookup"><span data-stu-id="53bad-144">Any type</span></span>|<span data-ttu-id="53bad-145">実装する任意のインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="53bad-145">Any interface it implements.</span></span>|  
|[<span data-ttu-id="53bad-146">Nothing</span><span class="sxs-lookup"><span data-stu-id="53bad-146">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)|<span data-ttu-id="53bad-147">任意のデータ型またはオブジェクト型。</span><span class="sxs-lookup"><span data-stu-id="53bad-147">Any data type or object type.</span></span>|  
  
 <span data-ttu-id="53bad-148"><sup>1</sup>定義により、すべてのデータ型がそれ自体に拡大変換されます。</span><span class="sxs-lookup"><span data-stu-id="53bad-148"><sup>1</sup> By definition, every data type widens to itself.</span></span>  
  
 <span data-ttu-id="53bad-149"><sup>2</sup> `Integer`、`UInteger`、`Long`、`ULong`、または `Decimal` から `Single` または `Double` への変換では、精度は失われますが、マグニチュードが失われることはありません。</span><span class="sxs-lookup"><span data-stu-id="53bad-149"><sup>2</sup> Conversions from `Integer`, `UInteger`, `Long`, `ULong`, or `Decimal` to `Single` or `Double` might result in loss of precision, but never in loss of magnitude.</span></span> <span data-ttu-id="53bad-150">この意味では、情報の損失は発生しません。</span><span class="sxs-lookup"><span data-stu-id="53bad-150">In this sense they do not incur information loss.</span></span>  
  
 <span data-ttu-id="53bad-151"><sup>3</sup>派生型からその基本型の1つへの変換が拡大しているように思えるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="53bad-151"><sup>3</sup> It might seem surprising that a conversion from a derived type to one of its base types is widening.</span></span> <span data-ttu-id="53bad-152">理由は、派生型には基本型のすべてのメンバーが含まれているため、基本型のインスタンスとして修飾されます。</span><span class="sxs-lookup"><span data-stu-id="53bad-152">The justification is that the derived type contains all the members of the base type, so it qualifies as an instance of the base type.</span></span> <span data-ttu-id="53bad-153">逆方向では、基本型には派生型によって定義された新しいメンバーは含まれません。</span><span class="sxs-lookup"><span data-stu-id="53bad-153">In the opposite direction, the base type does not contain any new members defined by the derived type.</span></span>  
  
 <span data-ttu-id="53bad-154">拡大変換は実行時に常に成功し、データ損失は発生しません。</span><span class="sxs-lookup"><span data-stu-id="53bad-154">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="53bad-155">[Option Strict ステートメント](../../../../visual-basic/language-reference/statements/option-strict-statement.md)で型チェックスイッチを `On` に設定するか `Off`に設定するかにかかわらず、常に暗黙的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="53bad-155">You can always perform them implicitly, whether the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) sets the type checking switch to `On` or to `Off`.</span></span>  
  
## <a name="narrowing-conversions"></a><span data-ttu-id="53bad-156">縮小変換</span><span class="sxs-lookup"><span data-stu-id="53bad-156">Narrowing Conversions</span></span>  
 <span data-ttu-id="53bad-157">標準的な縮小変換には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="53bad-157">The standard narrowing conversions include the following:</span></span>  
  
- <span data-ttu-id="53bad-158">前の表の拡大変換の逆方向 (すべての型がそれ自体に拡大変換される点を除く)</span><span class="sxs-lookup"><span data-stu-id="53bad-158">The reverse directions of the widening conversions in the preceding table (except that every type widens to itself)</span></span>  
  
- <span data-ttu-id="53bad-159">[ブール](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)型と任意の数値型の間の双方向の変換</span><span class="sxs-lookup"><span data-stu-id="53bad-159">Conversions in either direction between [Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) and any numeric type</span></span>  
  
- <span data-ttu-id="53bad-160">任意の数値型から任意の列挙型への変換 (`Enum`)</span><span class="sxs-lookup"><span data-stu-id="53bad-160">Conversions from any numeric type to any enumerated type (`Enum`)</span></span>  
  
- <span data-ttu-id="53bad-161">[文字列](../../../../visual-basic/language-reference/data-types/string-data-type.md)と任意の数値型、`Boolean`、または[日付](../../../../visual-basic/language-reference/data-types/date-data-type.md)の間の双方向の変換</span><span class="sxs-lookup"><span data-stu-id="53bad-161">Conversions in either direction between [String](../../../../visual-basic/language-reference/data-types/string-data-type.md) and any numeric type, `Boolean`, or [Date](../../../../visual-basic/language-reference/data-types/date-data-type.md)</span></span>  
  
- <span data-ttu-id="53bad-162">データ型またはオブジェクト型から派生した型への変換</span><span class="sxs-lookup"><span data-stu-id="53bad-162">Conversions from a data type or object type to a type derived from it</span></span>  
  
 <span data-ttu-id="53bad-163">縮小変換は実行時に必ず成功するわけではないため、失敗したり、データ損失が発生したりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="53bad-163">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="53bad-164">変換先のデータ型が変換されている値を受け取ることができない場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="53bad-164">An error occurs if the destination data type cannot receive the value being converted.</span></span> <span data-ttu-id="53bad-165">たとえば、数値変換でオーバーフローが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="53bad-165">For example, a numeric conversion can result in an overflow.</span></span> <span data-ttu-id="53bad-166">[Option Strict ステートメント](../../../../visual-basic/language-reference/statements/option-strict-statement.md)で型チェックスイッチが `Off`に設定されていない限り、コンパイラでは、暗黙的に縮小変換を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="53bad-166">The compiler does not allow you to perform narrowing conversions implicitly unless the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) sets the type checking switch to `Off`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="53bad-167">`For Each…Next` コレクション内の要素から loop コントロール変数への変換では、縮小変換エラーが抑制されます。</span><span class="sxs-lookup"><span data-stu-id="53bad-167">The narrowing-conversion error is suppressed for conversions from the elements in a `For Each…Next` collection to the loop control variable.</span></span> <span data-ttu-id="53bad-168">詳細と例については、「」の「縮小変換」セクションを参照してください。 [次のステートメント](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="53bad-168">For more information and examples, see the "Narrowing Conversions" section in [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
### <a name="when-to-use-narrowing-conversions"></a><span data-ttu-id="53bad-169">縮小変換を使用する場合</span><span class="sxs-lookup"><span data-stu-id="53bad-169">When to Use Narrowing Conversions</span></span>  
 <span data-ttu-id="53bad-170">変換元の値が変換先のデータ型に変換できることがわかっている場合は、縮小変換を使用します。エラーやデータの損失は発生しません。</span><span class="sxs-lookup"><span data-stu-id="53bad-170">You use a narrowing conversion when you know the source value can be converted to the destination data type without error or data loss.</span></span> <span data-ttu-id="53bad-171">たとえば、"True" または "False" のいずれかが含まれていることがわかっている `String` がある場合は、`CBool` キーワードを使用して `Boolean`に変換できます。</span><span class="sxs-lookup"><span data-stu-id="53bad-171">For example, if you have a `String` that you know contains either "True" or "False," you can use the `CBool` keyword to convert it to `Boolean`.</span></span>  
  
## <a name="exceptions-during-conversion"></a><span data-ttu-id="53bad-172">変換中の例外</span><span class="sxs-lookup"><span data-stu-id="53bad-172">Exceptions During Conversion</span></span>  
 <span data-ttu-id="53bad-173">拡大変換は常に成功するため、例外はスローされません。</span><span class="sxs-lookup"><span data-stu-id="53bad-173">Because widening conversions always succeed, they do not throw exceptions.</span></span> <span data-ttu-id="53bad-174">縮小変換では、エラーが発生した場合、通常、次の例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="53bad-174">Narrowing conversions, when they fail, most commonly throw the following exceptions:</span></span>  
  
- <span data-ttu-id="53bad-175"><xref:System.InvalidCastException> —2つの型の間に変換が定義されていない場合</span><span class="sxs-lookup"><span data-stu-id="53bad-175"><xref:System.InvalidCastException> — if no conversion is defined between the two types</span></span>  
  
- <span data-ttu-id="53bad-176">変換後の値が対象の型に対して大きすぎる場合の <xref:System.OverflowException> (整数型のみ)</span><span class="sxs-lookup"><span data-stu-id="53bad-176"><xref:System.OverflowException> — (integral types only) if the converted value is too large for the target type</span></span>  
  
 <span data-ttu-id="53bad-177">クラスまたは構造体で、そのクラスまたは構造体への変換演算子として機能する[CType 関数](../../../../visual-basic/language-reference/functions/ctype-function.md)が定義されている場合、その `CType` によって、適切な例外がスローされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="53bad-177">If a class or structure defines a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to serve as a conversion operator to or from that class or structure, that `CType` can throw any exception it deems appropriate.</span></span> <span data-ttu-id="53bad-178">さらに、この `CType` は Visual Basic 関数または .NET Framework メソッドを呼び出す可能性があります。これにより、さまざまな例外がスローされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="53bad-178">In addition, that `CType` might call Visual Basic functions or .NET Framework methods, which in turn could throw a variety of exceptions.</span></span>  
  
## <a name="changes-during-reference-type-conversions"></a><span data-ttu-id="53bad-179">参照型変換中の変更</span><span class="sxs-lookup"><span data-stu-id="53bad-179">Changes During Reference Type Conversions</span></span>  
 <span data-ttu-id="53bad-180">*参照型*からの変換では、ポインターだけが値にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="53bad-180">A conversion from a *reference type* copies only the pointer to the value.</span></span> <span data-ttu-id="53bad-181">値自体は、どのような方法でもコピーも変更もされません。</span><span class="sxs-lookup"><span data-stu-id="53bad-181">The value itself is neither copied nor changed in any way.</span></span> <span data-ttu-id="53bad-182">変更できるのは、ポインターを保持している変数のデータ型だけです。</span><span class="sxs-lookup"><span data-stu-id="53bad-182">The only thing that can change is the data type of the variable holding the pointer.</span></span> <span data-ttu-id="53bad-183">次の例では、データ型は派生クラスから基本クラスに変換されますが、両方の変数が参照するオブジェクトは変更されません。</span><span class="sxs-lookup"><span data-stu-id="53bad-183">In the following example, the data type is converted from the derived class to its base class, but the object that both variables now point to is unchanged.</span></span>  
  
```vb  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## <a name="see-also"></a><span data-ttu-id="53bad-184">参照</span><span class="sxs-lookup"><span data-stu-id="53bad-184">See also</span></span>

- [<span data-ttu-id="53bad-185">データの種類</span><span class="sxs-lookup"><span data-stu-id="53bad-185">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="53bad-186">Visual Basic での型変換</span><span class="sxs-lookup"><span data-stu-id="53bad-186">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="53bad-187">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="53bad-187">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="53bad-188">文字列とその他の型との変換</span><span class="sxs-lookup"><span data-stu-id="53bad-188">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="53bad-189">方法: Visual Basic でオブジェクトを別の型に変換する</span><span class="sxs-lookup"><span data-stu-id="53bad-189">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="53bad-190">配列変換</span><span class="sxs-lookup"><span data-stu-id="53bad-190">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [<span data-ttu-id="53bad-191">データの種類</span><span class="sxs-lookup"><span data-stu-id="53bad-191">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="53bad-192">CString</span><span class="sxs-lookup"><span data-stu-id="53bad-192">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
