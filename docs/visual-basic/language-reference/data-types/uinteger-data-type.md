---
title: UInteger データ型 (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.uinteger
helpviewer_keywords:
- numbers [Visual Basic], whole
- UInteger data type
- literal type characters [Visual Basic], UI
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- UI literal type characters [Visual Basic]
- data types [Visual Basic], integral
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
ms.openlocfilehash: 1ae0cbd3a518bf863a3c57f50934837a486d2901
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583132"
---
# <a name="uinteger-data-type"></a><span data-ttu-id="b374a-102">UInteger データ型</span><span class="sxs-lookup"><span data-stu-id="b374a-102">UInteger data type</span></span>

<span data-ttu-id="b374a-103">0 ~ 4294967295 の値の範囲内で、符号なし32ビット (4 バイト) の整数を保持します。</span><span class="sxs-lookup"><span data-stu-id="b374a-103">Holds unsigned 32-bit (4-byte) integers ranging in value from 0 through 4,294,967,295.</span></span>

## <a name="remarks"></a><span data-ttu-id="b374a-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="b374a-104">Remarks</span></span>

<span data-ttu-id="b374a-105">@No__t_0 データ型は、最も効率的なデータ幅で最も大きな符号なしの値を提供します。</span><span class="sxs-lookup"><span data-stu-id="b374a-105">The `UInteger` data type provides the largest unsigned value in the most efficient data width.</span></span>

<span data-ttu-id="b374a-106">`UInteger` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="b374a-106">The default value of `UInteger` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="b374a-107">リテラルの代入</span><span class="sxs-lookup"><span data-stu-id="b374a-107">Literal assignments</span></span>

<span data-ttu-id="b374a-108">@No__t_0 変数は、10進リテラル、16進リテラル、8進数リテラル、または (Visual Basic 2017 で始まる) バイナリリテラルを割り当てることによって、宣言および初期化できます。</span><span class="sxs-lookup"><span data-stu-id="b374a-108">You can declare and initialize a `UInteger` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="b374a-109">整数リテラルが `UInteger` の範囲外にある場合 (つまり、<xref:System.UInt32.MinValue?displayProperty=nameWithType> より小さいか、<xref:System.UInt32.MaxValue?displayProperty=nameWithType> より大きい場合)、コンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="b374a-109">If the integer literal is outside the range of `UInteger` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="b374a-110">次の例では、整数 3,000,000,000 を 10 進リテラル、16 進リテラル、バイナリ リテラルで表したものが、`UInteger` 値に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="b374a-110">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `UInteger` values.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]

> [!NOTE]
> <span data-ttu-id="b374a-111">プレフィックス `&h` または `&H` を使用して、16進リテラル、プレフィックス `&b` または `&B` がバイナリリテラルを示すようにし、プレフィックス `&o` または `&O` を使用して8進数リテラルを表します。</span><span class="sxs-lookup"><span data-stu-id="b374a-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="b374a-112">10 進リテラルには、プレフィックスはありません。</span><span class="sxs-lookup"><span data-stu-id="b374a-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="b374a-113">Visual Basic 2017 以降では、次の例に示すように、アンダースコア文字 (`_`) を桁区切り記号として使用して、読みやすくすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b374a-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]

<span data-ttu-id="b374a-114">Visual Basic 15.5 以降では、アンダースコア文字 (`_`) をプレフィックスと16進数、バイナリ、または8進数の間の先頭の区切り記号として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="b374a-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="b374a-115">(例:</span><span class="sxs-lookup"><span data-stu-id="b374a-115">For example:</span></span>

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="b374a-116">数値リテラルには、次の例に示すように、`UInteger` データ型を示す `UI` または `ui`[型の文字](../../programming-guide/language-features/data-types/type-characters.md)を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="b374a-116">Numeric literals can also include the `UI` or `ui` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UInteger` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a><span data-ttu-id="b374a-117">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="b374a-117">Programming tips</span></span>

<span data-ttu-id="b374a-118">@No__t_0 データ型と `Integer` データ型により、32ビットプロセッサで最適なパフォーマンスが得られます。これは、使用するビット数が少ない場合でも、より少ない整数型 (`UShort`、`Short`、`Byte`、および `SByte`) が使用されるためです。、格納、およびフェッチを行います。</span><span class="sxs-lookup"><span data-stu-id="b374a-118">The `UInteger` and `Integer` data types provide optimal performance on a 32-bit processor, because the smaller integer types (`UShort`, `Short`, `Byte`, and `SByte`), even though they use fewer bits, take more time to load, store, and fetch.</span></span>

- <span data-ttu-id="b374a-119">**負の数値。**</span><span class="sxs-lookup"><span data-stu-id="b374a-119">**Negative Numbers.**</span></span> <span data-ttu-id="b374a-120">@No__t_0 は符号なしの型であるため、負の数を表すことはできません。</span><span class="sxs-lookup"><span data-stu-id="b374a-120">Because `UInteger` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="b374a-121">@No__t_1 型に評価される式に対して単項マイナス記号 (`-`) 演算子を使用すると、Visual Basic 式が最初に `Long` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="b374a-121">If you use the unary minus (`-`) operator on an expression that evaluates to type `UInteger`, Visual Basic converts the expression to `Long` first.</span></span>

- <span data-ttu-id="b374a-122">**CLS 準拠。**</span><span class="sxs-lookup"><span data-stu-id="b374a-122">**CLS Compliance.**</span></span> <span data-ttu-id="b374a-123">@No__t_0 のデータ型は[共通言語仕様](https://www.ecma-international.org/publications/standards/Ecma-335.htm)(cls) の一部ではないため、cls 準拠のコードはそれを使用するコンポーネントを使用できません。</span><span class="sxs-lookup"><span data-stu-id="b374a-123">The `UInteger` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="b374a-124">**相互運用に関する考慮事項。**</span><span class="sxs-lookup"><span data-stu-id="b374a-124">**Interop Considerations.**</span></span> <span data-ttu-id="b374a-125">.NET Framework 用に作成されていないコンポーネント (オートメーションや COM オブジェクトなど) とやり取りしている場合は、`uint` などの型が他の環境で異なるデータ幅 (16 ビット) を持つ可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b374a-125">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `uint` can have a different data width (16 bits) in other environments.</span></span> <span data-ttu-id="b374a-126">このようなコンポーネントに16ビットの引数を渡す場合は、マネージ Visual Basic コードで `UInteger` ではなく、`UShort` として宣言します。</span><span class="sxs-lookup"><span data-stu-id="b374a-126">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>

- <span data-ttu-id="b374a-127">**広げ.**</span><span class="sxs-lookup"><span data-stu-id="b374a-127">**Widening.**</span></span> <span data-ttu-id="b374a-128">@No__t_0 のデータ型は、`Long`、`ULong`、`Decimal`、`Single`、および `Double` に拡大変換されます。</span><span class="sxs-lookup"><span data-stu-id="b374a-128">The `UInteger` data type widens to `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="b374a-129">つまり、<xref:System.OverflowException?displayProperty=nameWithType> エラーが発生することなく、`UInteger` をこれらの型のいずれかに変換できます。</span><span class="sxs-lookup"><span data-stu-id="b374a-129">This means you can convert `UInteger` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="b374a-130">**文字を入力します。**</span><span class="sxs-lookup"><span data-stu-id="b374a-130">**Type Characters.**</span></span> <span data-ttu-id="b374a-131">リテラルに `UI` リテラル型文字を追加すると、`UInteger` データ型に強制されます。</span><span class="sxs-lookup"><span data-stu-id="b374a-131">Appending the literal type characters `UI` to a literal forces it to the `UInteger` data type.</span></span> <span data-ttu-id="b374a-132">`UInteger` に識別子の型文字がありません。</span><span class="sxs-lookup"><span data-stu-id="b374a-132">`UInteger` has no identifier type character.</span></span>

- <span data-ttu-id="b374a-133">**フレームワークの種類。**</span><span class="sxs-lookup"><span data-stu-id="b374a-133">**Framework Type.**</span></span> <span data-ttu-id="b374a-134">.NET Framework において対応する型は、<xref:System.UInt32?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="b374a-134">The corresponding type in the .NET Framework is the <xref:System.UInt32?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="b374a-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="b374a-135">See also</span></span>

- <xref:System.UInt32>
- [<span data-ttu-id="b374a-136">データの種類</span><span class="sxs-lookup"><span data-stu-id="b374a-136">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="b374a-137">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="b374a-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="b374a-138">変換の概要</span><span class="sxs-lookup"><span data-stu-id="b374a-138">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="b374a-139">方法 : 符号なしの型を使用する Windows の機能を呼び出す</span><span class="sxs-lookup"><span data-stu-id="b374a-139">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="b374a-140">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="b374a-140">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
