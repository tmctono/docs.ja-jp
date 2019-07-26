---
title: C# 言語のバージョン管理 - C# ガイド
description: プロジェクトに基づいて C# 言語のバージョンが決定される方法、およびそれを手動で調整できるさまざまな値について説明します。
ms.date: 07/10/2019
ms.openlocfilehash: e35fdf2bcdb1a31b752c760f3f6df59232e498a4
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68236097"
---
# <a name="c-language-versioning"></a><span data-ttu-id="8f736-103">C# 言語のバージョン管理</span><span class="sxs-lookup"><span data-stu-id="8f736-103">C# language versioning</span></span>

<span data-ttu-id="8f736-104">C# コンパイラでは、プロジェクトのターゲット フレームワーク (1 つまたは複数) に基づいて既定の言語バージョンが決定されます。</span><span class="sxs-lookup"><span data-stu-id="8f736-104">The C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="8f736-105">これは、C# 言語には、.NET のすべての実装では使用できない型またはランタイム コンポーネントに依存する機能が存在する場合があるためです。</span><span class="sxs-lookup"><span data-stu-id="8f736-105">This is because the C# language may have features that rely on types or runtime components that are not available in every .NET implementation.</span></span> <span data-ttu-id="8f736-106">また、これにより、プロジェクトのビルド ターゲットが何であっても、互換性が最も高い言語バージョンが既定で選択されることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="8f736-106">This also ensures that for whatever target your project is built against, you get the highest compatible language version by default.</span></span>

## <a name="defaults"></a><span data-ttu-id="8f736-107">[既定値]</span><span class="sxs-lookup"><span data-stu-id="8f736-107">Defaults</span></span>

<span data-ttu-id="8f736-108">コンパイラでは、以下の規則に基づいて既定値が決定されます。</span><span class="sxs-lookup"><span data-stu-id="8f736-108">The compiler determines a default based on these rules:</span></span>

|<span data-ttu-id="8f736-109">ターゲット フレーム</span><span class="sxs-lookup"><span data-stu-id="8f736-109">Target framework</span></span>|<span data-ttu-id="8f736-110">version</span><span class="sxs-lookup"><span data-stu-id="8f736-110">version</span></span>|<span data-ttu-id="8f736-111">C# 言語の既定のバージョン</span><span class="sxs-lookup"><span data-stu-id="8f736-111">C# language version default</span></span>|
|----------------|-------|---------------------------|
|<span data-ttu-id="8f736-112">.NET Core</span><span class="sxs-lookup"><span data-stu-id="8f736-112">.NET Core</span></span>|<span data-ttu-id="8f736-113">3.x</span><span class="sxs-lookup"><span data-stu-id="8f736-113">3.x</span></span>|<span data-ttu-id="8f736-114">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="8f736-114">C# 8.0</span></span>|
|<span data-ttu-id="8f736-115">.NET Core</span><span class="sxs-lookup"><span data-stu-id="8f736-115">.NET Core</span></span>|<span data-ttu-id="8f736-116">2.x</span><span class="sxs-lookup"><span data-stu-id="8f736-116">2.x</span></span>|<span data-ttu-id="8f736-117">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="8f736-117">C# 7.3</span></span>|
|<span data-ttu-id="8f736-118">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="8f736-118">.NET Standard</span></span>|<span data-ttu-id="8f736-119">all</span><span class="sxs-lookup"><span data-stu-id="8f736-119">all</span></span>|<span data-ttu-id="8f736-120">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="8f736-120">C# 7.3</span></span>|
|<span data-ttu-id="8f736-121">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="8f736-121">.NET Framework</span></span>|<span data-ttu-id="8f736-122">all</span><span class="sxs-lookup"><span data-stu-id="8f736-122">all</span></span>|<span data-ttu-id="8f736-123">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="8f736-123">C# 7.3</span></span>|

## <a name="default-for-previews"></a><span data-ttu-id="8f736-124">プレビューの既定値</span><span class="sxs-lookup"><span data-stu-id="8f736-124">Default for previews</span></span>

<span data-ttu-id="8f736-125">ご自分のプロジェクトが、対応するプレビュー バージョンの言語を持つプレビュー フレームワークをターゲットにしている場合、使用される言語バージョンはプレビュー バージョンの言語です。</span><span class="sxs-lookup"><span data-stu-id="8f736-125">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="8f736-126">これにより、リリースされた .NET Core バージョンをターゲットとするプロジェクトに影響を与えずに、任意の環境においてそのプレビューで動作することが保証されている最新の機能を確実に使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f736-126">This ensures that you can use the latest features that are guaranteed to work with that preview in any environment without affecting your projects that target a released .NET Core version.</span></span>

## <a name="overriding-a-default"></a><span data-ttu-id="8f736-127">既定値のオーバーライド</span><span class="sxs-lookup"><span data-stu-id="8f736-127">Overriding a default</span></span>

<span data-ttu-id="8f736-128">C# のバージョンを明示的に指定する必要がある場合は、いくつかの方法で実行できます。</span><span class="sxs-lookup"><span data-stu-id="8f736-128">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="8f736-129">[プロジェクト ファイル](#edit-the-project-file)を手動で編集する。</span><span class="sxs-lookup"><span data-stu-id="8f736-129">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="8f736-130">[サブディレクトリ内の複数のプロジェクトに対して](#configure-multiple-projects)言語バージョンを設定する。</span><span class="sxs-lookup"><span data-stu-id="8f736-130">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="8f736-131">[`-langversion` コンパイラ オプション](compiler-options/langversion-compiler-option.md)を構成する</span><span class="sxs-lookup"><span data-stu-id="8f736-131">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md)</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="8f736-132">プロジェクト ファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="8f736-132">Edit the project file</span></span>

<span data-ttu-id="8f736-133">プロジェクト ファイルで言語のバージョンを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8f736-133">You can set the language version in your project file.</span></span> <span data-ttu-id="8f736-134">たとえば、プレビュー機能に明示的にアクセスしたい場合は、次のように要素を追加できます。</span><span class="sxs-lookup"><span data-stu-id="8f736-134">For example, if you explicitly wanted access to preview features, you could do add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="8f736-135">値 `preview` では、コンパイラでサポートされている使用可能な最新のプレビュー C# 言語が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f736-135">The value `preview` uses the latest available preview C# language that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="8f736-136">複数のプロジェクトを構成する</span><span class="sxs-lookup"><span data-stu-id="8f736-136">Configure multiple projects</span></span>

<span data-ttu-id="8f736-137">複数のディレクトリを構成する `<LangVersion>` 要素を含む **Directory.Build.props** ファイルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="8f736-137">You can create a **Directory.Build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="8f736-138">この操作は通常、ソリューション ディレクトリで実行します。</span><span class="sxs-lookup"><span data-stu-id="8f736-138">You typically do that in your solution directory.</span></span> <span data-ttu-id="8f736-139">ソリューション ディレクトリ内の **Directory.Build.props** ファイルに以下を追加します。</span><span class="sxs-lookup"><span data-stu-id="8f736-139">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="8f736-140">これで、そのファイルが含まれるディレクトリのすべてのサブディレクトリ内のビルドで、プレビュー C# バージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f736-140">Now, builds in every subdirectory of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="8f736-141">詳しくは、「[ビルドのカスタマイズ](/visualstudio/msbuild/customize-your-build)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f736-141">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="8f736-142">C# 言語バージョン リファレンス</span><span class="sxs-lookup"><span data-stu-id="8f736-142">C# language version reference</span></span>

<span data-ttu-id="8f736-143">次の表では、現在のすべての C# 言語バージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="8f736-143">The following table shows all current C# language versions.</span></span> <span data-ttu-id="8f736-144">コンパイラが古い場合、認識されない値が存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8f736-144">Your compiler may not necessarily understand every value if it is older.</span></span> <span data-ttu-id="8f736-145">.NET Core 3.0 をインストールすれば、一覧のすべての値にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8f736-145">If you install .NET Core 3.0, then you will have access to everything listed.</span></span>

|<span data-ttu-id="8f736-146">[値]</span><span class="sxs-lookup"><span data-stu-id="8f736-146">Value</span></span>|<span data-ttu-id="8f736-147">説明</span><span class="sxs-lookup"><span data-stu-id="8f736-147">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="8f736-148">preview</span><span class="sxs-lookup"><span data-stu-id="8f736-148">preview</span></span>|<span data-ttu-id="8f736-149">コンパイラは、最新のプレビュー バージョンの有効な言語構文をすべて受け入れます。</span><span class="sxs-lookup"><span data-stu-id="8f736-149">The compiler accepts all valid language syntax from the latest preview version.</span></span>|
|<span data-ttu-id="8f736-150">latest</span><span class="sxs-lookup"><span data-stu-id="8f736-150">latest</span></span>|<span data-ttu-id="8f736-151">コンパイラは、最新リリース バージョンのコンパイラ (マイナー バージョンを含む) の構文を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="8f736-151">The compiler accepts syntax from the latest released version of the compiler (including minor version).</span></span>|
|<span data-ttu-id="8f736-152">latestMajor</span><span class="sxs-lookup"><span data-stu-id="8f736-152">latestMajor</span></span>|<span data-ttu-id="8f736-153">コンパイラは、最新リリースのメジャー バージョンのコンパイラの構文を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="8f736-153">The compiler accepts syntax from the latest released major version of the compiler.</span></span>|
|<span data-ttu-id="8f736-154">8.0</span><span class="sxs-lookup"><span data-stu-id="8f736-154">8.0</span></span>|<span data-ttu-id="8f736-155">コンパイラは、C# 8.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="8f736-155">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="8f736-156">7.3</span><span class="sxs-lookup"><span data-stu-id="8f736-156">7.3</span></span>|<span data-ttu-id="8f736-157">コンパイラは、C# 7.3 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="8f736-157">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="8f736-158">7.2</span><span class="sxs-lookup"><span data-stu-id="8f736-158">7.2</span></span>|<span data-ttu-id="8f736-159">コンパイラは、C# 7.2 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="8f736-159">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="8f736-160">7.1</span><span class="sxs-lookup"><span data-stu-id="8f736-160">7.1</span></span>|<span data-ttu-id="8f736-161">コンパイラは、C# 7.1 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="8f736-161">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="8f736-162">7</span><span class="sxs-lookup"><span data-stu-id="8f736-162">7</span></span>|<span data-ttu-id="8f736-163">コンパイラは、C# 7.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="8f736-163">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="8f736-164">6</span><span class="sxs-lookup"><span data-stu-id="8f736-164">6</span></span>|<span data-ttu-id="8f736-165">コンパイラは、C# 6.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="8f736-165">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="8f736-166">5</span><span class="sxs-lookup"><span data-stu-id="8f736-166">5</span></span>|<span data-ttu-id="8f736-167">コンパイラは、C# 5.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="8f736-167">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="8f736-168">4</span><span class="sxs-lookup"><span data-stu-id="8f736-168">4</span></span>|<span data-ttu-id="8f736-169">コンパイラは、C# 4.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="8f736-169">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="8f736-170">3</span><span class="sxs-lookup"><span data-stu-id="8f736-170">3</span></span>|<span data-ttu-id="8f736-171">コンパイラは、C# 3.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="8f736-171">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="8f736-172">ISO-2</span><span class="sxs-lookup"><span data-stu-id="8f736-172">ISO-2</span></span>|<span data-ttu-id="8f736-173">コンパイラは、ISO/IEC 23270:2006 C# (2.0) に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="8f736-173">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0)</span></span> |
|<span data-ttu-id="8f736-174">ISO-1</span><span class="sxs-lookup"><span data-stu-id="8f736-174">ISO-1</span></span>|<span data-ttu-id="8f736-175">コンパイラは、ISO/IEC 23270:2003 C# (1.0/1.2) に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="8f736-175">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2)</span></span> |
