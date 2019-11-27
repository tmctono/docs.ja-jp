---
title: 型文字
ms.date: 01/31/2018
helpviewer_keywords:
- '&H prefix for hexadecimal values'
- hexadecimal literals [Visual Basic]
- F literal type character [Visual Basic]
- '& identifier type character'
- type characters [Visual Basic]
- octal literals [Visual Basic]
- literals [Visual Basic], hexadecimal
- '&O prefix for octal values'
- literals [Visual Basic], default types
- defaults, literal types
- C literal type character [Visual Basic]
- type characters [Visual Basic], literal
- $ identifier type character
- L literal type character [Visual Basic]
- UI literal type characters [Visual Basic]
- default literal types [Visual Basic]
- D literal type character [Visual Basic]
- literals [Visual Basic], octal
- S literal type character [Visual Basic]
- '! identifier type character'
- US literal type characters [Visual Basic]
- '% identifier type character'
- data types [Visual Basic], type characters
- characters [Visual Basic], identifier type
- type characters [Visual Basic], identifier
- '# identifier type character'
- identifier type characters [Visual Basic]
- literal type characters [Visual Basic]
- I literal type character [Visual Basic]
- R literal type character [Visual Basic]
- '@ identifier type character'
- UL literal type characters [Visual Basic]
- literal types [Visual Basic], default
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
ms.openlocfilehash: 628461c8136946dd902c0a52048eee7c516c52cd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352935"
---
# <a name="type-characters-visual-basic"></a><span data-ttu-id="bc276-102">型文字 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc276-102">Type characters (Visual Basic)</span></span>

<span data-ttu-id="bc276-103">宣言ステートメントでデータ型を指定するだけでなく、一部のプログラミング要素のデータ型を*型文字*に強制的に適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="bc276-103">In addition to specifying a data type in a declaration statement, you can force the data type of some programming elements with a *type character*.</span></span> <span data-ttu-id="bc276-104">型文字は、要素の直後に指定する必要があります。その際、任意の文字を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="bc276-104">The type character must immediately follow the element, with no intervening characters of any kind.</span></span>

<span data-ttu-id="bc276-105">型文字は、要素の名前の一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="bc276-105">The type character is not part of the name of the element.</span></span> <span data-ttu-id="bc276-106">型文字で定義された要素は、型文字を使用せずに参照できます。</span><span class="sxs-lookup"><span data-stu-id="bc276-106">An element defined with a type character can be referenced without the type character.</span></span>

## <a name="identifier-type-characters"></a><span data-ttu-id="bc276-107">識別子の型文字</span><span class="sxs-lookup"><span data-stu-id="bc276-107">Identifier type characters</span></span>

<span data-ttu-id="bc276-108">Visual Basic には、変数または定数のデータ型を指定するために宣言で使用できる*識別子の型文字*のセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bc276-108">Visual Basic supplies a set of *identifier type characters* that you can use in a declaration to specify the data type of a variable or constant.</span></span> <span data-ttu-id="bc276-109">使用できる識別子の型文字と使用例を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="bc276-109">The following table shows the available identifier type characters with examples of usage.</span></span>
  
|<span data-ttu-id="bc276-110">識別子の型文字</span><span class="sxs-lookup"><span data-stu-id="bc276-110">Identifier type character</span></span>|<span data-ttu-id="bc276-111">データ型</span><span class="sxs-lookup"><span data-stu-id="bc276-111">Data type</span></span>|<span data-ttu-id="bc276-112">例</span><span class="sxs-lookup"><span data-stu-id="bc276-112">Example</span></span>|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 <span data-ttu-id="bc276-113">`Boolean`、`Byte`、`Char`、`Date`、`Object`、`SByte`、`Short`、`UInteger`、`ULong`、または `UShort` のデータ型、または配列や構造体などの複合データ型には、識別子の型文字が存在しません。</span><span class="sxs-lookup"><span data-stu-id="bc276-113">No identifier type characters exist for the `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="bc276-114">場合によっては、`$` 文字を `Left`ではなく `Left$` などの Visual Basic 関数に追加して、型 `String`の戻り値を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="bc276-114">In some cases, you can append the `$` character to a Visual Basic function, for example `Left$` instead of `Left`, to obtain a returned value of type `String`.</span></span>

<span data-ttu-id="bc276-115">いずれの場合も、識別子の型文字は識別子名の直後に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc276-115">In all cases, the identifier type character must immediately follow the identifier name.</span></span>

## <a name="literal-type-characters"></a><span data-ttu-id="bc276-116">リテラルの型文字</span><span class="sxs-lookup"><span data-stu-id="bc276-116">Literal type characters</span></span>

<span data-ttu-id="bc276-117">*リテラル*は、データ型の特定の値のテキスト表現です。</span><span class="sxs-lookup"><span data-stu-id="bc276-117">A *literal* is a textual representation of a particular value of a data type.</span></span>  

### <a name="default-literal-types"></a><span data-ttu-id="bc276-118">既定のリテラル型</span><span class="sxs-lookup"><span data-stu-id="bc276-118">Default literal types</span></span>

<span data-ttu-id="bc276-119">コードに表示されるリテラルの形式は、通常、そのデータ型を決定します。</span><span class="sxs-lookup"><span data-stu-id="bc276-119">The form of a literal as it appears in your code ordinarily determines its data type.</span></span> <span data-ttu-id="bc276-120">これらの既定の型を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="bc276-120">The following table shows these default types.</span></span>  
  
|<span data-ttu-id="bc276-121">リテラルのテキスト形式</span><span class="sxs-lookup"><span data-stu-id="bc276-121">Textual form of literal</span></span>|<span data-ttu-id="bc276-122">既定のデータ型</span><span class="sxs-lookup"><span data-stu-id="bc276-122">Default data type</span></span>|<span data-ttu-id="bc276-123">例</span><span class="sxs-lookup"><span data-stu-id="bc276-123">Example</span></span>|  
|-----------------------------|-----------------------|-------------|  
|<span data-ttu-id="bc276-124">数値、小数部なし</span><span class="sxs-lookup"><span data-stu-id="bc276-124">Numeric, no fractional part</span></span>|`Integer`|`2147483647`|  
|<span data-ttu-id="bc276-125">数値、小数部を含まない、`Integer` に対して大きすぎます</span><span class="sxs-lookup"><span data-stu-id="bc276-125">Numeric, no fractional part, too large for `Integer`</span></span>|`Long`|`2147483648`|  
|<span data-ttu-id="bc276-126">数値、小数部</span><span class="sxs-lookup"><span data-stu-id="bc276-126">Numeric, fractional part</span></span>|`Double`|`1.2`|  
|<span data-ttu-id="bc276-127">二重引用符で囲む。</span><span class="sxs-lookup"><span data-stu-id="bc276-127">Enclosed in double quotation marks</span></span>|`String`|`"A"`|  
|<span data-ttu-id="bc276-128">シャープ記号で囲まれた</span><span class="sxs-lookup"><span data-stu-id="bc276-128">Enclosed within number signs</span></span>|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a><span data-ttu-id="bc276-129">強制されるリテラル型</span><span class="sxs-lookup"><span data-stu-id="bc276-129">Forced literal types</span></span>

<span data-ttu-id="bc276-130">Visual Basic には、リテラルの*型文字*のセットが用意されています。これを使用すると、リテラルが、フォームが示す以外のデータ型を強制的に想定することができます。</span><span class="sxs-lookup"><span data-stu-id="bc276-130">Visual Basic supplies a set of *literal type characters*, which you can use to force a literal to assume a data type other than the one its form indicates.</span></span> <span data-ttu-id="bc276-131">これを行うには、リテラルの末尾に文字を追加します。</span><span class="sxs-lookup"><span data-stu-id="bc276-131">You do this by appending the character to the end of the literal.</span></span> <span data-ttu-id="bc276-132">使用できるリテラル型文字と使用例を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="bc276-132">The following table shows the available literal type characters with examples of usage.</span></span>
  
|<span data-ttu-id="bc276-133">リテラルの型文字</span><span class="sxs-lookup"><span data-stu-id="bc276-133">Literal type character</span></span>|<span data-ttu-id="bc276-134">データ型</span><span class="sxs-lookup"><span data-stu-id="bc276-134">Data type</span></span>|<span data-ttu-id="bc276-135">例</span><span class="sxs-lookup"><span data-stu-id="bc276-135">Example</span></span>|  
|----------------------------|---------------|-------------|  
|`S`|`Short`|`I = 347S`|
|`I`|`Integer`|`J = 347I`|
|`L`|`Long`|`K = 347L`|
|`D`|`Decimal`|`X = 347D`|
|`F`|`Single`|`Y = 347F`|
|`R`|`Double`|`Z = 347R`|
|`US`|`UShort`|`L = 347US`|
|`UI`|`UInteger`|`M = 347UI`|
|`UL`|`ULong`|`N = 347UL`|
|`C`|`Char`|`Q = "."C`|

<span data-ttu-id="bc276-136">`Boolean`、`Byte`、`Date`、`Object`、`SByte`、または `String` のデータ型、または配列や構造体などの複合データ型のリテラル型文字は存在しません。</span><span class="sxs-lookup"><span data-stu-id="bc276-136">No literal type characters exist for the `Boolean`, `Byte`, `Date`, `Object`, `SByte`, or `String` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="bc276-137">リテラルでは、変数、定数、および式と同様に、識別子の型文字 (`%`、`&`、`@`、`!`、`#`、`$`) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="bc276-137">Literals can also use the identifier type characters (`%`, `&`, `@`, `!`, `#`, `$`), as can variables, constants, and expressions.</span></span> <span data-ttu-id="bc276-138">ただし、リテラルの型文字 (`S`、`I`、`L`、`D`、`F`、`R`、`C`) は、リテラルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="bc276-138">However, the literal type characters (`S`, `I`, `L`, `D`, `F`, `R`, `C`) can be used only with literals.</span></span>

<span data-ttu-id="bc276-139">いずれの場合も、リテラルの型文字はリテラル値の直後にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc276-139">In all cases, the literal type character must immediately follow the literal value.</span></span>

## <a name="hexadecimal-binary-and-octal-literals"></a><span data-ttu-id="bc276-140">16進数、バイナリ、および8進数のリテラル</span><span class="sxs-lookup"><span data-stu-id="bc276-140">Hexadecimal, binary, and octal literals</span></span>

<span data-ttu-id="bc276-141">通常、コンパイラは、整数リテラルを10進 (基数 10) の数値システムに配置します。</span><span class="sxs-lookup"><span data-stu-id="bc276-141">The compiler normally interprets an integer literal to be in the decimal (base 10) number system.</span></span> <span data-ttu-id="bc276-142">また、整数リテラルを16進数 (base 16) の数値として定義することもできます。これには、`&H` プレフィックス、`&B` プレフィックスを持つバイナリ (基数 2) 番号、および `&O` プレフィックスを持つ8進数 (基本 8) 番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="bc276-142">You can also define an integer literal as a hexadecimal (base 16) number with the `&H` prefix, as a binary (base 2) number with the `&B` prefix, and as an octal (base 8) number with the `&O` prefix.</span></span> <span data-ttu-id="bc276-143">プレフィックスの後の数字は、数値システムに適している必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc276-143">The digits that follow the prefix must be appropriate for the number system.</span></span> <span data-ttu-id="bc276-144">次の表にこれを示します。</span><span class="sxs-lookup"><span data-stu-id="bc276-144">The following table illustrates this.</span></span>  
  
|<span data-ttu-id="bc276-145">数値ベース</span><span class="sxs-lookup"><span data-stu-id="bc276-145">Number base</span></span>|<span data-ttu-id="bc276-146">［プレフィックス］</span><span class="sxs-lookup"><span data-stu-id="bc276-146">Prefix</span></span>|<span data-ttu-id="bc276-147">有効な桁の値</span><span class="sxs-lookup"><span data-stu-id="bc276-147">Valid digit values</span></span>|<span data-ttu-id="bc276-148">例</span><span class="sxs-lookup"><span data-stu-id="bc276-148">Example</span></span>|
|-----------------|------------|------------------------|-------------|
|<span data-ttu-id="bc276-149">16 進数 (基数 16)。</span><span class="sxs-lookup"><span data-stu-id="bc276-149">Hexadecimal (base 16)</span></span>|`&H`|<span data-ttu-id="bc276-150">0-9 と A-F</span><span class="sxs-lookup"><span data-stu-id="bc276-150">0-9 and A-F</span></span>|`&HFFFF`|
|<span data-ttu-id="bc276-151">Binary (基数 2)</span><span class="sxs-lookup"><span data-stu-id="bc276-151">Binary (base 2)</span></span>|`&B`|<span data-ttu-id="bc276-152">0-1</span><span class="sxs-lookup"><span data-stu-id="bc276-152">0-1</span></span>|`&B01111100`|
|<span data-ttu-id="bc276-153">8 進数 (基数 8)。</span><span class="sxs-lookup"><span data-stu-id="bc276-153">Octal (base 8)</span></span>|`&O`|<span data-ttu-id="bc276-154">0-7</span><span class="sxs-lookup"><span data-stu-id="bc276-154">0-7</span></span>|`&O77`|

<span data-ttu-id="bc276-155">Visual Basic 2017 以降では、アンダースコア文字 (`_`) をグループ区切り記号として使用して、整数リテラルの読みやすさを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="bc276-155">Starting in Visual Basic 2017, you can use the underscore character (`_`) as a group separator to enhance the readability of an integral literal.</span></span> <span data-ttu-id="bc276-156">次の例では、`_` 文字を使用して、バイナリリテラルを8ビットグループにグループ化します。</span><span class="sxs-lookup"><span data-stu-id="bc276-156">The following example uses the `_` character to group a binary literal into 8-bit groups:</span></span>

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

<span data-ttu-id="bc276-157">プレフィックス付きリテラルの後にリテラル文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bc276-157">You can follow a prefixed literal with a literal type character.</span></span> <span data-ttu-id="bc276-158">この例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bc276-158">The following example shows this.</span></span>

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

<span data-ttu-id="bc276-159">前の例では、`counter` の小数点以下の値は-32768 で、`flags` の10進値は + 32768 です。</span><span class="sxs-lookup"><span data-stu-id="bc276-159">In the previous example, `counter` has the decimal value of -32768, and `flags` has the decimal value of +32768.</span></span>

<span data-ttu-id="bc276-160">Visual Basic 15.5 以降では、アンダースコア文字 (`_`) をプレフィックスと16進数、バイナリ、または8進数の間の先頭の区切り記号として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="bc276-160">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="bc276-161">例 :</span><span class="sxs-lookup"><span data-stu-id="bc276-161">For example:</span></span>

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a><span data-ttu-id="bc276-162">参照</span><span class="sxs-lookup"><span data-stu-id="bc276-162">See also</span></span>

- [<span data-ttu-id="bc276-163">データの種類</span><span class="sxs-lookup"><span data-stu-id="bc276-163">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="bc276-164">基本データ型</span><span class="sxs-lookup"><span data-stu-id="bc276-164">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="bc276-165">値型と参照型</span><span class="sxs-lookup"><span data-stu-id="bc276-165">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="bc276-166">Visual Basic での型変換</span><span class="sxs-lookup"><span data-stu-id="bc276-166">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="bc276-167">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="bc276-167">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="bc276-168">変数宣言</span><span class="sxs-lookup"><span data-stu-id="bc276-168">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="bc276-169">データの種類</span><span class="sxs-lookup"><span data-stu-id="bc276-169">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
