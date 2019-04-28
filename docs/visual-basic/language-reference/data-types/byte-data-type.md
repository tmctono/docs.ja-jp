---
title: バイト型 (Byte) (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 217778a21fb9f231f448436ca5a68c42e5837566
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797008"
---
# <a name="byte-data-type-visual-basic"></a><span data-ttu-id="f66c4-102">Byte データ型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f66c4-102">Byte data type (Visual Basic)</span></span>
<span data-ttu-id="f66c4-103">0 から 255 までの範囲の符号なし 8 ビット (1 バイト) 整数を保持します。</span><span class="sxs-lookup"><span data-stu-id="f66c4-103">Holds unsigned 8-bit (1-byte) integers that range in value from 0 through 255.</span></span>

## <a name="remarks"></a><span data-ttu-id="f66c4-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="f66c4-104">Remarks</span></span>

<span data-ttu-id="f66c4-105">使用して、`Byte`バイナリ データを格納するデータ型。</span><span class="sxs-lookup"><span data-stu-id="f66c4-105">Use the `Byte` data type to contain binary data.</span></span>  
  
<span data-ttu-id="f66c4-106">`Byte` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="f66c4-106">The default value of `Byte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="f66c4-107">リテラルの割り当て</span><span class="sxs-lookup"><span data-stu-id="f66c4-107">Literal assignments</span></span>

<span data-ttu-id="f66c4-108">宣言し、初期化を`Byte`10 進リテラル、16 進リテラル、8 進数のリテラルを割り当てることや (Visual Basic 2017 以降) バイナリ リテラルでは、変数。</span><span class="sxs-lookup"><span data-stu-id="f66c4-108">You can declare and initialize a `Byte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="f66c4-109">整数リテラルの範囲外の場合、 `Byte` (である場合より小さい<xref:System.Byte.MinValue?displayProperty=nameWithType>以上<xref:System.Byte.MaxValue?displayProperty=nameWithType>)、コンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="f66c4-109">If the integral literal is outside the range of a `Byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="f66c4-110">次の例では、整数が 16 進数、10 進数として表される 201 に等しくなりからのバイナリ リテラルを暗黙的に変換されます[整数](integer-data-type.md)に`byte`値。</span><span class="sxs-lookup"><span data-stu-id="f66c4-110">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `byte` values.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> <span data-ttu-id="f66c4-111">プレフィックスを使用する`&h`または`&H`を 16 進リテラル、プレフィックスを示すために`&b`または`&B`、バイナリ リテラル、およびプレフィックスを示すために`&o`または`&O`を 8 進数のリテラルを示すためにします。</span><span class="sxs-lookup"><span data-stu-id="f66c4-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="f66c4-112">10 進リテラルには、プレフィックスはありません。</span><span class="sxs-lookup"><span data-stu-id="f66c4-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="f66c4-113">Visual Basic 2017 から始めて、使用することできますも、アンダー スコア文字`_`、読みやすさを強化するために、桁区切り記号として次の例として示します。</span><span class="sxs-lookup"><span data-stu-id="f66c4-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

<span data-ttu-id="f66c4-114">Visual Basic 15.5 以降では、使用することできますもアンダー スコア文字 (`_`) プレフィックスと 16 進数、バイナリ、または 8 進数の桁の間の先頭の区切り記号として。</span><span class="sxs-lookup"><span data-stu-id="f66c4-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="f66c4-115">例:</span><span class="sxs-lookup"><span data-stu-id="f66c4-115">For example:</span></span>

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a><span data-ttu-id="f66c4-116">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="f66c4-116">Programming tips</span></span>

- <span data-ttu-id="f66c4-117">**負の数。**</span><span class="sxs-lookup"><span data-stu-id="f66c4-117">**Negative Numbers.**</span></span> <span data-ttu-id="f66c4-118">`Byte`符号なしの型は、負の数を表すことはできません。</span><span class="sxs-lookup"><span data-stu-id="f66c4-118">Because `Byte` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="f66c4-119">単項マイナスを使用する場合 (`-`) 型に評価される式で演算子`Byte`、Visual Basic の式を変換する`Short`最初。</span><span class="sxs-lookup"><span data-stu-id="f66c4-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `Byte`, Visual Basic converts the expression to `Short` first.</span></span>
  
- <span data-ttu-id="f66c4-120">**形式の変換。**</span><span class="sxs-lookup"><span data-stu-id="f66c4-120">**Format Conversions.**</span></span> <span data-ttu-id="f66c4-121">Visual Basic の読み取りまたはファイルの書き込み時に、または Dll、メソッド、およびプロパティを呼び出すときは、データ形式間で自動的に変換できます。</span><span class="sxs-lookup"><span data-stu-id="f66c4-121">When Visual Basic reads or writes files, or when it calls DLLs, methods, and properties, it can automatically convert between data formats.</span></span> <span data-ttu-id="f66c4-122">格納されているバイナリ データ`Byte`変数および配列はこのような形式の変換中に保持されます。</span><span class="sxs-lookup"><span data-stu-id="f66c4-122">Binary data stored in `Byte` variables and arrays is preserved during such format conversions.</span></span> <span data-ttu-id="f66c4-123">使用しないようにする、 `String` ANSI および Unicode 形式の間で変換中にその内容が破損することがあるため、バイナリ データ変数。</span><span class="sxs-lookup"><span data-stu-id="f66c4-123">You should not use a `String` variable for binary data, because its contents can be corrupted during conversion between ANSI and Unicode formats.</span></span>

- <span data-ttu-id="f66c4-124">**拡大します。**</span><span class="sxs-lookup"><span data-stu-id="f66c4-124">**Widening.**</span></span> <span data-ttu-id="f66c4-125">`Byte`拡大変換後のデータ型`Short`、 `UShort`、 `Integer`、 `UInteger`、 `Long`、 `ULong`、 `Decimal`、 `Single`、または`Double`します。</span><span class="sxs-lookup"><span data-stu-id="f66c4-125">The `Byte` data type widens to `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="f66c4-126">つまり、変換できる`Byte`遭遇することがなくこれらの型のいずれにも、<xref:System.OverflowException?displayProperty=nameWithType>エラー。</span><span class="sxs-lookup"><span data-stu-id="f66c4-126">This means you can convert `Byte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
- <span data-ttu-id="f66c4-127">**型宣言文字。**</span><span class="sxs-lookup"><span data-stu-id="f66c4-127">**Type Characters.**</span></span> <span data-ttu-id="f66c4-128">`Byte` リテラルの型文字または識別子の型文字がありません。</span><span class="sxs-lookup"><span data-stu-id="f66c4-128">`Byte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="f66c4-129">**フレームワークの型。**</span><span class="sxs-lookup"><span data-stu-id="f66c4-129">**Framework Type.**</span></span> <span data-ttu-id="f66c4-130">.NET Framework において対応する型は、<xref:System.Byte?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="f66c4-130">The corresponding type in the .NET Framework is the <xref:System.Byte?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="f66c4-131">例</span><span class="sxs-lookup"><span data-stu-id="f66c4-131">Example</span></span>

 <span data-ttu-id="f66c4-132">次の例では、`b`は、`Byte`変数。</span><span class="sxs-lookup"><span data-stu-id="f66c4-132">In the following example, `b` is a `Byte` variable.</span></span> <span data-ttu-id="f66c4-133">ステートメントは、変数の範囲とビット シフト演算子のアプリケーションを示します。</span><span class="sxs-lookup"><span data-stu-id="f66c4-133">The statements demonstrate the range of the variable and the application of bit-shift operators to it.</span></span>

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a><span data-ttu-id="f66c4-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="f66c4-134">See also</span></span>

- <xref:System.Byte?displayProperty=nameWithType>
- [<span data-ttu-id="f66c4-135">データの種類</span><span class="sxs-lookup"><span data-stu-id="f66c4-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="f66c4-136">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="f66c4-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="f66c4-137">変換の概要</span><span class="sxs-lookup"><span data-stu-id="f66c4-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="f66c4-138">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="f66c4-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
