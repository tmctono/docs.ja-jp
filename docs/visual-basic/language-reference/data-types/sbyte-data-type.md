---
title: SByte 型
ms.date: 04/20/2017
f1_keywords:
- vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
ms.openlocfilehash: 01a0a4a261213d7e6e2016bf49128092e5b22308
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401383"
---
# <a name="sbyte-data-type-visual-basic"></a><span data-ttu-id="2983c-102">SByte データ型</span><span class="sxs-lookup"><span data-stu-id="2983c-102">SByte data type (Visual Basic)</span></span>

<span data-ttu-id="2983c-103">-128 から 127 までの範囲の符号付き 8 ビット (1 バイト) 整数を保持します。</span><span class="sxs-lookup"><span data-stu-id="2983c-103">Holds signed 8-bit (1-byte) integers that range in value from -128 through 127.</span></span>

## <a name="remarks"></a><span data-ttu-id="2983c-104">解説</span><span class="sxs-lookup"><span data-stu-id="2983c-104">Remarks</span></span>

<span data-ttu-id="2983c-105">データ型`SByte`を使用して、データの幅全体を必要としない整数値、または`Integer`の半分のデータ幅を`Short`含めるには、 を使用します。</span><span class="sxs-lookup"><span data-stu-id="2983c-105">Use the `SByte` data type to contain integer values that do not require the full data width of `Integer` or even the half data width of `Short`.</span></span> <span data-ttu-id="2983c-106">場合によっては、共通言語ランタイムが変数を密接にパックし、メモリ`SByte`消費量を節約できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2983c-106">In some cases, the common language runtime might be able to pack your `SByte` variables closely together and save memory consumption.</span></span>

<span data-ttu-id="2983c-107">`SByte` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="2983c-107">The default value of `SByte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="2983c-108">リテラル代入</span><span class="sxs-lookup"><span data-stu-id="2983c-108">Literal assignments</span></span>

<span data-ttu-id="2983c-109">変数を`SByte`宣言して初期化するには、10 進リテラル、16 進リテラル、8 進数リテラル、または (Visual Basic 2017 以降) バイナリ リテラルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2983c-109">You can declare and initialize an `SByte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span>

<span data-ttu-id="2983c-110">次の例では、10 進数、16 進数、およびバイナリ リテラルとして表される -102 に`SByte`等しい整数が値に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2983c-110">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are assigned to `SByte` values.</span></span> <span data-ttu-id="2983c-111">この例では、コンパイラ スイッチを`/removeintchecks`使用してコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2983c-111">This example requires that you compile with the `/removeintchecks` compiler switch.</span></span>

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> <span data-ttu-id="2983c-112">プレフィックス`&h`を使用`&H`するか、16 進リテラル、プレフィックス`&b`、または`&B`バイナリ リテラルを表す場合、およびプレフィックス`&o`を`&O`表すか、8 進数リテラルを表します。</span><span class="sxs-lookup"><span data-stu-id="2983c-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="2983c-113">10 進リテラルには、プレフィックスはありません。</span><span class="sxs-lookup"><span data-stu-id="2983c-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="2983c-114">Visual Basic 2017 以降では、`_`下線付きの文字を桁区切り記号として使用して読みやすさを向上させることもできます。</span><span class="sxs-lookup"><span data-stu-id="2983c-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

<span data-ttu-id="2983c-115">Visual Basic 15.5 以降では、接頭辞と`_`16 進数、2 進数、または 8 進数の間の先頭の区切り記号としてアンダースコア文字 ( ) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="2983c-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="2983c-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2983c-116">For example:</span></span>

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="2983c-117">整数リテラルが `SByte` の範囲外にある場合 (つまり、<xref:System.SByte.MinValue?displayProperty=nameWithType> より小さいか、<xref:System.SByte.MaxValue?displayProperty=nameWithType> より大きい場合)、コンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="2983c-117">If the integer literal is outside the range of `SByte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="2983c-118">整数リテラルにサフィックスがない場合、[整数](integer-data-type.md)は推論されます。</span><span class="sxs-lookup"><span data-stu-id="2983c-118">When an integer literal has no suffix, an [Integer](integer-data-type.md) is inferred.</span></span> <span data-ttu-id="2983c-119">整数リテラルが`Integer`型の範囲外の場合は、[長整数](long-data-type.md)型が推論されます。</span><span class="sxs-lookup"><span data-stu-id="2983c-119">If the integer literal is outside the range of the `Integer` type, a [Long](long-data-type.md) is inferred.</span></span> <span data-ttu-id="2983c-120">つまり、前の例では、数値リテラル`0x9A`と`0b10011010`、値が 156 の 32 ビット符号付き整数として解釈されます。 <xref:System.SByte.MaxValue?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="2983c-120">This means that, in the previous examples, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2983c-121">このようなコードを正常にコンパイルして、10 進以外の整数を`SByte`に割り当てるには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2983c-121">To successfully compile code like this that assigns a non-decimal integer to an `SByte`, you can do either of the following:</span></span>

- <span data-ttu-id="2983c-122">コンパイラ スイッチを使用してコンパイルすることにより、整数`/removeintchecks`の境界チェックを無効にします。</span><span class="sxs-lookup"><span data-stu-id="2983c-122">Disable integer bounds checks by compiling with the `/removeintchecks` compiler switch.</span></span>

- <span data-ttu-id="2983c-123">[型文字](../../programming-guide/language-features/data-types/type-characters.md)を使用して、に割り当てるリテラル値を明示的に定義します`SByte`。</span><span class="sxs-lookup"><span data-stu-id="2983c-123">Use a [type character](../../programming-guide/language-features/data-types/type-characters.md) to explicitly define the literal value that you want to assign to the `SByte`.</span></span> <span data-ttu-id="2983c-124">次の例では、負のリテラル`Short`値をに`SByte`代入します。</span><span class="sxs-lookup"><span data-stu-id="2983c-124">The following example assigns a negative literal `Short` value to an `SByte`.</span></span> <span data-ttu-id="2983c-125">負の数の場合は、数値リテラルの上位ワードの上位ビットを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2983c-125">Note that, for negative numbers, the high-order bit of the high-order word of the numeric literal must be set.</span></span> <span data-ttu-id="2983c-126">この例の場合、これはリテラル`Short`値のビット 15 です。</span><span class="sxs-lookup"><span data-stu-id="2983c-126">In the case of our example, this is bit 15 of the literal `Short` value.</span></span>

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a><span data-ttu-id="2983c-127">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="2983c-127">Programming tips</span></span>

- <span data-ttu-id="2983c-128">**CLS コンプライアンス。**</span><span class="sxs-lookup"><span data-stu-id="2983c-128">**CLS Compliance.**</span></span> <span data-ttu-id="2983c-129">データ`SByte`型は[共通言語仕様](https://www.ecma-international.org/publications/standards/Ecma-335.htm)(CLS) の一部ではないため、CLS 準拠のコードで使用するコンポーネントを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="2983c-129">The `SByte` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="2983c-130">**拡大。**</span><span class="sxs-lookup"><span data-stu-id="2983c-130">**Widening.**</span></span> <span data-ttu-id="2983c-131">データ`SByte`型は`Short`、 、 `Integer`、 `Long` `Decimal`、 `Single`、 `Double`、 、 、 にまで広がります。</span><span class="sxs-lookup"><span data-stu-id="2983c-131">The `SByte` data type widens to `Short`, `Integer`, `Long`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="2983c-132">つまり、<xref:System.OverflowException?displayProperty=nameWithType>エラーが発生`SByte`することなく、これらの型に変換できます。</span><span class="sxs-lookup"><span data-stu-id="2983c-132">This means you can convert `SByte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="2983c-133">**文字を入力します。**</span><span class="sxs-lookup"><span data-stu-id="2983c-133">**Type Characters.**</span></span> <span data-ttu-id="2983c-134">`SByte`リテラル型文字または識別子型文字がありません。</span><span class="sxs-lookup"><span data-stu-id="2983c-134">`SByte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="2983c-135">**Framework のデータ型**</span><span class="sxs-lookup"><span data-stu-id="2983c-135">**Framework Type.**</span></span> <span data-ttu-id="2983c-136">.NET Framework において対応する型は、<xref:System.SByte?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="2983c-136">The corresponding type in the .NET Framework is the <xref:System.SByte?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="2983c-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="2983c-137">See also</span></span>

- <xref:System.SByte?displayProperty=nameWithType>
- [<span data-ttu-id="2983c-138">データ型</span><span class="sxs-lookup"><span data-stu-id="2983c-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="2983c-139">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="2983c-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="2983c-140">変換の概要</span><span class="sxs-lookup"><span data-stu-id="2983c-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="2983c-141">Short データ型</span><span class="sxs-lookup"><span data-stu-id="2983c-141">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [<span data-ttu-id="2983c-142">整数データ型</span><span class="sxs-lookup"><span data-stu-id="2983c-142">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="2983c-143">Long データ型</span><span class="sxs-lookup"><span data-stu-id="2983c-143">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [<span data-ttu-id="2983c-144">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="2983c-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
