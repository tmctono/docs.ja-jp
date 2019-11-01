---
title: '方法: 文字列が有効な電子メール形式であるかどうかを検証する'
ms.date: 12/10/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, examples
- user input, examples
- Regex.IsMatch method
- regular expressions [.NET Framework], examples
- examples [Visual Basic], strings
- IsValidEmail
- validation, email strings
- input, checking
- strings [.NET Framework], examples [Visual Basic]
- email [.NET Framework], validating
- IsMatch method
ms.assetid: 7536af08-4e86-4953-98a1-a8298623df92
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 352808e561a0f59d41f092eb7c70c40a591da5b6
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846777"
---
# <a name="how-to-verify-that-strings-are-in-valid-email-format"></a><span data-ttu-id="5ab64-102">方法: 文字列が有効な電子メール形式であるかどうかを検証する</span><span class="sxs-lookup"><span data-stu-id="5ab64-102">How to: Verify that strings are in valid email format</span></span>

<span data-ttu-id="5ab64-103">正規表現を使用して文字列の形式が有効な電子メール形式であるかどうかを検証する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-103">The following example uses a regular expression to verify that a string is in valid email format.</span></span>

## <a name="example"></a><span data-ttu-id="5ab64-104">例</span><span class="sxs-lookup"><span data-stu-id="5ab64-104">Example</span></span>

<span data-ttu-id="5ab64-105">次の例では、 `IsValidEmail` メソッドを定義します。このメソッドは、文字列に有効な電子メール アドレスが含まれている場合に `true` を返し、含まれていない場合に `false` を返します。それ以外の動作は行いません。</span><span class="sxs-lookup"><span data-stu-id="5ab64-105">The example defines an `IsValidEmail` method, which returns `true` if the string contains a valid email address and `false` if it does not, but takes no other action.</span></span>

<span data-ttu-id="5ab64-106">電子メール アドレスが有効であることを確認するため、 `IsValidEmail` メソッドは <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.MatchEvaluator%29?displayProperty=nameWithType> メソッドを呼び出し、 `(@)(.+)$` の正規表現パターンを指定して、電子メール アドレスからドメイン名を切り離します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-106">To verify that the email address is valid, the `IsValidEmail` method calls the <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.MatchEvaluator%29?displayProperty=nameWithType> method with the `(@)(.+)$` regular expression pattern to separate the domain name from the email address.</span></span> <span data-ttu-id="5ab64-107">3 番目のパラメーターは、一致したテキストを操作また置換するメソッドを表す <xref:System.Text.RegularExpressions.MatchEvaluator> デリゲートです。</span><span class="sxs-lookup"><span data-stu-id="5ab64-107">The third parameter is a <xref:System.Text.RegularExpressions.MatchEvaluator> delegate that represents the method that processes and replaces the matched text.</span></span> <span data-ttu-id="5ab64-108">正規表現パターンは次のように解釈されます。</span><span class="sxs-lookup"><span data-stu-id="5ab64-108">The regular expression pattern is interpreted as follows.</span></span>

|<span data-ttu-id="5ab64-109">パターン</span><span class="sxs-lookup"><span data-stu-id="5ab64-109">Pattern</span></span>|<span data-ttu-id="5ab64-110">説明</span><span class="sxs-lookup"><span data-stu-id="5ab64-110">Description</span></span>|
|-------------|-----------------|
|`(@)`|<span data-ttu-id="5ab64-111">@ 文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-111">Match the @ character.</span></span> <span data-ttu-id="5ab64-112">これが最初のキャプチャ グループです。</span><span class="sxs-lookup"><span data-stu-id="5ab64-112">This is the first capturing group.</span></span>|
|`(.+)`|<span data-ttu-id="5ab64-113">任意の文字の 1 回以上の出現に一致します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-113">Match one or more occurrences of any character.</span></span> <span data-ttu-id="5ab64-114">これが 2 番目のキャプチャ グループです。</span><span class="sxs-lookup"><span data-stu-id="5ab64-114">This is the second capturing group.</span></span>|
|`$`|<span data-ttu-id="5ab64-115">入力文字列の末尾で照合を終了します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-115">End the match at the end of the string.</span></span>|

<span data-ttu-id="5ab64-116">ドメイン名は @ 文字と合わせて `DomainMapper` メソッドに渡されます。このメソッドは <xref:System.Globalization.IdnMapping> クラスを使用して、US-ASCII 文字の範囲に含まれない Unicode 文字を Punycode に変換します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-116">The domain name along with the @ character is passed to the `DomainMapper` method, which uses the <xref:System.Globalization.IdnMapping> class to translate Unicode characters that are outside the US-ASCII character range to Punycode.</span></span> <span data-ttu-id="5ab64-117">また、このメソッドは、 `invalid` メソッドがドメイン名に無効な文字を検出すると、 `True` フラグを <xref:System.Globalization.IdnMapping.GetAscii%2A?displayProperty=nameWithType> に設定します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-117">The method also sets the `invalid` flag to `True` if the <xref:System.Globalization.IdnMapping.GetAscii%2A?displayProperty=nameWithType> method detects any invalid characters in the domain name.</span></span> <span data-ttu-id="5ab64-118">このメソッドは、Punycode ドメイン名の前に @ 記号を付けて、これを `IsValidEmail` メソッドに返します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-118">The method returns the Punycode domain name preceded by the @ symbol to the `IsValidEmail` method.</span></span>

<span data-ttu-id="5ab64-119">次に、 `IsValidEmail` メソッドは <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=nameWithType> メソッドを呼び出して、電子メール アドレスが正規表現パターンに準拠するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-119">The `IsValidEmail` method then calls the <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=nameWithType> method to verify that the address conforms to a regular expression pattern.</span></span>

<span data-ttu-id="5ab64-120">`IsValidEmail` メソッドは、認証によって電子メール アドレスを検証するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="5ab64-120">Note that the `IsValidEmail` method does not perform authentication to validate the email address.</span></span> <span data-ttu-id="5ab64-121">電子メール アドレスの形式として有効かどうかを判断しているだけです。</span><span class="sxs-lookup"><span data-stu-id="5ab64-121">It merely determines whether its format is valid for an email address.</span></span> <span data-ttu-id="5ab64-122">さらに、 `IsValidEmail` メソッドは、最上位ドメイン名が [IANA ルート ゾーン データベース](https://www.iana.org/domains/root/db)に掲載されている有効なドメイン名であることを確認しません (これには検索操作が必要です)。</span><span class="sxs-lookup"><span data-stu-id="5ab64-122">In addition, the `IsValidEmail` method does not verify that the top-level domain name is a valid domain name listed at the [IANA Root Zone Database](https://www.iana.org/domains/root/db), which would require a look-up operation.</span></span> <span data-ttu-id="5ab64-123">代わりに、正規表現によって単に最上位ドメイン名が 2 ～ 24 文字の ASCII 英数字で構成されており、最初の文字と末尾の文字は英数字、その他の文字は英数字またはハイフン (-) であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-123">Instead, the regular expression merely verifies that the top-level domain name consists of between two and twenty-four ASCII characters, with alphanumeric first and last characters and the remaining characters being either alphanumeric or a hyphen (-).</span></span>

[!code-csharp[RegularExpressions.Examples.Email#7](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Email/cs/example4.cs#7)]
[!code-vb[RegularExpressions.Examples.Email#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Email/vb/example4.vb#7)]

<span data-ttu-id="5ab64-124">この例の正規表現パターン ``^(?(")(".+?(?<!\\)"@)|(([0-9a-z]((\.(?!\.))|[-!#\$%&'\*\+/=\?\^`\{\}\|~\w])*)(?<=[0-9a-z])@))(?([)([(\d{1,3}.){3}\d{1,3}])|(([0-9a-z][-0-9a-z]*[0-9a-z]*\.)+[a-z0-9][-a-z0-9]{0,22}[a-z0-9]))$`` の意味を次の凡例に示します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-124">In this example, the regular expression pattern ``^(?(")(".+?(?<!\\)"@)|(([0-9a-z]((\.(?!\.))|[-!#\$%&'\*\+/=\?\^`\{\}\|~\w])*)(?<=[0-9a-z])@))(?([)([(\d{1,3}.){3}\d{1,3}])|(([0-9a-z][-0-9a-z]*[0-9a-z]*\.)+[a-z0-9][-a-z0-9]{0,22}[a-z0-9]))$`` is interpreted as shown in the following legend.</span></span> <span data-ttu-id="5ab64-125">正規表現のコンパイルには、<xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> フラグが使用されます。</span><span class="sxs-lookup"><span data-stu-id="5ab64-125">The regular expression is compiled using the <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> flag.</span></span>

<span data-ttu-id="5ab64-126">パターン `^`:文字列の先頭から照合を開始します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-126">Pattern `^`: Begin the match at the start of the string.</span></span>

<span data-ttu-id="5ab64-127">パターン `(?(")`:最初の文字が引用符であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-127">Pattern `(?(")`: Determine whether the first character is a quotation mark.</span></span> <span data-ttu-id="5ab64-128">`(?(")` は代替構成体の開始位置です。</span><span class="sxs-lookup"><span data-stu-id="5ab64-128">`(?(")` is the beginning of an alternation construct.</span></span>

<span data-ttu-id="5ab64-129">パターン `(?(")(".+?(?<!\\)"@)`:最初の文字が引用符である場合、始まりの引用符に続く 1 つ以上の任意の文字と終わりの引用符に一致します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-129">Pattern `(?(")(".+?(?<!\\)"@)`: If the first character is a quotation mark, match a beginning quotation mark followed by at least one occurrence of any character, followed by an ending quotation mark.</span></span> <span data-ttu-id="5ab64-130">終わりの引用符の前には円記号 (\\) を使用できません。</span><span class="sxs-lookup"><span data-stu-id="5ab64-130">The ending quotation mark must not be preceded by a backslash character (\\).</span></span> <span data-ttu-id="5ab64-131">`(?<!` はゼロ幅の否定先読みアサーションの開始です。</span><span class="sxs-lookup"><span data-stu-id="5ab64-131">`(?<!` is the beginning of a zero-width negative lookbehind assertion.</span></span> <span data-ttu-id="5ab64-132">文字列はアット マーク (@) で終わる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ab64-132">The string should conclude with an at sign (@).</span></span>

<span data-ttu-id="5ab64-133">パターン `|(([0-9a-z]`:最初の文字が引用符でない場合は、a ～ z または A ～ Z の任意の英字または 0 ～ 9 の任意の数字と一致します (比較では大文字小文字は区別されません)。</span><span class="sxs-lookup"><span data-stu-id="5ab64-133">Pattern `|(([0-9a-z]`: If the first character is not a quotation mark, match any alphabetic character from a to z or A to Z (the comparison is case insensitive), or any numeric character from 0 to 9.</span></span>

<span data-ttu-id="5ab64-134">パターン `(\.(?!\.))`:次の文字がピリオドの場合は、その文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-134">Pattern `(\.(?!\.))`: If the next character is a period, match it.</span></span> <span data-ttu-id="5ab64-135">ピリオドでない場合は、次の文字を先読みして照合を継続します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-135">If it is not a period, look ahead to the next character and continue the match.</span></span> <span data-ttu-id="5ab64-136">`(?!\.)` は、2 つの連続するピリオドが電子メール アドレスのローカル部分に出現することを防ぐゼロ幅の負の先読みアサーションです。</span><span class="sxs-lookup"><span data-stu-id="5ab64-136">`(?!\.)` is a zero-width negative lookahead assertion that prevents two consecutive periods from appearing in the local part of an email address.</span></span>

<span data-ttu-id="5ab64-137">パターン ``|[-!#\$%&'\*\+/=\?\^`\{\}\|~\w]``:次の文字がピリオドでない場合は、任意の単語文字または -!#$%&'\*+/=?^\`{}|~ のいずれかの文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-137">Pattern ``|[-!#\$%&'\*\+/=\?\^`\{\}\|~\w]``: If the next character is not a period, match any word character or one of the following characters: -!#$%&'\*+/=?^\`{}|~</span></span>

<span data-ttu-id="5ab64-138">パターン ``((\.(?!\.))|[-!#\$%&'\*\+/=\?\^`\{\}\|~\w])*``:0 回以上の代替パターン (ピリオドとそれに続くピリオド以外の文字、または複数の文字のうちのいずれかの 1 文字) と一致します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-138">Pattern ``((\.(?!\.))|[-!#\$%&'\*\+/=\?\^`\{\}\|~\w])*``: Match the alternation pattern (a period followed by a non-period, or one of a number of characters) zero or more times.</span></span>

<span data-ttu-id="5ab64-139">パターン `@`:@ 文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-139">Pattern `@`: Match the @ character.</span></span>

<span data-ttu-id="5ab64-140">パターン `(?<=[0-9a-z])`:@ 文字の前にくる文字が A ～ Z、a ～ z、または 0 ～ 9 である場合に照合を継続します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-140">Pattern `(?<=[0-9a-z])`: Continue the match if the character that precedes the @ character is A through Z, a through z, or 0 through 9.</span></span> <span data-ttu-id="5ab64-141">このパターンは、ゼロ幅の正の後読みアサーションを定義します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-141">This pattern defines a zero-width positive lookbehind assertion.</span></span>

<span data-ttu-id="5ab64-142">パターン `(?(\[)`:@ に続く文字が左角かっこかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-142">Pattern `(?(\[)`: Check whether the character that follows @ is an opening bracket.</span></span>

<span data-ttu-id="5ab64-143">パターン `(\[(\d{1,3}\.){3}\d{1,3}\])`:左角かっこの場合は、左角かっこ、それに続く IP アドレス (各セットがピリオドで区切られた、4 セットの 1 ～ 3 桁の数字)、および右角かっこと一致します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-143">Pattern `(\[(\d{1,3}\.){3}\d{1,3}\])`: If it is an opening bracket, match the opening bracket followed by an IP address (four sets of one to three digits, with each set separated by a period) and a closing bracket.</span></span>

<span data-ttu-id="5ab64-144">パターン `|(([0-9a-z][-0-9a-z]*[0-9a-z]*\.)+`:@ に続く文字が左角かっこでない場合は、値が A - Z、a - z、または 0 - 9 の 1 つの英数字の後に、ハイフンの 0 回以上の出現、A - Z、a - z、または 0 - 9 の値の 0 個または 1 つの英数字、さらにピリオドが続くパターンと一致します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-144">Pattern `|(([0-9a-z][-0-9a-z]*[0-9a-z]*\.)+`: If the character that follows @ is not an opening bracket, match one alphanumeric character with a value of A-Z, a-z, or 0-9, followed by zero or more occurrences of a hyphen, followed by zero or one alphanumeric character with a value of A-Z, a-z, or 0-9, followed by a period.</span></span> <span data-ttu-id="5ab64-145">このパターンは 1 回以上繰り返すことができ、後ろに最上位ドメイン名が続く必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ab64-145">This pattern can be repeated one or more times, and must be followed by the top-level domain name.</span></span>

<span data-ttu-id="5ab64-146">パターン `[a-z0-9][\-a-z0-9]{0,22}[a-z0-9]))`:最上位ドメイン名では、最初の文字と最後の文字が英数字文字 (a ～ z、A ～ Z、0 ～ 9) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ab64-146">Pattern `[a-z0-9][\-a-z0-9]{0,22}[a-z0-9]))`: The top-level domain name must begin and end with an alphanumeric character (a-z, A-Z, and 0-9).</span></span> <span data-ttu-id="5ab64-147">また、0 ～ 22 文字の ASCII 文字 (英数字またはハイフン) を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5ab64-147">It can also include from zero to 22 ASCII characters that are either alphanumeric or hyphens.</span></span>

<span data-ttu-id="5ab64-148">パターン `$`:入力文字列の末尾で照合を終了します。</span><span class="sxs-lookup"><span data-stu-id="5ab64-148">Pattern `$`: End the match at the end of the string.</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="5ab64-149">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="5ab64-149">Compile the code</span></span>

<span data-ttu-id="5ab64-150">`IsValidEmail` メソッドと `DomainMapper` メソッドは、正規表現ユーティリティ メソッドのライブラリに含めることができるほか、アプリケーション クラス内のプライベートな静的メソッドやインスタンス メソッドとして含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="5ab64-150">The `IsValidEmail` and `DomainMapper` methods can be included in a library of regular expression utility methods, or they can be included as private static or instance methods in the application class.</span></span>

<span data-ttu-id="5ab64-151">また、 <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> メソッドを使用して、この正規表現を正規表現ライブラリに追加できます。</span><span class="sxs-lookup"><span data-stu-id="5ab64-151">You can also use the <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> method to include this regular expression in a regular expression library.</span></span>

<span data-ttu-id="5ab64-152">正規表現ライブラリ内で使用した場合は、次のようなコードを使用して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="5ab64-152">If they are used in a regular expression library, you can call them by using code such as the following:</span></span>

[!code-csharp[RegularExpressions.Examples.Email#8](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Email/cs/example4.cs#8)]
[!code-vb[RegularExpressions.Examples.Email#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Email/vb/example4.vb#8)]

## <a name="see-also"></a><span data-ttu-id="5ab64-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ab64-153">See also</span></span>

- [<span data-ttu-id="5ab64-154">.NET Framework 正規表現</span><span class="sxs-lookup"><span data-stu-id="5ab64-154">.NET Framework Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
