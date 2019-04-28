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
ms.openlocfilehash: b50c902f69f7602dbad4663dc35bf0a2b932973f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796982"
---
# <a name="char-data-type-visual-basic"></a><span data-ttu-id="3ba66-102">文字型 (Char) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ba66-102">Char Data Type (Visual Basic)</span></span>
<span data-ttu-id="3ba66-103">0 から 65535 まで符号なし 16 ビット (2 バイト) コード ポイントを保持します。</span><span class="sxs-lookup"><span data-stu-id="3ba66-103">Holds unsigned 16-bit (2-byte) code points ranging in value from 0 through 65535.</span></span> <span data-ttu-id="3ba66-104">各*コード ポイント*、または文字コードを 1 つの Unicode 文字を表します。</span><span class="sxs-lookup"><span data-stu-id="3ba66-104">Each *code point*, or character code, represents a single Unicode character.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ba66-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="3ba66-105">Remarks</span></span>  
 <span data-ttu-id="3ba66-106">使用して、`Char`データ型は、1 つのみを保持する必要があるときのオーバーヘッドは必要ありません、文字`String`します。</span><span class="sxs-lookup"><span data-stu-id="3ba66-106">Use the `Char` data type when you need to hold only a single character and do not need the overhead of `String`.</span></span> <span data-ttu-id="3ba66-107">使用することができる場合によっては`Char()`、配列の`Char`要素、複数の文字を保持するためにします。</span><span class="sxs-lookup"><span data-stu-id="3ba66-107">In some cases you can use `Char()`, an array of `Char` elements, to hold multiple characters.</span></span>  
  
 <span data-ttu-id="3ba66-108">既定値`Char`コード ポイント 0 の文字します。</span><span class="sxs-lookup"><span data-stu-id="3ba66-108">The default value of `Char` is the character with a code point of 0.</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="3ba66-109">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="3ba66-109">Unicode Characters</span></span>  
 <span data-ttu-id="3ba66-110">Unicode の最初の 128 個のコード ポイント (0 ~ 127) は、文字および記号の標準的な US キーボード上に対応します。</span><span class="sxs-lookup"><span data-stu-id="3ba66-110">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="3ba66-111">これら最初の 128 個のコード ポイントは、ASCII 文字セットの定義と同じです。</span><span class="sxs-lookup"><span data-stu-id="3ba66-111">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="3ba66-112">2 番目の 128 個のコード ポイント (128 ~ 255) では、ラテン語系のアルファベット文字、アクセント記号、通貨記号、および分数などの特殊文字を表します。</span><span class="sxs-lookup"><span data-stu-id="3ba66-112">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="3ba66-113">Unicode では、記号、世界中のテキスト文字、分音記号、数学的、技術的な記号などのさまざまな他のコード ポイント (256 ~ 65535) を使用します。</span><span class="sxs-lookup"><span data-stu-id="3ba66-113">Unicode uses the remaining code points (256-65535) for a wide variety of symbols, including worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="3ba66-114">などのメソッドを使用する<xref:System.Char.IsDigit%2A>と<xref:System.Char.IsPunctuation%2A>上、 `Char` Unicode 分類を決定する変数。</span><span class="sxs-lookup"><span data-stu-id="3ba66-114">You can use methods like <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on a `Char` variable to determine its Unicode classification.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="3ba66-115">型変換</span><span class="sxs-lookup"><span data-stu-id="3ba66-115">Type Conversions</span></span>  
 <span data-ttu-id="3ba66-116">Visual Basic では直接間変換されません`Char`と数値の型。</span><span class="sxs-lookup"><span data-stu-id="3ba66-116">Visual Basic does not convert directly between `Char` and the numeric types.</span></span> <span data-ttu-id="3ba66-117">使用することができます、<xref:Microsoft.VisualBasic.Strings.Asc%2A>または<xref:Microsoft.VisualBasic.Strings.AscW%2A>に変換する関数を`Char`値を`Integer`コード ポイントを表します。</span><span class="sxs-lookup"><span data-stu-id="3ba66-117">You can use the <xref:Microsoft.VisualBasic.Strings.Asc%2A> or <xref:Microsoft.VisualBasic.Strings.AscW%2A> function to convert a `Char` value to an `Integer` that represents its code point.</span></span> <span data-ttu-id="3ba66-118">使用することができます、<xref:Microsoft.VisualBasic.Strings.Chr%2A>または<xref:Microsoft.VisualBasic.Strings.ChrW%2A>関数に変換する、`Integer`値を`Char`を持つ、そのコード ポイント。</span><span class="sxs-lookup"><span data-stu-id="3ba66-118">You can use the <xref:Microsoft.VisualBasic.Strings.Chr%2A> or <xref:Microsoft.VisualBasic.Strings.ChrW%2A> function to convert an `Integer` value to a `Char` that has that code point.</span></span>  
  
 <span data-ttu-id="3ba66-119">型チェック スイッチの場合 ([Option Strict ステートメント](../../../visual-basic/language-reference/statements/option-strict-statement.md)) は、1 文字の文字列としてそれを識別するリテラルにリテラルの型文字を追加する必要があります、`Char`データ型。</span><span class="sxs-lookup"><span data-stu-id="3ba66-119">If the type checking switch ([Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) is on, you must append the literal type character to a single-character string literal to identify it as the `Char` data type.</span></span> <span data-ttu-id="3ba66-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3ba66-120">The following example illustrates this.</span></span>  
  
```  
Option Strict On  
Dim charVar As Char  
' The following statement attempts to convert a String literal to Char.  
' Because Option Strict is On, it generates a compiler error.  
charVar = "Z"  
' The following statement succeeds because it specifies a Char literal.  
charVar = "Z"C  
```  
  
## <a name="programming-tips"></a><span data-ttu-id="3ba66-121">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="3ba66-121">Programming Tips</span></span>  
  
- <span data-ttu-id="3ba66-122">**負の数。**</span><span class="sxs-lookup"><span data-stu-id="3ba66-122">**Negative Numbers.**</span></span> <span data-ttu-id="3ba66-123">`Char` 符号なしの型は、負の値を表すことはできません。</span><span class="sxs-lookup"><span data-stu-id="3ba66-123">`Char` is an unsigned type and cannot represent a negative value.</span></span> <span data-ttu-id="3ba66-124">いずれの場合も、行わないで`Char`数値の値を保持します。</span><span class="sxs-lookup"><span data-stu-id="3ba66-124">In any case, you should not use `Char` to hold numeric values.</span></span>  
  
- <span data-ttu-id="3ba66-125">**相互運用の考慮事項。**</span><span class="sxs-lookup"><span data-stu-id="3ba66-125">**Interop Considerations.**</span></span> <span data-ttu-id="3ba66-126">例のオートメーションまたは COM オブジェクト、.NET framework では、作成されていないコンポーネントを使用する場合、他の環境では文字型の別のデータ幅 (8 ビット) ことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3ba66-126">If you interface with components not written for the .NET Framework, for example Automation or COM objects, remember that character types have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="3ba66-127">このようなコンポーネントに 8 ビットの引数を渡すと場合、宣言として`Byte`の代わりに`Char`で新しい Visual Basic コードです。</span><span class="sxs-lookup"><span data-stu-id="3ba66-127">If you pass an 8-bit argument to such a component, declare it as `Byte` instead of `Char` in your new Visual Basic code.</span></span>  
  
- <span data-ttu-id="3ba66-128">**拡大します。**</span><span class="sxs-lookup"><span data-stu-id="3ba66-128">**Widening.**</span></span> <span data-ttu-id="3ba66-129">`Char`拡大変換後のデータ型`String`します。</span><span class="sxs-lookup"><span data-stu-id="3ba66-129">The `Char` data type widens to `String`.</span></span> <span data-ttu-id="3ba66-130">つまり、変換できる`Char`に`String`は発生しませんし、<xref:System.OverflowException?displayProperty=nameWithType>エラー。</span><span class="sxs-lookup"><span data-stu-id="3ba66-130">This means you can convert `Char` to `String` and will not encounter a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="3ba66-131">**型宣言文字。**</span><span class="sxs-lookup"><span data-stu-id="3ba66-131">**Type Characters.**</span></span> <span data-ttu-id="3ba66-132">リテラルの型文字を付加する`C`1 文字の文字列にリテラルを強制的に、`Char`データ型。</span><span class="sxs-lookup"><span data-stu-id="3ba66-132">Appending the literal type character `C` to a single-character string literal forces it to the `Char` data type.</span></span> <span data-ttu-id="3ba66-133">`Char` 識別子の型文字がありません。</span><span class="sxs-lookup"><span data-stu-id="3ba66-133">`Char` has no identifier type character.</span></span>  
  
- <span data-ttu-id="3ba66-134">**フレームワークの型。**</span><span class="sxs-lookup"><span data-stu-id="3ba66-134">**Framework Type.**</span></span> <span data-ttu-id="3ba66-135">.NET Framework において対応する型は、<xref:System.Char?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="3ba66-135">The corresponding type in the .NET Framework is the <xref:System.Char?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ba66-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ba66-136">See also</span></span>

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="3ba66-137">データの種類</span><span class="sxs-lookup"><span data-stu-id="3ba66-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="3ba66-138">String データ型</span><span class="sxs-lookup"><span data-stu-id="3ba66-138">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="3ba66-139">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="3ba66-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="3ba66-140">変換の概要</span><span class="sxs-lookup"><span data-stu-id="3ba66-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="3ba66-141">方法: 符号なしの型を使用する Windows の機能を呼び出す</span><span class="sxs-lookup"><span data-stu-id="3ba66-141">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="3ba66-142">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="3ba66-142">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
