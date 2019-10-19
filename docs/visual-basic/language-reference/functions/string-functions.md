---
title: 文字列関数 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- string functions
ms.assetid: f1bf9ac2-cbcf-4298-ae51-53182076bdc8
ms.openlocfilehash: 0002a3dd19b493f690f91f9b6c68a9241e6d6ea0
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582999"
---
# <a name="string-functions-visual-basic"></a><span data-ttu-id="25a45-102">文字列関数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25a45-102">String Functions (Visual Basic)</span></span>

<span data-ttu-id="25a45-103">次の表は、文字列を検索して操作するために <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType> クラスで提供 Visual Basic れる関数を示しています。</span><span class="sxs-lookup"><span data-stu-id="25a45-103">The following table lists the functions that Visual Basic provides in the <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType> class to search and manipulate strings.</span></span> <span data-ttu-id="25a45-104">これらは Visual Basic 組み込み関数と見なすことができます。つまり、例に示すように、クラスの明示的なメンバーとして呼び出す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="25a45-104">They can be regarded as Visual Basic intrinsic functions; that is, you do not have to call them as explicit members of a class, as the examples show.</span></span> <span data-ttu-id="25a45-105">@No__t_0 クラスでは、追加のメソッド、および場合によっては補完メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="25a45-105">Additional methods, and in some cases complementary methods, are available in the <xref:System.String?displayProperty=nameWithType> class.</span></span>

|<span data-ttu-id="25a45-106">.NET Framework メソッド</span><span class="sxs-lookup"><span data-stu-id="25a45-106">.NET Framework method</span></span>|<span data-ttu-id="25a45-107">説明</span><span class="sxs-lookup"><span data-stu-id="25a45-107">Description</span></span>|
|---------------------------|-----------------|
|<span data-ttu-id="25a45-108"><xref:Microsoft.VisualBasic.Strings.Asc%2A>、 <xref:Microsoft.VisualBasic.Strings.AscW%2A></span><span class="sxs-lookup"><span data-stu-id="25a45-108"><xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A></span></span>|<span data-ttu-id="25a45-109">文字に対応する文字コードを表す `Integer` 値を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-109">Returns an `Integer` value representing the character code corresponding to a character.</span></span>|
|<span data-ttu-id="25a45-110"><xref:Microsoft.VisualBasic.Strings.Chr%2A>、 <xref:Microsoft.VisualBasic.Strings.ChrW%2A></span><span class="sxs-lookup"><span data-stu-id="25a45-110"><xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A></span></span>|<span data-ttu-id="25a45-111">指定された文字コードに対応する文字を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-111">Returns the character associated with the specified character code.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Filter%2A>|<span data-ttu-id="25a45-112">指定されたフィルター条件に基づいた文字列 (`String`) 配列のサブセットを含むゼロ ベースの配列を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-112">Returns a zero-based array containing a subset of a `String` array based on specified filter criteria.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Format%2A>|<span data-ttu-id="25a45-113">書式指定文字列 (`String`) 式に含まれる指示に従って書式設定された文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-113">Returns a string formatted according to instructions contained in a format `String` expression.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.FormatCurrency%2A>|<span data-ttu-id="25a45-114">システムの [コントロール パネル] で定義されている通貨記号を使って通貨形式の文字列に書式設定して返す文字列処理関数です。</span><span class="sxs-lookup"><span data-stu-id="25a45-114">Returns an expression formatted as a currency value using the currency symbol defined in the system control panel.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|<span data-ttu-id="25a45-115">日時の値を表す文字列式を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-115">Returns a string expression representing a date/time value.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.FormatNumber%2A>|<span data-ttu-id="25a45-116">数値形式の文字列に書式設定して返す文字列処理関数です。</span><span class="sxs-lookup"><span data-stu-id="25a45-116">Returns an expression formatted as a number.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.FormatPercent%2A>|<span data-ttu-id="25a45-117">パーセント記号 (%) が付加されたパーセント形式 (100 で乗算した) の文字列に書式設定して返す文字列処理関数です。</span><span class="sxs-lookup"><span data-stu-id="25a45-117">Returns an expression formatted as a percentage (that is, multiplied by 100) with a trailing % character.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.InStr%2A>|<span data-ttu-id="25a45-118">ある文字列の中から指定した文字列を検索し、最初に見つかった文字列の開始位置を示す整数型の値を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-118">Returns an integer specifying the start position of the first occurrence of one string within another.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.InStrRev%2A>|<span data-ttu-id="25a45-119">ある文字列の中から指定された文字列を最後の文字位置から検索を開始し、最初に見つかった文字位置 (先頭からその位置までの文字数) を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-119">Returns the position of the first occurrence of one string within another, starting from the right side of the string.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Join%2A>|<span data-ttu-id="25a45-120">配列に含まれる多数の部分文字列を結合して作成される文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-120">Returns a string created by joining a number of substrings contained in an array.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.LCase%2A>|<span data-ttu-id="25a45-121">小文字に変換した文字列または文字を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-121">Returns a string or character converted to lowercase.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Left%2A>|<span data-ttu-id="25a45-122">指定された文字数を含む文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-122">Returns a string containing a specified number of characters from the left side of a string.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Len%2A>|<span data-ttu-id="25a45-123">文字列内の文字数を含む整数を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-123">Returns an integer that contains the number of characters in a string.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.LSet%2A>|<span data-ttu-id="25a45-124">指定の文字列が含まれている文字列を左寄せで指定の長さに調整して返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-124">Returns a left-aligned string containing the specified string adjusted to the specified length.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.LTrim%2A>|<span data-ttu-id="25a45-125">指定された文字列から、先頭の空白を除いたコピーを格納する文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-125">Returns a string containing a copy of a specified string with no leading spaces.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Mid%2A>|<span data-ttu-id="25a45-126">文字列から指定された文字数分の文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-126">Returns a string containing a specified number of characters from a string.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Replace%2A>|<span data-ttu-id="25a45-127">指定された文字列の一部を指定された回数分別の部分文字列で置換した文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-127">Returns a string in which a specified substring has been replaced with another substring a specified number of times.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Right%2A>|<span data-ttu-id="25a45-128">文字列の右端から指定された文字数分の文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-128">Returns a string containing a specified number of characters from the right side of a string.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.RSet%2A>|<span data-ttu-id="25a45-129">文字列と長さが指定され、その長さに調整された文字列右揃えにして文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-129">Returns a right-aligned string containing the specified string adjusted to the specified length.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.RTrim%2A>|<span data-ttu-id="25a45-130">指定された文字列から、末尾の空白を除いたコピーを格納する文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-130">Returns a string containing a copy of a specified string with no trailing spaces.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Space%2A>|<span data-ttu-id="25a45-131">指定された数のスペースから成る文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-131">Returns a string consisting of the specified number of spaces.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Split%2A>|<span data-ttu-id="25a45-132">部分文字列ごとに区切られた文字列からゼロ ベースの 1 次元配列を作成し、返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-132">Returns a zero-based, one-dimensional array containing a specified number of substrings.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.StrComp%2A>|<span data-ttu-id="25a45-133">文字列比較の結果により、-1、0、または 1 のいずれかを返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-133">Returns -1, 0, or 1, based on the result of a string comparison.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.StrConv%2A>|<span data-ttu-id="25a45-134">指定に従って変換された文字列型の値を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-134">Returns a string converted as specified.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.StrDup%2A>|<span data-ttu-id="25a45-135">指定された文字が指定された回数繰り返されている文字列型またはオブジェクト型の値を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-135">Returns a string or object consisting of the specified character repeated the specified number of times.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.StrReverse%2A>|<span data-ttu-id="25a45-136">指定された文字列の文字の並び順を逆にした文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-136">Returns a string in which the character order of a specified string is reversed.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.Trim%2A>|<span data-ttu-id="25a45-137">指定された文字列から、先頭または末尾の空白を除いたコピーを格納する文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-137">Returns a string containing a copy of a specified string with no leading or trailing spaces.</span></span>|
|<xref:Microsoft.VisualBasic.Strings.UCase%2A>|<span data-ttu-id="25a45-138">指定された文字列を大文字に変換して文字列型または char 型の値を返します。</span><span class="sxs-lookup"><span data-stu-id="25a45-138">Returns a string or character containing the specified string converted to uppercase.</span></span>|

<span data-ttu-id="25a45-139">[Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)ステートメントを使用すると、システムのロケール (`Text`) または文字の内部バイナリ表現 (`Binary`) によって決定される、大文字と小文字を区別しないテキストの並べ替え順序を使用して文字列を比較するかどうかを設定できます。</span><span class="sxs-lookup"><span data-stu-id="25a45-139">You can use the [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) statement to set whether strings are compared using a case-insensitive text sort order determined by your system's locale (`Text`) or by the internal binary representations of the characters (`Binary`).</span></span> <span data-ttu-id="25a45-140">既定のテキスト比較方法は `Binary` です。</span><span class="sxs-lookup"><span data-stu-id="25a45-140">The default text comparison method is `Binary`.</span></span>

## <a name="example-ucase"></a><span data-ttu-id="25a45-141">例: UCase</span><span class="sxs-lookup"><span data-stu-id="25a45-141">Example: UCase</span></span>

<span data-ttu-id="25a45-142">`UCase` 関数を使って文字列を大文字に変換して返す例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="25a45-142">This example uses the `UCase` function to return an uppercase version of a string.</span></span>
[!code-vb[VbVbalrStrings#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#31)]

## <a name="example-ltrim"></a><span data-ttu-id="25a45-143">例: LTrim</span><span class="sxs-lookup"><span data-stu-id="25a45-143">Example: LTrim</span></span>

<span data-ttu-id="25a45-144">この例では、文字列変数から、`LTrim` 関数を使って先頭の空白を除去し、`RTrim` 関数を使って後続の空白を除去しています。</span><span class="sxs-lookup"><span data-stu-id="25a45-144">This example uses the `LTrim` function to strip leading spaces and the `RTrim` function to strip trailing spaces from a string variable.</span></span> <span data-ttu-id="25a45-145">また、`Trim` 関数を使って両方のタイプの空白を除去しています。</span><span class="sxs-lookup"><span data-stu-id="25a45-145">It uses the `Trim` function to strip both types of spaces.</span></span>

[!code-vb[VbVbalrStrings#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#25)]

## <a name="example-mid"></a><span data-ttu-id="25a45-146">例: Mid</span><span class="sxs-lookup"><span data-stu-id="25a45-146">Example: Mid</span></span>

<span data-ttu-id="25a45-147">`Mid` 関数を使って、文字列から指定された字数を返す例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="25a45-147">This example uses the `Mid` function to return a specified number of characters from a string.</span></span>

[!code-vb[VbVbalrStrings#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#17)]

## <a name="example-len"></a><span data-ttu-id="25a45-148">例: Len</span><span class="sxs-lookup"><span data-stu-id="25a45-148">Example: Len</span></span>

<span data-ttu-id="25a45-149">`Len` 関数を使って文字列の文字数を返す例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="25a45-149">This example uses `Len` to return the number of characters in a string.</span></span>

[!code-vb[VbVbalrStrings#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#33)]

## <a name="example-instr"></a><span data-ttu-id="25a45-150">例: InStr</span><span class="sxs-lookup"><span data-stu-id="25a45-150">Example: InStr</span></span>

<span data-ttu-id="25a45-151">`InStr` 関数を使って、ある文字列の中から指定された文字列を検索し、最初に見つかった文字位置を返す例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="25a45-151">This example uses the `InStr` function to return the position of the first occurrence of one string within another.</span></span>

[!code-vb[VbVbalrStrings#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#8)]

## <a name="example-format"></a><span data-ttu-id="25a45-152">例: 形式</span><span class="sxs-lookup"><span data-stu-id="25a45-152">Example: Format</span></span>

<span data-ttu-id="25a45-153">`Format` の書式指定とユーザー定義の書式指定の両方を使って値の書式を指定する、`String` 関数のさまざまな使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="25a45-153">This example shows various uses of the `Format` function to format values using both `String` formats and user-defined formats.</span></span> <span data-ttu-id="25a45-154">日付の区切り記号 (`/`)、時刻の区切り記号 (`:`)、および午前/午後を示す文字 (`t` および `tt`) について、システムで実際に表示される書式は、コードが使用するロケール設定によって決まります。</span><span class="sxs-lookup"><span data-stu-id="25a45-154">For the date separator (`/`), time separator (`:`), and the AM/PM indicators (`t` and `tt`), the actual formatted output displayed by your system depends on the locale settings the code is using.</span></span> <span data-ttu-id="25a45-155">時刻と日付を開発環境で表示する場合は、コード ロケールの短い時刻書式と短い日付書式が使用されます。</span><span class="sxs-lookup"><span data-stu-id="25a45-155">When times and dates are displayed in the development environment, the short time format and short date format of the code locale are used.</span></span>

> [!NOTE]
> <span data-ttu-id="25a45-156">24 時間制を使用するロケールでは、午前/午後を示す記号 (`t` および `tt`) では何も表示されません。</span><span class="sxs-lookup"><span data-stu-id="25a45-156">For locales that use a 24-hour clock, the AM/PM indicators (`t` and `tt`) display nothing.</span></span>

[!code-vb[VbVbalrStrings#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#27)]

## <a name="see-also"></a><span data-ttu-id="25a45-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="25a45-157">See also</span></span>

- [<span data-ttu-id="25a45-158">キーワード</span><span class="sxs-lookup"><span data-stu-id="25a45-158">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="25a45-159">Visual Basic ランタイム ライブラリのメンバー</span><span class="sxs-lookup"><span data-stu-id="25a45-159">Visual Basic Runtime Library Members</span></span>](../../../visual-basic/language-reference/runtime-library-members.md)
- [<span data-ttu-id="25a45-160">文字列操作の概要</span><span class="sxs-lookup"><span data-stu-id="25a45-160">String Manipulation Summary</span></span>](../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)
- [<span data-ttu-id="25a45-161">System.string クラスのメソッド</span><span class="sxs-lookup"><span data-stu-id="25a45-161">System.String class methods</span></span>](xref:System.String#methods)
