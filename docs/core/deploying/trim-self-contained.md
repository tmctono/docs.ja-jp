---
title: 自己完結型アプリケーションのトリミング
description: 自己完結型アプリケーションをトリミングしてサイズを縮小する方法について説明します。 .NET Core は、自己完結型で公開されているアプリケーションでランタイムをバンドルし、通常は必要以上のランタイムを含んでいます。
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: bb8ac88c5e16b7fd20a7670e4ad76dbe4b44da1b
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242916"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="af16b-104">自己完結型の展開と実行可能ファイルのトリミング</span><span class="sxs-lookup"><span data-stu-id="af16b-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="af16b-105">自己完結型アプリケーションを公開する場合、.NET Core ランタイムにはアプリケーションもバンドルされます。</span><span class="sxs-lookup"><span data-stu-id="af16b-105">When publishing an application self-contained, the .NET Core runtime is bundled together with the application.</span></span> <span data-ttu-id="af16b-106">このバンドルにより、パッケージ アプリケーションに大量のコンテンツが追加されます。</span><span class="sxs-lookup"><span data-stu-id="af16b-106">This bundling adds a significant amount of content to your packaged application.</span></span> <span data-ttu-id="af16b-107">アプリケーションの展開では、多くの場合、サイズが重要な要素になります。</span><span class="sxs-lookup"><span data-stu-id="af16b-107">When it comes to deploying your application, size is often an important factor.</span></span> <span data-ttu-id="af16b-108">通常は、パッケージ アプリケーションのサイズをなるべく小さく保つことが、アプリケーション開発者の目標となります。</span><span class="sxs-lookup"><span data-stu-id="af16b-108">Keeping the size of the package application as small as possible is typically a goal for application developers.</span></span>

<span data-ttu-id="af16b-109">アプリケーションの複雑さによっては、アプリケーションの実行にランタイムのサブセットだけが必要となります。</span><span class="sxs-lookup"><span data-stu-id="af16b-109">Depending on the complexity of the application, only a subset of the runtime is required to run the application.</span></span> <span data-ttu-id="af16b-110">このようなランタイムの未使用部分は不要であり、パッケージ化されたアプリケーションから削除することができます。</span><span class="sxs-lookup"><span data-stu-id="af16b-110">These unused parts of the runtime are unnecessary and can be trimmed from the packaged application.</span></span>

<span data-ttu-id="af16b-111">トリミング機能は、アプリケーション バイナリを調べて、必要なランタイム アセンブリのグラフを検出し、構築することで機能します。</span><span class="sxs-lookup"><span data-stu-id="af16b-111">The trimming feature works by examining the application binaries to discover and build a graph of the required runtime assemblies.</span></span> <span data-ttu-id="af16b-112">参照されていないその他のランタイム アセンブリは除外されます。</span><span class="sxs-lookup"><span data-stu-id="af16b-112">The remaining runtime assemblies that aren't referenced are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="af16b-113">トリミングは .NET Core 3.1 の実験的な機能であり、自己完結型で公開されるアプリケーションで_のみ_使用できます。</span><span class="sxs-lookup"><span data-stu-id="af16b-113">Trimming is an experimental feature in .NET Core 3.1 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="prevent-assemblies-from-being-trimmed"></a><span data-ttu-id="af16b-114">アセンブリがトリミングされないようにする</span><span class="sxs-lookup"><span data-stu-id="af16b-114">Prevent assemblies from being trimmed</span></span>

<span data-ttu-id="af16b-115">トリミング機能が参照の検出に失敗するシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="af16b-115">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="af16b-116">たとえば、アプリケーションまたはアプリケーションによって参照されるライブラリから、ランタイム アセンブリに対してリフレクションが使用されている場合、アセンブリは直接参照されません。</span><span class="sxs-lookup"><span data-stu-id="af16b-116">For example, when reflection is used on a runtime assembly, either by your application or a library that is referenced by your application, the assembly isn't directly referenced.</span></span> <span data-ttu-id="af16b-117">このような間接参照はトリミングに認識されず、ライブラリは発行フォルダーから除外されます。</span><span class="sxs-lookup"><span data-stu-id="af16b-117">Trimming is unaware of these indirect references and would exclude the library from the published folder.</span></span>

<span data-ttu-id="af16b-118">コードからリフレクションを介して間接的にアセンブリを参照している場合は、`<TrimmerRootAssembly>` 設定を使用してアセンブリがトリミングされないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="af16b-118">When the code is indirectly referencing an assembly through reflection, you can prevent the assembly from being trimmed with the `<TrimmerRootAssembly>` setting.</span></span> <span data-ttu-id="af16b-119">次の例は、`System.Security` アセンブリという名前のアセンブリがトリミングされないようにする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="af16b-119">The following example shows how to prevent an assembly called `System.Security` assembly from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a><span data-ttu-id="af16b-120">アプリをトリミングする - CLI</span><span class="sxs-lookup"><span data-stu-id="af16b-120">Trim your app - CLI</span></span>

<span data-ttu-id="af16b-121">[dotnet publish](../tools/dotnet-publish.md) コマンドを使用してアプリケーションをトリミングします。</span><span class="sxs-lookup"><span data-stu-id="af16b-121">Trim your application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="af16b-122">アプリを発行するときは、次の 3 つの設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="af16b-122">When you publish your app, set the following three settings:</span></span>

- <span data-ttu-id="af16b-123">自己完結型として発行する: `--self-contained true`</span><span class="sxs-lookup"><span data-stu-id="af16b-123">Publish as self-contained: `--self-contained true`</span></span>
- <span data-ttu-id="af16b-124">単一ファイルの発行を無効にする: `-p:PublishSingleFile=false`</span><span class="sxs-lookup"><span data-stu-id="af16b-124">Disable single-file publishing: `-p:PublishSingleFile=false`</span></span>
- <span data-ttu-id="af16b-125">トリミングを有効にする: `p:PublishTrimmed=true`</span><span class="sxs-lookup"><span data-stu-id="af16b-125">Enable trimming: `p:PublishTrimmed=true`</span></span>

<span data-ttu-id="af16b-126">次の例では、Windows 10 用のアプリを自己完結型として発行し、出力をトリミングします。</span><span class="sxs-lookup"><span data-stu-id="af16b-126">The following example publishes an app for Windows 10 as self-contained and trims the output.</span></span>

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true -p:PublishSingleFile=false -p:PublishTrimmed=true
```

<span data-ttu-id="af16b-127">詳細については、「[.NET Core CLI を使用して .NET Core アプリを発行する](deploy-with-cli.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af16b-127">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="trim-your-app---visual-studio"></a><span data-ttu-id="af16b-128">アプリをトリミングする - Visual Studio</span><span class="sxs-lookup"><span data-stu-id="af16b-128">Trim your app - Visual Studio</span></span>

<span data-ttu-id="af16b-129">Visual Studio を使用すると、アプリケーションの発行方法を制御する再利用可能な発行プロファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="af16b-129">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="af16b-130">**[ソリューション エクスプローラー]** ペインで、発行するプロジェクトを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="af16b-130">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="af16b-131">**[発行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="af16b-131">Select **Publish...**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="右クリック メニューの [発行] オプションが強調表示されたソリューション エクスプローラー。":::

    <span data-ttu-id="af16b-133">発行プロファイルがまだない場合は、指示に従って作成し、ターゲットの種類として **[フォルダー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="af16b-133">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="af16b-134">**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="af16b-134">Choose **Edit**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="Visual Studio の発行プロファイルと [編集] ボタン":::

01. <span data-ttu-id="af16b-136">**[プロファイル設定]** ダイアログで、次のオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="af16b-136">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="af16b-137">**[配置モード]** を **[自己完結]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="af16b-137">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="af16b-138">**[ターゲット ランタイム]** を発行先のプラットフォームに設定します。</span><span class="sxs-lookup"><span data-stu-id="af16b-138">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="af16b-139">**[未使用のアセンブリをトリミングする (プレビュー)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="af16b-139">Select **Trim unused assemblies (in preview)**.</span></span>

    <span data-ttu-id="af16b-140">**[保存]** を選択して設定を保存し、 **[発行]** ダイアログに戻ります。</span><span class="sxs-lookup"><span data-stu-id="af16b-140">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="[配置モード]、[ターゲット ランタイム]、[未使用のアセンブリをトリミングする] オプションが強調表示されている [プロファイル設定] ダイアログ。":::

01. <span data-ttu-id="af16b-142">**[発行]** を選択してトリミングされたアプリを発行します。</span><span class="sxs-lookup"><span data-stu-id="af16b-142">Choose **Publish** to publish your app trimmed.</span></span>

<span data-ttu-id="af16b-143">詳細については、[Visual Studio を使用した .NET Core アプリの発行](deploy-with-vs.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="af16b-143">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="trim-your-app---visual-studio-for-mac"></a><span data-ttu-id="af16b-144">アプリをトリミングする - Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="af16b-144">Trim your app - Visual Studio for Mac</span></span>

<span data-ttu-id="af16b-145">Visual Studio for Mac には、発行時にアプリをトリミングするオプションがありません。</span><span class="sxs-lookup"><span data-stu-id="af16b-145">Visual Studio for Mac doesn't provide options to trim your app during publish.</span></span> <span data-ttu-id="af16b-146">「[アプリをトリミングする - CLI](#trim-your-app---cli)」セクションの手順に従って手動で発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af16b-146">You'll need to publish manually by following the instructions from the [Trim your app - CLI](#trim-your-app---cli) section.</span></span> <span data-ttu-id="af16b-147">詳細については、「[.NET Core CLI を使用して .NET Core アプリを発行する](deploy-with-cli.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af16b-147">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="af16b-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="af16b-148">See also</span></span>

- <span data-ttu-id="af16b-149">[.NET Core アプリケーションの配置](index.md)。</span><span class="sxs-lookup"><span data-stu-id="af16b-149">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="af16b-150">[.NET Core CLI を使用して .NET Core アプリを発行する](deploy-with-cli.md)。</span><span class="sxs-lookup"><span data-stu-id="af16b-150">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="af16b-151">[Visual Studio を使用して .NET Core アプリを発行する](deploy-with-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="af16b-151">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="af16b-152">[dotnet publish コマンド](../tools/dotnet-publish.md)。</span><span class="sxs-lookup"><span data-stu-id="af16b-152">[dotnet publish command](../tools/dotnet-publish.md).</span></span>
