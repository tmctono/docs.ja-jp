---
title: UShort 型
ms.date: 01/31/2018
f1_keywords:
- vb.ushort
helpviewer_keywords:
- numbers [Visual Basic], whole
- literal type characters [Visual Basic], US
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- UShort data type
- US literal type characters [Visual Basic]
ms.assetid: 138db892-665d-4ba8-9cae-d8d91c4a8f39
ms.openlocfilehash: 7cdbd5fb192fd5cc1be6260dcdcdb1f30cf3f865
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343850"
---
# <a name="ushort-data-type-visual-basic"></a><span data-ttu-id="5712f-102">UShort データ型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5712f-102">UShort data type (Visual Basic)</span></span>

<span data-ttu-id="5712f-103">0 ~ 65535 の値の範囲内の符号なし16ビット (2 バイト) 整数を保持します。</span><span class="sxs-lookup"><span data-stu-id="5712f-103">Holds unsigned 16-bit (2-byte) integers ranging in value from 0 through 65,535.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5712f-104">コメント</span><span class="sxs-lookup"><span data-stu-id="5712f-104">Remarks</span></span>

 <span data-ttu-id="5712f-105">`Byte`に対して大きすぎるバイナリデータを格納するには、`UShort` データ型を使用します。</span><span class="sxs-lookup"><span data-stu-id="5712f-105">Use the `UShort` data type to contain binary data too large for `Byte`.</span></span>  
  
 <span data-ttu-id="5712f-106">`UShort` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="5712f-106">The default value of `UShort` is 0.</span></span>  

## <a name="literal-assignments"></a><span data-ttu-id="5712f-107">リテラルの代入</span><span class="sxs-lookup"><span data-stu-id="5712f-107">Literal assignments</span></span>

<span data-ttu-id="5712f-108">`UShort` 変数は、10進リテラル、16進リテラル、8進数リテラル、または (Visual Basic 2017 で始まる) バイナリリテラルを割り当てることによって、宣言および初期化できます。</span><span class="sxs-lookup"><span data-stu-id="5712f-108">You can declare and initialize a `UShort` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="5712f-109">整数リテラルが `UShort` の範囲外にある場合 (つまり、<xref:System.UInt16.MinValue?displayProperty=nameWithType> より小さいか、<xref:System.UInt16.MaxValue?displayProperty=nameWithType> より大きい場合)、コンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="5712f-109">If the integer literal is outside the range of `UShort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="5712f-110">次の例では、整数65034を10進リテラル、16進リテラル、バイナリリテラルで表したものが `UShort` 値に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="5712f-110">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are assigned to `UShort` values.</span></span>
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> <span data-ttu-id="5712f-111">プレフィックス `&h` または `&H` を使用して、16進リテラル、プレフィックス `&b` または `&B` がバイナリリテラルを示すようにし、プレフィックス `&o` または `&O` を使用して8進数リテラルを表します。</span><span class="sxs-lookup"><span data-stu-id="5712f-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="5712f-112">10 進リテラルには、プレフィックスはありません。</span><span class="sxs-lookup"><span data-stu-id="5712f-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="5712f-113">Visual Basic 2017 以降では、次の例に示すように、アンダースコア文字 (`_`) を桁区切り記号として使用して、読みやすくすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5712f-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

<span data-ttu-id="5712f-114">Visual Basic 15.5 以降では、アンダースコア文字 (`_`) をプレフィックスと16進数、バイナリ、または8進数の間の先頭の区切り記号として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="5712f-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="5712f-115">例 :</span><span class="sxs-lookup"><span data-stu-id="5712f-115">For example:</span></span>

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="5712f-116">数値リテラルには、次の例に示すように、`UShort` データ型を示す `US` または `us`[型の文字](../../programming-guide/language-features/data-types/type-characters.md)を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="5712f-116">Numeric literals can also include the `US` or `us` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UShort` data type, as the following example shows.</span></span>

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a><span data-ttu-id="5712f-117">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="5712f-117">Programming tips</span></span>
  
- <span data-ttu-id="5712f-118">**負の数値。**</span><span class="sxs-lookup"><span data-stu-id="5712f-118">**Negative Numbers.**</span></span> <span data-ttu-id="5712f-119">`UShort` は符号なしの型であるため、負の数を表すことはできません。</span><span class="sxs-lookup"><span data-stu-id="5712f-119">Because `UShort` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="5712f-120">`UShort`型に評価される式に対して単項マイナス記号 (`-`) 演算子を使用すると、Visual Basic 式が最初に `Integer` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="5712f-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `UShort`, Visual Basic converts the expression to `Integer` first.</span></span>  
  
- <span data-ttu-id="5712f-121">**CLS 準拠。**</span><span class="sxs-lookup"><span data-stu-id="5712f-121">**CLS Compliance.**</span></span> <span data-ttu-id="5712f-122">`UShort` のデータ型は[共通言語仕様](https://www.ecma-international.org/publications/standards/Ecma-335.htm)(cls) の一部ではないため、cls 準拠のコードはそれを使用するコンポーネントを使用できません。</span><span class="sxs-lookup"><span data-stu-id="5712f-122">The `UShort` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
- <span data-ttu-id="5712f-123">**広げ.**</span><span class="sxs-lookup"><span data-stu-id="5712f-123">**Widening.**</span></span> <span data-ttu-id="5712f-124">`UShort` のデータ型は、`Integer`、`UInteger`、`Long`、`ULong`、`Decimal`、`Single`、`Double`に拡大変換されます。</span><span class="sxs-lookup"><span data-stu-id="5712f-124">The `UShort` data type widens to `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="5712f-125">つまり、<xref:System.OverflowException?displayProperty=nameWithType> エラーが発生することなく、`UShort` をこれらの型のいずれかに変換できます。</span><span class="sxs-lookup"><span data-stu-id="5712f-125">This means you can convert `UShort` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="5712f-126">**文字を入力します。**</span><span class="sxs-lookup"><span data-stu-id="5712f-126">**Type Characters.**</span></span> <span data-ttu-id="5712f-127">リテラルに `US` リテラル型文字を追加すると、`UShort` データ型に強制されます。</span><span class="sxs-lookup"><span data-stu-id="5712f-127">Appending the literal type characters `US` to a literal forces it to the `UShort` data type.</span></span> <span data-ttu-id="5712f-128">`UShort` に識別子の型文字がありません。</span><span class="sxs-lookup"><span data-stu-id="5712f-128">`UShort` has no identifier type character.</span></span>  
  
- <span data-ttu-id="5712f-129">**フレームワークの種類。**</span><span class="sxs-lookup"><span data-stu-id="5712f-129">**Framework Type.**</span></span> <span data-ttu-id="5712f-130">.NET Framework において対応する型は、<xref:System.UInt16?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="5712f-130">The corresponding type in the .NET Framework is the <xref:System.UInt16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5712f-131">参照</span><span class="sxs-lookup"><span data-stu-id="5712f-131">See also</span></span>

- <xref:System.UInt16>
- [<span data-ttu-id="5712f-132">データの種類</span><span class="sxs-lookup"><span data-stu-id="5712f-132">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="5712f-133">CString</span><span class="sxs-lookup"><span data-stu-id="5712f-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="5712f-134">変換の概要</span><span class="sxs-lookup"><span data-stu-id="5712f-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="5712f-135">方法 : 符号なしの型を使用する Windows の機能を呼び出す</span><span class="sxs-lookup"><span data-stu-id="5712f-135">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="5712f-136">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="5712f-136">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
