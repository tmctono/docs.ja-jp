---
title: UShort データ型
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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401311"
---
# <a name="ushort-data-type-visual-basic"></a><span data-ttu-id="f72bd-102">データ型を短くする</span><span class="sxs-lookup"><span data-stu-id="f72bd-102">UShort data type (Visual Basic)</span></span>

<span data-ttu-id="f72bd-103">0 から 65,535 までの範囲の符号なし 16 ビット (2 バイト) 整数を保持します。</span><span class="sxs-lookup"><span data-stu-id="f72bd-103">Holds unsigned 16-bit (2-byte) integers ranging in value from 0 through 65,535.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f72bd-104">解説</span><span class="sxs-lookup"><span data-stu-id="f72bd-104">Remarks</span></span>

 <span data-ttu-id="f72bd-105">データ型`UShort`を使用して、バイナリ データが大`Byte`きすぎて.</span><span class="sxs-lookup"><span data-stu-id="f72bd-105">Use the `UShort` data type to contain binary data too large for `Byte`.</span></span>  
  
 <span data-ttu-id="f72bd-106">`UShort` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="f72bd-106">The default value of `UShort` is 0.</span></span>  

## <a name="literal-assignments"></a><span data-ttu-id="f72bd-107">リテラル代入</span><span class="sxs-lookup"><span data-stu-id="f72bd-107">Literal assignments</span></span>

<span data-ttu-id="f72bd-108">変数を`UShort`宣言して初期化するには、10 進リテラル、16 進リテラル、8 進数リテラル、または (Visual Basic 2017 以降) バイナリ リテラルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f72bd-108">You can declare and initialize a `UShort` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="f72bd-109">整数リテラルが `UShort` の範囲外にある場合 (つまり、<xref:System.UInt16.MinValue?displayProperty=nameWithType> より小さいか、<xref:System.UInt16.MaxValue?displayProperty=nameWithType> より大きい場合)、コンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="f72bd-109">If the integer literal is outside the range of `UShort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="f72bd-110">次の例では、10 進数、16 進数、およびバイナリ リテラルとして表される 65,034 に`UShort`等しい整数が値に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f72bd-110">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are assigned to `UShort` values.</span></span>
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> <span data-ttu-id="f72bd-111">プレフィックス`&h`を使用`&H`するか、16 進リテラル、プレフィックス`&b`、または`&B`バイナリ リテラルを表す場合、およびプレフィックス`&o`を`&O`表すか、8 進数リテラルを表します。</span><span class="sxs-lookup"><span data-stu-id="f72bd-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="f72bd-112">10 進リテラルには、プレフィックスはありません。</span><span class="sxs-lookup"><span data-stu-id="f72bd-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="f72bd-113">Visual Basic 2017 以降では、`_`下線付きの文字を桁区切り記号として使用して読みやすさを向上させることもできます。</span><span class="sxs-lookup"><span data-stu-id="f72bd-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

<span data-ttu-id="f72bd-114">Visual Basic 15.5 以降では、接頭辞と`_`16 進数、2 進数、または 8 進数の間の先頭の区切り記号としてアンダースコア文字 ( ) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f72bd-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="f72bd-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f72bd-115">For example:</span></span>

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="f72bd-116">次の例に示すように、`US`数値`us`リテラルには`UShort`、データ型を示す[or 型文字](../../programming-guide/language-features/data-types/type-characters.md)を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="f72bd-116">Numeric literals can also include the `US` or `us` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UShort` data type, as the following example shows.</span></span>

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a><span data-ttu-id="f72bd-117">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="f72bd-117">Programming tips</span></span>
  
- <span data-ttu-id="f72bd-118">**負の数。**</span><span class="sxs-lookup"><span data-stu-id="f72bd-118">**Negative Numbers.**</span></span> <span data-ttu-id="f72bd-119">符号`UShort`なしの型であるため、負の数を表すことはできません。</span><span class="sxs-lookup"><span data-stu-id="f72bd-119">Because `UShort` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="f72bd-120">型`-``UShort`と評価される式に単項マイナス ( ) 演算子を使用すると、その式が最初に`Integer`変換されます。</span><span class="sxs-lookup"><span data-stu-id="f72bd-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `UShort`, Visual Basic converts the expression to `Integer` first.</span></span>  
  
- <span data-ttu-id="f72bd-121">**CLS コンプライアンス。**</span><span class="sxs-lookup"><span data-stu-id="f72bd-121">**CLS Compliance.**</span></span> <span data-ttu-id="f72bd-122">データ`UShort`型は[共通言語仕様](https://www.ecma-international.org/publications/standards/Ecma-335.htm)(CLS) の一部ではないため、CLS 準拠のコードで使用するコンポーネントを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f72bd-122">The `UShort` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
- <span data-ttu-id="f72bd-123">**拡大。**</span><span class="sxs-lookup"><span data-stu-id="f72bd-123">**Widening.**</span></span> <span data-ttu-id="f72bd-124">データ`UShort`型は`Integer`、 、 `UInteger`、 `Long` `ULong`、 `Decimal` `Single`、 `Double`、 、 、 、 にまで広がります。</span><span class="sxs-lookup"><span data-stu-id="f72bd-124">The `UShort` data type widens to `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="f72bd-125">つまり、<xref:System.OverflowException?displayProperty=nameWithType>エラーが発生`UShort`することなく、これらの型に変換できます。</span><span class="sxs-lookup"><span data-stu-id="f72bd-125">This means you can convert `UShort` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="f72bd-126">**文字を入力します。**</span><span class="sxs-lookup"><span data-stu-id="f72bd-126">**Type Characters.**</span></span> <span data-ttu-id="f72bd-127">リテラルにリテラルの型文字`US`を追加すると、データ型に`UShort`強制的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="f72bd-127">Appending the literal type characters `US` to a literal forces it to the `UShort` data type.</span></span> <span data-ttu-id="f72bd-128">`UShort`識別子の種類の文字がありません。</span><span class="sxs-lookup"><span data-stu-id="f72bd-128">`UShort` has no identifier type character.</span></span>  
  
- <span data-ttu-id="f72bd-129">**Framework のデータ型**</span><span class="sxs-lookup"><span data-stu-id="f72bd-129">**Framework Type.**</span></span> <span data-ttu-id="f72bd-130">.NET Framework において対応する型は、<xref:System.UInt16?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="f72bd-130">The corresponding type in the .NET Framework is the <xref:System.UInt16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f72bd-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="f72bd-131">See also</span></span>

- <xref:System.UInt16>
- [<span data-ttu-id="f72bd-132">データ型</span><span class="sxs-lookup"><span data-stu-id="f72bd-132">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="f72bd-133">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="f72bd-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="f72bd-134">変換の概要</span><span class="sxs-lookup"><span data-stu-id="f72bd-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="f72bd-135">方法 : 符号なしの型を使用する Windows の機能を呼び出す</span><span class="sxs-lookup"><span data-stu-id="f72bd-135">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="f72bd-136">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="f72bd-136">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
