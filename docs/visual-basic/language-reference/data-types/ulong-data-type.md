---
title: ULong データ型
ms.date: 01/31/2018
f1_keywords:
- vb.ulong
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- literal type characters [Visual Basic], UL
- ULong data type
- UL literal type characters [Visual Basic]
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
ms.openlocfilehash: 3c6cd4086e08b808c158948756b4806f098196b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401317"
---
# <a name="ulong-data-type-visual-basic"></a><span data-ttu-id="a7fd4-102">ULong データ型</span><span class="sxs-lookup"><span data-stu-id="a7fd4-102">ULong data type (Visual Basic)</span></span>

<span data-ttu-id="a7fd4-103">0 から 18,446,744,073,709,551,615 (1.84 倍以上 10 ^ 19) の範囲の符号なし 64 ビット (8 バイト) 整数を保持します。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-103">Holds unsigned 64-bit (8-byte) integers ranging in value from 0 through 18,446,744,073,709,551,615 (more than 1.84 times 10 ^ 19).</span></span>

## <a name="remarks"></a><span data-ttu-id="a7fd4-104">解説</span><span class="sxs-lookup"><span data-stu-id="a7fd4-104">Remarks</span></span>

<span data-ttu-id="a7fd4-105">データ型`ULong`を使用して、バイナリ データが大`UInteger`きすぎて に対しては大きすぎたか、または最大の符号なし整数値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-105">Use the `ULong` data type to contain binary data too large for `UInteger`, or the largest possible unsigned integer values.</span></span>

<span data-ttu-id="a7fd4-106">`ULong` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-106">The default value of `ULong` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="a7fd4-107">リテラル代入</span><span class="sxs-lookup"><span data-stu-id="a7fd4-107">Literal assignments</span></span>

<span data-ttu-id="a7fd4-108">変数を`ULong`宣言して初期化するには、10 進リテラル、16 進リテラル、8 進数リテラル、または (Visual Basic 2017 以降) バイナリ リテラルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-108">You can declare and initialize a `ULong` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="a7fd4-109">整数リテラルが `ULong` の範囲外にある場合 (つまり、<xref:System.UInt64.MinValue?displayProperty=nameWithType> より小さいか、<xref:System.UInt64.MaxValue?displayProperty=nameWithType> より大きい場合)、コンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-109">If the integer literal is outside the range of `ULong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="a7fd4-110">次の例では、整数 7,934,076,125 を 10 進リテラル、16 進リテラル、バイナリ リテラルで表したものが、`ULong` 値に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-110">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ULong` values.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> <span data-ttu-id="a7fd4-111">プレフィックス`&h`を使用`&H`するか、16 進リテラル、プレフィックス`&b`、または`&B`バイナリ リテラルを表す場合、およびプレフィックス`&o`を`&O`表すか、8 進数リテラルを表します。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="a7fd4-112">10 進リテラルには、プレフィックスはありません。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="a7fd4-113">Visual Basic 2017 以降では、`_`下線付きの文字を桁区切り記号として使用して読みやすさを向上させることもできます。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="a7fd4-114">Visual Basic 15.5 以降では、接頭辞と`_`16 進数、2 進数、または 8 進数の間の先頭の区切り記号としてアンダースコア文字 ( ) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="a7fd4-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-115">For example:</span></span>

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="a7fd4-116">次の例に示すように、`UL`数値`ul`リテラルには`ULong`、データ型を示す[or 型文字](../../programming-guide/language-features/data-types/type-characters.md)を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-116">Numeric literals can also include the `UL` or `ul` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `ULong` data type, as the following example shows.</span></span>

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a><span data-ttu-id="a7fd4-117">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="a7fd4-117">Programming tips</span></span>

- <span data-ttu-id="a7fd4-118">**負の数。**</span><span class="sxs-lookup"><span data-stu-id="a7fd4-118">**Negative Numbers.**</span></span> <span data-ttu-id="a7fd4-119">符号`ULong`なしの型であるため、負の数を表すことはできません。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-119">Because `ULong` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="a7fd4-120">型`-``ULong`と評価される式に単項マイナス ( ) 演算子を使用すると、その式が最初に`Decimal`変換されます。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `ULong`, Visual Basic converts the expression to `Decimal` first.</span></span>

- <span data-ttu-id="a7fd4-121">**CLS コンプライアンス。**</span><span class="sxs-lookup"><span data-stu-id="a7fd4-121">**CLS Compliance.**</span></span> <span data-ttu-id="a7fd4-122">データ`ULong`型は[共通言語仕様](https://www.ecma-international.org/publications/standards/Ecma-335.htm)(CLS) の一部ではないため、CLS 準拠のコードで使用するコンポーネントを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-122">The `ULong` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="a7fd4-123">**相互運用の考慮事項。**</span><span class="sxs-lookup"><span data-stu-id="a7fd4-123">**Interop Considerations.**</span></span> <span data-ttu-id="a7fd4-124">オートメーション オブジェクトや COM オブジェクトなど、.NET Framework 用に作成されていないコンポーネントとインターフェイスを使用している場合は、他`ulong`の環境ではデータ幅 (32 ビット) が異なる型が使用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-124">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `ulong` can have a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="a7fd4-125">このようなコンポーネントに 32 ビットの引数を渡す場合は、マネージ`UInteger`Visual `ULong` Basic コードではなく、それを宣言します。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-125">If you are passing a 32-bit argument to such a component, declare it as `UInteger` instead of `ULong` in your managed Visual Basic code.</span></span>

  <span data-ttu-id="a7fd4-126">さらに、オートメーションは、Windows 95、Windows 98、Windows ME、または Windows 2000 では 64 ビットの整数をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-126">Furthermore, Automation does not support 64-bit integers on Windows 95, Windows 98, Windows ME, or Windows 2000.</span></span> <span data-ttu-id="a7fd4-127">これらのプラットフォームでは、Visual `ULong` Basic の引数をオートメーション コンポーネントに渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-127">You cannot pass a Visual Basic `ULong` argument to an Automation component on these platforms.</span></span>

- <span data-ttu-id="a7fd4-128">**拡大。**</span><span class="sxs-lookup"><span data-stu-id="a7fd4-128">**Widening.**</span></span> <span data-ttu-id="a7fd4-129">データ`ULong`型は`Decimal`、 、 `Single`、 `Double`、 、 に拡大されます。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-129">The `ULong` data type widens to `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="a7fd4-130">つまり、<xref:System.OverflowException?displayProperty=nameWithType>エラーが発生`ULong`することなく、これらの型に変換できます。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-130">This means you can convert `ULong` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="a7fd4-131">**文字を入力します。**</span><span class="sxs-lookup"><span data-stu-id="a7fd4-131">**Type Characters.**</span></span> <span data-ttu-id="a7fd4-132">リテラルにリテラルの型文字`UL`を追加すると、データ型に`ULong`強制的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-132">Appending the literal type characters `UL` to a literal forces it to the `ULong` data type.</span></span> <span data-ttu-id="a7fd4-133">`ULong`識別子の種類の文字がありません。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-133">`ULong` has no identifier type character.</span></span>

- <span data-ttu-id="a7fd4-134">**Framework のデータ型**</span><span class="sxs-lookup"><span data-stu-id="a7fd4-134">**Framework Type.**</span></span> <span data-ttu-id="a7fd4-135">.NET Framework において対応する型は、<xref:System.UInt64?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="a7fd4-135">The corresponding type in the .NET Framework is the <xref:System.UInt64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7fd4-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7fd4-136">See also</span></span>

- <xref:System.UInt64>
- [<span data-ttu-id="a7fd4-137">データ型</span><span class="sxs-lookup"><span data-stu-id="a7fd4-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="a7fd4-138">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="a7fd4-138">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="a7fd4-139">変換の概要</span><span class="sxs-lookup"><span data-stu-id="a7fd4-139">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="a7fd4-140">方法 : 符号なしの型を使用する Windows の機能を呼び出す</span><span class="sxs-lookup"><span data-stu-id="a7fd4-140">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="a7fd4-141">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="a7fd4-141">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
