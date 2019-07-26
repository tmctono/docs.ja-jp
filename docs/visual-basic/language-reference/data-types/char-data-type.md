---
title: 文字型 (Char) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Char
helpviewer_keywords:
- literal type characters [Visual Basic], C
- Char data type
- C literal type character [Visual Basic]
- data types [Visual Basic], assigning
- Char data type [Visual Basic], character literals
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
ms.openlocfilehash: ca40e6c8dcba3da29bdb68b29c91c852e477f8f7
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512792"
---
# <a name="char-data-type-visual-basic"></a><span data-ttu-id="6df18-102">文字型 (Char) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6df18-102">Char Data Type (Visual Basic)</span></span>

<span data-ttu-id="6df18-103">0 ~ 65535 の値の範囲内の符号なし16ビット (2 バイト) コードポイントを保持します。</span><span class="sxs-lookup"><span data-stu-id="6df18-103">Holds unsigned 16-bit (2-byte) code points ranging in value from 0 through 65535.</span></span> <span data-ttu-id="6df18-104">各*コードポイント*(文字コード) は、1つの Unicode 文字を表します。</span><span class="sxs-lookup"><span data-stu-id="6df18-104">Each *code point*, or character code, represents a single Unicode character.</span></span>

## <a name="remarks"></a><span data-ttu-id="6df18-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="6df18-105">Remarks</span></span>

<span data-ttu-id="6df18-106">1つ`Char`の文字だけを保持する必要があり、の`String`オーバーヘッドを必要としない場合は、データ型を使用します。</span><span class="sxs-lookup"><span data-stu-id="6df18-106">Use the `Char` data type when you need to hold only a single character and do not need the overhead of `String`.</span></span> <span data-ttu-id="6df18-107">場合によっては、 `Char()`要素の`Char`配列を使用して、複数の文字を保持できます。</span><span class="sxs-lookup"><span data-stu-id="6df18-107">In some cases you can use `Char()`, an array of `Char` elements, to hold multiple characters.</span></span>

<span data-ttu-id="6df18-108">の`Char`既定値は、コードポイントが0の文字です。</span><span class="sxs-lookup"><span data-stu-id="6df18-108">The default value of `Char` is the character with a code point of 0.</span></span>

## <a name="unicode-characters"></a><span data-ttu-id="6df18-109">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="6df18-109">Unicode Characters</span></span>

<span data-ttu-id="6df18-110">Unicode の最初の128コードポイント (0 ~ 127) は、標準の U.S. キーボードの文字と記号に対応しています。</span><span class="sxs-lookup"><span data-stu-id="6df18-110">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="6df18-111">これらの最初の128コードポイントは、ASCII 文字セットで定義されているものと同じです。</span><span class="sxs-lookup"><span data-stu-id="6df18-111">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="6df18-112">2番目の128コードポイント (128 ~ 255) は、ラテン語に基づくアルファベット文字、アクセント、通貨記号、分数などの特殊文字を表します。</span><span class="sxs-lookup"><span data-stu-id="6df18-112">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="6df18-113">Unicode では、世界中のコードポイント (256-65535) を使用して、世界中のテキスト文字、分音記号、数学記号、技術記号などのさまざまなシンボルを使用します。</span><span class="sxs-lookup"><span data-stu-id="6df18-113">Unicode uses the remaining code points (256-65535) for a wide variety of symbols, including worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>

<span data-ttu-id="6df18-114">変数にや<xref:System.Char.IsDigit%2A> <xref:System.Char.IsPunctuation%2A>などのメソッドを使用して、Unicode 分類を決定することができます。 `Char`</span><span class="sxs-lookup"><span data-stu-id="6df18-114">You can use methods like <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on a `Char` variable to determine its Unicode classification.</span></span>

## <a name="type-conversions"></a><span data-ttu-id="6df18-115">型変換</span><span class="sxs-lookup"><span data-stu-id="6df18-115">Type Conversions</span></span>

<span data-ttu-id="6df18-116">Visual Basic は、と数値型`Char`の間で直接変換されません。</span><span class="sxs-lookup"><span data-stu-id="6df18-116">Visual Basic does not convert directly between `Char` and the numeric types.</span></span> <span data-ttu-id="6df18-117">関数<xref:Microsoft.VisualBasic.Strings.Asc%2A>または<xref:Microsoft.VisualBasic.Strings.AscW%2A>関数を使用すると、 `Char`そのコードポイント`Integer`を表すに値を変換できます。</span><span class="sxs-lookup"><span data-stu-id="6df18-117">You can use the <xref:Microsoft.VisualBasic.Strings.Asc%2A> or <xref:Microsoft.VisualBasic.Strings.AscW%2A> function to convert a `Char` value to an `Integer` that represents its code point.</span></span> <span data-ttu-id="6df18-118">関数<xref:Microsoft.VisualBasic.Strings.Chr%2A>または<xref:Microsoft.VisualBasic.Strings.ChrW%2A>関数を使用すると、 `Integer`そのコードポイント`Char`を持つに値を変換できます。</span><span class="sxs-lookup"><span data-stu-id="6df18-118">You can use the <xref:Microsoft.VisualBasic.Strings.Chr%2A> or <xref:Microsoft.VisualBasic.Strings.ChrW%2A> function to convert an `Integer` value to a `Char` that has that code point.</span></span>

<span data-ttu-id="6df18-119">型チェックスイッチ ([Option Strict ステートメント](../../../visual-basic/language-reference/statements/option-strict-statement.md)) がオンになっている場合は、リテラル型の文字を`Char`データ型として識別するために、1文字の文字列リテラルに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6df18-119">If the type checking switch ([Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) is on, you must append the literal type character to a single-character string literal to identify it as the `Char` data type.</span></span> <span data-ttu-id="6df18-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6df18-120">The following example illustrates this.</span></span>

```vb
Option Strict On
Dim charVar As Char
' The following statement attempts to convert a String literal to Char.
' Because Option Strict is On, it generates a compiler error.
charVar = "Z"
' The following statement succeeds because it specifies a Char literal.
charVar = "Z"C
```

## <a name="programming-tips"></a><span data-ttu-id="6df18-121">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="6df18-121">Programming Tips</span></span>

- <span data-ttu-id="6df18-122">**負の数値。**</span><span class="sxs-lookup"><span data-stu-id="6df18-122">**Negative Numbers.**</span></span> <span data-ttu-id="6df18-123">`Char`は符号なしの型であり、負の値を表すことはできません。</span><span class="sxs-lookup"><span data-stu-id="6df18-123">`Char` is an unsigned type and cannot represent a negative value.</span></span> <span data-ttu-id="6df18-124">どのような場合でも、を`Char`使用して数値を保持することはできません。</span><span class="sxs-lookup"><span data-stu-id="6df18-124">In any case, you should not use `Char` to hold numeric values.</span></span>

- <span data-ttu-id="6df18-125">**相互運用に関する考慮事項。**</span><span class="sxs-lookup"><span data-stu-id="6df18-125">**Interop Considerations.**</span></span> <span data-ttu-id="6df18-126">.NET Framework 用に作成されていないコンポーネント (オートメーションや COM オブジェクトなど) とのインターフェイスを使用する場合は、文字型のデータ幅が異なる (8 ビット) ことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6df18-126">If you interface with components not written for the .NET Framework, for example Automation or COM objects, remember that character types have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="6df18-127">このようなコンポーネントに8ビットの引数を渡す場合は、新しい Visual Basic `Byte`コードで`Char`ではなく、として宣言します。</span><span class="sxs-lookup"><span data-stu-id="6df18-127">If you pass an 8-bit argument to such a component, declare it as `Byte` instead of `Char` in your new Visual Basic code.</span></span>

- <span data-ttu-id="6df18-128">**広げ.**</span><span class="sxs-lookup"><span data-stu-id="6df18-128">**Widening.**</span></span> <span data-ttu-id="6df18-129">データ`Char`型はに`String`拡大変換されます。</span><span class="sxs-lookup"><span data-stu-id="6df18-129">The `Char` data type widens to `String`.</span></span> <span data-ttu-id="6df18-130">これは、に`Char` `String`変換でき<xref:System.OverflowException?displayProperty=nameWithType> 、エラーが発生しないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="6df18-130">This means you can convert `Char` to `String` and will not encounter a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="6df18-131">**文字を入力します。**</span><span class="sxs-lookup"><span data-stu-id="6df18-131">**Type Characters.**</span></span> <span data-ttu-id="6df18-132">リテラル型の文字`C`を1文字の文字列リテラルに追加すると、強制的`Char`にデータ型になります。</span><span class="sxs-lookup"><span data-stu-id="6df18-132">Appending the literal type character `C` to a single-character string literal forces it to the `Char` data type.</span></span> <span data-ttu-id="6df18-133">`Char`に識別子の型文字がありません。</span><span class="sxs-lookup"><span data-stu-id="6df18-133">`Char` has no identifier type character.</span></span>

- <span data-ttu-id="6df18-134">**フレームワークの種類。**</span><span class="sxs-lookup"><span data-stu-id="6df18-134">**Framework Type.**</span></span> <span data-ttu-id="6df18-135">.NET Framework において対応する型は、<xref:System.Char?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="6df18-135">The corresponding type in the .NET Framework is the <xref:System.Char?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="6df18-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="6df18-136">See also</span></span>

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="6df18-137">データの種類</span><span class="sxs-lookup"><span data-stu-id="6df18-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="6df18-138">String データ型</span><span class="sxs-lookup"><span data-stu-id="6df18-138">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="6df18-139">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="6df18-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="6df18-140">変換の概要</span><span class="sxs-lookup"><span data-stu-id="6df18-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="6df18-141">方法: 符号なしの型を使用する Windows の機能を呼び出す</span><span class="sxs-lookup"><span data-stu-id="6df18-141">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="6df18-142">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="6df18-142">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
