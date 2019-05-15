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
ms.openlocfilehash: 54d190bfa3f13ccfc78dd2501018442afb281d37
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64634701"
---
# <a name="character-classes-in-regular-expressions"></a><span data-ttu-id="c48b6-103">正規表現での文字クラス</span><span class="sxs-lookup"><span data-stu-id="c48b6-103">Character Classes in Regular Expressions</span></span>
<a name="Top"></a> <span data-ttu-id="c48b6-104">文字クラスは、いずれかが入力文字列に含まれると一致と見なされる文字のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-104">A character class defines a set of characters, any one of which can occur in an input string for a match to succeed.</span></span> <span data-ttu-id="c48b6-105">.NET の正規表現言語では、次の文字クラスがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-105">The regular expression language in .NET supports the following character classes:</span></span>  
  
- <span data-ttu-id="c48b6-106">文字グループの肯定。</span><span class="sxs-lookup"><span data-stu-id="c48b6-106">Positive character groups.</span></span> <span data-ttu-id="c48b6-107">入力文字列内の文字が指定した文字のセットのいずれかと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c48b6-107">A character in the input string must match one of a specified set of characters.</span></span> <span data-ttu-id="c48b6-108">詳細については、「[文字グループの肯定](#PositiveGroup)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-108">For more information, see [Positive Character Group](#PositiveGroup).</span></span>  
  
- <span data-ttu-id="c48b6-109">文字グループの否定。</span><span class="sxs-lookup"><span data-stu-id="c48b6-109">Negative character groups.</span></span> <span data-ttu-id="c48b6-110">入力文字列内の文字が指定した文字のセットのいずれかと一致しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="c48b6-110">A character in the input string must not match one of a specified set of characters.</span></span> <span data-ttu-id="c48b6-111">詳細については、「[文字グループの否定](#NegativeGroup)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-111">For more information, see [Negative Character Group](#NegativeGroup).</span></span>  
  
- <span data-ttu-id="c48b6-112">任意の文字。</span><span class="sxs-lookup"><span data-stu-id="c48b6-112">Any character.</span></span> <span data-ttu-id="c48b6-113">正規表現の `.` (ドットまたはピリオド) 文字は、`\n` を除く任意の文字と一致するワイルドカード文字です。</span><span class="sxs-lookup"><span data-stu-id="c48b6-113">The `.` (dot or period) character in a regular expression is a wildcard character that matches any character except `\n`.</span></span> <span data-ttu-id="c48b6-114">詳細については、「[任意の文字](#AnyCharacter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-114">For more information, see [Any Character](#AnyCharacter).</span></span>  
  
- <span data-ttu-id="c48b6-115">Unicode 一般カテゴリまたは名前付きブロック。</span><span class="sxs-lookup"><span data-stu-id="c48b6-115">A general Unicode category or named block.</span></span> <span data-ttu-id="c48b6-116">入力文字列内の文字が一致と見なされるには、その文字が特定の Unicode カテゴリのメンバーであるか、または Unicode 文字の連続した範囲内に含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c48b6-116">A character in the input string must be a member of a particular Unicode category or must fall within a contiguous range of Unicode characters for a match to succeed.</span></span> <span data-ttu-id="c48b6-117">詳細については、「[Unicode カテゴリまたは Unicode ブロック](#CategoryOrBlock)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-117">For more information, see [Unicode Category or Unicode Block](#CategoryOrBlock).</span></span>  
  
- <span data-ttu-id="c48b6-118">Unicode 一般カテゴリまたは名前付きブロックの否定。</span><span class="sxs-lookup"><span data-stu-id="c48b6-118">A negative general Unicode category or named block.</span></span> <span data-ttu-id="c48b6-119">入力文字列内の文字が一致と見なされるには、その文字が特定の Unicode カテゴリのメンバーでないか、または Unicode 文字の連続した範囲内に含まれない必要があります。</span><span class="sxs-lookup"><span data-stu-id="c48b6-119">A character in the input string must not be a member of a particular Unicode category or must not fall within a contiguous range of Unicode characters for a match to succeed.</span></span> <span data-ttu-id="c48b6-120">詳細については、「[Unicode カテゴリまたは Unicode ブロックの否定](#NegativeCategoryOrBlock)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-120">For more information, see [Negative Unicode Category or Unicode Block](#NegativeCategoryOrBlock).</span></span>  
  
- <span data-ttu-id="c48b6-121">単語に使用される文字。</span><span class="sxs-lookup"><span data-stu-id="c48b6-121">A word character.</span></span> <span data-ttu-id="c48b6-122">入力文字列内の文字が、単語内の文字に適した Unicode カテゴリのいずれかに属することができます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-122">A character in the input string can belong to any of the Unicode categories that are appropriate for characters in words.</span></span> <span data-ttu-id="c48b6-123">詳細については、「[単語に使用される文字](#WordCharacter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-123">For more information, see [Word Character](#WordCharacter).</span></span>  
  
- <span data-ttu-id="c48b6-124">単語に使用されない文字。</span><span class="sxs-lookup"><span data-stu-id="c48b6-124">A non-word character.</span></span> <span data-ttu-id="c48b6-125">入力文字列内の文字が、単語に使用される文字ではない Unicode カテゴリのいずれかに属することができます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-125">A character in the input string can belong to any Unicode category that is not a word character.</span></span> <span data-ttu-id="c48b6-126">詳細については、「[単語に使用されない文字](#NonWordCharacter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-126">For more information, see [Non-Word Character](#NonWordCharacter).</span></span>  
  
- <span data-ttu-id="c48b6-127">空白文字。</span><span class="sxs-lookup"><span data-stu-id="c48b6-127">A white-space character.</span></span> <span data-ttu-id="c48b6-128">入力文字列内の文字が、Unicode 区切り記号および各種制御文字のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="c48b6-128">A character in the input string can be any Unicode separator character, as well as any one of a number of control characters.</span></span> <span data-ttu-id="c48b6-129">詳細については、「[空白文字](#WhitespaceCharacter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-129">For more information, see [White-Space Character](#WhitespaceCharacter).</span></span>  
  
- <span data-ttu-id="c48b6-130">空白以外の文字。</span><span class="sxs-lookup"><span data-stu-id="c48b6-130">A non-white-space character.</span></span> <span data-ttu-id="c48b6-131">入力文字列内の文字が、空白文字以外の文字のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="c48b6-131">A character in the input string can be any character that is not a white-space character.</span></span> <span data-ttu-id="c48b6-132">詳細については、「[空白以外の文字](#NonWhitespaceCharacter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-132">For more information, see [Non-White-Space Character](#NonWhitespaceCharacter).</span></span>  
  
- <span data-ttu-id="c48b6-133">10 進数。</span><span class="sxs-lookup"><span data-stu-id="c48b6-133">A decimal digit.</span></span> <span data-ttu-id="c48b6-134">入力文字列内の文字が、Unicode 10 進数に分類される各種文字のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="c48b6-134">A character in the input string can be any of a number of characters classified as Unicode decimal digits.</span></span> <span data-ttu-id="c48b6-135">詳細については、「[10 進数字](#DigitCharacter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-135">For more information, see [Decimal Digit Character](#DigitCharacter).</span></span>  
  
- <span data-ttu-id="c48b6-136">10 進数字以外の文字。</span><span class="sxs-lookup"><span data-stu-id="c48b6-136">A non-decimal digit.</span></span> <span data-ttu-id="c48b6-137">入力文字列内の文字が、Unicode 10 進数以外の文字のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="c48b6-137">A character in the input string can be anything other than a Unicode decimal digit.</span></span> <span data-ttu-id="c48b6-138">詳細については、「[10 進数字](#NonDigitCharacter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-138">For more information, see [Decimal Digit Character](#NonDigitCharacter).</span></span>  
  
 <span data-ttu-id="c48b6-139">.NET は、文字クラスの減算式をサポートしています。これにより、ある文字クラスから別の文字クラスを除外した結果を文字のセットとして定義できます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-139">.NET supports character class subtraction expressions, which enables you to define a set of characters as the result of excluding one character class from another character class.</span></span> <span data-ttu-id="c48b6-140">詳細については、「[文字クラス減算](#CharacterClassSubtraction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-140">For more information, see [Character Class Subtraction](#CharacterClassSubtraction).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c48b6-141">カテゴリ別の文字に一致する文字クラス (単語文字に一致する [\w](#WordCharacter)、Unicode カテゴリに一致する [\p{}](#CategoryOrBlock) など) は、<xref:System.Globalization.CharUnicodeInfo> クラスを使用して文字カテゴリに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-141">Character classes that match characters by category, such as [\w](#WordCharacter) to match word characters or [\p{}](#CategoryOrBlock) to match a Unicode category, rely on the <xref:System.Globalization.CharUnicodeInfo> class to provide information about character categories.</span></span>  <span data-ttu-id="c48b6-142">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 以降の文字カテゴリは、[Unicode 標準バージョン 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="c48b6-142">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], character categories are based on [The Unicode Standard, Version 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/).</span></span> <span data-ttu-id="c48b6-143">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] から [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] の文字カテゴリは、[Unicode 標準バージョン 6.3.0](https://www.unicode.org/versions/Unicode6.3.0/) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="c48b6-143">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] through the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], they are based on [The Unicode Standard, Version 6.3.0](https://www.unicode.org/versions/Unicode6.3.0/).</span></span>  
  
<a name="PositiveGroup"></a>   
## <a name="positive-character-group--"></a><span data-ttu-id="c48b6-144">文字グループの肯定: [ ]</span><span class="sxs-lookup"><span data-stu-id="c48b6-144">Positive Character Group: [ ]</span></span>  
 <span data-ttu-id="c48b6-145">文字グループの肯定では、いずれかが入力文字列に含まれると一致と見なされる文字の一覧を指定します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-145">A positive character group specifies a list of characters, any one of which may appear in an input string for a match to occur.</span></span> <span data-ttu-id="c48b6-146">この文字の一覧は、個別に指定されることも範囲として指定されることも、その両方であることもあります。</span><span class="sxs-lookup"><span data-stu-id="c48b6-146">This list of characters may be specified individually, as a range, or both.</span></span>  
  
 <span data-ttu-id="c48b6-147">個別の文字の一覧を指定する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c48b6-147">The syntax for specifying a list of individual characters is as follows:</span></span>  
  
 <span data-ttu-id="c48b6-148">[*character_group*]</span><span class="sxs-lookup"><span data-stu-id="c48b6-148">[*character_group*]</span></span>  
  
 <span data-ttu-id="c48b6-149">ここで、*character_group* は、入力文字列に含まれるなら一致と見なされる個別の文字の一覧です。</span><span class="sxs-lookup"><span data-stu-id="c48b6-149">where *character_group* is a list of the individual characters that can appear in the input string for a match to succeed.</span></span> <span data-ttu-id="c48b6-150">*character_group* は、リテラル文字、[エスケープ文字](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md)、または文字クラスを 1 つ以上組み合わせて構成されます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-150">*character_group* can consist of any combination of one or more literal characters, [escape characters](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md), or character classes.</span></span>  
  
 <span data-ttu-id="c48b6-151">文字の範囲を指定する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c48b6-151">The syntax for specifying a range of characters is as follows:</span></span>  
  
```  
[firstCharacter-lastCharacter]  
```  
  
 <span data-ttu-id="c48b6-152">ここで、*firstCharacter* は範囲の最初の文字で、*lastCharacter* は範囲の最後の文字です。</span><span class="sxs-lookup"><span data-stu-id="c48b6-152">where *firstCharacter* is the character that begins the range and *lastCharacter* is the character that ends the range.</span></span> <span data-ttu-id="c48b6-153">文字範囲は連続する一連の文字で、範囲の最初の文字、ハイフン (-)、および範囲の最後の文字を指定することで定義されます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-153">A character range is a contiguous series of characters defined by specifying the first character in the series, a hyphen (-), and then the last character in the series.</span></span> <span data-ttu-id="c48b6-154">2 つの文字の Unicode コード ポイントが隣接している場合、それらの文字は連続しています。</span><span class="sxs-lookup"><span data-stu-id="c48b6-154">Two characters are contiguous if they have adjacent Unicode code points.</span></span>  
  
 <span data-ttu-id="c48b6-155">文字クラスの肯定を含む一般的な正規表現パターンをいくつか次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-155">Some common regular expression patterns that contain positive character classes are listed in the following table.</span></span>  
  
|<span data-ttu-id="c48b6-156">パターン</span><span class="sxs-lookup"><span data-stu-id="c48b6-156">Pattern</span></span>|<span data-ttu-id="c48b6-157">説明</span><span class="sxs-lookup"><span data-stu-id="c48b6-157">Description</span></span>|  
|-------------|-----------------|  
|`[aeiou]`|<span data-ttu-id="c48b6-158">すべての母音と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-158">Match all vowels.</span></span>|  
|`[\p{P}\d]`|<span data-ttu-id="c48b6-159">すべての句読点および 10 進数字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-159">Match all punctuation and decimal digit characters.</span></span>|  
|`[\s\p{P}]`|<span data-ttu-id="c48b6-160">すべての空白および句読点と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-160">Match all white space and punctuation.</span></span>|  
  
 <span data-ttu-id="c48b6-161">次の例では、"a" および "e" という文字を含む文字グループの肯定を定義し、入力文字列内で "grey" または "gray" という語の後に別の語が続くと一致と見なされるようにします。</span><span class="sxs-lookup"><span data-stu-id="c48b6-161">The following example defines a positive character group that contains the characters "a" and "e" so that the input string must contain the words "grey" or "gray" followed by another word for a match to occur.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/positivecharclasses.cs#1)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/positivecharclasses.vb#1)]  
  
 <span data-ttu-id="c48b6-162">正規表現パターン `gr[ae]y\s\S+?[\s|\p{P}]` は、次のように定義されます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-162">The regular expression `gr[ae]y\s\S+?[\s|\p{P}]` is defined as follows:</span></span>  
  
|<span data-ttu-id="c48b6-163">パターン</span><span class="sxs-lookup"><span data-stu-id="c48b6-163">Pattern</span></span>|<span data-ttu-id="c48b6-164">説明</span><span class="sxs-lookup"><span data-stu-id="c48b6-164">Description</span></span>|  
|-------------|-----------------|  
|`gr`|<span data-ttu-id="c48b6-165">リテラル文字 "gr" と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-165">Match the literal characters "gr".</span></span>|  
|`[ae]`|<span data-ttu-id="c48b6-166">"a" または "e" と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-166">Match either an "a" or an "e".</span></span>|  
|`y\s`|<span data-ttu-id="c48b6-167">リテラル文字 "y" の後に空白文字が続く語と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-167">Match the literal character "y" followed by a white-space character.</span></span>|  
|`\S+?`|<span data-ttu-id="c48b6-168">1 つ以上 (ただし、できるだけ少ない数) の空白以外の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-168">Match one or more non-white-space characters, but as few as possible.</span></span>|  
|`[\s\p{P}]`|<span data-ttu-id="c48b6-169">空白文字または句読点と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-169">Match either a white-space character or a punctuation mark.</span></span>|  
  
 <span data-ttu-id="c48b6-170">次の例は、大文字で始まる語と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-170">The following example matches words that begin with any capital letter.</span></span> <span data-ttu-id="c48b6-171">部分式 `[A-Z]` を使用して、A から Z の範囲の大文字を表します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-171">It uses the subexpression `[A-Z]` to represent the range of capital letters from A to Z.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/range.cs#3)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/range.vb#3)]  
  
 <span data-ttu-id="c48b6-172">正規表現 `\b[A-Z]\w*\b` は、次の表に示すように定義されています。</span><span class="sxs-lookup"><span data-stu-id="c48b6-172">The regular expression `\b[A-Z]\w*\b` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="c48b6-173">パターン</span><span class="sxs-lookup"><span data-stu-id="c48b6-173">Pattern</span></span>|<span data-ttu-id="c48b6-174">説明</span><span class="sxs-lookup"><span data-stu-id="c48b6-174">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="c48b6-175">ワード境界から開始します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-175">Start at a word boundary.</span></span>|  
|`[A-Z]`|<span data-ttu-id="c48b6-176">A から Z の任意の大文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-176">Match any uppercase character from A to Z.</span></span>|  
|`\w*`|<span data-ttu-id="c48b6-177">0 個以上の単語に使用される文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-177">Match zero or more word characters.</span></span>|  
|`\b`|<span data-ttu-id="c48b6-178">ワード境界に一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-178">Match a word boundary.</span></span>|  
  
 [<span data-ttu-id="c48b6-179">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c48b6-179">Back to Top</span></span>](#Top)  
  
<a name="NegativeGroup"></a>   
## <a name="negative-character-group-"></a><span data-ttu-id="c48b6-180">文字グループの否定: [^]</span><span class="sxs-lookup"><span data-stu-id="c48b6-180">Negative Character Group: [^]</span></span>  
 <span data-ttu-id="c48b6-181">文字グループの否定では、入力文字列に含まれなければ一致と見なされる文字の一覧を指定します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-181">A negative character group specifies a list of characters that must not appear in an input string for a match to occur.</span></span> <span data-ttu-id="c48b6-182">この文字の一覧は、個別に指定されることも範囲として指定されることも、その両方であることもあります。</span><span class="sxs-lookup"><span data-stu-id="c48b6-182">The list of characters may be specified individually, as a range, or both.</span></span>  
  
 <span data-ttu-id="c48b6-183">個別の文字の一覧を指定する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c48b6-183">The syntax for specifying a list of individual characters is as follows:</span></span>  
  
 <span data-ttu-id="c48b6-184">[*^character_group*]</span><span class="sxs-lookup"><span data-stu-id="c48b6-184">[*^character_group*]</span></span>  
  
 <span data-ttu-id="c48b6-185">ここで、*character_group* は、入力文字列に含まれない場合に一致と見なされる個別の文字の一覧です。</span><span class="sxs-lookup"><span data-stu-id="c48b6-185">where *character_group* is a list of the individual characters that cannot appear in the input string for a match to succeed.</span></span> <span data-ttu-id="c48b6-186">*character_group* は、リテラル文字、[エスケープ文字](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md)、または文字クラスを 1 つ以上組み合わせて構成されます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-186">*character_group* can consist of any combination of one or more literal characters, [escape characters](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md), or character classes.</span></span>  
  
 <span data-ttu-id="c48b6-187">文字の範囲を指定する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c48b6-187">The syntax for specifying a range of characters is as follows:</span></span>  
  
 <span data-ttu-id="c48b6-188">[^*firstCharacter*-*lastCharacter*]</span><span class="sxs-lookup"><span data-stu-id="c48b6-188">[^*firstCharacter*-*lastCharacter*]</span></span>  
  
 <span data-ttu-id="c48b6-189">ここで、*firstCharacter* は範囲の最初の文字で、*lastCharacter* は範囲の最後の文字です。</span><span class="sxs-lookup"><span data-stu-id="c48b6-189">where *firstCharacter* is the character that begins the range, and *lastCharacter* is the character that ends the range.</span></span> <span data-ttu-id="c48b6-190">文字範囲は連続する一連の文字で、範囲の最初の文字、ハイフン (-)、および範囲の最後の文字を指定することで定義されます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-190">A character range is a contiguous series of characters defined by specifying the first character in the series, a hyphen (-), and then the last character in the series.</span></span> <span data-ttu-id="c48b6-191">2 つの文字の Unicode コード ポイントが隣接している場合、それらの文字は連続しています。</span><span class="sxs-lookup"><span data-stu-id="c48b6-191">Two characters are contiguous if they have adjacent Unicode code points.</span></span>  
  
 <span data-ttu-id="c48b6-192">複数の文字範囲を連結することもできます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-192">Two or more character ranges can be concatenated.</span></span> <span data-ttu-id="c48b6-193">たとえば、"0" ～ "9" の範囲の 10 進数、"a" ～ "f" の範囲の小文字、および "A" ～ "F" の範囲の大文字を指定するには、`[0-9a-fA-F]` を使用します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-193">For example, to specify the range of decimal digits from "0" through "9", the range of lowercase letters from "a" through "f", and the range of uppercase letters from "A" through "F", use `[0-9a-fA-F]`.</span></span>  
  
 <span data-ttu-id="c48b6-194">文字グループの否定における先頭のキャレット文字 (`^`) は、文字グループが文字グループの肯定ではなく文字グループの否定であることを示し、省略できません。</span><span class="sxs-lookup"><span data-stu-id="c48b6-194">The leading carat character (`^`) in a negative character group is mandatory and indicates the character group is a negative character group instead of a positive character group.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c48b6-195">大規模な正規表現パターンにおける文字グループの否定は、ゼロ幅アサーションではありません。</span><span class="sxs-lookup"><span data-stu-id="c48b6-195">A negative character group in a larger regular expression pattern is not a zero-width assertion.</span></span> <span data-ttu-id="c48b6-196">つまり、正規表現エンジンは、文字グループの否定を評価した後に、入力文字列内で 1 文字進みます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-196">That is, after evaluating the negative character group, the regular expression engine advances one character in the input string.</span></span>  
  
 <span data-ttu-id="c48b6-197">文字グループの否定を含む一般的な正規表現パターンをいくつか次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-197">Some common regular expression patterns that contain negative character groups are listed in the following table.</span></span>  
  
|<span data-ttu-id="c48b6-198">パターン</span><span class="sxs-lookup"><span data-stu-id="c48b6-198">Pattern</span></span>|<span data-ttu-id="c48b6-199">説明</span><span class="sxs-lookup"><span data-stu-id="c48b6-199">Description</span></span>|  
|-------------|-----------------|  
|`[^aeiou]`|<span data-ttu-id="c48b6-200">母音を除くすべての文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-200">Match all characters except vowels.</span></span>|  
|`[^\p{P}\d]`|<span data-ttu-id="c48b6-201">句読点および 10 進数字を除くすべての文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-201">Match all characters except punctuation and decimal digit characters.</span></span>|  
  
 <span data-ttu-id="c48b6-202">次の例は、"th" という文字で始まってその後に "o" が続かない語と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-202">The following example matches any word that begins with the characters "th" and is not followed by an "o".</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/negativecharclasses.cs#2)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/negativecharclasses.vb#2)]  
  
 <span data-ttu-id="c48b6-203">正規表現 `\bth[^o]\w+\b` は、次の表に示すように定義されています。</span><span class="sxs-lookup"><span data-stu-id="c48b6-203">The regular expression `\bth[^o]\w+\b` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="c48b6-204">パターン</span><span class="sxs-lookup"><span data-stu-id="c48b6-204">Pattern</span></span>|<span data-ttu-id="c48b6-205">説明</span><span class="sxs-lookup"><span data-stu-id="c48b6-205">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="c48b6-206">ワード境界から開始します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-206">Start at a word boundary.</span></span>|  
|`th`|<span data-ttu-id="c48b6-207">リテラル文字 "th" と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-207">Match the literal characters "th".</span></span>|  
|`[^o]`|<span data-ttu-id="c48b6-208">"o" 以外の任意の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-208">Match any character that is not an "o".</span></span>|  
|`\w+`|<span data-ttu-id="c48b6-209">1 つ以上の単語文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-209">Match one or more word characters.</span></span>|  
|`\b`|<span data-ttu-id="c48b6-210">ワード境界で終了します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-210">End at a word boundary.</span></span>|  
  
 [<span data-ttu-id="c48b6-211">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c48b6-211">Back to Top</span></span>](#Top)  
  
<a name="AnyCharacter"></a>   
## <a name="any-character-"></a><span data-ttu-id="c48b6-212">任意の文字: .</span><span class="sxs-lookup"><span data-stu-id="c48b6-212">Any Character: .</span></span>  
 <span data-ttu-id="c48b6-213">ピリオド文字 (.) は、`\n` (改行文字、\u000A) を除く任意の文字と一致しますが、次の 2 つの制限があります。</span><span class="sxs-lookup"><span data-stu-id="c48b6-213">The period character (.) matches any character except `\n` (the newline character, \u000A), with the following two qualifications:</span></span>  
  
- <span data-ttu-id="c48b6-214">正規表現パターンが <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> オプションで修飾されている場合、または `.` 文字クラスを含むパターンの一部が `s` オプションで修飾されている場合は、`.` は任意の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-214">If a regular expression pattern is modified by the <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> option, or if the portion of the pattern that contains the `.` character class is modified by the `s` option, `.` matches any character.</span></span> <span data-ttu-id="c48b6-215">詳細については、「 [正規表現のオプション](../../../docs/standard/base-types/regular-expression-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-215">For more information, see [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
     <span data-ttu-id="c48b6-216">`.` 文字クラスの既定の動作と <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> オプションが指定されている場合の動作の違いの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-216">The following example illustrates the different behavior of the `.` character class by default and with the <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> option.</span></span> <span data-ttu-id="c48b6-217">正規表現 `^.+` は文字列の先頭から開始し、すべての文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-217">The regular expression `^.+` starts at the beginning of the string and matches every character.</span></span> <span data-ttu-id="c48b6-218">既定では、照合は 1 行目の末尾で終了します。正規表現パターンは復帰文字 `\r` (\u000D) と一致しますが、`\n` とは一致しません。</span><span class="sxs-lookup"><span data-stu-id="c48b6-218">By default, the match ends at the end of the first line; the regular expression pattern matches the carriage return character, `\r` or \u000D, but it does not match `\n`.</span></span> <span data-ttu-id="c48b6-219"><xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> オプションは入力文字列全体を単一行として解釈するので、`\n` を含む入力文字列内のすべての文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-219">Because the <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> option interprets the entire input string as a single line, it matches every character in the input string, including `\n`.</span></span>  
  
     [!code-csharp[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/any2.cs#5)]
     [!code-vb[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/any2.vb#5)]  
  
> [!NOTE]
>  <span data-ttu-id="c48b6-220">`.` 文字クラスは `\n` を除く任意の文字と一致するので、このクラスも `\r` (復帰文字、\u000D) と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-220">Because it matches any character except `\n`, the `.` character class also matches `\r` (the carriage return character, \u000D).</span></span>  
  
- <span data-ttu-id="c48b6-221">文字グループの肯定または文字グループの否定に含まれているピリオドは、文字クラスではなくリテラルのピリオド文字として扱われます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-221">In a positive or negative character group, a period is treated as a literal period character, and not as a character class.</span></span> <span data-ttu-id="c48b6-222">詳細については、このトピックで前述した「[文字グループの肯定](#PositiveGroup)」および「[文字グループの否定](#NegativeGroup)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-222">For more information, see [Positive Character Group](#PositiveGroup) and [Negative Character Group](#NegativeGroup) earlier in this topic.</span></span> <span data-ttu-id="c48b6-223">ピリオド文字 (`.`) を文字クラスとしても文字グループの肯定のメンバーとしても含む正規表現を定義する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-223">The following example provides an illustration by defining a regular expression that includes the period character (`.`) both as a character class and as a member of a positive character group.</span></span> <span data-ttu-id="c48b6-224">正規表現 `\b.*[.?!;:](\s|\z)` はワード境界から開始し、ピリオドを含む 5 つの句読点のいずれかが検出されるまで任意の文字と一致し、空白文字または文字列の末尾と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-224">The regular expression `\b.*[.?!;:](\s|\z)` begins at a word boundary, matches any character until it encounters one of five punctuation marks, including a period, and then matches either a white-space character or the end of the string.</span></span>  
  
     [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/any1.cs#4)]
     [!code-vb[Conceptual.RegEx.Language.CharacterClasses#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/any1.vb#4)]  
  
> [!NOTE]
>  <span data-ttu-id="c48b6-225">`.` 言語要素は任意の文字と一致するので、正規表現パターンが任意の文字と複数回一致する場合に最短一致の量指定子と共によく使用されます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-225">Because it matches any character, the `.` language element is often used with a lazy quantifier if a regular expression pattern attempts to match any character multiple times.</span></span> <span data-ttu-id="c48b6-226">詳細については、「 [量指定子](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-226">For more information, see [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).</span></span>  
  
 [<span data-ttu-id="c48b6-227">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c48b6-227">Back to Top</span></span>](#Top)  
  
<a name="CategoryOrBlock"></a>   
## <a name="unicode-category-or-unicode-block-p"></a><span data-ttu-id="c48b6-228">Unicode カテゴリまたは Unicode ブロック: \p{}</span><span class="sxs-lookup"><span data-stu-id="c48b6-228">Unicode Category or Unicode Block: \p{}</span></span>  
 <span data-ttu-id="c48b6-229">Unicode 規格では、各文字に一般カテゴリが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="c48b6-229">The Unicode standard assigns each character a general category.</span></span> <span data-ttu-id="c48b6-230">たとえば、特定の文字は、英大文字 (`Lu` カテゴリで表されます)、10 進数 (`Nd` カテゴリ)、数学記号 (`Sm` カテゴリ)、または段落区切り記号 (`Zl` カテゴリ) に分類できます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-230">For example, a particular character can be an uppercase letter (represented by the `Lu` category), a decimal digit (the `Nd` category), a math symbol (the `Sm` category), or a paragraph separator (the `Zl` category).</span></span> <span data-ttu-id="c48b6-231">また、Unicode 規格の特定の文字セットは、特定の範囲またはブロックの連続したコード ポイントに対応します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-231">Specific character sets in the Unicode standard also occupy a specific range or block of consecutive code points.</span></span> <span data-ttu-id="c48b6-232">たとえば、基本的なラテン語文字セットは \u0000 ～ \u007F で、アラビア語文字セットは \u0600 ～ \u06FF です。</span><span class="sxs-lookup"><span data-stu-id="c48b6-232">For example, the basic Latin character set is found from \u0000 through \u007F, while the Arabic character set is found from \u0600 through \u06FF.</span></span>  
  
 <span data-ttu-id="c48b6-233">正規表現の構成要素</span><span class="sxs-lookup"><span data-stu-id="c48b6-233">The regular expression construct</span></span>  
  
 <span data-ttu-id="c48b6-234">`\p{` *name* `}`</span><span class="sxs-lookup"><span data-stu-id="c48b6-234">`\p{` *name* `}`</span></span>  
  
 <span data-ttu-id="c48b6-235">Unicode 一般カテゴリまたは名前付きブロックに属する任意の文字と一致します。ここで、*name* はカテゴリの省略形または名前付きブロックの名前です。</span><span class="sxs-lookup"><span data-stu-id="c48b6-235">matches any character that belongs to a Unicode general category or named block, where *name* is the category abbreviation or named block name.</span></span> <span data-ttu-id="c48b6-236">カテゴリの省略形の一覧については、このトピックで後述する「[サポートされている Unicode 一般カテゴリ](#SupportedUnicodeGeneralCategories)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-236">For a list of category abbreviations, see the [Supported Unicode General Categories](#SupportedUnicodeGeneralCategories) section later in this topic.</span></span> <span data-ttu-id="c48b6-237">名前付きブロックの一覧については、このトピックで後述する「[サポートされている名前付きブロック](#SupportedNamedBlocks)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-237">For a list of named blocks, see the [Supported Named Blocks](#SupportedNamedBlocks) section later in this topic.</span></span>  
  
 <span data-ttu-id="c48b6-238">`\p{`*name*`}` 構成要素を使用して Unicode 一般カテゴリ (この場合は `Pd` (Punctuation, Dash: 句読点、ダッシュ) カテゴリ) と名前付きブロック (`IsGreek` 名前付きブロックおよび `IsBasicLatin` 名前付きブロック) の両方を照合する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-238">The following example uses the `\p{`*name*`}` construct to match both a Unicode general category (in this case, the `Pd`, or Punctuation, Dash category) and a named block (the `IsGreek` and `IsBasicLatin` named blocks).</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/category1.cs#6)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/category1.vb#6)]  
  
 <span data-ttu-id="c48b6-239">正規表現 `\b(\p{IsGreek}+(\s)?)+\p{Pd}\s(\p{IsBasicLatin}+(\s)?)+` は、次の表に示すように定義されています。</span><span class="sxs-lookup"><span data-stu-id="c48b6-239">The regular expression `\b(\p{IsGreek}+(\s)?)+\p{Pd}\s(\p{IsBasicLatin}+(\s)?)+` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="c48b6-240">パターン</span><span class="sxs-lookup"><span data-stu-id="c48b6-240">Pattern</span></span>|<span data-ttu-id="c48b6-241">説明</span><span class="sxs-lookup"><span data-stu-id="c48b6-241">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="c48b6-242">ワード境界から開始します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-242">Start at a word boundary.</span></span>|  
|`\p{IsGreek}+`|<span data-ttu-id="c48b6-243">1 つ以上のギリシャ文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-243">Match one or more Greek characters.</span></span>|  
|`(\s)?`|<span data-ttu-id="c48b6-244">0 個または 1 個の空白文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-244">Match zero or one white-space character.</span></span>|  
|`(\p{IsGreek}+(\s)?)+`|<span data-ttu-id="c48b6-245">1 つ以上のギリシャ文字の後に 0 個または 1 個の空白文字が 1 回以上続くパターンに一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-245">Match the pattern of one or more Greek characters followed by zero or one white-space characters one or more times.</span></span>|  
|`\p{Pd}`|<span data-ttu-id="c48b6-246">Punctuation, Dash (句読点、ダッシュ) 文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-246">Match a Punctuation, Dash character.</span></span>|  
|`\s`|<span data-ttu-id="c48b6-247">空白文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-247">Match a white-space character.</span></span>|  
|`\p{IsBasicLatin}+`|<span data-ttu-id="c48b6-248">1 つ以上の基本的なラテン文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-248">Match one or more basic Latin characters.</span></span>|  
|`(\s)?`|<span data-ttu-id="c48b6-249">0 個または 1 個の空白文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-249">Match zero or one white-space character.</span></span>|  
|`(\p{IsBasicLatin}+(\s)?)+`|<span data-ttu-id="c48b6-250">1 つ以上の基本的なラテン文字の後に 0 個または 1 個の空白文字が 1 回以上続くパターンに一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-250">Match the pattern of one or more basic Latin characters followed by zero or one white-space characters one or more times.</span></span>|  
  
 [<span data-ttu-id="c48b6-251">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c48b6-251">Back to Top</span></span>](#Top)  
  
<a name="NegativeCategoryOrBlock"></a>   
## <a name="negative-unicode-category-or-unicode-block-p"></a><span data-ttu-id="c48b6-252">Unicode カテゴリまたは Unicode ブロックの否定: \P{}</span><span class="sxs-lookup"><span data-stu-id="c48b6-252">Negative Unicode Category or Unicode Block: \P{}</span></span>  
 <span data-ttu-id="c48b6-253">Unicode 規格では、各文字に一般カテゴリが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="c48b6-253">The Unicode standard assigns each character a general category.</span></span> <span data-ttu-id="c48b6-254">たとえば、特定の文字は、英大文字 (`Lu` カテゴリで表されます)、10 進数 (`Nd` カテゴリ)、数学記号 (`Sm` カテゴリ)、または段落区切り記号 (`Zl` カテゴリ) に分類できます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-254">For example, a particular character can be an uppercase letter (represented by the `Lu` category), a decimal digit (the `Nd` category), a math symbol (the `Sm` category), or a paragraph separator (the `Zl` category).</span></span> <span data-ttu-id="c48b6-255">また、Unicode 規格の特定の文字セットは、特定の範囲またはブロックの連続したコード ポイントに対応します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-255">Specific character sets in the Unicode standard also occupy a specific range or block of consecutive code points.</span></span> <span data-ttu-id="c48b6-256">たとえば、基本的なラテン語文字セットは \u0000 ～ \u007F で、アラビア語文字セットは \u0600 ～ \u06FF です。</span><span class="sxs-lookup"><span data-stu-id="c48b6-256">For example, the basic Latin character set is found from \u0000 through \u007F, while the Arabic character set is found from \u0600 through \u06FF.</span></span>  
  
 <span data-ttu-id="c48b6-257">正規表現の構成要素</span><span class="sxs-lookup"><span data-stu-id="c48b6-257">The regular expression construct</span></span>  
  
 <span data-ttu-id="c48b6-258">`\P{` *name* `}`</span><span class="sxs-lookup"><span data-stu-id="c48b6-258">`\P{` *name* `}`</span></span>  
  
 <span data-ttu-id="c48b6-259">Unicode 一般カテゴリにも名前付きブロックにも属さない任意の文字と一致します。ここで、*name* はカテゴリの省略形または名前付きブロックの名前です。</span><span class="sxs-lookup"><span data-stu-id="c48b6-259">matches any character that does not belong to a Unicode general category or named block, where *name* is the category abbreviation or named block name.</span></span> <span data-ttu-id="c48b6-260">カテゴリの省略形の一覧については、このトピックで後述する「[サポートされている Unicode 一般カテゴリ](#SupportedUnicodeGeneralCategories)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-260">For a list of category abbreviations, see the [Supported Unicode General Categories](#SupportedUnicodeGeneralCategories) section later in this topic.</span></span> <span data-ttu-id="c48b6-261">名前付きブロックの一覧については、このトピックで後述する「[サポートされている名前付きブロック](#SupportedNamedBlocks)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-261">For a list of named blocks, see the [Supported Named Blocks](#SupportedNamedBlocks) section later in this topic.</span></span>  
  
 <span data-ttu-id="c48b6-262">`\P{`*name*`}` 構成要素を使用して通貨記号 (この場合は `Sc` (Symbol, Currency: 記号、通貨) カテゴリ) を数値文字列から削除する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-262">The following example uses the `\P{`*name*`}` construct to remove any currency symbols (in this case, the `Sc`, or Symbol, Currency category) from numeric strings.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/notcategory1.cs#7)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/notcategory1.vb#7)]  
  
 <span data-ttu-id="c48b6-263">正規表現パターン `(\P{Sc})+` は、通貨記号以外の 1 つ以上の文字と一致し、実質的に結果文字列から通貨記号を削除します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-263">The regular expression pattern `(\P{Sc})+` matches one or more characters that are not currency symbols; it effectively strips any currency symbol from the result string.</span></span>  
  
 [<span data-ttu-id="c48b6-264">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c48b6-264">Back to Top</span></span>](#Top)  
  
<a name="WordCharacter"></a>   
## <a name="word-character-w"></a><span data-ttu-id="c48b6-265">単語に使用される文字: \w</span><span class="sxs-lookup"><span data-stu-id="c48b6-265">Word Character: \w</span></span>  
 <span data-ttu-id="c48b6-266">`\w` は、単語に使用される任意の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-266">`\w` matches any word character.</span></span> <span data-ttu-id="c48b6-267">単語に使用される文字は、次の表に示す Unicode カテゴリのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="c48b6-267">A word character is a member of any of the Unicode categories listed in the following table.</span></span>  
  
|<span data-ttu-id="c48b6-268">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="c48b6-268">Category</span></span>|<span data-ttu-id="c48b6-269">説明</span><span class="sxs-lookup"><span data-stu-id="c48b6-269">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="c48b6-270">Ll</span><span class="sxs-lookup"><span data-stu-id="c48b6-270">Ll</span></span>|<span data-ttu-id="c48b6-271">Letter, Lowercase (字、小文字)</span><span class="sxs-lookup"><span data-stu-id="c48b6-271">Letter, Lowercase</span></span>|  
|<span data-ttu-id="c48b6-272">Lu</span><span class="sxs-lookup"><span data-stu-id="c48b6-272">Lu</span></span>|<span data-ttu-id="c48b6-273">Letter, Uppercase (字、大文字)</span><span class="sxs-lookup"><span data-stu-id="c48b6-273">Letter, Uppercase</span></span>|  
|<span data-ttu-id="c48b6-274">Lt</span><span class="sxs-lookup"><span data-stu-id="c48b6-274">Lt</span></span>|<span data-ttu-id="c48b6-275">Letter, Titlecase (字、タイトル文字)</span><span class="sxs-lookup"><span data-stu-id="c48b6-275">Letter, Titlecase</span></span>|  
|<span data-ttu-id="c48b6-276">Lo</span><span class="sxs-lookup"><span data-stu-id="c48b6-276">Lo</span></span>|<span data-ttu-id="c48b6-277">Letter, Other (字、その他)</span><span class="sxs-lookup"><span data-stu-id="c48b6-277">Letter, Other</span></span>|  
|<span data-ttu-id="c48b6-278">Lm</span><span class="sxs-lookup"><span data-stu-id="c48b6-278">Lm</span></span>|<span data-ttu-id="c48b6-279">Letter, Modifier (字、修飾)</span><span class="sxs-lookup"><span data-stu-id="c48b6-279">Letter, Modifier</span></span>|  
|<span data-ttu-id="c48b6-280">Mn</span><span class="sxs-lookup"><span data-stu-id="c48b6-280">Mn</span></span>|<span data-ttu-id="c48b6-281">Mark, Nonspacing (結合文字、幅なし)</span><span class="sxs-lookup"><span data-stu-id="c48b6-281">Mark, Nonspacing</span></span>|  
|<span data-ttu-id="c48b6-282">Nd</span><span class="sxs-lookup"><span data-stu-id="c48b6-282">Nd</span></span>|<span data-ttu-id="c48b6-283">Number, Decimal Digit (数、10 進数字)</span><span class="sxs-lookup"><span data-stu-id="c48b6-283">Number, Decimal Digit</span></span>|  
|<span data-ttu-id="c48b6-284">Pc</span><span class="sxs-lookup"><span data-stu-id="c48b6-284">Pc</span></span>|<span data-ttu-id="c48b6-285">Punctuation, Connector (句読点、接続)。</span><span class="sxs-lookup"><span data-stu-id="c48b6-285">Punctuation, Connector.</span></span> <span data-ttu-id="c48b6-286">このカテゴリには 10 文字が含まれ、そのうち最もよく使用される文字は LOWLINE 文字 (_)、u+005F です。</span><span class="sxs-lookup"><span data-stu-id="c48b6-286">This category includes ten characters, the most commonly used of which is the LOWLINE character (_), u+005F.</span></span>|  
  
 <span data-ttu-id="c48b6-287">ECMAScript 準拠の動作が指定された場合、`\w` は `[a-zA-Z_0-9]` と同じになります。</span><span class="sxs-lookup"><span data-stu-id="c48b6-287">If ECMAScript-compliant behavior is specified, `\w` is equivalent to `[a-zA-Z_0-9]`.</span></span> <span data-ttu-id="c48b6-288">ECMAScript 正規表現の詳細については、「[正規表現のオプション](../../../docs/standard/base-types/regular-expression-options.md)」の「ECMAScript 一致の動作」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-288">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c48b6-289">`\w` 言語要素は単語に使用される任意の文字と一致するので、正規表現パターンが単語に使用される任意の文字の後に特定の単語に使用される文字が続く語と複数回一致する場合に最短一致の量指定子と共によく使用されます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-289">Because it matches any word character, the `\w` language element is often used with a lazy quantifier if a regular expression pattern attempts to match any word character multiple times, followed by a specific word character.</span></span> <span data-ttu-id="c48b6-290">詳細については、「 [量指定子](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-290">For more information, see [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="c48b6-291">`\w` 言語要素を使用して単語内の重複する文字を照合する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-291">The following example uses the `\w` language element to match duplicate characters in a word.</span></span> <span data-ttu-id="c48b6-292">この例では、次のように解釈できる正規表現パターン `(\w)\1` を定義しています。</span><span class="sxs-lookup"><span data-stu-id="c48b6-292">The example defines a regular expression pattern, `(\w)\1`, which can be interpreted as follows.</span></span>  
  
|<span data-ttu-id="c48b6-293">要素</span><span class="sxs-lookup"><span data-stu-id="c48b6-293">Element</span></span>|<span data-ttu-id="c48b6-294">説明</span><span class="sxs-lookup"><span data-stu-id="c48b6-294">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c48b6-295">(\w)</span><span class="sxs-lookup"><span data-stu-id="c48b6-295">(\w)</span></span>|<span data-ttu-id="c48b6-296">単語に使用される文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-296">Match a word character.</span></span> <span data-ttu-id="c48b6-297">これが最初のキャプチャ グループです。</span><span class="sxs-lookup"><span data-stu-id="c48b6-297">This is the first capturing group.</span></span>|  
|<span data-ttu-id="c48b6-298">\1</span><span class="sxs-lookup"><span data-stu-id="c48b6-298">\1</span></span>|<span data-ttu-id="c48b6-299">最初のキャプチャの値と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-299">Match the value of the first capture.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/wordchar1.cs#8)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/wordchar1.vb#8)]  
  
 [<span data-ttu-id="c48b6-300">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c48b6-300">Back to Top</span></span>](#Top)  
  
<a name="NonWordCharacter"></a>   
## <a name="non-word-character-w"></a><span data-ttu-id="c48b6-301">単語に使用されない文字: \W</span><span class="sxs-lookup"><span data-stu-id="c48b6-301">Non-Word Character: \W</span></span>  
 <span data-ttu-id="c48b6-302">`\W` は、単語に使用される文字以外の任意の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-302">`\W` matches any non-word character.</span></span> <span data-ttu-id="c48b6-303">\W 言語要素は、次の文字クラスと同じ結果をもたらします。</span><span class="sxs-lookup"><span data-stu-id="c48b6-303">The \W language element is equivalent to the following character class:</span></span>  
  
```  
[^\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}\p{Lm}]  
```  
  
 <span data-ttu-id="c48b6-304">つまり、次の表に示す Unicode カテゴリの文字を除く任意の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-304">In other words, it matches any character except for those in the Unicode categories listed in the following table.</span></span>  
  
|<span data-ttu-id="c48b6-305">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="c48b6-305">Category</span></span>|<span data-ttu-id="c48b6-306">説明</span><span class="sxs-lookup"><span data-stu-id="c48b6-306">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="c48b6-307">Ll</span><span class="sxs-lookup"><span data-stu-id="c48b6-307">Ll</span></span>|<span data-ttu-id="c48b6-308">Letter, Lowercase (字、小文字)</span><span class="sxs-lookup"><span data-stu-id="c48b6-308">Letter, Lowercase</span></span>|  
|<span data-ttu-id="c48b6-309">Lu</span><span class="sxs-lookup"><span data-stu-id="c48b6-309">Lu</span></span>|<span data-ttu-id="c48b6-310">Letter, Uppercase (字、大文字)</span><span class="sxs-lookup"><span data-stu-id="c48b6-310">Letter, Uppercase</span></span>|  
|<span data-ttu-id="c48b6-311">Lt</span><span class="sxs-lookup"><span data-stu-id="c48b6-311">Lt</span></span>|<span data-ttu-id="c48b6-312">Letter, Titlecase (字、タイトル文字)</span><span class="sxs-lookup"><span data-stu-id="c48b6-312">Letter, Titlecase</span></span>|  
|<span data-ttu-id="c48b6-313">Lo</span><span class="sxs-lookup"><span data-stu-id="c48b6-313">Lo</span></span>|<span data-ttu-id="c48b6-314">Letter, Other (字、その他)</span><span class="sxs-lookup"><span data-stu-id="c48b6-314">Letter, Other</span></span>|  
|<span data-ttu-id="c48b6-315">Lm</span><span class="sxs-lookup"><span data-stu-id="c48b6-315">Lm</span></span>|<span data-ttu-id="c48b6-316">Letter, Modifier (字、修飾)</span><span class="sxs-lookup"><span data-stu-id="c48b6-316">Letter, Modifier</span></span>|  
|<span data-ttu-id="c48b6-317">Mn</span><span class="sxs-lookup"><span data-stu-id="c48b6-317">Mn</span></span>|<span data-ttu-id="c48b6-318">Mark, Nonspacing (結合文字、幅なし)</span><span class="sxs-lookup"><span data-stu-id="c48b6-318">Mark, Nonspacing</span></span>|  
|<span data-ttu-id="c48b6-319">Nd</span><span class="sxs-lookup"><span data-stu-id="c48b6-319">Nd</span></span>|<span data-ttu-id="c48b6-320">Number, Decimal Digit (数、10 進数字)</span><span class="sxs-lookup"><span data-stu-id="c48b6-320">Number, Decimal Digit</span></span>|  
|<span data-ttu-id="c48b6-321">Pc</span><span class="sxs-lookup"><span data-stu-id="c48b6-321">Pc</span></span>|<span data-ttu-id="c48b6-322">Punctuation, Connector (句読点、接続)。</span><span class="sxs-lookup"><span data-stu-id="c48b6-322">Punctuation, Connector.</span></span> <span data-ttu-id="c48b6-323">このカテゴリには 10 文字が含まれ、そのうち最もよく使用される文字は LOWLINE 文字 (_)、u+005F です。</span><span class="sxs-lookup"><span data-stu-id="c48b6-323">This category includes ten characters, the most commonly used of which is the LOWLINE character (_), u+005F.</span></span>|  
  
 <span data-ttu-id="c48b6-324">ECMAScript 準拠の動作が指定された場合、`\W` は `[^a-zA-Z_0-9]` と同じになります。</span><span class="sxs-lookup"><span data-stu-id="c48b6-324">If ECMAScript-compliant behavior is specified, `\W` is equivalent to `[^a-zA-Z_0-9]`.</span></span> <span data-ttu-id="c48b6-325">ECMAScript 正規表現の詳細については、「[正規表現のオプション](../../../docs/standard/base-types/regular-expression-options.md)」の「ECMAScript 一致の動作」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-325">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c48b6-326">`\W` 言語要素は単語に使用されない任意の文字と一致するので、正規表現パターンが単語に使用されない任意の文字の後に特定の単語に使用されない文字が続く語と複数回一致する場合に最短一致の量指定子と共によく使用されます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-326">Because it matches any non-word character, the `\W` language element is often used with a lazy quantifier if a regular expression pattern attempts to match any non-word character multiple times followed by a specific non-word character.</span></span> <span data-ttu-id="c48b6-327">詳細については、「[正規表現での量指定子](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-327">For more information, see [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="c48b6-328">`\W` 文字クラスの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-328">The following example illustrates the `\W` character class.</span></span>  <span data-ttu-id="c48b6-329">この例では、単語の後に 1 つまたは 2 つの単語に使用されない文字 (空白や句読点など) が続く場合に一致する正規表現パターン `\b(\w+)(\W){1,2}` を定義しています。</span><span class="sxs-lookup"><span data-stu-id="c48b6-329">It defines a regular expression pattern, `\b(\w+)(\W){1,2}`, that matches a word followed by one or two non-word characters, such as white space or punctuation.</span></span> <span data-ttu-id="c48b6-330">この正規表現の解釈を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-330">The regular expression is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="c48b6-331">要素</span><span class="sxs-lookup"><span data-stu-id="c48b6-331">Element</span></span>|<span data-ttu-id="c48b6-332">説明</span><span class="sxs-lookup"><span data-stu-id="c48b6-332">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c48b6-333">\b</span><span class="sxs-lookup"><span data-stu-id="c48b6-333">\b</span></span>|<span data-ttu-id="c48b6-334">ワード境界から照合を開始します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-334">Begin the match at a word boundary.</span></span>|  
|<span data-ttu-id="c48b6-335">(\w+)</span><span class="sxs-lookup"><span data-stu-id="c48b6-335">(\w+)</span></span>|<span data-ttu-id="c48b6-336">1 つ以上の単語文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-336">Match one or more word characters.</span></span> <span data-ttu-id="c48b6-337">これが最初のキャプチャ グループです。</span><span class="sxs-lookup"><span data-stu-id="c48b6-337">This is the first capturing group.</span></span>|  
|<span data-ttu-id="c48b6-338">(\W){1,2}</span><span class="sxs-lookup"><span data-stu-id="c48b6-338">(\W){1,2}</span></span>|<span data-ttu-id="c48b6-339">単語に使用されない文字と 1 回または 2 回一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-339">Match a non-word character either one or two times.</span></span> <span data-ttu-id="c48b6-340">これが 2 番目のキャプチャ グループです。</span><span class="sxs-lookup"><span data-stu-id="c48b6-340">This is the second capturing group.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nonwordchar1.cs#9)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nonwordchar1.vb#9)]  
  
 <span data-ttu-id="c48b6-341">2 番目のキャプチャ グループの <xref:System.Text.RegularExpressions.Group> オブジェクトには、キャプチャされた単語に使用されない文字が 1 つだけ含まれるので、この例では、<xref:System.Text.RegularExpressions.CaptureCollection> プロパティによって返される <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> オブジェクトから、キャプチャされたすべての単語に使用されない文字を取得します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-341">Because the <xref:System.Text.RegularExpressions.Group> object for the second capturing group contains only a single captured non-word character, the example retrieves all captured non-word characters from the <xref:System.Text.RegularExpressions.CaptureCollection> object that is returned by the <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> property.</span></span>  
  
 [<span data-ttu-id="c48b6-342">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c48b6-342">Back to Top</span></span>](#Top)  
  
<a name="WhitespaceCharacter"></a>   
## <a name="white-space-character-s"></a><span data-ttu-id="c48b6-343">空白文字: \s</span><span class="sxs-lookup"><span data-stu-id="c48b6-343">White-Space Character: \s</span></span>  
 <span data-ttu-id="c48b6-344">`\s` は、空白文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-344">`\s` matches any white-space character.</span></span> <span data-ttu-id="c48b6-345">次の表に示すエスケープ シーケンスおよび Unicode カテゴリと同じ結果をもたらします。</span><span class="sxs-lookup"><span data-stu-id="c48b6-345">It is equivalent to the escape sequences and Unicode categories listed in the following table.</span></span>  
  
|<span data-ttu-id="c48b6-346">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="c48b6-346">Category</span></span>|<span data-ttu-id="c48b6-347">説明</span><span class="sxs-lookup"><span data-stu-id="c48b6-347">Description</span></span>|  
|--------------|-----------------|  
|`\f`|<span data-ttu-id="c48b6-348">フォーム フィード文字 (\u000C)。</span><span class="sxs-lookup"><span data-stu-id="c48b6-348">The form feed character, \u000C.</span></span>|  
|`\n`|<span data-ttu-id="c48b6-349">改行文字 (\u000A)。</span><span class="sxs-lookup"><span data-stu-id="c48b6-349">The newline character, \u000A.</span></span>|  
|`\r`|<span data-ttu-id="c48b6-350">復帰文字 (\u000D)。</span><span class="sxs-lookup"><span data-stu-id="c48b6-350">The carriage return character, \u000D.</span></span>|  
|`\t`|<span data-ttu-id="c48b6-351">タブ文字 (\u0009)。</span><span class="sxs-lookup"><span data-stu-id="c48b6-351">The tab character, \u0009.</span></span>|  
|`\v`|<span data-ttu-id="c48b6-352">垂直タブ文字 (\u000B)。</span><span class="sxs-lookup"><span data-stu-id="c48b6-352">The vertical tab character, \u000B.</span></span>|  
|`\x85`|<span data-ttu-id="c48b6-353">省略記号または NEXT LINE (NEL) 文字 (…) (\u0085)。</span><span class="sxs-lookup"><span data-stu-id="c48b6-353">The ellipsis or NEXT LINE (NEL) character (…), \u0085.</span></span>|  
|`\p{Z}`|<span data-ttu-id="c48b6-354">任意の区切り記号と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-354">Matches any separator character.</span></span>|  
  
 <span data-ttu-id="c48b6-355">ECMAScript 準拠の動作が指定された場合、`\s` は `[ \f\n\r\t\v]` と同じになります。</span><span class="sxs-lookup"><span data-stu-id="c48b6-355">If ECMAScript-compliant behavior is specified, `\s` is equivalent to `[ \f\n\r\t\v]`.</span></span> <span data-ttu-id="c48b6-356">ECMAScript 正規表現の詳細については、「[正規表現のオプション](../../../docs/standard/base-types/regular-expression-options.md)」の「ECMAScript 一致の動作」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-356">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="c48b6-357">`\s` 文字クラスの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-357">The following example illustrates the `\s` character class.</span></span> <span data-ttu-id="c48b6-358">この例では、"s" または "es" で終わる単語の後に空白文字または入力文字列の末尾が続く場合に一致する正規表現パターン `\b\w+(e)?s(\s|$)` を定義しています。</span><span class="sxs-lookup"><span data-stu-id="c48b6-358">It defines a regular expression pattern, `\b\w+(e)?s(\s|$)`, that matches a word ending in either "s" or "es" followed by either a white-space character or the end of the input string.</span></span> <span data-ttu-id="c48b6-359">この正規表現の解釈を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-359">The regular expression is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="c48b6-360">要素</span><span class="sxs-lookup"><span data-stu-id="c48b6-360">Element</span></span>|<span data-ttu-id="c48b6-361">説明</span><span class="sxs-lookup"><span data-stu-id="c48b6-361">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c48b6-362">\b</span><span class="sxs-lookup"><span data-stu-id="c48b6-362">\b</span></span>|<span data-ttu-id="c48b6-363">ワード境界から照合を開始します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-363">Begin the match at a word boundary.</span></span>|  
|<span data-ttu-id="c48b6-364">\w+</span><span class="sxs-lookup"><span data-stu-id="c48b6-364">\w+</span></span>|<span data-ttu-id="c48b6-365">1 つ以上の単語文字に一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-365">Match one or more word characters.</span></span>|  
|<span data-ttu-id="c48b6-366">(e)?</span><span class="sxs-lookup"><span data-stu-id="c48b6-366">(e)?</span></span>|<span data-ttu-id="c48b6-367">"e" と 0 回または 1 回一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-367">Match an "e" either zero or one time.</span></span>|  
|<span data-ttu-id="c48b6-368">s</span><span class="sxs-lookup"><span data-stu-id="c48b6-368">s</span></span>|<span data-ttu-id="c48b6-369">"s" と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-369">Match an "s".</span></span>|  
|<span data-ttu-id="c48b6-370">(\s&#124;$)</span><span class="sxs-lookup"><span data-stu-id="c48b6-370">(\s&#124;$)</span></span>|<span data-ttu-id="c48b6-371">空白文字または入力文字列の末尾と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-371">Match either a white-space character or the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/whitespace1.cs#10)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/whitespace1.vb#10)]  
  
 [<span data-ttu-id="c48b6-372">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c48b6-372">Back to Top</span></span>](#Top)  
  
<a name="NonWhitespaceCharacter"></a>   
## <a name="non-white-space-character-s"></a><span data-ttu-id="c48b6-373">空白以外の文字: \S</span><span class="sxs-lookup"><span data-stu-id="c48b6-373">Non-White-Space Character: \S</span></span>  
 <span data-ttu-id="c48b6-374">`\S` は、空白文字以外の任意の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-374">`\S` matches any non-white-space character.</span></span> <span data-ttu-id="c48b6-375">`[^\f\n\r\t\v\x85\p{Z}]` 正規表現パターン、または空白文字と一致する `\s` に相当する正規表現パターンの逆と同じ結果をもたらします。</span><span class="sxs-lookup"><span data-stu-id="c48b6-375">It is equivalent to the `[^\f\n\r\t\v\x85\p{Z}]` regular expression pattern, or the opposite of the regular expression pattern that is equivalent to `\s`, which matches white-space characters.</span></span> <span data-ttu-id="c48b6-376">詳細については、「[空白文字: \s](#WhitespaceCharacter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-376">For more information, see [White-Space Character: \s](#WhitespaceCharacter).</span></span>  
  
 <span data-ttu-id="c48b6-377">ECMAScript 準拠の動作が指定された場合、`\S` は `[^ \f\n\r\t\v]` と同じになります。</span><span class="sxs-lookup"><span data-stu-id="c48b6-377">If ECMAScript-compliant behavior is specified, `\S` is equivalent to  `[^ \f\n\r\t\v]`.</span></span> <span data-ttu-id="c48b6-378">ECMAScript 正規表現の詳細については、「[正規表現のオプション](../../../docs/standard/base-types/regular-expression-options.md)」の「ECMAScript 一致の動作」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-378">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="c48b6-379">`\S` 言語要素の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-379">The following example illustrates the `\S` language element.</span></span> <span data-ttu-id="c48b6-380">正規表現パターン `\b(\S+)\s?` は、空白文字で区切られた文字列と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-380">The regular expression pattern `\b(\S+)\s?` matches strings that are delimited by white-space characters.</span></span> <span data-ttu-id="c48b6-381">一致部分の <xref:System.Text.RegularExpressions.GroupCollection> オブジェクトの 2 番目の要素に一致する文字列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-381">The second element in the match's <xref:System.Text.RegularExpressions.GroupCollection> object contains the matched string.</span></span> <span data-ttu-id="c48b6-382">この正規表現の解釈を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-382">The regular expression can be interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="c48b6-383">要素</span><span class="sxs-lookup"><span data-stu-id="c48b6-383">Element</span></span>|<span data-ttu-id="c48b6-384">説明</span><span class="sxs-lookup"><span data-stu-id="c48b6-384">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="c48b6-385">ワード境界から照合を開始します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-385">Begin the match at a word boundary.</span></span>|  
|`(\S+)`|<span data-ttu-id="c48b6-386">1 つ以上の空白以外の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-386">Match one or more non-white-space characters.</span></span> <span data-ttu-id="c48b6-387">これが最初のキャプチャ グループです。</span><span class="sxs-lookup"><span data-stu-id="c48b6-387">This is the first capturing group.</span></span>|  
|`\s?`|<span data-ttu-id="c48b6-388">0 個または 1 個の空白文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-388">Match zero or one white-space character.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nonwhitespace1.cs#11)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nonwhitespace1.vb#11)]  
  
 [<span data-ttu-id="c48b6-389">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c48b6-389">Back to Top</span></span>](#Top)  
  
<a name="DigitCharacter"></a>   
## <a name="decimal-digit-character-d"></a><span data-ttu-id="c48b6-390">10 進数字: \d</span><span class="sxs-lookup"><span data-stu-id="c48b6-390">Decimal Digit Character: \d</span></span>  
 <span data-ttu-id="c48b6-391">`\d` は、10 進数字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-391">`\d` matches any decimal digit.</span></span> <span data-ttu-id="c48b6-392">標準の 10 進数 0 ～ 9 およびその他の各種文字セットの 10 進数を含む `\p{Nd}` 正規表現パターンと同じ結果をもたらします。</span><span class="sxs-lookup"><span data-stu-id="c48b6-392">It is equivalent to the `\p{Nd}` regular expression pattern, which includes the standard decimal digits 0-9 as well as the decimal digits of a number of other character sets.</span></span>  
  
 <span data-ttu-id="c48b6-393">ECMAScript 準拠の動作が指定された場合、`\d` は `[0-9]` と同じになります。</span><span class="sxs-lookup"><span data-stu-id="c48b6-393">If ECMAScript-compliant behavior is specified, `\d` is equivalent to  `[0-9]`.</span></span> <span data-ttu-id="c48b6-394">ECMAScript 正規表現の詳細については、「[正規表現のオプション](../../../docs/standard/base-types/regular-expression-options.md)」の「ECMAScript 一致の動作」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-394">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="c48b6-395">`\d` 言語要素の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-395">The following example illustrates the `\d` language element.</span></span> <span data-ttu-id="c48b6-396">この例では、入力文字列が米国およびカナダの有効な電話番号を表すかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="c48b6-396">It tests whether an input string represents a valid telephone number in the United States and Canada.</span></span> <span data-ttu-id="c48b6-397">正規表現パターン `^(\(?\d{3}\)?[\s-])?\d{3}-\d{4}$` は、次の表に示すように定義されています。</span><span class="sxs-lookup"><span data-stu-id="c48b6-397">The regular expression pattern `^(\(?\d{3}\)?[\s-])?\d{3}-\d{4}$` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="c48b6-398">要素</span><span class="sxs-lookup"><span data-stu-id="c48b6-398">Element</span></span>|<span data-ttu-id="c48b6-399">説明</span><span class="sxs-lookup"><span data-stu-id="c48b6-399">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="c48b6-400">入力文字列の先頭から照合を開始します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-400">Begin the match at the beginning of the input string.</span></span>|  
|`\(?`|<span data-ttu-id="c48b6-401">0 個または 1 個のリテラル "(" 文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-401">Match zero or one literal "(" character.</span></span>|  
|`\d{3}`|<span data-ttu-id="c48b6-402">3 個の 10 進数と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-402">Match three decimal digits.</span></span>|  
|`\)?`|<span data-ttu-id="c48b6-403">0 個または 1 個のリテラル ")" 文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-403">Match zero or one literal ")" character.</span></span>|  
|`[\s-]`|<span data-ttu-id="c48b6-404">ハイフンまたは空白文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-404">Match a hyphen or a white-space character.</span></span>|  
|`(\(?\d{3}\)?[\s-])?`|<span data-ttu-id="c48b6-405">省略可能な左かっこの後に 3 個の 10 進数が続く部分、省略可能な右かっこ、および空白文字またはハイフンと 0 回または 1 回一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-405">Match an optional opening parenthesis followed by three decimal digits, an optional closing parenthesis, and either a white-space character or a hyphen zero or one time.</span></span> <span data-ttu-id="c48b6-406">これが最初のキャプチャ グループです。</span><span class="sxs-lookup"><span data-stu-id="c48b6-406">This is the first capturing group.</span></span>|  
|`\d{3}-\d{4}`|<span data-ttu-id="c48b6-407">3 個の 10 進数の後にハイフンおよび 4 個以上の 10 進数が続く場合に一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-407">Match three decimal digits followed by a hyphen and four more decimal digits.</span></span>|  
|`$`|<span data-ttu-id="c48b6-408">入力文字列の末尾と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-408">Match the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/digit1.cs#12)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/digit1.vb#12)]  
  
 [<span data-ttu-id="c48b6-409">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c48b6-409">Back to Top</span></span>](#Top)  
  
<a name="NonDigitCharacter"></a>   
## <a name="non-digit-character-d"></a><span data-ttu-id="c48b6-410">数字以外の文字: \D</span><span class="sxs-lookup"><span data-stu-id="c48b6-410">Non-Digit Character: \D</span></span>  
 <span data-ttu-id="c48b6-411">`\D` は、数字以外の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-411">`\D` matches any non-digit character.</span></span> <span data-ttu-id="c48b6-412">`\P{Nd}` 正規表現パターンと同じ結果をもたらします。</span><span class="sxs-lookup"><span data-stu-id="c48b6-412">It is equivalent to the `\P{Nd}` regular expression pattern.</span></span>  
  
 <span data-ttu-id="c48b6-413">ECMAScript 準拠の動作が指定された場合、`\D` は `[^0-9]` と同じになります。</span><span class="sxs-lookup"><span data-stu-id="c48b6-413">If ECMAScript-compliant behavior is specified, `\D` is equivalent to  `[^0-9]`.</span></span> <span data-ttu-id="c48b6-414">ECMAScript 正規表現の詳細については、「[正規表現のオプション](../../../docs/standard/base-types/regular-expression-options.md)」の「ECMAScript 一致の動作」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-414">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="c48b6-415">\D 言語要素の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-415">The following example illustrates the \D language element.</span></span> <span data-ttu-id="c48b6-416">部品番号などの文字列が 10 進数および 10 進数以外の文字を適切に組み合わせて構成されているかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="c48b6-416">It tests whether a string such as a part number consists of the appropriate combination of decimal and non-decimal characters.</span></span> <span data-ttu-id="c48b6-417">正規表現パターン `^\D\d{1,5}\D*$` は、次の表に示すように定義されています。</span><span class="sxs-lookup"><span data-stu-id="c48b6-417">The regular expression pattern `^\D\d{1,5}\D*$` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="c48b6-418">要素</span><span class="sxs-lookup"><span data-stu-id="c48b6-418">Element</span></span>|<span data-ttu-id="c48b6-419">説明</span><span class="sxs-lookup"><span data-stu-id="c48b6-419">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="c48b6-420">入力文字列の先頭から照合を開始します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-420">Begin the match at the beginning of the input string.</span></span>|  
|`\D`|<span data-ttu-id="c48b6-421">数字以外の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-421">Match a non-digit character.</span></span>|  
|`\d{1,5}`|<span data-ttu-id="c48b6-422">1 ～ 5 個の 10 進数と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-422">Match from one to five decimal digits.</span></span>|  
|`\D*`|<span data-ttu-id="c48b6-423">0 個または 1 個以上の 10 進数以外の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-423">Match zero, one, or more non-decimal characters.</span></span>|  
|`$`|<span data-ttu-id="c48b6-424">入力文字列の末尾と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-424">Match the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nondigit1.cs#13)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nondigit1.vb#13)]  
  
 [<span data-ttu-id="c48b6-425">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c48b6-425">Back to Top</span></span>](#Top)  
  
<a name="SupportedUnicodeGeneralCategories"></a>   
## <a name="supported-unicode-general-categories"></a><span data-ttu-id="c48b6-426">サポートされている Unicode 一般カテゴリ</span><span class="sxs-lookup"><span data-stu-id="c48b6-426">Supported Unicode General Categories</span></span>  
 <span data-ttu-id="c48b6-427">Unicode は、次の表に示されている一般カテゴリを定義しています。</span><span class="sxs-lookup"><span data-stu-id="c48b6-427">Unicode defines the general categories listed in the following table.</span></span> <span data-ttu-id="c48b6-428">詳細については、「[Unicode Character Database (Unicode 文字データベース)](https://www.unicode.org/reports/tr44/)」内の「UCD File Format (UCD ファイル形式)」および「General Category Values (一般カテゴリの値)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-428">For more information, see the "UCD File Format" and "General Category Values" subtopics at the [Unicode Character Database](https://www.unicode.org/reports/tr44/).</span></span>  
  
|<span data-ttu-id="c48b6-429">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="c48b6-429">Category</span></span>|<span data-ttu-id="c48b6-430">説明</span><span class="sxs-lookup"><span data-stu-id="c48b6-430">Description</span></span>|  
|--------------|-----------------|  
|`Lu`|<span data-ttu-id="c48b6-431">Letter, Uppercase (字、大文字)</span><span class="sxs-lookup"><span data-stu-id="c48b6-431">Letter, Uppercase</span></span>|  
|`Ll`|<span data-ttu-id="c48b6-432">Letter, Lowercase (字、小文字)</span><span class="sxs-lookup"><span data-stu-id="c48b6-432">Letter, Lowercase</span></span>|  
|`Lt`|<span data-ttu-id="c48b6-433">Letter, Titlecase (字、タイトル文字)</span><span class="sxs-lookup"><span data-stu-id="c48b6-433">Letter, Titlecase</span></span>|  
|`Lm`|<span data-ttu-id="c48b6-434">Letter, Modifier (字、修飾)</span><span class="sxs-lookup"><span data-stu-id="c48b6-434">Letter, Modifier</span></span>|  
|`Lo`|<span data-ttu-id="c48b6-435">Letter, Other (字、その他)</span><span class="sxs-lookup"><span data-stu-id="c48b6-435">Letter, Other</span></span>|  
|`L`|<span data-ttu-id="c48b6-436">すべてのアルファベット文字。</span><span class="sxs-lookup"><span data-stu-id="c48b6-436">All letter characters.</span></span> <span data-ttu-id="c48b6-437">これには、`Lu`、`Ll`、`Lt`、`Lm`、および `Lo` の各文字が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-437">This includes the `Lu`, `Ll`, `Lt`, `Lm`, and `Lo` characters.</span></span>|  
|`Mn`|<span data-ttu-id="c48b6-438">Mark, Nonspacing (結合文字、幅なし)</span><span class="sxs-lookup"><span data-stu-id="c48b6-438">Mark, Nonspacing</span></span>|  
|`Mc`|<span data-ttu-id="c48b6-439">Mark, Spacing Combining (結合文字、幅あり)</span><span class="sxs-lookup"><span data-stu-id="c48b6-439">Mark, Spacing Combining</span></span>|  
|`Me`|<span data-ttu-id="c48b6-440">Mark, Enclosing (結合文字、囲み)</span><span class="sxs-lookup"><span data-stu-id="c48b6-440">Mark, Enclosing</span></span>|  
|`M`|<span data-ttu-id="c48b6-441">すべての分音記号。</span><span class="sxs-lookup"><span data-stu-id="c48b6-441">All diacritic marks.</span></span> <span data-ttu-id="c48b6-442">これには、`Mn`、`Mc`、および `Me` の各カテゴリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-442">This includes the `Mn`, `Mc`, and `Me` categories.</span></span>|  
|`Nd`|<span data-ttu-id="c48b6-443">Number, Decimal Digit (数、10 進数字)</span><span class="sxs-lookup"><span data-stu-id="c48b6-443">Number, Decimal Digit</span></span>|  
|`Nl`|<span data-ttu-id="c48b6-444">Number, Letter (数、字)</span><span class="sxs-lookup"><span data-stu-id="c48b6-444">Number, Letter</span></span>|  
|`No`|<span data-ttu-id="c48b6-445">Number, Other (数、その他)</span><span class="sxs-lookup"><span data-stu-id="c48b6-445">Number, Other</span></span>|  
|`N`|<span data-ttu-id="c48b6-446">すべての数。</span><span class="sxs-lookup"><span data-stu-id="c48b6-446">All numbers.</span></span> <span data-ttu-id="c48b6-447">これには、`Nd`、`Nl`、および `No` の各カテゴリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-447">This includes the `Nd`, `Nl`, and `No` categories.</span></span>|  
|`Pc`|<span data-ttu-id="c48b6-448">Punctuation, Connector (句読点、接続)</span><span class="sxs-lookup"><span data-stu-id="c48b6-448">Punctuation, Connector</span></span>|  
|`Pd`|<span data-ttu-id="c48b6-449">Punctuation, Dash (句読点、ダッシュ)</span><span class="sxs-lookup"><span data-stu-id="c48b6-449">Punctuation, Dash</span></span>|  
|`Ps`|<span data-ttu-id="c48b6-450">Punctuation, Open (句読点、開き)</span><span class="sxs-lookup"><span data-stu-id="c48b6-450">Punctuation, Open</span></span>|  
|`Pe`|<span data-ttu-id="c48b6-451">Punctuation, Close (句読点、閉じ)</span><span class="sxs-lookup"><span data-stu-id="c48b6-451">Punctuation, Close</span></span>|  
|`Pi`|<span data-ttu-id="c48b6-452">Punctuation, Initial quote (句読点、開始引用符。使用状況に応じて Ps または Pe のように動作)</span><span class="sxs-lookup"><span data-stu-id="c48b6-452">Punctuation, Initial quote (may behave like Ps or Pe depending on usage)</span></span>|  
|`Pf`|<span data-ttu-id="c48b6-453">Punctuation, Final quote (句読点、終了引用符。使用状況に応じて Ps または Pe のように動作)</span><span class="sxs-lookup"><span data-stu-id="c48b6-453">Punctuation, Final quote (may behave like Ps or Pe depending on usage)</span></span>|  
|`Po`|<span data-ttu-id="c48b6-454">Punctuation, Other (句読点、その他)</span><span class="sxs-lookup"><span data-stu-id="c48b6-454">Punctuation, Other</span></span>|  
|`P`|<span data-ttu-id="c48b6-455">すべての句読点。</span><span class="sxs-lookup"><span data-stu-id="c48b6-455">All punctuation characters.</span></span> <span data-ttu-id="c48b6-456">これには、`Pc`、`Pd`、`Ps`、`Pe`、`Pi`、`Pf`、および `Po` の各カテゴリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-456">This includes the `Pc`, `Pd`, `Ps`, `Pe`, `Pi`, `Pf`, and `Po` categories.</span></span>|  
|`Sm`|<span data-ttu-id="c48b6-457">Symbol, Math (記号、数学)</span><span class="sxs-lookup"><span data-stu-id="c48b6-457">Symbol, Math</span></span>|  
|`Sc`|<span data-ttu-id="c48b6-458">Symbol, Currency (記号、通貨)</span><span class="sxs-lookup"><span data-stu-id="c48b6-458">Symbol, Currency</span></span>|  
|`Sk`|<span data-ttu-id="c48b6-459">Symbol, Modifier (記号、修飾)</span><span class="sxs-lookup"><span data-stu-id="c48b6-459">Symbol, Modifier</span></span>|  
|`So`|<span data-ttu-id="c48b6-460">Symbol, Other (記号、その他)</span><span class="sxs-lookup"><span data-stu-id="c48b6-460">Symbol, Other</span></span>|  
|`S`|<span data-ttu-id="c48b6-461">すべての記号。</span><span class="sxs-lookup"><span data-stu-id="c48b6-461">All symbols.</span></span> <span data-ttu-id="c48b6-462">これには、`Sm`、`Sc`、`Sk`、および `So` の各カテゴリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-462">This includes the `Sm`, `Sc`, `Sk`, and `So` categories.</span></span>|  
|`Zs`|<span data-ttu-id="c48b6-463">Separator, Space (区切り、空白)</span><span class="sxs-lookup"><span data-stu-id="c48b6-463">Separator, Space</span></span>|  
|`Zl`|<span data-ttu-id="c48b6-464">Separator, Line (区切り、行)</span><span class="sxs-lookup"><span data-stu-id="c48b6-464">Separator, Line</span></span>|  
|`Zp`|<span data-ttu-id="c48b6-465">Separator, Paragraph (区切り、段落)</span><span class="sxs-lookup"><span data-stu-id="c48b6-465">Separator, Paragraph</span></span>|  
|`Z`|<span data-ttu-id="c48b6-466">すべての区切り記号。</span><span class="sxs-lookup"><span data-stu-id="c48b6-466">All separator characters.</span></span> <span data-ttu-id="c48b6-467">これには、`Zs`、`Zl`、および `Zp` の各カテゴリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-467">This includes the `Zs`, `Zl`, and `Zp` categories.</span></span>|  
|`Cc`|<span data-ttu-id="c48b6-468">Other, Control (区切り、制御)</span><span class="sxs-lookup"><span data-stu-id="c48b6-468">Other, Control</span></span>|  
|`Cf`|<span data-ttu-id="c48b6-469">Other, Format (その他、書式)</span><span class="sxs-lookup"><span data-stu-id="c48b6-469">Other, Format</span></span>|  
|`Cs`|<span data-ttu-id="c48b6-470">Other, Surrogate (その他、サロゲート)</span><span class="sxs-lookup"><span data-stu-id="c48b6-470">Other, Surrogate</span></span>|  
|`Co`|<span data-ttu-id="c48b6-471">Other, Private Use (その他、プライベート用途)</span><span class="sxs-lookup"><span data-stu-id="c48b6-471">Other, Private Use</span></span>|  
|`Cn`|<span data-ttu-id="c48b6-472">Other, Not Assigned (その他、未割り当て。このプロパティを持つ文字はありません)</span><span class="sxs-lookup"><span data-stu-id="c48b6-472">Other, Not Assigned (no characters have this property)</span></span>|  
|`C`|<span data-ttu-id="c48b6-473">すべての制御文字。</span><span class="sxs-lookup"><span data-stu-id="c48b6-473">All control characters.</span></span> <span data-ttu-id="c48b6-474">これには、`Cc`、`Cf`、`Cs`、`Co`、および `Cn` の各カテゴリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-474">This includes the `Cc`, `Cf`, `Cs`, `Co`, and `Cn` categories.</span></span>|  
  
 <span data-ttu-id="c48b6-475">特定の文字の Unicode カテゴリを確認するには、その文字を <xref:System.Char.GetUnicodeCategory%2A> メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-475">You can determine the Unicode category of any particular character by passing that character to the <xref:System.Char.GetUnicodeCategory%2A> method.</span></span> <span data-ttu-id="c48b6-476"><xref:System.Char.GetUnicodeCategory%2A> メソッドを使用して、選択したラテン文字を含む配列の各要素のカテゴリを確認する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-476">The following example uses the <xref:System.Char.GetUnicodeCategory%2A> method to determine the category of each element in an array that contains selected Latin characters.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/getunicodecategory1.cs#14)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/getunicodecategory1.vb#14)]  
  
 [<span data-ttu-id="c48b6-477">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c48b6-477">Back to Top</span></span>](#Top)  
  
<a name="SupportedNamedBlocks"></a>   
## <a name="supported-named-blocks"></a><span data-ttu-id="c48b6-478">サポートされている名前付きブロック</span><span class="sxs-lookup"><span data-stu-id="c48b6-478">Supported Named Blocks</span></span>  
 <span data-ttu-id="c48b6-479">.NET には、次の表に示す名前付きブロックが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c48b6-479">.NET provides the named blocks listed in the following table.</span></span> <span data-ttu-id="c48b6-480">サポートされている一連の名前付きブロックは、Unicode 4.0 および Perl 5.6 に基づいています。</span><span class="sxs-lookup"><span data-stu-id="c48b6-480">The set of supported named blocks is based on Unicode 4.0 and Perl 5.6.</span></span>  
  
|<span data-ttu-id="c48b6-481">コード ポイント範囲</span><span class="sxs-lookup"><span data-stu-id="c48b6-481">Code point range</span></span>|<span data-ttu-id="c48b6-482">ブロック名</span><span class="sxs-lookup"><span data-stu-id="c48b6-482">Block name</span></span>|  
|----------------------|----------------|  
|<span data-ttu-id="c48b6-483">0000 ～ 007F</span><span class="sxs-lookup"><span data-stu-id="c48b6-483">0000 - 007F</span></span>|`IsBasicLatin`|  
|<span data-ttu-id="c48b6-484">0080 ～ 00FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-484">0080 - 00FF</span></span>|`IsLatin-1Supplement`|  
|<span data-ttu-id="c48b6-485">0100 ～ 017F</span><span class="sxs-lookup"><span data-stu-id="c48b6-485">0100 - 017F</span></span>|`IsLatinExtended-A`|  
|<span data-ttu-id="c48b6-486">0180 ～ 024F</span><span class="sxs-lookup"><span data-stu-id="c48b6-486">0180 - 024F</span></span>|`IsLatinExtended-B`|  
|<span data-ttu-id="c48b6-487">0250 ～ 02AF</span><span class="sxs-lookup"><span data-stu-id="c48b6-487">0250 - 02AF</span></span>|`IsIPAExtensions`|  
|<span data-ttu-id="c48b6-488">02B0 ～ 02FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-488">02B0 - 02FF</span></span>|`IsSpacingModifierLetters`|  
|<span data-ttu-id="c48b6-489">0300 ～ 036F</span><span class="sxs-lookup"><span data-stu-id="c48b6-489">0300 - 036F</span></span>|`IsCombiningDiacriticalMarks`|  
|<span data-ttu-id="c48b6-490">0370 ～ 03FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-490">0370 - 03FF</span></span>|`IsGreek`<br /><br /> <span data-ttu-id="c48b6-491">- または -</span><span class="sxs-lookup"><span data-stu-id="c48b6-491">-or-</span></span><br /><br /> `IsGreekandCoptic`|  
|<span data-ttu-id="c48b6-492">0400 ～ 04FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-492">0400 - 04FF</span></span>|`IsCyrillic`|  
|<span data-ttu-id="c48b6-493">0500 ～ 052F</span><span class="sxs-lookup"><span data-stu-id="c48b6-493">0500 - 052F</span></span>|`IsCyrillicSupplement`|  
|<span data-ttu-id="c48b6-494">0530 ～ 058F</span><span class="sxs-lookup"><span data-stu-id="c48b6-494">0530 - 058F</span></span>|`IsArmenian`|  
|<span data-ttu-id="c48b6-495">0590 ～ 05FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-495">0590 - 05FF</span></span>|`IsHebrew`|  
|<span data-ttu-id="c48b6-496">0600 ～ 06FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-496">0600 - 06FF</span></span>|`IsArabic`|  
|<span data-ttu-id="c48b6-497">0700 ～ 074F</span><span class="sxs-lookup"><span data-stu-id="c48b6-497">0700 - 074F</span></span>|`IsSyriac`|  
|<span data-ttu-id="c48b6-498">0780 ～ 07BF</span><span class="sxs-lookup"><span data-stu-id="c48b6-498">0780 - 07BF</span></span>|`IsThaana`|  
|<span data-ttu-id="c48b6-499">0900 ～ 097F</span><span class="sxs-lookup"><span data-stu-id="c48b6-499">0900 - 097F</span></span>|`IsDevanagari`|  
|<span data-ttu-id="c48b6-500">0980 ～ 09FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-500">0980 - 09FF</span></span>|`IsBengali`|  
|<span data-ttu-id="c48b6-501">0A00 ～ 0A7F</span><span class="sxs-lookup"><span data-stu-id="c48b6-501">0A00 - 0A7F</span></span>|`IsGurmukhi`|  
|<span data-ttu-id="c48b6-502">0A80 ～ 0AFF</span><span class="sxs-lookup"><span data-stu-id="c48b6-502">0A80 - 0AFF</span></span>|`IsGujarati`|  
|<span data-ttu-id="c48b6-503">0B00 ～ 0B7F</span><span class="sxs-lookup"><span data-stu-id="c48b6-503">0B00 - 0B7F</span></span>|`IsOriya`|  
|<span data-ttu-id="c48b6-504">0B80 ～ 0BFF</span><span class="sxs-lookup"><span data-stu-id="c48b6-504">0B80 - 0BFF</span></span>|`IsTamil`|  
|<span data-ttu-id="c48b6-505">0C00 ～ 0C7F</span><span class="sxs-lookup"><span data-stu-id="c48b6-505">0C00 - 0C7F</span></span>|`IsTelugu`|  
|<span data-ttu-id="c48b6-506">0C80 ～ 0CFF</span><span class="sxs-lookup"><span data-stu-id="c48b6-506">0C80 - 0CFF</span></span>|`IsKannada`|  
|<span data-ttu-id="c48b6-507">0D00 ～ 0D7F</span><span class="sxs-lookup"><span data-stu-id="c48b6-507">0D00 - 0D7F</span></span>|`IsMalayalam`|  
|<span data-ttu-id="c48b6-508">0D80 ～ 0DFF</span><span class="sxs-lookup"><span data-stu-id="c48b6-508">0D80 - 0DFF</span></span>|`IsSinhala`|  
|<span data-ttu-id="c48b6-509">0E00 ～ 0E7F</span><span class="sxs-lookup"><span data-stu-id="c48b6-509">0E00 - 0E7F</span></span>|`IsThai`|  
|<span data-ttu-id="c48b6-510">0E80 ～ 0EFF</span><span class="sxs-lookup"><span data-stu-id="c48b6-510">0E80 - 0EFF</span></span>|`IsLao`|  
|<span data-ttu-id="c48b6-511">0F00 ～ 0FFF</span><span class="sxs-lookup"><span data-stu-id="c48b6-511">0F00 - 0FFF</span></span>|`IsTibetan`|  
|<span data-ttu-id="c48b6-512">1000 ～ 109F</span><span class="sxs-lookup"><span data-stu-id="c48b6-512">1000 - 109F</span></span>|`IsMyanmar`|  
|<span data-ttu-id="c48b6-513">10A0 ～ 10FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-513">10A0 - 10FF</span></span>|`IsGeorgian`|  
|<span data-ttu-id="c48b6-514">1100 ～ 11FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-514">1100 - 11FF</span></span>|`IsHangulJamo`|  
|<span data-ttu-id="c48b6-515">1200 ～ 137F</span><span class="sxs-lookup"><span data-stu-id="c48b6-515">1200 - 137F</span></span>|`IsEthiopic`|  
|<span data-ttu-id="c48b6-516">13A0 ～ 13FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-516">13A0 - 13FF</span></span>|`IsCherokee`|  
|<span data-ttu-id="c48b6-517">1400 ～ 167F</span><span class="sxs-lookup"><span data-stu-id="c48b6-517">1400 - 167F</span></span>|`IsUnifiedCanadianAboriginalSyllabics`|  
|<span data-ttu-id="c48b6-518">1680 ～ 169F</span><span class="sxs-lookup"><span data-stu-id="c48b6-518">1680 - 169F</span></span>|`IsOgham`|  
|<span data-ttu-id="c48b6-519">16A0 ～ 16FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-519">16A0 - 16FF</span></span>|`IsRunic`|  
|<span data-ttu-id="c48b6-520">1700 ～ 171F</span><span class="sxs-lookup"><span data-stu-id="c48b6-520">1700 - 171F</span></span>|`IsTagalog`|  
|<span data-ttu-id="c48b6-521">1720 ～ 173F</span><span class="sxs-lookup"><span data-stu-id="c48b6-521">1720 - 173F</span></span>|`IsHanunoo`|  
|<span data-ttu-id="c48b6-522">1740 ～ 175F</span><span class="sxs-lookup"><span data-stu-id="c48b6-522">1740 - 175F</span></span>|`IsBuhid`|  
|<span data-ttu-id="c48b6-523">1760 ～ 177F</span><span class="sxs-lookup"><span data-stu-id="c48b6-523">1760 - 177F</span></span>|`IsTagbanwa`|  
|<span data-ttu-id="c48b6-524">1780 ～ 17FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-524">1780 - 17FF</span></span>|`IsKhmer`|  
|<span data-ttu-id="c48b6-525">1800 ～ 18AF</span><span class="sxs-lookup"><span data-stu-id="c48b6-525">1800 - 18AF</span></span>|`IsMongolian`|  
|<span data-ttu-id="c48b6-526">1900 ～ 194F</span><span class="sxs-lookup"><span data-stu-id="c48b6-526">1900 - 194F</span></span>|`IsLimbu`|  
|<span data-ttu-id="c48b6-527">1950 ～ 197F</span><span class="sxs-lookup"><span data-stu-id="c48b6-527">1950 - 197F</span></span>|`IsTaiLe`|  
|<span data-ttu-id="c48b6-528">19E0 ～ 19FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-528">19E0 - 19FF</span></span>|`IsKhmerSymbols`|  
|<span data-ttu-id="c48b6-529">1D00 ～ 1D7F</span><span class="sxs-lookup"><span data-stu-id="c48b6-529">1D00 - 1D7F</span></span>|`IsPhoneticExtensions`|  
|<span data-ttu-id="c48b6-530">1E00 ～ 1EFF</span><span class="sxs-lookup"><span data-stu-id="c48b6-530">1E00 - 1EFF</span></span>|`IsLatinExtendedAdditional`|  
|<span data-ttu-id="c48b6-531">1F00 ～ 1FFF</span><span class="sxs-lookup"><span data-stu-id="c48b6-531">1F00 - 1FFF</span></span>|`IsGreekExtended`|  
|<span data-ttu-id="c48b6-532">2000 ～ 206F</span><span class="sxs-lookup"><span data-stu-id="c48b6-532">2000 - 206F</span></span>|`IsGeneralPunctuation`|  
|<span data-ttu-id="c48b6-533">2070 ～ 209F</span><span class="sxs-lookup"><span data-stu-id="c48b6-533">2070 - 209F</span></span>|`IsSuperscriptsandSubscripts`|  
|<span data-ttu-id="c48b6-534">20A0 ～ 20CF</span><span class="sxs-lookup"><span data-stu-id="c48b6-534">20A0 - 20CF</span></span>|`IsCurrencySymbols`|  
|<span data-ttu-id="c48b6-535">20D0 ～ 20FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-535">20D0 - 20FF</span></span>|`IsCombiningDiacriticalMarksforSymbols`<br /><br /> <span data-ttu-id="c48b6-536">- または -</span><span class="sxs-lookup"><span data-stu-id="c48b6-536">-or-</span></span><br /><br /> `IsCombiningMarksforSymbols`|  
|<span data-ttu-id="c48b6-537">2100 ～ 214F</span><span class="sxs-lookup"><span data-stu-id="c48b6-537">2100 - 214F</span></span>|`IsLetterlikeSymbols`|  
|<span data-ttu-id="c48b6-538">2150 ～ 218F</span><span class="sxs-lookup"><span data-stu-id="c48b6-538">2150 - 218F</span></span>|`IsNumberForms`|  
|<span data-ttu-id="c48b6-539">2190 ～ 21FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-539">2190 - 21FF</span></span>|`IsArrows`|  
|<span data-ttu-id="c48b6-540">2200 ～ 22FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-540">2200 - 22FF</span></span>|`IsMathematicalOperators`|  
|<span data-ttu-id="c48b6-541">2300 ～ 23FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-541">2300 - 23FF</span></span>|`IsMiscellaneousTechnical`|  
|<span data-ttu-id="c48b6-542">2400 ～ 243F</span><span class="sxs-lookup"><span data-stu-id="c48b6-542">2400 - 243F</span></span>|`IsControlPictures`|  
|<span data-ttu-id="c48b6-543">2440 ～ 245F</span><span class="sxs-lookup"><span data-stu-id="c48b6-543">2440 - 245F</span></span>|`IsOpticalCharacterRecognition`|  
|<span data-ttu-id="c48b6-544">2460 ～ 24FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-544">2460 - 24FF</span></span>|`IsEnclosedAlphanumerics`|  
|<span data-ttu-id="c48b6-545">2500 ～ 257F</span><span class="sxs-lookup"><span data-stu-id="c48b6-545">2500 - 257F</span></span>|`IsBoxDrawing`|  
|<span data-ttu-id="c48b6-546">2580 ～ 259F</span><span class="sxs-lookup"><span data-stu-id="c48b6-546">2580 - 259F</span></span>|`IsBlockElements`|  
|<span data-ttu-id="c48b6-547">25A0 ～ 25FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-547">25A0 - 25FF</span></span>|`IsGeometricShapes`|  
|<span data-ttu-id="c48b6-548">2600 ～ 26FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-548">2600 - 26FF</span></span>|`IsMiscellaneousSymbols`|  
|<span data-ttu-id="c48b6-549">2700 ～ 27BF</span><span class="sxs-lookup"><span data-stu-id="c48b6-549">2700 - 27BF</span></span>|`IsDingbats`|  
|<span data-ttu-id="c48b6-550">27C0 ～ 27EF</span><span class="sxs-lookup"><span data-stu-id="c48b6-550">27C0 - 27EF</span></span>|`IsMiscellaneousMathematicalSymbols-A`|  
|<span data-ttu-id="c48b6-551">27F0 ～ 27FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-551">27F0 - 27FF</span></span>|`IsSupplementalArrows-A`|  
|<span data-ttu-id="c48b6-552">2800 ～ 28FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-552">2800 - 28FF</span></span>|`IsBraillePatterns`|  
|<span data-ttu-id="c48b6-553">2900 ～ 297F</span><span class="sxs-lookup"><span data-stu-id="c48b6-553">2900 - 297F</span></span>|`IsSupplementalArrows-B`|  
|<span data-ttu-id="c48b6-554">2980 ～ 29FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-554">2980 - 29FF</span></span>|`IsMiscellaneousMathematicalSymbols-B`|  
|<span data-ttu-id="c48b6-555">2A00 ～ 2AFF</span><span class="sxs-lookup"><span data-stu-id="c48b6-555">2A00 - 2AFF</span></span>|`IsSupplementalMathematicalOperators`|  
|<span data-ttu-id="c48b6-556">2B00 ～ 2BFF</span><span class="sxs-lookup"><span data-stu-id="c48b6-556">2B00 - 2BFF</span></span>|`IsMiscellaneousSymbolsandArrows`|  
|<span data-ttu-id="c48b6-557">2E80 ～ 2EFF</span><span class="sxs-lookup"><span data-stu-id="c48b6-557">2E80 - 2EFF</span></span>|`IsCJKRadicalsSupplement`|  
|<span data-ttu-id="c48b6-558">2F00 ～ 2FDF</span><span class="sxs-lookup"><span data-stu-id="c48b6-558">2F00 - 2FDF</span></span>|`IsKangxiRadicals`|  
|<span data-ttu-id="c48b6-559">2FF0 ～ 2FFF</span><span class="sxs-lookup"><span data-stu-id="c48b6-559">2FF0 - 2FFF</span></span>|`IsIdeographicDescriptionCharacters`|  
|<span data-ttu-id="c48b6-560">3000 ～ 303F</span><span class="sxs-lookup"><span data-stu-id="c48b6-560">3000 - 303F</span></span>|`IsCJKSymbolsandPunctuation`|  
|<span data-ttu-id="c48b6-561">3040 ～ 309F</span><span class="sxs-lookup"><span data-stu-id="c48b6-561">3040 - 309F</span></span>|`IsHiragana`|  
|<span data-ttu-id="c48b6-562">30A0 ～ 30FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-562">30A0 - 30FF</span></span>|`IsKatakana`|  
|<span data-ttu-id="c48b6-563">3100 ～ 312F</span><span class="sxs-lookup"><span data-stu-id="c48b6-563">3100 - 312F</span></span>|`IsBopomofo`|  
|<span data-ttu-id="c48b6-564">3130 ～ 318F</span><span class="sxs-lookup"><span data-stu-id="c48b6-564">3130 - 318F</span></span>|`IsHangulCompatibilityJamo`|  
|<span data-ttu-id="c48b6-565">3190 ～ 319F</span><span class="sxs-lookup"><span data-stu-id="c48b6-565">3190 - 319F</span></span>|`IsKanbun`|  
|<span data-ttu-id="c48b6-566">31A0 ～ 31BF</span><span class="sxs-lookup"><span data-stu-id="c48b6-566">31A0 - 31BF</span></span>|`IsBopomofoExtended`|  
|<span data-ttu-id="c48b6-567">31F0 ～ 31FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-567">31F0 - 31FF</span></span>|`IsKatakanaPhoneticExtensions`|  
|<span data-ttu-id="c48b6-568">3200 ～ 32FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-568">3200 - 32FF</span></span>|`IsEnclosedCJKLettersandMonths`|  
|<span data-ttu-id="c48b6-569">3300 ～ 33FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-569">3300 - 33FF</span></span>|`IsCJKCompatibility`|  
|<span data-ttu-id="c48b6-570">3400 ～ 4DBF</span><span class="sxs-lookup"><span data-stu-id="c48b6-570">3400 - 4DBF</span></span>|`IsCJKUnifiedIdeographsExtensionA`|  
|<span data-ttu-id="c48b6-571">4DC0 ～ 4DFF</span><span class="sxs-lookup"><span data-stu-id="c48b6-571">4DC0 - 4DFF</span></span>|`IsYijingHexagramSymbols`|  
|<span data-ttu-id="c48b6-572">4E00 ～ 9FFF</span><span class="sxs-lookup"><span data-stu-id="c48b6-572">4E00 - 9FFF</span></span>|`IsCJKUnifiedIdeographs`|  
|<span data-ttu-id="c48b6-573">A000 ～ A48F</span><span class="sxs-lookup"><span data-stu-id="c48b6-573">A000 - A48F</span></span>|`IsYiSyllables`|  
|<span data-ttu-id="c48b6-574">A490 ～ A4CF</span><span class="sxs-lookup"><span data-stu-id="c48b6-574">A490 - A4CF</span></span>|`IsYiRadicals`|  
|<span data-ttu-id="c48b6-575">AC00 ～ D7AF</span><span class="sxs-lookup"><span data-stu-id="c48b6-575">AC00 - D7AF</span></span>|`IsHangulSyllables`|  
|<span data-ttu-id="c48b6-576">D800 ～ DB7F</span><span class="sxs-lookup"><span data-stu-id="c48b6-576">D800 - DB7F</span></span>|`IsHighSurrogates`|  
|<span data-ttu-id="c48b6-577">DB80 ～ DBFF</span><span class="sxs-lookup"><span data-stu-id="c48b6-577">DB80 - DBFF</span></span>|`IsHighPrivateUseSurrogates`|  
|<span data-ttu-id="c48b6-578">DC00 ～ DFFF</span><span class="sxs-lookup"><span data-stu-id="c48b6-578">DC00 - DFFF</span></span>|`IsLowSurrogates`|  
|<span data-ttu-id="c48b6-579">E000 ～ F8FF</span><span class="sxs-lookup"><span data-stu-id="c48b6-579">E000 - F8FF</span></span>|<span data-ttu-id="c48b6-580">`IsPrivateUse` または `IsPrivateUseArea`</span><span class="sxs-lookup"><span data-stu-id="c48b6-580">`IsPrivateUse` or `IsPrivateUseArea`</span></span>|  
|<span data-ttu-id="c48b6-581">F900 ～ FAFF</span><span class="sxs-lookup"><span data-stu-id="c48b6-581">F900 - FAFF</span></span>|`IsCJKCompatibilityIdeographs`|  
|<span data-ttu-id="c48b6-582">FB00 ～ FB4F</span><span class="sxs-lookup"><span data-stu-id="c48b6-582">FB00 - FB4F</span></span>|`IsAlphabeticPresentationForms`|  
|<span data-ttu-id="c48b6-583">FB50 ～ FDFF</span><span class="sxs-lookup"><span data-stu-id="c48b6-583">FB50 - FDFF</span></span>|`IsArabicPresentationForms-A`|  
|<span data-ttu-id="c48b6-584">FE00 ～ FE0F</span><span class="sxs-lookup"><span data-stu-id="c48b6-584">FE00 - FE0F</span></span>|`IsVariationSelectors`|  
|<span data-ttu-id="c48b6-585">FE20 ～ FE2F</span><span class="sxs-lookup"><span data-stu-id="c48b6-585">FE20 - FE2F</span></span>|`IsCombiningHalfMarks`|  
|<span data-ttu-id="c48b6-586">FE30 ～ FE4F</span><span class="sxs-lookup"><span data-stu-id="c48b6-586">FE30 - FE4F</span></span>|`IsCJKCompatibilityForms`|  
|<span data-ttu-id="c48b6-587">FE50 ～ FE6F</span><span class="sxs-lookup"><span data-stu-id="c48b6-587">FE50 - FE6F</span></span>|`IsSmallFormVariants`|  
|<span data-ttu-id="c48b6-588">FE70 ～ FEFF</span><span class="sxs-lookup"><span data-stu-id="c48b6-588">FE70 - FEFF</span></span>|`IsArabicPresentationForms-B`|  
|<span data-ttu-id="c48b6-589">FF00 ～ FFEF</span><span class="sxs-lookup"><span data-stu-id="c48b6-589">FF00 - FFEF</span></span>|`IsHalfwidthandFullwidthForms`|  
|<span data-ttu-id="c48b6-590">FFF0 ～ FFFF</span><span class="sxs-lookup"><span data-stu-id="c48b6-590">FFF0 - FFFF</span></span>|`IsSpecials`|  
  
 [<span data-ttu-id="c48b6-591">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="c48b6-591">Back to Top</span></span>](#Top)  
  
<a name="CharacterClassSubtraction"></a>   
## <a name="character-class-subtraction-basegroup---excludedgroup"></a><span data-ttu-id="c48b6-592">文字クラスの減算: [base_group - [excluded_group]]</span><span class="sxs-lookup"><span data-stu-id="c48b6-592">Character Class Subtraction: [base_group - [excluded_group]]</span></span>  
 <span data-ttu-id="c48b6-593">文字クラスは、文字のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-593">A character class defines a set of characters.</span></span> <span data-ttu-id="c48b6-594">文字クラス減算によって、ある文字クラスから別の文字クラスの文字を除外した文字セットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-594">Character class subtraction yields a set of characters that is the result of excluding the characters in one character class from another character class.</span></span>  
  
 <span data-ttu-id="c48b6-595">文字クラス減算式の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c48b6-595">A character class subtraction expression has the following form:</span></span>  
  
 <span data-ttu-id="c48b6-596">`[` *base_group* `-[` *excluded_group* `]]`</span><span class="sxs-lookup"><span data-stu-id="c48b6-596">`[` *base_group* `-[` *excluded_group* `]]`</span></span>  
  
 <span data-ttu-id="c48b6-597">角かっこ (`[]`) とハイフン (`-`) は省略できません。</span><span class="sxs-lookup"><span data-stu-id="c48b6-597">The square brackets (`[]`) and hyphen (`-`) are mandatory.</span></span> <span data-ttu-id="c48b6-598">*base_group* は、[文字グループの肯定](#PositiveGroup)または[文字グループの否定](#NegativeGroup)です。</span><span class="sxs-lookup"><span data-stu-id="c48b6-598">The *base_group* is a [positive character group](#PositiveGroup) or a [negative character group](#NegativeGroup).</span></span> <span data-ttu-id="c48b6-599">*excluded_group* は、別の文字グループの肯定または文字グループの否定、あるいは別の文字クラス減算式です (つまり文字クラス減算式は入れ子にすることができます)。</span><span class="sxs-lookup"><span data-stu-id="c48b6-599">The *excluded_group* component is another positive or negative character group, or another character class subtraction expression (that is, you can nest character class subtraction expressions).</span></span>  
  
 <span data-ttu-id="c48b6-600">たとえば、"a" ～ "z" の文字範囲で構成される基本グループがあるとします。</span><span class="sxs-lookup"><span data-stu-id="c48b6-600">For example, suppose you have a base group that consists of the character range from "a" through "z".</span></span> <span data-ttu-id="c48b6-601">"m" を除外した基本グループで構成される文字のセットを定義するには、`[a-z-[m]]` を使用します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-601">To define the set of characters that consists of the base group except for the character "m", use `[a-z-[m]]`.</span></span> <span data-ttu-id="c48b6-602">"d"、"j" および "p" の文字を除外した基本グループで構成される文字のセットを定義するには、`[a-z-[djp]]` を使用します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-602">To define the set of characters that consists of the base group except for the set of characters "d", "j", and "p", use `[a-z-[djp]]`.</span></span> <span data-ttu-id="c48b6-603">"m" ～ "p" の文字範囲を除外した基本グループで構成される文字のセットを定義するには、`[a-z-[m-p]]` を使用します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-603">To define the set of characters that consists of the base group except for the character range from "m" through "p", use `[a-z-[m-p]]`.</span></span>  
  
 <span data-ttu-id="c48b6-604">入れ子になった文字クラス減算式 `[a-z-[d-w-[m-o]]]` について考えてみます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-604">Consider the nested character class subtraction expression, `[a-z-[d-w-[m-o]]]`.</span></span> <span data-ttu-id="c48b6-605">この式は、最も内部の文字範囲から順に外側へと評価されます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-605">The expression is evaluated from the innermost character range outward.</span></span> <span data-ttu-id="c48b6-606">まず、"m" ～ "o" の文字範囲が "d" ～ "w" の文字範囲から減算されて、"d" ～ "l" および "p" ～ "w" の文字セットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-606">First, the character range from "m" through "o" is subtracted from the character range "d" through "w", which yields the set of characters from "d" through "l" and "p" through "w".</span></span> <span data-ttu-id="c48b6-607">さらにこのセットが "a" ～ "z" の文字範囲から減算されて、`[abcmnoxyz]` という文字セットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-607">That set is then subtracted from the character range from "a" through "z", which yields the set of characters `[abcmnoxyz]`.</span></span>  
  
 <span data-ttu-id="c48b6-608">文字クラス減算では、任意の文字クラスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c48b6-608">You can use any character class with character class subtraction.</span></span> <span data-ttu-id="c48b6-609">\u0000 ～ \uFFFF の Unicode 文字から空白文字 (`\s`)、句読点一般カテゴリの文字 (`\p{P}`)、`IsGreek` 名前付きブロック内の文字 (`\p{IsGreek}`)、および Unicode NEXT LINE 制御文字 (\x85) を除いた文字のセットを定義するには、`[\u0000-\uFFFF-[\s\p{P}\p{IsGreek}\x85]]` を使用します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-609">To define the set of characters that consists of all Unicode characters from \u0000 through \uFFFF except white-space characters (`\s`), the characters in the punctuation general category (`\p{P}`), the characters in the `IsGreek` named block (`\p{IsGreek}`), and the Unicode NEXT LINE control character (\x85), use `[\u0000-\uFFFF-[\s\p{P}\p{IsGreek}\x85]]`.</span></span>  
  
 <span data-ttu-id="c48b6-610">有効な結果を生成する文字クラス減算式の文字クラスを選択します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-610">Choose character classes for a character class subtraction expression that will yield useful results.</span></span> <span data-ttu-id="c48b6-611">どの文字にも一致しない空の文字セットを生成する式、または元の基本グループと同じになる式は避けてください。</span><span class="sxs-lookup"><span data-stu-id="c48b6-611">Avoid an expression that yields an empty set of characters, which cannot match anything, or an expression that is equivalent to the original base group.</span></span> <span data-ttu-id="c48b6-612">たとえば、`[\p{IsBasicLatin}-[\x00-\x7F]]` という式は、`IsBasicLatin` 一般カテゴリから `IsBasicLatin` 文字範囲のすべての文字を減算して空のセットを生成します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-612">For example, the empty set is the result of the expression `[\p{IsBasicLatin}-[\x00-\x7F]]`, which subtracts all characters in the `IsBasicLatin` character range from the `IsBasicLatin` general category.</span></span> <span data-ttu-id="c48b6-613">同様に、`[a-z-[0-9]]` という式は元の基本グループと同じセットを生成します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-613">Similarly, the original base group is the result of the expression `[a-z-[0-9]]`.</span></span>  <span data-ttu-id="c48b6-614">これは、"a" ～ "z" の文字範囲である基本グループに、"0" ～ "9" という 10 進数字の文字範囲から成る除外対象グループ内の文字が含まれないためです。</span><span class="sxs-lookup"><span data-stu-id="c48b6-614">This is because the base group, which is the character range of letters from "a" through "z", does not contain any characters in the excluded group, which is the character range of decimal digits from "0" through "9".</span></span>  
  
 <span data-ttu-id="c48b6-615">入力文字列内の 0 および奇数と一致する正規表現 `^[0-9-[2468]]+$` を定義する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-615">The following example defines a regular expression, `^[0-9-[2468]]+$`, that matches zero and odd digits in an input string.</span></span>  <span data-ttu-id="c48b6-616">この正規表現の解釈を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-616">The regular expression is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="c48b6-617">要素</span><span class="sxs-lookup"><span data-stu-id="c48b6-617">Element</span></span>|<span data-ttu-id="c48b6-618">説明</span><span class="sxs-lookup"><span data-stu-id="c48b6-618">Description</span></span>|  
|-------------|-----------------|  
|^|<span data-ttu-id="c48b6-619">入力文字列の先頭から照合を開始します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-619">Begin the match at the start of the input string.</span></span>|  
|`[0-9-[2468]]+`|<span data-ttu-id="c48b6-620">2、4、6、および 8 を除く 0 ～ 9 の文字の 1 回以上の出現と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-620">Match one or more occurrences of any character from 0 to 9 except for 2, 4, 6, and 8.</span></span> <span data-ttu-id="c48b6-621">つまり、0 または奇数の 1 回以上の出現と一致します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-621">In other words, match one or more occurrences of zero or an odd digit.</span></span>|  
|$|<span data-ttu-id="c48b6-622">入力文字列の末尾で照合を終了します。</span><span class="sxs-lookup"><span data-stu-id="c48b6-622">End the match at the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/classsubtraction1.cs#15)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/classsubtraction1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="c48b6-623">関連項目</span><span class="sxs-lookup"><span data-stu-id="c48b6-623">See also</span></span>

- <xref:System.Char.GetUnicodeCategory%2A>
- [<span data-ttu-id="c48b6-624">正規表現言語 - クイック リファレンス</span><span class="sxs-lookup"><span data-stu-id="c48b6-624">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
- [<span data-ttu-id="c48b6-625">正規表現のオプション</span><span class="sxs-lookup"><span data-stu-id="c48b6-625">Regular Expression Options</span></span>](../../../docs/standard/base-types/regular-expression-options.md)
