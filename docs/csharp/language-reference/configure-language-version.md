---
title: C# 言語のバージョンの選択 - C# ガイド
description: 特定のコンパイラ バージョンを使用して構文の検証を実行するコンパイラを構成します。
ms.date: 02/28/2019
ms.openlocfilehash: feb3e51a107f9830071b55c7985f202edc842f4a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770881"
---
# <a name="select-the-c-language-version"></a><span data-ttu-id="05749-103">C# 言語のバージョンの選択</span><span class="sxs-lookup"><span data-stu-id="05749-103">Select the C# language version</span></span>

<span data-ttu-id="05749-104">C# コンパイラでは、プロジェクトのターゲット フレームワーク (1 つまたは複数) に基づいて既定の言語バージョンが決定されます。</span><span class="sxs-lookup"><span data-stu-id="05749-104">The C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="05749-105">ご自分のプロジェクトが、対応するプレビュー バージョンの言語を持つプレビュー フレームワークをターゲットにしている場合、使用される言語バージョンはプレビュー バージョンの言語です。</span><span class="sxs-lookup"><span data-stu-id="05749-105">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="05749-106">ご自分のプロジェクトがプレビュー フレームワークをターゲットにしていない場合、使用される言語バージョンは最新のマイナー バージョンです。</span><span class="sxs-lookup"><span data-stu-id="05749-106">When your project doesn't target a preview framework, the language version used is the latest minor version.</span></span>

<span data-ttu-id="05749-107">たとえば、.NET Core 3.0 のプレビュー期間中は、`netcoreapp3.0` または `netstandard2.1` (両方ともプレビュー段階) をターゲットにするすべてのプロジェクトで C# 8.0 言語 (これもプレビュー段階) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="05749-107">For example, during the preview period for .NET Core 3.0, any project that targets `netcoreapp3.0` or `netstandard2.1` (both in preview) will use the C# 8.0 language (also in preview).</span></span> <span data-ttu-id="05749-108">リリース バージョンをターゲットにするプロジェクトでは、C# 7.3 (最新リリース バージョン) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="05749-108">Projects targeting any released version will use C# 7.3 (the latest released version).</span></span> <span data-ttu-id="05749-109">この動作は、.NET Framework をターゲットにするすべてのプロジェクトで最新 (C# 7.3) が使用されることを意味しています。</span><span class="sxs-lookup"><span data-stu-id="05749-109">This behavior means that any project targeting .NET Framework will use latest (C# 7.3).</span></span> 

<span data-ttu-id="05749-110">この機能によって、開発環境に新しいバージョンの SDK とツールをインストールすることの決定と新しい言語機能をプロジェクトに組み込むことの決定が別になります。</span><span class="sxs-lookup"><span data-stu-id="05749-110">This capability decouples the decision to install new versions of the SDK and tools in your development environment from the decision to incorporate new language features in a project.</span></span> <span data-ttu-id="05749-111">ビルド コンピューターに最新の SDK とツールをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="05749-111">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="05749-112">特定バージョンの言語をビルドに使用するように各プロジェクトを構成できます。</span><span class="sxs-lookup"><span data-stu-id="05749-112">Each project can be configured to use a specific version of the language for its build.</span></span> <span data-ttu-id="05749-113">既定の動作は、新しい型や CLR の新しい動作に依存する言語機能が、プロジェクトでそれらのフレームワークをターゲットにしている場合にのみ有効になることを意味しています。</span><span class="sxs-lookup"><span data-stu-id="05749-113">The default behavior means that any language features that rely on new types or new CLR behavior are enabled only when projects target those frameworks.</span></span>

<span data-ttu-id="05749-114">言語バージョンを指定することで、既定の動作をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="05749-114">You can override the default behavior by specifying a language version.</span></span> <span data-ttu-id="05749-115">言語バージョンを設定する方法はいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="05749-115">There are several ways to set the language version:</span></span>

- <span data-ttu-id="05749-116">[Visual Studio のクイック アクション](#visual-studio-quick-action)を利用する。</span><span class="sxs-lookup"><span data-stu-id="05749-116">Rely on a [Visual Studio quick action](#visual-studio-quick-action).</span></span>
- <span data-ttu-id="05749-117">[Visual Studio UI](#set-the-language-version-in-visual-studio) で言語バージョンを設定する。</span><span class="sxs-lookup"><span data-stu-id="05749-117">Set the language version in the [Visual Studio UI](#set-the-language-version-in-visual-studio).</span></span>
- <span data-ttu-id="05749-118">[**.csproj** ファイルを手動で編集する](#edit-the-csproj-file)。</span><span class="sxs-lookup"><span data-stu-id="05749-118">Manually edit your [**.csproj** file](#edit-the-csproj-file).</span></span>
- <span data-ttu-id="05749-119">[サブディレクトリ内の複数のプロジェクトに対して](#configure-multiple-projects)言語バージョンを設定する。</span><span class="sxs-lookup"><span data-stu-id="05749-119">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="05749-120">[`-langversion` コンパイラ オプション](#set-the-langversion-compiler-option)を構成する。</span><span class="sxs-lookup"><span data-stu-id="05749-120">Configure the [`-langversion` compiler option](#set-the-langversion-compiler-option).</span></span>

## <a name="visual-studio-quick-action"></a><span data-ttu-id="05749-121">Visual Studio のクイック アクション</span><span class="sxs-lookup"><span data-stu-id="05749-121">Visual Studio quick action</span></span>

<span data-ttu-id="05749-122">Visual Studio は、必要な言語バージョンを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="05749-122">Visual Studio helps you determine the language version you need.</span></span> <span data-ttu-id="05749-123">現在構成されているバージョンで使用できない言語機能を使用する場合、Visual Studio は、プロジェクトの言語バージョンを更新する可能性のある修正プログラムを示します。</span><span class="sxs-lookup"><span data-stu-id="05749-123">If you use a language feature that is not available for the currently configured version, Visual Studio shows a potential fix to update the language version for the project.</span></span>

## <a name="set-the-language-version-in-visual-studio"></a><span data-ttu-id="05749-124">Visual Studio で言語バージョンを設定する</span><span class="sxs-lookup"><span data-stu-id="05749-124">Set the language version in Visual Studio</span></span>

<span data-ttu-id="05749-125">Visual Studio のバージョンを設定できます。</span><span class="sxs-lookup"><span data-stu-id="05749-125">You can set the version in Visual Studio.</span></span> <span data-ttu-id="05749-126">ソリューション エクスプローラーでプロジェクト ノードを右クリックして、**[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="05749-126">Right-click on the project node in Solution Explorer and select **Properties**.</span></span> <span data-ttu-id="05749-127">**[ビルド]** タブを選択し、**[詳細設定]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="05749-127">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="05749-128">ドロップダウン リストで、バージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="05749-128">In the dropdown, select the version.</span></span> <span data-ttu-id="05749-129">次の図は "最新の" 設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="05749-129">The following image shows the "latest" setting:</span></span>

![言語バージョンを指定できる高度なビルド設定のスクリーン ショット](./media/configure-language-version/advanced-build-settings.png)

> [!NOTE]
> <span data-ttu-id="05749-131">Visual Studio IDE を使用して csproj ファイルを更新する場合、IDE によって、ビルド構成ごとにノードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="05749-131">If you use the Visual Studio IDE to update your csproj files, the IDE creates separate nodes for each build configuration.</span></span> <span data-ttu-id="05749-132">一般的に、すべてのビルド構成で同じように値を設定しますが、ビルド構成ごとに明示的に設定する必要があります。あるいは、この設定を変更するとき、"すべての構成" を選択します。</span><span class="sxs-lookup"><span data-stu-id="05749-132">You'll typically set the value the same in all build configurations, but you need to set it explicitly for each build configuration, or select "All Configurations" when you modify this setting.</span></span> <span data-ttu-id="05749-133">csproj ファイルに次が表示されます。</span><span class="sxs-lookup"><span data-stu-id="05749-133">You'll see the following in your csproj file:</span></span>
>
>```xml
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
>  <LangVersion>latest</LangVersion>
></PropertyGroup>
>
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
>  <LangVersion>latest</LangVersion>
> </PropertyGroup>
> ```
>

## <a name="edit-the-csproj-file"></a><span data-ttu-id="05749-134">csproj ファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="05749-134">Edit the csproj file</span></span>

<span data-ttu-id="05749-135">**.csproj** ファイルで言語バージョンを設定できます。</span><span class="sxs-lookup"><span data-stu-id="05749-135">You can set the language version in your **.csproj** file.</span></span> <span data-ttu-id="05749-136">次のような要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="05749-136">Add an element like the following:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="05749-137">値 `latest` は、C# 言語の最新のマイナー バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="05749-137">The value `latest` uses the latest minor version of the C# language.</span></span> <span data-ttu-id="05749-138">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="05749-138">Valid values are:</span></span>

|<span data-ttu-id="05749-139">[値]</span><span class="sxs-lookup"><span data-stu-id="05749-139">Value</span></span>|<span data-ttu-id="05749-140">説明</span><span class="sxs-lookup"><span data-stu-id="05749-140">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="05749-141">preview</span><span class="sxs-lookup"><span data-stu-id="05749-141">preview</span></span>|<span data-ttu-id="05749-142">コンパイラは、最新のプレビュー バージョンの有効な言語構文をすべて受け入れます。</span><span class="sxs-lookup"><span data-stu-id="05749-142">The compiler accepts all valid language syntax from the latest preview version.</span></span>|
|<span data-ttu-id="05749-143">latest</span><span class="sxs-lookup"><span data-stu-id="05749-143">latest</span></span>|<span data-ttu-id="05749-144">コンパイラは、最新リリース バージョンのコンパイラ (マイナー バージョンを含む) の構文を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="05749-144">The compiler accepts syntax from the latest released version of the compiler (including minor version).</span></span>|
|<span data-ttu-id="05749-145">latestMajor</span><span class="sxs-lookup"><span data-stu-id="05749-145">latestMajor</span></span>|<span data-ttu-id="05749-146">コンパイラは、最新リリースのメジャー バージョンのコンパイラの構文を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="05749-146">The compiler accepts syntax from the latest released major version of the compiler.</span></span>|
|<span data-ttu-id="05749-147">8.0</span><span class="sxs-lookup"><span data-stu-id="05749-147">8.0</span></span>|<span data-ttu-id="05749-148">コンパイラは、C# 8.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="05749-148">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="05749-149">7.3</span><span class="sxs-lookup"><span data-stu-id="05749-149">7.3</span></span>|<span data-ttu-id="05749-150">コンパイラは、C# 7.3 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="05749-150">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="05749-151">7.2</span><span class="sxs-lookup"><span data-stu-id="05749-151">7.2</span></span>|<span data-ttu-id="05749-152">コンパイラは、C# 7.2 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="05749-152">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="05749-153">7.1</span><span class="sxs-lookup"><span data-stu-id="05749-153">7.1</span></span>|<span data-ttu-id="05749-154">コンパイラは、C# 7.1 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="05749-154">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="05749-155">7</span><span class="sxs-lookup"><span data-stu-id="05749-155">7</span></span>|<span data-ttu-id="05749-156">コンパイラは、C# 7.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="05749-156">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="05749-157">6</span><span class="sxs-lookup"><span data-stu-id="05749-157">6</span></span>|<span data-ttu-id="05749-158">コンパイラは、C# 6.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="05749-158">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="05749-159">5</span><span class="sxs-lookup"><span data-stu-id="05749-159">5</span></span>|<span data-ttu-id="05749-160">コンパイラは、C# 5.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="05749-160">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="05749-161">4</span><span class="sxs-lookup"><span data-stu-id="05749-161">4</span></span>|<span data-ttu-id="05749-162">コンパイラは、C# 4.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="05749-162">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="05749-163">3</span><span class="sxs-lookup"><span data-stu-id="05749-163">3</span></span>|<span data-ttu-id="05749-164">コンパイラは、C# 3.0 以下に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="05749-164">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="05749-165">ISO-2</span><span class="sxs-lookup"><span data-stu-id="05749-165">ISO-2</span></span>|<span data-ttu-id="05749-166">コンパイラは、ISO/IEC 23270:2006 C# (2.0) に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="05749-166">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0)</span></span> |
|<span data-ttu-id="05749-167">ISO-1</span><span class="sxs-lookup"><span data-stu-id="05749-167">ISO-1</span></span>|<span data-ttu-id="05749-168">コンパイラは、ISO/IEC 23270:2003 C# (1.0/1.2) に含まれている構文のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="05749-168">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2)</span></span> |

## <a name="configure-multiple-projects"></a><span data-ttu-id="05749-169">複数のプロジェクトを構成する</span><span class="sxs-lookup"><span data-stu-id="05749-169">Configure multiple projects</span></span>

<span data-ttu-id="05749-170">複数のディレクトリを構成する `<LangVersion>` 要素を含む **Directory.Build.props** ファイルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="05749-170">You can create a **Directory.Build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="05749-171">この操作は通常、ソリューション ディレクトリで実行します。</span><span class="sxs-lookup"><span data-stu-id="05749-171">You typically do that in your solution directory.</span></span> <span data-ttu-id="05749-172">ソリューション ディレクトリ内の **Directory.Build.props** ファイルに以下を追加します。</span><span class="sxs-lookup"><span data-stu-id="05749-172">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>7.3</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="05749-173">これで、そのファイルを含むディレクトリのすべてのサブディレクトリ内のビルドで、C# バージョン 7.3 構文が使用されます。</span><span class="sxs-lookup"><span data-stu-id="05749-173">Now, builds in every subdirectory of the directory containing that file will use C# version 7.3 syntax.</span></span> <span data-ttu-id="05749-174">詳しくは、「[ビルドのカスタマイズ](/visualstudio/msbuild/customize-your-build)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05749-174">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="set-the-langversion-compiler-option"></a><span data-ttu-id="05749-175">言語コンパイラ オプションを設定する</span><span class="sxs-lookup"><span data-stu-id="05749-175">Set the langversion compiler option</span></span>

<span data-ttu-id="05749-176">`-langversion` コマンド ライン オプションを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="05749-176">You can use the `-langversion` command-line option.</span></span> <span data-ttu-id="05749-177">詳しくは、[-langversion](../language-reference/compiler-options/langversion-compiler-option.md) コンパイラ オプションに関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05749-177">For more information, see the article on the [-langversion](../language-reference/compiler-options/langversion-compiler-option.md) compiler option.</span></span> <span data-ttu-id="05749-178">「`csc -langversion:?`」と入力して、有効な値の一覧を確認できます。</span><span class="sxs-lookup"><span data-stu-id="05749-178">You can see a list of the valid values by typing  `csc -langversion:?`.</span></span>
