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
ms.openlocfilehash: d1b01fac7368ffeceb554c6f12aecb8f8760fa1d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709336"
---
# <a name="general-naming-conventions"></a><span data-ttu-id="a3b85-102">一般的な名前付け規則</span><span class="sxs-lookup"><span data-stu-id="a3b85-102">General Naming Conventions</span></span>
<span data-ttu-id="a3b85-103">ここでは、単語の選択に関連する一般的な名前付け規則、略語と頭字語の使用に関するガイドライン、および言語固有の名前の使用を回避するための推奨事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3b85-103">This section describes general naming conventions that relate to word choice, guidelines on using abbreviations and acronyms, and recommendations on how to avoid using language-specific names.</span></span>  
  
## <a name="word-choice"></a><span data-ttu-id="a3b85-104">単語の選択</span><span class="sxs-lookup"><span data-stu-id="a3b85-104">Word Choice</span></span>  
 <span data-ttu-id="a3b85-105">**✓ DO** 読みやすい識別子の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3b85-105">**✓ DO** choose easily readable identifier names.</span></span>  
  
 <span data-ttu-id="a3b85-106">たとえば、`HorizontalAlignment`よりも英語読みしやすい `AlignmentHorizontal`という名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3b85-106">For example, a property named `HorizontalAlignment` is more English-readable than `AlignmentHorizontal`.</span></span>  
  
 <span data-ttu-id="a3b85-107">**✓ DO** 簡潔さよりも読みやすさを優先します。</span><span class="sxs-lookup"><span data-stu-id="a3b85-107">**✓ DO** favor readability over brevity.</span></span>  
  
 <span data-ttu-id="a3b85-108">プロパティ名として（Ｘ軸というのがわかりにくい）`ScrollableX` よりも `CanScrollHorizontally` の方が良いです。</span><span class="sxs-lookup"><span data-stu-id="a3b85-108">The property name `CanScrollHorizontally` is better than `ScrollableX` (an obscure reference to the X-axis).</span></span>  
  
 <span data-ttu-id="a3b85-109">**× DO NOT** アンダー スコア、ハイフン、またはその他の英数字以外の文字は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="a3b85-109">**X DO NOT** use underscores, hyphens, or any other nonalphanumeric characters.</span></span>  
  
 <span data-ttu-id="a3b85-110">**× DO NOT** ハンガリアン記法を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="a3b85-110">**X DO NOT** use Hungarian notation.</span></span>  
  
 <span data-ttu-id="a3b85-111">**X AVOID** 広くのキーワードと競合する識別子を使用してプログラミング言語を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3b85-111">**X AVOID** using identifiers that conflict with keywords of widely used programming languages.</span></span>  
  
 <span data-ttu-id="a3b85-112">共通言語仕様（CLS）に準拠している言語は、ルール4に従って、その言語のキーワードを識別子名として使用する名前付けされた項目へのアクセスを許す機構を供給しなくてはなりません。</span><span class="sxs-lookup"><span data-stu-id="a3b85-112">According to Rule 4 of the Common Language Specification (CLS), all compliant languages must provide a mechanism that allows access to named items that use a keyword of that language as an identifier.</span></span> <span data-ttu-id="a3b85-113">たとえば C# の場合、@ 記号をエスケープ メカニズムとして使用します。</span><span class="sxs-lookup"><span data-stu-id="a3b85-113">C#, for example, uses the @ sign as an escape mechanism in this case.</span></span> <span data-ttu-id="a3b85-114">しかしながら、エスケープ シーケンスを使う方法は、それを使わない方法よりもずっと難しいので、共通のキーワードを避けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a3b85-114">However, it is still a good idea to avoid common keywords because it is much more difficult to use a method with the escape sequence than one without it.</span></span>  
  
## <a name="using-abbreviations-and-acronyms"></a><span data-ttu-id="a3b85-115">省略形と頭字語の使用</span><span class="sxs-lookup"><span data-stu-id="a3b85-115">Using Abbreviations and Acronyms</span></span>  
 <span data-ttu-id="a3b85-116">**× DO NOT** 識別子名の一部としての省略形または短縮形を使用ないでください。</span><span class="sxs-lookup"><span data-stu-id="a3b85-116">**X DO NOT** use abbreviations or contractions as part of identifier names.</span></span>  
  
 <span data-ttu-id="a3b85-117">たとえば、`GetWin` ではなく、`GetWindow` を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3b85-117">For example, use `GetWindow` rather than `GetWin`.</span></span>  
  
 <span data-ttu-id="a3b85-118">**X DO NOT** 広く受け入れられていない頭字語は使用しないでください。使用する場合は、必要な場合にのみにしてください。</span><span class="sxs-lookup"><span data-stu-id="a3b85-118">**X DO NOT** use any acronyms that are not widely accepted, and even if they are, only when necessary.</span></span>  
  
## <a name="avoiding-language-specific-names"></a><span data-ttu-id="a3b85-119">言語固有の名前の回避</span><span class="sxs-lookup"><span data-stu-id="a3b85-119">Avoiding Language-Specific Names</span></span>  
 <span data-ttu-id="a3b85-120">**✓ DO** 型名に言語固有のキーワードではなく、意味的にわかりやすい名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3b85-120">**✓ DO** use semantically interesting names rather than language-specific keywords for type names.</span></span>  
  
 <span data-ttu-id="a3b85-121">たとえば、`GetInt` よりも `GetLength`を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3b85-121">For example, `GetLength` is a better name than `GetInt`.</span></span>  
  
 <span data-ttu-id="a3b85-122">**✓ DO** 識別子名が、その型以外の意味がないまれな場合には、言語固有の名称ではなく、汎用の CLR 型名を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3b85-122">**✓ DO** use a generic CLR type name, rather than a language-specific name, in the rare cases when an identifier has no semantic meaning beyond its type.</span></span>  
  
 <span data-ttu-id="a3b85-123">たとえば、<xref:System.Int64>へ変換するメソッドは、`ToLong` ではなく `ToInt64` という名前を付けます (<xref:System.Int64> は、C# 固有の `long`の CLR 名です-特定のエイリアス`long`)。</span><span class="sxs-lookup"><span data-stu-id="a3b85-123">For example, a method converting to <xref:System.Int64> should be named `ToInt64`, not `ToLong` (because <xref:System.Int64> is a CLR name for the C#-specific alias `long`).</span></span> <span data-ttu-id="a3b85-124">次の表は、CLR 型名 (だけでなく C#、Visual Basic、および C++ の対応する型名) を使用していくつかの基本データ型を示します。</span><span class="sxs-lookup"><span data-stu-id="a3b85-124">The following table presents several base data types using the CLR type names (as well as the corresponding type names for C#, Visual Basic, and C++).</span></span>  
  
|<span data-ttu-id="a3b85-125">C#</span><span class="sxs-lookup"><span data-stu-id="a3b85-125">C#</span></span>|<span data-ttu-id="a3b85-126">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a3b85-126">Visual Basic</span></span>|<span data-ttu-id="a3b85-127">C++</span><span class="sxs-lookup"><span data-stu-id="a3b85-127">C++</span></span>|<span data-ttu-id="a3b85-128">CLR</span><span class="sxs-lookup"><span data-stu-id="a3b85-128">CLR</span></span>|  
|---------|------------------|-----------|---------|  
|<span data-ttu-id="a3b85-129">**sbyte**</span><span class="sxs-lookup"><span data-stu-id="a3b85-129">**sbyte**</span></span>|<span data-ttu-id="a3b85-130">**SByte**</span><span class="sxs-lookup"><span data-stu-id="a3b85-130">**SByte**</span></span>|<span data-ttu-id="a3b85-131">**char**</span><span class="sxs-lookup"><span data-stu-id="a3b85-131">**char**</span></span>|<span data-ttu-id="a3b85-132">**SByte**</span><span class="sxs-lookup"><span data-stu-id="a3b85-132">**SByte**</span></span>|  
|<span data-ttu-id="a3b85-133">**byte**</span><span class="sxs-lookup"><span data-stu-id="a3b85-133">**byte**</span></span>|<span data-ttu-id="a3b85-134">**Byte**</span><span class="sxs-lookup"><span data-stu-id="a3b85-134">**Byte**</span></span>|<span data-ttu-id="a3b85-135">**unsigned char**</span><span class="sxs-lookup"><span data-stu-id="a3b85-135">**unsigned char**</span></span>|<span data-ttu-id="a3b85-136">**Byte**</span><span class="sxs-lookup"><span data-stu-id="a3b85-136">**Byte**</span></span>|  
|<span data-ttu-id="a3b85-137">**short**</span><span class="sxs-lookup"><span data-stu-id="a3b85-137">**short**</span></span>|<span data-ttu-id="a3b85-138">**Short**</span><span class="sxs-lookup"><span data-stu-id="a3b85-138">**Short**</span></span>|<span data-ttu-id="a3b85-139">**short**</span><span class="sxs-lookup"><span data-stu-id="a3b85-139">**short**</span></span>|<span data-ttu-id="a3b85-140">**Int16**</span><span class="sxs-lookup"><span data-stu-id="a3b85-140">**Int16**</span></span>|  
|<span data-ttu-id="a3b85-141">**ushort**</span><span class="sxs-lookup"><span data-stu-id="a3b85-141">**ushort**</span></span>|<span data-ttu-id="a3b85-142">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="a3b85-142">**UInt16**</span></span>|<span data-ttu-id="a3b85-143">**unsigned short**</span><span class="sxs-lookup"><span data-stu-id="a3b85-143">**unsigned short**</span></span>|<span data-ttu-id="a3b85-144">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="a3b85-144">**UInt16**</span></span>|  
|<span data-ttu-id="a3b85-145">**int**</span><span class="sxs-lookup"><span data-stu-id="a3b85-145">**int**</span></span>|<span data-ttu-id="a3b85-146">**Integer**</span><span class="sxs-lookup"><span data-stu-id="a3b85-146">**Integer**</span></span>|<span data-ttu-id="a3b85-147">**int**</span><span class="sxs-lookup"><span data-stu-id="a3b85-147">**int**</span></span>|<span data-ttu-id="a3b85-148">**Int32**</span><span class="sxs-lookup"><span data-stu-id="a3b85-148">**Int32**</span></span>|  
|<span data-ttu-id="a3b85-149">**uint**</span><span class="sxs-lookup"><span data-stu-id="a3b85-149">**uint**</span></span>|<span data-ttu-id="a3b85-150">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="a3b85-150">**UInt32**</span></span>|<span data-ttu-id="a3b85-151">**unsigned int**</span><span class="sxs-lookup"><span data-stu-id="a3b85-151">**unsigned int**</span></span>|<span data-ttu-id="a3b85-152">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="a3b85-152">**UInt32**</span></span>|  
|<span data-ttu-id="a3b85-153">**long**</span><span class="sxs-lookup"><span data-stu-id="a3b85-153">**long**</span></span>|<span data-ttu-id="a3b85-154">**Long**</span><span class="sxs-lookup"><span data-stu-id="a3b85-154">**Long**</span></span>|<span data-ttu-id="a3b85-155">**__int64**</span><span class="sxs-lookup"><span data-stu-id="a3b85-155">**__int64**</span></span>|<span data-ttu-id="a3b85-156">**Int64**</span><span class="sxs-lookup"><span data-stu-id="a3b85-156">**Int64**</span></span>|  
|<span data-ttu-id="a3b85-157">**ulong**</span><span class="sxs-lookup"><span data-stu-id="a3b85-157">**ulong**</span></span>|<span data-ttu-id="a3b85-158">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="a3b85-158">**UInt64**</span></span>|<span data-ttu-id="a3b85-159">**unsigned __int64**</span><span class="sxs-lookup"><span data-stu-id="a3b85-159">**unsigned __int64**</span></span>|<span data-ttu-id="a3b85-160">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="a3b85-160">**UInt64**</span></span>|  
|<span data-ttu-id="a3b85-161">**float**</span><span class="sxs-lookup"><span data-stu-id="a3b85-161">**float**</span></span>|<span data-ttu-id="a3b85-162">**Single**</span><span class="sxs-lookup"><span data-stu-id="a3b85-162">**Single**</span></span>|<span data-ttu-id="a3b85-163">**float**</span><span class="sxs-lookup"><span data-stu-id="a3b85-163">**float**</span></span>|<span data-ttu-id="a3b85-164">**Single**</span><span class="sxs-lookup"><span data-stu-id="a3b85-164">**Single**</span></span>|  
|<span data-ttu-id="a3b85-165">**double**</span><span class="sxs-lookup"><span data-stu-id="a3b85-165">**double**</span></span>|<span data-ttu-id="a3b85-166">**Double**</span><span class="sxs-lookup"><span data-stu-id="a3b85-166">**Double**</span></span>|<span data-ttu-id="a3b85-167">**double**</span><span class="sxs-lookup"><span data-stu-id="a3b85-167">**double**</span></span>|<span data-ttu-id="a3b85-168">**Double**</span><span class="sxs-lookup"><span data-stu-id="a3b85-168">**Double**</span></span>|  
|<span data-ttu-id="a3b85-169">**bool**</span><span class="sxs-lookup"><span data-stu-id="a3b85-169">**bool**</span></span>|<span data-ttu-id="a3b85-170">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="a3b85-170">**Boolean**</span></span>|<span data-ttu-id="a3b85-171">**bool**</span><span class="sxs-lookup"><span data-stu-id="a3b85-171">**bool**</span></span>|<span data-ttu-id="a3b85-172">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="a3b85-172">**Boolean**</span></span>|  
|<span data-ttu-id="a3b85-173">**char**</span><span class="sxs-lookup"><span data-stu-id="a3b85-173">**char**</span></span>|<span data-ttu-id="a3b85-174">**Char**</span><span class="sxs-lookup"><span data-stu-id="a3b85-174">**Char**</span></span>|<span data-ttu-id="a3b85-175">**wchar_t**</span><span class="sxs-lookup"><span data-stu-id="a3b85-175">**wchar_t**</span></span>|<span data-ttu-id="a3b85-176">**Char**</span><span class="sxs-lookup"><span data-stu-id="a3b85-176">**Char**</span></span>|  
|<span data-ttu-id="a3b85-177">**string**</span><span class="sxs-lookup"><span data-stu-id="a3b85-177">**string**</span></span>|<span data-ttu-id="a3b85-178">**String**</span><span class="sxs-lookup"><span data-stu-id="a3b85-178">**String**</span></span>|<span data-ttu-id="a3b85-179">**String**</span><span class="sxs-lookup"><span data-stu-id="a3b85-179">**String**</span></span>|<span data-ttu-id="a3b85-180">**String**</span><span class="sxs-lookup"><span data-stu-id="a3b85-180">**String**</span></span>|  
|<span data-ttu-id="a3b85-181">**object**</span><span class="sxs-lookup"><span data-stu-id="a3b85-181">**object**</span></span>|<span data-ttu-id="a3b85-182">**オブジェクト**</span><span class="sxs-lookup"><span data-stu-id="a3b85-182">**Object**</span></span>|<span data-ttu-id="a3b85-183">**オブジェクト**</span><span class="sxs-lookup"><span data-stu-id="a3b85-183">**Object**</span></span>|<span data-ttu-id="a3b85-184">**オブジェクト**</span><span class="sxs-lookup"><span data-stu-id="a3b85-184">**Object**</span></span>|  
  
 <span data-ttu-id="a3b85-185">**✓ DO** など、共通名を使用して`value`または`item`、まれなケース識別子は特別な意味を持たないし、パラメーターの型が重要でないときに、型名を繰り返しではなくです。</span><span class="sxs-lookup"><span data-stu-id="a3b85-185">**✓ DO**  use a common name, such as `value` or `item`, rather than repeating the type name, in the rare cases when an identifier has no semantic meaning and the type of the parameter is not important.</span></span>  
  
## <a name="naming-new-versions-of-existing-apis"></a><span data-ttu-id="a3b85-186">既存の Api の新しいバージョンの命名</span><span class="sxs-lookup"><span data-stu-id="a3b85-186">Naming New Versions of Existing APIs</span></span>  
 <span data-ttu-id="a3b85-187">**✓ DO** 既存の API の新しいバージョンを作成するときに、古い API に類似している名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3b85-187">**✓ DO** use a name similar to the old API when creating new versions of an existing API.</span></span>  
  
 <span data-ttu-id="a3b85-188">これにより、API の間の関係性を強調します。</span><span class="sxs-lookup"><span data-stu-id="a3b85-188">This helps to highlight the relationship between the APIs.</span></span>  
  
 <span data-ttu-id="a3b85-189">**✓ DO** 既存の API の新しいバージョンを示すには、プレフィックスではなく、サフィックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="a3b85-189">**✓ DO** prefer adding a suffix rather than a prefix to indicate a new version of an existing API.</span></span>  
  
 <span data-ttu-id="a3b85-190">これは、ドキュメントを参照したり、IntelliSense を使用したりする際に発見しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="a3b85-190">This will assist discovery when browsing documentation, or using IntelliSense.</span></span> <span data-ttu-id="a3b85-191">ほとんどのブラウザーや IntelliSense は、アルファベット順に名前を並べるため、新しいバージョンの API は、古いバージョンの API の近くに編成されます。</span><span class="sxs-lookup"><span data-stu-id="a3b85-191">The old version of the API will be organized close to the new APIs, because most browsers and IntelliSense show identifiers in alphabetical order.</span></span>  
  
 <span data-ttu-id="a3b85-192">**✓ CONSIDER** サフィックスまたはプリフィックスを追加する代わりに、新しく意味のある識別子を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3b85-192">**✓ CONSIDER** using a brand new, but meaningful identifier, instead of adding a suffix or a prefix.</span></span>  
  
 <span data-ttu-id="a3b85-193">**✓ DO** もし、既存の API の名前が意味をなす唯一の名前であって（すなわち、それが規格や標準によるものであり）、意味のあるサフィックスを加えること（あるいは新しい名前を付けること）が適切ではないなら、既存の API の新しいバージョンであることを、数字のサフィックスを使って表します。</span><span class="sxs-lookup"><span data-stu-id="a3b85-193">**✓ DO** use a numeric suffix to indicate a new version of an existing API, particularly if the existing name of the API is the only name that makes sense (i.e., if it is an industry standard) and if adding any meaningful suffix (or changing the name) is not an appropriate option.</span></span>  
  
 <span data-ttu-id="a3b85-194">**X DO NOT** 同じ API の以前のバージョンと区別するために、"Ex"(または類似した) サフィックスを使用して識別子を作ります。</span><span class="sxs-lookup"><span data-stu-id="a3b85-194">**X DO NOT** use the "Ex" (or a similar) suffix for an identifier to distinguish it from an earlier version of the same API.</span></span>  
  
 <span data-ttu-id="a3b85-195">**✓ DO** 32 ビット整数の代わりに 64 ビット整数 (長整数) で動作する API のバージョンを導入するときに、**「64」サフィックス**を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3b85-195">**✓ DO** use the "64" suffix when introducing versions of APIs that operate on a 64-bit integer (a long integer) instead of a 32-bit integer.</span></span> <span data-ttu-id="a3b85-196">既存の 32 ビット API が存在する場合にのみ、この方法を実行する必要があります。64 ビット バージョンのみの新しい API には使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="a3b85-196">You only need to take this approach when the existing 32-bit API exists; don’t do it for brand new APIs with only a 64-bit version.</span></span>  
  
 <span data-ttu-id="a3b85-197">*©2005、2009 Microsoft Corporation の部分。すべての権限が予約されています。*</span><span class="sxs-lookup"><span data-stu-id="a3b85-197">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a3b85-198">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="a3b85-198">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3b85-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3b85-199">See also</span></span>

- [<span data-ttu-id="a3b85-200">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="a3b85-200">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="a3b85-201">名前付けのガイドライン</span><span class="sxs-lookup"><span data-stu-id="a3b85-201">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
