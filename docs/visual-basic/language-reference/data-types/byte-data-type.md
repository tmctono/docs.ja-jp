---
title: バイト型 (Byte)
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 347d7e7d0f09e089886bc81bd0be659deaca9b46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401353"
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="7aca9-102">バイト データ型</span><span class="sxs-lookup"><span data-stu-id="7aca9-102">Byte data type (Visual Basic)</span></span>

<span data-ttu-id="7aca9-103">0 から 255 までの範囲の符号なし 8 ビット (1 バイト) 整数を保持します。</span><span class="sxs-lookup"><span data-stu-id="7aca9-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="7aca9-104">解説</span><span class="sxs-lookup"><span data-stu-id="7aca9-104">Remarks</span></span>

<span data-ttu-id="7aca9-105">バイナリ`Byte`データを格納するには、データ型を使用します。</span><span class="sxs-lookup"><span data-stu-id="7aca9-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="7aca9-106">`Byte` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="7aca9-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="7aca9-107">リテラル代入</span><span class="sxs-lookup"><span data-stu-id="7aca9-107">Literal assignments</span></span>

<span data-ttu-id="7aca9-108">変数を`Byte`宣言して初期化するには、10 進リテラル、16 進リテラル、8 進数リテラル、または (Visual Basic 2017 以降) バイナリ リテラルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7aca9-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="7aca9-109">整数リテラルが a`Byte`の範囲外の場合 (つまり、それより小さい<xref:System.Byte.MinValue?displayProperty=nameWithType>かそれより大<xref:System.Byte.MaxValue?displayProperty=nameWithType>きい場合)、コンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="7aca9-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="7aca9-110">次の例では、10 進数、16 進数、およびバイナリ リテラルとして表される 201 の整数は[、Integer](integer-data-type.md)から値に`byte`暗黙的に変換されます。</span><span class="sxs-lookup"><span data-stu-id="7aca9-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="7aca9-111">プレフィックス`&h`を使用`&H`するか、16 進リテラル、プレフィックス`&b`、または`&B`バイナリ リテラルを表す場合、およびプレフィックス`&o`を`&O`表すか、8 進数リテラルを表します。</span><span class="sxs-lookup"><span data-stu-id="7aca9-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="7aca9-112">10 進リテラルには、プレフィックスはありません。</span><span class="sxs-lookup"><span data-stu-id="7aca9-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="7aca9-113">Visual Basic 2017 以降では、`_`下線付きの文字を桁区切り記号として使用して読みやすさを向上させることもできます。</span><span class="sxs-lookup"><span data-stu-id="7aca9-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

<span data-ttu-id="7aca9-114">Visual Basic 15.5 以降では、接頭辞と`_`16 進数、2 進数、または 8 進数の間の先頭の区切り記号としてアンダースコア文字 ( ) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="7aca9-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="7aca9-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7aca9-115">For example:</span></span>

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a><span data-ttu-id="7aca9-116">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="7aca9-116">Programming tips</span></span>

- <span data-ttu-id="7aca9-117">**負の数。**</span><span class="sxs-lookup"><span data-stu-id="7aca9-117">**Negative Numbers.**</span></span> <span data-ttu-id="7aca9-118">符号`Byte`なしの型であるため、負の数を表すことはできません。</span><span class="sxs-lookup"><span data-stu-id="7aca9-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="7aca9-119">型`-``Byte`と評価される式に単項マイナス ( ) 演算子を使用すると、その式が最初に`Short`変換されます。</span><span class="sxs-lookup"><span data-stu-id="7aca9-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
- <span data-ttu-id="7aca9-120">**変換の書式設定。**</span><span class="sxs-lookup"><span data-stu-id="7aca9-120">**Format Conversions.**</span></span> <span data-ttu-id="7aca9-121">Visual Basic では、ファイルの読み取りまたは書き込みを行うとき、または DLL、メソッド、およびプロパティを呼び出すときに、データ形式間で自動的に変換できます。</span><span class="sxs-lookup"><span data-stu-id="7aca9-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="7aca9-122">変数や配列に`Byte`格納されたバイナリデータは、このようなフォーマット変換中に保持されます。</span><span class="sxs-lookup"><span data-stu-id="7aca9-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="7aca9-123">ANSI 形式`String`と Unicode 形式の変換中に、その内容が破損する可能性があるため、バイナリ データには変数を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="7aca9-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

- <span data-ttu-id="7aca9-124">**拡大。**</span><span class="sxs-lookup"><span data-stu-id="7aca9-124">**Widening.**</span></span> <span data-ttu-id="7aca9-125">データ`Byte`型`Short`は、 、 `UShort`、 `Integer` `UInteger`、 `Long` `ULong`、 `Decimal` `Single`、 `Double`、 、 、 、 、 、 、 に拡大されます。</span><span class="sxs-lookup"><span data-stu-id="7aca9-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="7aca9-126">つまり、<xref:System.OverflowException?displayProperty=nameWithType>エラーが発生`Byte`することなく、これらの型に変換できます。</span><span class="sxs-lookup"><span data-stu-id="7aca9-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
- <span data-ttu-id="7aca9-127">**文字を入力します。**</span><span class="sxs-lookup"><span data-stu-id="7aca9-127">**Type Characters.**</span></span> <span data-ttu-id="7aca9-128">`Byte`リテラル型文字または識別子型文字がありません。</span><span class="sxs-lookup"><span data-stu-id="7aca9-128">`Byte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="7aca9-129">**Framework のデータ型**</span><span class="sxs-lookup"><span data-stu-id="7aca9-129">**Framework Type.**</span></span> <span data-ttu-id="7aca9-130">.NET Framework において対応する型は、<xref:System.Byte?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="7aca9-130">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="7aca9-131">例</span><span class="sxs-lookup"><span data-stu-id="7aca9-131">Example</span></span>

 <span data-ttu-id="7aca9-132">次の例では、`b`変数です`Byte`。</span><span class="sxs-lookup"><span data-stu-id="7aca9-132">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="7aca9-133">このステートメントは、変数の範囲と、それに対するビットシフト演算子の適用を示します。</span><span class="sxs-lookup"><span data-stu-id="7aca9-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a><span data-ttu-id="7aca9-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="7aca9-134">See also</span></span>

- <xref:System.Byte?displayProperty=nameWithType>
- [<span data-ttu-id="7aca9-135">データ型</span><span class="sxs-lookup"><span data-stu-id="7aca9-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="7aca9-136">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="7aca9-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="7aca9-137">変換の概要</span><span class="sxs-lookup"><span data-stu-id="7aca9-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="7aca9-138">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="7aca9-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
