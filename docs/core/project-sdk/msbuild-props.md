---
title: Microsoft.NET.Sdk の MSBuild プロパティ
description: .NET Core SDK によって認識される MSBuild プロパティのリファレンスです。
ms.date: 02/14/2020
ms.topic: reference
ms.openlocfilehash: d4a204a1e0216313418d278ec3bd333f72db8751
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "81386658"
---
# <a name="msbuild-properties-for-net-core-sdk-projects"></a><span data-ttu-id="c10b1-103">.NET Core SDK プロジェクトの MSBuild プロパティ</span><span class="sxs-lookup"><span data-stu-id="c10b1-103">MSBuild properties for .NET Core SDK projects</span></span>

<span data-ttu-id="c10b1-104">このページでは、.NET Core プロジェクトを構成するための MSBuild プロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c10b1-104">This page describes MSBuild properties for configuring .NET Core projects.</span></span>

> [!NOTE]
> <span data-ttu-id="c10b1-105">このページの編集は進行中であり、.NET Core SDK の便利な MSBuild プロパティがすべて記載されている訳ではありません。</span><span class="sxs-lookup"><span data-stu-id="c10b1-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="c10b1-106">一般的な MSBuild プロパティの一覧については、「[MSBuild プロジェクトの共通プロパティ](/visualstudio/msbuild/common-msbuild-project-properties)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c10b1-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="c10b1-107">フレームワークのプロパティ</span><span class="sxs-lookup"><span data-stu-id="c10b1-107">Framework properties</span></span>

- [<span data-ttu-id="c10b1-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="c10b1-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="c10b1-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="c10b1-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="c10b1-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="c10b1-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="c10b1-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="c10b1-111">TargetFramework</span></span>

<span data-ttu-id="c10b1-112">`TargetFramework` プロパティには、[ メタパッケージ ](../packages.md#metapackages) を暗黙的に参照するアプリのターゲット フレームワーク バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c10b1-112">The `TargetFramework` property specifies the target framework version for the app, which implicitly references a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="c10b1-113">有効なターゲット フレームワーク モニカーの一覧については、「[SDK スタイルのプロジェクトでのターゲット フレームワーク](../../standard/frameworks.md#supported-target-framework-versions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c10b1-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="c10b1-114">詳細については、「[SDK スタイルのプロジェクトでのターゲット フレームワーク](../../standard/frameworks.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c10b1-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="c10b1-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="c10b1-115">TargetFrameworks</span></span>

<span data-ttu-id="c10b1-116">アプリで複数のプラットフォームをターゲットにする場合は、`TargetFrameworks` プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="c10b1-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="c10b1-117">有効なターゲット フレームワーク モニカーの一覧については、「[SDK スタイルのプロジェクトでのターゲット フレームワーク](../../standard/frameworks.md#supported-target-framework-versions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c10b1-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="c10b1-118">`TargetFramework` (単数形) が指定されている場合、このプロパティは無視されます。</span><span class="sxs-lookup"><span data-stu-id="c10b1-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="c10b1-119">詳細については、「[SDK スタイルのプロジェクトでのターゲット フレームワーク](../../standard/frameworks.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c10b1-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="c10b1-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="c10b1-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="c10b1-121">このプロパティは、`netstandard1.x` を使用するプロジェクトにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c10b1-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="c10b1-122">`netstandard2.x` を使用するプロジェクトには適用されません。</span><span class="sxs-lookup"><span data-stu-id="c10b1-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="c10b1-123">[メタパッケージ](../packages.md#metapackages) バージョンよりも低いフレームワーク バージョンを指定する場合は、`NetStandardImplicitPackageVersion` プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="c10b1-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the [metapackage](../packages.md#metapackages) version.</span></span> <span data-ttu-id="c10b1-124">次の例のプロジェクト ファイルは、`netstandard1.3` をターゲットにしていますが、`NETStandard.Library` の 1.6.0 バージョンを使用しています。</span><span class="sxs-lookup"><span data-stu-id="c10b1-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.3</TargetFramework>
    <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
  </PropertyGroup>
</Project>
```

## <a name="publish-properties"></a><span data-ttu-id="c10b1-125">[発行] プロパティ</span><span class="sxs-lookup"><span data-stu-id="c10b1-125">Publish properties</span></span>

- [<span data-ttu-id="c10b1-126">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="c10b1-126">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="c10b1-127">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="c10b1-127">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="c10b1-128">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="c10b1-128">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="c10b1-129">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="c10b1-129">RuntimeIdentifier</span></span>

<span data-ttu-id="c10b1-130">`RuntimeIdentifier` プロパティを使用すると、プロジェクトに 1 つの[ランタイム識別子 (RID)](../rid-catalog.md) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c10b1-130">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="c10b1-131">RID により、自己完結型の展開を発行できます。</span><span class="sxs-lookup"><span data-stu-id="c10b1-131">The RID enables publishing a self-contained deployment.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
  </PropertyGroup>
</Project>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="c10b1-132">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="c10b1-132">RuntimeIdentifiers</span></span>

<span data-ttu-id="c10b1-133">`RuntimeIdentifiers` プロパティには、プロジェクトの[ランタイム識別子 (RID)](../rid-catalog.md) のセミコロン区切りリストを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c10b1-133">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="c10b1-134">複数のランタイムに発行する必要がある場合は、このプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="c10b1-134">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="c10b1-135">`RuntimeIdentifiers` は、復元時に適切な資産をグラフに確実に含めるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c10b1-135">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="c10b1-136">`RuntimeIdentifier` (単数形) を使用すると、必要なランタイムが 1 つだけのとき、ビルドが速くなります。</span><span class="sxs-lookup"><span data-stu-id="c10b1-136">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

### <a name="useapphost"></a><span data-ttu-id="c10b1-137">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="c10b1-137">UseAppHost</span></span>

<span data-ttu-id="c10b1-138">`UseAppHost` プロパティは、.NET Core SDK の 2.1.400 バージョンで導入されました。</span><span class="sxs-lookup"><span data-stu-id="c10b1-138">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="c10b1-139">デプロイ用にネイティブ実行可能ファイルを作成するかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="c10b1-139">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="c10b1-140">自己完結型の配置にはネイティブの実行可能ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="c10b1-140">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="c10b1-141">.NET Core 3.0 以降のバージョンでは、既定でフレームワークに依存する実行可能ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c10b1-141">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="c10b1-142">実行可能ファイルの生成を無効にするには、`UseAppHost` プロパティを `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="c10b1-142">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <UseAppHost>false</UseAppHost>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="c10b1-143">配置の詳細については、[.NET Core アプリケーションの配置](../deploying/index.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c10b1-143">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="c10b1-144">コンパイルのプロパティ</span><span class="sxs-lookup"><span data-stu-id="c10b1-144">Compile properties</span></span>

### <a name="langversion"></a><span data-ttu-id="c10b1-145">LangVersion</span><span class="sxs-lookup"><span data-stu-id="c10b1-145">LangVersion</span></span>

<span data-ttu-id="c10b1-146">`LangVersion` プロパティを使用すると、特定のプログラミング言語バージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c10b1-146">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="c10b1-147">たとえば、C# プレビュー機能にアクセスする場合は、`LangVersion` を `preview` に設定します。</span><span class="sxs-lookup"><span data-stu-id="c10b1-147">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <LangVersion>preview</LangVersion>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="c10b1-148">詳細については、「[C# 言語のバージョン管理](../../csharp/language-reference/configure-language-version.md#override-a-default)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c10b1-148">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="nuget-packages"></a><span data-ttu-id="c10b1-149">NuGet パッケージ</span><span class="sxs-lookup"><span data-stu-id="c10b1-149">NuGet packages</span></span>

- [<span data-ttu-id="c10b1-150">PackageReference</span><span class="sxs-lookup"><span data-stu-id="c10b1-150">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="c10b1-151">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="c10b1-151">AssetTargetFallback</span></span>](#assettargetfallback)

### <a name="packagereference"></a><span data-ttu-id="c10b1-152">PackageReference</span><span class="sxs-lookup"><span data-stu-id="c10b1-152">PackageReference</span></span>

<span data-ttu-id="c10b1-153">`PackageReference` 項目を使用すると、NuGet の依存関係を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c10b1-153">The `PackageReference` item lets you specify a NuGet dependency.</span></span> <span data-ttu-id="c10b1-154">たとえば、[メタパッケージ](../packages.md#metapackages)ではなく 1 つのパッケージを参照する場合があります。</span><span class="sxs-lookup"><span data-stu-id="c10b1-154">For example, you may want to reference a single package instead of a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="c10b1-155">`Include` 属性は、パッケージ ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="c10b1-155">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="c10b1-156">次の例のプロジェクト ファイル スニペットでは、[System.Runtime](https://www.nuget.org/packages/System.Runtime/) パッケージを参照しています。</span><span class="sxs-lookup"><span data-stu-id="c10b1-156">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <ItemGroup>
    <PackageReference Include="System.Runtime" Version="4.3.0" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="c10b1-157">詳細については、[プロジェクト ファイルのパッケージ参照](/nuget/consume-packages/package-references-in-project-files)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c10b1-157">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="assettargetfallback"></a><span data-ttu-id="c10b1-158">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="c10b1-158">AssetTargetFallback</span></span>

<span data-ttu-id="c10b1-159">`AssetTargetFallback` プロパティを使用すると、プロジェクトから参照されるプロジェクトの互換性のある追加のフレームワーク バージョンと、プロジェクトに使用する NuGet パッケージを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c10b1-159">The `AssetTargetFallback` property lets you specify additional compatible framework versions for projects that your project references and NuGet packages that your project consumes.</span></span> <span data-ttu-id="c10b1-160">たとえば、`PackageReference` を使用してパッケージの依存関係を指定し、そのパッケージにプロジェクトの `TargetFramework` と互換性のある資産が含まれない場合は、`AssetTargetFallback` プロパティが機能します。</span><span class="sxs-lookup"><span data-stu-id="c10b1-160">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="c10b1-161">参照されたパッケージの互換性は、`AssetTargetFallback` で指定された各ターゲット フレームワークを使用して再確認されます。</span><span class="sxs-lookup"><span data-stu-id="c10b1-161">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="c10b1-162">`AssetTargetFallback` プロパティを 1 つ以上の[ターゲット フレームワーク バージョン](../../standard/frameworks.md#supported-target-framework-versions)に設定できます。</span><span class="sxs-lookup"><span data-stu-id="c10b1-162">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <PropertyGroup>
    <AssetTargetFallback>net461</AssetTargetFallback>
  </PropertyGroup>
</Project>
```

### <a name="pack-and-restore-targets"></a><span data-ttu-id="c10b1-163">ターゲットのパックと復元</span><span class="sxs-lookup"><span data-stu-id="c10b1-163">Pack and restore targets</span></span>

<span data-ttu-id="c10b1-164">MSBuild 15.1 では、ビルドの一部として NuGet パッケージを作成および復元するための `pack` および `restore` ターゲットが導入されました。</span><span class="sxs-lookup"><span data-stu-id="c10b1-164">MSBuild 15.1 introduced `pack` and `restore` targets for creating and restoring NuGet packages as part of a build.</span></span> <span data-ttu-id="c10b1-165">`PackageTargetFallback` など、これらのターゲットの MSBuild プロパティについては、「[MSBuild ターゲットとしての NuGet の pack と restor](/nuget/reference/msbuild-targets)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c10b1-165">For information about the MSBuild properties for these targets, including `PackageTargetFallback`, see [NuGet pack and restore as MSBuild targets](/nuget/reference/msbuild-targets).</span></span>

## <a name="see-also"></a><span data-ttu-id="c10b1-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="c10b1-166">See also</span></span>

- [<span data-ttu-id="c10b1-167">MSBuild スキーマ リファレンス</span><span class="sxs-lookup"><span data-stu-id="c10b1-167">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="c10b1-168">MSBuild の共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="c10b1-168">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="c10b1-169">NuGet pack の MSBuild プロパティ</span><span class="sxs-lookup"><span data-stu-id="c10b1-169">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="c10b1-170">NuGet restore の MSBuild プロパティ</span><span class="sxs-lookup"><span data-stu-id="c10b1-170">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="c10b1-171">ビルドのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="c10b1-171">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
