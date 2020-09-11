---
title: トリミングのオプション
description: 自己完結型アプリのトリミングを制御する方法について説明します。
author: sbomer
ms.author: svbomer
ms.date: 08/25/2020
ms.openlocfilehash: 42e98f9ede004f06221d2df5ecd076500061e37d
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465417"
---
# <a name="trimming-options"></a><span data-ttu-id="fe1ce-103">トリミングのオプション</span><span class="sxs-lookup"><span data-stu-id="fe1ce-103">Trimming options</span></span>

<span data-ttu-id="fe1ce-104">[トリミングされた自己完結型の展開](trim-self-contained.md)の動作は、MSBuild の次のプロパティと項目によって影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-104">The following MSBuild properties and items influence the behavior of [trimmed self-contained deployments](trim-self-contained.md).</span></span> <span data-ttu-id="fe1ce-105">一部のオプションで示されている `ILLink` は、トリミングが実装されている、基になるツールの名前です。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-105">Some of the options mention `ILLink`, which is the name of the underlying tool that implements trimming.</span></span> <span data-ttu-id="fe1ce-106">`ILLink` コマンド ライン ツールの詳細については、[illink のオプション](https://github.com/mono/linker/blob/master/docs/illink-options.md)に関する説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-106">More information about the `ILLink` command-line tool can be found at [illink options](https://github.com/mono/linker/blob/master/docs/illink-options.md).</span></span>

## <a name="enable-trimming"></a><span data-ttu-id="fe1ce-107">トリミングを有効にする</span><span class="sxs-lookup"><span data-stu-id="fe1ce-107">Enable trimming</span></span>

- `<PublishTrimmed>true</PublishTrimmed>`

   <span data-ttu-id="fe1ce-108">トリミングは、SDK で定義されている既定の設定を使用して、発行の間に有効にします。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-108">Enable trimming during publish, with the default settings defined by the SDK.</span></span>

<span data-ttu-id="fe1ce-109">`Microsoft.NET.Sdk` を使用しているときは、これにより netcoreapp ランタイム パックからのフレームワーク アセンブリのアセンブリ レベルのトリミングが実行されます。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-109">When using `Microsoft.NET.Sdk`, this will perform assembly-level trimming of the framework assemblies from the netcoreapp runtime pack.</span></span> <span data-ttu-id="fe1ce-110">アプリケーションのコードと非フレームワーク ライブラリはトリミングされません。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-110">Application code and non-framework libraries are not trimmed.</span></span> <span data-ttu-id="fe1ce-111">他の SDK では、異なる既定値が定義されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-111">Other SDKs may define different defaults.</span></span>

## <a name="trimming-granularity"></a><span data-ttu-id="fe1ce-112">トリミングの最小単位</span><span class="sxs-lookup"><span data-stu-id="fe1ce-112">Trimming granularity</span></span>

<span data-ttu-id="fe1ce-113">次の最小単位の設定により、使用されていない IL をどの程度まで破棄するかが制御されます。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-113">The following granularity settings control how aggressively unused IL is discarded.</span></span> <span data-ttu-id="fe1ce-114">これは、プロパティとして、または[個々のアセンブリ](#trimmed-assemblies)のメタデータとして、設定することができます。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-114">This can be set as a property, or as metadata on an [individual assembly](#trimmed-assemblies).</span></span>

- `<TrimMode>copyused</TrimMode>`

   <span data-ttu-id="fe1ce-115">アセンブリ レベルのトリミングを有効にします。一部でも使用されているアセンブリは、その全体が保持されます (静的に認識されます)。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-115">Enable assembly-level trimming, which will keep an entire assembly if any part of it is used (in a statically understood way).</span></span>

- `<TrimMode>link</TrimMode>`

    <span data-ttu-id="fe1ce-116">メンバー レベルのトリミングを有効にします。これにより、使用されていないメンバーが型から削除されます。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-116">Enable member-level trimming, which removes unused members from types.</span></span>

<span data-ttu-id="fe1ce-117">`<IsTrimmable>true</IsTrimmable>` メタデータが設定されていても、`TrimMode` が明示的に設定されていないアセンブリでは、グローバルな `TrimMode` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-117">Assemblies with `<IsTrimmable>true</IsTrimmable>` metadata but no explicit `TrimMode` will use the global `TrimMode`.</span></span> <span data-ttu-id="fe1ce-118">`Microsoft.NET.Sdk` に対する既定の`TrimMode` は `copyused` です。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-118">The default `TrimMode` for `Microsoft.NET.Sdk` is `copyused`.</span></span>

## <a name="trimmed-assemblies"></a><span data-ttu-id="fe1ce-119">トリミングされたアセンブリ</span><span class="sxs-lookup"><span data-stu-id="fe1ce-119">Trimmed assemblies</span></span>

<span data-ttu-id="fe1ce-120">トリミングされたアプリが発行されるとき、SDK では、トリミングで処理されるファイルのセットを表す、`ManagedAssemblyToLink` と呼ばれる `ItemGroup` が計算されます。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-120">When publishing a trimmed app, the SDK computes an `ItemGroup` called `ManagedAssemblyToLink` that represents the set of files to be processed for trimming.</span></span> <span data-ttu-id="fe1ce-121">`ManagedAssemblyToLink` では、アセンブリごとのトリミング動作を制御するメタデータを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-121">`ManagedAssemblyToLink` may have metadata that controls the trimming behavior per assembly.</span></span> <span data-ttu-id="fe1ce-122">このメタデータを設定するには、組み込みの `PrepareForILLink` ターゲットの前に実行されるターゲットを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-122">To set this metadata, create a target that runs before the built-in `PrepareForILLink` target.</span></span> <span data-ttu-id="fe1ce-123">次の例からは、`MyAssembly` のトリミングを有効にする方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-123">The following example shows how to enable trimming of `MyAssembly`.</span></span>

```xml
<Target Name="ConfigureTrimming"
        BeforeTargets="PrepareForILLink">
  <ItemGroup>
    <ManagedAssemblyToLink Condition="'%(Filename)' == 'MyAssembly'">
      <IsTrimmable>true</IsTrimmable>
    </ManagedAssemblyToLink>
  </ItemGroup>
</Target>
```

<span data-ttu-id="fe1ce-124">`ManagedAssemblyToLink` の項目を追加または削除しないでください。このセットは発行時に SDK によって計算され、変更されないものと想定されているためです。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-124">Do not add or remove items to/from `ManagedAssemblyToLink`, because the SDK computes this set during publish and expects it not to change.</span></span> <span data-ttu-id="fe1ce-125">サポートされているメタデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-125">The supported metadata is:</span></span>

- `<IsTrimmable>true</IsTrimmable>`

  <span data-ttu-id="fe1ce-126">特定のアセンブリをトリミングするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-126">Control whether the given assembly is trimmed.</span></span>

- <span data-ttu-id="fe1ce-127">`<TrimMode>copyused</TrimMode>` または `<TrimMode>link</TrimMode>`</span><span class="sxs-lookup"><span data-stu-id="fe1ce-127">`<TrimMode>copyused</TrimMode>` or `<TrimMode>link</TrimMode>`</span></span>

  <span data-ttu-id="fe1ce-128">このアセンブリの[トリミングの最小単位](#trimming-granularity)を制御します。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-128">Control the [trimming granularity](#trimming-granularity) of this assembly.</span></span> <span data-ttu-id="fe1ce-129">これは、グローバルな `TrimMode` より優先されます。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-129">This takes precedence over the global `TrimMode`.</span></span> <span data-ttu-id="fe1ce-130">アセンブリで `TrimMode` を設定すると、`<IsTrimmable>true</IsTrimmable>` を示します。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-130">Setting `TrimMode` on an assembly implies `<IsTrimmable>true</IsTrimmable>`.</span></span>

## <a name="root-assemblies"></a><span data-ttu-id="fe1ce-131">ルート アセンブリ</span><span class="sxs-lookup"><span data-stu-id="fe1ce-131">Root assemblies</span></span>

<span data-ttu-id="fe1ce-132">`<IsTrimmable>true</IsTrimmable>` を持たないすべてのアセンブリは、分析のルートと見なされます。これは、それらおよびそれらの静的に認識されたすべての依存関係が保持されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-132">All assemblies that do not have `<IsTrimmable>true</IsTrimmable>` are considered roots for the analysis, which means that they and all of their statically understood dependencies will be kept.</span></span> <span data-ttu-id="fe1ce-133">追加のアセンブリは、名前 (`.dll` 拡張子を除く) によって "ルート化" できます。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-133">Additional assemblies may be "rooted" by name (without the `.dll` extension):</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="MyAssembly" />
</ItemGroup>
```

## <a name="root-descriptors"></a><span data-ttu-id="fe1ce-134">ルート記述子</span><span class="sxs-lookup"><span data-stu-id="fe1ce-134">Root descriptors</span></span>

<span data-ttu-id="fe1ce-135">分析に対するルートを指定するもう 1 つの方法は、リンカーの[記述子形式](https://github.com/mono/linker/blob/master/docs/data-formats.md#descriptor-format)を使用する XML ファイルを使用することです。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-135">Another way to specify roots for analysis is using an XML file that uses the linker [descriptor format](https://github.com/mono/linker/blob/master/docs/data-formats.md#descriptor-format).</span></span> <span data-ttu-id="fe1ce-136">これにより、アセンブリ全体ではなく、特定のメンバーをルートにすることができます。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-136">This lets you root specific members instead of a whole assembly.</span></span>

```xml
<ItemGroup>
  <TrimmerRootDescriptor Include="MyRoots.xml" />
</ItemGroup>
```

<span data-ttu-id="fe1ce-137">たとえば、`MyRoots.xml` の場合、アプリケーションによって動的にアクセスされる特定のメソッドがルートになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-137">For example, `MyRoots.xml` might root a specific method that is dynamically accessed by the application:</span></span>

```xml
<linker>
  <assembly fullname="MyAssembly">
    <type fullname="MyAssembly.MyClass">
      <method name="DynamicallyAccessedMethod" />
    </type>
  </assembly>
</linker>
```

## <a name="analysis-warnings"></a><span data-ttu-id="fe1ce-138">分析の警告</span><span class="sxs-lookup"><span data-stu-id="fe1ce-138">Analysis warnings</span></span>

<span data-ttu-id="fe1ce-139">トリミングを行うと、静的に到達できない IL が削除されます。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-139">Trimming will remove IL that is not statically reachable.</span></span> <span data-ttu-id="fe1ce-140">リフレクションまたは動的な依存関係を作成するその他のパターンを使用するアプリは、トリミングによって壊れることがあります。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-140">Apps that use reflection or other patterns that create dynamic dependencies may be broken by trimming.</span></span> <span data-ttu-id="fe1ce-141">そのようなパターンについて警告するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-141">To warn about such patterns:</span></span>

- `<SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>`

    <span data-ttu-id="fe1ce-142">トリミング分析の警告を有効にします。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-142">Enable trim analysis warnings.</span></span>

<span data-ttu-id="fe1ce-143">これには、独自のコード、ライブラリ コード、フレームワーク コードを含む、アプリ全体に関する警告が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-143">This will include warnings about the entire app, including your own code, library code, and framework code.</span></span>

## <a name="warning-versions"></a><span data-ttu-id="fe1ce-144">警告のバージョン</span><span class="sxs-lookup"><span data-stu-id="fe1ce-144">Warning versions</span></span>

<span data-ttu-id="fe1ce-145">トリミング分析は、SDK 全体の分析警告のバージョンを制御する [`AnalysisLevel`](../project-sdk/msbuild-props.md#analysislevel) プロパティに従います。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-145">Trim analysis respects the [`AnalysisLevel`](../project-sdk/msbuild-props.md#analysislevel) property that controls the version of analysis warnings across the SDK.</span></span> <span data-ttu-id="fe1ce-146">トリミング分析の警告のバージョンを個別に制御するプロパティもあります (コンパイラの `WarningLevel` に似ています)。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-146">There is another property that controls the version of trim analysis warnings independently (similar to `WarningLevel` for the compiler):</span></span>

- `<ILLinkWarningLevel>5</ILLinkWarningLevel>`

    <span data-ttu-id="fe1ce-147">特定のレベル以下の警告のみを出力します。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-147">Emit only warnings of the given level or lower.</span></span> <span data-ttu-id="fe1ce-148">これを `9999` にすると、警告のすべてのバージョンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-148">This can be `9999` to include all warning versions.</span></span>

## <a name="suppressing-warnings"></a><span data-ttu-id="fe1ce-149">警告の抑制</span><span class="sxs-lookup"><span data-stu-id="fe1ce-149">Suppressing warnings</span></span>

<span data-ttu-id="fe1ce-150">`NoWarn`、`WarningsAsErrors`、`WarningsNotAsErrors`、`TreatWarningsAsErrors` など、ツールチェーンによって適用される通常の MSBuild プロパティを使用して、個々の[警告コード](https://github.com/mono/linker/blob/master/docs/error-codes.md#warning-codes)を抑制できます。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-150">Individual [warning codes](https://github.com/mono/linker/blob/master/docs/error-codes.md#warning-codes) can be suppressed using the usual MSBuild properties respected by the toolchain, including `NoWarn`, `WarningsAsErrors`, `WarningsNotAsErrors`, and `TreatWarningsAsErrors`.</span></span> <span data-ttu-id="fe1ce-151">ILLink のエラーとしての警告の動作を個別に制御する追加のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-151">There is an additional option that controls the ILLink warn-as-error behavior independently:</span></span>

- `<ILLinkTreatWarningsAsErrors>false</ILLinkTreatWarningsAsErrors>`

    <span data-ttu-id="fe1ce-152">ILLink の警告をエラーとして扱いません。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-152">Don't treat ILLink warnings as errors.</span></span> <span data-ttu-id="fe1ce-153">これは、コンパイラの警告をグローバルにエラーとして扱う場合に、トリミング分析の警告がエラーにならないようにするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-153">This may be useful to avoid turning trim analysis warnings into errors when treating compiler warnings as errors globally.</span></span>

## <a name="removing-symbols"></a><span data-ttu-id="fe1ce-154">シンボルの削除</span><span class="sxs-lookup"><span data-stu-id="fe1ce-154">Removing symbols</span></span>

<span data-ttu-id="fe1ce-155">通常、シンボルは、トリミングされたアセンブリと一致するようにトリミングされます。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-155">Symbols will normally be trimmed to match the trimmed assemblies.</span></span> <span data-ttu-id="fe1ce-156">すべてのシンボルを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-156">You can also remove all symbols:</span></span>

- `<TrimmerRemoveSymbols>true</TrimmerRemoveSymbols>`

    <span data-ttu-id="fe1ce-157">埋め込み PDB や別の PDB ファイルなど、トリミングされたアプリケーションからシンボルを削除します。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-157">Remove symbols from the trimmed application, including embedded PDBs and separate PDB files.</span></span> <span data-ttu-id="fe1ce-158">これは、アプリケーションのコードと、シンボルに付属するすべての依存関係の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-158">This applies to both the application code and any dependencies that come with symbols.</span></span>

<span data-ttu-id="fe1ce-159">また、SDK では、`DebuggerSupport` プロパティを使用してデバッガーのサポートを無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-159">The SDK also makes it possible to disable debugger support using the property `DebuggerSupport`.</span></span> <span data-ttu-id="fe1ce-160">デバッガーのサポートを無効にすると、トリミングによって自動的にシンボルが削除されます (`TrimmerRemoveSymbols` は既定で true に設定されます)。</span><span class="sxs-lookup"><span data-stu-id="fe1ce-160">When debugger support is disabled, trimming will remove symbols automatically (`TrimmerRemoveSymbols` will default to true).</span></span>
