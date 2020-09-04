---
title: Microsoft.NET.Sdk の MSBuild プロパティ
description: .NET Core SDK によって認識される MSBuild のプロパティと項目のリファレンスです。
ms.date: 02/14/2020
ms.topic: reference
ms.custom: updateeachrelease
ms.openlocfilehash: 39cbd18121d2b8659b2f5270f39624798f4ebbdc
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88810523"
---
# <a name="msbuild-reference-for-net-core-sdk-projects"></a><span data-ttu-id="c8f9a-103">.NET Core SDK プロジェクトの MSBuild リファレンス</span><span class="sxs-lookup"><span data-stu-id="c8f9a-103">MSBuild reference for .NET Core SDK projects</span></span>

<span data-ttu-id="c8f9a-104">このページは、.NET Core プロジェクトの構成に使用できる、MSBuild のプロパティと項目のリファレンスです。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-104">This page is a reference for the MSBuild properties and items that you can use to configure .NET Core projects.</span></span>

> [!NOTE]
> <span data-ttu-id="c8f9a-105">このページの編集は進行中であり、.NET Core SDK の便利な MSBuild プロパティがすべて記載されている訳ではありません。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="c8f9a-106">一般的な MSBuild プロパティの一覧については、「[MSBuild プロジェクトの共通プロパティ](/visualstudio/msbuild/common-msbuild-project-properties)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="c8f9a-107">フレームワークのプロパティ</span><span class="sxs-lookup"><span data-stu-id="c8f9a-107">Framework properties</span></span>

- [<span data-ttu-id="c8f9a-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="c8f9a-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="c8f9a-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="c8f9a-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="c8f9a-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="c8f9a-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="c8f9a-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="c8f9a-111">TargetFramework</span></span>

<span data-ttu-id="c8f9a-112">`TargetFramework` プロパティには、アプリのターゲット フレームワーク バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-112">The `TargetFramework` property specifies the target framework version for the app.</span></span> <span data-ttu-id="c8f9a-113">有効なターゲット フレームワーク モニカーの一覧については、「[SDK スタイルのプロジェクトでのターゲット フレームワーク](../../standard/frameworks.md#supported-target-framework-versions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="c8f9a-114">詳細については、「[SDK スタイルのプロジェクトでのターゲット フレームワーク](../../standard/frameworks.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="c8f9a-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="c8f9a-115">TargetFrameworks</span></span>

<span data-ttu-id="c8f9a-116">アプリで複数のプラットフォームをターゲットにする場合は、`TargetFrameworks` プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="c8f9a-117">有効なターゲット フレームワーク モニカーの一覧については、「[SDK スタイルのプロジェクトでのターゲット フレームワーク](../../standard/frameworks.md#supported-target-framework-versions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="c8f9a-118">`TargetFramework` (単数形) が指定されている場合、このプロパティは無視されます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="c8f9a-119">詳細については、「[SDK スタイルのプロジェクトでのターゲット フレームワーク](../../standard/frameworks.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="c8f9a-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="c8f9a-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="c8f9a-121">このプロパティは、`netstandard1.x` を使用するプロジェクトにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="c8f9a-122">`netstandard2.x` を使用するプロジェクトには適用されません。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="c8f9a-123">メタパッケージ バージョンよりも低いフレームワーク バージョンを指定する場合は、`NetStandardImplicitPackageVersion` プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the metapackage version.</span></span> <span data-ttu-id="c8f9a-124">次の例のプロジェクト ファイルは、`netstandard1.3` をターゲットにしていますが、`NETStandard.Library` の 1.6.0 バージョンを使用しています。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="c8f9a-125">パッケージのプロパティ</span><span class="sxs-lookup"><span data-stu-id="c8f9a-125">Package properties</span></span>

<span data-ttu-id="c8f9a-126">`PackageId`、`PackageVersion`、`PackageIcon`、`Title`、`Description` などのプロパティを指定し、プロジェクトから作成されたパッケージについて説明できます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-126">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="c8f9a-127">以上のプロパティとその他のプロパティの詳細については、「[pack ターゲット](/nuget/reference/msbuild-targets#pack-target)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-127">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-and-items"></a><span data-ttu-id="c8f9a-128">プロパティと項目の発行</span><span class="sxs-lookup"><span data-stu-id="c8f9a-128">Publish properties and items</span></span>

- [<span data-ttu-id="c8f9a-129">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="c8f9a-129">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="c8f9a-130">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="c8f9a-130">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="c8f9a-131">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="c8f9a-131">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="c8f9a-132">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="c8f9a-132">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="c8f9a-133">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="c8f9a-133">RuntimeIdentifier</span></span>

<span data-ttu-id="c8f9a-134">`RuntimeIdentifier` プロパティを使用すると、プロジェクトに 1 つの[ランタイム識別子 (RID)](../rid-catalog.md) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-134">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="c8f9a-135">RID により、自己完結型の展開を発行できます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-135">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="c8f9a-136">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="c8f9a-136">RuntimeIdentifiers</span></span>

<span data-ttu-id="c8f9a-137">`RuntimeIdentifiers` プロパティには、プロジェクトの[ランタイム識別子 (RID)](../rid-catalog.md) のセミコロン区切りリストを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-137">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="c8f9a-138">複数のランタイムに発行する必要がある場合は、このプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-138">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="c8f9a-139">`RuntimeIdentifiers` は、復元時に適切な資産をグラフに確実に含めるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-139">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="c8f9a-140">`RuntimeIdentifier` (単数形) を使用すると、必要なランタイムが 1 つだけのとき、ビルドが速くなります。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-140">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="c8f9a-141">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="c8f9a-141">TrimmerRootAssembly</span></span>

<span data-ttu-id="c8f9a-142">`TrimmerRootAssembly` 項目ではアセンブリを "[*トリミング*](../deploying/trim-self-contained.md)" から除外できます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-142">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="c8f9a-143">トリミングとは、パッケージ化されたアプリケーションからランタイムの未使用部分を削除するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-143">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="c8f9a-144">必要な参照がトリミングによって間違って削除されることもあります。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-144">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="c8f9a-145">次の XML では、トリミングから `System.Security` アセンブリが除外されます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-145">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="c8f9a-146">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="c8f9a-146">UseAppHost</span></span>

<span data-ttu-id="c8f9a-147">`UseAppHost` プロパティは、.NET Core SDK の 2.1.400 バージョンで導入されました。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-147">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="c8f9a-148">デプロイ用にネイティブ実行可能ファイルを作成するかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-148">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="c8f9a-149">自己完結型の配置にはネイティブの実行可能ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-149">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="c8f9a-150">.NET Core 3.0 以降のバージョンでは、既定でフレームワークに依存する実行可能ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-150">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="c8f9a-151">実行可能ファイルの生成を無効にするには、`UseAppHost` プロパティを `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-151">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="c8f9a-152">配置の詳細については、[.NET Core アプリケーションの配置](../deploying/index.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-152">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="c8f9a-153">コンパイルのプロパティ</span><span class="sxs-lookup"><span data-stu-id="c8f9a-153">Compile properties</span></span>

- [<span data-ttu-id="c8f9a-154">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="c8f9a-154">EmbeddedResourceUseDependentUponConvention</span></span>](#embeddedresourceusedependentuponconvention)
- [<span data-ttu-id="c8f9a-155">LangVersion</span><span class="sxs-lookup"><span data-stu-id="c8f9a-155">LangVersion</span></span>](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a><span data-ttu-id="c8f9a-156">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="c8f9a-156">EmbeddedResourceUseDependentUponConvention</span></span>

<span data-ttu-id="c8f9a-157">`EmbeddedResourceUseDependentUponConvention` プロパティは、リソース マニフェスト ファイル名が、リソース ファイルと併置されているソース ファイルの型情報から生成されるかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-157">The `EmbeddedResourceUseDependentUponConvention` property defines whether resource manifest file names are generated from type information in source files that are colocated with resource files.</span></span> <span data-ttu-id="c8f9a-158">たとえば、*Form1.vb* が *Form1.cs* と同じフォルダーにあり、`EmbeddedResourceUseDependentUponConvention` が `true` に設定されている場合、生成された *.resources* ファイルは *Form1.cs* で定義されている最初の型から名前を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-158">For example, if *Form1.resx* is in the same folder as *Form1.cs*, and `EmbeddedResourceUseDependentUponConvention` is set to `true`, the generated *.resources* file takes its name from the first type that's defined in *Form1.cs*.</span></span> <span data-ttu-id="c8f9a-159">たとえば、`MyNamespace.Form1` が *Form1.cs* で定義されている最初の型である場合、生成されたファイル名は *MyNamespace.Form1.resources* になります。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-159">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, the generated file name is *MyNamespace.Form1.resources*.</span></span>

> [!NOTE]
> <span data-ttu-id="c8f9a-160">`LogicalName`、`ManifestResourceName`、または `DependentUpon` メタデータが `EmbeddedResource` 項目に対して指定されている場合、そのリソース ファイルに対して生成されたマニフェスト ファイル名は、代わりにそのメタデータがベースになります。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-160">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item, the generated manifest file name for that resource file is based on that metadata instead.</span></span>

<span data-ttu-id="c8f9a-161">既定では、新しい .NET Core プロジェクトでは、このプロパティは `true` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-161">By default, in a new .NET Core project, this property is set to `true`.</span></span> <span data-ttu-id="c8f9a-162">`false` に設定され、かつプロジェクト ファイルの `EmbeddedResource` 項目に `LogicalName`、`ManifestResourceName`、`DependentUpon` のメタデータがどれも指定されていない場合、リソース マニフェストのファイル名は、プロジェクトのルート名前空間と、 *.resx* ファイルへの相対ファイル パスがベースになります。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-162">If set to `false`, and no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for the `EmbeddedResource` item in the project file, the resource manifest file name is based off the root namespace for the project and the relative file path to the *.resx* file.</span></span> <span data-ttu-id="c8f9a-163">詳細については、「[リソース マニフェスト ファイルの名前付けの方法](../resources/manifest-file-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-163">For more information, see [How resource manifest files are named](../resources/manifest-file-names.md).</span></span>

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a><span data-ttu-id="c8f9a-164">LangVersion</span><span class="sxs-lookup"><span data-stu-id="c8f9a-164">LangVersion</span></span>

<span data-ttu-id="c8f9a-165">`LangVersion` プロパティを使用すると、特定のプログラミング言語バージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-165">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="c8f9a-166">たとえば、C# プレビュー機能にアクセスする場合は、`LangVersion` を `preview` に設定します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-166">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="c8f9a-167">詳細については、「[C# 言語のバージョン管理](../../csharp/language-reference/configure-language-version.md#override-a-default)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-167">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="code-analysis-properties"></a><span data-ttu-id="c8f9a-168">コード分析のプロパティ</span><span class="sxs-lookup"><span data-stu-id="c8f9a-168">Code analysis properties</span></span>

### <a name="analysislevel"></a><span data-ttu-id="c8f9a-169">AnalysisLevel</span><span class="sxs-lookup"><span data-stu-id="c8f9a-169">AnalysisLevel</span></span>

<span data-ttu-id="c8f9a-170">`AnalysisLevel` プロパティを使用すると、コード分析レベルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-170">The `AnalysisLevel` property lets you specify a code analysis level.</span></span> <span data-ttu-id="c8f9a-171">たとえば、プレビューのコード アナライザーにアクセスする場合は、`AnalysisLevel` を `preview` に設定します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-171">For example, if you want access to preview code analyzers, set `AnalysisLevel` to `preview`.</span></span> <span data-ttu-id="c8f9a-172">既定値は `latest` です。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-172">The default value is `latest`.</span></span>

```xml
<PropertyGroup>
  <AnalysisLevel>preview</AnalysisLevel>
</PropertyGroup>
```

<span data-ttu-id="c8f9a-173">次の表で利用可能なオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-173">The following table shows the available options.</span></span>

| <span data-ttu-id="c8f9a-174">値</span><span class="sxs-lookup"><span data-stu-id="c8f9a-174">Value</span></span> | <span data-ttu-id="c8f9a-175">説明</span><span class="sxs-lookup"><span data-stu-id="c8f9a-175">Meaning</span></span> |
|-|-|
| `latest` | <span data-ttu-id="c8f9a-176">リリースされている最新のコード アナライザーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-176">The latest code analyzers that have been released are used.</span></span> <span data-ttu-id="c8f9a-177">既定値です。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-177">This is the default.</span></span> |
| `preview` | <span data-ttu-id="c8f9a-178">最新のコード アナライザーが、プレビュー段階であっても使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-178">The latest code analyzers are used, even if they are in preview.</span></span> |
| `5.0` | <span data-ttu-id="c8f9a-179">新しいルールが使用可能な場合でも、.NET 5.0 リリースで有効になっていた一連のルールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-179">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |
| `5` | <span data-ttu-id="c8f9a-180">新しいルールが使用可能な場合でも、.NET 5.0 リリースで有効になっていた一連のルールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-180">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |

### <a name="codeanalysistreatwarningsaserrors"></a><span data-ttu-id="c8f9a-181">CodeAnalysisTreatWarningsAsErrors</span><span class="sxs-lookup"><span data-stu-id="c8f9a-181">CodeAnalysisTreatWarningsAsErrors</span></span>

<span data-ttu-id="c8f9a-182">`CodeAnalysisTreatWarningsAsErrors` プロパティを使用すると、コード分析の警告を警告として扱い、ビルドを中断するかどうかを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-182">The `CodeAnalysisTreatWarningsAsErrors` property lets you configure whether code analysis warnings should be treated as warnings and break the build.</span></span> <span data-ttu-id="c8f9a-183">プロジェクトをビルドするときに `-warnaserror` フラグを使用すると、[.NET コード分析](../../fundamentals/productivity/code-analysis.md)の警告もエラーとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-183">If you use the `-warnaserror` flag when you build your projects, [.NET code analysis](../../fundamentals/productivity/code-analysis.md) warnings are also treated as errors.</span></span> <span data-ttu-id="c8f9a-184">コンパイラの警告のみをエラーとして処理する場合は、プロジェクト ファイル内の `CodeAnalysisTreatWarningsAsErrors` MSBuild プロパティを `false` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-184">If you only want compiler warnings to be treated as errors, you can set the `CodeAnalysisTreatWarningsAsErrors` MSBuild property to `false` in your project file.</span></span>

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

### <a name="enablenetanalyzers"></a><span data-ttu-id="c8f9a-185">EnableNETAnalyzers</span><span class="sxs-lookup"><span data-stu-id="c8f9a-185">EnableNETAnalyzers</span></span>

<span data-ttu-id="c8f9a-186">[.Net コード分析](../../fundamentals/productivity/code-analysis.md)は、.NET 5.0 以降を対象とするプロジェクトで既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-186">[.NET Code analysis](../../fundamentals/productivity/code-analysis.md) is enabled, by default, for projects that target .NET 5.0 or later.</span></span> <span data-ttu-id="c8f9a-187">以前のバージョンの .NET を対象とするプロジェクトで .NET コード分析を有効にするには、`EnableNETAnalyzers` プロパティを true に設定します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-187">You can enable .NET code analysis for projects that target earlier versions of .NET by setting the `EnableNETAnalyzers` property to true.</span></span> <span data-ttu-id="c8f9a-188">任意のプロジェクトでコード分析を無効にするには、このプロパティを `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-188">To disable code analysis in any project, set this property to `false`.</span></span>

```xml
<PropertyGroup>
  <EnableNETAnalyzers>true</EnableNETAnalyzers>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="c8f9a-189">.Net 5.0 より前の .NET バージョンを対象とするプロジェクトで .NET コード分析を有効にするもう 1 つの方法は、[AnalysisLevel](#analysislevel) プロパティを `latest` に設定することです。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-189">Another way to enable .NET code analysis on projects that target .NET versions prior to .NET 5.0 is to set the [AnalysisLevel](#analysislevel) property to `latest`.</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="c8f9a-190">ランタイム構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="c8f9a-190">Run-time configuration properties</span></span>

<span data-ttu-id="c8f9a-191">アプリのプロジェクト ファイルに MSBuild プロパティを指定することで一部のランタイム動作を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-191">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="c8f9a-192">ランタイム動作のその他の構成方法については、「[.NET Core ランタイム構成設定](../run-time-config/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-192">For information about other ways of configuring run-time behavior, see [.NET Core run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="c8f9a-193">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="c8f9a-193">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="c8f9a-194">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="c8f9a-194">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="c8f9a-195">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="c8f9a-195">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="c8f9a-196">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="c8f9a-196">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="c8f9a-197">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="c8f9a-197">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="c8f9a-198">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="c8f9a-198">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="c8f9a-199">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="c8f9a-199">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="c8f9a-200">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="c8f9a-200">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="c8f9a-201">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="c8f9a-201">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="c8f9a-202">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="c8f9a-202">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="c8f9a-203">`ConcurrentGarbageCollection` プロパティでは、[バックグラウンド (同時実行) ガベージ コレクション](../../standard/garbage-collection/background-gc.md)の有効または無効が設定されます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-203">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="c8f9a-204">この値を `false` に設定すると、バックグラウンド ガベージ コレクションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-204">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="c8f9a-205">詳細については、「[バックグラウンド GC](../run-time-config/garbage-collector.md#background-gc)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-205">For more information, see [Background GC](../run-time-config/garbage-collector.md#background-gc).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="c8f9a-206">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="c8f9a-206">InvariantGlobalization</span></span>

<span data-ttu-id="c8f9a-207">`InvariantGlobalization` プロパティでは、アプリを *globalization-invariant* モードで実行するかどうかを設定します。このモードでは、カルチャ固有のデータにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-207">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="c8f9a-208">この値を `true` に設定すると、globalization-invariant モードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-208">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="c8f9a-209">詳細については、「[インバリアント モード](../run-time-config/globalization.md#invariant-mode)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-209">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="c8f9a-210">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="c8f9a-210">RetainVMGarbageCollection</span></span>

<span data-ttu-id="c8f9a-211">`RetainVMGarbageCollection` プロパティでは、将来利用する目的で削除済みメモリ セグメントを待機一覧に載せるように、あるいは削除済みメモリ セグメントを解放するようにガベージ コレクターを設定します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-211">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="c8f9a-212">この値を `true` に設定すると、セグメントを待機一覧に載せるよう、ガベージ コレクターが命令されます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-212">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="c8f9a-213">詳細については、「[VM の保持](../run-time-config/garbage-collector.md#retain-vm)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-213">For more information, see [Retain VM](../run-time-config/garbage-collector.md#retain-vm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="c8f9a-214">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="c8f9a-214">ServerGarbageCollection</span></span>

<span data-ttu-id="c8f9a-215">`ServerGarbageCollection` プロパティでは、アプリケーションで使用するガベージ コレクションとして[ワークステーション ガベージ コレクションまたはサーバー ガベージ コレクション](../../standard/garbage-collection/workstation-server-gc.md)を設定します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-215">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="c8f9a-216">この値を `true` に設定すると、サーバー ガベージ コレクションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-216">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="c8f9a-217">詳細については、「[ワークステーションとサーバー](../run-time-config/garbage-collector.md#workstation-vs-server)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-217">For more information, see [Workstation vs. server](../run-time-config/garbage-collector.md#workstation-vs-server).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="c8f9a-218">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="c8f9a-218">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="c8f9a-219">`ThreadPoolMaxThreads` プロパティでは、ワーカー スレッド プールの最大スレッド数を設定します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-219">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="c8f9a-220">詳細については、「[最大スレッド数](../run-time-config/threading.md#maximum-threads)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-220">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="c8f9a-221">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="c8f9a-221">ThreadPoolMinThreads</span></span>

<span data-ttu-id="c8f9a-222">`ThreadPoolMinThreads` プロパティでは、ワーカー スレッド プールの最小スレッド数を設定します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-222">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="c8f9a-223">詳細については、「[最小スレッド数](../run-time-config/threading.md#minimum-threads)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-223">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="c8f9a-224">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="c8f9a-224">TieredCompilation</span></span>

<span data-ttu-id="c8f9a-225">`TieredCompilation` プロパティでは、Just-In-Time (JIT) コンパイラで[階層型コンパイル](../whats-new/dotnet-core-3-0.md#tiered-compilation)を使用するかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-225">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="c8f9a-226">この値を `false` に設定すると、階層型コンパイルが無効になります。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-226">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="c8f9a-227">詳細については、「[階層型コンパイル](../run-time-config/compilation.md#tiered-compilation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-227">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="c8f9a-228">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="c8f9a-228">TieredCompilationQuickJit</span></span>

<span data-ttu-id="c8f9a-229">`TieredCompilationQuickJit` プロパティでは、JIT コンパイラでクイック JIT を使用するかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-229">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="c8f9a-230">この値を `false` に設定すると、クイック JIT が無効になります。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-230">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="c8f9a-231">詳細については、「[クイック JIT](../run-time-config/compilation.md#quick-jit)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-231">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="c8f9a-232">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="c8f9a-232">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="c8f9a-233">`TieredCompilationQuickJitForLoops` プロパティでは、ループを含むメソッドに対して JIT コンパイラでクリック JIT を使用するかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-233">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="c8f9a-234">この値を `true` に設定すると、ループが含まれるメソッドでクイック JIT が有効になります。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-234">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="c8f9a-235">詳細については、「[ループに対するクイック JIT](../run-time-config/compilation.md#quick-jit-for-loops)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-235">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a><span data-ttu-id="c8f9a-236">プロパティと項目の参照</span><span class="sxs-lookup"><span data-stu-id="c8f9a-236">Reference properties and items</span></span>

- [<span data-ttu-id="c8f9a-237">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="c8f9a-237">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="c8f9a-238">PackageReference</span><span class="sxs-lookup"><span data-stu-id="c8f9a-238">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="c8f9a-239">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="c8f9a-239">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="c8f9a-240">参照</span><span class="sxs-lookup"><span data-stu-id="c8f9a-240">Reference</span></span>](#reference)
- [<span data-ttu-id="c8f9a-241">Restore プロパティ</span><span class="sxs-lookup"><span data-stu-id="c8f9a-241">Restore properties</span></span>](#restore-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="c8f9a-242">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="c8f9a-242">AssetTargetFallback</span></span>

<span data-ttu-id="c8f9a-243">`AssetTargetFallback` プロパティを使用すると、プロジェクト参照と NuGet パッケージに対して、互換性のある追加のフレームワーク バージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-243">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="c8f9a-244">たとえば、`PackageReference` を使用してパッケージの依存関係を指定し、そのパッケージにプロジェクトの `TargetFramework` と互換性のある資産が含まれない場合は、`AssetTargetFallback` プロパティが機能します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-244">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="c8f9a-245">参照されたパッケージの互換性は、`AssetTargetFallback` で指定された各ターゲット フレームワークを使用して再確認されます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-245">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="c8f9a-246">`AssetTargetFallback` プロパティを 1 つ以上の[ターゲット フレームワーク バージョン](../../standard/frameworks.md#supported-target-framework-versions)に設定できます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-246">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="c8f9a-247">PackageReference</span><span class="sxs-lookup"><span data-stu-id="c8f9a-247">PackageReference</span></span>

<span data-ttu-id="c8f9a-248">`PackageReference` 項目では、NuGet パッケージへの参照が定義されます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-248">The `PackageReference` item defines a reference to a NuGet package.</span></span>

<span data-ttu-id="c8f9a-249">`Include` 属性は、パッケージ ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-249">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="c8f9a-250">`Version` 属性では、バージョンまたはバージョン範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-250">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="c8f9a-251">最小バージョン、最大バージョン、範囲、厳密一致を指定する方法については、「[バージョン範囲](/nuget/concepts/package-versioning#version-ranges)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-251">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="c8f9a-252">また、メタデータ `IncludeAssets`、`ExcludeAssets`、`PrivateAssets` をプロジェクト参照に追加できます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-252">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="c8f9a-253">次の例のプロジェクト ファイル スニペットでは、[System.Runtime](https://www.nuget.org/packages/System.Runtime/) パッケージを参照しています。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-253">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="c8f9a-254">詳細については、[プロジェクト ファイルのパッケージ参照](/nuget/consume-packages/package-references-in-project-files)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-254">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="projectreference"></a><span data-ttu-id="c8f9a-255">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="c8f9a-255">ProjectReference</span></span>

<span data-ttu-id="c8f9a-256">`ProjectReference` 項目では、別のプロジェクトへの参照を定義します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-256">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="c8f9a-257">参照されたプロジェクトは NuGet パッケージ依存関係として追加されます。つまり、`PackageReference` と同じように処理されます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-257">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="c8f9a-258">`Include` 属性は、プロジェクトのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-258">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="c8f9a-259">また、メタデータ `IncludeAssets`、`ExcludeAssets`、`PrivateAssets` をプロジェクト参照に追加できます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-259">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="c8f9a-260">次の例のプロジェクト ファイル スニペットでは、`Project2` という名前のプロジェクトが参照されます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-260">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="c8f9a-261">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8f9a-261">Reference</span></span>

<span data-ttu-id="c8f9a-262">`Reference` 項目では、アセンブリ ファイルへの参照を定義します。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-262">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="c8f9a-263">`Include` 属性によってファイルの名前が指定され、`HintPath` メタデータによってアセンブリへのパスが指定されます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-263">The `Include` attribute specifies the name of the file, and the `HintPath` metadata specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-properties"></a><span data-ttu-id="c8f9a-264">restore のプロパティ</span><span class="sxs-lookup"><span data-stu-id="c8f9a-264">Restore properties</span></span>

<span data-ttu-id="c8f9a-265">参照されたパッケージを復元すると、その直接的な依存関係と間接的な依存関係がすべてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-265">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="c8f9a-266">`RestorePackagesPath` や `RestoreIgnoreFailedSources` など、プロパティを指定することでパッケージ復元をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-266">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="c8f9a-267">以上のプロパティとその他のプロパティの詳細については、「[restore ターゲット](/nuget/reference/msbuild-targets#restore-target)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f9a-267">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="c8f9a-268">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8f9a-268">See also</span></span>

- [<span data-ttu-id="c8f9a-269">MSBuild スキーマ リファレンス</span><span class="sxs-lookup"><span data-stu-id="c8f9a-269">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="c8f9a-270">MSBuild の共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="c8f9a-270">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="c8f9a-271">NuGet pack の MSBuild プロパティ</span><span class="sxs-lookup"><span data-stu-id="c8f9a-271">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="c8f9a-272">NuGet restore の MSBuild プロパティ</span><span class="sxs-lookup"><span data-stu-id="c8f9a-272">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="c8f9a-273">ビルドのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="c8f9a-273">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
