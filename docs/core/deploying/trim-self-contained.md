---
title: 自己完結型アプリケーションのトリミング
description: 自己完結型アプリケーションをトリミングしてサイズを縮小する方法について説明します。 .NET Core は、自己完結型で公開されているアプリケーションでランタイムをバンドルし、通常は必要以上のランタイムを含んでいます。
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: 9c2994c98a2ebe6f45b056256c2bda28db017fbf
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465482"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="7ea29-104">自己完結型の展開と実行可能ファイルのトリミング</span><span class="sxs-lookup"><span data-stu-id="7ea29-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="7ea29-105">[フレームワークに依存するデプロイ モデル](index.md#publish-framework-dependent)は、.NET の開始以降に最も一般的となったデプロイ モデルです。</span><span class="sxs-lookup"><span data-stu-id="7ea29-105">The [framework-dependent deployment model](index.md#publish-framework-dependent) has been the most successful deployment model since the inception of .NET.</span></span> <span data-ttu-id="7ea29-106">このシナリオでは、アプリケーション開発者は、.NET ランタイムおよびフレームワーク ライブラリがクライアント コンピューターで利用できることを見込んで、アプリケーションとサードパーティのアセンブリのみをバンドルします。</span><span class="sxs-lookup"><span data-stu-id="7ea29-106">In this scenario, the application developer bundles only the application and third-party assemblies with the expectation that the .NET runtime and framework libraries will be available in the client machine.</span></span> <span data-ttu-id="7ea29-107">このデプロイ モデルは .NET Core でも引き続き主に使用されますが、フレームワークに依存するモデルが最適ではないシナリオもあります。</span><span class="sxs-lookup"><span data-stu-id="7ea29-107">This deployment model continues to be the dominant one in .NET Core as well but there are some scenarios where the framework-dependent model is not optimal.</span></span> <span data-ttu-id="7ea29-108">別の方法としては、[自己完結型アプリケーション](index.md#publish-self-contained)を発行します。この場合、.NET Core ランタイムおよびフレームワークは、アプリケーションとサードパーティのアセンブリと共にバンドルされます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-108">The alternative is to publish a [self-contained application](index.md#publish-self-contained), where the .NET Core runtime and framework are bundled together with the application and third-party assemblies.</span></span>

<span data-ttu-id="7ea29-109">トリミング自己完結型のデプロイ モデルは、展開のサイズを小さくするために最適化された、自己完結型のデプロイ モデルの特殊なバージョンです。</span><span class="sxs-lookup"><span data-stu-id="7ea29-109">The trim-self-contained deployment model is a specialized version of the self-contained deployment model that is optimized to reduce deployment size.</span></span> <span data-ttu-id="7ea29-110">展開のサイズを最小限に抑えることは、Blazor アプリケーションなどの一部のクライアント側のシナリオでは重要な要件です。</span><span class="sxs-lookup"><span data-stu-id="7ea29-110">Minimizing deployment size is a critical requirement for some client-side scenarios like Blazor applications.</span></span> <span data-ttu-id="7ea29-111">アプリケーションの複雑さによっては、アプリケーションを実行するために、フレームワーク アセンブリのサブセットのみが参照され、各アセンブリ内のコードのサブセットのみが必要となります。</span><span class="sxs-lookup"><span data-stu-id="7ea29-111">Depending on the complexity of the application, only a subset of the framework assemblies are referenced, and a subset of the code within each assembly is required to run the application.</span></span> <span data-ttu-id="7ea29-112">ライブラリの未使用部分は不要であり、パッケージ化されたアプリケーションから削除することができます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-112">The unused parts of the libraries are unnecessary and can be trimmed from the packaged application.</span></span>

<span data-ttu-id="7ea29-113">ただし、アプリケーションのビルド時分析によってランタイム エラーが発生しうるというリスクがあります。これは、問題のあるさまざまなコード パターンを確実に分析できないためです (ほとんどの場合、リフレクション使用が中心となります)。</span><span class="sxs-lookup"><span data-stu-id="7ea29-113">However, there is a risk that the build time analysis of the application can cause failures at runtime, due to not being able to reliably analyze various problematic code patterns (largely centered on reflection use).</span></span> <span data-ttu-id="7ea29-114">信頼性を保証できないため、このデプロイ モデルはプレビュー機能として提供されます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-114">Because reliability can't be guaranteed, this deployment model is offered as a preview feature.</span></span>

<span data-ttu-id="7ea29-115">ビルド時分析エンジンによって、問題のあるコード パターンの開発者に対して、必要な他のコードを検出するように警告が与えられます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-115">The build time analysis engine provides warnings to the developer of code patterns that are problematic to detect which other code is required.</span></span> <span data-ttu-id="7ea29-116">コードには、他に含めるものをトリマーに指示する属性を使用して注釈が付けられます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-116">Code can be annotated with attributes to tell the trimmer what else to include.</span></span> <span data-ttu-id="7ea29-117">多くのリフレクション パターンは、[ソース ジェネレーター](https://github.com/dotnet/roslyn/blob/master/docs/features/source-generators.md)を使用して、ビルド時コード生成に置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-117">Many reflection patterns can be replaced with build-time code generation using [Source Generators](https://github.com/dotnet/roslyn/blob/master/docs/features/source-generators.md).</span></span>

<span data-ttu-id="7ea29-118">アプリケーションのトリミング モードは、`TrimMode` 設定で構成されます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-118">The trim mode for the applications is configured with the `TrimMode` setting.</span></span> <span data-ttu-id="7ea29-119">既定値は `copyused` で、参照されるアセンブリがアプリケーションとバンドルされます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-119">The default value is `copyused` and bundles referenced assemblies with the application.</span></span> <span data-ttu-id="7ea29-120">Blazor WebAssembly では、`link` 値が使用され、アセンブリ内の使用されていないコードがトリミングされます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-120">The `link` value is used with Blazor WebAssembly applications and trims unused code within assemblies.</span></span> <span data-ttu-id="7ea29-121">トリミング分析の警告により、完全な依存関係分析が不可能なコード パターンに関する情報が示されます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-121">Trim analysis warnings give information on code patterns where a full dependency analysis was not possible.</span></span> <span data-ttu-id="7ea29-122">これらの警告は、既定では非表示となり、フラグ `SuppressTrimAnalysisWarnings` を `false` に設定することで有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-122">These warnings are suppressed by default and can be turned on by setting the flag `SuppressTrimAnalysisWarnings` to `false`.</span></span> <span data-ttu-id="7ea29-123">使用可能なトリミング オプションの詳細については、「[トリミング オプション](trimming-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ea29-123">For more information about the trim options available, see [Trimming options](trimming-options.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7ea29-124">トリミングは .NET Core 3.1、5.0 の実験的な機能であり、自己完結型で公開されるアプリケーションで "_のみ_" 使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-124">Trimming is an experimental feature in .NET Core 3.1, 5.0 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="prevent-assemblies-from-being-trimmed"></a><span data-ttu-id="7ea29-125">アセンブリがトリミングされないようにする</span><span class="sxs-lookup"><span data-stu-id="7ea29-125">Prevent assemblies from being trimmed</span></span>

<span data-ttu-id="7ea29-126">トリミング機能が参照の検出に失敗するシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="7ea29-126">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="7ea29-127">たとえば、アプリケーションまたはアプリケーションによって参照されるライブラリから、ランタイム アセンブリに対してリフレクションが使用されている場合、アセンブリは直接参照されません。</span><span class="sxs-lookup"><span data-stu-id="7ea29-127">For example, when reflection is used on a runtime assembly, either by your application or a library that is referenced by your application, the assembly isn't directly referenced.</span></span> <span data-ttu-id="7ea29-128">このような間接参照はトリミングに認識されず、ライブラリは発行フォルダーから除外されます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-128">Trimming is unaware of these indirect references and would exclude the library from the published folder.</span></span>

<span data-ttu-id="7ea29-129">コードからリフレクションを介して間接的にアセンブリを参照している場合は、`<TrimmerRootAssembly>` 設定を使用してアセンブリがトリミングされないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-129">When the code is indirectly referencing an assembly through reflection, you can prevent the assembly from being trimmed with the `<TrimmerRootAssembly>` setting.</span></span> <span data-ttu-id="7ea29-130">次の例は、`System.Security` アセンブリという名前のアセンブリがトリミングされないようにする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7ea29-130">The following example shows how to prevent an assembly called `System.Security` assembly from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a><span data-ttu-id="7ea29-131">アプリをトリミングする - CLI</span><span class="sxs-lookup"><span data-stu-id="7ea29-131">Trim your app - CLI</span></span>

<span data-ttu-id="7ea29-132">[dotnet publish](../tools/dotnet-publish.md) コマンドを使用してアプリケーションをトリミングします。</span><span class="sxs-lookup"><span data-stu-id="7ea29-132">Trim your application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="7ea29-133">アプリを発行する場合、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-133">When you publish your app, set the following properties:</span></span>

- <span data-ttu-id="7ea29-134">特定のランタイムの自己完結型アプリとして発行する: `-r win-x64`</span><span class="sxs-lookup"><span data-stu-id="7ea29-134">Publish as a self-contained app for a specific runtime: `-r win-x64`</span></span>
- <span data-ttu-id="7ea29-135">トリミングを有効にする: `/p:PublishTrimmed=true`</span><span class="sxs-lookup"><span data-stu-id="7ea29-135">Enable trimming: `/p:PublishTrimmed=true`</span></span>

<span data-ttu-id="7ea29-136">次の例では、Windows 用のアプリを自己完結型として発行し、出力をトリミングします。</span><span class="sxs-lookup"><span data-stu-id="7ea29-136">The following example publishes an app for Windows as self-contained and trims the output.</span></span>

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

<span data-ttu-id="7ea29-137">次の例では、アグレッシブなトリミング モードでアプリを発行します。このモードでは、アセンブリ内の使用されていないコードがトリミングされ、トリマー警告が有効になります。</span><span class="sxs-lookup"><span data-stu-id="7ea29-137">The following example publishes an app in the aggressive trim mode where unused code within assemblies will be trimmed and trimmer warnings enabled.</span></span>

```xml
<PropertyGroup>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
    <TrimMode>link</TrimMode>
    <SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>
</PropertyGroup>
```

<span data-ttu-id="7ea29-138">詳細については、「[.NET Core CLI を使用して .NET Core アプリを発行する](deploy-with-cli.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ea29-138">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="trim-your-app---visual-studio"></a><span data-ttu-id="7ea29-139">アプリをトリミングする - Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7ea29-139">Trim your app - Visual Studio</span></span>

<span data-ttu-id="7ea29-140">Visual Studio を使用すると、アプリケーションの発行方法を制御する再利用可能な発行プロファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7ea29-140">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="7ea29-141">**[ソリューション エクスプローラー]** ペインで、発行するプロジェクトを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="7ea29-141">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="7ea29-142">**[発行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-142">Select **Publish...**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="右クリック メニューの [発行] オプションが強調表示されたソリューション エクスプローラー。":::

    <span data-ttu-id="7ea29-144">発行プロファイルがまだない場合は、指示に従って作成し、ターゲットの種類として **[フォルダー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-144">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="7ea29-145">**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-145">Choose **Edit**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="Visual Studio の発行プロファイルと [編集] ボタン":::

01. <span data-ttu-id="7ea29-147">**[プロファイル設定]** ダイアログで、次のオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-147">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="7ea29-148">**[配置モード]** を **[自己完結]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-148">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="7ea29-149">**[ターゲット ランタイム]** を発行先のプラットフォームに設定します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-149">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="7ea29-150">**[未使用のアセンブリをトリミングする (プレビュー)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-150">Select **Trim unused assemblies (in preview)**.</span></span>

    <span data-ttu-id="7ea29-151">**[保存]** を選択して設定を保存し、 **[発行]** ダイアログに戻ります。</span><span class="sxs-lookup"><span data-stu-id="7ea29-151">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="[配置モード]、[ターゲット ランタイム]、[未使用のアセンブリをトリミングする] オプションが強調表示されている [プロファイル設定] ダイアログ。":::

01. <span data-ttu-id="7ea29-153">**[発行]** を選択してトリミングされたアプリを発行します。</span><span class="sxs-lookup"><span data-stu-id="7ea29-153">Choose **Publish** to publish your app trimmed.</span></span>

<span data-ttu-id="7ea29-154">詳細については、[Visual Studio を使用した .NET Core アプリの発行](deploy-with-vs.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ea29-154">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="trim-your-app---visual-studio-for-mac"></a><span data-ttu-id="7ea29-155">アプリをトリミングする - Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="7ea29-155">Trim your app - Visual Studio for Mac</span></span>

<span data-ttu-id="7ea29-156">Visual Studio for Mac には、発行時にアプリをトリミングするオプションがありません。</span><span class="sxs-lookup"><span data-stu-id="7ea29-156">Visual Studio for Mac doesn't provide options to trim your app during publish.</span></span> <span data-ttu-id="7ea29-157">「[アプリをトリミングする - CLI](#trim-your-app---cli)」セクションの手順に従って手動で発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ea29-157">You'll need to publish manually by following the instructions from the [Trim your app - CLI](#trim-your-app---cli) section.</span></span> <span data-ttu-id="7ea29-158">詳細については、「[.NET Core CLI を使用して .NET Core アプリを発行する](deploy-with-cli.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ea29-158">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7ea29-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ea29-159">See also</span></span>

- <span data-ttu-id="7ea29-160">[.NET Core アプリケーションの配置](index.md)。</span><span class="sxs-lookup"><span data-stu-id="7ea29-160">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="7ea29-161">[.NET Core CLI を使用して .NET Core アプリを発行する](deploy-with-cli.md)。</span><span class="sxs-lookup"><span data-stu-id="7ea29-161">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="7ea29-162">[Visual Studio を使用して .NET Core アプリを発行する](deploy-with-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="7ea29-162">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="7ea29-163">[dotnet publish コマンド](../tools/dotnet-publish.md)。</span><span class="sxs-lookup"><span data-stu-id="7ea29-163">[dotnet publish command](../tools/dotnet-publish.md).</span></span>
