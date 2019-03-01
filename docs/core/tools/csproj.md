---
title: .NET Core の csproj 形式に追加されたもの
description: 既存の csproj ファイルと .NET Core の csproj ファイルの違いについて説明します
author: blackdwarf
ms.date: 09/22/2017
ms.openlocfilehash: d715a3a30c48f1c3fa837b24ee21b49fa947011a
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "56748011"
---
# <a name="additions-to-the-csproj-format-for-net-core"></a><span data-ttu-id="c758e-103">.NET Core の csproj 形式に追加されたもの</span><span class="sxs-lookup"><span data-stu-id="c758e-103">Additions to the csproj format for .NET Core</span></span>

<span data-ttu-id="c758e-104">ここでは、*project.json* から *csproj* および [MSBuild](https://github.com/Microsoft/MSBuild) への移行に伴ってプロジェクト ファイルに追加された変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="c758e-104">This document outlines the changes that were added to the project files as part of the move from *project.json* to *csproj* and [MSBuild](https://github.com/Microsoft/MSBuild).</span></span> <span data-ttu-id="c758e-105">一般的なプロジェクト ファイルの構文とリファレンスの詳細については、[MSBuild プロジェクト ファイル](/visualstudio/msbuild/msbuild-project-file-schema-reference)のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c758e-105">For more information about general project file syntax and reference, see [the MSBuild project file](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation.</span></span>  

## <a name="implicit-package-references"></a><span data-ttu-id="c758e-106">暗黙的なパッケージ参照</span><span class="sxs-lookup"><span data-stu-id="c758e-106">Implicit package references</span></span>
<span data-ttu-id="c758e-107">メタパッケージは、プロジェクト ファイルの `<TargetFramework>` または `<TargetFrameworks>` プロパティに指定されている対象フレームワークに基づいて暗黙的に参照されています。</span><span class="sxs-lookup"><span data-stu-id="c758e-107">Metapackages are implicitly referenced based on the target framework(s) specified in the `<TargetFramework>` or `<TargetFrameworks>` property of your project file.</span></span> <span data-ttu-id="c758e-108">`<TargetFramework>` を指定すると、順序に関係なく `<TargetFrameworks>` は無視されます。</span><span class="sxs-lookup"><span data-stu-id="c758e-108">`<TargetFrameworks>` is ignored if `<TargetFramework>` is specified, independent of order.</span></span>

```xml
 <PropertyGroup>
   <TargetFramework>netcoreapp2.1</TargetFramework>
 </PropertyGroup>
 ```
 
 ```xml
 <PropertyGroup>
   <TargetFrameworks>netcoreapp2.1;net462</TargetFrameworks>
 </PropertyGroup>
 ```

### <a name="recommendations"></a><span data-ttu-id="c758e-109">推奨事項</span><span class="sxs-lookup"><span data-stu-id="c758e-109">Recommendations</span></span>
<span data-ttu-id="c758e-110">`Microsoft.NETCore.App` または `NetStandard.Library` メタパッケージは暗黙的に参照されるので、ベスト プラクティスとして以下が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="c758e-110">Since `Microsoft.NETCore.App` or `NetStandard.Library` metapackages are implicitly referenced, the following are our recommended best practices:</span></span>

* <span data-ttu-id="c758e-111">.NET Core または .NET Standard を対象とするとき、プロジェクト ファイルの `<PackageReference>` アイテム経由で `Microsoft.NETCore.App` または `NetStandard.Library` メタパッケージを明示的に参照しないようにします。</span><span class="sxs-lookup"><span data-stu-id="c758e-111">When targeting .NET Core or .NET Standard, never have an explicit reference to the `Microsoft.NETCore.App` or `NetStandard.Library` metapackages via a `<PackageReference>` item in your project file.</span></span>
* <span data-ttu-id="c758e-112">.NET Core を対象にするとき、特定バージョンのランタイムが必要な場合、メタパッケージを参照するのではなく、プロジェクト内で `<RuntimeFrameworkVersion>` プロパティを使用します (`1.0.4` など)。</span><span class="sxs-lookup"><span data-stu-id="c758e-112">If you need a specific version of the runtime when targeting .NET Core, you should use the `<RuntimeFrameworkVersion>` property in your project (for example, `1.0.4`) instead of referencing the metapackage.</span></span>
    * <span data-ttu-id="c758e-113">[自己完結型の展開](../deploying/index.md#self-contained-deployments-scd)を使用し、特定のパッチ バージョンの 1.0.0 LTS ランタイムが必要な場合などにこの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c758e-113">This might happen if you are using [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) and you need a specific patch version of 1.0.0 LTS runtime, for example.</span></span>
* <span data-ttu-id="c758e-114">.NET Standard を対象にするとき、特定バージョンの `NetStandard.Library` メタパッケージが必要な場合、`<NetStandardImplicitPackageVersion>` プロパティを使用し、必要なバージョンを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c758e-114">If you need a specific version of the `NetStandard.Library` metapackage when targeting .NET Standard, you can use the `<NetStandardImplicitPackageVersion>` property and set the version you need.</span></span>
* <span data-ttu-id="c758e-115">.NET Framework プロジェクトでは、`Microsoft.NETCore.App` または `NetStandard.Library` メタパッケージに参照を明示的に追加したり、更新したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="c758e-115">Don't explicitly add or update references to either the `Microsoft.NETCore.App` or `NetStandard.Library` metapackage in .NET Framework projects.</span></span> <span data-ttu-id="c758e-116">.NET Standard ベースの NuGet パッケージを使用するとき、何らかのバージョンの `NetStandard.Library` が必要であれば、NuGet はそのバージョンを自動的にインストールします。</span><span class="sxs-lookup"><span data-stu-id="c758e-116">If any version of `NetStandard.Library` is needed when using a .NET Standard-based NuGet package, NuGet automatically installs that version.</span></span>

## <a name="default-compilation-includes-in-net-core-projects"></a><span data-ttu-id="c758e-117">.NET Core プロジェクトの既定のコンパイルの include</span><span class="sxs-lookup"><span data-stu-id="c758e-117">Default compilation includes in .NET Core projects</span></span>
<span data-ttu-id="c758e-118">最新バージョンの SDK の *csproj* 形式に移行すると共に、コンパイル項目と、SDK プロパティ ファイルに埋め込みリソースの既定の include と exclude を SDK プロパティ ファイルに移行しました。</span><span class="sxs-lookup"><span data-stu-id="c758e-118">With the move to the *csproj* format in the latest SDK versions, we've moved the default includes and excludes for compile items and embedded resources to the SDK properties files.</span></span> <span data-ttu-id="c758e-119">つまり、これらの項目をプロジェクト ファイルに指定する必要はなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c758e-119">This means that you no longer need to specify these items in your project file.</span></span> 

<span data-ttu-id="c758e-120">これを行う主な理由は、プロジェクト ファイルを見やすくするためです。</span><span class="sxs-lookup"><span data-stu-id="c758e-120">The main reason for doing this is to reduce the clutter in your project file.</span></span> <span data-ttu-id="c758e-121">SDK の既定値は、最も一般的な使用例に対応しているので、作成するプロジェクトごとに繰り返す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c758e-121">The defaults that are present in the SDK should cover most common use cases, so there is no need to repeat them in every project that you create.</span></span> <span data-ttu-id="c758e-122">その結果、プロジェクト ファイルが小さくなり、わかりやすく、編集が必要な場合に編集しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="c758e-122">This leads to smaller project files that are much easier to understand as well as edit by hand, if needed.</span></span> 

<span data-ttu-id="c758e-123">次の表は、SDK に含まれる、および除外される要素と [glob](https://en.wikipedia.org/wiki/Glob_(programming)) の一覧です。</span><span class="sxs-lookup"><span data-stu-id="c758e-123">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are both included and excluded in the SDK:</span></span> 

| <span data-ttu-id="c758e-124">要素</span><span class="sxs-lookup"><span data-stu-id="c758e-124">Element</span></span>           | <span data-ttu-id="c758e-125">含まれる glob</span><span class="sxs-lookup"><span data-stu-id="c758e-125">Include glob</span></span>                              | <span data-ttu-id="c758e-126">除外される glob</span><span class="sxs-lookup"><span data-stu-id="c758e-126">Exclude glob</span></span>                                                  | <span data-ttu-id="c758e-127">glob の削除</span><span class="sxs-lookup"><span data-stu-id="c758e-127">Remove glob</span></span>                |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| <span data-ttu-id="c758e-128">Compile</span><span class="sxs-lookup"><span data-stu-id="c758e-128">Compile</span></span>           | <span data-ttu-id="c758e-129">\*\*/\*.cs (または他の言語拡張機能)</span><span class="sxs-lookup"><span data-stu-id="c758e-129">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="c758e-130">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="c758e-130">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="c758e-131">N/A</span><span class="sxs-lookup"><span data-stu-id="c758e-131">N/A</span></span>                        |
| <span data-ttu-id="c758e-132">EmbeddedResource</span><span class="sxs-lookup"><span data-stu-id="c758e-132">EmbeddedResource</span></span>  | <span data-ttu-id="c758e-133">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="c758e-133">\*\*/\*.resx</span></span>                              | <span data-ttu-id="c758e-134">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="c758e-134">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="c758e-135">N/A</span><span class="sxs-lookup"><span data-stu-id="c758e-135">N/A</span></span>                        |
| <span data-ttu-id="c758e-136">なし</span><span class="sxs-lookup"><span data-stu-id="c758e-136">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="c758e-137">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="c758e-137">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="c758e-138">- \*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="c758e-138">- \*\*/\*.cs; \*\*/\*.resx</span></span> |

<span data-ttu-id="c758e-139">プロジェクトに glob があり、最新の SDK を使用してビルドしようとすると、次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c758e-139">If you have globs in your project and you try to build it using the newest SDK, you'll get the following error:</span></span>

> <span data-ttu-id="c758e-140">重複するコンパイル項目が含まれていました。</span><span class="sxs-lookup"><span data-stu-id="c758e-140">Duplicate Compile items were included.</span></span> <span data-ttu-id="c758e-141">.NET SDK には、既定でプロジェクト ディレクトリのコンパイル項目が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c758e-141">The .NET SDK includes Compile items from your project directory by default.</span></span> <span data-ttu-id="c758e-142">これらの項目をプロジェクト ファイルから削除するか、プロジェクト ファイルに明示的に含める場合は 'EnableDefaultCompileItems' プロパティを 'false' に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="c758e-142">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span> 

<span data-ttu-id="c758e-143">このエラーを回避するには、前の表にあるものと一致する明示的な `Compile` 項目を削除するか、次のように `<EnableDefaultCompileItems>` プロパティを `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-143">In order to get around this error, you can either remove the explicit `Compile` items that match the ones listed on the previous table, or you can set the `<EnableDefaultCompileItems>` property to `false`, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
<span data-ttu-id="c758e-144">このプロパティを `false` に設定すると、暗黙的に含める動作が無効になり、以前の SDK の動作に戻り、プロジェクトに既定の glob が指定されます。</span><span class="sxs-lookup"><span data-stu-id="c758e-144">Setting this property to `false` will disable implicit inclusion, reverting to the behavior of previous SDKs where you had to specify the default globs in your project.</span></span>

<span data-ttu-id="c758e-145">この変更で、他の include の主なしくみは変わりません。</span><span class="sxs-lookup"><span data-stu-id="c758e-145">This change does not modify the main mechanics of other includes.</span></span> <span data-ttu-id="c758e-146">ただし、たとえばアプリで発行する一部のファイルを指定する場合は、*csproj* で既知のしくみ (たとえば `<Content>` 要素) を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="c758e-146">However, if you wish to specify, for example, some files to get published with your app, you can still use the known mechanisms in *csproj* for that (for example, the `<Content>` element).</span></span>

<span data-ttu-id="c758e-147">`<EnableDefaultCompileItems>` は `Compile` glob のみを無効にし、\*.cs 項目にも適用される暗黙的 `None` glob など、他の Glob には影響しません。</span><span class="sxs-lookup"><span data-stu-id="c758e-147">`<EnableDefaultCompileItems>` only disables `Compile` globs but doesn't affect other globs, like the implicit `None` glob, which also applies to \*.cs items.</span></span> <span data-ttu-id="c758e-148">そのため、**ソリューション エクスプローラー**は \*.cs 項目を `None` 項目として含まれた、プロジェクトの一部として引き続き表示します。</span><span class="sxs-lookup"><span data-stu-id="c758e-148">Because of that, **Solution Explorer** will continue show \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="c758e-149">同様に、`<EnableDefaultNoneItems>` を利用して暗黙的 `None` glob を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="c758e-149">In a similar way, you can use `<EnableDefaultNoneItems>` to disable the implicit `None` glob.</span></span>

<span data-ttu-id="c758e-150">**暗黙的 glob をすべて**無効にするには、`<EnableDefaultItems>` プロパティを `false` に設定します。次の例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c758e-150">To disable **all implicit globs**, you can set the `<EnableDefaultItems>` property to `false` as in the following example:</span></span>
```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a><span data-ttu-id="c758e-151">MSBuild と同じようにプロジェクト全体を表示する方法</span><span class="sxs-lookup"><span data-stu-id="c758e-151">How to see the whole project as MSBuild sees it</span></span>

<span data-ttu-id="c758e-152">これらの csproj 変更でプロジェクト ファイルが大幅に簡素化されますが、SDK とそのターゲットが追加されたとき、MSBuild と同様にプロジェクト全体を表示すると便利なことがあります。</span><span class="sxs-lookup"><span data-stu-id="c758e-152">While those csproj changes greatly simplify project files, you might want to see the fully expanded project as MSBuild sees it once the SDK and its targets are included.</span></span> <span data-ttu-id="c758e-153">[`dotnet msbuild`](dotnet-msbuild.md) コマンドの [`/pp` スイッチ](/visualstudio/msbuild/msbuild-command-line-reference#preprocess)でプロジェクトを事前処理します。インポートされるファイル、そのソース、ビルドに対するその貢献が、実際にプロジェクトをビルドすることなく、表示されます。</span><span class="sxs-lookup"><span data-stu-id="c758e-153">Preprocess the project with [the `/pp` switch](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) of the [`dotnet msbuild`](dotnet-msbuild.md) command, which shows which files are imported, their sources, and their contributions to the build without actually building the project:</span></span>

`dotnet msbuild -pp:fullproject.xml`

<span data-ttu-id="c758e-154">プロジェクトにターゲット フレームワークが複数存在する場合、MSBuild プロパティとして指定し、1 つだけにコマンドの結果を集中させてください。</span><span class="sxs-lookup"><span data-stu-id="c758e-154">If the project has multiple target frameworks, the results of the command should be focused on only one of them by specifying it as an MSBuild property:</span></span>

`dotnet msbuild -p:TargetFramework=netcoreapp2.0 -pp:fullproject.xml`

## <a name="additions"></a><span data-ttu-id="c758e-155">追加</span><span class="sxs-lookup"><span data-stu-id="c758e-155">Additions</span></span>

### <a name="sdk-attribute"></a><span data-ttu-id="c758e-156">SDK 属性</span><span class="sxs-lookup"><span data-stu-id="c758e-156">Sdk attribute</span></span> 
<span data-ttu-id="c758e-157">*.csproj* ファイルのルート `<Project>` 要素には、`Sdk` という新しい属性があります。</span><span class="sxs-lookup"><span data-stu-id="c758e-157">The root `<Project>` element of the *.csproj* file has a new attribute called `Sdk`.</span></span> <span data-ttu-id="c758e-158">`Sdk` は、プロジェクトで使用される SDK を指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-158">`Sdk` specifies which SDK will be used by the project.</span></span> <span data-ttu-id="c758e-159">[レイヤー化のドキュメント](cli-msbuild-architecture.md)で説明されているように、SDK は、.NET Core コードをビルドできる MSBuild [タスク](/visualstudio/msbuild/msbuild-tasks)および[ターゲット](/visualstudio/msbuild/msbuild-targets)のセットです。</span><span class="sxs-lookup"><span data-stu-id="c758e-159">The SDK, as the [layering document](cli-msbuild-architecture.md) describes, is a set of MSBuild [tasks](/visualstudio/msbuild/msbuild-tasks) and [targets](/visualstudio/msbuild/msbuild-targets) that can build .NET Core code.</span></span> <span data-ttu-id="c758e-160">.NET Core ツールには主に 3 つの SDK が付属しています。</span><span class="sxs-lookup"><span data-stu-id="c758e-160">We ship three main SDKs with the .NET Core tools:</span></span>

1. <span data-ttu-id="c758e-161">ID が `Microsoft.NET.Sdk` の .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="c758e-161">The .NET Core SDK with the ID of `Microsoft.NET.Sdk`</span></span>
2. <span data-ttu-id="c758e-162">ID が `Microsoft.NET.Sdk.Web` の .NET Core Web SDK</span><span class="sxs-lookup"><span data-stu-id="c758e-162">The .NET Core web SDK with the ID of `Microsoft.NET.Sdk.Web`</span></span>
3. <span data-ttu-id="c758e-163">ID が `Microsoft.NET.Sdk.Razor` の .NET Core Razor クラス ライブラリ SDK</span><span class="sxs-lookup"><span data-stu-id="c758e-163">The .NET Core Razor Class Library SDK with the ID of `Microsoft.NET.Sdk.Razor`</span></span>

<span data-ttu-id="c758e-164">.NET Core ツールを使用し、コードをビルドするには、`Sdk` 属性を `<Project>` 要素の ID のいずれかに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c758e-164">You need to have the `Sdk` attribute set to one of those IDs on the `<Project>` element in order to use the .NET Core tools and build your code.</span></span> 

### <a name="packagereference"></a><span data-ttu-id="c758e-165">PackageReference</span><span class="sxs-lookup"><span data-stu-id="c758e-165">PackageReference</span></span>
<span data-ttu-id="c758e-166">`<PackageReference>` 項目要素では、[プロジェクトでの NuGet の依存関係](/nuget/consume-packages/package-references-in-project-files)を指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-166">A `<PackageReference>` item element specifies a [NuGet dependency in the project](/nuget/consume-packages/package-references-in-project-files).</span></span> <span data-ttu-id="c758e-167">`Include` 属性は、パッケージ ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-167">The `Include` attribute specifies the package ID.</span></span> 

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a><span data-ttu-id="c758e-168">Version</span><span class="sxs-lookup"><span data-stu-id="c758e-168">Version</span></span>
<span data-ttu-id="c758e-169">必須の `Version` 属性では、復元するパッケージのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-169">The required `Version` attribute specifies the version of the package to restore.</span></span> <span data-ttu-id="c758e-170">この属性は、[NuGet バージョン管理](/nuget/reference/package-versioning#version-ranges-and-wildcards)スキームの規則に従います。</span><span class="sxs-lookup"><span data-stu-id="c758e-170">The attribute respects the rules of the [NuGet versioning](/nuget/reference/package-versioning#version-ranges-and-wildcards) scheme.</span></span> <span data-ttu-id="c758e-171">既定の動作では、バージョンを正確に一致させます。</span><span class="sxs-lookup"><span data-stu-id="c758e-171">The default behavior is an exact version match.</span></span> <span data-ttu-id="c758e-172">たとえば、`Version="1.2.3"` を指定すると、パッケージのバージョンが正確に 1.2.3 であることを表す NuGet 表記の `[1.2.3]` と同じになります。</span><span class="sxs-lookup"><span data-stu-id="c758e-172">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

#### <a name="includeassets-excludeassets-and-privateassets"></a><span data-ttu-id="c758e-173">IncludeAssets、ExcludeAssets、PrivateAssets</span><span class="sxs-lookup"><span data-stu-id="c758e-173">IncludeAssets, ExcludeAssets and PrivateAssets</span></span>
<span data-ttu-id="c758e-174">`IncludeAssets` 属性は、`<PackageReference>` で指定されているパッケージに属するアセットのうち、使う必要があるものを指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-174">`IncludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> <span data-ttu-id="c758e-175">既定では、パッケージのすべてのアセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c758e-175">By default, all package assets are included.</span></span>

<span data-ttu-id="c758e-176">`ExcludeAssets` 属性は、`<PackageReference>` で指定されているパッケージに属するアセットのうち、使う必要がないものを指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-176">`ExcludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span>

<span data-ttu-id="c758e-177">`PrivateAssets` 属性は、`<PackageReference>` で指定されているパッケージに属するアセットで、使う必要はあるが、次のプロジェクトに渡してはならないものを指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-177">`PrivateAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed but not flow to the next project.</span></span> <span data-ttu-id="c758e-178">この属性が存在しない場合、`Analyzers`、`Build`、`ContentFiles` アセットは既定でプライベートになります。</span><span class="sxs-lookup"><span data-stu-id="c758e-178">The `Analyzers`, `Build` and `ContentFiles` assets are private by default when this attribute is not present.</span></span>

> [!NOTE]
> <span data-ttu-id="c758e-179">`PrivateAssets` は *project.json*/*xproj* `SuppressParent` 要素と同等です。</span><span class="sxs-lookup"><span data-stu-id="c758e-179">`PrivateAssets` is equivalent to the *project.json*/*xproj* `SuppressParent` element.</span></span>

<span data-ttu-id="c758e-180">これらの属性には以下の項目を 1 つ以上含めることができ、複数ある場合はセミコロン `;` 文字で区切ります。</span><span class="sxs-lookup"><span data-stu-id="c758e-180">These attributes can contain one or more of the following items, separated by the semicolon `;` character if more than one is listed:</span></span>

* <span data-ttu-id="c758e-181">`Compile` - コンパイルで使用できる lib フォルダーの内容です。</span><span class="sxs-lookup"><span data-stu-id="c758e-181">`Compile` – the contents of the lib folder are available to compile against.</span></span>
* <span data-ttu-id="c758e-182">`Runtime` - 配布する runtime フォルダーの内容です。</span><span class="sxs-lookup"><span data-stu-id="c758e-182">`Runtime` – the contents of the runtime folder are distributed.</span></span>
* <span data-ttu-id="c758e-183">`ContentFiles` - 使用する *contentfiles* フォルダーの内容です。</span><span class="sxs-lookup"><span data-stu-id="c758e-183">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
* <span data-ttu-id="c758e-184">`Build` - 使用する build フォルダーのプロパティ/ターゲットです。</span><span class="sxs-lookup"><span data-stu-id="c758e-184">`Build` – the props/targets in the build folder are used.</span></span>
* <span data-ttu-id="c758e-185">`Native` - ランタイムの output フォルダーにコピーするネイティブ アセットの内容です。</span><span class="sxs-lookup"><span data-stu-id="c758e-185">`Native` – the contents from native assets are copied to the output folder for runtime.</span></span>
* <span data-ttu-id="c758e-186">`Analyzers` - アナライザーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c758e-186">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="c758e-187">代わりに、次の値を属性に含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="c758e-187">Alternatively, the attribute can contain:</span></span>

* <span data-ttu-id="c758e-188">`None` - いずれのアセットも使用されません。</span><span class="sxs-lookup"><span data-stu-id="c758e-188">`None` – none of the assets are used.</span></span>
* <span data-ttu-id="c758e-189">`All` - すべてのアセットが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c758e-189">`All` – all assets are used.</span></span>

### <a name="dotnetclitoolreference"></a><span data-ttu-id="c758e-190">DotNetCliToolReference</span><span class="sxs-lookup"><span data-stu-id="c758e-190">DotNetCliToolReference</span></span>
<span data-ttu-id="c758e-191">`<DotNetCliToolReference>` 項目要素は、プロジェクトのコンテキストでユーザーが復元を望む CLI ツールを指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-191">A `<DotNetCliToolReference>` item element specifies the CLI tool that the user wants to restore in the context of the project.</span></span> <span data-ttu-id="c758e-192">*project.json* の `tools` ノードに代わるものです。</span><span class="sxs-lookup"><span data-stu-id="c758e-192">It's a replacement for the `tools` node in *project.json*.</span></span> 

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

#### <a name="version"></a><span data-ttu-id="c758e-193">Version</span><span class="sxs-lookup"><span data-stu-id="c758e-193">Version</span></span>
<span data-ttu-id="c758e-194">`Version` は、復元するパッケージのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-194">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="c758e-195">この属性は、[NuGet バージョン管理](/nuget/create-packages/dependency-versions#version-ranges)スキームの規則に従います。</span><span class="sxs-lookup"><span data-stu-id="c758e-195">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="c758e-196">既定の動作では、バージョンを正確に一致させます。</span><span class="sxs-lookup"><span data-stu-id="c758e-196">The default behavior is an exact version match.</span></span> <span data-ttu-id="c758e-197">たとえば、`Version="1.2.3"` を指定すると、パッケージのバージョンが正確に 1.2.3 であることを表す NuGet 表記の `[1.2.3]` と同じになります。</span><span class="sxs-lookup"><span data-stu-id="c758e-197">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

### <a name="runtimeidentifiers"></a><span data-ttu-id="c758e-198">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="c758e-198">RuntimeIdentifiers</span></span>
<span data-ttu-id="c758e-199">`<RuntimeIdentifiers>` プロパティ要素では、プロジェクトの[ランタイム識別子 (RID)](../rid-catalog.md) のセミコロン区切りリストを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c758e-199">The `<RuntimeIdentifiers>` property element lets you specify a semicolon-delimited list of [Runtime Identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="c758e-200">RID により、自己完結型の展開を発行できます。</span><span class="sxs-lookup"><span data-stu-id="c758e-200">RIDs enable publishing self-contained deployments.</span></span> 

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a><span data-ttu-id="c758e-201">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="c758e-201">RuntimeIdentifier</span></span>
<span data-ttu-id="c758e-202">`<RuntimeIdentifier>` プロパティ要素では、プロジェクトの[ランタイム識別子 (RID)](../rid-catalog.md) を 1 つだけ指定できます。</span><span class="sxs-lookup"><span data-stu-id="c758e-202">The `<RuntimeIdentifier>` property element allows you to specify only one [Runtime Identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="c758e-203">RID により、自己完結型の展開を発行できます。</span><span class="sxs-lookup"><span data-stu-id="c758e-203">The RID enables publishing a self-contained deployment.</span></span>

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

<span data-ttu-id="c758e-204">複数のランタイムに対して発行する必要がある場合、代わりに `<RuntimeIdentifiers>` (複数) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c758e-204">Use `<RuntimeIdentifiers>` (plural) instead if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="c758e-205">`<RuntimeIdentifier>` では、必要なランタイムが 1 つだけのとき、ビルドが速くなります。</span><span class="sxs-lookup"><span data-stu-id="c758e-205">`<RuntimeIdentifier>` can provide faster builds when only a single runtime is required.</span></span>

### <a name="packagetargetfallback"></a><span data-ttu-id="c758e-206">PackageTargetFallback</span><span class="sxs-lookup"><span data-stu-id="c758e-206">PackageTargetFallback</span></span> 
<span data-ttu-id="c758e-207">`<PackageTargetFallback>` プロパティ要素では、パッケージの復元時に使用する、互換性のある一連のターゲットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c758e-207">The `<PackageTargetFallback>` property element allows you to specify a set of compatible targets to be used when restoring packages.</span></span> <span data-ttu-id="c758e-208">dotnet [TxM (Target x Moniker)](/nuget/schema/target-frameworks) を使用するパッケージに、dotnet TxM を宣言しないパッケージで動作することを許可するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="c758e-208">It's designed to allow packages that use the dotnet [TxM (Target x Moniker)](/nuget/schema/target-frameworks) to operate with packages that don't declare a dotnet TxM.</span></span> <span data-ttu-id="c758e-209">プロジェクトで dotnet TxM を使用せず、依存するすべてのパッケージに dotnet TxM を与える必要がある場合、非 dotnet プラットフォームを dotnet 対応にするためにプロジェクトに `<PackageTargetFallback>` を追加します。</span><span class="sxs-lookup"><span data-stu-id="c758e-209">If your project uses the dotnet TxM, then all the packages it depends on must also have a dotnet TxM, unless you add the `<PackageTargetFallback>` to your project in order to allow non-dotnet platforms to be compatible with dotnet.</span></span> 

<span data-ttu-id="c758e-210">次の例では、プロジェクトのすべてのターゲットにフォールバックを提供しています。</span><span class="sxs-lookup"><span data-stu-id="c758e-210">The following example provides the fallbacks for all targets in your project:</span></span> 

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

<span data-ttu-id="c758e-211">次の例では、`netcoreapp2.1` ターゲットにのみフォールバックを指定しています。</span><span class="sxs-lookup"><span data-stu-id="c758e-211">The following example specifies the fallbacks only for the `netcoreapp2.1` target:</span></span>

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp2.1'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="nuget-metadata-properties"></a><span data-ttu-id="c758e-212">NuGet メタデータ プロパティ</span><span class="sxs-lookup"><span data-stu-id="c758e-212">NuGet metadata properties</span></span>
<span data-ttu-id="c758e-213">MSBuild への移行に伴い、*project.json* ファイルから *csproj* ファイルに NuGet パッケージをパックするときに使用される入力メタデータを移動しました。</span><span class="sxs-lookup"><span data-stu-id="c758e-213">With the move to MSBuild, we have moved the input metadata that is used when packing a NuGet package from *project.json* to *.csproj* files.</span></span> <span data-ttu-id="c758e-214">入力は MSBuild プロパティなので、`<PropertyGroup>` グループ内で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c758e-214">The inputs are MSBuild properties so they have to go within a `<PropertyGroup>` group.</span></span> <span data-ttu-id="c758e-215">次に示すのは、`dotnet pack` コマンドまたは SDK の一部である `Pack` MSBuild ターゲットを使用するときに、パッキング プロセスへの入力として使用されるプロパティの一覧です。</span><span class="sxs-lookup"><span data-stu-id="c758e-215">The following is the list of properties that are used as inputs to the packing process when using the `dotnet pack` command or the `Pack` MSBuild target that is part of the SDK.</span></span> 

### <a name="ispackable"></a><span data-ttu-id="c758e-216">IsPackable</span><span class="sxs-lookup"><span data-stu-id="c758e-216">IsPackable</span></span>
<span data-ttu-id="c758e-217">プロジェクトをパックできるかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="c758e-217">A Boolean value that specifies whether the project can be packed.</span></span> <span data-ttu-id="c758e-218">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="c758e-218">The default value is `true`.</span></span> 

### <a name="packageversion"></a><span data-ttu-id="c758e-219">PackageVersion</span><span class="sxs-lookup"><span data-stu-id="c758e-219">PackageVersion</span></span>
<span data-ttu-id="c758e-220">結果のパッケージのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-220">Specifies the version that the resulting package will have.</span></span> <span data-ttu-id="c758e-221">すべてのフォームの NuGet バージョン文字列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="c758e-221">Accepts all forms of NuGet version string.</span></span> <span data-ttu-id="c758e-222">既定値は `$(Version)` です。つまり、プロジェクトのプロパティ `Version` の値です。</span><span class="sxs-lookup"><span data-stu-id="c758e-222">Default is the value of `$(Version)`, that is, of the property `Version` in the project.</span></span> 

### <a name="packageid"></a><span data-ttu-id="c758e-223">PackageId</span><span class="sxs-lookup"><span data-stu-id="c758e-223">PackageId</span></span>
<span data-ttu-id="c758e-224">結果のパッケージの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-224">Specifies the name for the resulting package.</span></span> <span data-ttu-id="c758e-225">指定しない場合、`pack` 操作の既定では、`AssemblyName` またはディレクトリ名をパッケージ名として使用します。</span><span class="sxs-lookup"><span data-stu-id="c758e-225">If not specified, the `pack` operation will default to using the `AssemblyName` or directory name as the name of the package.</span></span> 

### <a name="title"></a><span data-ttu-id="c758e-226">Title</span><span class="sxs-lookup"><span data-stu-id="c758e-226">Title</span></span>
<span data-ttu-id="c758e-227">人が読みやすいパッケージのタイトル。通常、nuget.org と、Visual Studio のパッケージ マネージャーの UI 画面で使用されます。</span><span class="sxs-lookup"><span data-stu-id="c758e-227">A human-friendly title of the package, typically used in UI displays as on nuget.org and the Package Manager in Visual Studio.</span></span> <span data-ttu-id="c758e-228">指定しない場合、パッケージ ID が代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c758e-228">If not specified, the package ID is used instead.</span></span>

### <a name="authors"></a><span data-ttu-id="c758e-229">Authors</span><span class="sxs-lookup"><span data-stu-id="c758e-229">Authors</span></span>
<span data-ttu-id="c758e-230">nuget.org のプロファイル名と一致するパッケージ作成者をセミコロンで区切った一覧。これらは nuget.org の NuGet ギャラリーに表示され、同じ作成者によるパッケージの相互参照に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c758e-230">A semicolon-separated list of packages authors, matching the profile names on nuget.org. These are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span>

### <a name="packagedescription"></a><span data-ttu-id="c758e-231">PackageDescription</span><span class="sxs-lookup"><span data-stu-id="c758e-231">PackageDescription</span></span>

<span data-ttu-id="c758e-232">UI 画面用のパッケージの長い説明。</span><span class="sxs-lookup"><span data-stu-id="c758e-232">A long description of the package for UI display.</span></span>

### <a name="description"></a><span data-ttu-id="c758e-233">説明</span><span class="sxs-lookup"><span data-stu-id="c758e-233">Description</span></span>
<span data-ttu-id="c758e-234">アセンブリの長い説明。</span><span class="sxs-lookup"><span data-stu-id="c758e-234">A long description for the assembly.</span></span> <span data-ttu-id="c758e-235">`PackageDescription` が指定されていない場合、このプロパティはパッケージの説明としても使用されます。</span><span class="sxs-lookup"><span data-stu-id="c758e-235">If `PackageDescription` is not specified then this property is also used as the description of the package.</span></span>

### <a name="copyright"></a><span data-ttu-id="c758e-236">Copyright</span><span class="sxs-lookup"><span data-stu-id="c758e-236">Copyright</span></span>
<span data-ttu-id="c758e-237">パッケージの著作権の詳細。</span><span class="sxs-lookup"><span data-stu-id="c758e-237">Copyright details for the package.</span></span>

### <a name="packagerequirelicenseacceptance"></a><span data-ttu-id="c758e-238">PackageRequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="c758e-238">PackageRequireLicenseAcceptance</span></span>
<span data-ttu-id="c758e-239">クライアントがユーザーに対して、パッケージのインストール前にパッケージ ライセンスに同意することを必須にするかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="c758e-239">A Boolean value that specifies whether the client must prompt the consumer to accept the package license before installing the package.</span></span> <span data-ttu-id="c758e-240">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="c758e-240">The default is `false`.</span></span>

### <a name="packagelicenseexpression"></a><span data-ttu-id="c758e-241">PackageLicenseExpression</span><span class="sxs-lookup"><span data-stu-id="c758e-241">PackageLicenseExpression</span></span>

<span data-ttu-id="c758e-242">パッケージ内のライセンス ファイルに対する SPDX ライセンス式またはパスであり、UI 表示や nuget.org でよく示されます。</span><span class="sxs-lookup"><span data-stu-id="c758e-242">An SPDX license expression or path to a license file within the package, often shown in UI displays as well as nuget.org.</span></span>

<span data-ttu-id="c758e-243">[SPDX ライセンス識別子](https://spdx.org/licenses/)の完全な一覧はこちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c758e-243">Here is the complete list of [SPDX license identifiers](https://spdx.org/licenses/).</span></span> <span data-ttu-id="c758e-244">ライセンス タイプ式を使用する場合、NuGet.org では OSI または FSF で承認されたライセンスのみが受け付けられます。</span><span class="sxs-lookup"><span data-stu-id="c758e-244">NuGet.org accepts only OSI or FSF approved licenses when using license type expression.</span></span>

<span data-ttu-id="c758e-245">ライセンス式の正確な構文については、[ABNF](https://tools.ietf.org/html/rfc5234) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c758e-245">The exact syntax of the license expressions is described below in [ABNF](https://tools.ietf.org/html/rfc5234).</span></span>
```cli
license-id            = <short form license identifier from https://spdx.org/spdx-specification-21-web-version#h.luq9dgcle9mo>

license-exception-id  = <short form license exception identifier from https://spdx.org/spdx-specification-21-web-version#h.ruv3yl8g6czd>

simple-expression = license-id / license-id”+”

compound-expression =  1*1(simple-expression /
                simple-expression "WITH" license-exception-id /
                compound-expression "AND" compound-expression /
                compound-expression "OR" compound-expression ) /                
                "(" compound-expression ")" )

license-expression =  1*1(simple-expression / compound-expression / UNLICENSED)
```

> [!NOTE]
> <span data-ttu-id="c758e-246">一度に指定できるのは、`PackageLicenseExpression`、`PackageLicenseFile`、`PackageLicenseUrl` のどれか 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="c758e-246">Only one of `PackageLicenseExpression`, `PackageLicenseFile` and `PackageLicenseUrl` can be specified at a time.</span></span>

### <a name="packagelicensefile"></a><span data-ttu-id="c758e-247">PackageLicenseFile</span><span class="sxs-lookup"><span data-stu-id="c758e-247">PackageLicenseFile</span></span>

<span data-ttu-id="c758e-248">SPDX 識別子が割り当てられていないライセンス、またはカスタム ライセンスを使用している場合、パッケージ内のライセンス ファイルへのパス (それ以外の場合は、`PackageLicenseExpression` が優先されます)</span><span class="sxs-lookup"><span data-stu-id="c758e-248">Path to a license file within the package if you are using a license that hasn’t been assigned an SPDX identifier, or it is a custom license (Otherwise `PackageLicenseExpression` is prefered)</span></span>

> [!NOTE]
> <span data-ttu-id="c758e-249">一度に指定できるのは、`PackageLicenseExpression`、`PackageLicenseFile`、`PackageLicenseUrl` のどれか 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="c758e-249">Only one of `PackageLicenseExpression`, `PackageLicenseFile` and `PackageLicenseUrl` can be specified at a time.</span></span>

### <a name="packagelicenseurl"></a><span data-ttu-id="c758e-250">PackageLicenseUrl</span><span class="sxs-lookup"><span data-stu-id="c758e-250">PackageLicenseUrl</span></span>

<span data-ttu-id="c758e-251">パッケージに適用されるライセンスの URL。</span><span class="sxs-lookup"><span data-stu-id="c758e-251">An URL to the license that is applicable to the package.</span></span> <span data-ttu-id="c758e-252">("_Visual Studio 15.9.4、.NET SDK 2.1.502 および 2.2.101 以降では非推奨_")</span><span class="sxs-lookup"><span data-stu-id="c758e-252">(_deprecated since Visual Studio 15.9.4, .NET SDK 2.1.502 and 2.2.101_)</span></span>

### <a name="packagelicenseexpression"></a><span data-ttu-id="c758e-253">PackageLicenseExpression</span><span class="sxs-lookup"><span data-stu-id="c758e-253">PackageLicenseExpression</span></span>

<span data-ttu-id="c758e-254">[SPDX ライセンス識別子](https://spdx.org/licenses/)または式 (つまり`Apache-2.0`)。</span><span class="sxs-lookup"><span data-stu-id="c758e-254">An [SPDX license identifier](https://spdx.org/licenses/) or expression, i.e. `Apache-2.0`.</span></span>

<span data-ttu-id="c758e-255">`PackageLicenseUrl` を置き換えるもので、`PackageLicenseFile` と組み合わせることはできず、Visual Studio 15.9.4、.NET SDK 2.1.502 または 2.2.101 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="c758e-255">Replaces `PackageLicenseUrl`, can't be combined with `PackageLicenseFile` and requires Visual Studio 15.9.4, .NET SDK 2.1.502 or 2.2.101, or newer.</span></span>

### <a name="packagelicensefile"></a><span data-ttu-id="c758e-256">PackageLicenseFile</span><span class="sxs-lookup"><span data-stu-id="c758e-256">PackageLicenseFile</span></span>

<span data-ttu-id="c758e-257">プロジェクト ファイルを基準とするディスク上のライセンス ファイルへのパス (つまり `LICENSE.txt`)。</span><span class="sxs-lookup"><span data-stu-id="c758e-257">A path to the license file on disk, relative to the project file, i.e. `LICENSE.txt`.</span></span>

<span data-ttu-id="c758e-258">`PackageLicenseUrl` を置き換えるもので、`PackageLicenseExpression` と組み合わせることはできず、Visual Studio 15.9.4、.NET SDK 2.1.502 または 2.2.101 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="c758e-258">Replaces `PackageLicenseUrl`, can't be combined with `PackageLicenseExpression` and requires Visual Studio 15.9.4, .NET SDK 2.1.502 or 2.2.101, or newer.</span></span>

<span data-ttu-id="c758e-259">プロジェクトに明示的に追加することによって、ライセンス ファイルをパックする必要があります。使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c758e-259">You will need to ensure the license file is packed by adding it explicitly to the project, example usage:</span></span>
```xml
<PropertyGroup>
  <PackageLicenseFile>LICENSE.txt</PackageLicenseFile>
</PropertyGroup>
<ItemGroup>
  <None Include="licenses\LICENSE.txt" Pack="true" PackagePath="$(PackageLicenseFile)"/>
</ItemGroup>
```
### <a name="packageiconurl"></a><span data-ttu-id="c758e-260">PackageIconUrl</span><span class="sxs-lookup"><span data-stu-id="c758e-260">PackageIconUrl</span></span>
<span data-ttu-id="c758e-261">UI 画面のパッケージのアイコンとして使用する背景が透明な 64x64 の画像の URL。</span><span class="sxs-lookup"><span data-stu-id="c758e-261">A URL for a 64x64 image with transparent background to use as the icon for the package in UI display.</span></span>

### <a name="packagereleasenotes"></a><span data-ttu-id="c758e-262">PackageReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="c758e-262">PackageReleaseNotes</span></span>
<span data-ttu-id="c758e-263">パッケージのリリース ノート。</span><span class="sxs-lookup"><span data-stu-id="c758e-263">Release notes for the package.</span></span>

### <a name="packagetags"></a><span data-ttu-id="c758e-264">PackageTags</span><span class="sxs-lookup"><span data-stu-id="c758e-264">PackageTags</span></span>
<span data-ttu-id="c758e-265">パッケージを指定するタグのセミコロン区切りの一覧。</span><span class="sxs-lookup"><span data-stu-id="c758e-265">A semicolon-delimited list of tags that designates the package.</span></span>

### <a name="packageoutputpath"></a><span data-ttu-id="c758e-266">PackageOutputPath</span><span class="sxs-lookup"><span data-stu-id="c758e-266">PackageOutputPath</span></span>
<span data-ttu-id="c758e-267">パックされたパッケージをドロップする出力パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-267">Determines the output path in which the packed package will be dropped.</span></span> <span data-ttu-id="c758e-268">既定値は `$(OutputPath)` です。</span><span class="sxs-lookup"><span data-stu-id="c758e-268">Default is `$(OutputPath)`.</span></span> 

### <a name="includesymbols"></a><span data-ttu-id="c758e-269">IncludeSymbols</span><span class="sxs-lookup"><span data-stu-id="c758e-269">IncludeSymbols</span></span>
<span data-ttu-id="c758e-270">このブール値は、プロジェクトをパックするときに、パッケージが追加のシンボル パッケージを作成するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-270">This Boolean value indicates whether the package should create an additional symbols package when the project is packed.</span></span> <span data-ttu-id="c758e-271">このパッケージの拡張子は *.symbols.nupkg* になります。DLL や他の出力ファイルと共に PDF ファイルがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="c758e-271">This package will have a *.symbols.nupkg* extension and will copy the PDB files along with the DLL and other output files.</span></span>

### <a name="includesource"></a><span data-ttu-id="c758e-272">IncludeSource</span><span class="sxs-lookup"><span data-stu-id="c758e-272">IncludeSource</span></span>
<span data-ttu-id="c758e-273">このブール値は、パック プロセスでソース パッケージを作成するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c758e-273">This Boolean value indicates whether the pack process should create a source package.</span></span> <span data-ttu-id="c758e-274">ソース パッケージには、ライブラリのソース コードと PDB ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c758e-274">The source package contains the library's source code as well as PDB files.</span></span> <span data-ttu-id="c758e-275">ソース ファイルは、結果のパッケージ ファイルの `src/ProjectName` ディレクトリに置かれます。</span><span class="sxs-lookup"><span data-stu-id="c758e-275">Source files are put under the `src/ProjectName` directory in the resulting package file.</span></span> 

### <a name="istool"></a><span data-ttu-id="c758e-276">IsTool</span><span class="sxs-lookup"><span data-stu-id="c758e-276">IsTool</span></span>
<span data-ttu-id="c758e-277">すべての出力ファイルを *lib* フォルダーではなく *tools* フォルダーにコピーするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-277">Specifies whether all output files are copied to the *tools* folder instead of the *lib* folder.</span></span> <span data-ttu-id="c758e-278">*.csproj* ファイルに `PackageType` を設定することで指定される `DotNetCliTool` とは異なります。</span><span class="sxs-lookup"><span data-stu-id="c758e-278">Note that this is different from a `DotNetCliTool` which is specified by setting the `PackageType` in the *.csproj* file.</span></span>

### <a name="repositoryurl"></a><span data-ttu-id="c758e-279">RepositoryUrl</span><span class="sxs-lookup"><span data-stu-id="c758e-279">RepositoryUrl</span></span>
<span data-ttu-id="c758e-280">パッケージのソース コードがある、またはビルド元のリポジトリの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-280">Specifies the URL for the repository where the source code for the package resides and/or from which it's being built.</span></span> 

### <a name="repositorytype"></a><span data-ttu-id="c758e-281">RepositoryType</span><span class="sxs-lookup"><span data-stu-id="c758e-281">RepositoryType</span></span>
<span data-ttu-id="c758e-282">リポジトリの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-282">Specifies the type of the repository.</span></span> <span data-ttu-id="c758e-283">既定値は "git" です。</span><span class="sxs-lookup"><span data-stu-id="c758e-283">Default is "git".</span></span> 

### <a name="nopackageanalysis"></a><span data-ttu-id="c758e-284">NoPackageAnalysis</span><span class="sxs-lookup"><span data-stu-id="c758e-284">NoPackageAnalysis</span></span>
<span data-ttu-id="c758e-285">パッケージのビルド後に、パックでパッケージの分析を実行しないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-285">Specifies that pack should not run package analysis after building the package.</span></span>

### <a name="minclientversion"></a><span data-ttu-id="c758e-286">MinClientVersion</span><span class="sxs-lookup"><span data-stu-id="c758e-286">MinClientVersion</span></span>
<span data-ttu-id="c758e-287">nuget.exe および Visual Studio パッケージ マネージャーで強制する、このパッケージをインストールできる NuGet クライアントの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-287">Specifies the minimum version of the NuGet client that can install this package, enforced by nuget.exe and the Visual Studio Package Manager.</span></span>

### <a name="includebuildoutput"></a><span data-ttu-id="c758e-288">IncludeBuildOutput</span><span class="sxs-lookup"><span data-stu-id="c758e-288">IncludeBuildOutput</span></span>
<span data-ttu-id="c758e-289">このブール値は、ビルド出力アセンブリを *.nupkg* ファイルにパックするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-289">This Boolean values specifies whether the build output assemblies should be packed into the *.nupkg* file or not.</span></span>

### <a name="includecontentinpack"></a><span data-ttu-id="c758e-290">IncludeContentInPack</span><span class="sxs-lookup"><span data-stu-id="c758e-290">IncludeContentInPack</span></span>
<span data-ttu-id="c758e-291">このブール値は、種類が `Content` の項目を結果のパッケージに自動的に含めるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-291">This Boolean value specifies whether any items that have a type of `Content` will be included in the resulting package automatically.</span></span> <span data-ttu-id="c758e-292">既定値は、`true` です。</span><span class="sxs-lookup"><span data-stu-id="c758e-292">The default is `true`.</span></span> 

### <a name="buildoutputtargetfolder"></a><span data-ttu-id="c758e-293">BuildOutputTargetFolder</span><span class="sxs-lookup"><span data-stu-id="c758e-293">BuildOutputTargetFolder</span></span>
<span data-ttu-id="c758e-294">出力アセンブリを配置するフォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-294">Specifies the folder where to place the output assemblies.</span></span> <span data-ttu-id="c758e-295">出力アセンブリ (および他の出力ファイル) は、各フレームワーク フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="c758e-295">The output assemblies (and other output files) are copied into their respective framework folders.</span></span>

### <a name="contenttargetfolders"></a><span data-ttu-id="c758e-296">ContentTargetFolders</span><span class="sxs-lookup"><span data-stu-id="c758e-296">ContentTargetFolders</span></span>
<span data-ttu-id="c758e-297">このプロパティには、`PackagePath` が指定されていない場合に、すべてのコンテンツ ファイルを配置する既定の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="c758e-297">This property specifies the default location of where all the content files should go if `PackagePath` is not specified for them.</span></span> <span data-ttu-id="c758e-298">既定値は "content;contentFiles" です。</span><span class="sxs-lookup"><span data-stu-id="c758e-298">The default value is "content;contentFiles".</span></span>

### <a name="nuspecfile"></a><span data-ttu-id="c758e-299">NuspecFile</span><span class="sxs-lookup"><span data-stu-id="c758e-299">NuspecFile</span></span>
<span data-ttu-id="c758e-300">パックに使用する *.nuspec* ファイルの相対パスまたは絶対パス。</span><span class="sxs-lookup"><span data-stu-id="c758e-300">Relative or absolute path to the *.nuspec* file being used for packing.</span></span> 

> [!NOTE]
> <span data-ttu-id="c758e-301">*.nuspec* ファイルを指定すると、情報のパッケージに**のみ**使用され、プロジェクト内の情報は使用されません。</span><span class="sxs-lookup"><span data-stu-id="c758e-301">If the *.nuspec* file is specified, it's used **exclusively** for packaging information and any information in the projects is not used.</span></span> 

### <a name="nuspecbasepath"></a><span data-ttu-id="c758e-302">NuspecBasePath</span><span class="sxs-lookup"><span data-stu-id="c758e-302">NuspecBasePath</span></span>
<span data-ttu-id="c758e-303">*.nuspec* ファイルのベース パス。</span><span class="sxs-lookup"><span data-stu-id="c758e-303">Base path for the *.nuspec* file.</span></span>

### <a name="nuspecproperties"></a><span data-ttu-id="c758e-304">NuspecProperties</span><span class="sxs-lookup"><span data-stu-id="c758e-304">NuspecProperties</span></span>
<span data-ttu-id="c758e-305">キー=値ペアのセミコロン区切りの一覧。</span><span class="sxs-lookup"><span data-stu-id="c758e-305">Semicolon separated list of key=value pairs.</span></span>

## <a name="assemblyinfo-properties"></a><span data-ttu-id="c758e-306">AssemblyInfo プロパティ</span><span class="sxs-lookup"><span data-stu-id="c758e-306">AssemblyInfo properties</span></span>
<span data-ttu-id="c758e-307">通常、*AssemblyInfo* ファイル内に存在していた[アセンブリ属性](../../framework/app-domains/set-assembly-attributes.md)は、プロパティから自動的に生成されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c758e-307">[Assembly attributes](../../framework/app-domains/set-assembly-attributes.md) that were typically present in an *AssemblyInfo* file are now automatically generated from properties.</span></span>

### <a name="properties-per-attribute"></a><span data-ttu-id="c758e-308">属性ごとのプロパティ</span><span class="sxs-lookup"><span data-stu-id="c758e-308">Properties per attribute</span></span>

<span data-ttu-id="c758e-309">次の表に示すように、各属性にはコンテンツを制御するプロパティと生成を無効にするプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="c758e-309">Each attribute has a property that control its content and another to disable its generation as shown in the following table:</span></span>

| <span data-ttu-id="c758e-310">属性</span><span class="sxs-lookup"><span data-stu-id="c758e-310">Attribute</span></span>                                                      | <span data-ttu-id="c758e-311">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c758e-311">Property</span></span>               | <span data-ttu-id="c758e-312">無効にするプロパティ</span><span class="sxs-lookup"><span data-stu-id="c758e-312">Property to disable</span></span>                             |
|----------------------------------------------------------------|------------------------|-------------------------------------------------|
| <xref:System.Reflection.AssemblyCompanyAttribute>              | `Company`              | `GenerateAssemblyCompanyAttribute`              |
| <xref:System.Reflection.AssemblyConfigurationAttribute>        | `Configuration`        | `GenerateAssemblyConfigurationAttribute`        |
| <xref:System.Reflection.AssemblyCopyrightAttribute>            | `Copyright`            | `GenerateAssemblyCopyrightAttribute`            |
| <xref:System.Reflection.AssemblyDescriptionAttribute>          | `Description`          | `GenerateAssemblyDescriptionAttribute`          |
| <xref:System.Reflection.AssemblyFileVersionAttribute>          | `FileVersion`          | `GenerateAssemblyFileVersionAttribute`          |
| <xref:System.Reflection.AssemblyInformationalVersionAttribute> | `InformationalVersion` | `GenerateAssemblyInformationalVersionAttribute` |
| <xref:System.Reflection.AssemblyProductAttribute>              | `Product`              | `GenerateAssemblyProductAttribute`              |
| <xref:System.Reflection.AssemblyTitleAttribute>                | `AssemblyTitle`        | `GenerateAssemblyTitleAttribute`                |
| <xref:System.Reflection.AssemblyVersionAttribute>              | `AssemblyVersion`      | `GenerateAssemblyVersionAttribute`              |
| <xref:System.Resources.NeutralResourcesLanguageAttribute>      | `NeutralLanguage`      | `GenerateNeutralResourcesLanguageAttribute`     |

<span data-ttu-id="c758e-313">メモ:</span><span class="sxs-lookup"><span data-stu-id="c758e-313">Notes:</span></span>

* <span data-ttu-id="c758e-314">`AssemblyVersion` と `FileVersion` の既定値は、サフィックスなしで `$(Version)` の値を受け取ることです。</span><span class="sxs-lookup"><span data-stu-id="c758e-314">`AssemblyVersion` and `FileVersion` default is to take the value of `$(Version)` without suffix.</span></span> <span data-ttu-id="c758e-315">たとえば、`$(Version)` が `1.2.3-beta.4` の場合、値は `1.2.3` です。</span><span class="sxs-lookup"><span data-stu-id="c758e-315">For example, if `$(Version)` is `1.2.3-beta.4`, then the value would be `1.2.3`.</span></span>
* <span data-ttu-id="c758e-316">`InformationalVersion` の既定値は、`$(Version)` の値です。</span><span class="sxs-lookup"><span data-stu-id="c758e-316">`InformationalVersion` defaults to the value of `$(Version)`.</span></span>
* <span data-ttu-id="c758e-317">プロパティが存在する場合、`InformationalVersion` の末尾には `$(SourceRevisionId)` が付加されます。</span><span class="sxs-lookup"><span data-stu-id="c758e-317">`InformationalVersion` has `$(SourceRevisionId)` appended if the property is present.</span></span> <span data-ttu-id="c758e-318">`IncludeSourceRevisionInInformationalVersion` を使用して無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c758e-318">It can be disabled using `IncludeSourceRevisionInInformationalVersion`.</span></span>
* <span data-ttu-id="c758e-319">NuGet メタデータには、`Copyright` および `Description` プロパティも使用されます。</span><span class="sxs-lookup"><span data-stu-id="c758e-319">`Copyright` and `Description` properties are also used for NuGet metadata.</span></span>
* <span data-ttu-id="c758e-320">`Configuration` はすべてのビルド プロセスで共有され、設定には `dotnet` コマンドの`--configuration` パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c758e-320">`Configuration` is shared with all the build process and set via the `--configuration` parameter of `dotnet` commands.</span></span>

### <a name="generateassemblyinfo"></a><span data-ttu-id="c758e-321">GenerateAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="c758e-321">GenerateAssemblyInfo</span></span> 
<span data-ttu-id="c758e-322">すべての AssemblyInfo 生成を有効または無効にするブール値。</span><span class="sxs-lookup"><span data-stu-id="c758e-322">A Boolean that enable or disable all the AssemblyInfo generation.</span></span> <span data-ttu-id="c758e-323">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="c758e-323">The default value is `true`.</span></span> 

### <a name="generatedassemblyinfofile"></a><span data-ttu-id="c758e-324">GeneratedAssemblyInfoFile</span><span class="sxs-lookup"><span data-stu-id="c758e-324">GeneratedAssemblyInfoFile</span></span> 
<span data-ttu-id="c758e-325">生成されたアセンブリ情報ファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="c758e-325">The path of the generated assembly info file.</span></span> <span data-ttu-id="c758e-326">既定値は `$(IntermediateOutputPath)` (obj) ディレクトリ内のファイルです。</span><span class="sxs-lookup"><span data-stu-id="c758e-326">Default to a file in the `$(IntermediateOutputPath)` (obj) directory.</span></span>
