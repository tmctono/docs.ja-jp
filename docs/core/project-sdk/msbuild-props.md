---
title: Microsoft.NET.Sdk の MSBuild プロパティ
description: .NET Core SDK によって認識される MSBuild プロパティのリファレンスです。
ms.date: 02/14/2020
ms.topic: reference
ms.openlocfilehash: 800ff59310d8437d7f770bf20a5bdf37714f8515
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795574"
---
# <a name="msbuild-properties-for-net-core-sdk-projects"></a><span data-ttu-id="6377c-103">.NET Core SDK プロジェクトの MSBuild プロパティ</span><span class="sxs-lookup"><span data-stu-id="6377c-103">MSBuild properties for .NET Core SDK projects</span></span>

<span data-ttu-id="6377c-104">このページでは、.NET Core プロジェクトを構成するための MSBuild プロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6377c-104">This page describes MSBuild properties for configuring .NET Core projects.</span></span> <span data-ttu-id="6377c-105">プロパティの子要素としてプロパティごとに "*メタデータ*" を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6377c-105">You can specify *metadata* for each property as child elements of the property.</span></span>

> [!NOTE]
> <span data-ttu-id="6377c-106">このページの編集は進行中であり、.NET Core SDK の便利な MSBuild プロパティがすべて記載されている訳ではありません。</span><span class="sxs-lookup"><span data-stu-id="6377c-106">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="6377c-107">一般的な MSBuild プロパティの一覧については、「[MSBuild プロジェクトの共通プロパティ](/visualstudio/msbuild/common-msbuild-project-properties)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6377c-107">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="6377c-108">フレームワークのプロパティ</span><span class="sxs-lookup"><span data-stu-id="6377c-108">Framework properties</span></span>

- [<span data-ttu-id="6377c-109">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="6377c-109">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="6377c-110">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="6377c-110">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="6377c-111">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="6377c-111">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="6377c-112">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="6377c-112">TargetFramework</span></span>

<span data-ttu-id="6377c-113">`TargetFramework` プロパティには、[ メタパッケージ ](../packages.md#metapackages) を暗黙的に参照するアプリのターゲット フレームワーク バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="6377c-113">The `TargetFramework` property specifies the target framework version for the app, which implicitly references a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="6377c-114">有効なターゲット フレームワーク モニカーの一覧については、「[SDK スタイルのプロジェクトでのターゲット フレームワーク](../../standard/frameworks.md#supported-target-framework-versions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6377c-114">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="6377c-115">詳細については、「[SDK スタイルのプロジェクトでのターゲット フレームワーク](../../standard/frameworks.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6377c-115">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="6377c-116">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="6377c-116">TargetFrameworks</span></span>

<span data-ttu-id="6377c-117">アプリで複数のプラットフォームをターゲットにする場合は、`TargetFrameworks` プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="6377c-117">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="6377c-118">有効なターゲット フレームワーク モニカーの一覧については、「[SDK スタイルのプロジェクトでのターゲット フレームワーク](../../standard/frameworks.md#supported-target-framework-versions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6377c-118">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="6377c-119">`TargetFramework` (単数形) が指定されている場合、このプロパティは無視されます。</span><span class="sxs-lookup"><span data-stu-id="6377c-119">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="6377c-120">詳細については、「[SDK スタイルのプロジェクトでのターゲット フレームワーク](../../standard/frameworks.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6377c-120">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="6377c-121">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="6377c-121">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="6377c-122">このプロパティは、`netstandard1.x` を使用するプロジェクトにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="6377c-122">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="6377c-123">`netstandard2.x` を使用するプロジェクトには適用されません。</span><span class="sxs-lookup"><span data-stu-id="6377c-123">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="6377c-124">[メタパッケージ](../packages.md#metapackages) バージョンよりも低いフレームワーク バージョンを指定する場合は、`NetStandardImplicitPackageVersion` プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="6377c-124">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the [metapackage](../packages.md#metapackages) version.</span></span> <span data-ttu-id="6377c-125">次の例のプロジェクト ファイルは、`netstandard1.3` をターゲットにしていますが、`NETStandard.Library` の 1.6.0 バージョンを使用しています。</span><span class="sxs-lookup"><span data-stu-id="6377c-125">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="6377c-126">パッケージのプロパティ</span><span class="sxs-lookup"><span data-stu-id="6377c-126">Package properties</span></span>

<span data-ttu-id="6377c-127">`PackageId`、`PackageVersion`、`PackageIcon`、`Title`、`Description` などのプロパティを指定し、プロジェクトから作成されたパッケージについて説明できます。</span><span class="sxs-lookup"><span data-stu-id="6377c-127">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="6377c-128">以上のプロパティとその他のプロパティの詳細については、「[pack ターゲット](/nuget/reference/msbuild-targets#pack-target)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6377c-128">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties"></a><span data-ttu-id="6377c-129">[発行] プロパティ</span><span class="sxs-lookup"><span data-stu-id="6377c-129">Publish properties</span></span>

- [<span data-ttu-id="6377c-130">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="6377c-130">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="6377c-131">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="6377c-131">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="6377c-132">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="6377c-132">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="6377c-133">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="6377c-133">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="6377c-134">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="6377c-134">RuntimeIdentifier</span></span>

<span data-ttu-id="6377c-135">`RuntimeIdentifier` プロパティを使用すると、プロジェクトに 1 つの[ランタイム識別子 (RID)](../rid-catalog.md) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6377c-135">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="6377c-136">RID により、自己完結型の展開を発行できます。</span><span class="sxs-lookup"><span data-stu-id="6377c-136">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="6377c-137">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="6377c-137">RuntimeIdentifiers</span></span>

<span data-ttu-id="6377c-138">`RuntimeIdentifiers` プロパティには、プロジェクトの[ランタイム識別子 (RID)](../rid-catalog.md) のセミコロン区切りリストを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6377c-138">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="6377c-139">複数のランタイムに発行する必要がある場合は、このプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="6377c-139">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="6377c-140">`RuntimeIdentifiers` は、復元時に適切な資産をグラフに確実に含めるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6377c-140">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="6377c-141">`RuntimeIdentifier` (単数形) を使用すると、必要なランタイムが 1 つだけのとき、ビルドが速くなります。</span><span class="sxs-lookup"><span data-stu-id="6377c-141">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="6377c-142">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="6377c-142">TrimmerRootAssembly</span></span>

<span data-ttu-id="6377c-143">`TrimmerRootAssembly` 項目ではアセンブリを "[*トリミング*](../deploying/trim-self-contained.md)" から除外できます。</span><span class="sxs-lookup"><span data-stu-id="6377c-143">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="6377c-144">トリミングとは、パッケージ化されたアプリケーションからランタイムの未使用部分を削除するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="6377c-144">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="6377c-145">必要な参照がトリミングによって間違って削除されることもあります。</span><span class="sxs-lookup"><span data-stu-id="6377c-145">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="6377c-146">次の XML では、トリミングから `System.Security` アセンブリが除外されます。</span><span class="sxs-lookup"><span data-stu-id="6377c-146">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="6377c-147">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="6377c-147">UseAppHost</span></span>

<span data-ttu-id="6377c-148">`UseAppHost` プロパティは、.NET Core SDK の 2.1.400 バージョンで導入されました。</span><span class="sxs-lookup"><span data-stu-id="6377c-148">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="6377c-149">デプロイ用にネイティブ実行可能ファイルを作成するかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="6377c-149">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="6377c-150">自己完結型の配置にはネイティブの実行可能ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="6377c-150">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="6377c-151">.NET Core 3.0 以降のバージョンでは、既定でフレームワークに依存する実行可能ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6377c-151">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="6377c-152">実行可能ファイルの生成を無効にするには、`UseAppHost` プロパティを `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="6377c-152">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="6377c-153">配置の詳細については、[.NET Core アプリケーションの配置](../deploying/index.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6377c-153">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="6377c-154">コンパイルのプロパティ</span><span class="sxs-lookup"><span data-stu-id="6377c-154">Compile properties</span></span>

- [<span data-ttu-id="6377c-155">LangVersion</span><span class="sxs-lookup"><span data-stu-id="6377c-155">LangVersion</span></span>](#langversion)

### <a name="langversion"></a><span data-ttu-id="6377c-156">LangVersion</span><span class="sxs-lookup"><span data-stu-id="6377c-156">LangVersion</span></span>

<span data-ttu-id="6377c-157">`LangVersion` プロパティを使用すると、特定のプログラミング言語バージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6377c-157">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="6377c-158">たとえば、C# プレビュー機能にアクセスする場合は、`LangVersion` を `preview` に設定します。</span><span class="sxs-lookup"><span data-stu-id="6377c-158">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="6377c-159">詳細については、「[C# 言語のバージョン管理](../../csharp/language-reference/configure-language-version.md#override-a-default)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6377c-159">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="6377c-160">ランタイム構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="6377c-160">Run-time configuration properties</span></span>

<span data-ttu-id="6377c-161">アプリのプロジェクト ファイルに MSBuild プロパティを指定することで一部のランタイム動作を構成できます。</span><span class="sxs-lookup"><span data-stu-id="6377c-161">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="6377c-162">ランタイム動作のその他の構成方法については、「[.NET Core ランタイム構成設定](../run-time-config/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6377c-162">For information about other ways of configuring run-time behavior, see [.NET Core run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="6377c-163">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="6377c-163">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="6377c-164">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="6377c-164">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="6377c-165">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="6377c-165">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="6377c-166">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="6377c-166">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="6377c-167">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="6377c-167">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="6377c-168">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="6377c-168">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="6377c-169">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="6377c-169">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="6377c-170">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="6377c-170">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="6377c-171">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="6377c-171">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="6377c-172">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="6377c-172">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="6377c-173">`ConcurrentGarbageCollection` プロパティでは、[バックグラウンド (同時実行) ガベージ コレクション](../../standard/garbage-collection/background-gc.md)の有効または無効が設定されます。</span><span class="sxs-lookup"><span data-stu-id="6377c-173">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="6377c-174">この値を `false` に設定すると、バックグラウンド ガベージ コレクションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="6377c-174">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="6377c-175">詳細については、「[System.GC.Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6377c-175">For more information, see [System.GC.Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="6377c-176">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="6377c-176">InvariantGlobalization</span></span>

<span data-ttu-id="6377c-177">`InvariantGlobalization` プロパティでは、アプリを *globalization-invariant* モードで実行するかどうかを設定します。このモードでは、カルチャ固有のデータにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="6377c-177">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="6377c-178">この値を `true` に設定すると、globalization-invariant モードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="6377c-178">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="6377c-179">詳細については、「[インバリアント モード](../run-time-config/globalization.md#invariant-mode)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6377c-179">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="6377c-180">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="6377c-180">RetainVMGarbageCollection</span></span>

<span data-ttu-id="6377c-181">`RetainVMGarbageCollection` プロパティでは、将来利用する目的で削除済みメモリ セグメントを待機一覧に載せるように、あるいは削除済みメモリ セグメントを解放するようにガベージ コレクターを設定します。</span><span class="sxs-lookup"><span data-stu-id="6377c-181">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="6377c-182">この値を `true` に設定すると、セグメントを待機一覧に載せるよう、ガベージ コレクターが命令されます。</span><span class="sxs-lookup"><span data-stu-id="6377c-182">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="6377c-183">詳細については、「[System.GC.RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6377c-183">For more information, see [System.GC.RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="6377c-184">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="6377c-184">ServerGarbageCollection</span></span>

<span data-ttu-id="6377c-185">`ServerGarbageCollection` プロパティでは、アプリケーションで使用するガベージ コレクションとして[ワークステーション ガベージ コレクションまたはサーバー ガベージ コレクション](../../standard/garbage-collection/workstation-server-gc.md)を設定します。</span><span class="sxs-lookup"><span data-stu-id="6377c-185">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="6377c-186">この値を `true` に設定すると、サーバー ガベージ コレクションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6377c-186">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="6377c-187">詳細については、「[System.GC.Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6377c-187">For more information, see [System.GC.Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="6377c-188">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="6377c-188">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="6377c-189">`ThreadPoolMaxThreads` プロパティでは、ワーカー スレッド プールの最大スレッド数を設定します。</span><span class="sxs-lookup"><span data-stu-id="6377c-189">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="6377c-190">詳細については、「[最大スレッド数](../run-time-config/threading.md#maximum-threads)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6377c-190">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="6377c-191">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="6377c-191">ThreadPoolMinThreads</span></span>

<span data-ttu-id="6377c-192">`ThreadPoolMinThreads` プロパティでは、ワーカー スレッド プールの最小スレッド数を設定します。</span><span class="sxs-lookup"><span data-stu-id="6377c-192">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="6377c-193">詳細については、「[最小スレッド数](../run-time-config/threading.md#minimum-threads)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6377c-193">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="6377c-194">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="6377c-194">TieredCompilation</span></span>

<span data-ttu-id="6377c-195">`TieredCompilation` プロパティでは、Just-In-Time (JIT) コンパイラで[階層型コンパイル](../whats-new/dotnet-core-3-0.md#tiered-compilation)を使用するかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="6377c-195">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="6377c-196">この値を `false` に設定すると、階層型コンパイルが無効になります。</span><span class="sxs-lookup"><span data-stu-id="6377c-196">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="6377c-197">詳細については、「[階層型コンパイル](../run-time-config/compilation.md#tiered-compilation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6377c-197">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="6377c-198">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="6377c-198">TieredCompilationQuickJit</span></span>

<span data-ttu-id="6377c-199">`TieredCompilationQuickJit` プロパティでは、JIT コンパイラでクイック JIT を使用するかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="6377c-199">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="6377c-200">この値を `false` に設定すると、クイック JIT が無効になります。</span><span class="sxs-lookup"><span data-stu-id="6377c-200">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="6377c-201">詳細については、「[クイック JIT](../run-time-config/compilation.md#quick-jit)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6377c-201">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="6377c-202">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="6377c-202">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="6377c-203">`TieredCompilationQuickJitForLoops` プロパティでは、ループを含むメソッドに対して JIT コンパイラでクリック JIT を使用するかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="6377c-203">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="6377c-204">この値を `true` に設定すると、ループが含まれるメソッドでクイック JIT が有効になります。</span><span class="sxs-lookup"><span data-stu-id="6377c-204">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="6377c-205">詳細については、「[ループに対するクイック JIT](../run-time-config/compilation.md#quick-jit-for-loops)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6377c-205">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties"></a><span data-ttu-id="6377c-206">参照のプロパティ</span><span class="sxs-lookup"><span data-stu-id="6377c-206">Reference properties</span></span>

- [<span data-ttu-id="6377c-207">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="6377c-207">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="6377c-208">PackageReference</span><span class="sxs-lookup"><span data-stu-id="6377c-208">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="6377c-209">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="6377c-209">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="6377c-210">参照</span><span class="sxs-lookup"><span data-stu-id="6377c-210">Reference</span></span>](#reference)
- [<span data-ttu-id="6377c-211">Restore プロパティ</span><span class="sxs-lookup"><span data-stu-id="6377c-211">Restore properties</span></span>](#restore-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="6377c-212">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="6377c-212">AssetTargetFallback</span></span>

<span data-ttu-id="6377c-213">`AssetTargetFallback` プロパティを使用すると、プロジェクト参照と NuGet パッケージに対して、互換性のある追加のフレームワーク バージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6377c-213">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="6377c-214">たとえば、`PackageReference` を使用してパッケージの依存関係を指定し、そのパッケージにプロジェクトの `TargetFramework` と互換性のある資産が含まれない場合は、`AssetTargetFallback` プロパティが機能します。</span><span class="sxs-lookup"><span data-stu-id="6377c-214">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="6377c-215">参照されたパッケージの互換性は、`AssetTargetFallback` で指定された各ターゲット フレームワークを使用して再確認されます。</span><span class="sxs-lookup"><span data-stu-id="6377c-215">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="6377c-216">`AssetTargetFallback` プロパティを 1 つ以上の[ターゲット フレームワーク バージョン](../../standard/frameworks.md#supported-target-framework-versions)に設定できます。</span><span class="sxs-lookup"><span data-stu-id="6377c-216">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="6377c-217">PackageReference</span><span class="sxs-lookup"><span data-stu-id="6377c-217">PackageReference</span></span>

<span data-ttu-id="6377c-218">`PackageReference` では、NuGet パッケージへの参照が定義されます。</span><span class="sxs-lookup"><span data-stu-id="6377c-218">The `PackageReference` defines a reference to a NuGet package.</span></span> <span data-ttu-id="6377c-219">たとえば、[メタパッケージ](../packages.md#metapackages)ではなく 1 つのパッケージを参照する場合があります。</span><span class="sxs-lookup"><span data-stu-id="6377c-219">For example, you may want to reference a single package instead of a [metapackage](../packages.md#metapackages).</span></span>

<span data-ttu-id="6377c-220">`Include` 属性は、パッケージ ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="6377c-220">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="6377c-221">`Version` 属性では、バージョンまたはバージョン範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="6377c-221">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="6377c-222">最小バージョン、最大バージョン、範囲、厳密一致を指定する方法については、「[バージョン範囲](/nuget/concepts/package-versioning#version-ranges)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6377c-222">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="6377c-223">また、メタデータ `IncludeAssets`、`ExcludeAssets`、`PrivateAssets` をプロジェクト参照に追加できます。</span><span class="sxs-lookup"><span data-stu-id="6377c-223">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="6377c-224">次の例のプロジェクト ファイル スニペットでは、[System.Runtime](https://www.nuget.org/packages/System.Runtime/) パッケージを参照しています。</span><span class="sxs-lookup"><span data-stu-id="6377c-224">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="6377c-225">詳細については、[プロジェクト ファイルのパッケージ参照](/nuget/consume-packages/package-references-in-project-files)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6377c-225">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="projectreference"></a><span data-ttu-id="6377c-226">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="6377c-226">ProjectReference</span></span>

<span data-ttu-id="6377c-227">`ProjectReference` 項目では、別のプロジェクトへの参照を定義します。</span><span class="sxs-lookup"><span data-stu-id="6377c-227">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="6377c-228">参照されたプロジェクトは NuGet パッケージ依存関係として追加されます。つまり、`PackageReference` と同じように処理されます。</span><span class="sxs-lookup"><span data-stu-id="6377c-228">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="6377c-229">`Include` 属性は、プロジェクトのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="6377c-229">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="6377c-230">また、メタデータ `IncludeAssets`、`ExcludeAssets`、`PrivateAssets` をプロジェクト参照に追加できます。</span><span class="sxs-lookup"><span data-stu-id="6377c-230">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="6377c-231">次の例のプロジェクト ファイル スニペットでは、`Project2` という名前のプロジェクトが参照されます。</span><span class="sxs-lookup"><span data-stu-id="6377c-231">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="6377c-232">関連項目</span><span class="sxs-lookup"><span data-stu-id="6377c-232">Reference</span></span>

<span data-ttu-id="6377c-233">`Reference` 項目では、アセンブリ ファイルへの参照を定義します。</span><span class="sxs-lookup"><span data-stu-id="6377c-233">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="6377c-234">`Include` 属性によってファイルの名前が指定され、`HintPath` 子要素によってアセンブリへのパスが指定されます。</span><span class="sxs-lookup"><span data-stu-id="6377c-234">The `Include` attribute specifies the name of the file, and the `HintPath` child element specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-properties"></a><span data-ttu-id="6377c-235">restore のプロパティ</span><span class="sxs-lookup"><span data-stu-id="6377c-235">Restore properties</span></span>

<span data-ttu-id="6377c-236">参照されたパッケージを復元すると、その直接的な依存関係と間接的な依存関係がすべてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6377c-236">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="6377c-237">`RestorePackagesPath` や `RestoreIgnoreFailedSources` など、プロパティを指定することでパッケージ復元をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="6377c-237">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="6377c-238">以上のプロパティとその他のプロパティの詳細については、「[restore ターゲット](/nuget/reference/msbuild-targets#restore-target)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6377c-238">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="6377c-239">関連項目</span><span class="sxs-lookup"><span data-stu-id="6377c-239">See also</span></span>

- [<span data-ttu-id="6377c-240">MSBuild スキーマ リファレンス</span><span class="sxs-lookup"><span data-stu-id="6377c-240">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="6377c-241">MSBuild の共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="6377c-241">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="6377c-242">NuGet pack の MSBuild プロパティ</span><span class="sxs-lookup"><span data-stu-id="6377c-242">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="6377c-243">NuGet restore の MSBuild プロパティ</span><span class="sxs-lookup"><span data-stu-id="6377c-243">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="6377c-244">ビルドのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="6377c-244">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
