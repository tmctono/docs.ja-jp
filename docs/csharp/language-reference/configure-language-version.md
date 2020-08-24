---
title: C# 言語のバージョン管理 - C# ガイド
description: C# 言語のバージョンがプロジェクトに基づいて決定されるしくみとその選択の背後にある理由について説明します。 既定値を手動でオーバーライドする方法について説明します。
ms.custom: updateeachrelease
ms.date: 05/20/2020
ms.openlocfilehash: a27f3210f399f1bed190c18d778cf3824772d576
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656853"
---
# <a name="c-language-versioning"></a><span data-ttu-id="58e81-104">C# 言語のバージョン管理</span><span class="sxs-lookup"><span data-stu-id="58e81-104">C# language versioning</span></span>

<span data-ttu-id="58e81-105">最新の C# コンパイラでは、プロジェクトのターゲット フレームワーク (1 つまたは複数) に基づいて既定の言語バージョンが決定されます。</span><span class="sxs-lookup"><span data-stu-id="58e81-105">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="58e81-106">Visual Studio には値を変更するための UI がありませんが、それは *csproj* ファイルを編集することで変更できます。</span><span class="sxs-lookup"><span data-stu-id="58e81-106">Visual Studio doesn't provide a UI to change the value, but you can change it by editing the *csproj* file.</span></span> <span data-ttu-id="58e81-107">既定値を選択すれば、ターゲット フレームワークと互換性がある最新の言語バージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="58e81-107">The choice of default ensures that you use the latest language version compatible with your target framework.</span></span> <span data-ttu-id="58e81-108">プロジェクトのターゲットと互換性がある最新の言語機能にアクセスできるという利点があります。</span><span class="sxs-lookup"><span data-stu-id="58e81-108">You benefit from access to the latest language features compatible with your project's target.</span></span> <span data-ttu-id="58e81-109">また、このように既定値を選択すると、ターゲット フレームワークで利用できない型や実行時動作を必要とする言語が使用されません。</span><span class="sxs-lookup"><span data-stu-id="58e81-109">This default choice also ensures you don't use a language that requires types or runtime behavior not available in your target framework.</span></span> <span data-ttu-id="58e81-110">既定値より新しい言語バージョンを選択すると、コンパイル時間や実行時エラーの診断が困難になることがあります。</span><span class="sxs-lookup"><span data-stu-id="58e81-110">Choosing a language version newer than the default can cause hard to diagnose compile-time and runtime errors.</span></span>

<span data-ttu-id="58e81-111">この記事の規則は、Visual Studio 2019 または .NET Core 3.0 SDK に付属するコンパイラに適用されます。</span><span class="sxs-lookup"><span data-stu-id="58e81-111">The rules in this article apply to the compiler delivered with Visual Studio 2019 or the .NET Core 3.0 SDK.</span></span> <span data-ttu-id="58e81-112">Visual Studio 2017 インストールまたは以前の .NET Core SDK バージョンに含まれる C# コンパイラは、既定で C# 7.0 を対象とします。</span><span class="sxs-lookup"><span data-stu-id="58e81-112">The C# compilers that are part of the Visual Studio 2017 installation or earlier .NET Core SDK versions target C# 7.0 by default.</span></span>

<span data-ttu-id="58e81-113">C# 8.0 (以降) は .NET Core 3.x 以降のバージョンでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="58e81-113">C# 8.0 (and higher) is supported only on .NET Core 3.x and newer versions.</span></span> <span data-ttu-id="58e81-114">最新機能の多くには、.NET Core 3.x で導入されたライブラリとランタイムの機能が必要になります。</span><span class="sxs-lookup"><span data-stu-id="58e81-114">Many of the newest features require library and runtime features introduced in .NET Core 3.x:</span></span>

- <span data-ttu-id="58e81-115">[既定のインターフェイスの実装](../whats-new/csharp-8.md#default-interface-methods)では、.NET Core 3.0 CLR の新機能が必要です。</span><span class="sxs-lookup"><span data-stu-id="58e81-115">[Default interface implementation](../whats-new/csharp-8.md#default-interface-methods) requires new features in the .NET Core 3.0 CLR.</span></span>
- <span data-ttu-id="58e81-116">[非同期ストリーム](../whats-new/csharp-8.md#asynchronous-streams)には、新しい型 <xref:System.IAsyncDisposable?displayProperty=nameWithType>、<xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType>、<xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType> が必要です。</span><span class="sxs-lookup"><span data-stu-id="58e81-116">[Async streams](../whats-new/csharp-8.md#asynchronous-streams) require the new types <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType>, and <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="58e81-117">[インデックスと範囲](../whats-new/csharp-8.md#indices-and-ranges)には、新しい型 <xref:System.Index?displayProperty=nameWithType> と <xref:System.Range?displayProperty=nameWithType> が必要です。</span><span class="sxs-lookup"><span data-stu-id="58e81-117">[Indices and ranges](../whats-new/csharp-8.md#indices-and-ranges) require the new types <xref:System.Index?displayProperty=nameWithType> and <xref:System.Range?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="58e81-118">[null 許容参照型](../whats-new/csharp-8.md#nullable-reference-types)では、より適切な警告を提供するためにいくつかの[属性](attributes/nullable-analysis.md)が利用されます。</span><span class="sxs-lookup"><span data-stu-id="58e81-118">[Nullable reference types](../whats-new/csharp-8.md#nullable-reference-types) make use of several [attributes](attributes/nullable-analysis.md) to provide better warnings.</span></span> <span data-ttu-id="58e81-119">その属性は .NET Core 3.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="58e81-119">Those attributes were added in .NET Core 3.0.</span></span> <span data-ttu-id="58e81-120">他のターゲット フレームには、そのような属性に関する注釈が付けられていません。</span><span class="sxs-lookup"><span data-stu-id="58e81-120">Other target frameworks haven't been annotated with any of these attributes.</span></span> <span data-ttu-id="58e81-121">つまり、null 許容警告は潜在的な問題を正確に反映していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="58e81-121">That means nullable warnings may not accurately reflect potential issues.</span></span>

## <a name="defaults"></a><span data-ttu-id="58e81-122">[既定値]</span><span class="sxs-lookup"><span data-stu-id="58e81-122">Defaults</span></span>

<span data-ttu-id="58e81-123">コンパイラでは、以下の規則に基づいて既定値が決定されます。</span><span class="sxs-lookup"><span data-stu-id="58e81-123">The compiler determines a default based on these rules:</span></span>

| <span data-ttu-id="58e81-124">ターゲット フレーム</span><span class="sxs-lookup"><span data-stu-id="58e81-124">Target framework</span></span> | <span data-ttu-id="58e81-125">version</span><span class="sxs-lookup"><span data-stu-id="58e81-125">version</span></span> | <span data-ttu-id="58e81-126">C# 言語の既定のバージョン</span><span class="sxs-lookup"><span data-stu-id="58e81-126">C# language version default</span></span> |
|------------------|---------|-----------------------------|
| <span data-ttu-id="58e81-127">.NET Core</span><span class="sxs-lookup"><span data-stu-id="58e81-127">.NET Core</span></span>        | <span data-ttu-id="58e81-128">3.x</span><span class="sxs-lookup"><span data-stu-id="58e81-128">3.x</span></span>     | <span data-ttu-id="58e81-129">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="58e81-129">C# 8.0</span></span>                      |
| <span data-ttu-id="58e81-130">.NET Core</span><span class="sxs-lookup"><span data-stu-id="58e81-130">.NET Core</span></span>        | <span data-ttu-id="58e81-131">2.x</span><span class="sxs-lookup"><span data-stu-id="58e81-131">2.x</span></span>     | <span data-ttu-id="58e81-132">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="58e81-132">C# 7.3</span></span>                      |
| <span data-ttu-id="58e81-133">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="58e81-133">.NET Standard</span></span>    | <span data-ttu-id="58e81-134">2.1</span><span class="sxs-lookup"><span data-stu-id="58e81-134">2.1</span></span>     | <span data-ttu-id="58e81-135">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="58e81-135">C# 8.0</span></span>                      |
| <span data-ttu-id="58e81-136">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="58e81-136">.NET Standard</span></span>    | <span data-ttu-id="58e81-137">2.0</span><span class="sxs-lookup"><span data-stu-id="58e81-137">2.0</span></span>     | <span data-ttu-id="58e81-138">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="58e81-138">C# 7.3</span></span>                      |
| <span data-ttu-id="58e81-139">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="58e81-139">.NET Standard</span></span>    | <span data-ttu-id="58e81-140">1.x</span><span class="sxs-lookup"><span data-stu-id="58e81-140">1.x</span></span>     | <span data-ttu-id="58e81-141">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="58e81-141">C# 7.3</span></span>                      |
| <span data-ttu-id="58e81-142">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="58e81-142">.NET Framework</span></span>   | <span data-ttu-id="58e81-143">all</span><span class="sxs-lookup"><span data-stu-id="58e81-143">all</span></span>     | <span data-ttu-id="58e81-144">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="58e81-144">C# 7.3</span></span>                      |

<span data-ttu-id="58e81-145">ご自分のプロジェクトが、対応するプレビュー バージョンの言語を持つプレビュー フレームワークをターゲットにしている場合、使用される言語バージョンはプレビュー バージョンの言語です。</span><span class="sxs-lookup"><span data-stu-id="58e81-145">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="58e81-146">環境を問わず、そのプレビューでは最新の機能が使用されます。リリース済みの .NET Core バージョンをターゲットにするプロジェクトに影響はありません。</span><span class="sxs-lookup"><span data-stu-id="58e81-146">You use the latest features with that preview in any environment, without affecting projects that target a released .NET Core version.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="58e81-147">既定値のオーバーライド</span><span class="sxs-lookup"><span data-stu-id="58e81-147">Override a default</span></span>

<span data-ttu-id="58e81-148">C# のバージョンを明示的に指定する必要がある場合は、いくつかの方法で実行できます。</span><span class="sxs-lookup"><span data-stu-id="58e81-148">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="58e81-149">[プロジェクト ファイル](#edit-the-project-file)を手動で編集する。</span><span class="sxs-lookup"><span data-stu-id="58e81-149">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="58e81-150">[サブディレクトリ内の複数のプロジェクトに対して](#configure-multiple-projects)言語バージョンを設定する。</span><span class="sxs-lookup"><span data-stu-id="58e81-150">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="58e81-151">[`-langversion` コンパイラ オプション](compiler-options/langversion-compiler-option.md)を構成する。</span><span class="sxs-lookup"><span data-stu-id="58e81-151">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md).</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="58e81-152">プロジェクト ファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="58e81-152">Edit the project file</span></span>

<span data-ttu-id="58e81-153">プロジェクト ファイルで言語のバージョンを設定できます。</span><span class="sxs-lookup"><span data-stu-id="58e81-153">You can set the language version in your project file.</span></span> <span data-ttu-id="58e81-154">たとえば、プレビュー機能に明示的にアクセスしたい場合は、次のように要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="58e81-154">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="58e81-155">値 `preview` では、コンパイラでサポートされている使用可能な最新のプレビュー C# 言語バージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="58e81-155">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="58e81-156">複数のプロジェクトを構成する</span><span class="sxs-lookup"><span data-stu-id="58e81-156">Configure multiple projects</span></span>

<span data-ttu-id="58e81-157">複数のプロジェクトを構成するには、`<LangVersion>` 要素を含む **Directory.build.props** ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="58e81-157">To configure multiple projects, you can create a **Directory.Build.props** file that contains the `<LangVersion>` element.</span></span> <span data-ttu-id="58e81-158">この操作は通常、ソリューション ディレクトリで実行します。</span><span class="sxs-lookup"><span data-stu-id="58e81-158">You typically do that in your solution directory.</span></span> <span data-ttu-id="58e81-159">ソリューション ディレクトリ内の **Directory.Build.props** ファイルに以下を追加します。</span><span class="sxs-lookup"><span data-stu-id="58e81-159">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="58e81-160">そのファイルが含まれるディレクトリのすべてのサブディレクトリ内のビルドで、プレビュー C# バージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="58e81-160">Builds in all subdirectories of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="58e81-161">詳しくは、「[ビルドのカスタマイズ](/visualstudio/msbuild/customize-your-build)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58e81-161">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="58e81-162">C# 言語バージョン リファレンス</span><span class="sxs-lookup"><span data-stu-id="58e81-162">C# language version reference</span></span>

<span data-ttu-id="58e81-163">次の表では、現在のすべての C# 言語バージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="58e81-163">The following table shows all current C# language versions.</span></span> <span data-ttu-id="58e81-164">コンパイラが古い場合、一部の値が正しく解釈されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="58e81-164">Your compiler may not necessarily understand every value if it's older.</span></span> <span data-ttu-id="58e81-165">.NET Core 3.0 以降をインストールすれば、一覧にあるすべてにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="58e81-165">If you install .NET Core 3.0 or later, then you have access to everything listed.</span></span>

[!INCLUDE [langversion-table](includes/langversion-table.md)]

> [!TIP]
> <span data-ttu-id="58e81-166">お使いのコンピューターで使用可能な言語バージョンの一覧を表示するには、[Visual Studio の開発者コマンド プロンプト](../../framework/tools/developer-command-prompt-for-vs.md)を開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="58e81-166">Open the [Developer Command Prompt for Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), and run the following command to see the listing of language versions available on your machine.</span></span>
>
> ```CMD
> csc -langversion:?
> ```
>
> <span data-ttu-id="58e81-167">このように [-langversion](compiler-options/langversion-compiler-option.md) コンパイル オプションを指定すると、次のような内容が出力されます。</span><span class="sxs-lookup"><span data-stu-id="58e81-167">Questioning the [-langversion](compiler-options/langversion-compiler-option.md) compile option like this, will print something similar to the following:</span></span>
>
> ```CMD
> Supported language versions:
> default
> 1
> 2
> 3
> 4
> 5
> 6
> 7.0
> 7.1
> 7.2
> 7.3
> 8.0 (default)
> latestmajor
> preview
> latest
> ```
