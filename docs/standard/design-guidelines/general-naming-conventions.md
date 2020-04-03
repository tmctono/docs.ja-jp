---
title: 一般的な名前付け規則
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], conflicts
- type names, conflicts
- language-specific type names
- names [.NET Framework], about naming guidelines
- names [.NET Framework], abbreviations
- abbreviation naming guidelines
- acronym naming guidelines
- Hungarian notation
- names [.NET Framework], type names
- names [.NET Framework], acronyms
ms.assetid: d3a77ea1-75d2-4969-a8c3-3e1e3e1aaedc
ms.openlocfilehash: ef4a8f571a67477739bbc59d3103ba78dea47177
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635919"
---
# <a name="general-naming-conventions"></a><span data-ttu-id="c93a2-102">一般的な名前付け規則</span><span class="sxs-lookup"><span data-stu-id="c93a2-102">General Naming Conventions</span></span>

<span data-ttu-id="c93a2-103">このセクションでは、単語の選択に関連する一般的な命名規則、略語と略語の使用に関するガイドライン、および言語固有の名前の使用を避ける方法に関する推奨事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="c93a2-103">This section describes general naming conventions that relate to word choice, guidelines on using abbreviations and acronyms, and recommendations on how to avoid using language-specific names.</span></span>

## <a name="word-choice"></a><span data-ttu-id="c93a2-104">単語の選択</span><span class="sxs-lookup"><span data-stu-id="c93a2-104">Word Choice</span></span>
 <span data-ttu-id="c93a2-105">✔️は、読みやすい識別子名を選択します。</span><span class="sxs-lookup"><span data-stu-id="c93a2-105">✔️ DO choose easily readable identifier names.</span></span>

 <span data-ttu-id="c93a2-106">たとえば、という名前`HorizontalAlignment`のプロパティは、 より`AlignmentHorizontal`英語で読み取り可能です。</span><span class="sxs-lookup"><span data-stu-id="c93a2-106">For example, a property named `HorizontalAlignment` is more English-readable than `AlignmentHorizontal`.</span></span>

 <span data-ttu-id="c93a2-107">簡潔✔️よりも読みやすさを優先します。</span><span class="sxs-lookup"><span data-stu-id="c93a2-107">✔️ DO favor readability over brevity.</span></span>

 <span data-ttu-id="c93a2-108">プロパティ名`CanScrollHorizontally`は、X`ScrollableX`軸への参照が不明である場合よりも優れています。</span><span class="sxs-lookup"><span data-stu-id="c93a2-108">The property name `CanScrollHorizontally` is better than `ScrollableX` (an obscure reference to the X-axis).</span></span>

 <span data-ttu-id="c93a2-109">❌下線、ハイフン、その他の英数字以外の文字は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="c93a2-109">❌ DO NOT use underscores, hyphens, or any other nonalphanumeric characters.</span></span>

 <span data-ttu-id="c93a2-110">❌ハンガリー語表記法を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="c93a2-110">❌ DO NOT use Hungarian notation.</span></span>

 <span data-ttu-id="c93a2-111">❌広く使用されているプログラミング言語のキーワードと競合する識別子を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="c93a2-111">❌ AVOID using identifiers that conflict with keywords of widely used programming languages.</span></span>

 <span data-ttu-id="c93a2-112">共通言語仕様 (CLS) の規則 4 に従って、すべての準拠言語は、識別子としてその言語のキーワードを使用する名前付き項目へのアクセスを許可するメカニズムを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c93a2-112">According to Rule 4 of the Common Language Specification (CLS), all compliant languages must provide a mechanism that allows access to named items that use a keyword of that language as an identifier.</span></span> <span data-ttu-id="c93a2-113">たとえば、C# では、 @ 記号をエスケープ メカニズムとして使用します。</span><span class="sxs-lookup"><span data-stu-id="c93a2-113">C#, for example, uses the @ sign as an escape mechanism in this case.</span></span> <span data-ttu-id="c93a2-114">ただし、エスケープ シーケンスを使用するメソッドを使用する方が、一般的なキーワードを使用しない場合よりも、メソッドを使用する方が難しいため、一般的なキーワードを避けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c93a2-114">However, it is still a good idea to avoid common keywords because it is much more difficult to use a method with the escape sequence than one without it.</span></span>

## <a name="using-abbreviations-and-acronyms"></a><span data-ttu-id="c93a2-115">略語と頭字語の使用</span><span class="sxs-lookup"><span data-stu-id="c93a2-115">Using Abbreviations and Acronyms</span></span>
 <span data-ttu-id="c93a2-116">❌識別子名の一部として省略形または短縮を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="c93a2-116">❌ DO NOT use abbreviations or contractions as part of identifier names.</span></span>

 <span data-ttu-id="c93a2-117">たとえば、 ではなく`GetWindow``GetWin`を使用します。</span><span class="sxs-lookup"><span data-stu-id="c93a2-117">For example, use `GetWindow` rather than `GetWin`.</span></span>

 <span data-ttu-id="c93a2-118">❌広く受け入れられていない頭字語を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="c93a2-118">❌ DO NOT use any acronyms that are not widely accepted, and even if they are, only when necessary.</span></span>

## <a name="avoiding-language-specific-names"></a><span data-ttu-id="c93a2-119">言語固有の名前の回避</span><span class="sxs-lookup"><span data-stu-id="c93a2-119">Avoiding Language-Specific Names</span></span>
 <span data-ttu-id="c93a2-120">✔️は、型名に言語固有のキーワードではなく、意味的に興味深い名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="c93a2-120">✔️ DO use semantically interesting names rather than language-specific keywords for type names.</span></span>

 <span data-ttu-id="c93a2-121">たとえば、`GetLength`より`GetInt`良い名前です。</span><span class="sxs-lookup"><span data-stu-id="c93a2-121">For example, `GetLength` is a better name than `GetInt`.</span></span>

 <span data-ttu-id="c93a2-122">識別子の型を超えて意味を持たない場合✔️、言語固有の名前ではなく、一般的な CLR 型名を使用します。</span><span class="sxs-lookup"><span data-stu-id="c93a2-122">✔️ DO use a generic CLR type name, rather than a language-specific name, in the rare cases when an identifier has no semantic meaning beyond its type.</span></span>

 <span data-ttu-id="c93a2-123">たとえば、変換する<xref:System.Int64>メソッドは、 ではなく`ToInt64`という名前`ToLong`にする<xref:System.Int64>必要があります ( C# 固有のエイリアス`long`の CLR 名であるため ) 。</span><span class="sxs-lookup"><span data-stu-id="c93a2-123">For example, a method converting to <xref:System.Int64> should be named `ToInt64`, not `ToLong` (because <xref:System.Int64> is a CLR name for the C#-specific alias `long`).</span></span> <span data-ttu-id="c93a2-124">次の表は、CLR 型名を使用する基本データ型を示しています ( C# 、Visual Basic、および C++ の対応する型名 ) を示します。</span><span class="sxs-lookup"><span data-stu-id="c93a2-124">The following table presents several base data types using the CLR type names (as well as the corresponding type names for C#, Visual Basic, and C++).</span></span>

|<span data-ttu-id="c93a2-125">C#</span><span class="sxs-lookup"><span data-stu-id="c93a2-125">C#</span></span>|<span data-ttu-id="c93a2-126">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c93a2-126">Visual Basic</span></span>|<span data-ttu-id="c93a2-127">C++</span><span class="sxs-lookup"><span data-stu-id="c93a2-127">C++</span></span>|<span data-ttu-id="c93a2-128">CLR</span><span class="sxs-lookup"><span data-stu-id="c93a2-128">CLR</span></span>|
|---------|------------------|-----------|---------|
|<span data-ttu-id="c93a2-129">**sbyte**</span><span class="sxs-lookup"><span data-stu-id="c93a2-129">**sbyte**</span></span>|<span data-ttu-id="c93a2-130">**SByte**</span><span class="sxs-lookup"><span data-stu-id="c93a2-130">**SByte**</span></span>|<span data-ttu-id="c93a2-131">**char**</span><span class="sxs-lookup"><span data-stu-id="c93a2-131">**char**</span></span>|<span data-ttu-id="c93a2-132">**SByte**</span><span class="sxs-lookup"><span data-stu-id="c93a2-132">**SByte**</span></span>|
|<span data-ttu-id="c93a2-133">**byte**</span><span class="sxs-lookup"><span data-stu-id="c93a2-133">**byte**</span></span>|<span data-ttu-id="c93a2-134">**Byte**</span><span class="sxs-lookup"><span data-stu-id="c93a2-134">**Byte**</span></span>|<span data-ttu-id="c93a2-135">**unsigned char**</span><span class="sxs-lookup"><span data-stu-id="c93a2-135">**unsigned char**</span></span>|<span data-ttu-id="c93a2-136">**Byte**</span><span class="sxs-lookup"><span data-stu-id="c93a2-136">**Byte**</span></span>|
|<span data-ttu-id="c93a2-137">**short**</span><span class="sxs-lookup"><span data-stu-id="c93a2-137">**short**</span></span>|<span data-ttu-id="c93a2-138">**短い**</span><span class="sxs-lookup"><span data-stu-id="c93a2-138">**Short**</span></span>|<span data-ttu-id="c93a2-139">**short**</span><span class="sxs-lookup"><span data-stu-id="c93a2-139">**short**</span></span>|<span data-ttu-id="c93a2-140">**Int16**</span><span class="sxs-lookup"><span data-stu-id="c93a2-140">**Int16**</span></span>|
|<span data-ttu-id="c93a2-141">**ushort**</span><span class="sxs-lookup"><span data-stu-id="c93a2-141">**ushort**</span></span>|<span data-ttu-id="c93a2-142">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="c93a2-142">**UInt16**</span></span>|<span data-ttu-id="c93a2-143">**unsigned short**</span><span class="sxs-lookup"><span data-stu-id="c93a2-143">**unsigned short**</span></span>|<span data-ttu-id="c93a2-144">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="c93a2-144">**UInt16**</span></span>|
|<span data-ttu-id="c93a2-145">**int**</span><span class="sxs-lookup"><span data-stu-id="c93a2-145">**int**</span></span>|<span data-ttu-id="c93a2-146">**Integer**</span><span class="sxs-lookup"><span data-stu-id="c93a2-146">**Integer**</span></span>|<span data-ttu-id="c93a2-147">**int**</span><span class="sxs-lookup"><span data-stu-id="c93a2-147">**int**</span></span>|<span data-ttu-id="c93a2-148">**Int32**</span><span class="sxs-lookup"><span data-stu-id="c93a2-148">**Int32**</span></span>|
|<span data-ttu-id="c93a2-149">**uint**</span><span class="sxs-lookup"><span data-stu-id="c93a2-149">**uint**</span></span>|<span data-ttu-id="c93a2-150">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="c93a2-150">**UInt32**</span></span>|<span data-ttu-id="c93a2-151">**unsigned int**</span><span class="sxs-lookup"><span data-stu-id="c93a2-151">**unsigned int**</span></span>|<span data-ttu-id="c93a2-152">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="c93a2-152">**UInt32**</span></span>|
|<span data-ttu-id="c93a2-153">**長い**</span><span class="sxs-lookup"><span data-stu-id="c93a2-153">**long**</span></span>|<span data-ttu-id="c93a2-154">**長い**</span><span class="sxs-lookup"><span data-stu-id="c93a2-154">**Long**</span></span>|<span data-ttu-id="c93a2-155">**__int64**</span><span class="sxs-lookup"><span data-stu-id="c93a2-155">**__int64**</span></span>|<span data-ttu-id="c93a2-156">**Int64**</span><span class="sxs-lookup"><span data-stu-id="c93a2-156">**Int64**</span></span>|
|<span data-ttu-id="c93a2-157">**ulong**</span><span class="sxs-lookup"><span data-stu-id="c93a2-157">**ulong**</span></span>|<span data-ttu-id="c93a2-158">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="c93a2-158">**UInt64**</span></span>|<span data-ttu-id="c93a2-159">**unsigned __int64**</span><span class="sxs-lookup"><span data-stu-id="c93a2-159">**unsigned __int64**</span></span>|<span data-ttu-id="c93a2-160">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="c93a2-160">**UInt64**</span></span>|
|<span data-ttu-id="c93a2-161">**float**</span><span class="sxs-lookup"><span data-stu-id="c93a2-161">**float**</span></span>|<span data-ttu-id="c93a2-162">**Single**</span><span class="sxs-lookup"><span data-stu-id="c93a2-162">**Single**</span></span>|<span data-ttu-id="c93a2-163">**float**</span><span class="sxs-lookup"><span data-stu-id="c93a2-163">**float**</span></span>|<span data-ttu-id="c93a2-164">**Single**</span><span class="sxs-lookup"><span data-stu-id="c93a2-164">**Single**</span></span>|
|<span data-ttu-id="c93a2-165">**double**</span><span class="sxs-lookup"><span data-stu-id="c93a2-165">**double**</span></span>|<span data-ttu-id="c93a2-166">**Double**</span><span class="sxs-lookup"><span data-stu-id="c93a2-166">**Double**</span></span>|<span data-ttu-id="c93a2-167">**double**</span><span class="sxs-lookup"><span data-stu-id="c93a2-167">**double**</span></span>|<span data-ttu-id="c93a2-168">**Double**</span><span class="sxs-lookup"><span data-stu-id="c93a2-168">**Double**</span></span>|
|<span data-ttu-id="c93a2-169">**bool**</span><span class="sxs-lookup"><span data-stu-id="c93a2-169">**bool**</span></span>|<span data-ttu-id="c93a2-170">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="c93a2-170">**Boolean**</span></span>|<span data-ttu-id="c93a2-171">**bool**</span><span class="sxs-lookup"><span data-stu-id="c93a2-171">**bool**</span></span>|<span data-ttu-id="c93a2-172">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="c93a2-172">**Boolean**</span></span>|
|<span data-ttu-id="c93a2-173">**char**</span><span class="sxs-lookup"><span data-stu-id="c93a2-173">**char**</span></span>|<span data-ttu-id="c93a2-174">**Char**</span><span class="sxs-lookup"><span data-stu-id="c93a2-174">**Char**</span></span>|<span data-ttu-id="c93a2-175">**wchar_t**</span><span class="sxs-lookup"><span data-stu-id="c93a2-175">**wchar_t**</span></span>|<span data-ttu-id="c93a2-176">**Char**</span><span class="sxs-lookup"><span data-stu-id="c93a2-176">**Char**</span></span>|
|<span data-ttu-id="c93a2-177">**string**</span><span class="sxs-lookup"><span data-stu-id="c93a2-177">**string**</span></span>|<span data-ttu-id="c93a2-178">**String**</span><span class="sxs-lookup"><span data-stu-id="c93a2-178">**String**</span></span>|<span data-ttu-id="c93a2-179">**String**</span><span class="sxs-lookup"><span data-stu-id="c93a2-179">**String**</span></span>|<span data-ttu-id="c93a2-180">**String**</span><span class="sxs-lookup"><span data-stu-id="c93a2-180">**String**</span></span>|
|<span data-ttu-id="c93a2-181">**オブジェクト**</span><span class="sxs-lookup"><span data-stu-id="c93a2-181">**object**</span></span>|<span data-ttu-id="c93a2-182">**Object**</span><span class="sxs-lookup"><span data-stu-id="c93a2-182">**Object**</span></span>|<span data-ttu-id="c93a2-183">**Object**</span><span class="sxs-lookup"><span data-stu-id="c93a2-183">**Object**</span></span>|<span data-ttu-id="c93a2-184">**Object**</span><span class="sxs-lookup"><span data-stu-id="c93a2-184">**Object**</span></span>|

 <span data-ttu-id="c93a2-185">識別子に意味を持たない場合やパラメータ`value`の`item`型が重要でない場合✔️、型名を繰り返すのではなく、 or などの共通名を使用します。</span><span class="sxs-lookup"><span data-stu-id="c93a2-185">✔️ DO  use a common name, such as `value` or `item`, rather than repeating the type name, in the rare cases when an identifier has no semantic meaning and the type of the parameter is not important.</span></span>

## <a name="naming-new-versions-of-existing-apis"></a><span data-ttu-id="c93a2-186">既存の API の新しいバージョンの命名</span><span class="sxs-lookup"><span data-stu-id="c93a2-186">Naming New Versions of Existing APIs</span></span>
 <span data-ttu-id="c93a2-187">既存の API の新しいバージョンを作成するときに、古い API と同様の名前を使用✔️。</span><span class="sxs-lookup"><span data-stu-id="c93a2-187">✔️ DO use a name similar to the old API when creating new versions of an existing API.</span></span>

 <span data-ttu-id="c93a2-188">これは、API 間の関係を強調するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c93a2-188">This helps to highlight the relationship between the APIs.</span></span>

 <span data-ttu-id="c93a2-189">既存の API の新しいバージョンを示すプレフィックスではなくサフィックスを追加✔️。</span><span class="sxs-lookup"><span data-stu-id="c93a2-189">✔️ DO prefer adding a suffix rather than a prefix to indicate a new version of an existing API.</span></span>

 <span data-ttu-id="c93a2-190">これは、ドキュメントを参照するとき、または IntelliSense を使用する場合の検出に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c93a2-190">This will assist discovery when browsing documentation, or using IntelliSense.</span></span> <span data-ttu-id="c93a2-191">ほとんどのブラウザーと IntelliSense はアルファベット順に識別子を表示するため、API の古いバージョンは新しい API の近くに整理されます。</span><span class="sxs-lookup"><span data-stu-id="c93a2-191">The old version of the API will be organized close to the new APIs, because most browsers and IntelliSense show identifiers in alphabetical order.</span></span>

 <span data-ttu-id="c93a2-192">✔️、サフィックスやプレフィックスを追加するのではなく、新しいが意味のある識別子を使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="c93a2-192">✔️ CONSIDER using a brand new, but meaningful identifier, instead of adding a suffix or a prefix.</span></span>

 <span data-ttu-id="c93a2-193">✔️は、既存の API の新しいバージョンを示すために数値サフィックスを使用しますが、特に API の既存の名前が意味のある唯一の名前である場合 (つまり、業界標準である場合)、意味のあるサフィックスを追加する (または名前を変更する) ことが適切なオプションではない場合。</span><span class="sxs-lookup"><span data-stu-id="c93a2-193">✔️ DO use a numeric suffix to indicate a new version of an existing API, particularly if the existing name of the API is the only name that makes sense (i.e., if it is an industry standard) and if adding any meaningful suffix (or changing the name) is not an appropriate option.</span></span>

 <span data-ttu-id="c93a2-194">❌同じ API の以前のバージョンと区別するために、識別子に "Ex" (または類似の) サフィックスを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="c93a2-194">❌ DO NOT use the "Ex" (or a similar) suffix for an identifier to distinguish it from an earlier version of the same API.</span></span>

 <span data-ttu-id="c93a2-195">✔️ DO は、32 ビット整数ではなく 64 ビット整数 (長整数) で動作する API のバージョンを導入する場合に、サフィックス 「64」を使用します。</span><span class="sxs-lookup"><span data-stu-id="c93a2-195">✔️ DO use the "64" suffix when introducing versions of APIs that operate on a 64-bit integer (a long integer) instead of a 32-bit integer.</span></span> <span data-ttu-id="c93a2-196">既存の 32 ビット API が存在する場合にのみ、このアプローチを使用する必要があります。64 ビットバージョンの新しい API に対しては、この操作を行わないでください。</span><span class="sxs-lookup"><span data-stu-id="c93a2-196">You only need to take this approach when the existing 32-bit API exists; don't do it for brand new APIs with only a 64-bit version.</span></span>

 <span data-ttu-id="c93a2-197">*2005年&copy;、2009年マイクロソフト株式会社。すべての権利が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="c93a2-197">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="c93a2-198">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="c93a2-198">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="c93a2-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="c93a2-199">See also</span></span>

- [<span data-ttu-id="c93a2-200">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="c93a2-200">Framework design guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="c93a2-201">命名のガイドライン</span><span class="sxs-lookup"><span data-stu-id="c93a2-201">Naming guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
- [<span data-ttu-id="c93a2-202">EditorConfig での .NET の名前付け規則</span><span class="sxs-lookup"><span data-stu-id="c93a2-202">.NET naming conventions for EditorConfig</span></span>](/visualstudio/ide/editorconfig-naming-conventions)
