---
title: C# 言語のバージョン管理 - C# ガイド
description: C# 言語のバージョンがプロジェクトに基づいて決定されるしくみとその選択の背後にある理由について説明します。 既定値を手動でオーバーライドする方法について説明します。
ms.date: 02/21/2020
ms.openlocfilehash: 2be76fdac471a7175b661d896b0da2910b3609f3
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626765"
---
# <a name="c-language-versioning"></a><span data-ttu-id="3dda5-104">C# 言語のバージョン管理</span><span class="sxs-lookup"><span data-stu-id="3dda5-104">C# language versioning</span></span>

<span data-ttu-id="3dda5-105">最新の C# コンパイラでは、プロジェクトのターゲット フレームワーク (1 つまたは複数) に基づいて既定の言語バージョンが決定されます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-105">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="3dda5-106">Visual Studio には値を変更するための UI がありませんが、それは *csproj* ファイルを編集することで変更できます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-106">Visual Studio doesn't provide a UI to change the value, but you can change it by editing the *csproj* file.</span></span> <span data-ttu-id="3dda5-107">既定値を選択すれば、ターゲット フレームワークと互換性がある最新の言語バージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-107">The choice of default ensures that you use the latest language version compatible with your target framework.</span></span> <span data-ttu-id="3dda5-108">プロジェクトのターゲットと互換性がある最新の言語機能にアクセスできるという利点があります。</span><span class="sxs-lookup"><span data-stu-id="3dda5-108">You benefit from access to the latest language features compatible with your project's target.</span></span> <span data-ttu-id="3dda5-109">また、このように既定値を選択すると、ターゲット フレームワークで利用できない型や実行時動作を必要とする言語が使用されません。</span><span class="sxs-lookup"><span data-stu-id="3dda5-109">This default choice also ensures you don't use a language that requires types or runtime behavior not available in your target framework.</span></span> <span data-ttu-id="3dda5-110">既定値より新しい言語バージョンを選択すると、コンパイル時間や実行時エラーの診断が困難になることがあります。</span><span class="sxs-lookup"><span data-stu-id="3dda5-110">Choosing a language version newer than the default can cause hard to diagnose compile-time and runtime errors.</span></span>

<span data-ttu-id="3dda5-111">C# 8.0 (以降) は .NET Core 3.x 以降のバージョンでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3dda5-111">C# 8.0 (and higher) is supported only on .NET Core 3.x and newer versions.</span></span> <span data-ttu-id="3dda5-112">最新機能の多くには、.NET Core 3.x で導入されたライブラリとランタイムの機能が必要になります。</span><span class="sxs-lookup"><span data-stu-id="3dda5-112">Many of the newest features require library and runtime features introduced in .NET Core 3.x:</span></span>

- <span data-ttu-id="3dda5-113">既定のインターフェイス メンバー実装には、.NET Core 3.0 CLR の新機能が必要になります。</span><span class="sxs-lookup"><span data-stu-id="3dda5-113">Default interface member implementation requires new features in the .NET Core 3.0 CLR.</span></span>
- <span data-ttu-id="3dda5-114">非同期ストリームには、<xref:System.IAsyncDisposable?displayProperty=nameWithType>、<xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType>、<xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType> という新しい型が必要になります。</span><span class="sxs-lookup"><span data-stu-id="3dda5-114">Async streams require the new types <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType>, and <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="3dda5-115">インデックスと範囲には、<xref:System.Index?displayProperty=nameWithType> と <xref:System.Range?displayProperty=nameWithType> という新しい型が必要です。</span><span class="sxs-lookup"><span data-stu-id="3dda5-115">Indexes and Ranges require the new types <xref:System.Index?displayProperty=nameWithType> and <xref:System.Range?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="3dda5-116">null 参照型では、効果的に警告を与える目的でいくつかの[属性](../nullable-attributes.md)が利用されます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-116">Nullable reference types make use of several [attributes](../nullable-attributes.md) to provide better warnings.</span></span> <span data-ttu-id="3dda5-117">その属性は .NET Core 3.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="3dda5-117">Those attributes were added in .NET Core 3.0.</span></span> <span data-ttu-id="3dda5-118">他のターゲット フレームには、そのような属性に関する注釈が付けられていません。</span><span class="sxs-lookup"><span data-stu-id="3dda5-118">Other target frameworks haven't been annotated with any of these attributes.</span></span> <span data-ttu-id="3dda5-119">つまり、null 許容警告は潜在的な問題を正確に反映していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3dda5-119">That means nullable warnings may not accurately reflect potential issues.</span></span>

## <a name="defaults"></a><span data-ttu-id="3dda5-120">[既定値]</span><span class="sxs-lookup"><span data-stu-id="3dda5-120">Defaults</span></span>

<span data-ttu-id="3dda5-121">コンパイラでは、以下の規則に基づいて既定値が決定されます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-121">The compiler determines a default based on these rules:</span></span>

|<span data-ttu-id="3dda5-122">ターゲット フレーム</span><span class="sxs-lookup"><span data-stu-id="3dda5-122">Target framework</span></span>|<span data-ttu-id="3dda5-123">version</span><span class="sxs-lookup"><span data-stu-id="3dda5-123">version</span></span>|<span data-ttu-id="3dda5-124">C# 言語の既定のバージョン</span><span class="sxs-lookup"><span data-stu-id="3dda5-124">C# language version default</span></span>|
|----------------|-------|---------------------------|
|<span data-ttu-id="3dda5-125">.NET Core</span><span class="sxs-lookup"><span data-stu-id="3dda5-125">.NET Core</span></span>|<span data-ttu-id="3dda5-126">3.x</span><span class="sxs-lookup"><span data-stu-id="3dda5-126">3.x</span></span>|<span data-ttu-id="3dda5-127">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="3dda5-127">C# 8.0</span></span>|
|<span data-ttu-id="3dda5-128">.NET Core</span><span class="sxs-lookup"><span data-stu-id="3dda5-128">.NET Core</span></span>|<span data-ttu-id="3dda5-129">2.x</span><span class="sxs-lookup"><span data-stu-id="3dda5-129">2.x</span></span>|<span data-ttu-id="3dda5-130">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="3dda5-130">C# 7.3</span></span>|
|<span data-ttu-id="3dda5-131">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="3dda5-131">.NET Standard</span></span>|<span data-ttu-id="3dda5-132">2.1</span><span class="sxs-lookup"><span data-stu-id="3dda5-132">2.1</span></span>|<span data-ttu-id="3dda5-133">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="3dda5-133">C# 8.0</span></span>|
|<span data-ttu-id="3dda5-134">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="3dda5-134">.NET Standard</span></span>|<span data-ttu-id="3dda5-135">2.0</span><span class="sxs-lookup"><span data-stu-id="3dda5-135">2.0</span></span>|<span data-ttu-id="3dda5-136">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="3dda5-136">C# 7.3</span></span>|
|<span data-ttu-id="3dda5-137">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="3dda5-137">.NET Standard</span></span>|<span data-ttu-id="3dda5-138">1.x</span><span class="sxs-lookup"><span data-stu-id="3dda5-138">1.x</span></span>|<span data-ttu-id="3dda5-139">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="3dda5-139">C# 7.3</span></span>|
|<span data-ttu-id="3dda5-140">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="3dda5-140">.NET Framework</span></span>|<span data-ttu-id="3dda5-141">all</span><span class="sxs-lookup"><span data-stu-id="3dda5-141">all</span></span>|<span data-ttu-id="3dda5-142">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="3dda5-142">C# 7.3</span></span>|

<span data-ttu-id="3dda5-143">ご自分のプロジェクトが、対応するプレビュー バージョンの言語を持つプレビュー フレームワークをターゲットにしている場合、使用される言語バージョンはプレビュー バージョンの言語です。</span><span class="sxs-lookup"><span data-stu-id="3dda5-143">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="3dda5-144">環境を問わず、そのプレビューでは最新の機能が使用されます。リリース済みの .NET Core バージョンをターゲットにするプロジェクトに影響はありません。</span><span class="sxs-lookup"><span data-stu-id="3dda5-144">You use the latest features with that preview in any environment, without affecting projects that target a released .NET Core version.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="3dda5-145">既定値のオーバーライド</span><span class="sxs-lookup"><span data-stu-id="3dda5-145">Override a default</span></span>

<span data-ttu-id="3dda5-146">C# のバージョンを明示的に指定する必要がある場合は、いくつかの方法で実行できます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-146">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="3dda5-147">[プロジェクト ファイル](#edit-the-project-file)を手動で編集する。</span><span class="sxs-lookup"><span data-stu-id="3dda5-147">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="3dda5-148">[サブディレクトリ内の複数のプロジェクトに対して](#configure-multiple-projects)言語バージョンを設定する。</span><span class="sxs-lookup"><span data-stu-id="3dda5-148">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="3dda5-149">[`-langversion` コンパイラ オプション](compiler-options/langversion-compiler-option.md)を構成する。</span><span class="sxs-lookup"><span data-stu-id="3dda5-149">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md).</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="3dda5-150">プロジェクト ファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="3dda5-150">Edit the project file</span></span>

<span data-ttu-id="3dda5-151">プロジェクト ファイルで言語のバージョンを設定できます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-151">You can set the language version in your project file.</span></span> <span data-ttu-id="3dda5-152">たとえば、プレビュー機能に明示的にアクセスしたい場合は、次のように要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="3dda5-152">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="3dda5-153">値 `preview` では、コンパイラでサポートされている使用可能な最新のプレビュー C# 言語バージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-153">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="3dda5-154">複数のプロジェクトを構成する</span><span class="sxs-lookup"><span data-stu-id="3dda5-154">Configure multiple projects</span></span>

<span data-ttu-id="3dda5-155">複数のプロジェクトを構成するには、`<LangVersion>` 要素を含む **Directory.build.props** ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3dda5-155">To configure multiple projects, you can create a **Directory.Build.props** file that contains the `<LangVersion>` element.</span></span> <span data-ttu-id="3dda5-156">この操作は通常、ソリューション ディレクトリで実行します。</span><span class="sxs-lookup"><span data-stu-id="3dda5-156">You typically do that in your solution directory.</span></span> <span data-ttu-id="3dda5-157">ソリューション ディレクトリ内の **Directory.Build.props** ファイルに以下を追加します。</span><span class="sxs-lookup"><span data-stu-id="3dda5-157">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="3dda5-158">そのファイルが含まれるディレクトリのすべてのサブディレクトリ内のビルドで、プレビュー C# バージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-158">Builds in all subdirectories of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="3dda5-159">詳しくは、「[ビルドのカスタマイズ](/visualstudio/msbuild/customize-your-build)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3dda5-159">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="3dda5-160">C# 言語バージョン リファレンス</span><span class="sxs-lookup"><span data-stu-id="3dda5-160">C# language version reference</span></span>

<span data-ttu-id="3dda5-161">次の表では、現在のすべての C# 言語バージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="3dda5-161">The following table shows all current C# language versions.</span></span> <span data-ttu-id="3dda5-162">コンパイラが古い場合、一部の値が正しく解釈されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3dda5-162">Your compiler may not necessarily understand every value if it's older.</span></span> <span data-ttu-id="3dda5-163">.NET Core 3.0 以降をインストールすれば、一覧にあるすべてにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-163">If you install .NET Core 3.0 or later, then you have access to everything listed.</span></span>

|<span data-ttu-id="3dda5-164">[値]</span><span class="sxs-lookup"><span data-stu-id="3dda5-164">Value</span></span>|<span data-ttu-id="3dda5-165">説明</span><span class="sxs-lookup"><span data-stu-id="3dda5-165">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="3dda5-166">preview</span><span class="sxs-lookup"><span data-stu-id="3dda5-166">preview</span></span>|<span data-ttu-id="3dda5-167">コンパイラは、最新のプレビュー バージョンの有効な言語構文をすべて受け入れます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-167">The compiler accepts all valid language syntax from the latest preview version.</span></span>|
|<span data-ttu-id="3dda5-168">latest</span><span class="sxs-lookup"><span data-stu-id="3dda5-168">latest</span></span>|<span data-ttu-id="3dda5-169">コンパイラは、最新リリース バージョンのコンパイラ (マイナー バージョンを含む) の構文を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-169">The compiler accepts syntax from the latest released version of the compiler (including minor version).</span></span>|
|<span data-ttu-id="3dda5-170">latestMajor</span><span class="sxs-lookup"><span data-stu-id="3dda5-170">latestMajor</span></span>|<span data-ttu-id="3dda5-171">コンパイラは、最新リリースのメジャー バージョンのコンパイラの構文を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-171">The compiler accepts syntax from the latest released major version of the compiler.</span></span>|
|<span data-ttu-id="3dda5-172">8.0</span><span class="sxs-lookup"><span data-stu-id="3dda5-172">8.0</span></span>|<span data-ttu-id="3dda5-173">コンパイラは、C# 8.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-173">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="3dda5-174">7.3</span><span class="sxs-lookup"><span data-stu-id="3dda5-174">7.3</span></span>|<span data-ttu-id="3dda5-175">コンパイラは、C# 7.3 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-175">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="3dda5-176">7.2</span><span class="sxs-lookup"><span data-stu-id="3dda5-176">7.2</span></span>|<span data-ttu-id="3dda5-177">コンパイラは、C# 7.2 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-177">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="3dda5-178">7.1</span><span class="sxs-lookup"><span data-stu-id="3dda5-178">7.1</span></span>|<span data-ttu-id="3dda5-179">コンパイラは、C# 7.1 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-179">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="3dda5-180">7</span><span class="sxs-lookup"><span data-stu-id="3dda5-180">7</span></span>|<span data-ttu-id="3dda5-181">コンパイラは、C# 7.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-181">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="3dda5-182">6</span><span class="sxs-lookup"><span data-stu-id="3dda5-182">6</span></span>|<span data-ttu-id="3dda5-183">コンパイラは、C# 6.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-183">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="3dda5-184">5</span><span class="sxs-lookup"><span data-stu-id="3dda5-184">5</span></span>|<span data-ttu-id="3dda5-185">コンパイラは、C# 5.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-185">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="3dda5-186">4</span><span class="sxs-lookup"><span data-stu-id="3dda5-186">4</span></span>|<span data-ttu-id="3dda5-187">コンパイラは、C# 4.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-187">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="3dda5-188">3</span><span class="sxs-lookup"><span data-stu-id="3dda5-188">3</span></span>|<span data-ttu-id="3dda5-189">コンパイラは、C# 3.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-189">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="3dda5-190">ISO-2</span><span class="sxs-lookup"><span data-stu-id="3dda5-190">ISO-2</span></span>|<span data-ttu-id="3dda5-191">コンパイラは、ISO/IEC 23270:2006 C# (2.0) に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-191">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0).</span></span> |
|<span data-ttu-id="3dda5-192">ISO-1</span><span class="sxs-lookup"><span data-stu-id="3dda5-192">ISO-1</span></span>|<span data-ttu-id="3dda5-193">コンパイラは、ISO/IEC 23270:2003 C# (1.0/1.2) に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="3dda5-193">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2).</span></span> |
