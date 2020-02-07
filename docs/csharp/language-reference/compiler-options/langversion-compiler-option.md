---
title: -langversion (C# コンパイラ オプション)
ms.date: 08/23/2019
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: 007b10f6f27233c43caad4c1910e3d1158682950
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920367"
---
# <a name="-langversion-c-compiler-options"></a><span data-ttu-id="03878-102">-langversion (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="03878-102">-langversion (C# Compiler Options)</span></span>

<span data-ttu-id="03878-103">コンパイラが、選択した C# 言語仕様に含まれている構文のみを受け入れるようにします。</span><span class="sxs-lookup"><span data-stu-id="03878-103">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>

## <a name="syntax"></a><span data-ttu-id="03878-104">構文</span><span class="sxs-lookup"><span data-stu-id="03878-104">Syntax</span></span>

```console
-langversion:option
```

## <a name="arguments"></a><span data-ttu-id="03878-105">引数</span><span class="sxs-lookup"><span data-stu-id="03878-105">Arguments</span></span>

`option`

<span data-ttu-id="03878-106">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="03878-106">The following values are valid:</span></span>

|<span data-ttu-id="03878-107">オプション</span><span class="sxs-lookup"><span data-stu-id="03878-107">Option</span></span>|<span data-ttu-id="03878-108">説明</span><span class="sxs-lookup"><span data-stu-id="03878-108">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="03878-109">preview</span><span class="sxs-lookup"><span data-stu-id="03878-109">preview</span></span>|<span data-ttu-id="03878-110">コンパイラは、サポート可能な最新のプレビュー バージョンの有効な言語構文をすべて受け入れます。</span><span class="sxs-lookup"><span data-stu-id="03878-110">The compiler accepts all valid language syntax from the latest preview version that it can support.</span></span>|
|<span data-ttu-id="03878-111">latest</span><span class="sxs-lookup"><span data-stu-id="03878-111">latest</span></span>|<span data-ttu-id="03878-112">コンパイラは、サポート可能な最新バージョン (マイナー リリースを含む) の有効な言語構文をすべて受け入れます。</span><span class="sxs-lookup"><span data-stu-id="03878-112">The compiler accepts all valid language syntax from the latest version (including minor releases) that it can support.</span></span>|
|<span data-ttu-id="03878-113">latestMajor</span><span class="sxs-lookup"><span data-stu-id="03878-113">latestMajor</span></span>|<span data-ttu-id="03878-114">コンパイラは、最新のメジャー バージョンからサポートできるすべての有効な言語構文を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="03878-114">The compiler accepts all valid language syntax from the latest major version that it can support.</span></span>|
|<span data-ttu-id="03878-115">8.0</span><span class="sxs-lookup"><span data-stu-id="03878-115">8.0</span></span>|<span data-ttu-id="03878-116">コンパイラは、C# 8.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="03878-116">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="03878-117">7.3</span><span class="sxs-lookup"><span data-stu-id="03878-117">7.3</span></span>|<span data-ttu-id="03878-118">コンパイラは、C# 7.3 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="03878-118">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="03878-119">7.2</span><span class="sxs-lookup"><span data-stu-id="03878-119">7.2</span></span>|<span data-ttu-id="03878-120">コンパイラは、C# 7.2 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="03878-120">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="03878-121">7.1</span><span class="sxs-lookup"><span data-stu-id="03878-121">7.1</span></span>|<span data-ttu-id="03878-122">コンパイラは、C# 7.1 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="03878-122">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="03878-123">7</span><span class="sxs-lookup"><span data-stu-id="03878-123">7</span></span>|<span data-ttu-id="03878-124">コンパイラは、C# 7.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="03878-124">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="03878-125">6</span><span class="sxs-lookup"><span data-stu-id="03878-125">6</span></span>|<span data-ttu-id="03878-126">コンパイラは、C# 6.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="03878-126">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="03878-127">5</span><span class="sxs-lookup"><span data-stu-id="03878-127">5</span></span>|<span data-ttu-id="03878-128">コンパイラは、C# 5.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="03878-128">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="03878-129">4</span><span class="sxs-lookup"><span data-stu-id="03878-129">4</span></span>|<span data-ttu-id="03878-130">コンパイラは、C# 4.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="03878-130">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="03878-131">3</span><span class="sxs-lookup"><span data-stu-id="03878-131">3</span></span>|<span data-ttu-id="03878-132">コンパイラは、C# 3.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="03878-132">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="03878-133">ISO-2</span><span class="sxs-lookup"><span data-stu-id="03878-133">ISO-2</span></span>|<span data-ttu-id="03878-134">コンパイラは、ISO/IEC 23270:2006 C# (2.0) に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="03878-134">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0).</span></span>|
|<span data-ttu-id="03878-135">ISO-1</span><span class="sxs-lookup"><span data-stu-id="03878-135">ISO-1</span></span>|<span data-ttu-id="03878-136">コンパイラは、ISO/IEC 23270:2003 C# (1.0/1.2) に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="03878-136">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2).</span></span>|

<span data-ttu-id="03878-137">既定の言語バージョンは、アプリケーションのターゲット フレームワークやインストールされている SDK または Visual Studio のバージョンに依存します。</span><span class="sxs-lookup"><span data-stu-id="03878-137">The default language version depends on the target framework for your application and the version of the SDK or Visual Studio installed.</span></span> <span data-ttu-id="03878-138">これらの規則は、[言語バージョンの構成](../configure-language-version.md#defaults)に関する記事の中で定義されています。</span><span class="sxs-lookup"><span data-stu-id="03878-138">Those rules are defined in the [configuring the language version](../configure-language-version.md#defaults) article.</span></span>

## <a name="remarks"></a><span data-ttu-id="03878-139">Remarks</span><span class="sxs-lookup"><span data-stu-id="03878-139">Remarks</span></span>

<span data-ttu-id="03878-140">C# アプリケーションで参照されるメタデータは、 **-langversion** コンパイラ オプションの対象になりません。</span><span class="sxs-lookup"><span data-stu-id="03878-140">Metadata referenced by your C# application is not subject to **-langversion** compiler option.</span></span>

<span data-ttu-id="03878-141">C# コンパイラのバージョンごとに言語仕様の拡張機能が含まれているため、 **-langversion** は、コンパイラの以前のバージョンと同じ機能を提供しません。</span><span class="sxs-lookup"><span data-stu-id="03878-141">Because each version of the C# compiler contains extensions to the language specification, **-langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>

<span data-ttu-id="03878-142">さらに、C# バージョンの更新は、一般的に主要な .NET Framework のリリースと一致しますが、新しい構文および機能は必ずしも特定のフレームワーク バージョンに関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="03878-142">Additionally, while C# version updates generally coincide with major .NET Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="03878-143">新機能では、C# リビジョンと共にリリースされる新しいコンパイラの更新プログラムを確実に必要としますが、各特定機能には、独自の最小の .NET API または共通言語ランタイムの要件があり、この要件によって、NuGet パッケージやその他のライブラリを含めることで下位レベルのフレームワークで実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="03878-143">While the new features definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .NET API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>

<span data-ttu-id="03878-144">使用する **-langversion** の設定に関係なく、現在のバージョンの共通言語ランタイムを使用して .exe や .dll を作成します。</span><span class="sxs-lookup"><span data-stu-id="03878-144">Regardless of which **-langversion** setting you use, use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="03878-145">1 つの例外は、 **-langversion:ISO-1** の下で機能する、フレンド アセンブリと [-moduleassemblyname (C# コンパイラ オプション)](./moduleassemblyname-compiler-option.md) です。</span><span class="sxs-lookup"><span data-stu-id="03878-145">One exception is friend assemblies and [-moduleassemblyname (C# Compiler Option)](./moduleassemblyname-compiler-option.md), which work under **-langversion:ISO-1**.</span></span>

<span data-ttu-id="03878-146">C# 言語バージョンを指定するその他の方法については、[C# 言語のバージョンの選択](../configure-language-version.md)に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="03878-146">For other ways to specify the C# language version, see the [Select the C# language version](../configure-language-version.md) article.</span></span>

<span data-ttu-id="03878-147">このコンパイラ オプションをプログラムで設定する方法については、「<xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03878-147">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="03878-148">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="03878-148">C# language specification</span></span>

|<span data-ttu-id="03878-149">バージョン</span><span class="sxs-lookup"><span data-stu-id="03878-149">Version</span></span>|<span data-ttu-id="03878-150">Link</span><span class="sxs-lookup"><span data-stu-id="03878-150">Link</span></span>|<span data-ttu-id="03878-151">説明</span><span class="sxs-lookup"><span data-stu-id="03878-151">Description</span></span>|
|-------|----|-----------|
|<span data-ttu-id="03878-152">C# 7.0 以降</span><span class="sxs-lookup"><span data-stu-id="03878-152">C# 7.0 and later</span></span>||<span data-ttu-id="03878-153">現在使用できません</span><span class="sxs-lookup"><span data-stu-id="03878-153">not currently available</span></span>|
|<span data-ttu-id="03878-154">C# 6.0</span><span class="sxs-lookup"><span data-stu-id="03878-154">C# 6.0</span></span>|[<span data-ttu-id="03878-155">リンク</span><span class="sxs-lookup"><span data-stu-id="03878-155">Link</span></span>](/dotnet/csharp/language-reference/language-specification/introduction)|<span data-ttu-id="03878-156">C# 言語仕様バージョン 6 - 非公式ドラフト: .NET Foundation</span><span class="sxs-lookup"><span data-stu-id="03878-156">C# Language Specification Version 6 - Unofficial Draft: .NET Foundation</span></span>|
|<span data-ttu-id="03878-157">C# 5.0</span><span class="sxs-lookup"><span data-stu-id="03878-157">C# 5.0</span></span>|[<span data-ttu-id="03878-158">PDF のダウンロード</span><span class="sxs-lookup"><span data-stu-id="03878-158">Download PDF</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf)|<span data-ttu-id="03878-159">Standard ECMA-334 5th Edition</span><span class="sxs-lookup"><span data-stu-id="03878-159">Standard ECMA-334 5th Edition</span></span>|
|<span data-ttu-id="03878-160">C# 3.0</span><span class="sxs-lookup"><span data-stu-id="03878-160">C# 3.0</span></span>|[<span data-ttu-id="03878-161">DOC のダウンロード</span><span class="sxs-lookup"><span data-stu-id="03878-161">Download DOC</span></span>](https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc)|<span data-ttu-id="03878-162">C# 言語仕様バージョン 3.0:Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="03878-162">C# Language Specification Version 3.0: Microsoft Corporation</span></span>|
|<span data-ttu-id="03878-163">C# 2.0</span><span class="sxs-lookup"><span data-stu-id="03878-163">C# 2.0</span></span>|[<span data-ttu-id="03878-164">PDF のダウンロード</span><span class="sxs-lookup"><span data-stu-id="03878-164">Download PDF</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%204th%20edition%20June%202006.pdf)|<span data-ttu-id="03878-165">Standard ECMA-334 4th Edition</span><span class="sxs-lookup"><span data-stu-id="03878-165">Standard ECMA-334 4th Edition</span></span>|
|<span data-ttu-id="03878-166">C# 1.2</span><span class="sxs-lookup"><span data-stu-id="03878-166">C# 1.2</span></span>|[<span data-ttu-id="03878-167">DOC のダウンロード</span><span class="sxs-lookup"><span data-stu-id="03878-167">Download DOC</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%202nd%20edition%20December%202002.pdf)|<span data-ttu-id="03878-168">C# 言語仕様バージョン 1.2:Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="03878-168">C# Language Specification Version 1.2: Microsoft Corporation</span></span>|
|<span data-ttu-id="03878-169">C# 1.0</span><span class="sxs-lookup"><span data-stu-id="03878-169">C# 1.0</span></span>|[<span data-ttu-id="03878-170">DOC のダウンロード</span><span class="sxs-lookup"><span data-stu-id="03878-170">Download DOC</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%201st%20edition%20December%202001.pdf)|<span data-ttu-id="03878-171">C# 言語仕様バージョン 1.0:Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="03878-171">C# Language Specification Version 1.0: Microsoft Corporation</span></span>|

## <a name="minimum-sdk-version-needed-to-support-all-language-features"></a><span data-ttu-id="03878-172">すべての言語機能をサポートするために必要な SDK の最小バージョン</span><span class="sxs-lookup"><span data-stu-id="03878-172">Minimum SDK version needed to support all language features</span></span>

<span data-ttu-id="03878-173">次の表は、SDK の最小バージョンに対応する言語バージョンをサポートする C# コンパイラを示しています。</span><span class="sxs-lookup"><span data-stu-id="03878-173">The following table lists the minimum versions of the SDK with the C# compiler that supports the corresponding language version:</span></span>

|<span data-ttu-id="03878-174">C# バージョン</span><span class="sxs-lookup"><span data-stu-id="03878-174">C# version</span></span>|<span data-ttu-id="03878-175">SDK の最小バージョン</span><span class="sxs-lookup"><span data-stu-id="03878-175">Minimum SDK version</span></span>|
|----------|-------------------|
|<span data-ttu-id="03878-176">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="03878-176">C# 8.0</span></span>| <span data-ttu-id="03878-177">Microsoft Visual Studio/Build Tools 2019、バージョン 16.3 または .NET Core 3.0 SDK</span><span class="sxs-lookup"><span data-stu-id="03878-177">Microsoft Visual Studio/Build Tools 2019, version 16.3, or .NET Core 3.0 SDK</span></span> |
|<span data-ttu-id="03878-178">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="03878-178">C# 7.3</span></span>| <span data-ttu-id="03878-179">Microsoft Visual Studio/Build Tools 2017、バージョン 15.7</span><span class="sxs-lookup"><span data-stu-id="03878-179">Microsoft Visual Studio/Build Tools 2017, version 15.7</span></span> |
|<span data-ttu-id="03878-180">C# 7.2</span><span class="sxs-lookup"><span data-stu-id="03878-180">C# 7.2</span></span>| <span data-ttu-id="03878-181">Microsoft Visual Studio/Build Tools 2017、バージョン 15.5</span><span class="sxs-lookup"><span data-stu-id="03878-181">Microsoft Visual Studio/Build Tools 2017, version 15.5</span></span> |
|<span data-ttu-id="03878-182">C# 7.1</span><span class="sxs-lookup"><span data-stu-id="03878-182">C# 7.1</span></span>| <span data-ttu-id="03878-183">Microsoft Visual Studio/Build Tools 2017、バージョン 15.3</span><span class="sxs-lookup"><span data-stu-id="03878-183">Microsoft Visual Studio/Build Tools 2017, version 15.3</span></span> |
|<span data-ttu-id="03878-184">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="03878-184">C# 7.0</span></span>| <span data-ttu-id="03878-185">Microsoft Visual Studio/Build Tools 2017</span><span class="sxs-lookup"><span data-stu-id="03878-185">Microsoft Visual Studio/Build Tools 2017</span></span> |
|<span data-ttu-id="03878-186">C# 6</span><span class="sxs-lookup"><span data-stu-id="03878-186">C# 6</span></span>| <span data-ttu-id="03878-187">Microsoft Visual Studio/Build Tools 2015</span><span class="sxs-lookup"><span data-stu-id="03878-187">Microsoft Visual Studio/Build Tools 2015</span></span> |
|<span data-ttu-id="03878-188">C# 5</span><span class="sxs-lookup"><span data-stu-id="03878-188">C# 5</span></span>| <span data-ttu-id="03878-189">Microsoft Visual Studio/Build Tools 2012、またはバンドルされている .Net Framework 4.5 コンパイラ</span><span class="sxs-lookup"><span data-stu-id="03878-189">Microsoft Visual Studio/Build Tools 2012 or bundled .NET Framework 4.5 compiler</span></span> |
|<span data-ttu-id="03878-190">C# 4</span><span class="sxs-lookup"><span data-stu-id="03878-190">C# 4</span></span>| <span data-ttu-id="03878-191">Microsoft Visual Studio/Build Tools 2010、またはバンドルされている .Net Framework 4.0 コンパイラ</span><span class="sxs-lookup"><span data-stu-id="03878-191">Microsoft Visual Studio/Build Tools 2010 or bundled .NET Framework 4.0 compiler</span></span> |
|<span data-ttu-id="03878-192">C# 3</span><span class="sxs-lookup"><span data-stu-id="03878-192">C# 3</span></span>| <span data-ttu-id="03878-193">Microsoft Visual Studio/Build Tools 2008、またはバンドルされている .Net Framework 3.5 コンパイラ</span><span class="sxs-lookup"><span data-stu-id="03878-193">Microsoft Visual Studio/Build Tools 2008 or bundled .NET Framework 3.5 compiler</span></span> |
|<span data-ttu-id="03878-194">C# 2</span><span class="sxs-lookup"><span data-stu-id="03878-194">C# 2</span></span>| <span data-ttu-id="03878-195">Microsoft Visual Studio/Build Tools 2005、またはバンドルされている .Net Framework 2.0 コンパイラ</span><span class="sxs-lookup"><span data-stu-id="03878-195">Microsoft Visual Studio/Build Tools 2005 or bundled .NET Framework 2.0 compiler</span></span> |
|<span data-ttu-id="03878-196">C# 1.0/1.2</span><span class="sxs-lookup"><span data-stu-id="03878-196">C# 1.0/1.2</span></span> | <span data-ttu-id="03878-197">Microsoft Visual Studio/Build Tools .NET 2002 またはバンドルされている .NET Framework 1.0 コンパイラ</span><span class="sxs-lookup"><span data-stu-id="03878-197">Microsoft Visual Studio/Build Tools .NET 2002 or bundled .NET Framework 1.0 compiler</span></span> |

## <a name="see-also"></a><span data-ttu-id="03878-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="03878-198">See also</span></span>

- [<span data-ttu-id="03878-199">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="03878-199">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="03878-200">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="03878-200">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
