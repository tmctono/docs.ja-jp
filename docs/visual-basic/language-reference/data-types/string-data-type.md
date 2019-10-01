---
title: 文字列型 (String) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.String
helpviewer_keywords:
- strings [Visual Basic], character
- strings [Visual Basic], fixed-length
- string keyword [Visual Basic]
- fixed-length strings [Visual Basic], string data type
- literals [Visual Basic], string
- text [Visual Basic], String data type
- $ identifier type character
- String data type
- fixed-length strings
- string literals [Visual Basic]
- data types [Visual Basic], assigning
- String literals [Visual Basic]
- identifier type characters [Visual Basic], $
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
ms.openlocfilehash: 6d2fd226735622de5cd7197060c05b8ac12b69f1
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696839"
---
# <a name="string-data-type-visual-basic"></a><span data-ttu-id="57a04-102">文字列型 (String) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57a04-102">String Data Type (Visual Basic)</span></span>
<span data-ttu-id="57a04-103">0 ~ 65535 の範囲の値を範囲とする符号なし16ビット (2 バイト) コードポイントのシーケンスを保持します。</span><span class="sxs-lookup"><span data-stu-id="57a04-103">Holds sequences of unsigned 16-bit (2-byte) code points that range in value from 0 through 65535.</span></span> <span data-ttu-id="57a04-104">各*コードポイント*(文字コード) は、1つの Unicode 文字を表します。</span><span class="sxs-lookup"><span data-stu-id="57a04-104">Each *code point*, or character code, represents a single Unicode character.</span></span> <span data-ttu-id="57a04-105">文字列には、0 ~ 約 20億 (2 ^ 31) の Unicode 文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="57a04-105">A string can contain from 0 to approximately two billion (2 ^ 31) Unicode characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57a04-106">コメント</span><span class="sxs-lookup"><span data-stu-id="57a04-106">Remarks</span></span>  
 <span data-ttu-id="57a04-107">@No__t 0 のデータ型を使用して、`Char` 要素の配列である `Char()` の配列管理オーバーヘッドを発生させずに、複数の文字を保持します。</span><span class="sxs-lookup"><span data-stu-id="57a04-107">Use the `String` data type to hold multiple characters without the array management overhead of `Char()`, an array of `Char` elements.</span></span>  
  
 <span data-ttu-id="57a04-108">@No__t-0 の既定値は `Nothing` (null 参照) です。</span><span class="sxs-lookup"><span data-stu-id="57a04-108">The default value of `String` is `Nothing` (a null reference).</span></span> <span data-ttu-id="57a04-109">これは空の文字列 (値 `""`) と同じではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="57a04-109">Note that this is not the same as the empty string (value `""`).</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="57a04-110">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="57a04-110">Unicode Characters</span></span>  
 <span data-ttu-id="57a04-111">Unicode の最初の128コードポイント (0 ~ 127) は、標準の U.S. キーボードの文字と記号に対応しています。</span><span class="sxs-lookup"><span data-stu-id="57a04-111">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="57a04-112">これらの最初の128コードポイントは、ASCII 文字セットで定義されているものと同じです。</span><span class="sxs-lookup"><span data-stu-id="57a04-112">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="57a04-113">2番目の128コードポイント (128 ~ 255) は、ラテン語に基づくアルファベット文字、アクセント、通貨記号、分数などの特殊文字を表します。</span><span class="sxs-lookup"><span data-stu-id="57a04-113">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="57a04-114">Unicode では、さまざまなシンボルについて、残りのコードポイント (256-65535) を使用します。</span><span class="sxs-lookup"><span data-stu-id="57a04-114">Unicode uses the remaining code points (256-65535) for a wide variety of symbols.</span></span> <span data-ttu-id="57a04-115">これには、世界中のテキスト文字、分音記号、数学、およびテクニカルシンボルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="57a04-115">This includes worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="57a04-116">@No__t-2 変数の個々の文字に <xref:System.Char.IsDigit%2A> や <xref:System.Char.IsPunctuation%2A> などのメソッドを使用して、Unicode 分類を決定することができます。</span><span class="sxs-lookup"><span data-stu-id="57a04-116">You can use methods such as <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on an individual character in a `String` variable to determine its Unicode classification.</span></span>  
  
## <a name="format-requirements"></a><span data-ttu-id="57a04-117">書式の要件</span><span class="sxs-lookup"><span data-stu-id="57a04-117">Format Requirements</span></span>  
 <span data-ttu-id="57a04-118">@No__t-0 リテラルは引用符で囲む必要があります (`" "`)。</span><span class="sxs-lookup"><span data-stu-id="57a04-118">You must enclose a `String` literal within quotation marks (`" "`).</span></span> <span data-ttu-id="57a04-119">文字列内のいずれかの文字として引用符を含める必要がある場合は、2つの連続する引用符 (`""`) を使用します。</span><span class="sxs-lookup"><span data-stu-id="57a04-119">If you must include a quotation mark as one of the characters in the string, you use two contiguous quotation marks (`""`).</span></span> <span data-ttu-id="57a04-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="57a04-120">The following example illustrates this.</span></span>  
  
```vb  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 <span data-ttu-id="57a04-121">文字列内の引用符を表す連続した引用符は、@no__t 0 リテラルを開始および終了する引用符とは関係がないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="57a04-121">Note that the contiguous quotation marks that represent a quotation mark in the string are independent of the quotation marks that begin and end the `String` literal.</span></span>  
  
## <a name="string-manipulations"></a><span data-ttu-id="57a04-122">文字列操作</span><span class="sxs-lookup"><span data-stu-id="57a04-122">String Manipulations</span></span>  
 <span data-ttu-id="57a04-123">@No__t 0 の変数に文字列を割り当てると、その文字列は*不変*になります。つまり、長さや内容を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="57a04-123">Once you assign a string to a `String` variable, that string is *immutable*, which means you cannot change its length or contents.</span></span> <span data-ttu-id="57a04-124">文字列を任意の方法で変更すると、Visual Basic によって新しい文字列が作成され、前の文字列が破棄されます。</span><span class="sxs-lookup"><span data-stu-id="57a04-124">When you alter a string in any way, Visual Basic creates a new string and abandons the previous one.</span></span> <span data-ttu-id="57a04-125">@No__t 0 の変数は、新しい文字列を指します。</span><span class="sxs-lookup"><span data-stu-id="57a04-125">The `String` variable then points to the new string.</span></span>  
  
 <span data-ttu-id="57a04-126">@No__t 0 変数の内容を操作するには、さまざまな文字列関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="57a04-126">You can manipulate the contents of a `String` variable by using a variety of string functions.</span></span> <span data-ttu-id="57a04-127">次の例は、<xref:Microsoft.VisualBasic.Strings.Left%2A> 関数を示しています。</span><span class="sxs-lookup"><span data-stu-id="57a04-127">The following example illustrates the <xref:Microsoft.VisualBasic.Strings.Left%2A> function</span></span>  
  
```vb  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 <span data-ttu-id="57a04-128">別のコンポーネントによって作成された文字列は、先頭または末尾にスペースが埋め込まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="57a04-128">A string created by another component might be padded with leading or trailing spaces.</span></span> <span data-ttu-id="57a04-129">このような文字列を受け取った場合は、<xref:Microsoft.VisualBasic.Strings.Trim%2A>、<xref:Microsoft.VisualBasic.Strings.LTrim%2A>、<xref:Microsoft.VisualBasic.Strings.RTrim%2A> の各関数を使用して、これらのスペースを削除できます。</span><span class="sxs-lookup"><span data-stu-id="57a04-129">If you receive such a string, you can use the <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, and <xref:Microsoft.VisualBasic.Strings.RTrim%2A> functions to remove these spaces.</span></span>  
  
 <span data-ttu-id="57a04-130">文字列操作の詳細については、「[文字列](../../../visual-basic/programming-guide/language-features/strings/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57a04-130">For more information about string manipulations, see [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="57a04-131">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="57a04-131">Programming Tips</span></span>  
  
- <span data-ttu-id="57a04-132">**負の数値。**</span><span class="sxs-lookup"><span data-stu-id="57a04-132">**Negative Numbers.**</span></span> <span data-ttu-id="57a04-133">@No__t-0 によって保持されている文字は符号なしであり、負の値を表すことはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="57a04-133">Remember that the characters held by `String` are unsigned and cannot represent negative values.</span></span> <span data-ttu-id="57a04-134">どのような場合でも、`String` を使用して数値を保持することはできません。</span><span class="sxs-lookup"><span data-stu-id="57a04-134">In any case, you should not use `String` to hold numeric values.</span></span>  
  
- <span data-ttu-id="57a04-135">**相互運用に関する考慮事項。**</span><span class="sxs-lookup"><span data-stu-id="57a04-135">**Interop Considerations.**</span></span> <span data-ttu-id="57a04-136">.NET Framework 用に作成されていないコンポーネント (たとえば、オートメーションや COM オブジェクト) とやり取りする場合は、他の環境で文字列文字のデータ幅が異なる (8 ビット) ことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="57a04-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that string characters have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="57a04-137">8ビット文字の文字列引数をこのようなコンポーネントに渡す場合は、新しい Visual Basic コードで `String` ではなく、`Byte` 要素の配列 @no__t 0 として宣言します。</span><span class="sxs-lookup"><span data-stu-id="57a04-137">If you are passing a string argument of 8-bit characters to such a component, declare it as `Byte()`, an array of `Byte` elements, instead of `String` in your new Visual Basic code.</span></span>  
  
- <span data-ttu-id="57a04-138">**文字を入力します。**</span><span class="sxs-lookup"><span data-stu-id="57a04-138">**Type Characters.**</span></span> <span data-ttu-id="57a04-139">識別子の型文字 `$` を任意の識別子に追加すると、強制的に `String` のデータ型になります。</span><span class="sxs-lookup"><span data-stu-id="57a04-139">Appending the identifier type character `$` to any identifier forces it to the `String` data type.</span></span> <span data-ttu-id="57a04-140">`String` にはリテラルの型文字がありません。</span><span class="sxs-lookup"><span data-stu-id="57a04-140">`String` has no literal type character.</span></span> <span data-ttu-id="57a04-141">ただし、コンパイラは、引用符で囲まれたリテラル (`" "`) を `String` として扱います。</span><span class="sxs-lookup"><span data-stu-id="57a04-141">However, the compiler treats literals enclosed in quotation marks (`" "`) as `String`.</span></span>  
  
- <span data-ttu-id="57a04-142">**フレームワークの種類。**</span><span class="sxs-lookup"><span data-stu-id="57a04-142">**Framework Type.**</span></span> <span data-ttu-id="57a04-143">.NET Framework 内の対応する型は、@no__t 0 のクラスです。</span><span class="sxs-lookup"><span data-stu-id="57a04-143">The corresponding type in the .NET Framework is the <xref:System.String?displayProperty=nameWithType> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57a04-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="57a04-144">See also</span></span>

- <xref:System.String?displayProperty=nameWithType>
- [<span data-ttu-id="57a04-145">データの種類</span><span class="sxs-lookup"><span data-stu-id="57a04-145">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="57a04-146">Char データ型</span><span class="sxs-lookup"><span data-stu-id="57a04-146">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="57a04-147">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="57a04-147">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="57a04-148">変換の概要</span><span class="sxs-lookup"><span data-stu-id="57a04-148">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="57a04-149">2 つのオブジェクトが等しいかどうかをテストする方法符号なしの型を使用する Windows の機能を呼び出す</span><span class="sxs-lookup"><span data-stu-id="57a04-149">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="57a04-150">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="57a04-150">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
