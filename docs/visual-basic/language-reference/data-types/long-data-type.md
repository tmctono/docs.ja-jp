---
title: Long 型
ms.date: 01/31/2018
f1_keywords:
- vb.Long
helpviewer_keywords:
- identifier type characters [Visual Basic], &
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- '& identifier type character'
- integer numbers
- literal type characters [Visual Basic], L
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- L literal type character [Visual Basic]
- integers [Visual Basic], types
- Long keyword [Visual Basic]
- data types [Visual Basic], integral
- data types [Visual Basic], assigning
- Long data type
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
ms.openlocfilehash: 16d7409c802e97b1f33474d810134db4d9f0ad6c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343972"
---
# <a name="long-data-type-visual-basic"></a><span data-ttu-id="8cd81-102">Long データ型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8cd81-102">Long data type (Visual Basic)</span></span>

<span data-ttu-id="8cd81-103">-9223372036854775808 ~ 9223372036854775807 (9.2... E + 18) の値の範囲内で、64ビット (8 バイト) の符号付き整数を保持します。</span><span class="sxs-lookup"><span data-stu-id="8cd81-103">Holds signed 64-bit (8-byte) integers ranging in value from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807 (9.2...E+18).</span></span>

## <a name="remarks"></a><span data-ttu-id="8cd81-104">コメント</span><span class="sxs-lookup"><span data-stu-id="8cd81-104">Remarks</span></span>

<span data-ttu-id="8cd81-105">`Long` データ型を使用して、`Integer` データ型には大きすぎる整数値を格納します。</span><span class="sxs-lookup"><span data-stu-id="8cd81-105">Use the `Long` data type to contain integer numbers that are too large to fit in the `Integer` data type.</span></span>

<span data-ttu-id="8cd81-106">`Long` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="8cd81-106">The default value of `Long` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="8cd81-107">リテラルの代入</span><span class="sxs-lookup"><span data-stu-id="8cd81-107">Literal assignments</span></span>

<span data-ttu-id="8cd81-108">`Long` 変数は、10進リテラル、16進リテラル、8進数リテラル、または (Visual Basic 2017 で始まる) バイナリリテラルを割り当てることによって、宣言および初期化できます。</span><span class="sxs-lookup"><span data-stu-id="8cd81-108">You can declare and initialize a `Long` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="8cd81-109">整数リテラルが `Long` の範囲外にある場合 (つまり、<xref:System.Int64.MinValue?displayProperty=nameWithType> より小さいか、<xref:System.Int64.MaxValue?displayProperty=nameWithType> より大きい場合)、コンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="8cd81-109">If the integer literal is outside the range of `Long` (that is, if it is less than <xref:System.Int64.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="8cd81-110">次の例では、整数 4,294,967,296 を 10 進リテラル、16 進リテラル、バイナリ リテラルで表したものが、`Long` 値に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="8cd81-110">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `Long` values.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]

> [!NOTE]
> <span data-ttu-id="8cd81-111">プレフィックス `&h` または `&H` を使用して、16進リテラル、プレフィックス `&b` または `&B` がバイナリリテラルを示すようにし、プレフィックス `&o` または `&O` を使用して8進数リテラルを表します。</span><span class="sxs-lookup"><span data-stu-id="8cd81-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="8cd81-112">10 進リテラルには、プレフィックスはありません。</span><span class="sxs-lookup"><span data-stu-id="8cd81-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="8cd81-113">Visual Basic 2017 以降では、次の例に示すように、アンダースコア文字 (`_`) を桁区切り記号として使用して、読みやすくすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8cd81-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="8cd81-114">Visual Basic 15.5 以降では、アンダースコア文字 (`_`) をプレフィックスと16進数、バイナリ、または8進数の間の先頭の区切り記号として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8cd81-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="8cd81-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8cd81-115">For example:</span></span>

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="8cd81-116">数値リテラルには、次の例に示すように、`Long` データ型を示す `L`[型文字](../../programming-guide/language-features/data-types/type-characters.md)を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="8cd81-116">Numeric literals can also include the `L` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Long` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a><span data-ttu-id="8cd81-117">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="8cd81-117">Programming tips</span></span>

- <span data-ttu-id="8cd81-118">**相互運用に関する考慮事項。**</span><span class="sxs-lookup"><span data-stu-id="8cd81-118">**Interop Considerations.**</span></span> <span data-ttu-id="8cd81-119">.NET Framework 用に作成されていないコンポーネント (たとえば、オートメーションや COM オブジェクト) とやり取りする場合は、他の環境で `Long` が異なるデータ幅 (32 ビット) を持っていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8cd81-119">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that `Long` has a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="8cd81-120">このようなコンポーネントに32ビットの引数を渡す場合は、新しい Visual Basic コードで `Long` の代わりに `Integer` として宣言します。</span><span class="sxs-lookup"><span data-stu-id="8cd81-120">If you are passing a 32-bit argument to such a component, declare it as `Integer` instead of `Long` in your new Visual Basic code.</span></span>

- <span data-ttu-id="8cd81-121">**広げ.**</span><span class="sxs-lookup"><span data-stu-id="8cd81-121">**Widening.**</span></span> <span data-ttu-id="8cd81-122">`Long` のデータ型は、`Decimal`、`Single`、または `Double`に拡大変換されます。</span><span class="sxs-lookup"><span data-stu-id="8cd81-122">The `Long` data type widens to `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="8cd81-123">これは、`Long` エラーを発生させることなく、これらの型のいずれかに <xref:System.OverflowException?displayProperty=nameWithType> を変換できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8cd81-123">This means you can convert `Long` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="8cd81-124">**文字を入力します。**</span><span class="sxs-lookup"><span data-stu-id="8cd81-124">**Type Characters.**</span></span> <span data-ttu-id="8cd81-125">あるリテラルにリテラルの型文字 `L` を付けると、そのリテラルは `Long` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="8cd81-125">Appending the literal type character `L` to a literal forces it to the `Long` data type.</span></span> <span data-ttu-id="8cd81-126">ある識別子に識別子の型文字 `&` を付けると、その識別子は整数型 (`Long`) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="8cd81-126">Appending the identifier type character `&` to any identifier forces it to `Long`.</span></span>

- <span data-ttu-id="8cd81-127">**フレームワークの種類。**</span><span class="sxs-lookup"><span data-stu-id="8cd81-127">**Framework Type.**</span></span> <span data-ttu-id="8cd81-128">.NET Framework において対応する型は、<xref:System.Int64?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="8cd81-128">The corresponding type in the .NET Framework is the <xref:System.Int64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="8cd81-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="8cd81-129">See also</span></span>

- <xref:System.Int64>
- [<span data-ttu-id="8cd81-130">データの種類</span><span class="sxs-lookup"><span data-stu-id="8cd81-130">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="8cd81-131">Integer データ型</span><span class="sxs-lookup"><span data-stu-id="8cd81-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="8cd81-132">Short データ型</span><span class="sxs-lookup"><span data-stu-id="8cd81-132">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [<span data-ttu-id="8cd81-133">CString</span><span class="sxs-lookup"><span data-stu-id="8cd81-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="8cd81-134">変換の概要</span><span class="sxs-lookup"><span data-stu-id="8cd81-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="8cd81-135">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="8cd81-135">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
