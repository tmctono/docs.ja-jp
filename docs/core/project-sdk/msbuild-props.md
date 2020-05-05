---
title: Microsoft.NET.Sdk の MSBuild プロパティ
description: .NET Core SDK によって認識される MSBuild プロパティのリファレンスです。
ms.date: 02/14/2020
ms.topic: reference
ms.openlocfilehash: 105b7d67ea24515ea88481cb4a4fe42d2a03cfd0
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506791"
---
# <a name="msbuild-properties-for-net-core-sdk-projects"></a><span data-ttu-id="c2776-103">.NET Core SDK プロジェクトの MSBuild プロパティ</span><span class="sxs-lookup"><span data-stu-id="c2776-103">MSBuild properties for .NET Core SDK projects</span></span>

<span data-ttu-id="c2776-104">このページでは、.NET Core プロジェクトを構成するための MSBuild プロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c2776-104">This page describes MSBuild properties for configuring .NET Core projects.</span></span>

> [!NOTE]
> <span data-ttu-id="c2776-105">このページの編集は進行中であり、.NET Core SDK の便利な MSBuild プロパティがすべて記載されている訳ではありません。</span><span class="sxs-lookup"><span data-stu-id="c2776-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="c2776-106">一般的な MSBuild プロパティの一覧については、「[MSBuild プロジェクトの共通プロパティ](/visualstudio/msbuild/common-msbuild-project-properties)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2776-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="c2776-107">フレームワークのプロパティ</span><span class="sxs-lookup"><span data-stu-id="c2776-107">Framework properties</span></span>

- [<span data-ttu-id="c2776-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="c2776-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="c2776-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="c2776-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="c2776-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="c2776-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="c2776-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="c2776-111">TargetFramework</span></span>

<span data-ttu-id="c2776-112">`TargetFramework` プロパティには、[ メタパッケージ ](../packages.md#metapackages) を暗黙的に参照するアプリのターゲット フレームワーク バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c2776-112">The `TargetFramework` property specifies the target framework version for the app, which implicitly references a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="c2776-113">有効なターゲット フレームワーク モニカーの一覧については、「[SDK スタイルのプロジェクトでのターゲット フレームワーク](../../standard/frameworks.md#supported-target-framework-versions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2776-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="c2776-114">詳細については、「[SDK スタイルのプロジェクトでのターゲット フレームワーク](../../standard/frameworks.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2776-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="c2776-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="c2776-115">TargetFrameworks</span></span>

<span data-ttu-id="c2776-116">アプリで複数のプラットフォームをターゲットにする場合は、`TargetFrameworks` プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2776-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="c2776-117">有効なターゲット フレームワーク モニカーの一覧については、「[SDK スタイルのプロジェクトでのターゲット フレームワーク](../../standard/frameworks.md#supported-target-framework-versions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2776-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="c2776-118">`TargetFramework` (単数形) が指定されている場合、このプロパティは無視されます。</span><span class="sxs-lookup"><span data-stu-id="c2776-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="c2776-119">詳細については、「[SDK スタイルのプロジェクトでのターゲット フレームワーク](../../standard/frameworks.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2776-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="c2776-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="c2776-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="c2776-121">このプロパティは、`netstandard1.x` を使用するプロジェクトにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c2776-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="c2776-122">`netstandard2.x` を使用するプロジェクトには適用されません。</span><span class="sxs-lookup"><span data-stu-id="c2776-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="c2776-123">[メタパッケージ](../packages.md#metapackages) バージョンよりも低いフレームワーク バージョンを指定する場合は、`NetStandardImplicitPackageVersion` プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2776-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the [metapackage](../packages.md#metapackages) version.</span></span> <span data-ttu-id="c2776-124">次の例のプロジェクト ファイルは、`netstandard1.3` をターゲットにしていますが、`NETStandard.Library` の 1.6.0 バージョンを使用しています。</span><span class="sxs-lookup"><span data-stu-id="c2776-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.3</TargetFramework>
    <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
  </PropertyGroup>
</Project>
```

## <a name="publish-properties"></a><span data-ttu-id="c2776-125">[発行] プロパティ</span><span class="sxs-lookup"><span data-stu-id="c2776-125">Publish properties</span></span>

- [<span data-ttu-id="c2776-126">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="c2776-126">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="c2776-127">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="c2776-127">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="c2776-128">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="c2776-128">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="c2776-129">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="c2776-129">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="c2776-130">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="c2776-130">RuntimeIdentifier</span></span>

<span data-ttu-id="c2776-131">`RuntimeIdentifier` プロパティを使用すると、プロジェクトに 1 つの[ランタイム識別子 (RID)](../rid-catalog.md) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c2776-131">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="c2776-132">RID により、自己完結型の展開を発行できます。</span><span class="sxs-lookup"><span data-stu-id="c2776-132">The RID enables publishing a self-contained deployment.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
  </PropertyGroup>
</Project>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="c2776-133">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="c2776-133">RuntimeIdentifiers</span></span>

<span data-ttu-id="c2776-134">`RuntimeIdentifiers` プロパティには、プロジェクトの[ランタイム識別子 (RID)](../rid-catalog.md) のセミコロン区切りリストを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c2776-134">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="c2776-135">複数のランタイムに発行する必要がある場合は、このプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2776-135">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="c2776-136">`RuntimeIdentifiers` は、復元時に適切な資産をグラフに確実に含めるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c2776-136">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="c2776-137">`RuntimeIdentifier` (単数形) を使用すると、必要なランタイムが 1 つだけのとき、ビルドが速くなります。</span><span class="sxs-lookup"><span data-stu-id="c2776-137">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="c2776-138">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="c2776-138">TrimmerRootAssembly</span></span>

<span data-ttu-id="c2776-139">`TrimmerRootAssembly` 項目ではアセンブリを "[*トリミング*](../deploying/trim-self-contained.md)" から除外できます。</span><span class="sxs-lookup"><span data-stu-id="c2776-139">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="c2776-140">トリミングとは、パッケージ化されたアプリケーションからランタイムの未使用部分を削除するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="c2776-140">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="c2776-141">必要な参照がトリミングによって間違って削除されることもあります。</span><span class="sxs-lookup"><span data-stu-id="c2776-141">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="c2776-142">次の XML では、トリミングから `System.Security` アセンブリが除外されます。</span><span class="sxs-lookup"><span data-stu-id="c2776-142">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
  </ItemGroup>
</Project>
```

### <a name="useapphost"></a><span data-ttu-id="c2776-143">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="c2776-143">UseAppHost</span></span>

<span data-ttu-id="c2776-144">`UseAppHost` プロパティは、.NET Core SDK の 2.1.400 バージョンで導入されました。</span><span class="sxs-lookup"><span data-stu-id="c2776-144">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="c2776-145">デプロイ用にネイティブ実行可能ファイルを作成するかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="c2776-145">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="c2776-146">自己完結型の配置にはネイティブの実行可能ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="c2776-146">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="c2776-147">.NET Core 3.0 以降のバージョンでは、既定でフレームワークに依存する実行可能ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c2776-147">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="c2776-148">実行可能ファイルの生成を無効にするには、`UseAppHost` プロパティを `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="c2776-148">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <UseAppHost>false</UseAppHost>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="c2776-149">配置の詳細については、[.NET Core アプリケーションの配置](../deploying/index.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2776-149">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="c2776-150">コンパイルのプロパティ</span><span class="sxs-lookup"><span data-stu-id="c2776-150">Compile properties</span></span>

- [<span data-ttu-id="c2776-151">LangVersion</span><span class="sxs-lookup"><span data-stu-id="c2776-151">LangVersion</span></span>](#langversion)

### <a name="langversion"></a><span data-ttu-id="c2776-152">LangVersion</span><span class="sxs-lookup"><span data-stu-id="c2776-152">LangVersion</span></span>

<span data-ttu-id="c2776-153">`LangVersion` プロパティを使用すると、特定のプログラミング言語バージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c2776-153">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="c2776-154">たとえば、C# プレビュー機能にアクセスする場合は、`LangVersion` を `preview` に設定します。</span><span class="sxs-lookup"><span data-stu-id="c2776-154">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <LangVersion>preview</LangVersion>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="c2776-155">詳細については、「[C# 言語のバージョン管理](../../csharp/language-reference/configure-language-version.md#override-a-default)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2776-155">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="c2776-156">ランタイム構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="c2776-156">Run-time configuration properties</span></span>

<span data-ttu-id="c2776-157">アプリのプロジェクト ファイルに MSBuild プロパティを指定することで一部のランタイム動作を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c2776-157">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="c2776-158">ランタイム動作のその他の構成方法については、「[.NET Core ランタイム構成設定](../run-time-config/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2776-158">For information about other ways of configuring run-time behavior, see [.NET Core run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="c2776-159">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="c2776-159">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="c2776-160">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="c2776-160">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="c2776-161">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="c2776-161">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="c2776-162">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="c2776-162">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="c2776-163">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="c2776-163">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="c2776-164">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="c2776-164">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="c2776-165">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="c2776-165">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="c2776-166">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="c2776-166">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="c2776-167">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="c2776-167">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="c2776-168">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="c2776-168">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="c2776-169">`ConcurrentGarbageCollection` プロパティでは、[バックグラウンド (同時実行) ガベージ コレクション](../../standard/garbage-collection/background-gc.md)の有効または無効が設定されます。</span><span class="sxs-lookup"><span data-stu-id="c2776-169">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="c2776-170">この値を `false` に設定すると、バックグラウンド ガベージ コレクションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="c2776-170">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="c2776-171">詳細については、「[System.GC.Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2776-171">For more information, see [System.GC.Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>
</Project>
```

### <a name="invariantglobalization"></a><span data-ttu-id="c2776-172">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="c2776-172">InvariantGlobalization</span></span>

<span data-ttu-id="c2776-173">`InvariantGlobalization` プロパティでは、アプリを *globalization-invariant* モードで実行するかどうかを設定します。このモードでは、カルチャ固有のデータにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="c2776-173">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="c2776-174">この値を `true` に設定すると、globalization-invariant モードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="c2776-174">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="c2776-175">詳細については、「[インバリアント モード](../run-time-config/globalization.md#invariant-mode)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2776-175">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>
</Project>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="c2776-176">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="c2776-176">RetainVMGarbageCollection</span></span>

<span data-ttu-id="c2776-177">`RetainVMGarbageCollection` プロパティでは、将来利用する目的で削除済みメモリ セグメントを待機一覧に載せるように、あるいは削除済みメモリ セグメントを解放するようにガベージ コレクターを設定します。</span><span class="sxs-lookup"><span data-stu-id="c2776-177">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="c2776-178">この値を `true` に設定すると、セグメントを待機一覧に載せるよう、ガベージ コレクターが命令されます。</span><span class="sxs-lookup"><span data-stu-id="c2776-178">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="c2776-179">詳細については、「[System.GC.RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2776-179">For more information, see [System.GC.RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>
</Project>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="c2776-180">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="c2776-180">ServerGarbageCollection</span></span>

<span data-ttu-id="c2776-181">`ServerGarbageCollection` プロパティでは、アプリケーションで使用するガベージ コレクションとして[ワークステーション ガベージ コレクションまたはサーバー ガベージ コレクション](../../standard/garbage-collection/workstation-server-gc.md)を設定します。</span><span class="sxs-lookup"><span data-stu-id="c2776-181">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="c2776-182">この値を `true` に設定すると、サーバー ガベージ コレクションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c2776-182">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="c2776-183">詳細については、「[System.GC.Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2776-183">For more information, see [System.GC.Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>
</Project>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="c2776-184">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="c2776-184">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="c2776-185">`ThreadPoolMaxThreads` プロパティでは、ワーカー スレッド プールの最大スレッド数を設定します。</span><span class="sxs-lookup"><span data-stu-id="c2776-185">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="c2776-186">詳細については、「[最大スレッド数](../run-time-config/threading.md#maximum-threads)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2776-186">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>
</Project>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="c2776-187">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="c2776-187">ThreadPoolMinThreads</span></span>

<span data-ttu-id="c2776-188">`ThreadPoolMinThreads` プロパティでは、ワーカー スレッド プールの最小スレッド数を設定します。</span><span class="sxs-lookup"><span data-stu-id="c2776-188">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="c2776-189">詳細については、「[最小スレッド数](../run-time-config/threading.md#minimum-threads)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2776-189">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>
</Project>
```

### <a name="tieredcompilation"></a><span data-ttu-id="c2776-190">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="c2776-190">TieredCompilation</span></span>

<span data-ttu-id="c2776-191">`TieredCompilation` プロパティでは、Just-In-Time (JIT) コンパイラで[階層型コンパイル](../whats-new/dotnet-core-3-0.md#tiered-compilation)を使用するかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="c2776-191">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="c2776-192">この値を `false` に設定すると、階層型コンパイルが無効になります。</span><span class="sxs-lookup"><span data-stu-id="c2776-192">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="c2776-193">詳細については、「[階層型コンパイル](../run-time-config/compilation.md#tiered-compilation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2776-193">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TieredCompilation>false</TieredCompilation>
  </PropertyGroup>
</Project>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="c2776-194">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="c2776-194">TieredCompilationQuickJit</span></span>

<span data-ttu-id="c2776-195">`TieredCompilationQuickJit` プロパティでは、JIT コンパイラでクイック JIT を使用するかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="c2776-195">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="c2776-196">この値を `false` に設定すると、クイック JIT が無効になります。</span><span class="sxs-lookup"><span data-stu-id="c2776-196">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="c2776-197">詳細については、「[クイック JIT](../run-time-config/compilation.md#quick-jit)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2776-197">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
  </PropertyGroup>
</Project>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="c2776-198">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="c2776-198">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="c2776-199">`TieredCompilationQuickJitForLoops` プロパティでは、ループを含むメソッドに対して JIT コンパイラでクリック JIT を使用するかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="c2776-199">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="c2776-200">この値を `true` に設定すると、ループが含まれるメソッドでクイック JIT が有効になります。</span><span class="sxs-lookup"><span data-stu-id="c2776-200">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="c2776-201">詳細については、「[ループに対するクイック JIT](../run-time-config/compilation.md#quick-jit-for-loops)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2776-201">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
  </PropertyGroup>
</Project>
```

## <a name="nuget-packages"></a><span data-ttu-id="c2776-202">NuGet パッケージ</span><span class="sxs-lookup"><span data-stu-id="c2776-202">NuGet packages</span></span>

- [<span data-ttu-id="c2776-203">PackageReference</span><span class="sxs-lookup"><span data-stu-id="c2776-203">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="c2776-204">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="c2776-204">AssetTargetFallback</span></span>](#assettargetfallback)

### <a name="packagereference"></a><span data-ttu-id="c2776-205">PackageReference</span><span class="sxs-lookup"><span data-stu-id="c2776-205">PackageReference</span></span>

<span data-ttu-id="c2776-206">`PackageReference` 項目を使用すると、NuGet の依存関係を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c2776-206">The `PackageReference` item lets you specify a NuGet dependency.</span></span> <span data-ttu-id="c2776-207">たとえば、[メタパッケージ](../packages.md#metapackages)ではなく 1 つのパッケージを参照する場合があります。</span><span class="sxs-lookup"><span data-stu-id="c2776-207">For example, you may want to reference a single package instead of a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="c2776-208">`Include` 属性は、パッケージ ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="c2776-208">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="c2776-209">次の例のプロジェクト ファイル スニペットでは、[System.Runtime](https://www.nuget.org/packages/System.Runtime/) パッケージを参照しています。</span><span class="sxs-lookup"><span data-stu-id="c2776-209">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <ItemGroup>
    <PackageReference Include="System.Runtime" Version="4.3.0" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="c2776-210">詳細については、[プロジェクト ファイルのパッケージ参照](/nuget/consume-packages/package-references-in-project-files)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2776-210">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="assettargetfallback"></a><span data-ttu-id="c2776-211">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="c2776-211">AssetTargetFallback</span></span>

<span data-ttu-id="c2776-212">`AssetTargetFallback` プロパティを使用すると、プロジェクトから参照されるプロジェクトの互換性のある追加のフレームワーク バージョンと、プロジェクトに使用する NuGet パッケージを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c2776-212">The `AssetTargetFallback` property lets you specify additional compatible framework versions for projects that your project references and NuGet packages that your project consumes.</span></span> <span data-ttu-id="c2776-213">たとえば、`PackageReference` を使用してパッケージの依存関係を指定し、そのパッケージにプロジェクトの `TargetFramework` と互換性のある資産が含まれない場合は、`AssetTargetFallback` プロパティが機能します。</span><span class="sxs-lookup"><span data-stu-id="c2776-213">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="c2776-214">参照されたパッケージの互換性は、`AssetTargetFallback` で指定された各ターゲット フレームワークを使用して再確認されます。</span><span class="sxs-lookup"><span data-stu-id="c2776-214">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="c2776-215">`AssetTargetFallback` プロパティを 1 つ以上の[ターゲット フレームワーク バージョン](../../standard/frameworks.md#supported-target-framework-versions)に設定できます。</span><span class="sxs-lookup"><span data-stu-id="c2776-215">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <PropertyGroup>
    <AssetTargetFallback>net461</AssetTargetFallback>
  </PropertyGroup>
</Project>
```

### <a name="pack-and-restore-targets"></a><span data-ttu-id="c2776-216">ターゲットのパックと復元</span><span class="sxs-lookup"><span data-stu-id="c2776-216">Pack and restore targets</span></span>

<span data-ttu-id="c2776-217">MSBuild 15.1 では、ビルドの一部として NuGet パッケージを作成および復元するための `pack` および `restore` ターゲットが導入されました。</span><span class="sxs-lookup"><span data-stu-id="c2776-217">MSBuild 15.1 introduced `pack` and `restore` targets for creating and restoring NuGet packages as part of a build.</span></span> <span data-ttu-id="c2776-218">`PackageTargetFallback` など、これらのターゲットの MSBuild プロパティについては、「[MSBuild ターゲットとしての NuGet の pack と restor](/nuget/reference/msbuild-targets)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2776-218">For information about the MSBuild properties for these targets, including `PackageTargetFallback`, see [NuGet pack and restore as MSBuild targets](/nuget/reference/msbuild-targets).</span></span>

## <a name="see-also"></a><span data-ttu-id="c2776-219">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2776-219">See also</span></span>

- [<span data-ttu-id="c2776-220">MSBuild スキーマ リファレンス</span><span class="sxs-lookup"><span data-stu-id="c2776-220">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="c2776-221">MSBuild の共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="c2776-221">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="c2776-222">NuGet pack の MSBuild プロパティ</span><span class="sxs-lookup"><span data-stu-id="c2776-222">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="c2776-223">NuGet restore の MSBuild プロパティ</span><span class="sxs-lookup"><span data-stu-id="c2776-223">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="c2776-224">ビルドのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="c2776-224">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
