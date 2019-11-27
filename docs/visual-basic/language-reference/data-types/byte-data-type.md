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
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344078"
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="ba5ba-102">Byte データ型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ba5ba-102">Byte data type (Visual Basic)</span></span>

<span data-ttu-id="ba5ba-103">0 ~ 255 の範囲の値を範囲とする符号なし8ビット (1 バイト) 整数を保持します。</span><span class="sxs-lookup"><span data-stu-id="ba5ba-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="ba5ba-104">コメント</span><span class="sxs-lookup"><span data-stu-id="ba5ba-104">Remarks</span></span>

<span data-ttu-id="ba5ba-105">バイナリデータを格納するには、`Byte` データ型を使用します。</span><span class="sxs-lookup"><span data-stu-id="ba5ba-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="ba5ba-106">`Byte` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="ba5ba-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="ba5ba-107">リテラルの代入</span><span class="sxs-lookup"><span data-stu-id="ba5ba-107">Literal assignments</span></span>

<span data-ttu-id="ba5ba-108">`Byte` 変数は、10進リテラル、16進リテラル、8進数リテラル、または (Visual Basic 2017 で始まる) バイナリリテラルを割り当てることによって、宣言および初期化できます。</span><span class="sxs-lookup"><span data-stu-id="ba5ba-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="ba5ba-109">整数リテラルが `Byte` の範囲外の場合 (つまり、<xref:System.Byte.MinValue?displayProperty=nameWithType> より小さいか <xref:System.Byte.MaxValue?displayProperty=nameWithType>より大きい場合)、コンパイルエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="ba5ba-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="ba5ba-110">次の例では、整数201を10進リテラル、16進リテラル、バイナリリテラルで表したものが、[整数](integer-data-type.md)から `byte` 値に暗黙的に変換されています。</span><span class="sxs-lookup"><span data-stu-id="ba5ba-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="ba5ba-111">プレフィックス `&h` または `&H` を使用して、16進リテラル、プレフィックス `&b` または `&B` がバイナリリテラルを示すようにし、プレフィックス `&o` または `&O` を使用して8進数リテラルを表します。</span><span class="sxs-lookup"><span data-stu-id="ba5ba-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="ba5ba-112">10 進リテラルには、プレフィックスはありません。</span><span class="sxs-lookup"><span data-stu-id="ba5ba-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="ba5ba-113">Visual Basic 2017 以降では、次の例に示すように、アンダースコア文字 (`_`) を桁区切り記号として使用して、読みやすくすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ba5ba-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

<span data-ttu-id="ba5ba-114">Visual Basic 15.5 以降では、アンダースコア文字 (`_`) をプレフィックスと16進数、バイナリ、または8進数の間の先頭の区切り記号として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="ba5ba-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="ba5ba-115">例 :</span><span class="sxs-lookup"><span data-stu-id="ba5ba-115">For example:</span></span>

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a><span data-ttu-id="ba5ba-116">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="ba5ba-116">Programming tips</span></span>

- <span data-ttu-id="ba5ba-117">**負の数値。**</span><span class="sxs-lookup"><span data-stu-id="ba5ba-117">**Negative Numbers.**</span></span> <span data-ttu-id="ba5ba-118">`Byte` は符号なしの型であるため、負の数を表すことはできません。</span><span class="sxs-lookup"><span data-stu-id="ba5ba-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="ba5ba-119">`Byte`型に評価される式に対して単項マイナス記号 (`-`) 演算子を使用すると、Visual Basic 式が最初に `Short` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ba5ba-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
- <span data-ttu-id="ba5ba-120">**書式変換。**</span><span class="sxs-lookup"><span data-stu-id="ba5ba-120">**Format Conversions.**</span></span> <span data-ttu-id="ba5ba-121">Visual Basic がファイルの読み取りまたは書き込みを行うとき、または Dll、メソッド、およびプロパティを呼び出すときに、データ形式間で自動的に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="ba5ba-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="ba5ba-122">`Byte` の変数および配列に格納されているバイナリデータは、そのような形式の変換中に保持されます。</span><span class="sxs-lookup"><span data-stu-id="ba5ba-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="ba5ba-123">バイナリデータには `String` 変数を使用しないでください。 ANSI 形式と Unicode 形式の間の変換中は、その内容が破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ba5ba-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

- <span data-ttu-id="ba5ba-124">**広げ.**</span><span class="sxs-lookup"><span data-stu-id="ba5ba-124">**Widening.**</span></span> <span data-ttu-id="ba5ba-125">`Byte` のデータ型は、`Short`、`UShort`、`Integer`、`UInteger`、`Long`、`ULong`、`Decimal`、`Single`、`Double`に拡大変換されます。</span><span class="sxs-lookup"><span data-stu-id="ba5ba-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="ba5ba-126">つまり、<xref:System.OverflowException?displayProperty=nameWithType> エラーが発生することなく、`Byte` をこれらの型のいずれかに変換できます。</span><span class="sxs-lookup"><span data-stu-id="ba5ba-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
- <span data-ttu-id="ba5ba-127">**文字を入力します。**</span><span class="sxs-lookup"><span data-stu-id="ba5ba-127">**Type Characters.**</span></span> <span data-ttu-id="ba5ba-128">`Byte` には、リテラルの型文字または識別子の型文字がありません。</span><span class="sxs-lookup"><span data-stu-id="ba5ba-128">`Byte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="ba5ba-129">**フレームワークの種類。**</span><span class="sxs-lookup"><span data-stu-id="ba5ba-129">**Framework Type.**</span></span> <span data-ttu-id="ba5ba-130">.NET Framework において対応する型は、<xref:System.Byte?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="ba5ba-130">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="ba5ba-131">例</span><span class="sxs-lookup"><span data-stu-id="ba5ba-131">Example</span></span>

 <span data-ttu-id="ba5ba-132">次の例では、`b` は `Byte` 変数です。</span><span class="sxs-lookup"><span data-stu-id="ba5ba-132">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="ba5ba-133">ステートメントでは、変数の範囲と、それに対するビットシフト演算子の適用を示します。</span><span class="sxs-lookup"><span data-stu-id="ba5ba-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a><span data-ttu-id="ba5ba-134">参照</span><span class="sxs-lookup"><span data-stu-id="ba5ba-134">See also</span></span>

- <xref:System.Byte?displayProperty=nameWithType>
- [<span data-ttu-id="ba5ba-135">データの種類</span><span class="sxs-lookup"><span data-stu-id="ba5ba-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="ba5ba-136">CString</span><span class="sxs-lookup"><span data-stu-id="ba5ba-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="ba5ba-137">変換の概要</span><span class="sxs-lookup"><span data-stu-id="ba5ba-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="ba5ba-138">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="ba5ba-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
