---
title: ULong 型 (Visual Basic)
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
ms.openlocfilehash: 19a75f056436b858a22588d7ac5f37df5dd326f2
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583111"
---
# <a name="ulong-data-type-visual-basic"></a><span data-ttu-id="70637-102">ULong データ型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70637-102">ULong data type (Visual Basic)</span></span>

<span data-ttu-id="70637-103">0 ~ 18446744073709551615 (1.84 倍以上 10 ^ 19) の値の範囲内で、符号なし64ビット (8 バイト) の整数を保持します。</span><span class="sxs-lookup"><span data-stu-id="70637-103">Holds unsigned 64-bit (8-byte) integers ranging in value from 0 through 18,446,744,073,709,551,615 (more than 1.84 times 10 ^ 19).</span></span>

## <a name="remarks"></a><span data-ttu-id="70637-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="70637-104">Remarks</span></span>

<span data-ttu-id="70637-105">@No__t_0 データ型を使用して、`UInteger` に対して大きすぎるバイナリデータや、可能性のある最大の符号なし整数値を格納します。</span><span class="sxs-lookup"><span data-stu-id="70637-105">Use the `ULong` data type to contain binary data too large for `UInteger`, or the largest possible unsigned integer values.</span></span>

<span data-ttu-id="70637-106">`ULong` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="70637-106">The default value of `ULong` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="70637-107">リテラルの代入</span><span class="sxs-lookup"><span data-stu-id="70637-107">Literal assignments</span></span>

<span data-ttu-id="70637-108">@No__t_0 変数は、10進リテラル、16進リテラル、8進数リテラル、または (Visual Basic 2017 で始まる) バイナリリテラルを割り当てることによって、宣言および初期化できます。</span><span class="sxs-lookup"><span data-stu-id="70637-108">You can declare and initialize a `ULong` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="70637-109">整数リテラルが `ULong` の範囲外にある場合 (つまり、<xref:System.UInt64.MinValue?displayProperty=nameWithType> より小さいか、<xref:System.UInt64.MaxValue?displayProperty=nameWithType> より大きい場合)、コンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="70637-109">If the integer literal is outside the range of `ULong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="70637-110">次の例では、整数 7,934,076,125 を 10 進リテラル、16 進リテラル、バイナリ リテラルで表したものが、`ULong` 値に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="70637-110">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ULong` values.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> <span data-ttu-id="70637-111">プレフィックス `&h` または `&H` を使用して、16進リテラル、プレフィックス `&b` または `&B` がバイナリリテラルを示すようにし、プレフィックス `&o` または `&O` を使用して8進数リテラルを表します。</span><span class="sxs-lookup"><span data-stu-id="70637-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="70637-112">10 進リテラルには、プレフィックスはありません。</span><span class="sxs-lookup"><span data-stu-id="70637-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="70637-113">Visual Basic 2017 以降では、次の例に示すように、アンダースコア文字 (`_`) を桁区切り記号として使用して、読みやすくすることもできます。</span><span class="sxs-lookup"><span data-stu-id="70637-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="70637-114">Visual Basic 15.5 以降では、アンダースコア文字 (`_`) をプレフィックスと16進数、バイナリ、または8進数の間の先頭の区切り記号として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="70637-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="70637-115">(例:</span><span class="sxs-lookup"><span data-stu-id="70637-115">For example:</span></span>

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="70637-116">数値リテラルには、次の例に示すように、`ULong` データ型を示す `UL` または `ul`[型の文字](../../programming-guide/language-features/data-types/type-characters.md)を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="70637-116">Numeric literals can also include the `UL` or `ul` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `ULong` data type, as the following example shows.</span></span>

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a><span data-ttu-id="70637-117">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="70637-117">Programming tips</span></span>

- <span data-ttu-id="70637-118">**負の数値。**</span><span class="sxs-lookup"><span data-stu-id="70637-118">**Negative Numbers.**</span></span> <span data-ttu-id="70637-119">@No__t_0 は符号なしの型であるため、負の数を表すことはできません。</span><span class="sxs-lookup"><span data-stu-id="70637-119">Because `ULong` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="70637-120">@No__t_1 型に評価される式に対して単項マイナス記号 (`-`) 演算子を使用すると、Visual Basic 式が最初に `Decimal` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="70637-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `ULong`, Visual Basic converts the expression to `Decimal` first.</span></span>

- <span data-ttu-id="70637-121">**CLS 準拠。**</span><span class="sxs-lookup"><span data-stu-id="70637-121">**CLS Compliance.**</span></span> <span data-ttu-id="70637-122">@No__t_0 のデータ型は[共通言語仕様](https://www.ecma-international.org/publications/standards/Ecma-335.htm)(cls) の一部ではないため、cls 準拠のコードはそれを使用するコンポーネントを使用できません。</span><span class="sxs-lookup"><span data-stu-id="70637-122">The `ULong` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="70637-123">**相互運用に関する考慮事項。**</span><span class="sxs-lookup"><span data-stu-id="70637-123">**Interop Considerations.**</span></span> <span data-ttu-id="70637-124">.NET Framework 用に作成されていないコンポーネント (オートメーションや COM オブジェクトなど) とやり取りしている場合は、`ulong` などの型が他の環境で異なるデータ幅 (32 ビット) を持つ可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="70637-124">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `ulong` can have a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="70637-125">このようなコンポーネントに32ビットの引数を渡す場合は、マネージ Visual Basic コードで `ULong` の代わりに `UInteger` として宣言します。</span><span class="sxs-lookup"><span data-stu-id="70637-125">If you are passing a 32-bit argument to such a component, declare it as `UInteger` instead of `ULong` in your managed Visual Basic code.</span></span>

  <span data-ttu-id="70637-126">さらに、オートメーションでは、Windows 95、Windows 98、Windows ME、または Windows 2000 で64ビットの整数はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="70637-126">Furthermore, Automation does not support 64-bit integers on Windows 95, Windows 98, Windows ME, or Windows 2000.</span></span> <span data-ttu-id="70637-127">これらのプラットフォームのオートメーションコンポーネントに Visual Basic `ULong` 引数を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="70637-127">You cannot pass a Visual Basic `ULong` argument to an Automation component on these platforms.</span></span>

- <span data-ttu-id="70637-128">**広げ.**</span><span class="sxs-lookup"><span data-stu-id="70637-128">**Widening.**</span></span> <span data-ttu-id="70637-129">@No__t_0 のデータ型は、`Decimal`、`Single`、および `Double` に拡大変換されます。</span><span class="sxs-lookup"><span data-stu-id="70637-129">The `ULong` data type widens to `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="70637-130">つまり、<xref:System.OverflowException?displayProperty=nameWithType> エラーが発生することなく、`ULong` をこれらの型のいずれかに変換できます。</span><span class="sxs-lookup"><span data-stu-id="70637-130">This means you can convert `ULong` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="70637-131">**文字を入力します。**</span><span class="sxs-lookup"><span data-stu-id="70637-131">**Type Characters.**</span></span> <span data-ttu-id="70637-132">リテラルに `UL` リテラル型文字を追加すると、`ULong` データ型に強制されます。</span><span class="sxs-lookup"><span data-stu-id="70637-132">Appending the literal type characters `UL` to a literal forces it to the `ULong` data type.</span></span> <span data-ttu-id="70637-133">`ULong` に識別子の型文字がありません。</span><span class="sxs-lookup"><span data-stu-id="70637-133">`ULong` has no identifier type character.</span></span>

- <span data-ttu-id="70637-134">**フレームワークの種類。**</span><span class="sxs-lookup"><span data-stu-id="70637-134">**Framework Type.**</span></span> <span data-ttu-id="70637-135">.NET Framework において対応する型は、<xref:System.UInt64?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="70637-135">The corresponding type in the .NET Framework is the <xref:System.UInt64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="70637-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="70637-136">See also</span></span>

- <xref:System.UInt64>
- [<span data-ttu-id="70637-137">データの種類</span><span class="sxs-lookup"><span data-stu-id="70637-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="70637-138">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="70637-138">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="70637-139">変換の概要</span><span class="sxs-lookup"><span data-stu-id="70637-139">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="70637-140">方法 : 符号なしの型を使用する Windows の機能を呼び出す</span><span class="sxs-lookup"><span data-stu-id="70637-140">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="70637-141">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="70637-141">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
