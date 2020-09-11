---
title: 単一ファイル アプリケーション
description: 単一ファイル アプリケーションの概要、およびこのアプリケーション デプロイ モデルの使用を検討すべき理由について説明します。
author: lakshanf
ms.author: lakshanf
ms.date: 08/28/2020
ms.openlocfilehash: 795ea98a9fd9d672b199eb2d9b24151340ef8246
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89495748"
---
# <a name="single-file-deployment-and-executable"></a><span data-ttu-id="654b2-103">単一ファイルの配置と実行可能ファイル</span><span class="sxs-lookup"><span data-stu-id="654b2-103">Single file deployment and executable</span></span>

<span data-ttu-id="654b2-104">アプリケーションに依存するすべてのファイルを単一のバイナリにバンドルすることで、アプリケーション開発者は、アプリケーションを単一ファイルとして配置し、配布することができます。</span><span class="sxs-lookup"><span data-stu-id="654b2-104">Bundling all application-dependent files into a single binary provides an application developer with the attractive option to deploy and distribute the application as a single file.</span></span> <span data-ttu-id="654b2-105">このデプロイ モデルは、.NET Core 3.0 以降で利用可能であり、.NET 5.0 で拡張されています。</span><span class="sxs-lookup"><span data-stu-id="654b2-105">This deployment model has been available since .NET Core 3.0 and has been enhanced in .NET 5.0.</span></span> <span data-ttu-id="654b2-106">以前の .NET Core 3.0 では、ユーザーが単一ファイル アプリを実行する場合、そのアプリケーションが実行される前に、まず .NET Core ホストがすべてのファイルを一時ディレクトリに抽出します。</span><span class="sxs-lookup"><span data-stu-id="654b2-106">Previously in .NET Core 3.0, when a user runs your single-file app, .NET Core host first extracts all files to a temporary directory before running the application.</span></span> <span data-ttu-id="654b2-107">.NET 5.0 では、アプリからファイルを抽出する必要がなく、コードを直接実行するので、このエクスペリエンスが向上しています。</span><span class="sxs-lookup"><span data-stu-id="654b2-107">.NET 5.0 improves this experience by directly running the code without the need to extract the files from the app.</span></span>

<span data-ttu-id="654b2-108">[フレームワークに依存するデプロイ モデル](index.md#publish-framework-dependent)と[自己完結型アプリケーション](index.md#publish-self-contained)の両方で、単一ファイルの配置が可能です。</span><span class="sxs-lookup"><span data-stu-id="654b2-108">Single File deployment is available for both the [framework-dependent deployment model](index.md#publish-framework-dependent) and [self-contained applications](index.md#publish-self-contained).</span></span> <span data-ttu-id="654b2-109">自己完結型アプリケーション内にある単一ファイルは、ランタイム ライブラリとフレームワーク ライブラリが含まれるため、大きなサイズとなります。</span><span class="sxs-lookup"><span data-stu-id="654b2-109">The size of the single file in a self-contained application will be large since it will include the runtime and the framework libraries.</span></span> <span data-ttu-id="654b2-110">単一ファイル配置オプションは、[ReadyToRun](../tools/dotnet-publish.md) と [Trim (.NET 5.0 の試験的な機能)](trim-self-contained.md) の各発行オプションと組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="654b2-110">The single file deployment option can be combined with [ReadyToRun](../tools/dotnet-publish.md) and [Trim (an experimental feature in .NET 5.0)](trim-self-contained.md) publish options.</span></span>

<span data-ttu-id="654b2-111">単一ファイルを使用する場合に把握しておくべきいくつかの注意事項があります。1 つめは、アプリケーションの場所を基準としてファイルを検索するときのパス情報の使用です。</span><span class="sxs-lookup"><span data-stu-id="654b2-111">There are some caveats that you need to be aware for single-file use, first of which is the use of path information to locate a file relative to the location of your application.</span></span> <span data-ttu-id="654b2-112"><xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> API は、空の文字列を返します。これは、メモリから読み込まれたアセンブリの既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="654b2-112">The <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> API will return an empty string, which is the default behavior for assemblies loaded from memory.</span></span> <span data-ttu-id="654b2-113">コンパイラは、ビルド時にこの API に対する警告を表示し、特定の動作について開発者に注意を促します。</span><span class="sxs-lookup"><span data-stu-id="654b2-113">The compiler will give a warning for this API during build time to alert the developer to the specific behavior.</span></span> <span data-ttu-id="654b2-114">アプリケーション ディレクトリへのパスが必要な場合、<xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> API は AppHost (単一ファイル バンドル自体) が存在するディレクトリを返します。</span><span class="sxs-lookup"><span data-stu-id="654b2-114">If the path to the application directory is needed, the <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> API will return the directory where the AppHost (the single-file bundle itself) resides.</span></span> <span data-ttu-id="654b2-115">マネージド C++ アプリケーションは、単一ファイルの配置には適していません。単一ファイルとの互換性を確保するには、アプリケーションを C# で記述することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="654b2-115">Managed C++ applications aren't well suited for single-file deployment and we recommend that you write applications in C# to be single-file compatible.</span></span>

<span data-ttu-id="654b2-116">既定では、単一ファイルを使用してネイティブ ライブラリをバンドルすることができません。</span><span class="sxs-lookup"><span data-stu-id="654b2-116">Single-file doesn't bundle native libraries by default.</span></span> <span data-ttu-id="654b2-117">Linux では、ランタイム ライブラリをバンドルに事前にリンクして、アプリケーション ネイティブ ライブラリのみを単一ファイル アプリと同じディレクトリに配置します。</span><span class="sxs-lookup"><span data-stu-id="654b2-117">On Linux, we prelink the runtime into the bundle and only application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="654b2-118">Windows では、ホスト コードのみを事前にリンクして、ランタイム ライブラリとアプリケーション ネイティブ ライブラリの両方を単一ファイル アプリと同じディレクトリに配置します。</span><span class="sxs-lookup"><span data-stu-id="654b2-118">On Windows, we prelink only the hosting code and both the runtime and application native libraries are deployed to the same directory as the single-file app.</span></span> <span data-ttu-id="654b2-119">これにより、優れたデバッグ エクスペリエンスが確保されます。それには、ネイティブ ファイルを単一ファイルから除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="654b2-119">This is to ensure a good debugging experience, which requires native files to be excluded from the single file.</span></span> <span data-ttu-id="654b2-120">単一ファイル バンドルにネイティブ ライブラリを含めるようにフラグ `IncludeNativeLibrariesForSelfExtract` を設定するオプションがありますが、これらのファイルは、単一ファイル アプリケーションが実行されるときに、クライアント コンピューターの一時ディレクトリに抽出されます。</span><span class="sxs-lookup"><span data-stu-id="654b2-120">There is an option to set a flag, `IncludeNativeLibrariesForSelfExtract`, to include native libraries in the single file bundle, but these files will be extracted to a temporary directory in the client machine when the single file application is run.</span></span>

## <a name="exclude-files-from-being-embedded"></a><span data-ttu-id="654b2-121">ファイルを埋め込み対象から除外する</span><span class="sxs-lookup"><span data-stu-id="654b2-121">Exclude files from being embedded</span></span>

<span data-ttu-id="654b2-122">次のメタデータを設定すると、特定のファイルを単一ファイルの埋め込み対象から明示的に除外することができます。</span><span class="sxs-lookup"><span data-stu-id="654b2-122">Certain files can be explicitly excluded from being embedded in the single-file by setting following metadata:</span></span>

```xml
<ExcludeFromSingleFile>true</ExcludeFromSingleFile>
```

<span data-ttu-id="654b2-123">たとえば、いくつかのファイルを発行ディレクトリに配置するものの、単一ファイルへのバンドルは行わない場合などです。</span><span class="sxs-lookup"><span data-stu-id="654b2-123">For example, to place some files in the publish directory but not bundle them in the single-file:</span></span>

```xml
<ItemGroup>
  <Content Update="Plugin.dll">
    <CopyToPublishDirectory>PreserveNewest</CopyToPublishDirectory>
    <ExcludeFromSingleFile>true</ExcludeFromSingleFile>
  </Content>
</ItemGroup>
```

## <a name="publish-a-single-file-app---cli"></a><span data-ttu-id="654b2-124">単一ファイル アプリを発行する - CLI</span><span class="sxs-lookup"><span data-stu-id="654b2-124">Publish a single file app - CLI</span></span>

<span data-ttu-id="654b2-125">[dotnet publish](../tools/dotnet-publish.md) コマンドを使用して、単一ファイル アプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="654b2-125">Publish a single file application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="654b2-126">アプリを発行する場合、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="654b2-126">When you publish your app, set the following properties:</span></span>

- <span data-ttu-id="654b2-127">特定のランタイムに対して発行する: `-r win-x64`</span><span class="sxs-lookup"><span data-stu-id="654b2-127">Publish for a specific runtime: `-r win-x64`</span></span>
- <span data-ttu-id="654b2-128">単一ファイルとして発行する: `-p:PublishSingleFile=true`</span><span class="sxs-lookup"><span data-stu-id="654b2-128">Publish as a single-file: `-p:PublishSingleFile=true`</span></span>

<span data-ttu-id="654b2-129">次の例では、Windows 用のアプリを自己完結型の単一ファイル アプリケーションとして発行します。</span><span class="sxs-lookup"><span data-stu-id="654b2-129">The following example publishes an app for Windows as a self-contained single file application.</span></span>

```dotnetcli
dotnet publish -r win-x64 -p:PublishSingleFile=true --self-contained true
```

<span data-ttu-id="654b2-130">次の例では、Linux 用のアプリをフレームワークに依存する単一ファイル アプリケーションとして発行します。</span><span class="sxs-lookup"><span data-stu-id="654b2-130">The following example publishes an app for Linux as a framework dependent single file application.</span></span>

```dotnetcli
dotnet publish -r linux-x64 -p:PublishSingleFile=true --self-contained false
```

<span data-ttu-id="654b2-131">詳細については、「[.NET Core CLI を使用して .NET Core アプリを発行する](deploy-with-cli.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="654b2-131">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio"></a><span data-ttu-id="654b2-132">単一ファイル アプリを発行する - Visual Studio</span><span class="sxs-lookup"><span data-stu-id="654b2-132">Publish a single file app - Visual Studio</span></span>

<span data-ttu-id="654b2-133">Visual Studio を使用すると、アプリケーションの発行方法を制御する再利用可能な発行プロファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="654b2-133">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="654b2-134">**[ソリューション エクスプローラー]** ペインで、発行するプロジェクトを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="654b2-134">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="654b2-135">**[発行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="654b2-135">Select **Publish**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-solution-explorer.png" alt-text="右クリック メニューの [発行] オプションが強調表示されたソリューション エクスプローラー。":::

    <span data-ttu-id="654b2-137">発行プロファイルがまだない場合は、指示に従って作成し、ターゲットの種類として **[フォルダー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="654b2-137">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="654b2-138">**[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="654b2-138">Choose **Edit**.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-edit-settings.png" alt-text="Visual Studio の発行プロファイルと [編集] ボタン":::

01. <span data-ttu-id="654b2-140">**[プロファイル設定]** ダイアログで、次のオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="654b2-140">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="654b2-141">**[配置モード]** を **[自己完結]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="654b2-141">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="654b2-142">**[ターゲット ランタイム]** を発行先のプラットフォームに設定します。</span><span class="sxs-lookup"><span data-stu-id="654b2-142">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="654b2-143">**[単一ファイルの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="654b2-143">Select **Produce single file**.</span></span>

    <span data-ttu-id="654b2-144">**[保存]** を選択して設定を保存し、 **[発行]** ダイアログに戻ります。</span><span class="sxs-lookup"><span data-stu-id="654b2-144">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/single-file/visual-studio-publish-single-file-properties.png" alt-text="[配置モード]、[ターゲット ランタイム]、[単一ファイルの作成] の各オプションが強調表示されている [プロファイル設定] ダイアログ。":::

01. <span data-ttu-id="654b2-146">**[発行]** を選択して、アプリを単一ファイルとして発行します。</span><span class="sxs-lookup"><span data-stu-id="654b2-146">Choose **Publish** to publish your app as a single file.</span></span>

<span data-ttu-id="654b2-147">詳細については、[Visual Studio を使用した .NET Core アプリの発行](deploy-with-vs.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="654b2-147">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="publish-a-single-file-app---visual-studio-for-mac"></a><span data-ttu-id="654b2-148">単一ファイル アプリを発行する - Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="654b2-148">Publish a single file app - Visual Studio for Mac</span></span>

<span data-ttu-id="654b2-149">Visual Studio for Mac には、アプリを単一ファイルとして発行するためのオプションがありません。</span><span class="sxs-lookup"><span data-stu-id="654b2-149">Visual Studio for Mac doesn't provide options to publish your app as a single file.</span></span> <span data-ttu-id="654b2-150">「[単一ファイル アプリを発行する - CLI](#publish-a-single-file-app---cli)」セクションの手順に従って、手動で発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="654b2-150">You'll need to publish manually by following the instructions from the [Publish a single file app - CLI](#publish-a-single-file-app---cli) section.</span></span> <span data-ttu-id="654b2-151">詳細については、「[.NET Core CLI を使用して .NET Core アプリを発行する](deploy-with-cli.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="654b2-151">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="654b2-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="654b2-152">See also</span></span>

- <span data-ttu-id="654b2-153">[.NET Core アプリケーションの配置](index.md)。</span><span class="sxs-lookup"><span data-stu-id="654b2-153">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="654b2-154">[.NET Core CLI を使用して .NET Core アプリを発行する](deploy-with-cli.md)。</span><span class="sxs-lookup"><span data-stu-id="654b2-154">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="654b2-155">[Visual Studio を使用して .NET Core アプリを発行する](deploy-with-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="654b2-155">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="654b2-156">[`dotnet publish` コマンド](../tools/dotnet-publish.md)。</span><span class="sxs-lookup"><span data-stu-id="654b2-156">[`dotnet publish` command](../tools/dotnet-publish.md).</span></span>
