---
title: .NET Core の csproj 形式に追加されたもの
description: 既存の csproj ファイルと .NET Core の csproj ファイルの違いについて説明します
ms.date: 04/08/2019
ms.openlocfilehash: fadc6de43f522129970e48bc72914cf187fe3f82
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607707"
---
# <a name="additions-to-the-csproj-format-for-net-core"></a><span data-ttu-id="d8b1f-103">.NET Core の csproj 形式に追加されたもの</span><span class="sxs-lookup"><span data-stu-id="d8b1f-103">Additions to the csproj format for .NET Core</span></span>

<span data-ttu-id="d8b1f-104">ここでは、*project.json* から *csproj* および [MSBuild](https://github.com/Microsoft/MSBuild) への移行に伴ってプロジェクト ファイルに追加された変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-104">This document outlines the changes that were added to the project files as part of the move from *project.json* to *csproj* and [MSBuild](https://github.com/Microsoft/MSBuild).</span></span> <span data-ttu-id="d8b1f-105">一般的なプロジェクト ファイルの構文とリファレンスの詳細については、[MSBuild プロジェクト ファイル](/visualstudio/msbuild/msbuild-project-file-schema-reference)のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-105">For more information about general project file syntax and reference, see [the MSBuild project file](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation.</span></span>

## <a name="implicit-package-references"></a><span data-ttu-id="d8b1f-106">暗黙的なパッケージ参照</span><span class="sxs-lookup"><span data-stu-id="d8b1f-106">Implicit package references</span></span>

<span data-ttu-id="d8b1f-107">メタパッケージは、プロジェクト ファイルの `<TargetFramework>` または `<TargetFrameworks>` プロパティに指定されている対象フレームワークに基づいて暗黙的に参照されています。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-107">Metapackages are implicitly referenced based on the target framework(s) specified in the `<TargetFramework>` or `<TargetFrameworks>` property of your project file.</span></span> <span data-ttu-id="d8b1f-108">`<TargetFramework>` を指定すると、順序に関係なく `<TargetFrameworks>` は無視されます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-108">`<TargetFrameworks>` is ignored if `<TargetFramework>` is specified, independent of order.</span></span> <span data-ttu-id="d8b1f-109">詳細については、「[パッケージ、メタパッケージ、フレームワーク](../packages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-109">For more information, see [Packages, metapackages, and frameworks](../packages.md).</span></span>

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

### <a name="recommendations"></a><span data-ttu-id="d8b1f-110">推奨事項</span><span class="sxs-lookup"><span data-stu-id="d8b1f-110">Recommendations</span></span>

<span data-ttu-id="d8b1f-111">`Microsoft.NETCore.App` または `NETStandard.Library` メタパッケージは暗黙的に参照されるので、ベスト プラクティスとして以下が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-111">Since `Microsoft.NETCore.App` or `NETStandard.Library` metapackages are implicitly referenced, the following are our recommended best practices:</span></span>

- <span data-ttu-id="d8b1f-112">.NET Core または .NET Standard を対象とするとき、プロジェクト ファイルの `<PackageReference>` アイテム経由で `Microsoft.NETCore.App` または `NETStandard.Library` メタパッケージを明示的に参照しないようにします。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-112">When targeting .NET Core or .NET Standard, never have an explicit reference to the `Microsoft.NETCore.App` or `NETStandard.Library` metapackages via a `<PackageReference>` item in your project file.</span></span>
- <span data-ttu-id="d8b1f-113">.NET Core を対象にするとき、特定バージョンのランタイムが必要な場合、メタパッケージを参照するのではなく、プロジェクト内で `<RuntimeFrameworkVersion>` プロパティを使用します (`1.0.4` など)。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-113">If you need a specific version of the runtime when targeting .NET Core, you should use the `<RuntimeFrameworkVersion>` property in your project (for example, `1.0.4`) instead of referencing the metapackage.</span></span>
  - <span data-ttu-id="d8b1f-114">[自己完結型の展開](../deploying/index.md#publish-self-contained)を使用し、特定のパッチ バージョンの 1.0.0 LTS ランタイムが必要な場合などにこの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-114">This might happen if you are using [self-contained deployments](../deploying/index.md#publish-self-contained) and you need a specific patch version of 1.0.0 LTS runtime, for example.</span></span>
- <span data-ttu-id="d8b1f-115">.NET Standard を対象にするとき、特定バージョンの `NETStandard.Library` メタパッケージが必要な場合、`<NetStandardImplicitPackageVersion>` プロパティを使用し、必要なバージョンを設定できます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-115">If you need a specific version of the `NETStandard.Library` metapackage when targeting .NET Standard, you can use the `<NetStandardImplicitPackageVersion>` property and set the version you need.</span></span>
- <span data-ttu-id="d8b1f-116">.NET Framework プロジェクトでは、`Microsoft.NETCore.App` または `NETStandard.Library` メタパッケージに参照を明示的に追加したり、更新したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-116">Don't explicitly add or update references to either the `Microsoft.NETCore.App` or `NETStandard.Library` metapackage in .NET Framework projects.</span></span> <span data-ttu-id="d8b1f-117">.NET Standard ベースの NuGet パッケージを使用するとき、何らかのバージョンの `NETStandard.Library` が必要であれば、NuGet はそのバージョンを自動的にインストールします。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-117">If any version of `NETStandard.Library` is needed when using a .NET Standard-based NuGet package, NuGet automatically installs that version.</span></span>

## <a name="implicit-version-for-some-package-references"></a><span data-ttu-id="d8b1f-118">一部のパッケージ参照に対する暗黙的なバージョン</span><span class="sxs-lookup"><span data-stu-id="d8b1f-118">Implicit version for some package references</span></span>

<span data-ttu-id="d8b1f-119">[`<PackageReference>`](#packagereference) を使用するほとんどの場合に、`Version` 属性を設定して、使用する NuGet パッケージのバージョンを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-119">Most usages of [`<PackageReference>`](#packagereference) require setting the `Version` attribute to specify the NuGet package version to be used.</span></span> <span data-ttu-id="d8b1f-120">ただし、.NET Core 2.1 または 2.2 を使用し、[Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage-app) または [Microsoft.AspNetCore.All](/aspnet/core/fundamentals/metapackage) を参照するときは、その属性は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-120">When using .NET Core 2.1 or 2.2 and referencing [Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage-app) or [Microsoft.AspNetCore.All](/aspnet/core/fundamentals/metapackage), however, the  attribute is unnecessary.</span></span> <span data-ttu-id="d8b1f-121">.NET Core SDK では、使用する必要があるこれらのパッケージのバージョンを自動的に選択できます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-121">The .NET Core SDK can automatically select the version of these packages that should be used.</span></span>

### <a name="recommendation"></a><span data-ttu-id="d8b1f-122">推奨事項</span><span class="sxs-lookup"><span data-stu-id="d8b1f-122">Recommendation</span></span>

<span data-ttu-id="d8b1f-123">`Microsoft.AspNetCore.App` または `Microsoft.AspNetCore.All` パッケージを参照するときは、それらのバージョンを指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-123">When referencing the `Microsoft.AspNetCore.App` or `Microsoft.AspNetCore.All` packages, do not specify their version.</span></span> <span data-ttu-id="d8b1f-124">バージョンを指定すると、SDK で警告 NETSDK1071 が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-124">If a version is specified, the SDK may produce warning NETSDK1071.</span></span> <span data-ttu-id="d8b1f-125">この警告を解決するには、次の例のようなパッケージのバージョンを削除します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-125">To fix this warning, remove the package version like in the following example:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.AspNetCore.App" />
</ItemGroup>
```

> <span data-ttu-id="d8b1f-126">既知の問題: .NET Core 2.1 SDK では、プロジェクトでも Microsoft.NET.Sdk.Web が使用されている場合にのみ、この構文がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-126">Known issue: the .NET Core 2.1 SDK only supported this syntax when the project also uses Microsoft.NET.Sdk.Web.</span></span> <span data-ttu-id="d8b1f-127">これは、.NET Core 2.2 SDK で解決されます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-127">This is resolved in the .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="d8b1f-128">ASP.NET Core メタパッケージに対するこれらの参照では、ほとんどの通常の NuGet パッケージとは動作が若干異なります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-128">These references to ASP.NET Core metapackages have a slightly different behavior from most normal NuGet packages.</span></span> <span data-ttu-id="d8b1f-129">これらのメタパッケージを使用するアプリケーションの[フレームワーク依存の展開](../deploying/index.md#publish-runtime-dependent)では、ASP.NET Core 共有フレームワークが自動的に利用されます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-129">[Framework-dependent deployments](../deploying/index.md#publish-runtime-dependent) of applications that use these metapackages automatically take advantage of the ASP.NET Core shared framework.</span></span> <span data-ttu-id="d8b1f-130">メタパッケージを使用する場合、参照される ASP.NET Core NuGet パッケージの資産は、アプリケーションと共に展開**されません**。ASP.NET Core 共有フレームワークにはこれらの資産が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-130">When you use the metapackages, **no** assets from the referenced ASP.NET Core NuGet packages are deployed with the application—the ASP.NET Core shared framework contains these assets.</span></span> <span data-ttu-id="d8b1f-131">共有フレームワーク内の資産は、アプリケーションの起動時間を向上させるため、ターゲット プラットフォームに対して最適化されています。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-131">The assets in the shared framework are optimized for the target platform to improve application startup time.</span></span> <span data-ttu-id="d8b1f-132">共有フレームワークについて詳しくは、「[.NET Core の配布パッケージ](../distribution-packaging.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-132">For more information about shared framework, see [.NET Core distribution packaging](../distribution-packaging.md).</span></span>

<span data-ttu-id="d8b1f-133">バージョンを "*指定する*" と、フレームワーク依存の展開では ASP.NET Core の共有フレームワークの "*最小*" バージョンとして扱われ、自己完結型の展開では "*厳密な*" バージョンとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-133">If a version *is* specified, it's treated as the *minimum* version of ASP.NET Core shared framework for framework-dependent deployments and as an *exact* version for self-contained deployments.</span></span> <span data-ttu-id="d8b1f-134">これには、次のような影響があります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-134">This can have the following consequences:</span></span>

- <span data-ttu-id="d8b1f-135">サーバーにインストールされている ASP.NET Core のバージョンが、PackageReference で指定されているバージョンより小さい場合、.NET Core プロセスの起動は失敗します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-135">If the version of ASP.NET Core installed on the server is less than the version specified on the PackageReference, the .NET Core process fails to launch.</span></span> <span data-ttu-id="d8b1f-136">Azure などのホスティング環境でメタパッケージの更新プログラムが使用できるようになる前に、NuGet.org で更新プログラムが利用可能になることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-136">Updates to the metapackage are often available on NuGet.org before updates have been made available in hosting environments such as Azure.</span></span> <span data-ttu-id="d8b1f-137">PackageReference でのバージョンを ASP.NET Core に更新すると、展開されているアプリケーションが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-137">Updating the version on the PackageReference to ASP.NET Core could cause a deployed application to fail.</span></span>
- <span data-ttu-id="d8b1f-138">アプリケーションが[自己完結型の展開](../deploying/index.md#publish-self-contained)として展開されている場合、アプリケーションに .NET Core の最新のセキュリティ更新プログラムが含まれていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-138">If the application is deployed as a [self-contained deployment](../deploying/index.md#publish-self-contained), the application may not contain the latest security updates to .NET Core.</span></span> <span data-ttu-id="d8b1f-139">バージョンを指定しないと、SDK は自己完結型の展開に ASP.NET Core の最新バージョンを自動的に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-139">When a version isn't specified, the SDK can automatically include the newest version of ASP.NET Core in the self-contained deployment.</span></span>

## <a name="default-compilation-includes-in-net-core-projects"></a><span data-ttu-id="d8b1f-140">.NET Core プロジェクトの既定のコンパイルの include</span><span class="sxs-lookup"><span data-stu-id="d8b1f-140">Default compilation includes in .NET Core projects</span></span>

<span data-ttu-id="d8b1f-141">最新バージョンの SDK の *csproj* 形式に移行すると共に、コンパイル項目と、SDK プロパティ ファイルに埋め込みリソースの既定の include と exclude を SDK プロパティ ファイルに移行しました。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-141">With the move to the *csproj* format in the latest SDK versions, we've moved the default includes and excludes for compile items and embedded resources to the SDK properties files.</span></span> <span data-ttu-id="d8b1f-142">つまり、これらの項目をプロジェクト ファイルに指定する必要はなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-142">This means that you no longer need to specify these items in your project file.</span></span>

<span data-ttu-id="d8b1f-143">これを行う主な理由は、プロジェクト ファイルを見やすくするためです。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-143">The main reason for doing this is to reduce the clutter in your project file.</span></span> <span data-ttu-id="d8b1f-144">SDK の既定値は、最も一般的な使用例に対応しているので、作成するプロジェクトごとに繰り返す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-144">The defaults that are present in the SDK should cover most common use cases, so there is no need to repeat them in every project that you create.</span></span> <span data-ttu-id="d8b1f-145">その結果、プロジェクト ファイルが小さくなり、わかりやすく、編集が必要な場合に編集しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-145">This leads to smaller project files that are much easier to understand as well as edit by hand, if needed.</span></span>

<span data-ttu-id="d8b1f-146">次の表は、SDK に含まれる、および除外される要素と [glob](https://en.wikipedia.org/wiki/Glob_(programming)) の一覧です。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-146">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are both included and excluded in the SDK:</span></span>

| <span data-ttu-id="d8b1f-147">要素</span><span class="sxs-lookup"><span data-stu-id="d8b1f-147">Element</span></span>           | <span data-ttu-id="d8b1f-148">含まれる glob</span><span class="sxs-lookup"><span data-stu-id="d8b1f-148">Include glob</span></span>                              | <span data-ttu-id="d8b1f-149">除外される glob</span><span class="sxs-lookup"><span data-stu-id="d8b1f-149">Exclude glob</span></span>                                                  | <span data-ttu-id="d8b1f-150">glob の削除</span><span class="sxs-lookup"><span data-stu-id="d8b1f-150">Remove glob</span></span>              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| <span data-ttu-id="d8b1f-151">Compile</span><span class="sxs-lookup"><span data-stu-id="d8b1f-151">Compile</span></span>           | <span data-ttu-id="d8b1f-152">\*\*/\*.cs (または他の言語拡張機能)</span><span class="sxs-lookup"><span data-stu-id="d8b1f-152">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="d8b1f-153">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="d8b1f-153">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="d8b1f-154">N/A</span><span class="sxs-lookup"><span data-stu-id="d8b1f-154">N/A</span></span>                      |
| <span data-ttu-id="d8b1f-155">EmbeddedResource</span><span class="sxs-lookup"><span data-stu-id="d8b1f-155">EmbeddedResource</span></span>  | <span data-ttu-id="d8b1f-156">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="d8b1f-156">\*\*/\*.resx</span></span>                              | <span data-ttu-id="d8b1f-157">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="d8b1f-157">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="d8b1f-158">N/A</span><span class="sxs-lookup"><span data-stu-id="d8b1f-158">N/A</span></span>                      |
| <span data-ttu-id="d8b1f-159">None</span><span class="sxs-lookup"><span data-stu-id="d8b1f-159">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="d8b1f-160">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="d8b1f-160">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="d8b1f-161">\*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="d8b1f-161">\*\*/\*.cs; \*\*/\*.resx</span></span>   |

> [!NOTE]
> <span data-ttu-id="d8b1f-162">**除外される glob** では、`./bin` と `./obj` フォルダーが常に除外されます。これらはそれぞれ MSBuild プロパティ `$(BaseOutputPath)` と `$(BaseIntermediateOutputPath)` で表されます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-162">**Exclude glob** always excludes the `./bin` and `./obj` folders, which are represented by the `$(BaseOutputPath)` and `$(BaseIntermediateOutputPath)` MSBuild properties, respectively.</span></span> <span data-ttu-id="d8b1f-163">全体として、すべての除外は `$(DefaultItemExcludes)` で表されます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-163">As a whole, all excludes are represented by `$(DefaultItemExcludes)`.</span></span>

<span data-ttu-id="d8b1f-164">プロジェクトに glob があり、最新の SDK を使用してビルドしようとすると、次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-164">If you have globs in your project and you try to build it using the newest SDK, you'll get the following error:</span></span>

> <span data-ttu-id="d8b1f-165">重複するコンパイル項目が含まれていました。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-165">Duplicate Compile items were included.</span></span> <span data-ttu-id="d8b1f-166">.NET SDK には、既定でプロジェクト ディレクトリのコンパイル項目が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-166">The .NET SDK includes Compile items from your project directory by default.</span></span> <span data-ttu-id="d8b1f-167">これらの項目をプロジェクト ファイルから削除するか、プロジェクト ファイルに明示的に含める場合は 'EnableDefaultCompileItems' プロパティを 'false' に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-167">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span>

<span data-ttu-id="d8b1f-168">このエラーを回避するには、前の表にあるものと一致する明示的な `Compile` 項目を削除するか、次のように `<EnableDefaultCompileItems>` プロパティを `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-168">In order to get around this error, you can either remove the explicit `Compile` items that match the ones listed on the previous table, or you can set the `<EnableDefaultCompileItems>` property to `false`, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

<span data-ttu-id="d8b1f-169">このプロパティを `false` に設定すると、暗黙的に含める動作が無効になり、以前の SDK の動作に戻り、プロジェクトに既定の glob が指定されます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-169">Setting this property to `false` will disable implicit inclusion, reverting to the behavior of previous SDKs where you had to specify the default globs in your project.</span></span>

<span data-ttu-id="d8b1f-170">この変更で、他の include の主なしくみは変わりません。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-170">This change does not modify the main mechanics of other includes.</span></span> <span data-ttu-id="d8b1f-171">ただし、たとえばアプリで発行する一部のファイルを指定する場合は、*csproj* で既知のしくみ (たとえば `<Content>` 要素) を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-171">However, if you wish to specify, for example, some files to get published with your app, you can still use the known mechanisms in *csproj* for that (for example, the `<Content>` element).</span></span>

<span data-ttu-id="d8b1f-172">`<EnableDefaultCompileItems>` は `Compile` glob のみを無効にし、\*.cs 項目にも適用される暗黙的 `None` glob など、他の Glob には影響しません。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-172">`<EnableDefaultCompileItems>` only disables `Compile` globs but doesn't affect other globs, like the implicit `None` glob, which also applies to \*.cs items.</span></span> <span data-ttu-id="d8b1f-173">そのため、**ソリューション エクスプローラー**は \*.cs 項目を `None` 項目として含まれた、プロジェクトの一部として引き続き表示します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-173">Because of that, **Solution Explorer** will continue show \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="d8b1f-174">同様に、次のように `<EnableDefaultNoneItems>` を false に設定し、暗黙的 `None` glob を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-174">In a similar way, you can set `<EnableDefaultNoneItems>` to false to disable the implicit `None` glob, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

<span data-ttu-id="d8b1f-175">**暗黙的 glob をすべて**無効にするには、`<EnableDefaultItems>` プロパティを `false` に設定します。次の例をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-175">To disable **all implicit globs**, you can set the `<EnableDefaultItems>` property to `false` as in the following example:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a><span data-ttu-id="d8b1f-176">MSBuild と同じようにプロジェクト全体を表示する方法</span><span class="sxs-lookup"><span data-stu-id="d8b1f-176">How to see the whole project as MSBuild sees it</span></span>

<span data-ttu-id="d8b1f-177">これらの csproj 変更でプロジェクト ファイルが大幅に簡素化されますが、SDK とそのターゲットが追加されたとき、MSBuild と同様にプロジェクト全体を表示すると便利なことがあります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-177">While those csproj changes greatly simplify project files, you might want to see the fully expanded project as MSBuild sees it once the SDK and its targets are included.</span></span> <span data-ttu-id="d8b1f-178">[`dotnet msbuild`](dotnet-msbuild.md) コマンドの [`/pp` スイッチ](/visualstudio/msbuild/msbuild-command-line-reference#preprocess)でプロジェクトを事前処理します。インポートされるファイル、そのソース、ビルドに対するその貢献が、実際にプロジェクトをビルドすることなく、表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-178">Preprocess the project with [the `/pp` switch](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) of the [`dotnet msbuild`](dotnet-msbuild.md) command, which shows which files are imported, their sources, and their contributions to the build without actually building the project:</span></span>

`dotnet msbuild -pp:fullproject.xml`

<span data-ttu-id="d8b1f-179">プロジェクトにターゲット フレームワークが複数存在する場合、MSBuild プロパティとして指定し、1 つだけにコマンドの結果を集中させてください。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-179">If the project has multiple target frameworks, the results of the command should be focused on only one of them by specifying it as an MSBuild property:</span></span>

`dotnet msbuild -p:TargetFramework=netcoreapp2.0 -pp:fullproject.xml`

## <a name="additions"></a><span data-ttu-id="d8b1f-180">追加</span><span class="sxs-lookup"><span data-stu-id="d8b1f-180">Additions</span></span>

### <a name="sdk-attribute"></a><span data-ttu-id="d8b1f-181">SDK 属性</span><span class="sxs-lookup"><span data-stu-id="d8b1f-181">Sdk attribute</span></span>

<span data-ttu-id="d8b1f-182">*.csproj* ファイルのルート `<Project>` 要素には、`Sdk` という新しい属性があります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-182">The root `<Project>` element of the *.csproj* file has a new attribute called `Sdk`.</span></span> <span data-ttu-id="d8b1f-183">`Sdk` は、プロジェクトで使用される SDK を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-183">`Sdk` specifies which SDK will be used by the project.</span></span> <span data-ttu-id="d8b1f-184">[レイヤー化のドキュメント](cli-msbuild-architecture.md)で説明されているように、SDK は、.NET Core コードをビルドできる MSBuild [タスク](/visualstudio/msbuild/msbuild-tasks)および[ターゲット](/visualstudio/msbuild/msbuild-targets)のセットです。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-184">The SDK, as the [layering document](cli-msbuild-architecture.md) describes, is a set of MSBuild [tasks](/visualstudio/msbuild/msbuild-tasks) and [targets](/visualstudio/msbuild/msbuild-targets) that can build .NET Core code.</span></span> <span data-ttu-id="d8b1f-185">.NET Core では、次の SDK を利用できます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-185">The following SDKs are available for .NET Core:</span></span>

1. <span data-ttu-id="d8b1f-186">ID が `Microsoft.NET.Sdk` の .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="d8b1f-186">The .NET Core SDK with the ID of `Microsoft.NET.Sdk`</span></span>
2. <span data-ttu-id="d8b1f-187">ID が `Microsoft.NET.Sdk.Web` の .NET Core Web SDK</span><span class="sxs-lookup"><span data-stu-id="d8b1f-187">The .NET Core web SDK with the ID of `Microsoft.NET.Sdk.Web`</span></span>
3. <span data-ttu-id="d8b1f-188">ID が `Microsoft.NET.Sdk.Razor` の .NET Core Razor クラス ライブラリ SDK</span><span class="sxs-lookup"><span data-stu-id="d8b1f-188">The .NET Core Razor Class Library SDK with the ID of `Microsoft.NET.Sdk.Razor`</span></span>
4. <span data-ttu-id="d8b1f-189">ID が `Microsoft.NET.Sdk.Worker` の .NET Core Worker Service (.NET Core 3.0 以降)</span><span class="sxs-lookup"><span data-stu-id="d8b1f-189">The .NET Core Worker Service with the ID of `Microsoft.NET.Sdk.Worker` (since .NET Core 3.0)</span></span>
5. <span data-ttu-id="d8b1f-190">ID が `Microsoft.NET.Sdk.WindowsDesktop` の .NET Core WinForms および WPF (.NET Core 3.0 以降)</span><span class="sxs-lookup"><span data-stu-id="d8b1f-190">The .NET Core WinForms and WPF with the ID of `Microsoft.NET.Sdk.WindowsDesktop` (since .NET Core 3.0)</span></span>

<span data-ttu-id="d8b1f-191">.NET Core ツールを使用し、コードをビルドするには、`Sdk` 属性を `<Project>` 要素の ID のいずれかに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-191">You need to have the `Sdk` attribute set to one of those IDs on the `<Project>` element in order to use the .NET Core tools and build your code.</span></span>

### <a name="packagereference"></a><span data-ttu-id="d8b1f-192">PackageReference</span><span class="sxs-lookup"><span data-stu-id="d8b1f-192">PackageReference</span></span>

<span data-ttu-id="d8b1f-193">`<PackageReference>` 項目要素では、[プロジェクトでの NuGet の依存関係](/nuget/consume-packages/package-references-in-project-files)を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-193">A `<PackageReference>` item element specifies a [NuGet dependency in the project](/nuget/consume-packages/package-references-in-project-files).</span></span> <span data-ttu-id="d8b1f-194">`Include` 属性は、パッケージ ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-194">The `Include` attribute specifies the package ID.</span></span>

```xml
<PackageReference Include="package-id" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a><span data-ttu-id="d8b1f-195">バージョン</span><span class="sxs-lookup"><span data-stu-id="d8b1f-195">Version</span></span>

<span data-ttu-id="d8b1f-196">必須の `Version` 属性では、復元するパッケージのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-196">The required `Version` attribute specifies the version of the package to restore.</span></span> <span data-ttu-id="d8b1f-197">この属性は、[NuGet バージョンの範囲](/nuget/concepts/package-versioning#version-ranges)スキームの規則に従います。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-197">The attribute respects the rules of the [NuGet version range](/nuget/concepts/package-versioning#version-ranges) scheme.</span></span> <span data-ttu-id="d8b1f-198">既定の動作は、最小一致バージョンです。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-198">The default behavior is a minimum version, inclusive match.</span></span> <span data-ttu-id="d8b1f-199">たとえば、`Version="1.2.3"` を指定すると、NuGet 表記の `[1.2.3, )` と同等になります。つまり、パッケージのバージョンは、使用できる場合は 1.2.3 になり、使用できない場合はその後のバージョンになります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-199">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3, )` and means the resolved package will have the version 1.2.3 if available or greater otherwise.</span></span>

#### <a name="includeassets-excludeassets-and-privateassets"></a><span data-ttu-id="d8b1f-200">IncludeAssets、ExcludeAssets、PrivateAssets</span><span class="sxs-lookup"><span data-stu-id="d8b1f-200">IncludeAssets, ExcludeAssets, and PrivateAssets</span></span>

<span data-ttu-id="d8b1f-201">`IncludeAssets` 属性は、`<PackageReference>` で指定されているパッケージに属するアセットのうち、使う必要があるものを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-201">`IncludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> <span data-ttu-id="d8b1f-202">既定では、パッケージのすべてのアセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-202">By default, all package assets are included.</span></span>

<span data-ttu-id="d8b1f-203">`ExcludeAssets` 属性は、`<PackageReference>` で指定されているパッケージに属するアセットのうち、使う必要がないものを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-203">`ExcludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span>

<span data-ttu-id="d8b1f-204">`PrivateAssets` 属性は、`<PackageReference>` で指定されているパッケージに属するアセットで、使う必要はあるが、次のプロジェクトに渡してはならないものを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-204">`PrivateAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed but not flow to the next project.</span></span> <span data-ttu-id="d8b1f-205">この属性が存在しない場合、`Analyzers`、`Build`、`ContentFiles` アセットは既定でプライベートになります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-205">The `Analyzers`, `Build` and `ContentFiles` assets are private by default when this attribute is not present.</span></span>

> [!NOTE]
> <span data-ttu-id="d8b1f-206">`PrivateAssets` は *project.json*/*xproj* `SuppressParent` 要素と同等です。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-206">`PrivateAssets` is equivalent to the *project.json*/*xproj* `SuppressParent` element.</span></span>

<span data-ttu-id="d8b1f-207">これらの属性には以下の項目を 1 つ以上含めることができ、複数ある場合はセミコロン `;` 文字で区切ります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-207">These attributes can contain one or more of the following items, separated by the semicolon `;` character if more than one is listed:</span></span>

- <span data-ttu-id="d8b1f-208">`Compile` - コンパイルで使用できる *lib* フォルダーの内容です。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-208">`Compile` – the contents of the *lib* folder are available to compile against.</span></span>
- <span data-ttu-id="d8b1f-209">`Runtime` - 配布する *runtime* フォルダーの内容です。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-209">`Runtime` – the contents of the *runtime* folder are distributed.</span></span>
- <span data-ttu-id="d8b1f-210">`ContentFiles` - 使用する *contentfiles* フォルダーの内容です。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-210">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
- <span data-ttu-id="d8b1f-211">`Build` - 使用する *build* フォルダーのプロパティ/ターゲットです。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-211">`Build` – the props/targets in the *build* folder are used.</span></span>
- <span data-ttu-id="d8b1f-212">`Native` - ランタイムの *output* フォルダーにコピーするネイティブ アセットの内容です。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-212">`Native` – the contents from native assets are copied to the *output* folder for runtime.</span></span>
- <span data-ttu-id="d8b1f-213">`Analyzers` - アナライザーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-213">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="d8b1f-214">代わりに、次の値を属性に含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-214">Alternatively, the attribute can contain:</span></span>

- <span data-ttu-id="d8b1f-215">`None` - いずれのアセットも使用されません。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-215">`None` – none of the assets are used.</span></span>
- <span data-ttu-id="d8b1f-216">`All` - すべてのアセットが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-216">`All` – all assets are used.</span></span>

### <a name="dotnetclitoolreference"></a><span data-ttu-id="d8b1f-217">DotNetCliToolReference</span><span class="sxs-lookup"><span data-stu-id="d8b1f-217">DotNetCliToolReference</span></span>

<span data-ttu-id="d8b1f-218">`<DotNetCliToolReference>` 項目要素は、プロジェクトのコンテキストでユーザーが復元を望む CLI ツールを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-218">A `<DotNetCliToolReference>` item element specifies the CLI tool that the user wants to restore in the context of the project.</span></span> <span data-ttu-id="d8b1f-219">*project.json* の `tools` ノードに代わるものです。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-219">It's a replacement for the `tools` node in *project.json*.</span></span>

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

<span data-ttu-id="d8b1f-220">`DotNetCliToolReference` は[現在非推奨であり](https://github.com/dotnet/announcements/issues/107)、[.NET Core Local Tools](https://aka.ms/local-tools) の使用が推奨されています。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-220">Note that `DotNetCliToolReference` is [now deprecated](https://github.com/dotnet/announcements/issues/107) in favor of [.NET Core Local Tools](https://aka.ms/local-tools).</span></span>

#### <a name="version"></a><span data-ttu-id="d8b1f-221">バージョン</span><span class="sxs-lookup"><span data-stu-id="d8b1f-221">Version</span></span>

<span data-ttu-id="d8b1f-222">`Version` は、復元するパッケージのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-222">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="d8b1f-223">この属性は、[NuGet バージョン管理](/nuget/create-packages/dependency-versions#version-ranges)スキームの規則に従います。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-223">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="d8b1f-224">既定の動作は、最小一致バージョンです。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-224">The default behavior is a minimum version, inclusive match.</span></span> <span data-ttu-id="d8b1f-225">たとえば、`Version="1.2.3"` を指定すると、NuGet 表記の `[1.2.3, )` と同等になります。つまり、パッケージのバージョンは、使用できる場合は 1.2.3 になり、使用できない場合はその後のバージョンになります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-225">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3, )` and means the resolved package will have the version 1.2.3 if available or greater otherwise.</span></span>

### <a name="runtimeidentifiers"></a><span data-ttu-id="d8b1f-226">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="d8b1f-226">RuntimeIdentifiers</span></span>

<span data-ttu-id="d8b1f-227">`<RuntimeIdentifiers>` プロパティ要素では、プロジェクトの[ランタイム識別子 (RID)](../rid-catalog.md) のセミコロン区切りリストを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-227">The `<RuntimeIdentifiers>` property element lets you specify a semicolon-delimited list of [Runtime Identifiers (RIDs)](../rid-catalog.md) for the project.</span></span>
<span data-ttu-id="d8b1f-228">RID により、自己完結型の展開を発行できます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-228">RIDs enable publishing self-contained deployments.</span></span>

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a><span data-ttu-id="d8b1f-229">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="d8b1f-229">RuntimeIdentifier</span></span>

<span data-ttu-id="d8b1f-230">`<RuntimeIdentifier>` プロパティ要素では、プロジェクトの[ランタイム識別子 (RID)](../rid-catalog.md) を 1 つだけ指定できます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-230">The `<RuntimeIdentifier>` property element allows you to specify only one [Runtime Identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="d8b1f-231">RID により、自己完結型の展開を発行できます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-231">The RID enables publishing a self-contained deployment.</span></span>

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

<span data-ttu-id="d8b1f-232">複数のランタイムに対して発行する必要がある場合、代わりに `<RuntimeIdentifiers>` (複数) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-232">Use `<RuntimeIdentifiers>` (plural) instead if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="d8b1f-233">`<RuntimeIdentifier>` では、必要なランタイムが 1 つだけのとき、ビルドが速くなります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-233">`<RuntimeIdentifier>` can provide faster builds when only a single runtime is required.</span></span>

### <a name="packagetargetfallback"></a><span data-ttu-id="d8b1f-234">PackageTargetFallback</span><span class="sxs-lookup"><span data-stu-id="d8b1f-234">PackageTargetFallback</span></span>

<span data-ttu-id="d8b1f-235">`<PackageTargetFallback>` プロパティ要素では、パッケージの復元時に使用する、互換性のある一連のターゲットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-235">The `<PackageTargetFallback>` property element allows you to specify a set of compatible targets to be used when restoring packages.</span></span> <span data-ttu-id="d8b1f-236">dotnet [TxM (Target x Moniker)](/nuget/schema/target-frameworks) を使用するパッケージに、dotnet TxM を宣言しないパッケージで動作することを許可するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-236">It's designed to allow packages that use the dotnet [TxM (Target x Moniker)](/nuget/schema/target-frameworks) to operate with packages that don't declare a dotnet TxM.</span></span> <span data-ttu-id="d8b1f-237">プロジェクトで dotnet TxM を使用せず、依存するすべてのパッケージに dotnet TxM を与える必要がある場合、非 dotnet プラットフォームを dotnet 対応にするためにプロジェクトに `<PackageTargetFallback>` を追加します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-237">If your project uses the dotnet TxM, then all the packages it depends on must also have a dotnet TxM, unless you add the `<PackageTargetFallback>` to your project in order to allow non-dotnet platforms to be compatible with dotnet.</span></span>

<span data-ttu-id="d8b1f-238">次の例では、プロジェクトのすべてのターゲットにフォールバックを提供しています。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-238">The following example provides the fallbacks for all targets in your project:</span></span>

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

<span data-ttu-id="d8b1f-239">次の例では、`netcoreapp2.1` ターゲットにのみフォールバックを指定しています。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-239">The following example specifies the fallbacks only for the `netcoreapp2.1` target:</span></span>

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp2.1'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="build-events"></a><span data-ttu-id="d8b1f-240">ビルド イベント</span><span class="sxs-lookup"><span data-stu-id="d8b1f-240">Build events</span></span>

<span data-ttu-id="d8b1f-241">プロジェクト ファイルでビルド前およびビルド後のイベントを指定する方法が変更されました。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-241">The way that pre-build and post-build events are specified in the project file has changed.</span></span> <span data-ttu-id="d8b1f-242">$ (ProjectDir) などのマクロが解決されないため、PreBuildEvent および PostBuildEvent プロパティは SDK スタイルのプロジェクト形式では推奨されません。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-242">The properties PreBuildEvent and PostBuildEvent are not recommended in the SDK-style project format, because macros such as $(ProjectDir) are not resolved.</span></span> <span data-ttu-id="d8b1f-243">たとえば、次のコードはサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-243">For example, the following code is no longer supported:</span></span>

```xml
<PropertyGroup>
    <PreBuildEvent>"$(ProjectDir)PreBuildEvent.bat" "$(ProjectDir)..\" "$(ProjectDir)" "$(TargetDir)"</PreBuildEvent>
</PropertyGroup>
```

<span data-ttu-id="d8b1f-244">SDK スタイルのプロジェクトでは、`PreBuild` または `PostBuild` という名前の MSBuild ターゲットを使用し、`PreBuild` の `BeforeTargets` プロパティまたは `AfterTargets` の `PostBuild` プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-244">In SDK-style projects, use an MSBuild target named `PreBuild` or `PostBuild` and set the `BeforeTargets` property for `PreBuild` or the `AfterTargets` property for `PostBuild`.</span></span> <span data-ttu-id="d8b1f-245">前の例では、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-245">For the preceding example, use the following code:</span></span>

```xml
<Target Name="PreBuild" BeforeTargets="PreBuildEvent">
    <Exec Command="&quot;$(ProjectDir)PreBuildEvent.bat&quot; &quot;$(ProjectDir)..\&quot; &quot;$(ProjectDir)&quot; &quot;$(TargetDir)&quot;" />
</Target>

<Target Name="PostBuild" AfterTargets="PostBuildEvent">
   <Exec Command="echo Output written to $(TargetDir)" />
</Target>
```

> [!NOTE]
><span data-ttu-id="d8b1f-246">MSBuild ターゲットには任意の名前を使用できますが、Visual Studio IDE では `PreBuild` と `PostBuild` ターゲットが認識されるため、Visual Studio IDE でコマンドを編集できるようにするには、これらの名前を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-246">You can use any name for the MSBuild targets, but the Visual Studio IDE recognizes `PreBuild` and `PostBuild` targets, so we recommend using those names so that you can edit the commands in the Visual Studio IDE.</span></span>

## <a name="nuget-metadata-properties"></a><span data-ttu-id="d8b1f-247">NuGet メタデータ プロパティ</span><span class="sxs-lookup"><span data-stu-id="d8b1f-247">NuGet metadata properties</span></span>

<span data-ttu-id="d8b1f-248">MSBuild への移行に伴い、*project.json* ファイルから *csproj* ファイルに NuGet パッケージをパックするときに使用される入力メタデータを移動しました。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-248">With the move to MSBuild, we have moved the input metadata that is used when packing a NuGet package from *project.json* to *.csproj* files.</span></span> <span data-ttu-id="d8b1f-249">入力は MSBuild プロパティなので、`<PropertyGroup>` グループ内で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-249">The inputs are MSBuild properties so they have to go within a `<PropertyGroup>` group.</span></span> <span data-ttu-id="d8b1f-250">次に示すのは、`dotnet pack` コマンドまたは SDK の一部である `Pack` MSBuild ターゲットを使用するときに、パッキング プロセスへの入力として使用されるプロパティの一覧です。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-250">The following is the list of properties that are used as inputs to the packing process when using the `dotnet pack` command or the `Pack` MSBuild target that is part of the SDK:</span></span>

### <a name="ispackable"></a><span data-ttu-id="d8b1f-251">IsPackable</span><span class="sxs-lookup"><span data-stu-id="d8b1f-251">IsPackable</span></span>

<span data-ttu-id="d8b1f-252">プロジェクトをパックできるかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-252">A Boolean value that specifies whether the project can be packed.</span></span> <span data-ttu-id="d8b1f-253">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-253">The default value is `true`.</span></span>

### <a name="packageversion"></a><span data-ttu-id="d8b1f-254">PackageVersion</span><span class="sxs-lookup"><span data-stu-id="d8b1f-254">PackageVersion</span></span>

<span data-ttu-id="d8b1f-255">結果のパッケージのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-255">Specifies the version that the resulting package will have.</span></span> <span data-ttu-id="d8b1f-256">すべてのフォームの NuGet バージョン文字列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-256">Accepts all forms of NuGet version string.</span></span> <span data-ttu-id="d8b1f-257">既定値は `$(Version)` です。つまり、プロジェクトのプロパティ `Version` の値です。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-257">Default is the value of `$(Version)`, that is, of the property `Version` in the project.</span></span>

### <a name="packageid"></a><span data-ttu-id="d8b1f-258">PackageId</span><span class="sxs-lookup"><span data-stu-id="d8b1f-258">PackageId</span></span>

<span data-ttu-id="d8b1f-259">結果のパッケージの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-259">Specifies the name for the resulting package.</span></span> <span data-ttu-id="d8b1f-260">指定しない場合、`pack` 操作の既定では、`AssemblyName` またはディレクトリ名をパッケージ名として使用します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-260">If not specified, the `pack` operation will default to using the `AssemblyName` or directory name as the name of the package.</span></span>

### <a name="title"></a><span data-ttu-id="d8b1f-261">Title</span><span class="sxs-lookup"><span data-stu-id="d8b1f-261">Title</span></span>

<span data-ttu-id="d8b1f-262">人が読みやすいパッケージのタイトル。通常、nuget.org と、Visual Studio のパッケージ マネージャーの UI 画面で使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-262">A human-friendly title of the package, typically used in UI displays as on nuget.org and the Package Manager in Visual Studio.</span></span> <span data-ttu-id="d8b1f-263">指定しない場合、パッケージ ID が代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-263">If not specified, the package ID is used instead.</span></span>

### <a name="authors"></a><span data-ttu-id="d8b1f-264">Authors</span><span class="sxs-lookup"><span data-stu-id="d8b1f-264">Authors</span></span>

<span data-ttu-id="d8b1f-265">nuget.org のプロファイル名と一致するパッケージ作成者をセミコロンで区切った一覧。これらは nuget.org の NuGet ギャラリーに表示され、同じ作成者によるパッケージの相互参照に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-265">A semicolon-separated list of packages authors, matching the profile names on nuget.org. These are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span>

### <a name="packagedescription"></a><span data-ttu-id="d8b1f-266">PackageDescription</span><span class="sxs-lookup"><span data-stu-id="d8b1f-266">PackageDescription</span></span>

<span data-ttu-id="d8b1f-267">UI 画面用のパッケージの長い説明。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-267">A long description of the package for UI display.</span></span>

### <a name="description"></a><span data-ttu-id="d8b1f-268">説明</span><span class="sxs-lookup"><span data-stu-id="d8b1f-268">Description</span></span>

<span data-ttu-id="d8b1f-269">アセンブリの長い説明。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-269">A long description for the assembly.</span></span> <span data-ttu-id="d8b1f-270">`PackageDescription` が指定されていない場合、このプロパティはパッケージの説明としても使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-270">If `PackageDescription` is not specified, then this property is also used as the description of the package.</span></span>

### <a name="copyright"></a><span data-ttu-id="d8b1f-271">Copyright</span><span class="sxs-lookup"><span data-stu-id="d8b1f-271">Copyright</span></span>

<span data-ttu-id="d8b1f-272">パッケージの著作権の詳細。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-272">Copyright details for the package.</span></span>

### <a name="packagerequirelicenseacceptance"></a><span data-ttu-id="d8b1f-273">PackageRequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="d8b1f-273">PackageRequireLicenseAcceptance</span></span>

<span data-ttu-id="d8b1f-274">クライアントがユーザーに対して、パッケージのインストール前にパッケージ ライセンスに同意することを必須にするかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-274">A Boolean value that specifies whether the client must prompt the consumer to accept the package license before installing the package.</span></span> <span data-ttu-id="d8b1f-275">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-275">The default is `false`.</span></span>

### <a name="developmentdependency"></a><span data-ttu-id="d8b1f-276">DevelopmentDependency</span><span class="sxs-lookup"><span data-stu-id="d8b1f-276">DevelopmentDependency</span></span>

<span data-ttu-id="d8b1f-277">開発専用の依存関係としてパッケージをマークするかどうかを指定するブール値。指定すると、そのパッケージは他のパッケージに依存関係として含まれなくなります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-277">A Boolean value that specifies whether the package is marked as a development-only dependency, which prevents the package from being included as a dependency in other packages.</span></span> <span data-ttu-id="d8b1f-278">PackageReference (NuGet 4.8 以降) では、このフラグは、コンパイルからコンパイル時アセットが除外されることも意味します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-278">With PackageReference (NuGet 4.8+), this flag also means that compile-time assets are excluded from compilation.</span></span> <span data-ttu-id="d8b1f-279">詳しくは、「[DevelopmentDependency support for PackageReference (PackageReference に対する DevelopmentDependency のサポート)](https://github.com/NuGet/Home/wiki/DevelopmentDependency-support-for-PackageReference)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-279">For more information, see [DevelopmentDependency support for PackageReference](https://github.com/NuGet/Home/wiki/DevelopmentDependency-support-for-PackageReference).</span></span>

### <a name="packagelicenseexpression"></a><span data-ttu-id="d8b1f-280">PackageLicenseExpression</span><span class="sxs-lookup"><span data-stu-id="d8b1f-280">PackageLicenseExpression</span></span>

<span data-ttu-id="d8b1f-281">[SPDX ライセンス識別子](https://spdx.org/licenses/)、または式です。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-281">An [SPDX license identifier](https://spdx.org/licenses/) or expression.</span></span> <span data-ttu-id="d8b1f-282">たとえば、`Apache-2.0` のようにします。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-282">For example, `Apache-2.0`.</span></span>

<span data-ttu-id="d8b1f-283">[SPDX ライセンス識別子](https://spdx.org/licenses/)の完全な一覧はこちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-283">Here is the complete list of [SPDX license identifiers](https://spdx.org/licenses/).</span></span> <span data-ttu-id="d8b1f-284">ライセンス タイプ式を使用する場合、NuGet.org では OSI または FSF で承認されたライセンスのみが受け付けられます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-284">NuGet.org accepts only OSI or FSF approved licenses when using license type expression.</span></span>

<span data-ttu-id="d8b1f-285">ライセンス式の正確な構文については、[ABNF](https://tools.ietf.org/html/rfc5234) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-285">The exact syntax of the license expressions is described below in [ABNF](https://tools.ietf.org/html/rfc5234).</span></span>

```abnf
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
> <span data-ttu-id="d8b1f-286">一度に指定できるのは、`PackageLicenseExpression`、`PackageLicenseFile`、`PackageLicenseUrl` のどれか 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-286">Only one of `PackageLicenseExpression`, `PackageLicenseFile` and `PackageLicenseUrl` can be specified at a time.</span></span>

### <a name="packagelicensefile"></a><span data-ttu-id="d8b1f-287">PackageLicenseFile</span><span class="sxs-lookup"><span data-stu-id="d8b1f-287">PackageLicenseFile</span></span>

<span data-ttu-id="d8b1f-288">SPDX 識別子が割り当てられていないライセンス、またはカスタム ライセンスを使用している場合、パッケージ内のライセンス ファイルへのパス (それ以外の場合は、`PackageLicenseExpression` が優先されます)</span><span class="sxs-lookup"><span data-stu-id="d8b1f-288">Path to a license file within the package if you are using a license that hasn’t been assigned an SPDX identifier, or it is a custom license (Otherwise `PackageLicenseExpression` is preferred)</span></span>

<span data-ttu-id="d8b1f-289">`PackageLicenseUrl` が置き換えられ、`PackageLicenseExpression` と組み合わせることはできず、Visual Studio バージョン 15.9.4 および.NET SDK 2.1.502 または 2.2.101 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-289">Replaces `PackageLicenseUrl`, can't be combined with `PackageLicenseExpression`, and requires Visual Studio version 15.9.4 and .NET SDK 2.1.502 or 2.2.101 or newer.</span></span>

<span data-ttu-id="d8b1f-290">プロジェクトに明示的に追加することによって、ライセンス ファイルをパックする必要があります。使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-290">You will need to ensure the license file is packed by adding it explicitly to the project, example usage:</span></span>

```xml
<PropertyGroup>
  <PackageLicenseFile>LICENSE.txt</PackageLicenseFile>
</PropertyGroup>
<ItemGroup>
  <None Include="licenses\LICENSE.txt" Pack="true" PackagePath="$(PackageLicenseFile)"/>
</ItemGroup>
```

### <a name="packagelicenseurl"></a><span data-ttu-id="d8b1f-291">PackageLicenseUrl</span><span class="sxs-lookup"><span data-stu-id="d8b1f-291">PackageLicenseUrl</span></span>

<span data-ttu-id="d8b1f-292">パッケージに適用されるライセンスの URL。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-292">A URL to the license that is applicable to the package.</span></span> <span data-ttu-id="d8b1f-293">("_Visual Studio 15.9.4、.NET SDK 2.1.502 および 2.2.101 以降では非推奨_")</span><span class="sxs-lookup"><span data-stu-id="d8b1f-293">(_deprecated since Visual Studio 15.9.4, .NET SDK 2.1.502 and 2.2.101_)</span></span>

### <a name="packageiconurl"></a><span data-ttu-id="d8b1f-294">PackageIconUrl</span><span class="sxs-lookup"><span data-stu-id="d8b1f-294">PackageIconUrl</span></span>

<span data-ttu-id="d8b1f-295">UI 画面のパッケージのアイコンとして使用する背景が透明な 64x64 の画像の URL。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-295">A URL for a 64x64 image with transparent background to use as the icon for the package in UI display.</span></span>

### <a name="packagereleasenotes"></a><span data-ttu-id="d8b1f-296">PackageReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="d8b1f-296">PackageReleaseNotes</span></span>

<span data-ttu-id="d8b1f-297">パッケージのリリース ノート。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-297">Release notes for the package.</span></span>

### <a name="packagetags"></a><span data-ttu-id="d8b1f-298">PackageTags</span><span class="sxs-lookup"><span data-stu-id="d8b1f-298">PackageTags</span></span>

<span data-ttu-id="d8b1f-299">パッケージを指定するタグのセミコロン区切りの一覧。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-299">A semicolon-delimited list of tags that designates the package.</span></span>

### <a name="packageoutputpath"></a><span data-ttu-id="d8b1f-300">PackageOutputPath</span><span class="sxs-lookup"><span data-stu-id="d8b1f-300">PackageOutputPath</span></span>

<span data-ttu-id="d8b1f-301">パックされたパッケージをドロップする出力パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-301">Determines the output path in which the packed package will be dropped.</span></span> <span data-ttu-id="d8b1f-302">既定値は `$(OutputPath)` です。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-302">Default is `$(OutputPath)`.</span></span>

### <a name="includesymbols"></a><span data-ttu-id="d8b1f-303">IncludeSymbols</span><span class="sxs-lookup"><span data-stu-id="d8b1f-303">IncludeSymbols</span></span>
<span data-ttu-id="d8b1f-304">このブール値は、プロジェクトをパックするときに、パッケージが追加のシンボル パッケージを作成するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-304">This Boolean value indicates whether the package should create an additional symbols package when the project is packed.</span></span> <span data-ttu-id="d8b1f-305">シンボル パッケージの形式は、`SymbolPackageFormat` プロパティで制御します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-305">The symbols package's format is controlled by the `SymbolPackageFormat` property.</span></span>

### <a name="symbolpackageformat"></a><span data-ttu-id="d8b1f-306">SymbolPackageFormat</span><span class="sxs-lookup"><span data-stu-id="d8b1f-306">SymbolPackageFormat</span></span>
<span data-ttu-id="d8b1f-307">シンボル パッケージの形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-307">Specifies the format of the symbols package.</span></span> <span data-ttu-id="d8b1f-308">"symbols.nupkg" では、 *.symbols.nupkg* 拡張子と共に、PDB、DLL、およびその他の出力ファイルを含む従来のシンボル パッケージが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-308">If "symbols.nupkg", a legacy symbols package will be created with a *.symbols.nupkg* extension containing PDBs, DLLs, and other output files.</span></span> <span data-ttu-id="d8b1f-309">"snupkg" では、ポータブル PDB を含む snupkg シンボル パッケージが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-309">If "snupkg", a snupkg symbol package will be created containing the portable PDBs.</span></span> <span data-ttu-id="d8b1f-310">既定値は "symbols.nupkg" です。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-310">Default is "symbols.nupkg".</span></span>

### <a name="includesource"></a><span data-ttu-id="d8b1f-311">IncludeSource</span><span class="sxs-lookup"><span data-stu-id="d8b1f-311">IncludeSource</span></span>

<span data-ttu-id="d8b1f-312">このブール値は、パック プロセスでソース パッケージを作成するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-312">This Boolean value indicates whether the pack process should create a source package.</span></span> <span data-ttu-id="d8b1f-313">ソース パッケージには、ライブラリのソース コードと PDB ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-313">The source package contains the library's source code as well as PDB files.</span></span> <span data-ttu-id="d8b1f-314">ソース ファイルは、結果のパッケージ ファイルの `src/ProjectName` ディレクトリに置かれます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-314">Source files are put under the `src/ProjectName` directory in the resulting package file.</span></span>

### <a name="istool"></a><span data-ttu-id="d8b1f-315">IsTool</span><span class="sxs-lookup"><span data-stu-id="d8b1f-315">IsTool</span></span>

<span data-ttu-id="d8b1f-316">すべての出力ファイルを *lib* フォルダーではなく *tools* フォルダーにコピーするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-316">Specifies whether all output files are copied to the *tools* folder instead of the *lib* folder.</span></span> <span data-ttu-id="d8b1f-317">*.csproj* ファイルに `PackageType` を設定することで指定される `DotNetCliTool` とは異なります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-317">This is different from a `DotNetCliTool`, which is specified by setting the `PackageType` in the *.csproj* file.</span></span>

### <a name="repositoryurl"></a><span data-ttu-id="d8b1f-318">RepositoryUrl</span><span class="sxs-lookup"><span data-stu-id="d8b1f-318">RepositoryUrl</span></span>

<span data-ttu-id="d8b1f-319">パッケージのソース コードがある、またはビルド元のリポジトリの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-319">Specifies the URL for the repository where the source code for the package resides and/or from which it's being built.</span></span>

### <a name="repositorytype"></a><span data-ttu-id="d8b1f-320">RepositoryType</span><span class="sxs-lookup"><span data-stu-id="d8b1f-320">RepositoryType</span></span>

<span data-ttu-id="d8b1f-321">リポジトリの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-321">Specifies the type of the repository.</span></span> <span data-ttu-id="d8b1f-322">既定値は "git" です。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-322">Default is "git".</span></span>

### <a name="repositorybranch"></a><span data-ttu-id="d8b1f-323">RepositoryBranch</span><span class="sxs-lookup"><span data-stu-id="d8b1f-323">RepositoryBranch</span></span>
<span data-ttu-id="d8b1f-324">リポジトリ内のソース ブランチの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-324">Specifies the name of the source branch in the repository.</span></span> <span data-ttu-id="d8b1f-325">プロジェクトが NuGet パッケージにパッケージ化されると、パッケージ メタデータに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-325">When the project is packaged in a NuGet package, it's added to the package metadata.</span></span>

### <a name="repositorycommit"></a><span data-ttu-id="d8b1f-326">RepositoryCommit</span><span class="sxs-lookup"><span data-stu-id="d8b1f-326">RepositoryCommit</span></span>
<span data-ttu-id="d8b1f-327">任意のリポジトリ コミットまたは変更セット。パッケージがどのソースに対してビルドされたかを示します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-327">Optional repository commit or changeset to indicate which source the package was built against.</span></span> <span data-ttu-id="d8b1f-328">このプロパティを含めるには、`RepositoryUrl` も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-328">`RepositoryUrl` must also be specified for this property to be included.</span></span> <span data-ttu-id="d8b1f-329">プロジェクトが NuGet パッケージにパッケージ化されると、このコミットまたは変更セットがパッケージ メタデータに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-329">When the project is packaged in a NuGet package, this commit or changeset is added to the package metadata.</span></span>

### <a name="nopackageanalysis"></a><span data-ttu-id="d8b1f-330">NoPackageAnalysis</span><span class="sxs-lookup"><span data-stu-id="d8b1f-330">NoPackageAnalysis</span></span>

<span data-ttu-id="d8b1f-331">パッケージのビルド後に、パックでパッケージの分析を実行しないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-331">Specifies that pack should not run package analysis after building the package.</span></span>

### <a name="minclientversion"></a><span data-ttu-id="d8b1f-332">MinClientVersion</span><span class="sxs-lookup"><span data-stu-id="d8b1f-332">MinClientVersion</span></span>

<span data-ttu-id="d8b1f-333">nuget.exe および Visual Studio パッケージ マネージャーで強制する、このパッケージをインストールできる NuGet クライアントの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-333">Specifies the minimum version of the NuGet client that can install this package, enforced by nuget.exe and the Visual Studio Package Manager.</span></span>

### <a name="includebuildoutput"></a><span data-ttu-id="d8b1f-334">IncludeBuildOutput</span><span class="sxs-lookup"><span data-stu-id="d8b1f-334">IncludeBuildOutput</span></span>

<span data-ttu-id="d8b1f-335">このブール値は、ビルド出力アセンブリを *.nupkg* ファイルにパッケージ化するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-335">This Boolean value specifies whether the build output assemblies should be packed into the *.nupkg* file or not.</span></span>

### <a name="includecontentinpack"></a><span data-ttu-id="d8b1f-336">IncludeContentInPack</span><span class="sxs-lookup"><span data-stu-id="d8b1f-336">IncludeContentInPack</span></span>

<span data-ttu-id="d8b1f-337">このブール値は、種類が `Content` の項目を結果のパッケージに自動的に含めるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-337">This Boolean value specifies whether any items that have a type of `Content` will be included in the resulting package automatically.</span></span> <span data-ttu-id="d8b1f-338">既定値は、`true` です。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-338">The default is `true`.</span></span>

### <a name="buildoutputtargetfolder"></a><span data-ttu-id="d8b1f-339">BuildOutputTargetFolder</span><span class="sxs-lookup"><span data-stu-id="d8b1f-339">BuildOutputTargetFolder</span></span>

<span data-ttu-id="d8b1f-340">出力アセンブリを配置するフォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-340">Specifies the folder where to place the output assemblies.</span></span> <span data-ttu-id="d8b1f-341">出力アセンブリ (および他の出力ファイル) は、各フレームワーク フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-341">The output assemblies (and other output files) are copied into their respective framework folders.</span></span>

### <a name="contenttargetfolders"></a><span data-ttu-id="d8b1f-342">ContentTargetFolders</span><span class="sxs-lookup"><span data-stu-id="d8b1f-342">ContentTargetFolders</span></span>

<span data-ttu-id="d8b1f-343">このプロパティには、`PackagePath` が指定されていない場合に、すべてのコンテンツ ファイルを配置する既定の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-343">This property specifies the default location of where all the content files should go if `PackagePath` is not specified for them.</span></span> <span data-ttu-id="d8b1f-344">既定値は "content;contentFiles" です。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-344">The default value is "content;contentFiles".</span></span>

### <a name="nuspecfile"></a><span data-ttu-id="d8b1f-345">NuspecFile</span><span class="sxs-lookup"><span data-stu-id="d8b1f-345">NuspecFile</span></span>

<span data-ttu-id="d8b1f-346">パックに使用する *.nuspec* ファイルの相対パスまたは絶対パス。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-346">Relative or absolute path to the *.nuspec* file being used for packing.</span></span>

> [!NOTE]
> <span data-ttu-id="d8b1f-347">*.nuspec* ファイルを指定すると、情報のパッケージに**のみ**使用され、プロジェクト内の情報は使用されません。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-347">If the *.nuspec* file is specified, it's used **exclusively** for packaging information and any information in the projects is not used.</span></span>

### <a name="nuspecbasepath"></a><span data-ttu-id="d8b1f-348">NuspecBasePath</span><span class="sxs-lookup"><span data-stu-id="d8b1f-348">NuspecBasePath</span></span>

<span data-ttu-id="d8b1f-349">*.nuspec* ファイルのベース パス。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-349">Base path for the *.nuspec* file.</span></span>

### <a name="nuspecproperties"></a><span data-ttu-id="d8b1f-350">NuspecProperties</span><span class="sxs-lookup"><span data-stu-id="d8b1f-350">NuspecProperties</span></span>

<span data-ttu-id="d8b1f-351">キー=値ペアのセミコロン区切りの一覧。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-351">Semicolon separated list of key=value pairs.</span></span>

## <a name="assemblyinfo-properties"></a><span data-ttu-id="d8b1f-352">AssemblyInfo プロパティ</span><span class="sxs-lookup"><span data-stu-id="d8b1f-352">AssemblyInfo properties</span></span>

<span data-ttu-id="d8b1f-353">通常、*AssemblyInfo* ファイル内に存在していた[アセンブリ属性](../../standard/assembly/set-attributes.md)は、プロパティから自動的に生成されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-353">[Assembly attributes](../../standard/assembly/set-attributes.md) that were typically present in an *AssemblyInfo* file are now automatically generated from properties.</span></span>

### <a name="properties-per-attribute"></a><span data-ttu-id="d8b1f-354">属性ごとのプロパティ</span><span class="sxs-lookup"><span data-stu-id="d8b1f-354">Properties per attribute</span></span>

<span data-ttu-id="d8b1f-355">次の表に示すように、各属性にはその内容を制御するプロパティと、その生成を無効にするプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-355">As shown in the following table, each attribute has a property that controls its content and another that disables its generation:</span></span>

| <span data-ttu-id="d8b1f-356">属性</span><span class="sxs-lookup"><span data-stu-id="d8b1f-356">Attribute</span></span>                                                      | <span data-ttu-id="d8b1f-357">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d8b1f-357">Property</span></span>               | <span data-ttu-id="d8b1f-358">無効にするプロパティ</span><span class="sxs-lookup"><span data-stu-id="d8b1f-358">Property to disable</span></span>                             |
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

<span data-ttu-id="d8b1f-359">メモ:</span><span class="sxs-lookup"><span data-stu-id="d8b1f-359">Notes:</span></span>

- <span data-ttu-id="d8b1f-360">`AssemblyVersion` と `FileVersion` の既定値は、サフィックスなしで `$(Version)` の値を受け取ることです。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-360">`AssemblyVersion` and `FileVersion` default is to take the value of `$(Version)` without suffix.</span></span> <span data-ttu-id="d8b1f-361">たとえば、`$(Version)` が `1.2.3-beta.4` の場合、値は `1.2.3` です。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-361">For example, if `$(Version)` is `1.2.3-beta.4`, then the value would be `1.2.3`.</span></span>
- <span data-ttu-id="d8b1f-362">`InformationalVersion` の既定値は、`$(Version)` の値です。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-362">`InformationalVersion` defaults to the value of `$(Version)`.</span></span>
- <span data-ttu-id="d8b1f-363">プロパティが存在する場合、`InformationalVersion` の末尾には `$(SourceRevisionId)` が付加されます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-363">`InformationalVersion` has `$(SourceRevisionId)` appended if the property is present.</span></span> <span data-ttu-id="d8b1f-364">`IncludeSourceRevisionInInformationalVersion` を使用して無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-364">It can be disabled using `IncludeSourceRevisionInInformationalVersion`.</span></span>
- <span data-ttu-id="d8b1f-365">NuGet メタデータには、`Copyright` および `Description` プロパティも使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-365">`Copyright` and `Description` properties are also used for NuGet metadata.</span></span>
- <span data-ttu-id="d8b1f-366">`Configuration` はすべてのビルド プロセスで共有され、設定には `dotnet` コマンドの`--configuration` パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-366">`Configuration` is shared with all the build process and set via the `--configuration` parameter of `dotnet` commands.</span></span>

### <a name="generateassemblyinfo"></a><span data-ttu-id="d8b1f-367">GenerateAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="d8b1f-367">GenerateAssemblyInfo</span></span>

<span data-ttu-id="d8b1f-368">すべての AssemblyInfo 生成を有効または無効にするブール値。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-368">A Boolean that enable or disable all the AssemblyInfo generation.</span></span> <span data-ttu-id="d8b1f-369">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-369">The default value is `true`.</span></span>

### <a name="generatedassemblyinfofile"></a><span data-ttu-id="d8b1f-370">GeneratedAssemblyInfoFile</span><span class="sxs-lookup"><span data-stu-id="d8b1f-370">GeneratedAssemblyInfoFile</span></span>

<span data-ttu-id="d8b1f-371">生成されたアセンブリ情報ファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-371">The path of the generated assembly info file.</span></span> <span data-ttu-id="d8b1f-372">既定値は `$(IntermediateOutputPath)` (obj) ディレクトリ内のファイルです。</span><span class="sxs-lookup"><span data-stu-id="d8b1f-372">Default to a file in the `$(IntermediateOutputPath)` (obj) directory.</span></span>
