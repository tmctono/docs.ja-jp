---
title: .NET 正規表現での文字クラス
description: 文字クラスを使用して、.NET 正規表現での文字のセットを表す方法について説明します。
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- character classes
- regular expressions, character classes
- characters, matching syntax
- .NET Framework regular expressions, character classes
ms.assetid: 0f8bffab-ee0d-4e0e-9a96-2b4a252bb7e4
author: rpetrusha
ms.author: ronpet
ms.custom: seodec18
ms.openlocfilehash: 556181d32f0539b4a9e24cb1a898b4ccc3788f4e
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2019
ms.locfileid: "66250884"
---
# <a name="character-classes-in-regular-expressions"></a><span data-ttu-id="31ab6-103">正規表現での文字クラス</span><span class="sxs-lookup"><span data-stu-id="31ab6-103">Character classes in regular expressions</span></span>

<span data-ttu-id="31ab6-104">文字クラスは、いずれかが入力文字列に含まれると一致と見なされる文字のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-104">A character class defines a set of characters, any one of which can occur in an input string for a match to succeed.</span></span> <span data-ttu-id="31ab6-105">.NET の正規表現言語では、次の文字クラスがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-105">The regular expression language in .NET supports the following character classes:</span></span>  
  
- <span data-ttu-id="31ab6-106">文字グループの肯定。</span><span class="sxs-lookup"><span data-stu-id="31ab6-106">Positive character groups.</span></span> <span data-ttu-id="31ab6-107">入力文字列内の文字が指定した文字のセットのいずれかと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31ab6-107">A character in the input string must match one of a specified set of characters.</span></span> <span data-ttu-id="31ab6-108">詳細については、「[文字グループの肯定](#PositiveGroup)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-108">For more information, see [Positive Character Group](#PositiveGroup).</span></span>  
  
- <span data-ttu-id="31ab6-109">文字グループの否定。</span><span class="sxs-lookup"><span data-stu-id="31ab6-109">Negative character groups.</span></span> <span data-ttu-id="31ab6-110">入力文字列内の文字が指定した文字のセットのいずれかと一致しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="31ab6-110">A character in the input string must not match one of a specified set of characters.</span></span> <span data-ttu-id="31ab6-111">詳細については、「[文字グループの否定](#NegativeGroup)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-111">For more information, see [Negative Character Group](#NegativeGroup).</span></span>  
  
- <span data-ttu-id="31ab6-112">任意の文字。</span><span class="sxs-lookup"><span data-stu-id="31ab6-112">Any character.</span></span> <span data-ttu-id="31ab6-113">正規表現の `.` (ドットまたはピリオド) 文字は、`\n` を除く任意の文字と一致するワイルドカード文字です。</span><span class="sxs-lookup"><span data-stu-id="31ab6-113">The `.` (dot or period) character in a regular expression is a wildcard character that matches any character except `\n`.</span></span> <span data-ttu-id="31ab6-114">詳細については、「[任意の文字](#AnyCharacter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-114">For more information, see [Any Character](#AnyCharacter).</span></span>  
  
- <span data-ttu-id="31ab6-115">Unicode 一般カテゴリまたは名前付きブロック。</span><span class="sxs-lookup"><span data-stu-id="31ab6-115">A general Unicode category or named block.</span></span> <span data-ttu-id="31ab6-116">入力文字列内の文字が一致と見なされるには、その文字が特定の Unicode カテゴリのメンバーであるか、または Unicode 文字の連続した範囲内に含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="31ab6-116">A character in the input string must be a member of a particular Unicode category or must fall within a contiguous range of Unicode characters for a match to succeed.</span></span> <span data-ttu-id="31ab6-117">詳細については、「[Unicode カテゴリまたは Unicode ブロック](#CategoryOrBlock)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-117">For more information, see [Unicode Category or Unicode Block](#CategoryOrBlock).</span></span>  
  
- <span data-ttu-id="31ab6-118">Unicode 一般カテゴリまたは名前付きブロックの否定。</span><span class="sxs-lookup"><span data-stu-id="31ab6-118">A negative general Unicode category or named block.</span></span> <span data-ttu-id="31ab6-119">入力文字列内の文字が一致と見なされるには、その文字が特定の Unicode カテゴリのメンバーでないか、または Unicode 文字の連続した範囲内に含まれない必要があります。</span><span class="sxs-lookup"><span data-stu-id="31ab6-119">A character in the input string must not be a member of a particular Unicode category or must not fall within a contiguous range of Unicode characters for a match to succeed.</span></span> <span data-ttu-id="31ab6-120">詳細については、「[Unicode カテゴリまたは Unicode ブロックの否定](#NegativeCategoryOrBlock)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-120">For more information, see [Negative Unicode Category or Unicode Block](#NegativeCategoryOrBlock).</span></span>  
  
- <span data-ttu-id="31ab6-121">単語に使用される文字。</span><span class="sxs-lookup"><span data-stu-id="31ab6-121">A word character.</span></span> <span data-ttu-id="31ab6-122">入力文字列内の文字が、単語内の文字に適した Unicode カテゴリのいずれかに属することができます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-122">A character in the input string can belong to any of the Unicode categories that are appropriate for characters in words.</span></span> <span data-ttu-id="31ab6-123">詳細については、「[単語に使用される文字](#WordCharacter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-123">For more information, see [Word Character](#WordCharacter).</span></span>  
  
- <span data-ttu-id="31ab6-124">単語に使用されない文字。</span><span class="sxs-lookup"><span data-stu-id="31ab6-124">A non-word character.</span></span> <span data-ttu-id="31ab6-125">入力文字列内の文字が、単語に使用される文字ではない Unicode カテゴリのいずれかに属することができます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-125">A character in the input string can belong to any Unicode category that is not a word character.</span></span> <span data-ttu-id="31ab6-126">詳細については、「[単語に使用されない文字](#NonWordCharacter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-126">For more information, see [Non-Word Character](#NonWordCharacter).</span></span>  
  
- <span data-ttu-id="31ab6-127">空白文字。</span><span class="sxs-lookup"><span data-stu-id="31ab6-127">A white-space character.</span></span> <span data-ttu-id="31ab6-128">入力文字列内の文字が、Unicode 区切り記号および各種制御文字のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="31ab6-128">A character in the input string can be any Unicode separator character, as well as any one of a number of control characters.</span></span> <span data-ttu-id="31ab6-129">詳細については、「[空白文字](#WhitespaceCharacter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-129">For more information, see [White-Space Character](#WhitespaceCharacter).</span></span>  
  
- <span data-ttu-id="31ab6-130">空白以外の文字。</span><span class="sxs-lookup"><span data-stu-id="31ab6-130">A non-white-space character.</span></span> <span data-ttu-id="31ab6-131">入力文字列内の文字が、空白文字以外の文字のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="31ab6-131">A character in the input string can be any character that is not a white-space character.</span></span> <span data-ttu-id="31ab6-132">詳細については、「[空白以外の文字](#NonWhitespaceCharacter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-132">For more information, see [Non-White-Space Character](#NonWhitespaceCharacter).</span></span>  
  
- <span data-ttu-id="31ab6-133">10 進数。</span><span class="sxs-lookup"><span data-stu-id="31ab6-133">A decimal digit.</span></span> <span data-ttu-id="31ab6-134">入力文字列内の文字が、Unicode 10 進数に分類される各種文字のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="31ab6-134">A character in the input string can be any of a number of characters classified as Unicode decimal digits.</span></span> <span data-ttu-id="31ab6-135">詳細については、「[10 進数字](#DigitCharacter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-135">For more information, see [Decimal Digit Character](#DigitCharacter).</span></span>  
  
- <span data-ttu-id="31ab6-136">10 進数字以外の文字。</span><span class="sxs-lookup"><span data-stu-id="31ab6-136">A non-decimal digit.</span></span> <span data-ttu-id="31ab6-137">入力文字列内の文字が、Unicode 10 進数以外の文字のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="31ab6-137">A character in the input string can be anything other than a Unicode decimal digit.</span></span> <span data-ttu-id="31ab6-138">詳細については、「[10 進数字](#NonDigitCharacter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-138">For more information, see [Decimal Digit Character](#NonDigitCharacter).</span></span>  
  
 <span data-ttu-id="31ab6-139">.NET は、文字クラスの減算式をサポートしています。これにより、ある文字クラスから別の文字クラスを除外した結果を文字のセットとして定義できます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-139">.NET supports character class subtraction expressions, which enables you to define a set of characters as the result of excluding one character class from another character class.</span></span> <span data-ttu-id="31ab6-140">詳細については、「[文字クラス減算](#CharacterClassSubtraction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-140">For more information, see [Character Class Subtraction](#CharacterClassSubtraction).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31ab6-141">カテゴリ別の文字に一致する文字クラス (単語文字に一致する [\w](#WordCharacter)、Unicode カテゴリに一致する [\p{}](#CategoryOrBlock) など) は、<xref:System.Globalization.CharUnicodeInfo> クラスを使用して文字カテゴリに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-141">Character classes that match characters by category, such as [\w](#WordCharacter) to match word characters or [\p{}](#CategoryOrBlock) to match a Unicode category, rely on the <xref:System.Globalization.CharUnicodeInfo> class to provide information about character categories.</span></span>  <span data-ttu-id="31ab6-142">.NET Framework 4.6.2 以降の文字カテゴリは、[Unicode 標準バージョン 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="31ab6-142">Starting with the .NET Framework 4.6.2, character categories are based on [The Unicode Standard, Version 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/).</span></span> <span data-ttu-id="31ab6-143">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] から .NET Framework 4.6.1 では、[Unicode 標準バージョン 6.3.0](https://www.unicode.org/versions/Unicode6.3.0/) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="31ab6-143">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] through the .NET Framework 4.6.1, they are based on [The Unicode Standard, Version 6.3.0](https://www.unicode.org/versions/Unicode6.3.0/).</span></span>  
  
<a name="PositiveGroup"></a>   
## <a name="positive-character-group--"></a><span data-ttu-id="31ab6-144">文字グループの肯定: [ ]</span><span class="sxs-lookup"><span data-stu-id="31ab6-144">Positive character group: [ ]</span></span>  
 <span data-ttu-id="31ab6-145">文字グループの肯定では、いずれかが入力文字列に含まれると一致と見なされる文字の一覧を指定します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-145">A positive character group specifies a list of characters, any one of which may appear in an input string for a match to occur.</span></span> <span data-ttu-id="31ab6-146">この文字の一覧は、個別に指定されることも範囲として指定されることも、その両方であることもあります。</span><span class="sxs-lookup"><span data-stu-id="31ab6-146">This list of characters may be specified individually, as a range, or both.</span></span>  
  
 <span data-ttu-id="31ab6-147">個別の文字の一覧を指定する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="31ab6-147">The syntax for specifying a list of individual characters is as follows:</span></span>  

```  
[*character_group*]  
```

 <span data-ttu-id="31ab6-148">ここで、*character_group* は、入力文字列に含まれるなら一致と見なされる個別の文字の一覧です。</span><span class="sxs-lookup"><span data-stu-id="31ab6-148">where *character_group* is a list of the individual characters that can appear in the input string for a match to succeed.</span></span> <span data-ttu-id="31ab6-149">*character_group* は、リテラル文字、[エスケープ文字](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md)、または文字クラスを 1 つ以上組み合わせて構成されます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-149">*character_group* can consist of any combination of one or more literal characters, [escape characters](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md), or character classes.</span></span>  
  
 <span data-ttu-id="31ab6-150">文字の範囲を指定する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="31ab6-150">The syntax for specifying a range of characters is as follows:</span></span>  
  
```  
[firstCharacter-lastCharacter]  
```  
  
 <span data-ttu-id="31ab6-151">ここで、*firstCharacter* は範囲の最初の文字で、*lastCharacter* は範囲の最後の文字です。</span><span class="sxs-lookup"><span data-stu-id="31ab6-151">where *firstCharacter* is the character that begins the range and *lastCharacter* is the character that ends the range.</span></span> <span data-ttu-id="31ab6-152">文字範囲は連続する一連の文字で、範囲の最初の文字、ハイフン (-)、および範囲の最後の文字を指定することで定義されます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-152">A character range is a contiguous series of characters defined by specifying the first character in the series, a hyphen (-), and then the last character in the series.</span></span> <span data-ttu-id="31ab6-153">2 つの文字の Unicode コード ポイントが隣接している場合、それらの文字は連続しています。</span><span class="sxs-lookup"><span data-stu-id="31ab6-153">Two characters are contiguous if they have adjacent Unicode code points.</span></span> <span data-ttu-id="31ab6-154">*firstCharacter* は、より低いコード ポイントを持つ文字にする必要があります。*lastCharacter* はより高いコード ポイントを持つ文字にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="31ab6-154">*firstCharacter* must be the character with the lower code point, and *lastCharacter* must be the character with the higher code point.</span></span>

> [!NOTE]
> <span data-ttu-id="31ab6-155">正の文字グループには文字セットと文字範囲の両方を含めることができるため、ハイフン文字 (`-`) は、グループの最初の文字または最後の文字でない限り、常に範囲の区切り文字として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-155">Because a positive character group can include both a set of characters and a character range, a hyphen character (`-`) is always interpreted as the range separator unless it is the first or last character of the group.</span></span>

<span data-ttu-id="31ab6-156">文字クラスの肯定を含む一般的な正規表現パターンをいくつか次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-156">Some common regular expression patterns that contain positive character classes are listed in the following table.</span></span>  
  
|<span data-ttu-id="31ab6-157">パターン</span><span class="sxs-lookup"><span data-stu-id="31ab6-157">Pattern</span></span>|<span data-ttu-id="31ab6-158">説明</span><span class="sxs-lookup"><span data-stu-id="31ab6-158">Description</span></span>|  
|-------------|-----------------|  
|`[aeiou]`|<span data-ttu-id="31ab6-159">すべての母音と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-159">Match all vowels.</span></span>|  
|`[\p{P}\d]`|<span data-ttu-id="31ab6-160">すべての句読点および 10 進数字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-160">Match all punctuation and decimal digit characters.</span></span>|  
|`[\s\p{P}]`|<span data-ttu-id="31ab6-161">すべての空白および句読点と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-161">Match all white space and punctuation.</span></span>|  
  
 <span data-ttu-id="31ab6-162">次の例では、"a" および "e" という文字を含む文字グループの肯定を定義し、入力文字列内で "grey" または "gray" という語の後に別の語が続くと一致と見なされるようにします。</span><span class="sxs-lookup"><span data-stu-id="31ab6-162">The following example defines a positive character group that contains the characters "a" and "e" so that the input string must contain the words "grey" or "gray" followed by another word for a match to occur.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/positivecharclasses.cs#1)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/positivecharclasses.vb#1)]  
  
 <span data-ttu-id="31ab6-163">正規表現パターン `gr[ae]y\s\S+?[\s|\p{P}]` は、次のように定義されます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-163">The regular expression `gr[ae]y\s\S+?[\s|\p{P}]` is defined as follows:</span></span>  
  
|<span data-ttu-id="31ab6-164">パターン</span><span class="sxs-lookup"><span data-stu-id="31ab6-164">Pattern</span></span>|<span data-ttu-id="31ab6-165">説明</span><span class="sxs-lookup"><span data-stu-id="31ab6-165">Description</span></span>|  
|-------------|-----------------|  
|`gr`|<span data-ttu-id="31ab6-166">リテラル文字 "gr" と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-166">Match the literal characters "gr".</span></span>|  
|`[ae]`|<span data-ttu-id="31ab6-167">"a" または "e" と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-167">Match either an "a" or an "e".</span></span>|  
|`y\s`|<span data-ttu-id="31ab6-168">リテラル文字 "y" の後に空白文字が続く語と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-168">Match the literal character "y" followed by a white-space character.</span></span>|  
|`\S+?`|<span data-ttu-id="31ab6-169">1 つ以上 (ただし、できるだけ少ない数) の空白以外の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-169">Match one or more non-white-space characters, but as few as possible.</span></span>|  
|`[\s\p{P}]`|<span data-ttu-id="31ab6-170">空白文字または句読点と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-170">Match either a white-space character or a punctuation mark.</span></span>|  
  
 <span data-ttu-id="31ab6-171">次の例は、大文字で始まる語と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-171">The following example matches words that begin with any capital letter.</span></span> <span data-ttu-id="31ab6-172">部分式 `[A-Z]` を使用して、A から Z の範囲の大文字を表します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-172">It uses the subexpression `[A-Z]` to represent the range of capital letters from A to Z.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/range.cs#3)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/range.vb#3)]  
  
 <span data-ttu-id="31ab6-173">正規表現 `\b[A-Z]\w*\b` は、次の表に示すように定義されています。</span><span class="sxs-lookup"><span data-stu-id="31ab6-173">The regular expression `\b[A-Z]\w*\b` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="31ab6-174">パターン</span><span class="sxs-lookup"><span data-stu-id="31ab6-174">Pattern</span></span>|<span data-ttu-id="31ab6-175">説明</span><span class="sxs-lookup"><span data-stu-id="31ab6-175">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="31ab6-176">ワード境界から開始します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-176">Start at a word boundary.</span></span>|  
|`[A-Z]`|<span data-ttu-id="31ab6-177">A から Z の任意の大文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-177">Match any uppercase character from A to Z.</span></span>|  
|`\w*`|<span data-ttu-id="31ab6-178">0 個以上の単語に使用される文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-178">Match zero or more word characters.</span></span>|  
|`\b`|<span data-ttu-id="31ab6-179">ワード境界に一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-179">Match a word boundary.</span></span>|  
  
<a name="NegativeGroup"></a>   
## <a name="negative-character-group-"></a><span data-ttu-id="31ab6-180">文字グループの否定: [^]</span><span class="sxs-lookup"><span data-stu-id="31ab6-180">Negative character group: [^]</span></span>  
 <span data-ttu-id="31ab6-181">文字グループの否定では、入力文字列に含まれなければ一致と見なされる文字の一覧を指定します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-181">A negative character group specifies a list of characters that must not appear in an input string for a match to occur.</span></span> <span data-ttu-id="31ab6-182">この文字の一覧は、個別に指定されることも範囲として指定されることも、その両方であることもあります。</span><span class="sxs-lookup"><span data-stu-id="31ab6-182">The list of characters may be specified individually, as a range, or both.</span></span>  
  
<span data-ttu-id="31ab6-183">個別の文字の一覧を指定する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="31ab6-183">The syntax for specifying a list of individual characters is as follows:</span></span>  

```
[*^character_group*]  
```

 <span data-ttu-id="31ab6-184">ここで、*character_group* は、入力文字列に含まれない場合に一致と見なされる個別の文字の一覧です。</span><span class="sxs-lookup"><span data-stu-id="31ab6-184">where *character_group* is a list of the individual characters that cannot appear in the input string for a match to succeed.</span></span> <span data-ttu-id="31ab6-185">*character_group* は、リテラル文字、[エスケープ文字](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md)、または文字クラスを 1 つ以上組み合わせて構成されます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-185">*character_group* can consist of any combination of one or more literal characters, [escape characters](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md), or character classes.</span></span>  
  
 <span data-ttu-id="31ab6-186">文字の範囲を指定する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="31ab6-186">The syntax for specifying a range of characters is as follows:</span></span>  

```
[^*firstCharacter*-*lastCharacter*]  
```

<span data-ttu-id="31ab6-187">ここで、*firstCharacter* は範囲の最初の文字で、*lastCharacter* は範囲の最後の文字です。</span><span class="sxs-lookup"><span data-stu-id="31ab6-187">where *firstCharacter* is the character that begins the range and *lastCharacter* is the character that ends the range.</span></span> <span data-ttu-id="31ab6-188">文字範囲は連続する一連の文字で、範囲の最初の文字、ハイフン (-)、および範囲の最後の文字を指定することで定義されます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-188">A character range is a contiguous series of characters defined by specifying the first character in the series, a hyphen (-), and then the last character in the series.</span></span> <span data-ttu-id="31ab6-189">2 つの文字の Unicode コード ポイントが隣接している場合、それらの文字は連続しています。</span><span class="sxs-lookup"><span data-stu-id="31ab6-189">Two characters are contiguous if they have adjacent Unicode code points.</span></span> <span data-ttu-id="31ab6-190">*firstCharacter* は、より低いコード ポイントを持つ文字にする必要があります。*lastCharacter* はより高いコード ポイントを持つ文字にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="31ab6-190">*firstCharacter* must be the character with the lower code point, and *lastCharacter* must be the character with the higher code point.</span></span>

> [!NOTE]
> <span data-ttu-id="31ab6-191">負の文字グループには文字セットと文字範囲の両方を含めることができるため、ハイフン文字 (`-`) は、グループの最初の文字または最後の文字でない限り、常に範囲の区切り文字として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-191">Because a negative character group can include both a set of characters and a character range, a hyphen character (`-`) is always interpreted as the range separator unless it is the first or last character of the group.</span></span>
  
 <span data-ttu-id="31ab6-192">複数の文字範囲を連結することもできます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-192">Two or more character ranges can be concatenated.</span></span> <span data-ttu-id="31ab6-193">たとえば、"0" ～ "9" の範囲の 10 進数、"a" ～ "f" の範囲の小文字、および "A" ～ "F" の範囲の大文字を指定するには、`[0-9a-fA-F]` を使用します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-193">For example, to specify the range of decimal digits from "0" through "9", the range of lowercase letters from "a" through "f", and the range of uppercase letters from "A" through "F", use `[0-9a-fA-F]`.</span></span>  
  
 <span data-ttu-id="31ab6-194">文字グループの否定における先頭のキャレット文字 (`^`) は、文字グループが文字グループの肯定ではなく文字グループの否定であることを示し、省略できません。</span><span class="sxs-lookup"><span data-stu-id="31ab6-194">The leading carat character (`^`) in a negative character group is mandatory and indicates the character group is a negative character group instead of a positive character group.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="31ab6-195">大規模な正規表現パターンにおける文字グループの否定は、ゼロ幅アサーションではありません。</span><span class="sxs-lookup"><span data-stu-id="31ab6-195">A negative character group in a larger regular expression pattern is not a zero-width assertion.</span></span> <span data-ttu-id="31ab6-196">つまり、正規表現エンジンは、文字グループの否定を評価した後に、入力文字列内で 1 文字進みます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-196">That is, after evaluating the negative character group, the regular expression engine advances one character in the input string.</span></span>  
  
 <span data-ttu-id="31ab6-197">文字グループの否定を含む一般的な正規表現パターンをいくつか次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-197">Some common regular expression patterns that contain negative character groups are listed in the following table.</span></span>  
  
|<span data-ttu-id="31ab6-198">パターン</span><span class="sxs-lookup"><span data-stu-id="31ab6-198">Pattern</span></span>|<span data-ttu-id="31ab6-199">説明</span><span class="sxs-lookup"><span data-stu-id="31ab6-199">Description</span></span>|  
|-------------|-----------------|  
|`[^aeiou]`|<span data-ttu-id="31ab6-200">母音を除くすべての文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-200">Match all characters except vowels.</span></span>|  
|`[^\p{P}\d]`|<span data-ttu-id="31ab6-201">句読点および 10 進数字を除くすべての文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-201">Match all characters except punctuation and decimal digit characters.</span></span>|  
  
 <span data-ttu-id="31ab6-202">次の例は、"th" という文字で始まってその後に "o" が続かない語と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-202">The following example matches any word that begins with the characters "th" and is not followed by an "o".</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/negativecharclasses.cs#2)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/negativecharclasses.vb#2)]  
  
 <span data-ttu-id="31ab6-203">正規表現 `\bth[^o]\w+\b` は、次の表に示すように定義されています。</span><span class="sxs-lookup"><span data-stu-id="31ab6-203">The regular expression `\bth[^o]\w+\b` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="31ab6-204">パターン</span><span class="sxs-lookup"><span data-stu-id="31ab6-204">Pattern</span></span>|<span data-ttu-id="31ab6-205">説明</span><span class="sxs-lookup"><span data-stu-id="31ab6-205">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="31ab6-206">ワード境界から開始します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-206">Start at a word boundary.</span></span>|  
|`th`|<span data-ttu-id="31ab6-207">リテラル文字 "th" と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-207">Match the literal characters "th".</span></span>|  
|`[^o]`|<span data-ttu-id="31ab6-208">"o" 以外の任意の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-208">Match any character that is not an "o".</span></span>|  
|`\w+`|<span data-ttu-id="31ab6-209">1 つ以上の単語文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-209">Match one or more word characters.</span></span>|  
|`\b`|<span data-ttu-id="31ab6-210">ワード境界で終了します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-210">End at a word boundary.</span></span>|  
  
<a name="AnyCharacter"></a>   
## <a name="any-character-"></a><span data-ttu-id="31ab6-211">任意の文字: .</span><span class="sxs-lookup"><span data-stu-id="31ab6-211">Any character: .</span></span>  
 <span data-ttu-id="31ab6-212">ピリオド文字 (.) は、`\n` (改行文字、\u000A) を除く任意の文字と一致しますが、次の 2 つの制限があります。</span><span class="sxs-lookup"><span data-stu-id="31ab6-212">The period character (.) matches any character except `\n` (the newline character, \u000A), with the following two qualifications:</span></span>  
  
- <span data-ttu-id="31ab6-213">正規表現パターンが <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> オプションで修飾されている場合、または `.` 文字クラスを含むパターンの一部が `s` オプションで修飾されている場合は、`.` は任意の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-213">If a regular expression pattern is modified by the <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> option, or if the portion of the pattern that contains the `.` character class is modified by the `s` option, `.` matches any character.</span></span> <span data-ttu-id="31ab6-214">詳細については、「 [正規表現のオプション](../../../docs/standard/base-types/regular-expression-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-214">For more information, see [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
     <span data-ttu-id="31ab6-215">`.` 文字クラスの既定の動作と <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> オプションが指定されている場合の動作の違いの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-215">The following example illustrates the different behavior of the `.` character class by default and with the <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> option.</span></span> <span data-ttu-id="31ab6-216">正規表現 `^.+` は文字列の先頭から開始し、すべての文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-216">The regular expression `^.+` starts at the beginning of the string and matches every character.</span></span> <span data-ttu-id="31ab6-217">既定では、照合は 1 行目の末尾で終了します。正規表現パターンは復帰文字 `\r` (\u000D) と一致しますが、`\n` とは一致しません。</span><span class="sxs-lookup"><span data-stu-id="31ab6-217">By default, the match ends at the end of the first line; the regular expression pattern matches the carriage return character, `\r` or \u000D, but it does not match `\n`.</span></span> <span data-ttu-id="31ab6-218"><xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> オプションは入力文字列全体を単一行として解釈するので、`\n` を含む入力文字列内のすべての文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-218">Because the <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> option interprets the entire input string as a single line, it matches every character in the input string, including `\n`.</span></span>  
  
     [!code-csharp[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/any2.cs#5)]
     [!code-vb[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/any2.vb#5)]  
  
> [!NOTE]
>  <span data-ttu-id="31ab6-219">`.` 文字クラスは `\n` を除く任意の文字と一致するので、このクラスも `\r` (復帰文字、\u000D) と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-219">Because it matches any character except `\n`, the `.` character class also matches `\r` (the carriage return character, \u000D).</span></span>  
  
- <span data-ttu-id="31ab6-220">文字グループの肯定または文字グループの否定に含まれているピリオドは、文字クラスではなくリテラルのピリオド文字として扱われます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-220">In a positive or negative character group, a period is treated as a literal period character, and not as a character class.</span></span> <span data-ttu-id="31ab6-221">詳細については、このトピックで前述した「[文字グループの肯定](#PositiveGroup)」および「[文字グループの否定](#NegativeGroup)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-221">For more information, see [Positive Character Group](#PositiveGroup) and [Negative Character Group](#NegativeGroup) earlier in this topic.</span></span> <span data-ttu-id="31ab6-222">ピリオド文字 (`.`) を文字クラスとしても文字グループの肯定のメンバーとしても含む正規表現を定義する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-222">The following example provides an illustration by defining a regular expression that includes the period character (`.`) both as a character class and as a member of a positive character group.</span></span> <span data-ttu-id="31ab6-223">正規表現 `\b.*[.?!;:](\s|\z)` はワード境界から開始し、ピリオドを含む 5 つの句読点のいずれかが検出されるまで任意の文字と一致し、空白文字または文字列の末尾と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-223">The regular expression `\b.*[.?!;:](\s|\z)` begins at a word boundary, matches any character until it encounters one of five punctuation marks, including a period, and then matches either a white-space character or the end of the string.</span></span>  
  
     [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/any1.cs#4)]
     [!code-vb[Conceptual.RegEx.Language.CharacterClasses#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/any1.vb#4)]  
  
> [!NOTE]
>  <span data-ttu-id="31ab6-224">`.` 言語要素は任意の文字と一致するので、正規表現パターンが任意の文字と複数回一致する場合に最短一致の量指定子と共によく使用されます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-224">Because it matches any character, the `.` language element is often used with a lazy quantifier if a regular expression pattern attempts to match any character multiple times.</span></span> <span data-ttu-id="31ab6-225">詳細については、「 [量指定子](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-225">For more information, see [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).</span></span>  
  
<a name="CategoryOrBlock"></a>   
## <a name="unicode-category-or-unicode-block-p"></a><span data-ttu-id="31ab6-226">Unicode カテゴリまたは Unicode ブロック: \p{}</span><span class="sxs-lookup"><span data-stu-id="31ab6-226">Unicode category or Unicode block: \p{}</span></span>  
 <span data-ttu-id="31ab6-227">Unicode 規格では、各文字に一般カテゴリが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="31ab6-227">The Unicode standard assigns each character a general category.</span></span> <span data-ttu-id="31ab6-228">たとえば、特定の文字は、英大文字 (`Lu` カテゴリで表されます)、10 進数 (`Nd` カテゴリ)、数学記号 (`Sm` カテゴリ)、または段落区切り記号 (`Zl` カテゴリ) に分類できます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-228">For example, a particular character can be an uppercase letter (represented by the `Lu` category), a decimal digit (the `Nd` category), a math symbol (the `Sm` category), or a paragraph separator (the `Zl` category).</span></span> <span data-ttu-id="31ab6-229">また、Unicode 規格の特定の文字セットは、特定の範囲またはブロックの連続したコード ポイントに対応します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-229">Specific character sets in the Unicode standard also occupy a specific range or block of consecutive code points.</span></span> <span data-ttu-id="31ab6-230">たとえば、基本的なラテン語文字セットは \u0000 ～ \u007F で、アラビア語文字セットは \u0600 ～ \u06FF です。</span><span class="sxs-lookup"><span data-stu-id="31ab6-230">For example, the basic Latin character set is found from \u0000 through \u007F, while the Arabic character set is found from \u0600 through \u06FF.</span></span>  
  
 <span data-ttu-id="31ab6-231">正規表現の構成要素</span><span class="sxs-lookup"><span data-stu-id="31ab6-231">The regular expression construct</span></span>  
  
 <span data-ttu-id="31ab6-232">`\p{` *name* `}`</span><span class="sxs-lookup"><span data-stu-id="31ab6-232">`\p{` *name* `}`</span></span>  
  
 <span data-ttu-id="31ab6-233">Unicode 一般カテゴリまたは名前付きブロックに属する任意の文字と一致します。ここで、*name* はカテゴリの省略形または名前付きブロックの名前です。</span><span class="sxs-lookup"><span data-stu-id="31ab6-233">matches any character that belongs to a Unicode general category or named block, where *name* is the category abbreviation or named block name.</span></span> <span data-ttu-id="31ab6-234">カテゴリの省略形の一覧については、このトピックで後述する「[サポートされている Unicode 一般カテゴリ](#SupportedUnicodeGeneralCategories)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-234">For a list of category abbreviations, see the [Supported Unicode General Categories](#SupportedUnicodeGeneralCategories) section later in this topic.</span></span> <span data-ttu-id="31ab6-235">名前付きブロックの一覧については、このトピックで後述する「[サポートされている名前付きブロック](#SupportedNamedBlocks)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-235">For a list of named blocks, see the [Supported Named Blocks](#SupportedNamedBlocks) section later in this topic.</span></span>  
  
 <span data-ttu-id="31ab6-236">`\p{`*name*`}` 構成要素を使用して Unicode 一般カテゴリ (この場合は `Pd` (Punctuation, Dash: 句読点、ダッシュ) カテゴリ) と名前付きブロック (`IsGreek` 名前付きブロックおよび `IsBasicLatin` 名前付きブロック) の両方を照合する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-236">The following example uses the `\p{`*name*`}` construct to match both a Unicode general category (in this case, the `Pd`, or Punctuation, Dash category) and a named block (the `IsGreek` and `IsBasicLatin` named blocks).</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/category1.cs#6)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/category1.vb#6)]  
  
 <span data-ttu-id="31ab6-237">正規表現 `\b(\p{IsGreek}+(\s)?)+\p{Pd}\s(\p{IsBasicLatin}+(\s)?)+` は、次の表に示すように定義されています。</span><span class="sxs-lookup"><span data-stu-id="31ab6-237">The regular expression `\b(\p{IsGreek}+(\s)?)+\p{Pd}\s(\p{IsBasicLatin}+(\s)?)+` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="31ab6-238">パターン</span><span class="sxs-lookup"><span data-stu-id="31ab6-238">Pattern</span></span>|<span data-ttu-id="31ab6-239">説明</span><span class="sxs-lookup"><span data-stu-id="31ab6-239">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="31ab6-240">ワード境界から開始します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-240">Start at a word boundary.</span></span>|  
|`\p{IsGreek}+`|<span data-ttu-id="31ab6-241">1 つ以上のギリシャ文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-241">Match one or more Greek characters.</span></span>|  
|`(\s)?`|<span data-ttu-id="31ab6-242">0 個または 1 個の空白文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-242">Match zero or one white-space character.</span></span>|  
|`(\p{IsGreek}+(\s)?)+`|<span data-ttu-id="31ab6-243">1 つ以上のギリシャ文字の後に 0 個または 1 個の空白文字が 1 回以上続くパターンに一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-243">Match the pattern of one or more Greek characters followed by zero or one white-space characters one or more times.</span></span>|  
|`\p{Pd}`|<span data-ttu-id="31ab6-244">Punctuation, Dash (句読点、ダッシュ) 文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-244">Match a Punctuation, Dash character.</span></span>|  
|`\s`|<span data-ttu-id="31ab6-245">空白文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-245">Match a white-space character.</span></span>|  
|`\p{IsBasicLatin}+`|<span data-ttu-id="31ab6-246">1 つ以上の基本的なラテン文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-246">Match one or more basic Latin characters.</span></span>|  
|`(\s)?`|<span data-ttu-id="31ab6-247">0 個または 1 個の空白文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-247">Match zero or one white-space character.</span></span>|  
|`(\p{IsBasicLatin}+(\s)?)+`|<span data-ttu-id="31ab6-248">1 つ以上の基本的なラテン文字の後に 0 個または 1 個の空白文字が 1 回以上続くパターンに一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-248">Match the pattern of one or more basic Latin characters followed by zero or one white-space characters one or more times.</span></span>|  
  
<a name="NegativeCategoryOrBlock"></a>   
## <a name="negative-unicode-category-or-unicode-block-p"></a><span data-ttu-id="31ab6-249">Unicode カテゴリまたは Unicode ブロックの否定: \P{}</span><span class="sxs-lookup"><span data-stu-id="31ab6-249">Negative Unicode category or Unicode block: \P{}</span></span>  
 <span data-ttu-id="31ab6-250">Unicode 規格では、各文字に一般カテゴリが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="31ab6-250">The Unicode standard assigns each character a general category.</span></span> <span data-ttu-id="31ab6-251">たとえば、特定の文字は、英大文字 (`Lu` カテゴリで表されます)、10 進数 (`Nd` カテゴリ)、数学記号 (`Sm` カテゴリ)、または段落区切り記号 (`Zl` カテゴリ) に分類できます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-251">For example, a particular character can be an uppercase letter (represented by the `Lu` category), a decimal digit (the `Nd` category), a math symbol (the `Sm` category), or a paragraph separator (the `Zl` category).</span></span> <span data-ttu-id="31ab6-252">また、Unicode 規格の特定の文字セットは、特定の範囲またはブロックの連続したコード ポイントに対応します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-252">Specific character sets in the Unicode standard also occupy a specific range or block of consecutive code points.</span></span> <span data-ttu-id="31ab6-253">たとえば、基本的なラテン語文字セットは \u0000 ～ \u007F で、アラビア語文字セットは \u0600 ～ \u06FF です。</span><span class="sxs-lookup"><span data-stu-id="31ab6-253">For example, the basic Latin character set is found from \u0000 through \u007F, while the Arabic character set is found from \u0600 through \u06FF.</span></span>  
  
 <span data-ttu-id="31ab6-254">正規表現の構成要素</span><span class="sxs-lookup"><span data-stu-id="31ab6-254">The regular expression construct</span></span>  
  
 <span data-ttu-id="31ab6-255">`\P{` *name* `}`</span><span class="sxs-lookup"><span data-stu-id="31ab6-255">`\P{` *name* `}`</span></span>  
  
 <span data-ttu-id="31ab6-256">Unicode 一般カテゴリにも名前付きブロックにも属さない任意の文字と一致します。ここで、*name* はカテゴリの省略形または名前付きブロックの名前です。</span><span class="sxs-lookup"><span data-stu-id="31ab6-256">matches any character that does not belong to a Unicode general category or named block, where *name* is the category abbreviation or named block name.</span></span> <span data-ttu-id="31ab6-257">カテゴリの省略形の一覧については、このトピックで後述する「[サポートされている Unicode 一般カテゴリ](#SupportedUnicodeGeneralCategories)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-257">For a list of category abbreviations, see the [Supported Unicode General Categories](#SupportedUnicodeGeneralCategories) section later in this topic.</span></span> <span data-ttu-id="31ab6-258">名前付きブロックの一覧については、このトピックで後述する「[サポートされている名前付きブロック](#SupportedNamedBlocks)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-258">For a list of named blocks, see the [Supported Named Blocks](#SupportedNamedBlocks) section later in this topic.</span></span>  
  
 <span data-ttu-id="31ab6-259">`\P{`*name*`}` 構成要素を使用して通貨記号 (この場合は `Sc` (Symbol, Currency: 記号、通貨) カテゴリ) を数値文字列から削除する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-259">The following example uses the `\P{`*name*`}` construct to remove any currency symbols (in this case, the `Sc`, or Symbol, Currency category) from numeric strings.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/notcategory1.cs#7)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/notcategory1.vb#7)]  
  
 <span data-ttu-id="31ab6-260">正規表現パターン `(\P{Sc})+` は、通貨記号以外の 1 つ以上の文字と一致し、実質的に結果文字列から通貨記号を削除します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-260">The regular expression pattern `(\P{Sc})+` matches one or more characters that are not currency symbols; it effectively strips any currency symbol from the result string.</span></span>  
  
<a name="WordCharacter"></a>   
## <a name="word-character-w"></a><span data-ttu-id="31ab6-261">単語に使用される文字: \w</span><span class="sxs-lookup"><span data-stu-id="31ab6-261">Word character: \w</span></span>  
 <span data-ttu-id="31ab6-262">`\w` は、単語に使用される任意の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-262">`\w` matches any word character.</span></span> <span data-ttu-id="31ab6-263">単語に使用される文字は、次の表に示す Unicode カテゴリのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="31ab6-263">A word character is a member of any of the Unicode categories listed in the following table.</span></span>  
  
|<span data-ttu-id="31ab6-264">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="31ab6-264">Category</span></span>|<span data-ttu-id="31ab6-265">説明</span><span class="sxs-lookup"><span data-stu-id="31ab6-265">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="31ab6-266">Ll</span><span class="sxs-lookup"><span data-stu-id="31ab6-266">Ll</span></span>|<span data-ttu-id="31ab6-267">Letter, Lowercase (字、小文字)</span><span class="sxs-lookup"><span data-stu-id="31ab6-267">Letter, Lowercase</span></span>|  
|<span data-ttu-id="31ab6-268">Lu</span><span class="sxs-lookup"><span data-stu-id="31ab6-268">Lu</span></span>|<span data-ttu-id="31ab6-269">Letter, Uppercase (字、大文字)</span><span class="sxs-lookup"><span data-stu-id="31ab6-269">Letter, Uppercase</span></span>|  
|<span data-ttu-id="31ab6-270">Lt</span><span class="sxs-lookup"><span data-stu-id="31ab6-270">Lt</span></span>|<span data-ttu-id="31ab6-271">Letter, Titlecase (字、タイトル文字)</span><span class="sxs-lookup"><span data-stu-id="31ab6-271">Letter, Titlecase</span></span>|  
|<span data-ttu-id="31ab6-272">Lo</span><span class="sxs-lookup"><span data-stu-id="31ab6-272">Lo</span></span>|<span data-ttu-id="31ab6-273">Letter, Other (字、その他)</span><span class="sxs-lookup"><span data-stu-id="31ab6-273">Letter, Other</span></span>|  
|<span data-ttu-id="31ab6-274">Lm</span><span class="sxs-lookup"><span data-stu-id="31ab6-274">Lm</span></span>|<span data-ttu-id="31ab6-275">Letter, Modifier (字、修飾)</span><span class="sxs-lookup"><span data-stu-id="31ab6-275">Letter, Modifier</span></span>|  
|<span data-ttu-id="31ab6-276">Mn</span><span class="sxs-lookup"><span data-stu-id="31ab6-276">Mn</span></span>|<span data-ttu-id="31ab6-277">Mark, Nonspacing (結合文字、幅なし)</span><span class="sxs-lookup"><span data-stu-id="31ab6-277">Mark, Nonspacing</span></span>|  
|<span data-ttu-id="31ab6-278">Nd</span><span class="sxs-lookup"><span data-stu-id="31ab6-278">Nd</span></span>|<span data-ttu-id="31ab6-279">Number, Decimal Digit (数、10 進数字)</span><span class="sxs-lookup"><span data-stu-id="31ab6-279">Number, Decimal Digit</span></span>|  
|<span data-ttu-id="31ab6-280">Pc</span><span class="sxs-lookup"><span data-stu-id="31ab6-280">Pc</span></span>|<span data-ttu-id="31ab6-281">Punctuation, Connector (句読点、接続)。</span><span class="sxs-lookup"><span data-stu-id="31ab6-281">Punctuation, Connector.</span></span> <span data-ttu-id="31ab6-282">このカテゴリには 10 文字が含まれ、そのうち最もよく使用される文字は LOWLINE 文字 (_)、u+005F です。</span><span class="sxs-lookup"><span data-stu-id="31ab6-282">This category includes ten characters, the most commonly used of which is the LOWLINE character (_), u+005F.</span></span>|  
  
 <span data-ttu-id="31ab6-283">ECMAScript 準拠の動作が指定された場合、`\w` は `[a-zA-Z_0-9]` と同じになります。</span><span class="sxs-lookup"><span data-stu-id="31ab6-283">If ECMAScript-compliant behavior is specified, `\w` is equivalent to `[a-zA-Z_0-9]`.</span></span> <span data-ttu-id="31ab6-284">ECMAScript 正規表現の詳細については、「[正規表現のオプション](../../../docs/standard/base-types/regular-expression-options.md)」の「ECMAScript 一致の動作」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-284">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31ab6-285">`\w` 言語要素は単語に使用される任意の文字と一致するので、正規表現パターンが単語に使用される任意の文字の後に特定の単語に使用される文字が続く語と複数回一致する場合に最短一致の量指定子と共によく使用されます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-285">Because it matches any word character, the `\w` language element is often used with a lazy quantifier if a regular expression pattern attempts to match any word character multiple times, followed by a specific word character.</span></span> <span data-ttu-id="31ab6-286">詳細については、「 [量指定子](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-286">For more information, see [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="31ab6-287">`\w` 言語要素を使用して単語内の重複する文字を照合する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-287">The following example uses the `\w` language element to match duplicate characters in a word.</span></span> <span data-ttu-id="31ab6-288">この例では、次のように解釈できる正規表現パターン `(\w)\1` を定義しています。</span><span class="sxs-lookup"><span data-stu-id="31ab6-288">The example defines a regular expression pattern, `(\w)\1`, which can be interpreted as follows.</span></span>  
  
|<span data-ttu-id="31ab6-289">要素</span><span class="sxs-lookup"><span data-stu-id="31ab6-289">Element</span></span>|<span data-ttu-id="31ab6-290">説明</span><span class="sxs-lookup"><span data-stu-id="31ab6-290">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="31ab6-291">(\w)</span><span class="sxs-lookup"><span data-stu-id="31ab6-291">(\w)</span></span>|<span data-ttu-id="31ab6-292">単語に使用される文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-292">Match a word character.</span></span> <span data-ttu-id="31ab6-293">これが最初のキャプチャ グループです。</span><span class="sxs-lookup"><span data-stu-id="31ab6-293">This is the first capturing group.</span></span>|  
|<span data-ttu-id="31ab6-294">\1</span><span class="sxs-lookup"><span data-stu-id="31ab6-294">\1</span></span>|<span data-ttu-id="31ab6-295">最初のキャプチャの値と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-295">Match the value of the first capture.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/wordchar1.cs#8)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/wordchar1.vb#8)]  
  
<a name="NonWordCharacter"></a>   
## <a name="non-word-character-w"></a><span data-ttu-id="31ab6-296">単語に使用されない文字: \W</span><span class="sxs-lookup"><span data-stu-id="31ab6-296">Non-word character: \W</span></span>  
 <span data-ttu-id="31ab6-297">`\W` は、単語に使用される文字以外の任意の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-297">`\W` matches any non-word character.</span></span> <span data-ttu-id="31ab6-298">\W 言語要素は、次の文字クラスと同じ結果をもたらします。</span><span class="sxs-lookup"><span data-stu-id="31ab6-298">The \W language element is equivalent to the following character class:</span></span>  
  
```  
[^\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}\p{Lm}]  
```  
  
 <span data-ttu-id="31ab6-299">つまり、次の表に示す Unicode カテゴリの文字を除く任意の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-299">In other words, it matches any character except for those in the Unicode categories listed in the following table.</span></span>  
  
|<span data-ttu-id="31ab6-300">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="31ab6-300">Category</span></span>|<span data-ttu-id="31ab6-301">説明</span><span class="sxs-lookup"><span data-stu-id="31ab6-301">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="31ab6-302">Ll</span><span class="sxs-lookup"><span data-stu-id="31ab6-302">Ll</span></span>|<span data-ttu-id="31ab6-303">Letter, Lowercase (字、小文字)</span><span class="sxs-lookup"><span data-stu-id="31ab6-303">Letter, Lowercase</span></span>|  
|<span data-ttu-id="31ab6-304">Lu</span><span class="sxs-lookup"><span data-stu-id="31ab6-304">Lu</span></span>|<span data-ttu-id="31ab6-305">Letter, Uppercase (字、大文字)</span><span class="sxs-lookup"><span data-stu-id="31ab6-305">Letter, Uppercase</span></span>|  
|<span data-ttu-id="31ab6-306">Lt</span><span class="sxs-lookup"><span data-stu-id="31ab6-306">Lt</span></span>|<span data-ttu-id="31ab6-307">Letter, Titlecase (字、タイトル文字)</span><span class="sxs-lookup"><span data-stu-id="31ab6-307">Letter, Titlecase</span></span>|  
|<span data-ttu-id="31ab6-308">Lo</span><span class="sxs-lookup"><span data-stu-id="31ab6-308">Lo</span></span>|<span data-ttu-id="31ab6-309">Letter, Other (字、その他)</span><span class="sxs-lookup"><span data-stu-id="31ab6-309">Letter, Other</span></span>|  
|<span data-ttu-id="31ab6-310">Lm</span><span class="sxs-lookup"><span data-stu-id="31ab6-310">Lm</span></span>|<span data-ttu-id="31ab6-311">Letter, Modifier (字、修飾)</span><span class="sxs-lookup"><span data-stu-id="31ab6-311">Letter, Modifier</span></span>|  
|<span data-ttu-id="31ab6-312">Mn</span><span class="sxs-lookup"><span data-stu-id="31ab6-312">Mn</span></span>|<span data-ttu-id="31ab6-313">Mark, Nonspacing (結合文字、幅なし)</span><span class="sxs-lookup"><span data-stu-id="31ab6-313">Mark, Nonspacing</span></span>|  
|<span data-ttu-id="31ab6-314">Nd</span><span class="sxs-lookup"><span data-stu-id="31ab6-314">Nd</span></span>|<span data-ttu-id="31ab6-315">Number, Decimal Digit (数、10 進数字)</span><span class="sxs-lookup"><span data-stu-id="31ab6-315">Number, Decimal Digit</span></span>|  
|<span data-ttu-id="31ab6-316">Pc</span><span class="sxs-lookup"><span data-stu-id="31ab6-316">Pc</span></span>|<span data-ttu-id="31ab6-317">Punctuation, Connector (句読点、接続)。</span><span class="sxs-lookup"><span data-stu-id="31ab6-317">Punctuation, Connector.</span></span> <span data-ttu-id="31ab6-318">このカテゴリには 10 文字が含まれ、そのうち最もよく使用される文字は LOWLINE 文字 (_)、u+005F です。</span><span class="sxs-lookup"><span data-stu-id="31ab6-318">This category includes ten characters, the most commonly used of which is the LOWLINE character (_), u+005F.</span></span>|  
  
 <span data-ttu-id="31ab6-319">ECMAScript 準拠の動作が指定された場合、`\W` は `[^a-zA-Z_0-9]` と同じになります。</span><span class="sxs-lookup"><span data-stu-id="31ab6-319">If ECMAScript-compliant behavior is specified, `\W` is equivalent to `[^a-zA-Z_0-9]`.</span></span> <span data-ttu-id="31ab6-320">ECMAScript 正規表現の詳細については、「[正規表現のオプション](../../../docs/standard/base-types/regular-expression-options.md)」の「ECMAScript 一致の動作」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-320">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31ab6-321">`\W` 言語要素は単語に使用されない任意の文字と一致するので、正規表現パターンが単語に使用されない任意の文字の後に特定の単語に使用されない文字が続く語と複数回一致する場合に最短一致の量指定子と共によく使用されます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-321">Because it matches any non-word character, the `\W` language element is often used with a lazy quantifier if a regular expression pattern attempts to match any non-word character multiple times followed by a specific non-word character.</span></span> <span data-ttu-id="31ab6-322">詳細については、「[正規表現での量指定子](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-322">For more information, see [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="31ab6-323">`\W` 文字クラスの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-323">The following example illustrates the `\W` character class.</span></span>  <span data-ttu-id="31ab6-324">この例では、単語の後に 1 つまたは 2 つの単語に使用されない文字 (空白や句読点など) が続く場合に一致する正規表現パターン `\b(\w+)(\W){1,2}` を定義しています。</span><span class="sxs-lookup"><span data-stu-id="31ab6-324">It defines a regular expression pattern, `\b(\w+)(\W){1,2}`, that matches a word followed by one or two non-word characters, such as white space or punctuation.</span></span> <span data-ttu-id="31ab6-325">この正規表現の解釈を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-325">The regular expression is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="31ab6-326">要素</span><span class="sxs-lookup"><span data-stu-id="31ab6-326">Element</span></span>|<span data-ttu-id="31ab6-327">説明</span><span class="sxs-lookup"><span data-stu-id="31ab6-327">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="31ab6-328">\b</span><span class="sxs-lookup"><span data-stu-id="31ab6-328">\b</span></span>|<span data-ttu-id="31ab6-329">ワード境界から照合を開始します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-329">Begin the match at a word boundary.</span></span>|  
|<span data-ttu-id="31ab6-330">(\w+)</span><span class="sxs-lookup"><span data-stu-id="31ab6-330">(\w+)</span></span>|<span data-ttu-id="31ab6-331">1 つ以上の単語文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-331">Match one or more word characters.</span></span> <span data-ttu-id="31ab6-332">これが最初のキャプチャ グループです。</span><span class="sxs-lookup"><span data-stu-id="31ab6-332">This is the first capturing group.</span></span>|  
|<span data-ttu-id="31ab6-333">(\W){1,2}</span><span class="sxs-lookup"><span data-stu-id="31ab6-333">(\W){1,2}</span></span>|<span data-ttu-id="31ab6-334">単語に使用されない文字と 1 回または 2 回一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-334">Match a non-word character either one or two times.</span></span> <span data-ttu-id="31ab6-335">これが 2 番目のキャプチャ グループです。</span><span class="sxs-lookup"><span data-stu-id="31ab6-335">This is the second capturing group.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nonwordchar1.cs#9)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nonwordchar1.vb#9)]  
  
 <span data-ttu-id="31ab6-336">2 番目のキャプチャ グループの <xref:System.Text.RegularExpressions.Group> オブジェクトには、キャプチャされた単語に使用されない文字が 1 つだけ含まれるので、この例では、<xref:System.Text.RegularExpressions.CaptureCollection> プロパティによって返される <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> オブジェクトから、キャプチャされたすべての単語に使用されない文字を取得します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-336">Because the <xref:System.Text.RegularExpressions.Group> object for the second capturing group contains only a single captured non-word character, the example retrieves all captured non-word characters from the <xref:System.Text.RegularExpressions.CaptureCollection> object that is returned by the <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> property.</span></span>  
  
<a name="WhitespaceCharacter"></a>   
## <a name="whitespace-character-s"></a><span data-ttu-id="31ab6-337">空白文字: \s</span><span class="sxs-lookup"><span data-stu-id="31ab6-337">Whitespace character: \s</span></span>  
 <span data-ttu-id="31ab6-338">`\s` は任意の空白文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-338">`\s` matches any whitespace character.</span></span> <span data-ttu-id="31ab6-339">次の表に示すエスケープ シーケンスおよび Unicode カテゴリと同じ結果をもたらします。</span><span class="sxs-lookup"><span data-stu-id="31ab6-339">It is equivalent to the escape sequences and Unicode categories listed in the following table.</span></span>  
  
|<span data-ttu-id="31ab6-340">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="31ab6-340">Category</span></span>|<span data-ttu-id="31ab6-341">説明</span><span class="sxs-lookup"><span data-stu-id="31ab6-341">Description</span></span>|  
|--------------|-----------------|  
|`\f`|<span data-ttu-id="31ab6-342">フォーム フィード文字 (\u000C)。</span><span class="sxs-lookup"><span data-stu-id="31ab6-342">The form feed character, \u000C.</span></span>|  
|`\n`|<span data-ttu-id="31ab6-343">改行文字 (\u000A)。</span><span class="sxs-lookup"><span data-stu-id="31ab6-343">The newline character, \u000A.</span></span>|  
|`\r`|<span data-ttu-id="31ab6-344">復帰文字 (\u000D)。</span><span class="sxs-lookup"><span data-stu-id="31ab6-344">The carriage return character, \u000D.</span></span>|  
|`\t`|<span data-ttu-id="31ab6-345">タブ文字 (\u0009)。</span><span class="sxs-lookup"><span data-stu-id="31ab6-345">The tab character, \u0009.</span></span>|  
|`\v`|<span data-ttu-id="31ab6-346">垂直タブ文字 (\u000B)。</span><span class="sxs-lookup"><span data-stu-id="31ab6-346">The vertical tab character, \u000B.</span></span>|  
|`\x85`|<span data-ttu-id="31ab6-347">省略記号または NEXT LINE (NEL) 文字 (…) (\u0085)。</span><span class="sxs-lookup"><span data-stu-id="31ab6-347">The ellipsis or NEXT LINE (NEL) character (…), \u0085.</span></span>|  
|`\p{Z}`|<span data-ttu-id="31ab6-348">任意の区切り記号と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-348">Matches any separator character.</span></span>|  
  
 <span data-ttu-id="31ab6-349">ECMAScript 準拠の動作が指定された場合、`\s` は `[ \f\n\r\t\v]` と同じになります。</span><span class="sxs-lookup"><span data-stu-id="31ab6-349">If ECMAScript-compliant behavior is specified, `\s` is equivalent to `[ \f\n\r\t\v]`.</span></span> <span data-ttu-id="31ab6-350">ECMAScript 正規表現の詳細については、「[正規表現のオプション](../../../docs/standard/base-types/regular-expression-options.md)」の「ECMAScript 一致の動作」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-350">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="31ab6-351">`\s` 文字クラスの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-351">The following example illustrates the `\s` character class.</span></span> <span data-ttu-id="31ab6-352">この例では、"s" または "es" で終わる単語の後に空白文字または入力文字列の末尾が続く場合に一致する正規表現パターン `\b\w+(e)?s(\s|$)` を定義しています。</span><span class="sxs-lookup"><span data-stu-id="31ab6-352">It defines a regular expression pattern, `\b\w+(e)?s(\s|$)`, that matches a word ending in either "s" or "es" followed by either a white-space character or the end of the input string.</span></span> <span data-ttu-id="31ab6-353">この正規表現の解釈を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-353">The regular expression is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="31ab6-354">要素</span><span class="sxs-lookup"><span data-stu-id="31ab6-354">Element</span></span>|<span data-ttu-id="31ab6-355">説明</span><span class="sxs-lookup"><span data-stu-id="31ab6-355">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="31ab6-356">\b</span><span class="sxs-lookup"><span data-stu-id="31ab6-356">\b</span></span>|<span data-ttu-id="31ab6-357">ワード境界から照合を開始します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-357">Begin the match at a word boundary.</span></span>|  
|<span data-ttu-id="31ab6-358">\w+</span><span class="sxs-lookup"><span data-stu-id="31ab6-358">\w+</span></span>|<span data-ttu-id="31ab6-359">1 つ以上の単語文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-359">Match one or more word characters.</span></span>|  
|<span data-ttu-id="31ab6-360">(e)?</span><span class="sxs-lookup"><span data-stu-id="31ab6-360">(e)?</span></span>|<span data-ttu-id="31ab6-361">"e" と 0 回または 1 回一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-361">Match an "e" either zero or one time.</span></span>|  
|<span data-ttu-id="31ab6-362">s</span><span class="sxs-lookup"><span data-stu-id="31ab6-362">s</span></span>|<span data-ttu-id="31ab6-363">"s" と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-363">Match an "s".</span></span>|  
|<span data-ttu-id="31ab6-364">(\s&#124;$)</span><span class="sxs-lookup"><span data-stu-id="31ab6-364">(\s&#124;$)</span></span>|<span data-ttu-id="31ab6-365">空白文字または入力文字列の末尾と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-365">Match either a white-space character or the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/whitespace1.cs#10)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/whitespace1.vb#10)]  
  
<a name="NonWhitespaceCharacter"></a>   
## <a name="non-whitespace-character-s"></a><span data-ttu-id="31ab6-366">空白以外の文字: \S</span><span class="sxs-lookup"><span data-stu-id="31ab6-366">Non-whitespace character: \S</span></span>  
 <span data-ttu-id="31ab6-367">`\S` は、空白文字以外の任意の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-367">`\S` matches any non-white-space character.</span></span> <span data-ttu-id="31ab6-368">`[^\f\n\r\t\v\x85\p{Z}]` 正規表現パターン、または空白文字と一致する `\s` に相当する正規表現パターンの逆と同じ結果をもたらします。</span><span class="sxs-lookup"><span data-stu-id="31ab6-368">It is equivalent to the `[^\f\n\r\t\v\x85\p{Z}]` regular expression pattern, or the opposite of the regular expression pattern that is equivalent to `\s`, which matches white-space characters.</span></span> <span data-ttu-id="31ab6-369">詳細については、「[空白文字: \s](#WhitespaceCharacter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-369">For more information, see [White-Space Character: \s](#WhitespaceCharacter).</span></span>  
  
 <span data-ttu-id="31ab6-370">ECMAScript 準拠の動作が指定された場合、`\S` は `[^ \f\n\r\t\v]` と同じになります。</span><span class="sxs-lookup"><span data-stu-id="31ab6-370">If ECMAScript-compliant behavior is specified, `\S` is equivalent to  `[^ \f\n\r\t\v]`.</span></span> <span data-ttu-id="31ab6-371">ECMAScript 正規表現の詳細については、「[正規表現のオプション](../../../docs/standard/base-types/regular-expression-options.md)」の「ECMAScript 一致の動作」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-371">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="31ab6-372">`\S` 言語要素の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-372">The following example illustrates the `\S` language element.</span></span> <span data-ttu-id="31ab6-373">正規表現パターン `\b(\S+)\s?` は、空白文字で区切られた文字列と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-373">The regular expression pattern `\b(\S+)\s?` matches strings that are delimited by white-space characters.</span></span> <span data-ttu-id="31ab6-374">一致部分の <xref:System.Text.RegularExpressions.GroupCollection> オブジェクトの 2 番目の要素に一致する文字列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-374">The second element in the match's <xref:System.Text.RegularExpressions.GroupCollection> object contains the matched string.</span></span> <span data-ttu-id="31ab6-375">この正規表現の解釈を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-375">The regular expression can be interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="31ab6-376">要素</span><span class="sxs-lookup"><span data-stu-id="31ab6-376">Element</span></span>|<span data-ttu-id="31ab6-377">説明</span><span class="sxs-lookup"><span data-stu-id="31ab6-377">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="31ab6-378">ワード境界から照合を開始します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-378">Begin the match at a word boundary.</span></span>|  
|`(\S+)`|<span data-ttu-id="31ab6-379">1 つ以上の空白以外の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-379">Match one or more non-white-space characters.</span></span> <span data-ttu-id="31ab6-380">これが最初のキャプチャ グループです。</span><span class="sxs-lookup"><span data-stu-id="31ab6-380">This is the first capturing group.</span></span>|  
|`\s?`|<span data-ttu-id="31ab6-381">0 個または 1 個の空白文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-381">Match zero or one white-space character.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nonwhitespace1.cs#11)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nonwhitespace1.vb#11)]  
  
<a name="DigitCharacter"></a>   
## <a name="decimal-digit-character-d"></a><span data-ttu-id="31ab6-382">10 進数字: \d</span><span class="sxs-lookup"><span data-stu-id="31ab6-382">Decimal digit character: \d</span></span>  
 <span data-ttu-id="31ab6-383">`\d` は、10 進数字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-383">`\d` matches any decimal digit.</span></span> <span data-ttu-id="31ab6-384">標準の 10 進数 0 ～ 9 およびその他の各種文字セットの 10 進数を含む `\p{Nd}` 正規表現パターンと同じ結果をもたらします。</span><span class="sxs-lookup"><span data-stu-id="31ab6-384">It is equivalent to the `\p{Nd}` regular expression pattern, which includes the standard decimal digits 0-9 as well as the decimal digits of a number of other character sets.</span></span>  
  
 <span data-ttu-id="31ab6-385">ECMAScript 準拠の動作が指定された場合、`\d` は `[0-9]` と同じになります。</span><span class="sxs-lookup"><span data-stu-id="31ab6-385">If ECMAScript-compliant behavior is specified, `\d` is equivalent to  `[0-9]`.</span></span> <span data-ttu-id="31ab6-386">ECMAScript 正規表現の詳細については、「[正規表現のオプション](../../../docs/standard/base-types/regular-expression-options.md)」の「ECMAScript 一致の動作」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-386">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="31ab6-387">`\d` 言語要素の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-387">The following example illustrates the `\d` language element.</span></span> <span data-ttu-id="31ab6-388">この例では、入力文字列が米国およびカナダの有効な電話番号を表すかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="31ab6-388">It tests whether an input string represents a valid telephone number in the United States and Canada.</span></span> <span data-ttu-id="31ab6-389">正規表現パターン `^(\(?\d{3}\)?[\s-])?\d{3}-\d{4}$` は、次の表に示すように定義されています。</span><span class="sxs-lookup"><span data-stu-id="31ab6-389">The regular expression pattern `^(\(?\d{3}\)?[\s-])?\d{3}-\d{4}$` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="31ab6-390">要素</span><span class="sxs-lookup"><span data-stu-id="31ab6-390">Element</span></span>|<span data-ttu-id="31ab6-391">説明</span><span class="sxs-lookup"><span data-stu-id="31ab6-391">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="31ab6-392">入力文字列の先頭から照合を開始します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-392">Begin the match at the beginning of the input string.</span></span>|  
|`\(?`|<span data-ttu-id="31ab6-393">0 個または 1 個のリテラル "(" 文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-393">Match zero or one literal "(" character.</span></span>|  
|`\d{3}`|<span data-ttu-id="31ab6-394">3 個の 10 進数と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-394">Match three decimal digits.</span></span>|  
|`\)?`|<span data-ttu-id="31ab6-395">0 個または 1 個のリテラル ")" 文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-395">Match zero or one literal ")" character.</span></span>|  
|`[\s-]`|<span data-ttu-id="31ab6-396">ハイフンまたは空白文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-396">Match a hyphen or a white-space character.</span></span>|  
|`(\(?\d{3}\)?[\s-])?`|<span data-ttu-id="31ab6-397">省略可能な左かっこの後に 3 個の 10 進数が続く部分、省略可能な右かっこ、および空白文字またはハイフンと 0 回または 1 回一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-397">Match an optional opening parenthesis followed by three decimal digits, an optional closing parenthesis, and either a white-space character or a hyphen zero or one time.</span></span> <span data-ttu-id="31ab6-398">これが最初のキャプチャ グループです。</span><span class="sxs-lookup"><span data-stu-id="31ab6-398">This is the first capturing group.</span></span>|  
|`\d{3}-\d{4}`|<span data-ttu-id="31ab6-399">3 個の 10 進数の後にハイフンおよび 4 個以上の 10 進数が続く場合に一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-399">Match three decimal digits followed by a hyphen and four more decimal digits.</span></span>|  
|`$`|<span data-ttu-id="31ab6-400">入力文字列の末尾と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-400">Match the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/digit1.cs#12)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/digit1.vb#12)]  
  
<a name="NonDigitCharacter"></a>   
## <a name="non-digit-character-d"></a><span data-ttu-id="31ab6-401">数字以外の文字: \D</span><span class="sxs-lookup"><span data-stu-id="31ab6-401">Non-digit character: \D</span></span>  
 <span data-ttu-id="31ab6-402">`\D` は、数字以外の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-402">`\D` matches any non-digit character.</span></span> <span data-ttu-id="31ab6-403">`\P{Nd}` 正規表現パターンと同じ結果をもたらします。</span><span class="sxs-lookup"><span data-stu-id="31ab6-403">It is equivalent to the `\P{Nd}` regular expression pattern.</span></span>  
  
 <span data-ttu-id="31ab6-404">ECMAScript 準拠の動作が指定された場合、`\D` は `[^0-9]` と同じになります。</span><span class="sxs-lookup"><span data-stu-id="31ab6-404">If ECMAScript-compliant behavior is specified, `\D` is equivalent to  `[^0-9]`.</span></span> <span data-ttu-id="31ab6-405">ECMAScript 正規表現の詳細については、「[正規表現のオプション](../../../docs/standard/base-types/regular-expression-options.md)」の「ECMAScript 一致の動作」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-405">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="31ab6-406">\D 言語要素の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-406">The following example illustrates the \D language element.</span></span> <span data-ttu-id="31ab6-407">部品番号などの文字列が 10 進数および 10 進数以外の文字を適切に組み合わせて構成されているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="31ab6-407">It tests whether a string such as a part number consists of the appropriate combination of decimal and non-decimal characters.</span></span> <span data-ttu-id="31ab6-408">正規表現パターン `^\D\d{1,5}\D*$` は、次の表に示すように定義されています。</span><span class="sxs-lookup"><span data-stu-id="31ab6-408">The regular expression pattern `^\D\d{1,5}\D*$` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="31ab6-409">要素</span><span class="sxs-lookup"><span data-stu-id="31ab6-409">Element</span></span>|<span data-ttu-id="31ab6-410">説明</span><span class="sxs-lookup"><span data-stu-id="31ab6-410">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="31ab6-411">入力文字列の先頭から照合を開始します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-411">Begin the match at the beginning of the input string.</span></span>|  
|`\D`|<span data-ttu-id="31ab6-412">数字以外の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-412">Match a non-digit character.</span></span>|  
|`\d{1,5}`|<span data-ttu-id="31ab6-413">1 ～ 5 個の 10 進数と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-413">Match from one to five decimal digits.</span></span>|  
|`\D*`|<span data-ttu-id="31ab6-414">0 個または 1 個以上の 10 進数以外の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-414">Match zero, one, or more non-decimal characters.</span></span>|  
|`$`|<span data-ttu-id="31ab6-415">入力文字列の末尾と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-415">Match the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nondigit1.cs#13)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nondigit1.vb#13)]  
  
<a name="SupportedUnicodeGeneralCategories"></a>   
## <a name="supported-unicode-general-categories"></a><span data-ttu-id="31ab6-416">サポートされている Unicode 一般カテゴリ</span><span class="sxs-lookup"><span data-stu-id="31ab6-416">Supported Unicode general categories</span></span>  
 <span data-ttu-id="31ab6-417">Unicode は、次の表に示されている一般カテゴリを定義しています。</span><span class="sxs-lookup"><span data-stu-id="31ab6-417">Unicode defines the general categories listed in the following table.</span></span> <span data-ttu-id="31ab6-418">詳細については、「[Unicode Character Database (Unicode 文字データベース)](https://www.unicode.org/reports/tr44/)」内の「UCD File Format (UCD ファイル形式)」および「General Category Values (一般カテゴリの値)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-418">For more information, see the "UCD File Format" and "General Category Values" subtopics at the [Unicode Character Database](https://www.unicode.org/reports/tr44/).</span></span>  
  
|<span data-ttu-id="31ab6-419">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="31ab6-419">Category</span></span>|<span data-ttu-id="31ab6-420">説明</span><span class="sxs-lookup"><span data-stu-id="31ab6-420">Description</span></span>|  
|--------------|-----------------|  
|`Lu`|<span data-ttu-id="31ab6-421">Letter, Uppercase (字、大文字)</span><span class="sxs-lookup"><span data-stu-id="31ab6-421">Letter, Uppercase</span></span>|  
|`Ll`|<span data-ttu-id="31ab6-422">Letter, Lowercase (字、小文字)</span><span class="sxs-lookup"><span data-stu-id="31ab6-422">Letter, Lowercase</span></span>|  
|`Lt`|<span data-ttu-id="31ab6-423">Letter, Titlecase (字、タイトル文字)</span><span class="sxs-lookup"><span data-stu-id="31ab6-423">Letter, Titlecase</span></span>|  
|`Lm`|<span data-ttu-id="31ab6-424">Letter, Modifier (字、修飾)</span><span class="sxs-lookup"><span data-stu-id="31ab6-424">Letter, Modifier</span></span>|  
|`Lo`|<span data-ttu-id="31ab6-425">Letter, Other (字、その他)</span><span class="sxs-lookup"><span data-stu-id="31ab6-425">Letter, Other</span></span>|  
|`L`|<span data-ttu-id="31ab6-426">すべてのアルファベット文字。</span><span class="sxs-lookup"><span data-stu-id="31ab6-426">All letter characters.</span></span> <span data-ttu-id="31ab6-427">これには、`Lu`、`Ll`、`Lt`、`Lm`、および `Lo` の各文字が含まれます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-427">This includes the `Lu`, `Ll`, `Lt`, `Lm`, and `Lo` characters.</span></span>|  
|`Mn`|<span data-ttu-id="31ab6-428">Mark, Nonspacing (結合文字、幅なし)</span><span class="sxs-lookup"><span data-stu-id="31ab6-428">Mark, Nonspacing</span></span>|  
|`Mc`|<span data-ttu-id="31ab6-429">Mark, Spacing Combining (結合文字、幅あり)</span><span class="sxs-lookup"><span data-stu-id="31ab6-429">Mark, Spacing Combining</span></span>|  
|`Me`|<span data-ttu-id="31ab6-430">Mark, Enclosing (結合文字、囲み)</span><span class="sxs-lookup"><span data-stu-id="31ab6-430">Mark, Enclosing</span></span>|  
|`M`|<span data-ttu-id="31ab6-431">すべての分音記号。</span><span class="sxs-lookup"><span data-stu-id="31ab6-431">All diacritic marks.</span></span> <span data-ttu-id="31ab6-432">これには、`Mn`、`Mc`、および `Me` の各カテゴリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-432">This includes the `Mn`, `Mc`, and `Me` categories.</span></span>|  
|`Nd`|<span data-ttu-id="31ab6-433">Number, Decimal Digit (数、10 進数字)</span><span class="sxs-lookup"><span data-stu-id="31ab6-433">Number, Decimal Digit</span></span>|  
|`Nl`|<span data-ttu-id="31ab6-434">Number, Letter (数、字)</span><span class="sxs-lookup"><span data-stu-id="31ab6-434">Number, Letter</span></span>|  
|`No`|<span data-ttu-id="31ab6-435">Number, Other (数、その他)</span><span class="sxs-lookup"><span data-stu-id="31ab6-435">Number, Other</span></span>|  
|`N`|<span data-ttu-id="31ab6-436">すべての数。</span><span class="sxs-lookup"><span data-stu-id="31ab6-436">All numbers.</span></span> <span data-ttu-id="31ab6-437">これには、`Nd`、`Nl`、および `No` の各カテゴリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-437">This includes the `Nd`, `Nl`, and `No` categories.</span></span>|  
|`Pc`|<span data-ttu-id="31ab6-438">Punctuation, Connector (句読点、接続)</span><span class="sxs-lookup"><span data-stu-id="31ab6-438">Punctuation, Connector</span></span>|  
|`Pd`|<span data-ttu-id="31ab6-439">Punctuation, Dash (句読点、ダッシュ)</span><span class="sxs-lookup"><span data-stu-id="31ab6-439">Punctuation, Dash</span></span>|  
|`Ps`|<span data-ttu-id="31ab6-440">Punctuation, Open (句読点、開き)</span><span class="sxs-lookup"><span data-stu-id="31ab6-440">Punctuation, Open</span></span>|  
|`Pe`|<span data-ttu-id="31ab6-441">Punctuation, Close (句読点、閉じ)</span><span class="sxs-lookup"><span data-stu-id="31ab6-441">Punctuation, Close</span></span>|  
|`Pi`|<span data-ttu-id="31ab6-442">Punctuation, Initial quote (句読点、開始引用符。使用状況に応じて Ps または Pe のように動作)</span><span class="sxs-lookup"><span data-stu-id="31ab6-442">Punctuation, Initial quote (may behave like Ps or Pe depending on usage)</span></span>|  
|`Pf`|<span data-ttu-id="31ab6-443">Punctuation, Final quote (句読点、終了引用符。使用状況に応じて Ps または Pe のように動作)</span><span class="sxs-lookup"><span data-stu-id="31ab6-443">Punctuation, Final quote (may behave like Ps or Pe depending on usage)</span></span>|  
|`Po`|<span data-ttu-id="31ab6-444">Punctuation, Other (句読点、その他)</span><span class="sxs-lookup"><span data-stu-id="31ab6-444">Punctuation, Other</span></span>|  
|`P`|<span data-ttu-id="31ab6-445">すべての句読点。</span><span class="sxs-lookup"><span data-stu-id="31ab6-445">All punctuation characters.</span></span> <span data-ttu-id="31ab6-446">これには、`Pc`、`Pd`、`Ps`、`Pe`、`Pi`、`Pf`、および `Po` の各カテゴリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-446">This includes the `Pc`, `Pd`, `Ps`, `Pe`, `Pi`, `Pf`, and `Po` categories.</span></span>|  
|`Sm`|<span data-ttu-id="31ab6-447">Symbol, Math (記号、数学)</span><span class="sxs-lookup"><span data-stu-id="31ab6-447">Symbol, Math</span></span>|  
|`Sc`|<span data-ttu-id="31ab6-448">Symbol, Currency (記号、通貨)</span><span class="sxs-lookup"><span data-stu-id="31ab6-448">Symbol, Currency</span></span>|  
|`Sk`|<span data-ttu-id="31ab6-449">Symbol, Modifier (記号、修飾)</span><span class="sxs-lookup"><span data-stu-id="31ab6-449">Symbol, Modifier</span></span>|  
|`So`|<span data-ttu-id="31ab6-450">Symbol, Other (記号、その他)</span><span class="sxs-lookup"><span data-stu-id="31ab6-450">Symbol, Other</span></span>|  
|`S`|<span data-ttu-id="31ab6-451">すべての記号。</span><span class="sxs-lookup"><span data-stu-id="31ab6-451">All symbols.</span></span> <span data-ttu-id="31ab6-452">これには、`Sm`、`Sc`、`Sk`、および `So` の各カテゴリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-452">This includes the `Sm`, `Sc`, `Sk`, and `So` categories.</span></span>|  
|`Zs`|<span data-ttu-id="31ab6-453">Separator, Space (区切り、空白)</span><span class="sxs-lookup"><span data-stu-id="31ab6-453">Separator, Space</span></span>|  
|`Zl`|<span data-ttu-id="31ab6-454">Separator, Line (区切り、行)</span><span class="sxs-lookup"><span data-stu-id="31ab6-454">Separator, Line</span></span>|  
|`Zp`|<span data-ttu-id="31ab6-455">Separator, Paragraph (区切り、段落)</span><span class="sxs-lookup"><span data-stu-id="31ab6-455">Separator, Paragraph</span></span>|  
|`Z`|<span data-ttu-id="31ab6-456">すべての区切り記号。</span><span class="sxs-lookup"><span data-stu-id="31ab6-456">All separator characters.</span></span> <span data-ttu-id="31ab6-457">これには、`Zs`、`Zl`、および `Zp` の各カテゴリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-457">This includes the `Zs`, `Zl`, and `Zp` categories.</span></span>|  
|`Cc`|<span data-ttu-id="31ab6-458">Other, Control (区切り、制御)</span><span class="sxs-lookup"><span data-stu-id="31ab6-458">Other, Control</span></span>|  
|`Cf`|<span data-ttu-id="31ab6-459">Other, Format (その他、書式)</span><span class="sxs-lookup"><span data-stu-id="31ab6-459">Other, Format</span></span>|  
|`Cs`|<span data-ttu-id="31ab6-460">Other, Surrogate (その他、サロゲート)</span><span class="sxs-lookup"><span data-stu-id="31ab6-460">Other, Surrogate</span></span>|  
|`Co`|<span data-ttu-id="31ab6-461">Other, Private Use (その他、プライベート用途)</span><span class="sxs-lookup"><span data-stu-id="31ab6-461">Other, Private Use</span></span>|  
|`Cn`|<span data-ttu-id="31ab6-462">Other, Not Assigned (その他、未割り当て。このプロパティを持つ文字はありません)</span><span class="sxs-lookup"><span data-stu-id="31ab6-462">Other, Not Assigned (no characters have this property)</span></span>|  
|`C`|<span data-ttu-id="31ab6-463">すべての制御文字。</span><span class="sxs-lookup"><span data-stu-id="31ab6-463">All control characters.</span></span> <span data-ttu-id="31ab6-464">これには、`Cc`、`Cf`、`Cs`、`Co`、および `Cn` の各カテゴリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-464">This includes the `Cc`, `Cf`, `Cs`, `Co`, and `Cn` categories.</span></span>|  
  
 <span data-ttu-id="31ab6-465">特定の文字の Unicode カテゴリを確認するには、その文字を <xref:System.Char.GetUnicodeCategory%2A> メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-465">You can determine the Unicode category of any particular character by passing that character to the <xref:System.Char.GetUnicodeCategory%2A> method.</span></span> <span data-ttu-id="31ab6-466"><xref:System.Char.GetUnicodeCategory%2A> メソッドを使用して、選択したラテン文字を含む配列の各要素のカテゴリを確認する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-466">The following example uses the <xref:System.Char.GetUnicodeCategory%2A> method to determine the category of each element in an array that contains selected Latin characters.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/getunicodecategory1.cs#14)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/getunicodecategory1.vb#14)]  
  
<a name="SupportedNamedBlocks"></a>   
## <a name="supported-named-blocks"></a><span data-ttu-id="31ab6-467">サポートされている名前付きブロック</span><span class="sxs-lookup"><span data-stu-id="31ab6-467">Supported named blocks</span></span>

<span data-ttu-id="31ab6-468">.NET には、次の表に示す名前付きブロックが用意されています。</span><span class="sxs-lookup"><span data-stu-id="31ab6-468">.NET provides the named blocks listed in the following table.</span></span> <span data-ttu-id="31ab6-469">サポートされている一連の名前付きブロックは、Unicode 4.0 および Perl 5.6 に基づいています。</span><span class="sxs-lookup"><span data-stu-id="31ab6-469">The set of supported named blocks is based on Unicode 4.0 and Perl 5.6.</span></span> <span data-ttu-id="31ab6-470">名前付きブロックを使用する正規表現については、「[Unicode カテゴリまたは Unicode ブロック: \\p{}](#unicode-category-or-unicode-block-p)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-470">For a regular expression that uses named blocks, see the [Unicode category or Unicode block: \\p{}](#unicode-category-or-unicode-block-p) section.</span></span>  
  
|<span data-ttu-id="31ab6-471">コード ポイント範囲</span><span class="sxs-lookup"><span data-stu-id="31ab6-471">Code point range</span></span>|<span data-ttu-id="31ab6-472">ブロック名</span><span class="sxs-lookup"><span data-stu-id="31ab6-472">Block name</span></span>|  
|----------------------|----------------|  
|<span data-ttu-id="31ab6-473">0000 ～ 007F</span><span class="sxs-lookup"><span data-stu-id="31ab6-473">0000 - 007F</span></span>|`IsBasicLatin`|  
|<span data-ttu-id="31ab6-474">0080 ～ 00FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-474">0080 - 00FF</span></span>|`IsLatin-1Supplement`|  
|<span data-ttu-id="31ab6-475">0100 ～ 017F</span><span class="sxs-lookup"><span data-stu-id="31ab6-475">0100 - 017F</span></span>|`IsLatinExtended-A`|  
|<span data-ttu-id="31ab6-476">0180 ～ 024F</span><span class="sxs-lookup"><span data-stu-id="31ab6-476">0180 - 024F</span></span>|`IsLatinExtended-B`|  
|<span data-ttu-id="31ab6-477">0250 ～ 02AF</span><span class="sxs-lookup"><span data-stu-id="31ab6-477">0250 - 02AF</span></span>|`IsIPAExtensions`|  
|<span data-ttu-id="31ab6-478">02B0 ～ 02FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-478">02B0 - 02FF</span></span>|`IsSpacingModifierLetters`|  
|<span data-ttu-id="31ab6-479">0300 ～ 036F</span><span class="sxs-lookup"><span data-stu-id="31ab6-479">0300 - 036F</span></span>|`IsCombiningDiacriticalMarks`|  
|<span data-ttu-id="31ab6-480">0370 ～ 03FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-480">0370 - 03FF</span></span>|`IsGreek`<br /><br /> <span data-ttu-id="31ab6-481">- または -</span><span class="sxs-lookup"><span data-stu-id="31ab6-481">-or-</span></span><br /><br /> `IsGreekandCoptic`|  
|<span data-ttu-id="31ab6-482">0400 ～ 04FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-482">0400 - 04FF</span></span>|`IsCyrillic`|  
|<span data-ttu-id="31ab6-483">0500 ～ 052F</span><span class="sxs-lookup"><span data-stu-id="31ab6-483">0500 - 052F</span></span>|`IsCyrillicSupplement`|  
|<span data-ttu-id="31ab6-484">0530 ～ 058F</span><span class="sxs-lookup"><span data-stu-id="31ab6-484">0530 - 058F</span></span>|`IsArmenian`|  
|<span data-ttu-id="31ab6-485">0590 ～ 05FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-485">0590 - 05FF</span></span>|`IsHebrew`|  
|<span data-ttu-id="31ab6-486">0600 ～ 06FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-486">0600 - 06FF</span></span>|`IsArabic`|  
|<span data-ttu-id="31ab6-487">0700 ～ 074F</span><span class="sxs-lookup"><span data-stu-id="31ab6-487">0700 - 074F</span></span>|`IsSyriac`|  
|<span data-ttu-id="31ab6-488">0780 ～ 07BF</span><span class="sxs-lookup"><span data-stu-id="31ab6-488">0780 - 07BF</span></span>|`IsThaana`|  
|<span data-ttu-id="31ab6-489">0900 ～ 097F</span><span class="sxs-lookup"><span data-stu-id="31ab6-489">0900 - 097F</span></span>|`IsDevanagari`|  
|<span data-ttu-id="31ab6-490">0980 ～ 09FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-490">0980 - 09FF</span></span>|`IsBengali`|  
|<span data-ttu-id="31ab6-491">0A00 ～ 0A7F</span><span class="sxs-lookup"><span data-stu-id="31ab6-491">0A00 - 0A7F</span></span>|`IsGurmukhi`|  
|<span data-ttu-id="31ab6-492">0A80 ～ 0AFF</span><span class="sxs-lookup"><span data-stu-id="31ab6-492">0A80 - 0AFF</span></span>|`IsGujarati`|  
|<span data-ttu-id="31ab6-493">0B00 ～ 0B7F</span><span class="sxs-lookup"><span data-stu-id="31ab6-493">0B00 - 0B7F</span></span>|`IsOriya`|  
|<span data-ttu-id="31ab6-494">0B80 ～ 0BFF</span><span class="sxs-lookup"><span data-stu-id="31ab6-494">0B80 - 0BFF</span></span>|`IsTamil`|  
|<span data-ttu-id="31ab6-495">0C00 ～ 0C7F</span><span class="sxs-lookup"><span data-stu-id="31ab6-495">0C00 - 0C7F</span></span>|`IsTelugu`|  
|<span data-ttu-id="31ab6-496">0C80 ～ 0CFF</span><span class="sxs-lookup"><span data-stu-id="31ab6-496">0C80 - 0CFF</span></span>|`IsKannada`|  
|<span data-ttu-id="31ab6-497">0D00 ～ 0D7F</span><span class="sxs-lookup"><span data-stu-id="31ab6-497">0D00 - 0D7F</span></span>|`IsMalayalam`|  
|<span data-ttu-id="31ab6-498">0D80 ～ 0DFF</span><span class="sxs-lookup"><span data-stu-id="31ab6-498">0D80 - 0DFF</span></span>|`IsSinhala`|  
|<span data-ttu-id="31ab6-499">0E00 ～ 0E7F</span><span class="sxs-lookup"><span data-stu-id="31ab6-499">0E00 - 0E7F</span></span>|`IsThai`|  
|<span data-ttu-id="31ab6-500">0E80 ～ 0EFF</span><span class="sxs-lookup"><span data-stu-id="31ab6-500">0E80 - 0EFF</span></span>|`IsLao`|  
|<span data-ttu-id="31ab6-501">0F00 ～ 0FFF</span><span class="sxs-lookup"><span data-stu-id="31ab6-501">0F00 - 0FFF</span></span>|`IsTibetan`|  
|<span data-ttu-id="31ab6-502">1000 ～ 109F</span><span class="sxs-lookup"><span data-stu-id="31ab6-502">1000 - 109F</span></span>|`IsMyanmar`|  
|<span data-ttu-id="31ab6-503">10A0 ～ 10FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-503">10A0 - 10FF</span></span>|`IsGeorgian`|  
|<span data-ttu-id="31ab6-504">1100 ～ 11FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-504">1100 - 11FF</span></span>|`IsHangulJamo`|  
|<span data-ttu-id="31ab6-505">1200 ～ 137F</span><span class="sxs-lookup"><span data-stu-id="31ab6-505">1200 - 137F</span></span>|`IsEthiopic`|  
|<span data-ttu-id="31ab6-506">13A0 ～ 13FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-506">13A0 - 13FF</span></span>|`IsCherokee`|  
|<span data-ttu-id="31ab6-507">1400 ～ 167F</span><span class="sxs-lookup"><span data-stu-id="31ab6-507">1400 - 167F</span></span>|`IsUnifiedCanadianAboriginalSyllabics`|  
|<span data-ttu-id="31ab6-508">1680 ～ 169F</span><span class="sxs-lookup"><span data-stu-id="31ab6-508">1680 - 169F</span></span>|`IsOgham`|  
|<span data-ttu-id="31ab6-509">16A0 ～ 16FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-509">16A0 - 16FF</span></span>|`IsRunic`|  
|<span data-ttu-id="31ab6-510">1700 ～ 171F</span><span class="sxs-lookup"><span data-stu-id="31ab6-510">1700 - 171F</span></span>|`IsTagalog`|  
|<span data-ttu-id="31ab6-511">1720 ～ 173F</span><span class="sxs-lookup"><span data-stu-id="31ab6-511">1720 - 173F</span></span>|`IsHanunoo`|  
|<span data-ttu-id="31ab6-512">1740 ～ 175F</span><span class="sxs-lookup"><span data-stu-id="31ab6-512">1740 - 175F</span></span>|`IsBuhid`|  
|<span data-ttu-id="31ab6-513">1760 ～ 177F</span><span class="sxs-lookup"><span data-stu-id="31ab6-513">1760 - 177F</span></span>|`IsTagbanwa`|  
|<span data-ttu-id="31ab6-514">1780 ～ 17FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-514">1780 - 17FF</span></span>|`IsKhmer`|  
|<span data-ttu-id="31ab6-515">1800 ～ 18AF</span><span class="sxs-lookup"><span data-stu-id="31ab6-515">1800 - 18AF</span></span>|`IsMongolian`|  
|<span data-ttu-id="31ab6-516">1900 ～ 194F</span><span class="sxs-lookup"><span data-stu-id="31ab6-516">1900 - 194F</span></span>|`IsLimbu`|  
|<span data-ttu-id="31ab6-517">1950 ～ 197F</span><span class="sxs-lookup"><span data-stu-id="31ab6-517">1950 - 197F</span></span>|`IsTaiLe`|  
|<span data-ttu-id="31ab6-518">19E0 ～ 19FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-518">19E0 - 19FF</span></span>|`IsKhmerSymbols`|  
|<span data-ttu-id="31ab6-519">1D00 ～ 1D7F</span><span class="sxs-lookup"><span data-stu-id="31ab6-519">1D00 - 1D7F</span></span>|`IsPhoneticExtensions`|  
|<span data-ttu-id="31ab6-520">1E00 ～ 1EFF</span><span class="sxs-lookup"><span data-stu-id="31ab6-520">1E00 - 1EFF</span></span>|`IsLatinExtendedAdditional`|  
|<span data-ttu-id="31ab6-521">1F00 ～ 1FFF</span><span class="sxs-lookup"><span data-stu-id="31ab6-521">1F00 - 1FFF</span></span>|`IsGreekExtended`|  
|<span data-ttu-id="31ab6-522">2000 ～ 206F</span><span class="sxs-lookup"><span data-stu-id="31ab6-522">2000 - 206F</span></span>|`IsGeneralPunctuation`|  
|<span data-ttu-id="31ab6-523">2070 ～ 209F</span><span class="sxs-lookup"><span data-stu-id="31ab6-523">2070 - 209F</span></span>|`IsSuperscriptsandSubscripts`|  
|<span data-ttu-id="31ab6-524">20A0 ～ 20CF</span><span class="sxs-lookup"><span data-stu-id="31ab6-524">20A0 - 20CF</span></span>|`IsCurrencySymbols`|  
|<span data-ttu-id="31ab6-525">20D0 ～ 20FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-525">20D0 - 20FF</span></span>|`IsCombiningDiacriticalMarksforSymbols`<br /><br /> <span data-ttu-id="31ab6-526">- または -</span><span class="sxs-lookup"><span data-stu-id="31ab6-526">-or-</span></span><br /><br /> `IsCombiningMarksforSymbols`|  
|<span data-ttu-id="31ab6-527">2100 ～ 214F</span><span class="sxs-lookup"><span data-stu-id="31ab6-527">2100 - 214F</span></span>|`IsLetterlikeSymbols`|  
|<span data-ttu-id="31ab6-528">2150 ～ 218F</span><span class="sxs-lookup"><span data-stu-id="31ab6-528">2150 - 218F</span></span>|`IsNumberForms`|  
|<span data-ttu-id="31ab6-529">2190 ～ 21FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-529">2190 - 21FF</span></span>|`IsArrows`|  
|<span data-ttu-id="31ab6-530">2200 ～ 22FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-530">2200 - 22FF</span></span>|`IsMathematicalOperators`|  
|<span data-ttu-id="31ab6-531">2300 ～ 23FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-531">2300 - 23FF</span></span>|`IsMiscellaneousTechnical`|  
|<span data-ttu-id="31ab6-532">2400 ～ 243F</span><span class="sxs-lookup"><span data-stu-id="31ab6-532">2400 - 243F</span></span>|`IsControlPictures`|  
|<span data-ttu-id="31ab6-533">2440 ～ 245F</span><span class="sxs-lookup"><span data-stu-id="31ab6-533">2440 - 245F</span></span>|`IsOpticalCharacterRecognition`|  
|<span data-ttu-id="31ab6-534">2460 ～ 24FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-534">2460 - 24FF</span></span>|`IsEnclosedAlphanumerics`|  
|<span data-ttu-id="31ab6-535">2500 ～ 257F</span><span class="sxs-lookup"><span data-stu-id="31ab6-535">2500 - 257F</span></span>|`IsBoxDrawing`|  
|<span data-ttu-id="31ab6-536">2580 ～ 259F</span><span class="sxs-lookup"><span data-stu-id="31ab6-536">2580 - 259F</span></span>|`IsBlockElements`|  
|<span data-ttu-id="31ab6-537">25A0 ～ 25FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-537">25A0 - 25FF</span></span>|`IsGeometricShapes`|  
|<span data-ttu-id="31ab6-538">2600 ～ 26FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-538">2600 - 26FF</span></span>|`IsMiscellaneousSymbols`|  
|<span data-ttu-id="31ab6-539">2700 ～ 27BF</span><span class="sxs-lookup"><span data-stu-id="31ab6-539">2700 - 27BF</span></span>|`IsDingbats`|  
|<span data-ttu-id="31ab6-540">27C0 ～ 27EF</span><span class="sxs-lookup"><span data-stu-id="31ab6-540">27C0 - 27EF</span></span>|`IsMiscellaneousMathematicalSymbols-A`|  
|<span data-ttu-id="31ab6-541">27F0 ～ 27FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-541">27F0 - 27FF</span></span>|`IsSupplementalArrows-A`|  
|<span data-ttu-id="31ab6-542">2800 ～ 28FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-542">2800 - 28FF</span></span>|`IsBraillePatterns`|  
|<span data-ttu-id="31ab6-543">2900 ～ 297F</span><span class="sxs-lookup"><span data-stu-id="31ab6-543">2900 - 297F</span></span>|`IsSupplementalArrows-B`|  
|<span data-ttu-id="31ab6-544">2980 ～ 29FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-544">2980 - 29FF</span></span>|`IsMiscellaneousMathematicalSymbols-B`|  
|<span data-ttu-id="31ab6-545">2A00 ～ 2AFF</span><span class="sxs-lookup"><span data-stu-id="31ab6-545">2A00 - 2AFF</span></span>|`IsSupplementalMathematicalOperators`|  
|<span data-ttu-id="31ab6-546">2B00 ～ 2BFF</span><span class="sxs-lookup"><span data-stu-id="31ab6-546">2B00 - 2BFF</span></span>|`IsMiscellaneousSymbolsandArrows`|  
|<span data-ttu-id="31ab6-547">2E80 ～ 2EFF</span><span class="sxs-lookup"><span data-stu-id="31ab6-547">2E80 - 2EFF</span></span>|`IsCJKRadicalsSupplement`|  
|<span data-ttu-id="31ab6-548">2F00 ～ 2FDF</span><span class="sxs-lookup"><span data-stu-id="31ab6-548">2F00 - 2FDF</span></span>|`IsKangxiRadicals`|  
|<span data-ttu-id="31ab6-549">2FF0 ～ 2FFF</span><span class="sxs-lookup"><span data-stu-id="31ab6-549">2FF0 - 2FFF</span></span>|`IsIdeographicDescriptionCharacters`|  
|<span data-ttu-id="31ab6-550">3000 ～ 303F</span><span class="sxs-lookup"><span data-stu-id="31ab6-550">3000 - 303F</span></span>|`IsCJKSymbolsandPunctuation`|  
|<span data-ttu-id="31ab6-551">3040 ～ 309F</span><span class="sxs-lookup"><span data-stu-id="31ab6-551">3040 - 309F</span></span>|`IsHiragana`|  
|<span data-ttu-id="31ab6-552">30A0 ～ 30FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-552">30A0 - 30FF</span></span>|`IsKatakana`|  
|<span data-ttu-id="31ab6-553">3100 ～ 312F</span><span class="sxs-lookup"><span data-stu-id="31ab6-553">3100 - 312F</span></span>|`IsBopomofo`|  
|<span data-ttu-id="31ab6-554">3130 ～ 318F</span><span class="sxs-lookup"><span data-stu-id="31ab6-554">3130 - 318F</span></span>|`IsHangulCompatibilityJamo`|  
|<span data-ttu-id="31ab6-555">3190 ～ 319F</span><span class="sxs-lookup"><span data-stu-id="31ab6-555">3190 - 319F</span></span>|`IsKanbun`|  
|<span data-ttu-id="31ab6-556">31A0 ～ 31BF</span><span class="sxs-lookup"><span data-stu-id="31ab6-556">31A0 - 31BF</span></span>|`IsBopomofoExtended`|  
|<span data-ttu-id="31ab6-557">31F0 ～ 31FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-557">31F0 - 31FF</span></span>|`IsKatakanaPhoneticExtensions`|  
|<span data-ttu-id="31ab6-558">3200 ～ 32FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-558">3200 - 32FF</span></span>|`IsEnclosedCJKLettersandMonths`|  
|<span data-ttu-id="31ab6-559">3300 ～ 33FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-559">3300 - 33FF</span></span>|`IsCJKCompatibility`|  
|<span data-ttu-id="31ab6-560">3400 ～ 4DBF</span><span class="sxs-lookup"><span data-stu-id="31ab6-560">3400 - 4DBF</span></span>|`IsCJKUnifiedIdeographsExtensionA`|  
|<span data-ttu-id="31ab6-561">4DC0 ～ 4DFF</span><span class="sxs-lookup"><span data-stu-id="31ab6-561">4DC0 - 4DFF</span></span>|`IsYijingHexagramSymbols`|  
|<span data-ttu-id="31ab6-562">4E00 ～ 9FFF</span><span class="sxs-lookup"><span data-stu-id="31ab6-562">4E00 - 9FFF</span></span>|`IsCJKUnifiedIdeographs`|  
|<span data-ttu-id="31ab6-563">A000 ～ A48F</span><span class="sxs-lookup"><span data-stu-id="31ab6-563">A000 - A48F</span></span>|`IsYiSyllables`|  
|<span data-ttu-id="31ab6-564">A490 ～ A4CF</span><span class="sxs-lookup"><span data-stu-id="31ab6-564">A490 - A4CF</span></span>|`IsYiRadicals`|  
|<span data-ttu-id="31ab6-565">AC00 ～ D7AF</span><span class="sxs-lookup"><span data-stu-id="31ab6-565">AC00 - D7AF</span></span>|`IsHangulSyllables`|  
|<span data-ttu-id="31ab6-566">D800 ～ DB7F</span><span class="sxs-lookup"><span data-stu-id="31ab6-566">D800 - DB7F</span></span>|`IsHighSurrogates`|  
|<span data-ttu-id="31ab6-567">DB80 ～ DBFF</span><span class="sxs-lookup"><span data-stu-id="31ab6-567">DB80 - DBFF</span></span>|`IsHighPrivateUseSurrogates`|  
|<span data-ttu-id="31ab6-568">DC00 ～ DFFF</span><span class="sxs-lookup"><span data-stu-id="31ab6-568">DC00 - DFFF</span></span>|`IsLowSurrogates`|  
|<span data-ttu-id="31ab6-569">E000 ～ F8FF</span><span class="sxs-lookup"><span data-stu-id="31ab6-569">E000 - F8FF</span></span>|<span data-ttu-id="31ab6-570">`IsPrivateUse` または `IsPrivateUseArea`</span><span class="sxs-lookup"><span data-stu-id="31ab6-570">`IsPrivateUse` or `IsPrivateUseArea`</span></span>|  
|<span data-ttu-id="31ab6-571">F900 ～ FAFF</span><span class="sxs-lookup"><span data-stu-id="31ab6-571">F900 - FAFF</span></span>|`IsCJKCompatibilityIdeographs`|  
|<span data-ttu-id="31ab6-572">FB00 ～ FB4F</span><span class="sxs-lookup"><span data-stu-id="31ab6-572">FB00 - FB4F</span></span>|`IsAlphabeticPresentationForms`|  
|<span data-ttu-id="31ab6-573">FB50 ～ FDFF</span><span class="sxs-lookup"><span data-stu-id="31ab6-573">FB50 - FDFF</span></span>|`IsArabicPresentationForms-A`|  
|<span data-ttu-id="31ab6-574">FE00 ～ FE0F</span><span class="sxs-lookup"><span data-stu-id="31ab6-574">FE00 - FE0F</span></span>|`IsVariationSelectors`|  
|<span data-ttu-id="31ab6-575">FE20 ～ FE2F</span><span class="sxs-lookup"><span data-stu-id="31ab6-575">FE20 - FE2F</span></span>|`IsCombiningHalfMarks`|  
|<span data-ttu-id="31ab6-576">FE30 ～ FE4F</span><span class="sxs-lookup"><span data-stu-id="31ab6-576">FE30 - FE4F</span></span>|`IsCJKCompatibilityForms`|  
|<span data-ttu-id="31ab6-577">FE50 ～ FE6F</span><span class="sxs-lookup"><span data-stu-id="31ab6-577">FE50 - FE6F</span></span>|`IsSmallFormVariants`|  
|<span data-ttu-id="31ab6-578">FE70 ～ FEFF</span><span class="sxs-lookup"><span data-stu-id="31ab6-578">FE70 - FEFF</span></span>|`IsArabicPresentationForms-B`|  
|<span data-ttu-id="31ab6-579">FF00 ～ FFEF</span><span class="sxs-lookup"><span data-stu-id="31ab6-579">FF00 - FFEF</span></span>|`IsHalfwidthandFullwidthForms`|  
|<span data-ttu-id="31ab6-580">FFF0 ～ FFFF</span><span class="sxs-lookup"><span data-stu-id="31ab6-580">FFF0 - FFFF</span></span>|`IsSpecials`|  
  
<a name="CharacterClassSubtraction"></a>   
## <a name="character-class-subtraction-basegroup---excludedgroup"></a><span data-ttu-id="31ab6-581">文字クラスの減算: [base_group - [excluded_group]]</span><span class="sxs-lookup"><span data-stu-id="31ab6-581">Character class subtraction: [base_group - [excluded_group]]</span></span>  
 <span data-ttu-id="31ab6-582">文字クラスは、文字のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-582">A character class defines a set of characters.</span></span> <span data-ttu-id="31ab6-583">文字クラス減算によって、ある文字クラスから別の文字クラスの文字を除外した文字セットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-583">Character class subtraction yields a set of characters that is the result of excluding the characters in one character class from another character class.</span></span>  
  
 <span data-ttu-id="31ab6-584">文字クラス減算式の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="31ab6-584">A character class subtraction expression has the following form:</span></span>  
  
 <span data-ttu-id="31ab6-585">`[` *base_group* `-[` *excluded_group* `]]`</span><span class="sxs-lookup"><span data-stu-id="31ab6-585">`[` *base_group* `-[` *excluded_group* `]]`</span></span>  
  
 <span data-ttu-id="31ab6-586">角かっこ (`[]`) とハイフン (`-`) は省略できません。</span><span class="sxs-lookup"><span data-stu-id="31ab6-586">The square brackets (`[]`) and hyphen (`-`) are mandatory.</span></span> <span data-ttu-id="31ab6-587">*base_group* は、[文字グループの肯定](#PositiveGroup)または[文字グループの否定](#NegativeGroup)です。</span><span class="sxs-lookup"><span data-stu-id="31ab6-587">The *base_group* is a [positive character group](#PositiveGroup) or a [negative character group](#NegativeGroup).</span></span> <span data-ttu-id="31ab6-588">*excluded_group* は、別の文字グループの肯定または文字グループの否定、あるいは別の文字クラス減算式です (つまり文字クラス減算式は入れ子にすることができます)。</span><span class="sxs-lookup"><span data-stu-id="31ab6-588">The *excluded_group* component is another positive or negative character group, or another character class subtraction expression (that is, you can nest character class subtraction expressions).</span></span>  
  
 <span data-ttu-id="31ab6-589">たとえば、"a" ～ "z" の文字範囲で構成される基本グループがあるとします。</span><span class="sxs-lookup"><span data-stu-id="31ab6-589">For example, suppose you have a base group that consists of the character range from "a" through "z".</span></span> <span data-ttu-id="31ab6-590">"m" を除外した基本グループで構成される文字のセットを定義するには、`[a-z-[m]]` を使用します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-590">To define the set of characters that consists of the base group except for the character "m", use `[a-z-[m]]`.</span></span> <span data-ttu-id="31ab6-591">"d"、"j" および "p" の文字を除外した基本グループで構成される文字のセットを定義するには、`[a-z-[djp]]` を使用します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-591">To define the set of characters that consists of the base group except for the set of characters "d", "j", and "p", use `[a-z-[djp]]`.</span></span> <span data-ttu-id="31ab6-592">"m" ～ "p" の文字範囲を除外した基本グループで構成される文字のセットを定義するには、`[a-z-[m-p]]` を使用します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-592">To define the set of characters that consists of the base group except for the character range from "m" through "p", use `[a-z-[m-p]]`.</span></span>  
  
 <span data-ttu-id="31ab6-593">入れ子になった文字クラス減算式 `[a-z-[d-w-[m-o]]]` について考えてみます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-593">Consider the nested character class subtraction expression, `[a-z-[d-w-[m-o]]]`.</span></span> <span data-ttu-id="31ab6-594">この式は、最も内部の文字範囲から順に外側へと評価されます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-594">The expression is evaluated from the innermost character range outward.</span></span> <span data-ttu-id="31ab6-595">まず、"m" ～ "o" の文字範囲が "d" ～ "w" の文字範囲から減算されて、"d" ～ "l" および "p" ～ "w" の文字セットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-595">First, the character range from "m" through "o" is subtracted from the character range "d" through "w", which yields the set of characters from "d" through "l" and "p" through "w".</span></span> <span data-ttu-id="31ab6-596">さらにこのセットが "a" ～ "z" の文字範囲から減算されて、`[abcmnoxyz]` という文字セットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-596">That set is then subtracted from the character range from "a" through "z", which yields the set of characters `[abcmnoxyz]`.</span></span>  
  
 <span data-ttu-id="31ab6-597">文字クラス減算では、任意の文字クラスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="31ab6-597">You can use any character class with character class subtraction.</span></span> <span data-ttu-id="31ab6-598">\u0000 ～ \uFFFF の Unicode 文字から空白文字 (`\s`)、句読点一般カテゴリの文字 (`\p{P}`)、`IsGreek` 名前付きブロック内の文字 (`\p{IsGreek}`)、および Unicode NEXT LINE 制御文字 (\x85) を除いた文字のセットを定義するには、`[\u0000-\uFFFF-[\s\p{P}\p{IsGreek}\x85]]` を使用します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-598">To define the set of characters that consists of all Unicode characters from \u0000 through \uFFFF except white-space characters (`\s`), the characters in the punctuation general category (`\p{P}`), the characters in the `IsGreek` named block (`\p{IsGreek}`), and the Unicode NEXT LINE control character (\x85), use `[\u0000-\uFFFF-[\s\p{P}\p{IsGreek}\x85]]`.</span></span>  
  
 <span data-ttu-id="31ab6-599">有効な結果を生成する文字クラス減算式の文字クラスを選択します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-599">Choose character classes for a character class subtraction expression that will yield useful results.</span></span> <span data-ttu-id="31ab6-600">どの文字にも一致しない空の文字セットを生成する式、または元の基本グループと同じになる式は避けてください。</span><span class="sxs-lookup"><span data-stu-id="31ab6-600">Avoid an expression that yields an empty set of characters, which cannot match anything, or an expression that is equivalent to the original base group.</span></span> <span data-ttu-id="31ab6-601">たとえば、`[\p{IsBasicLatin}-[\x00-\x7F]]` という式は、`IsBasicLatin` 一般カテゴリから `IsBasicLatin` 文字範囲のすべての文字を減算して空のセットを生成します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-601">For example, the empty set is the result of the expression `[\p{IsBasicLatin}-[\x00-\x7F]]`, which subtracts all characters in the `IsBasicLatin` character range from the `IsBasicLatin` general category.</span></span> <span data-ttu-id="31ab6-602">同様に、`[a-z-[0-9]]` という式は元の基本グループと同じセットを生成します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-602">Similarly, the original base group is the result of the expression `[a-z-[0-9]]`.</span></span>  <span data-ttu-id="31ab6-603">これは、"a" ～ "z" の文字範囲である基本グループに、"0" ～ "9" という 10 進数字の文字範囲から成る除外対象グループ内の文字が含まれないためです。</span><span class="sxs-lookup"><span data-stu-id="31ab6-603">This is because the base group, which is the character range of letters from "a" through "z", does not contain any characters in the excluded group, which is the character range of decimal digits from "0" through "9".</span></span>  
  
 <span data-ttu-id="31ab6-604">入力文字列内の 0 および奇数と一致する正規表現 `^[0-9-[2468]]+$` を定義する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-604">The following example defines a regular expression, `^[0-9-[2468]]+$`, that matches zero and odd digits in an input string.</span></span>  <span data-ttu-id="31ab6-605">この正規表現の解釈を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-605">The regular expression is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="31ab6-606">要素</span><span class="sxs-lookup"><span data-stu-id="31ab6-606">Element</span></span>|<span data-ttu-id="31ab6-607">説明</span><span class="sxs-lookup"><span data-stu-id="31ab6-607">Description</span></span>|  
|-------------|-----------------|  
|^|<span data-ttu-id="31ab6-608">入力文字列の先頭から照合を開始します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-608">Begin the match at the start of the input string.</span></span>|  
|`[0-9-[2468]]+`|<span data-ttu-id="31ab6-609">2、4、6、および 8 を除く 0 ～ 9 の文字の 1 回以上の出現と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-609">Match one or more occurrences of any character from 0 to 9 except for 2, 4, 6, and 8.</span></span> <span data-ttu-id="31ab6-610">つまり、0 または奇数の 1 回以上の出現と一致します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-610">In other words, match one or more occurrences of zero or an odd digit.</span></span>|  
|$|<span data-ttu-id="31ab6-611">入力文字列の末尾で照合を終了します。</span><span class="sxs-lookup"><span data-stu-id="31ab6-611">End the match at the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/classsubtraction1.cs#15)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/classsubtraction1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="31ab6-612">関連項目</span><span class="sxs-lookup"><span data-stu-id="31ab6-612">See also</span></span>

- <xref:System.Char.GetUnicodeCategory%2A>
- [<span data-ttu-id="31ab6-613">正規表現言語 - クイック リファレンス</span><span class="sxs-lookup"><span data-stu-id="31ab6-613">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
- [<span data-ttu-id="31ab6-614">正規表現のオプション</span><span class="sxs-lookup"><span data-stu-id="31ab6-614">Regular Expression Options</span></span>](../../../docs/standard/base-types/regular-expression-options.md)
