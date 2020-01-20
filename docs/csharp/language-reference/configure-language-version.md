---
title: C# 言語のバージョン管理 - C# ガイド
description: プロジェクトに基づいて C# 言語のバージョンが決定される方法、およびそれを手動で調整できるさまざまな値について説明します。
ms.date: 07/10/2019
ms.openlocfilehash: 90624816a68de694cacd0017c6d3162f6a89431c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713872"
---
# <a name="c-language-versioning"></a><span data-ttu-id="9bc69-103">C# 言語のバージョン管理</span><span class="sxs-lookup"><span data-stu-id="9bc69-103">C# language versioning</span></span>

<span data-ttu-id="9bc69-104">最新の C# コンパイラでは、プロジェクトのターゲット フレームワーク (1 つまたは複数) に基づいて既定の言語バージョンが決定されます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-104">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="9bc69-105">これは、C# 言語には、.NET のすべての実装では使用できない型またはランタイム コンポーネントに依存する機能が存在する場合があるためです。</span><span class="sxs-lookup"><span data-stu-id="9bc69-105">This is because the C# language may have features that rely on types or runtime components that are not available in every .NET implementation.</span></span> <span data-ttu-id="9bc69-106">また、これにより、プロジェクトのビルド ターゲットが何であっても、互換性が最も高い言語バージョンが既定で選択されることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-106">This also ensures that for whatever target your project is built against, you get the highest compatible language version by default.</span></span>

<span data-ttu-id="9bc69-107">この記事の規則は、Visual Studio 2019 または .NET Core 3.0 SDK に付属するコンパイラに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-107">The rules in this article apply to the compiler delivered with Visual Studio 2019, or the .NET Core 3.0 SDK.</span></span> <span data-ttu-id="9bc69-108">Visual Studio 2017 インストールまたは以前の .NET Core SDK バージョンに含まれる C# コンパイラは、既定で C# 7.0 を対象とします。</span><span class="sxs-lookup"><span data-stu-id="9bc69-108">The C# compilers that are part of the Visual Studio 2017 installation or earlier .NET Core SDK versions target C# 7.0 by default.</span></span> 

## <a name="defaults"></a><span data-ttu-id="9bc69-109">[既定値]</span><span class="sxs-lookup"><span data-stu-id="9bc69-109">Defaults</span></span>

<span data-ttu-id="9bc69-110">コンパイラでは、以下の規則に基づいて既定値が決定されます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-110">The compiler determines a default based on these rules:</span></span>

|<span data-ttu-id="9bc69-111">ターゲット フレーム</span><span class="sxs-lookup"><span data-stu-id="9bc69-111">Target framework</span></span>|<span data-ttu-id="9bc69-112">version</span><span class="sxs-lookup"><span data-stu-id="9bc69-112">version</span></span>|<span data-ttu-id="9bc69-113">C# 言語の既定のバージョン</span><span class="sxs-lookup"><span data-stu-id="9bc69-113">C# language version default</span></span>|
|----------------|-------|---------------------------|
|<span data-ttu-id="9bc69-114">.NET Core</span><span class="sxs-lookup"><span data-stu-id="9bc69-114">.NET Core</span></span>|<span data-ttu-id="9bc69-115">3.x</span><span class="sxs-lookup"><span data-stu-id="9bc69-115">3.x</span></span>|<span data-ttu-id="9bc69-116">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="9bc69-116">C# 8.0</span></span>|
|<span data-ttu-id="9bc69-117">.NET Core</span><span class="sxs-lookup"><span data-stu-id="9bc69-117">.NET Core</span></span>|<span data-ttu-id="9bc69-118">2.x</span><span class="sxs-lookup"><span data-stu-id="9bc69-118">2.x</span></span>|<span data-ttu-id="9bc69-119">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="9bc69-119">C# 7.3</span></span>|
|<span data-ttu-id="9bc69-120">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="9bc69-120">.NET Standard</span></span>|<span data-ttu-id="9bc69-121">2.1</span><span class="sxs-lookup"><span data-stu-id="9bc69-121">2.1</span></span>|<span data-ttu-id="9bc69-122">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="9bc69-122">C# 8.0</span></span>|
|<span data-ttu-id="9bc69-123">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="9bc69-123">.NET Standard</span></span>|<span data-ttu-id="9bc69-124">2.0</span><span class="sxs-lookup"><span data-stu-id="9bc69-124">2.0</span></span>|<span data-ttu-id="9bc69-125">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="9bc69-125">C# 7.3</span></span>|
|<span data-ttu-id="9bc69-126">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="9bc69-126">.NET Standard</span></span>|<span data-ttu-id="9bc69-127">1.x</span><span class="sxs-lookup"><span data-stu-id="9bc69-127">1.x</span></span>|<span data-ttu-id="9bc69-128">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="9bc69-128">C# 7.3</span></span>|
|<span data-ttu-id="9bc69-129">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="9bc69-129">.NET Framework</span></span>|<span data-ttu-id="9bc69-130">all</span><span class="sxs-lookup"><span data-stu-id="9bc69-130">all</span></span>|<span data-ttu-id="9bc69-131">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="9bc69-131">C# 7.3</span></span>|

## <a name="default-for-previews"></a><span data-ttu-id="9bc69-132">プレビューの既定値</span><span class="sxs-lookup"><span data-stu-id="9bc69-132">Default for previews</span></span>

<span data-ttu-id="9bc69-133">ご自分のプロジェクトが、対応するプレビュー バージョンの言語を持つプレビュー フレームワークをターゲットにしている場合、使用される言語バージョンはプレビュー バージョンの言語です。</span><span class="sxs-lookup"><span data-stu-id="9bc69-133">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="9bc69-134">これにより、リリースされた .NET Core バージョンをターゲットとするプロジェクトに影響を与えずに、任意の環境においてそのプレビューで動作することが保証されている最新の機能を確実に使用できます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-134">This ensures that you can use the latest features that are guaranteed to work with that preview in any environment without affecting your projects that target a released .NET Core version.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="9bc69-135">既定値のオーバーライド</span><span class="sxs-lookup"><span data-stu-id="9bc69-135">Override a default</span></span>

<span data-ttu-id="9bc69-136">C# のバージョンを明示的に指定する必要がある場合は、いくつかの方法で実行できます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-136">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="9bc69-137">[プロジェクト ファイル](#edit-the-project-file)を手動で編集する。</span><span class="sxs-lookup"><span data-stu-id="9bc69-137">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="9bc69-138">[サブディレクトリ内の複数のプロジェクトに対して](#configure-multiple-projects)言語バージョンを設定する。</span><span class="sxs-lookup"><span data-stu-id="9bc69-138">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="9bc69-139">[`-langversion` コンパイラ オプション](compiler-options/langversion-compiler-option.md)を構成する。</span><span class="sxs-lookup"><span data-stu-id="9bc69-139">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md).</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="9bc69-140">プロジェクト ファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="9bc69-140">Edit the project file</span></span>

<span data-ttu-id="9bc69-141">プロジェクト ファイルで言語のバージョンを設定できます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-141">You can set the language version in your project file.</span></span> <span data-ttu-id="9bc69-142">たとえば、プレビュー機能に明示的にアクセスしたい場合は、次のように要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="9bc69-142">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="9bc69-143">値 `preview` では、コンパイラでサポートされている使用可能な最新のプレビュー C# 言語バージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-143">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="9bc69-144">複数のプロジェクトを構成する</span><span class="sxs-lookup"><span data-stu-id="9bc69-144">Configure multiple projects</span></span>

<span data-ttu-id="9bc69-145">複数のディレクトリを構成する `<LangVersion>` 要素を含む **Directory.Build.props** ファイルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-145">You can create a **Directory.Build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="9bc69-146">この操作は通常、ソリューション ディレクトリで実行します。</span><span class="sxs-lookup"><span data-stu-id="9bc69-146">You typically do that in your solution directory.</span></span> <span data-ttu-id="9bc69-147">ソリューション ディレクトリ内の **Directory.Build.props** ファイルに以下を追加します。</span><span class="sxs-lookup"><span data-stu-id="9bc69-147">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="9bc69-148">これで、そのファイルが含まれるディレクトリのすべてのサブディレクトリ内のビルドで、プレビュー C# バージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-148">Now, builds in every subdirectory of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="9bc69-149">詳しくは、「[ビルドのカスタマイズ](/visualstudio/msbuild/customize-your-build)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bc69-149">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="9bc69-150">C# 言語バージョン リファレンス</span><span class="sxs-lookup"><span data-stu-id="9bc69-150">C# language version reference</span></span>

<span data-ttu-id="9bc69-151">次の表では、現在のすべての C# 言語バージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="9bc69-151">The following table shows all current C# language versions.</span></span> <span data-ttu-id="9bc69-152">コンパイラが古い場合、認識されない値が存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9bc69-152">Your compiler may not necessarily understand every value if it is older.</span></span> <span data-ttu-id="9bc69-153">.NET Core 3.0 をインストールすれば、一覧のすべての値にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-153">If you install .NET Core 3.0, then you will have access to everything listed.</span></span>

|<span data-ttu-id="9bc69-154">[値]</span><span class="sxs-lookup"><span data-stu-id="9bc69-154">Value</span></span>|<span data-ttu-id="9bc69-155">説明</span><span class="sxs-lookup"><span data-stu-id="9bc69-155">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="9bc69-156">preview</span><span class="sxs-lookup"><span data-stu-id="9bc69-156">preview</span></span>|<span data-ttu-id="9bc69-157">コンパイラは、最新のプレビュー バージョンの有効な言語構文をすべて受け入れます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-157">The compiler accepts all valid language syntax from the latest preview version.</span></span>|
|<span data-ttu-id="9bc69-158">latest</span><span class="sxs-lookup"><span data-stu-id="9bc69-158">latest</span></span>|<span data-ttu-id="9bc69-159">コンパイラは、最新リリース バージョンのコンパイラ (マイナー バージョンを含む) の構文を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-159">The compiler accepts syntax from the latest released version of the compiler (including minor version).</span></span>|
|<span data-ttu-id="9bc69-160">latestMajor</span><span class="sxs-lookup"><span data-stu-id="9bc69-160">latestMajor</span></span>|<span data-ttu-id="9bc69-161">コンパイラは、最新リリースのメジャー バージョンのコンパイラの構文を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-161">The compiler accepts syntax from the latest released major version of the compiler.</span></span>|
|<span data-ttu-id="9bc69-162">8.0</span><span class="sxs-lookup"><span data-stu-id="9bc69-162">8.0</span></span>|<span data-ttu-id="9bc69-163">コンパイラは、C# 8.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-163">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="9bc69-164">7.3</span><span class="sxs-lookup"><span data-stu-id="9bc69-164">7.3</span></span>|<span data-ttu-id="9bc69-165">コンパイラは、C# 7.3 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-165">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="9bc69-166">7.2</span><span class="sxs-lookup"><span data-stu-id="9bc69-166">7.2</span></span>|<span data-ttu-id="9bc69-167">コンパイラは、C# 7.2 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-167">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="9bc69-168">7.1</span><span class="sxs-lookup"><span data-stu-id="9bc69-168">7.1</span></span>|<span data-ttu-id="9bc69-169">コンパイラは、C# 7.1 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-169">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="9bc69-170">7</span><span class="sxs-lookup"><span data-stu-id="9bc69-170">7</span></span>|<span data-ttu-id="9bc69-171">コンパイラは、C# 7.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-171">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="9bc69-172">6</span><span class="sxs-lookup"><span data-stu-id="9bc69-172">6</span></span>|<span data-ttu-id="9bc69-173">コンパイラは、C# 6.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-173">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="9bc69-174">5</span><span class="sxs-lookup"><span data-stu-id="9bc69-174">5</span></span>|<span data-ttu-id="9bc69-175">コンパイラは、C# 5.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-175">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="9bc69-176">4</span><span class="sxs-lookup"><span data-stu-id="9bc69-176">4</span></span>|<span data-ttu-id="9bc69-177">コンパイラは、C# 4.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-177">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="9bc69-178">3</span><span class="sxs-lookup"><span data-stu-id="9bc69-178">3</span></span>|<span data-ttu-id="9bc69-179">コンパイラは、C# 3.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-179">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="9bc69-180">ISO-2</span><span class="sxs-lookup"><span data-stu-id="9bc69-180">ISO-2</span></span>|<span data-ttu-id="9bc69-181">コンパイラは、ISO/IEC 23270:2006 C# (2.0) に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-181">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0)</span></span> |
|<span data-ttu-id="9bc69-182">ISO-1</span><span class="sxs-lookup"><span data-stu-id="9bc69-182">ISO-1</span></span>|<span data-ttu-id="9bc69-183">コンパイラは、ISO/IEC 23270:2003 C# (1.0/1.2) に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="9bc69-183">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2)</span></span> |
