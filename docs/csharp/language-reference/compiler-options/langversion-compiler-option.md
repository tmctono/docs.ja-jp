---
title: -langversion (C# コンパイラ オプション)
ms.date: 05/20/2020
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: 408b2fb1f19f872db675321601ebc1b0c921044b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802945"
---
# <a name="-langversion-c-compiler-options"></a><span data-ttu-id="49a9b-102">-langversion (C# コンパイラ オプション)</span><span class="sxs-lookup"><span data-stu-id="49a9b-102">-langversion (C# Compiler Options)</span></span>

<span data-ttu-id="49a9b-103">コンパイラが、選択した C# 言語仕様に含まれている構文のみを受け入れるようにします。</span><span class="sxs-lookup"><span data-stu-id="49a9b-103">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>

## <a name="syntax"></a><span data-ttu-id="49a9b-104">構文</span><span class="sxs-lookup"><span data-stu-id="49a9b-104">Syntax</span></span>

```console
-langversion:option
```

## <a name="arguments"></a><span data-ttu-id="49a9b-105">引数</span><span class="sxs-lookup"><span data-stu-id="49a9b-105">Arguments</span></span>

`option`

<span data-ttu-id="49a9b-106">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="49a9b-106">The following values are valid:</span></span>

[!INCLUDE [lang-versions-table](../includes/langversion-table.md)]

<span data-ttu-id="49a9b-107">既定の言語バージョンは、アプリケーションのターゲット フレームワークやインストールされている SDK または Visual Studio のバージョンに依存します。</span><span class="sxs-lookup"><span data-stu-id="49a9b-107">The default language version depends on the target framework for your application and the version of the SDK or Visual Studio installed.</span></span> <span data-ttu-id="49a9b-108">これらの規則は、[言語バージョンの構成](../configure-language-version.md#defaults)に関する記事の中で定義されています。</span><span class="sxs-lookup"><span data-stu-id="49a9b-108">Those rules are defined in the [configuring the language version](../configure-language-version.md#defaults) article.</span></span>

## <a name="remarks"></a><span data-ttu-id="49a9b-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="49a9b-109">Remarks</span></span>

<span data-ttu-id="49a9b-110">C# アプリケーションで参照されるメタデータは、 **-langversion** コンパイラ オプションの対象になりません。</span><span class="sxs-lookup"><span data-stu-id="49a9b-110">Metadata referenced by your C# application is not subject to **-langversion** compiler option.</span></span>

<span data-ttu-id="49a9b-111">C# コンパイラのバージョンごとに言語仕様の拡張機能が含まれているため、 **-langversion** は、コンパイラの以前のバージョンと同じ機能を提供しません。</span><span class="sxs-lookup"><span data-stu-id="49a9b-111">Because each version of the C# compiler contains extensions to the language specification, **-langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>

<span data-ttu-id="49a9b-112">さらに、C# バージョンの更新は、一般的に主要な .NET Framework のリリースと一致しますが、新しい構文および機能は必ずしも特定のフレームワーク バージョンに関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="49a9b-112">Additionally, while C# version updates generally coincide with major .NET Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="49a9b-113">新機能では、C# リビジョンと共にリリースされる新しいコンパイラの更新プログラムを確実に必要としますが、各特定機能には、独自の最小の .NET API または共通言語ランタイムの要件があり、この要件によって、NuGet パッケージやその他のライブラリを含めることで下位レベルのフレームワークで実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="49a9b-113">While the new features definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .NET API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>

<span data-ttu-id="49a9b-114">使用する **-langversion** の設定に関係なく、現在のバージョンの共通言語ランタイムを使用して .exe や .dll を作成します。</span><span class="sxs-lookup"><span data-stu-id="49a9b-114">Regardless of which **-langversion** setting you use, use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="49a9b-115">1 つの例外は、 **-langversion:ISO-1** の下で機能する、フレンド アセンブリと [-moduleassemblyname (C# コンパイラ オプション)](./moduleassemblyname-compiler-option.md) です。</span><span class="sxs-lookup"><span data-stu-id="49a9b-115">One exception is friend assemblies and [-moduleassemblyname (C# Compiler Option)](./moduleassemblyname-compiler-option.md), which work under **-langversion:ISO-1**.</span></span>

<span data-ttu-id="49a9b-116">C# 言語バージョンを指定するその他の方法については、[C# 言語のバージョンの選択](../configure-language-version.md)に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="49a9b-116">For other ways to specify the C# language version, see the [Select the C# language version](../configure-language-version.md) article.</span></span>

<span data-ttu-id="49a9b-117">このコンパイラ オプションをプログラムで設定する方法については、「<xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49a9b-117">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="49a9b-118">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="49a9b-118">C# language specification</span></span>

| <span data-ttu-id="49a9b-119">バージョン</span><span class="sxs-lookup"><span data-stu-id="49a9b-119">Version</span></span>          | <span data-ttu-id="49a9b-120">Link</span><span class="sxs-lookup"><span data-stu-id="49a9b-120">Link</span></span>                       | <span data-ttu-id="49a9b-121">説明</span><span class="sxs-lookup"><span data-stu-id="49a9b-121">Description</span></span>                                                             |
|------------------|----------------------------|-------------------------------------------------------------------------|
| <span data-ttu-id="49a9b-122">C# 7.0 以降</span><span class="sxs-lookup"><span data-stu-id="49a9b-122">C# 7.0 and later</span></span> |                            | <span data-ttu-id="49a9b-123">現在、利用できません</span><span class="sxs-lookup"><span data-stu-id="49a9b-123">Not currently available</span></span>                                                 |
| <span data-ttu-id="49a9b-124">C# 6.0</span><span class="sxs-lookup"><span data-stu-id="49a9b-124">C# 6.0</span></span>           | <span data-ttu-id="49a9b-125">[リンク][csharp-6]</span><span class="sxs-lookup"><span data-stu-id="49a9b-125">[Link][csharp-6]</span></span>           | <span data-ttu-id="49a9b-126">C# 言語仕様バージョン 6 - 非公式ドラフト: .NET Foundation</span><span class="sxs-lookup"><span data-stu-id="49a9b-126">C# Language Specification Version 6 - Unofficial Draft: .NET Foundation</span></span> |
| <span data-ttu-id="49a9b-127">C# 5.0</span><span class="sxs-lookup"><span data-stu-id="49a9b-127">C# 5.0</span></span>           | <span data-ttu-id="49a9b-128">[PDF のダウンロード][csharp-5]</span><span class="sxs-lookup"><span data-stu-id="49a9b-128">[Download PDF][csharp-5]</span></span>   | <span data-ttu-id="49a9b-129">Standard ECMA-334 5th Edition</span><span class="sxs-lookup"><span data-stu-id="49a9b-129">Standard ECMA-334 5th Edition</span></span>                                           |
| <span data-ttu-id="49a9b-130">C# 3.0</span><span class="sxs-lookup"><span data-stu-id="49a9b-130">C# 3.0</span></span>           | <span data-ttu-id="49a9b-131">[DOC のダウンロード][csharp-3]</span><span class="sxs-lookup"><span data-stu-id="49a9b-131">[Download DOC][csharp-3]</span></span>   | <span data-ttu-id="49a9b-132">C# 言語仕様バージョン 3.0:Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="49a9b-132">C# Language Specification Version 3.0: Microsoft Corporation</span></span>            |
| <span data-ttu-id="49a9b-133">C# 2.0</span><span class="sxs-lookup"><span data-stu-id="49a9b-133">C# 2.0</span></span>           | <span data-ttu-id="49a9b-134">[PDF のダウンロード][csharp-2]</span><span class="sxs-lookup"><span data-stu-id="49a9b-134">[Download PDF][csharp-2]</span></span>   | <span data-ttu-id="49a9b-135">Standard ECMA-334 4th Edition</span><span class="sxs-lookup"><span data-stu-id="49a9b-135">Standard ECMA-334 4th Edition</span></span>                                           |
| <span data-ttu-id="49a9b-136">C# 1.2</span><span class="sxs-lookup"><span data-stu-id="49a9b-136">C# 1.2</span></span>           | <span data-ttu-id="49a9b-137">[DOC のダウンロード][csharp-1.2]</span><span class="sxs-lookup"><span data-stu-id="49a9b-137">[Download DOC][csharp-1.2]</span></span> | <span data-ttu-id="49a9b-138">C# 言語仕様バージョン 1.2:Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="49a9b-138">C# Language Specification Version 1.2: Microsoft Corporation</span></span>            |
| <span data-ttu-id="49a9b-139">C# 1.0</span><span class="sxs-lookup"><span data-stu-id="49a9b-139">C# 1.0</span></span>           | <span data-ttu-id="49a9b-140">[DOC のダウンロード][csharp-1]</span><span class="sxs-lookup"><span data-stu-id="49a9b-140">[Download DOC][csharp-1]</span></span>   | <span data-ttu-id="49a9b-141">C# 言語仕様バージョン 1.0:Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="49a9b-141">C# Language Specification Version 1.0: Microsoft Corporation</span></span>            |

[csharp-6]: /dotnet/csharp/language-reference/language-specification/introduction
[csharp-5]: https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf
[csharp-3]: https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc
[csharp-2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%204th%20edition%20June%202006.pdf
[csharp-1.2]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%202nd%20edition%20December%202002.pdf
[csharp-1]: https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%201st%20edition%20December%202001.pdf

## <a name="minimum-sdk-version-needed-to-support-all-language-features"></a><span data-ttu-id="49a9b-142">すべての言語機能をサポートするために必要な SDK の最小バージョン</span><span class="sxs-lookup"><span data-stu-id="49a9b-142">Minimum SDK version needed to support all language features</span></span>

<span data-ttu-id="49a9b-143">次の表は、SDK の最小バージョンに対応する言語バージョンをサポートする C# コンパイラを示しています。</span><span class="sxs-lookup"><span data-stu-id="49a9b-143">The following table lists the minimum versions of the SDK with the C# compiler that supports the corresponding language version:</span></span>

| <span data-ttu-id="49a9b-144">C# バージョン</span><span class="sxs-lookup"><span data-stu-id="49a9b-144">C# version</span></span> | <span data-ttu-id="49a9b-145">SDK の最小バージョン</span><span class="sxs-lookup"><span data-stu-id="49a9b-145">Minimum SDK version</span></span>                                                                  |
|------------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="49a9b-146">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="49a9b-146">C# 8.0</span></span>     | <span data-ttu-id="49a9b-147">Microsoft Visual Studio/Build Tools 2019、バージョン 16.3 または .NET Core 3.0 SDK</span><span class="sxs-lookup"><span data-stu-id="49a9b-147">Microsoft Visual Studio/Build Tools 2019, version 16.3, or .NET Core 3.0 SDK</span></span>         |
| <span data-ttu-id="49a9b-148">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="49a9b-148">C# 7.3</span></span>     | <span data-ttu-id="49a9b-149">Microsoft Visual Studio/Build Tools 2017、バージョン 15.7</span><span class="sxs-lookup"><span data-stu-id="49a9b-149">Microsoft Visual Studio/Build Tools 2017, version 15.7</span></span>                               |
| <span data-ttu-id="49a9b-150">C# 7.2</span><span class="sxs-lookup"><span data-stu-id="49a9b-150">C# 7.2</span></span>     | <span data-ttu-id="49a9b-151">Microsoft Visual Studio/Build Tools 2017、バージョン 15.5</span><span class="sxs-lookup"><span data-stu-id="49a9b-151">Microsoft Visual Studio/Build Tools 2017, version 15.5</span></span>                               |
| <span data-ttu-id="49a9b-152">C# 7.1</span><span class="sxs-lookup"><span data-stu-id="49a9b-152">C# 7.1</span></span>     | <span data-ttu-id="49a9b-153">Microsoft Visual Studio/Build Tools 2017、バージョン 15.3</span><span class="sxs-lookup"><span data-stu-id="49a9b-153">Microsoft Visual Studio/Build Tools 2017, version 15.3</span></span>                               |
| <span data-ttu-id="49a9b-154">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="49a9b-154">C# 7.0</span></span>     | <span data-ttu-id="49a9b-155">Microsoft Visual Studio/Build Tools 2017</span><span class="sxs-lookup"><span data-stu-id="49a9b-155">Microsoft Visual Studio/Build Tools 2017</span></span>                                             |
| <span data-ttu-id="49a9b-156">C# 6</span><span class="sxs-lookup"><span data-stu-id="49a9b-156">C# 6</span></span>       | <span data-ttu-id="49a9b-157">Microsoft Visual Studio/Build Tools 2015</span><span class="sxs-lookup"><span data-stu-id="49a9b-157">Microsoft Visual Studio/Build Tools 2015</span></span>                                             |
| <span data-ttu-id="49a9b-158">C# 5</span><span class="sxs-lookup"><span data-stu-id="49a9b-158">C# 5</span></span>       | <span data-ttu-id="49a9b-159">Microsoft Visual Studio/Build Tools 2012、またはバンドルされている .Net Framework 4.5 コンパイラ</span><span class="sxs-lookup"><span data-stu-id="49a9b-159">Microsoft Visual Studio/Build Tools 2012 or bundled .NET Framework 4.5 compiler</span></span>      |
| <span data-ttu-id="49a9b-160">C# 4</span><span class="sxs-lookup"><span data-stu-id="49a9b-160">C# 4</span></span>       | <span data-ttu-id="49a9b-161">Microsoft Visual Studio/Build Tools 2010、またはバンドルされている .Net Framework 4.0 コンパイラ</span><span class="sxs-lookup"><span data-stu-id="49a9b-161">Microsoft Visual Studio/Build Tools 2010 or bundled .NET Framework 4.0 compiler</span></span>      |
| <span data-ttu-id="49a9b-162">C# 3</span><span class="sxs-lookup"><span data-stu-id="49a9b-162">C# 3</span></span>       | <span data-ttu-id="49a9b-163">Microsoft Visual Studio/Build Tools 2008、またはバンドルされている .Net Framework 3.5 コンパイラ</span><span class="sxs-lookup"><span data-stu-id="49a9b-163">Microsoft Visual Studio/Build Tools 2008 or bundled .NET Framework 3.5 compiler</span></span>      |
| <span data-ttu-id="49a9b-164">C# 2</span><span class="sxs-lookup"><span data-stu-id="49a9b-164">C# 2</span></span>       | <span data-ttu-id="49a9b-165">Microsoft Visual Studio/Build Tools 2005、またはバンドルされている .Net Framework 2.0 コンパイラ</span><span class="sxs-lookup"><span data-stu-id="49a9b-165">Microsoft Visual Studio/Build Tools 2005 or bundled .NET Framework 2.0 compiler</span></span>      |
| <span data-ttu-id="49a9b-166">C# 1.0/1.2</span><span class="sxs-lookup"><span data-stu-id="49a9b-166">C# 1.0/1.2</span></span> | <span data-ttu-id="49a9b-167">Microsoft Visual Studio/Build Tools .NET 2002 またはバンドルされている .NET Framework 1.0 コンパイラ</span><span class="sxs-lookup"><span data-stu-id="49a9b-167">Microsoft Visual Studio/Build Tools .NET 2002 or bundled .NET Framework 1.0 compiler</span></span> |

## <a name="see-also"></a><span data-ttu-id="49a9b-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="49a9b-168">See also</span></span>

- [<span data-ttu-id="49a9b-169">C# コンパイラ オプション</span><span class="sxs-lookup"><span data-stu-id="49a9b-169">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="49a9b-170">プロジェクトおよびソリューションのプロパティの管理</span><span class="sxs-lookup"><span data-stu-id="49a9b-170">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
