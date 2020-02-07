---
title: .NET Core 3.0 の新機能
description: .NET Core 3.0 の新機能について説明します。
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 01/27/2020
ms.openlocfilehash: 92d97ca3efe761c879d0940a02342edb5a8180f0
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920378"
---
# <a name="whats-new-in-net-core-30"></a><span data-ttu-id="e3f4b-103">.NET Core 3.0 の新機能</span><span class="sxs-lookup"><span data-stu-id="e3f4b-103">What's new in .NET Core 3.0</span></span>

<span data-ttu-id="e3f4b-104">この記事では、.NET Core 3.0 の新機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-104">This article describes what is new in .NET Core 3.0.</span></span> <span data-ttu-id="e3f4b-105">最も大きな強化点の 1 つは、Windows デスクトップ アプリケーションのサポートです (Windows のみ)。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="e3f4b-106">.NET Core 3.0 SDK コンポーネントの Windows デスクトップを使用して、Windows フォームおよび Windows Presentation Foundation (WPF) アプリケーションを移植することができます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-106">By using the .NET Core 3.0 SDK component Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="e3f4b-107">誤解のないように言うと、Windows Desktop コンポーネントは Windows でのみサポートされており、Windows にのみ含まれています。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="e3f4b-108">詳細については、この記事で後述する「[Windows デスクトップ](#windows-desktop)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-108">For more information, see the [Windows desktop](#windows-desktop) section later in this article.</span></span>

<span data-ttu-id="e3f4b-109">.NET Core 3.0 では C# 8.0 のサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-109">.NET Core 3.0 adds support for C# 8.0.</span></span> <span data-ttu-id="e3f4b-110">**C# の拡張機能**では、[Visual Studio 2019 バージョン 16.3](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 以降、[Visual Studio for Mac 8.3](/visualstudio/mac/install-preview) 以降、または [Visual Studio Code](https://code.visualstudio.com/) を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-110">It's highly recommended that you use [Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or newer, [Visual Studio for Mac 8.3](/visualstudio/mac/install-preview) or newer, or [Visual Studio Code](https://code.visualstudio.com/) with the latest **C# extension**.</span></span>

<span data-ttu-id="e3f4b-111">[.NET Core 3.0 を今すぐダウンロード](https://aka.ms/netcore3download)して Windows、macOS、または Linux 上で使い始めましょう。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-111">[Download and get started with .NET Core 3.0](https://aka.ms/netcore3download) right now on Windows, macOS, or Linux.</span></span>

<span data-ttu-id="e3f4b-112">リリースの詳細については、[.NET Core 3.0 のアナウンス](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-112">For more information about the release, see the [.NET Core 3.0 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0/).</span></span>

<span data-ttu-id="e3f4b-113">.NET Core RC1 は、運用の準備ができていると Microsoft で見なされていたもので、完全にサポートされていました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-113">.NET Core RC1 was considered production ready by Microsoft and was fully supported.</span></span> <span data-ttu-id="e3f4b-114">プレビュー リリースを使用している場合は、サポートを継続するために RTM バージョンに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-114">If you're using a preview release, you must move to the RTM version for continued support.</span></span>

## <a name="language-improvements-c-80"></a><span data-ttu-id="e3f4b-115">C# 8.0 の言語自体の強化</span><span class="sxs-lookup"><span data-stu-id="e3f4b-115">Language improvements C# 8.0</span></span>

<span data-ttu-id="e3f4b-116">C#8.0 も、このリリースの一部であり、[null を許容する参照型の機能](../../csharp/tutorials/nullable-reference-types.md)、[非同期ストリーム](../../csharp/tutorials/generate-consume-asynchronous-stream.md)、[追加のパターン](../../csharp/tutorials/pattern-matching.md)が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-116">C# 8.0 is also part of this release, which includes the [nullable reference types](../../csharp/tutorials/nullable-reference-types.md) feature, [async streams](../../csharp/tutorials/generate-consume-asynchronous-stream.md), and [more patterns](../../csharp/tutorials/pattern-matching.md).</span></span> <span data-ttu-id="e3f4b-117">C# 8.0 の機能の詳細については、「[C# 8.0 の新機能](../../csharp/whats-new/csharp-8.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-117">For more information about C# 8.0 features, see [What's new in C# 8.0](../../csharp/whats-new/csharp-8.md).</span></span>

<span data-ttu-id="e3f4b-118">次のような API 機能をサポートするために、言語の機能強化が追加されました。これらについては、以下で詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-118">Language enhancements were added to support the following API features detailed below:</span></span>

- [<span data-ttu-id="e3f4b-119">範囲とインデックス</span><span class="sxs-lookup"><span data-stu-id="e3f4b-119">Ranges and indices</span></span>](#ranges-and-indices)
- [<span data-ttu-id="e3f4b-120">非同期ストリーム</span><span class="sxs-lookup"><span data-stu-id="e3f4b-120">Async streams</span></span>](#async-streams)

## <a name="net-standard-21"></a><span data-ttu-id="e3f4b-121">.NET Standard 2.1</span><span class="sxs-lookup"><span data-stu-id="e3f4b-121">.NET Standard 2.1</span></span>

<span data-ttu-id="e3f4b-122">.NET core 3.0 では **.NET Standard 2.1** が実装されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-122">.NET Core 3.0 implements **.NET Standard 2.1**.</span></span> <span data-ttu-id="e3f4b-123">しかし、既定の `dotnet new classlib` テンプレートでは、引き続き **.NET Standard 2.0** をターゲットとするプロジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-123">However, the default `dotnet new classlib` template generates a project that still targets **.NET Standard 2.0**.</span></span> <span data-ttu-id="e3f4b-124">**.NET Standard 2.1** をターゲットにするには、プロジェクト ファイルを編集して `TargetFramework` プロパティを `netstandard2.1` に変更します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-124">To target **.NET Standard 2.1**, edit your project file and change the `TargetFramework` property to `netstandard2.1`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="e3f4b-125">Visual Studio を使用している場合、Visual Studio 2017 では **.NET Standard 2.1** または **.NET Core 3.0** がサポートされていないため、[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) が必要です。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-125">If you're using Visual Studio, you need [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), as Visual Studio 2017 doesn't support **.NET Standard 2.1** or **.NET Core 3.0**.</span></span>

## <a name="compiledeploy"></a><span data-ttu-id="e3f4b-126">コンパイル/デプロイ</span><span class="sxs-lookup"><span data-stu-id="e3f4b-126">Compile/Deploy</span></span>

### <a name="default-executables"></a><span data-ttu-id="e3f4b-127">既定の実行可能ファイル</span><span class="sxs-lookup"><span data-stu-id="e3f4b-127">Default executables</span></span>

<span data-ttu-id="e3f4b-128">.NET Core では、既定で[フレームワーク依存の実行可能ファイル](../deploying/index.md#framework-dependent-executables-fde)が作成されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-128">.NET Core now builds [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="e3f4b-129">この動作は、グローバルにインストールされているバージョンの .NET Core を使用するアプリケーションの新機能です。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-129">This behavior is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="e3f4b-130">以前は、[自己完結型の配置](../deploying/index.md#self-contained-deployments-scd)でのみ実行可能ファイルが生成されました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-130">Previously, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="e3f4b-131">`dotnet build` または `dotnet publish` の実行中に、使用している SDK の環境およびプラットフォームと一致する実行可能ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-131">During `dotnet build` or `dotnet publish`, an executable is created that matches the environment and platform of the SDK you're using.</span></span> <span data-ttu-id="e3f4b-132">これらの実行可能ファイルでは、次のような他のネイティブ実行可能ファイルと同じことを期待できます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-132">You can expect the same things with these executables as you would other native executables, such as:</span></span>

- <span data-ttu-id="e3f4b-133">実行可能ファイルはダブルクリックすることができます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-133">You can double-click on the executable.</span></span>
- <span data-ttu-id="e3f4b-134">Windows では `myapp.exe`、Linux と macOS では`./myapp` など、コマンド プロンプトからアプリケーションを直接起動できます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-134">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

### <a name="single-file-executables"></a><span data-ttu-id="e3f4b-135">単一ファイルの実行可能ファイル</span><span class="sxs-lookup"><span data-stu-id="e3f4b-135">Single-file executables</span></span>

<span data-ttu-id="e3f4b-136">`dotnet publish` コマンドは、プラットフォーム固有の単一ファイルの実行可能ファイルにアプリをパッケージ化することをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-136">The `dotnet publish` command supports packaging your app into a platform-specific single-file executable.</span></span> <span data-ttu-id="e3f4b-137">実行可能ファイルは自己展開型であり、アプリの実行に必要なすべての依存関係 (ネイティブを含む) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-137">The executable is self-extracting and contains all dependencies (including native) that are required to run your app.</span></span> <span data-ttu-id="e3f4b-138">アプリを初めて実行すると、アプリ名とビルド ID に基づいてアプリケーションがディレクトリに抽出されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-138">When the app is first run, the application is extracted to a directory based on the app name and build identifier.</span></span> <span data-ttu-id="e3f4b-139">アプリケーションを再実行すると、起動は速くなります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-139">Startup is faster when the application is run again.</span></span> <span data-ttu-id="e3f4b-140">新しいバージョンが使用されない限り、アプリケーションは自身を 2 回抽出する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-140">The application doesn't need to extract itself a second time unless a new version was used.</span></span>

<span data-ttu-id="e3f4b-141">単一ファイルの実行可能ファイルを発行するには、プロジェクト内またはコマンド ラインで `dotnet publish` コマンドを使用して `PublishSingleFile` を設定します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-141">To publish a single-file executable, set the `PublishSingleFile` in your project or on the command line with the `dotnet publish` command:</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>win10-x64</RuntimeIdentifier>
  <PublishSingleFile>true</PublishSingleFile>
</PropertyGroup>
```

<span data-ttu-id="e3f4b-142">\- または -</span><span class="sxs-lookup"><span data-stu-id="e3f4b-142">-or-</span></span>

```dotnetcli
dotnet publish -r win10-x64 -p:PublishSingleFile=true
```

<span data-ttu-id="e3f4b-143">単一ファイルの発行の詳細については、[単一ファイル バンドラー設計のドキュメント](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-143">For more information about single-file publishing, see the [single-file bundler design document](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).</span></span>

### <a name="assembly-linking"></a><span data-ttu-id="e3f4b-144">アセンブリのリンク</span><span class="sxs-lookup"><span data-stu-id="e3f4b-144">Assembly linking</span></span>

<span data-ttu-id="e3f4b-145">.NET Core 3.0 SDK に付属するツールを使うと、IL を分析し、未使用のアセンブリをトリミングすることによって、アプリのサイズを減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-145">The .NET core 3.0 SDK comes with a tool that can reduce the size of apps by analyzing IL and trimming unused assemblies.</span></span>

<span data-ttu-id="e3f4b-146">自己完結型アプリには、コードの実行に必要なものがすべて含まれるので、ホスト コンピューターに .NET をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-146">Self-contained apps include everything needed to run your code, without requiring .NET to be installed on the host computer.</span></span> <span data-ttu-id="e3f4b-147">ただし、多くの場合、アプリが機能するにはフレームワークの小さなサブセットのみが必要であり、使用されていない他のライブラリは削除できます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-147">However, many times the app only requires a small subset of the framework to function, and other unused libraries could be removed.</span></span>

<span data-ttu-id="e3f4b-148">.NET Core には、[IL リンカー](https://github.com/mono/linker) ツールを使ってアプリの IL をスキャンする設定が含まれるようになっています。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-148">.NET Core now includes a setting that will use the [IL linker](https://github.com/mono/linker) tool to scan the IL of your app.</span></span> <span data-ttu-id="e3f4b-149">このツールでは、必要なコードが検出された後、使われていないライブラリがトリミングされます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-149">This tool detects what code is required, and then trims unused libraries.</span></span> <span data-ttu-id="e3f4b-150">このツールを使うと、一部のアプリの展開サイズを大幅に削減できます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-150">This tool can significantly reduce the deployment size of some apps.</span></span>

<span data-ttu-id="e3f4b-151">このツールを有効にするには、プロジェクトで `<PublishTrimmed>` 設定を追加し、自己完結型アプリを発行します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-151">To enable this tool, add the `<PublishTrimmed>` setting in your project and publish a self-contained app:</span></span>

```xml
<PropertyGroup>
  <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

```dotnetcli
dotnet publish -r <rid> -c Release
```

<span data-ttu-id="e3f4b-152">たとえば、含まれている基本的な "hello world" という新しいコンソール プロジェクト テンプレートは、発行されるときに、サイズが約 70 MB になります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-152">As an example, the basic "hello world" new console project template that is included, when published, hits about 70 MB in size.</span></span> <span data-ttu-id="e3f4b-153">`<PublishTrimmed>` を使うことにより、そのサイズが約 30 MB に減ります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-153">By using `<PublishTrimmed>`, that size is reduced to about 30 MB.</span></span>

<span data-ttu-id="e3f4b-154">考慮すべき重要なこととして、リフレクションまたは関連する動的機能を使っているアプリケーションまたはフレームワーク (ASP.NET Core と WPF を含む) では、トリミングすると壊れることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-154">It's important to consider that applications or frameworks (including ASP.NET Core and WPF) that use reflection or related dynamic features, will often break when trimmed.</span></span> <span data-ttu-id="e3f4b-155">このような破損が発生するのは、リンカーはこの動的な動作を認識しておらず、リフレクションに必要なフレームワークの種類を判断できないためです。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-155">This breakage occurs because the linker doesn't know about this dynamic behavior and can't determine which framework types are required for reflection.</span></span> <span data-ttu-id="e3f4b-156">IL リンカー ツールは、このシナリオを認識するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-156">The IL Linker tool can be configured to be aware of this scenario.</span></span>

<span data-ttu-id="e3f4b-157">何よりも、必ずトリミング後のアプリをテストしてください。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-157">Above all else, be sure to test your app after trimming.</span></span>

<span data-ttu-id="e3f4b-158">IL リンカー ツールについて詳しくは、[ドキュメント](https://aka.ms/dotnet-illink)または [mono/linker]( https://github.com/mono/linker) リポジトリをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-158">For more information about the IL Linker tool, see the [documentation](https://aka.ms/dotnet-illink) or visit the [mono/linker]( https://github.com/mono/linker) repo.</span></span>

### <a name="tiered-compilation"></a><span data-ttu-id="e3f4b-159">階層型コンパイル</span><span class="sxs-lookup"><span data-stu-id="e3f4b-159">Tiered compilation</span></span>

<span data-ttu-id="e3f4b-160">.NET Core 3.0 では、[階層型コンパイル](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation-guide.md) (TC) が既定で有効になりました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-160">[Tiered compilation](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation-guide.md) (TC) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="e3f4b-161">この機能により、ランタイムが状況に応じて Just-In-Time (JIT) コンパイラを使用してパフォーマンスを向上できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-161">This feature enables the runtime to more adaptively use the just-in-time (JIT) compiler to achieve better performance.</span></span>

<span data-ttu-id="e3f4b-162">階層型コンパイルの主な利点は、2 とおりの JIT メソッドを与えることです。低品質で高速の階層と高品質で低速の階層です。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-162">The main benefit of tiered compilation is to provide two ways of jitting methods: in a lower-quality-but-faster tier or a higher-quality-but-slower tier.</span></span> <span data-ttu-id="e3f4b-163">品質とは、メソッドの最適化の程度を指します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-163">The quality refers to how well the method is optimized.</span></span> <span data-ttu-id="e3f4b-164">TC は、起動から安定した状態まで、さまざまな実行段階を経るときに、アプリケーションのパフォーマンスを向上するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-164">TC helps to improve the performance of an application as it goes through various stages of execution, from startup through steady state.</span></span> <span data-ttu-id="e3f4b-165">階層型コンパイルが無効になっていると、すべてのメソッドが起動より安定した状態に偏る 1 つの方法でコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-165">When tiered compilation is disabled, every method is compiled in a single way that's biased to steady-state performance over startup performance.</span></span>

<span data-ttu-id="e3f4b-166">TC が有効になっていると、アプリの起動時、メソッド コンパイルは次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-166">When TC is enabled, the following behavior applies for method compilation when an app starts up:</span></span>

- <span data-ttu-id="e3f4b-167">メソッドに Ahead Of Time コンパイル済みコード ([ReadyToRun](#readytorun-images)) がある場合、事前に生成されたコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-167">If the method has ahead-of-time-compiled code, or [ReadyToRun](#readytorun-images), the pregenerated code is used.</span></span>
- <span data-ttu-id="e3f4b-168">ない場合、メソッドは JIT になります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-168">Otherwise, the method is jitted.</span></span> <span data-ttu-id="e3f4b-169">通常、これらのメソッドは値の型を超えるジェネリックです。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-169">Typically, these methods are generics over value types.</span></span>
  - <span data-ttu-id="e3f4b-170">*クイック JIT* では、低品質 (最適化の程度が低い) コードが高速で生成されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-170">*Quick JIT* produces lower-quality (or less optimized) code more quickly.</span></span> <span data-ttu-id="e3f4b-171">.NET Core 3.0 では、ループを含まないメソッドに対してクイック JIT が既定で有効になり、起動時に優先されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-171">In .NET Core 3.0, Quick JIT is enabled by default for methods that don't contain loops and is preferred during startup.</span></span>
  - <span data-ttu-id="e3f4b-172">完全最適化 JIT では、より高品質な (またはより最適化された) コードがより低速で生成されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-172">The fully optimizing JIT produces higher-quality (or more optimized) code more slowly.</span></span> <span data-ttu-id="e3f4b-173">クイック JIT が使用されないメソッド (たとえば、メソッドが属性 <xref:System.Runtime.CompilerServices.MethodImplOptions.AggressiveOptimization?displayProperty=nameWithType> を持つ場合) では、完全最適化 JIT が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-173">For methods where Quick JIT would not be used (for example, if the method is attributed with <xref:System.Runtime.CompilerServices.MethodImplOptions.AggressiveOptimization?displayProperty=nameWithType>), the fully optimizing JIT is used.</span></span>

<span data-ttu-id="e3f4b-174">頻繁に呼び出されるメソッドについては、JIT コンパイラにより最終的に、バックグラウンドで完全に最適化されたコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-174">For frequently called methods, the just-in-time compiler eventually creates fully optimized code in the background.</span></span> <span data-ttu-id="e3f4b-175">この最適化されたコードがそのメソッドに対して事前コンパイルされたコードに取って代わります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-175">The optimized code then replaces the pre-compiled code for that method.</span></span>

<span data-ttu-id="e3f4b-176">クイック JIT によって生成されたコードは、実行速度が低下したり、より多くのメモリが割り当てられたり、より多くのスタック領域を使用したりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-176">Code generated by Quick JIT may run slower, allocate more memory, or use more stack space.</span></span> <span data-ttu-id="e3f4b-177">問題がある場合、プロジェクト ファイルのこの MSBuild プロパティを使用し、クイック JIT を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-177">If there are issues, you can disabled Quick JIT using this MSBuild property in the project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

<span data-ttu-id="e3f4b-178">TC を完全に無効にするには、プロジェクト ファイルでこの MSBuild プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-178">To disable TC completely, use this MSBuild property in your project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="e3f4b-179">プロジェクト ファイルでこれらの設定を変更するとき、場合によっては、新しい設定を反映させる目的でクリーン ビルドを実行する必要があります (`obj` ディレクトリと `bin` ディレクトリを削除し、リビルドします)。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-179">If you change these settings in the project file, you may need to perform a clean build for the new settings to be reflected (delete the `obj` and `bin` directories and rebuild).</span></span>

<span data-ttu-id="e3f4b-180">ランタイム時のコンパイル構成に関する詳細については、「[コンパイルのランタイム構成オプション](../run-time-config/compilation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-180">For more information about configuring compilation at run time, see [Run-time configuration options for compilation](../run-time-config/compilation.md).</span></span>

### <a name="readytorun-images"></a><span data-ttu-id="e3f4b-181">ReadyToRun イメージ</span><span class="sxs-lookup"><span data-stu-id="e3f4b-181">ReadyToRun images</span></span>

<span data-ttu-id="e3f4b-182">アプリケーション アセンブリを ReadyToRun (R2R) 形式としてコンパイルすることで、.NET Core アプリケーションの起動時間を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-182">You can improve the startup time of your .NET Core application by compiling your application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="e3f4b-183">R2R とは、Ahead-Of-Time (AOT) コンパイルの一種です。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-183">R2R is a form of ahead-of-time (AOT) compilation.</span></span>

<span data-ttu-id="e3f4b-184">R2R バイナリでは、アプリケーションの読み込み時に Just-In-Time (JIT) コンパイラで行う必要がある作業量を減らすことにより、起動時のパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-184">R2R binaries improve startup performance by reducing the amount of work the just-in-time (JIT) compiler needs to do as your application loads.</span></span> <span data-ttu-id="e3f4b-185">バイナリには、JIT で生成されるものと似たネイティブ コードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-185">The binaries contain similar native code compared to what the JIT would produce.</span></span> <span data-ttu-id="e3f4b-186">ただし、R2R バイナリは、中間言語 (IL) コード (一部のシナリオでまだ必要です) と同じコードのネイティブ バージョンの両方が含まれるため、大きくなります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-186">However, R2R binaries are larger because they contain both intermediate language (IL) code, which is still needed for some scenarios, and the native version of the same code.</span></span> <span data-ttu-id="e3f4b-187">R2R は、Linux x64 や Windows x64 などの特定のランタイム環境 (RID) をターゲットとする自己完結型アプリを発行するときにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-187">R2R is only available when you publish a self-contained app that targets specific runtime environments (RID) such as Linux x64 or Windows x64.</span></span>

<span data-ttu-id="e3f4b-188">ReadyToRun としてプロジェクトをコンパイルするには、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-188">To compile your project as ReadyToRun, do the following:</span></span>

01. <span data-ttu-id="e3f4b-189">`<PublishReadyToRun>` 設定をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-189">Add the `<PublishReadyToRun>` setting to your project:</span></span>

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

01. <span data-ttu-id="e3f4b-190">自己完結型アプリを発行します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-190">Publish a self-contained app.</span></span> <span data-ttu-id="e3f4b-191">たとえば、次のコマンドでは、Windows の 64 ビット版向けの自己完結型アプリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-191">For example, this command creates a self-contained app for the 64-bit version of Windows:</span></span>

    ```dotnetcli
    dotnet publish -c Release -r win-x64 --self-contained
    ```

#### <a name="cross-platformarchitecture-restrictions"></a><span data-ttu-id="e3f4b-192">クロス プラットフォーム/アーキテクチャの制限</span><span class="sxs-lookup"><span data-stu-id="e3f4b-192">Cross platform/architecture restrictions</span></span>

<span data-ttu-id="e3f4b-193">現在、ReadyToRun コンパイラではクロスターゲットはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-193">The ReadyToRun compiler doesn't currently support cross-targeting.</span></span> <span data-ttu-id="e3f4b-194">特定のターゲットに対してコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-194">You must compile on a given target.</span></span> <span data-ttu-id="e3f4b-195">たとえば、Windows x64 用の R2R イメージが必要な場合は、その環境で publish コマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-195">For example, if you want R2R images for Windows x64, you need to run the publish command on that environment.</span></span>

<span data-ttu-id="e3f4b-196">クロスターゲットに対する例外:</span><span class="sxs-lookup"><span data-stu-id="e3f4b-196">Exceptions to cross-targeting:</span></span>

- <span data-ttu-id="e3f4b-197">Windows x64 を使って、Windows ARM32、ARM64、x86 のイメージをコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-197">Windows x64 can be used to compile Windows ARM32, ARM64, and x86 images.</span></span>
- <span data-ttu-id="e3f4b-198">Windows x86 を使って、Windows ARM32 のイメージをコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-198">Windows x86 can be used to compile Windows ARM32 images.</span></span>
- <span data-ttu-id="e3f4b-199">Linux x64 を使って、Linux ARM32 と ARM64 のイメージをコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-199">Linux x64 can be used to compile Linux ARM32 and ARM64 images.</span></span>

## <a name="runtimesdk"></a><span data-ttu-id="e3f4b-200">ランタイム/SDK</span><span class="sxs-lookup"><span data-stu-id="e3f4b-200">Runtime/SDK</span></span>

### <a name="major-version-runtime-roll-forward"></a><span data-ttu-id="e3f4b-201">メジャーバージョン ランタイムのロールフォワード</span><span class="sxs-lookup"><span data-stu-id="e3f4b-201">Major-version runtime roll forward</span></span>

<span data-ttu-id="e3f4b-202">.NET Core 3.0 では、アプリを最新メジャー バージョンの .NET Core にロールフォワードできるようにするオプトイン機能が導入されました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-202">.NET Core 3.0 introduces an opt-in feature that allows your app to roll forward to the latest major version of .NET Core.</span></span> <span data-ttu-id="e3f4b-203">さらに、ロールフォワードをアプリに適用する方法を制御する新しい設定が追加されました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-203">Additionally, a new setting has been added to control how roll forward is applied to your app.</span></span> <span data-ttu-id="e3f4b-204">これは、以下の方法で構成できます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-204">This can be configured in the following ways:</span></span>

- <span data-ttu-id="e3f4b-205">プロジェクト ファイルのプロパティ: `RollForward`</span><span class="sxs-lookup"><span data-stu-id="e3f4b-205">Project file property: `RollForward`</span></span>
- <span data-ttu-id="e3f4b-206">ランタイム構成ファイルのプロパティ: `rollForward`</span><span class="sxs-lookup"><span data-stu-id="e3f4b-206">Run-time configuration file property: `rollForward`</span></span>
- <span data-ttu-id="e3f4b-207">環境変数: `DOTNET_ROLL_FORWARD`</span><span class="sxs-lookup"><span data-stu-id="e3f4b-207">Environment variable: `DOTNET_ROLL_FORWARD`</span></span>
- <span data-ttu-id="e3f4b-208">コマンドライン引数: `--roll-forward`</span><span class="sxs-lookup"><span data-stu-id="e3f4b-208">Command-line argument: `--roll-forward`</span></span>

<span data-ttu-id="e3f4b-209">次の値のいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-209">One of the following values must be specified.</span></span> <span data-ttu-id="e3f4b-210">設定を省略すると、**Minor** が既定値になります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-210">If the setting is omitted, **Minor** is the default.</span></span>

- <span data-ttu-id="e3f4b-211">**LatestPatch**</span><span class="sxs-lookup"><span data-stu-id="e3f4b-211">**LatestPatch**</span></span>\
<span data-ttu-id="e3f4b-212">最新のパッチ バージョンにロールフォワードします。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-212">Roll forward to the highest patch version.</span></span> <span data-ttu-id="e3f4b-213">これで、マイナー バージョンのロールフォワードが無効になります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-213">This disables minor version roll forward.</span></span>
- <span data-ttu-id="e3f4b-214">**Minor**</span><span class="sxs-lookup"><span data-stu-id="e3f4b-214">**Minor**</span></span>\
<span data-ttu-id="e3f4b-215">要求されたマイナー バージョンが見つからない場合は、それよりも高い最小マイナー バージョンにロールフォワードします。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-215">Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="e3f4b-216">要求されたマイナー バージョンが存在する場合は、**LatestPatch** ポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-216">If the requested minor version is present, then the **LatestPatch** policy is used.</span></span>
- <span data-ttu-id="e3f4b-217">**Major**</span><span class="sxs-lookup"><span data-stu-id="e3f4b-217">**Major**</span></span>\
<span data-ttu-id="e3f4b-218">要求されたメジャー バージョンが見つからない場合は、それよりも高い最小メジャー バージョンで最小マイナー バージョンにロールフォワードします。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-218">Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="e3f4b-219">要求されたメジャー バージョンが存在する場合は、**Minor** ポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-219">If the requested major version is present, then the **Minor** policy is used.</span></span>
- <span data-ttu-id="e3f4b-220">**LatestMinor**</span><span class="sxs-lookup"><span data-stu-id="e3f4b-220">**LatestMinor**</span></span>\
<span data-ttu-id="e3f4b-221">要求されたマイナー バージョンが存在する場合でも、最上位のマイナー バージョンにロールフォワードします。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-221">Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="e3f4b-222">コンポーネント ホスティング シナリオを対象としています。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-222">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="e3f4b-223">**LatestMajor**</span><span class="sxs-lookup"><span data-stu-id="e3f4b-223">**LatestMajor**</span></span>\
<span data-ttu-id="e3f4b-224">要求されたメジャーが存在する場合でも、最上位のメジャー バージョンで最上位のマイナー バージョンにロールフォワードします。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-224">Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="e3f4b-225">コンポーネント ホスティング シナリオを対象としています。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-225">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="e3f4b-226">**Disable**</span><span class="sxs-lookup"><span data-stu-id="e3f4b-226">**Disable**</span></span>\
<span data-ttu-id="e3f4b-227">ロールフォワードしません。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-227">Don't roll forward.</span></span> <span data-ttu-id="e3f4b-228">指定されたバージョンにのみバインドします。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-228">Only bind to specified version.</span></span> <span data-ttu-id="e3f4b-229">このポリシーは、最新のパッチにロールフォワードする機能が無効になるため、一般的な使用にはお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-229">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="e3f4b-230">この値はテスト用にのみ推奨されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-230">This value is only recommended for testing.</span></span>

<span data-ttu-id="e3f4b-231">**Disable** の設定を除くすべての設定では、利用できる最新のパッチ バージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-231">Besides the **Disable** setting, all settings will use the highest available patch version.</span></span>

### <a name="build-copies-dependencies"></a><span data-ttu-id="e3f4b-232">ビルドによる依存関係のコピー</span><span class="sxs-lookup"><span data-stu-id="e3f4b-232">Build copies dependencies</span></span>

<span data-ttu-id="e3f4b-233">`dotnet build` コマンドでは、アプリケーションの NuGet 依存関係が NuGet キャッシュからビルド出力フォルダーにコピーされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-233">The `dotnet build` command now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="e3f4b-234">以前は、依存関係のコピーは `dotnet publish` の一部としてのみ行われていました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-234">Previously, dependencies were only copied as part of `dotnet publish`.</span></span>

<span data-ttu-id="e3f4b-235">リンクや razor ページの発行など、まだ発行が必要な操作がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-235">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>

### <a name="local-tools"></a><span data-ttu-id="e3f4b-236">ローカル ツール</span><span class="sxs-lookup"><span data-stu-id="e3f4b-236">Local tools</span></span>

<span data-ttu-id="e3f4b-237">.NET Core 3.0 にローカル ツールが導入されました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-237">.NET Core 3.0 introduces local tools.</span></span> <span data-ttu-id="e3f4b-238">ローカル ツールは[グローバル ツール](../tools/global-tools.md)に似ていますが、ディスク上の特定の場所に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-238">Local tools are similar to [global tools](../tools/global-tools.md) but are associated with a particular location on disk.</span></span> <span data-ttu-id="e3f4b-239">ローカル ツールはグローバルには使用できず、NuGet パッケージとして配布されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-239">Local tools aren't available globally and are distributed as NuGet packages.</span></span>

> [!WARNING]
> <span data-ttu-id="e3f4b-240">.NET Core 3.0 Preview 1 で `dotnet tool restore` や `dotnet tool install` の実行などのローカル ツールを試した場合は、ローカル ツールのキャッシュ フォルダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-240">If you tried local tools in .NET Core 3.0 Preview 1, such as running `dotnet tool restore` or `dotnet tool install`, delete the local tools cache folder.</span></span> <span data-ttu-id="e3f4b-241">そうしないと、ローカル ツールは新しいリリースで動作しません。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-241">Otherwise, local tools won't work on any newer release.</span></span> <span data-ttu-id="e3f4b-242">このフォルダーは次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-242">This folder is located at:</span></span>
>
> <span data-ttu-id="e3f4b-243">macOS、Linux の場合: `rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="e3f4b-243">On macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
> <span data-ttu-id="e3f4b-244">Windows の場合: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="e3f4b-244">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>

<span data-ttu-id="e3f4b-245">ローカル ツールは、現在のディレクトリ内のマニフェスト ファイル名 `dotnet-tools.json` に依存しています。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-245">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="e3f4b-246">このマニフェスト ファイルは、ツールをそのフォルダー下で使用できるように定義します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-246">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="e3f4b-247">コードを使用するすべての人が確実に同じツールを復元して使用できるように、自分のコードと一緒にマニフェスト ファイルを配布することができます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-247">You can distribute the manifest file with your code to ensure that anyone who works with your code can restore and use the same tools.</span></span>

<span data-ttu-id="e3f4b-248">グローバル ツールとローカル ツールの両方で、ランタイムの互換バージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-248">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="e3f4b-249">現在 NuGet.org 上にある多くのツールは、.NET Core Runtime 2.1 をターゲットとしています。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-249">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="e3f4b-250">グローバルにまたはローカルにこのようなツールをインストールするには、[NET Core 2.1 ランタイム](https://dotnet.microsoft.com/download/dotnet-core/2.1)をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-250">To install these tools globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

### <a name="new-globaljson-options"></a><span data-ttu-id="e3f4b-251">新しい global.json オプション</span><span class="sxs-lookup"><span data-stu-id="e3f4b-251">New global.json options</span></span>

<span data-ttu-id="e3f4b-252">*global.json* ファイルには、どのバージョンの .NET Core SD を使用するか定義する際にさらなる柔軟性をもたらす新しいオプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-252">The *global.json* file has new options that provide more flexibility when you're trying to define which version of the .NET Core SDK is used.</span></span> <span data-ttu-id="e3f4b-253">新しいオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-253">The new options are:</span></span>

- <span data-ttu-id="e3f4b-254">`allowPrerelease`:使用する SDK バージョンを選択するときに、SDK リゾルバーでプレリリース バージョンを考慮する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-254">`allowPrerelease`: Indicates whether the SDK resolver should consider prerelease versions when selecting the SDK version to use.</span></span>
- <span data-ttu-id="e3f4b-255">`rollForward`:SDK バージョンを選択するときに使用するロールフォワード ポリシーを示します。特定の SDK バージョンが不足している場合のフォールバックとして、またはより新しいバージョンを使用するためのディレクティブとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-255">`rollForward`: Indicates the roll-forward policy to use when selecting an SDK version, either as a fallback when a specific SDK version is missing or as a directive to use a higher version.</span></span>

<span data-ttu-id="e3f4b-256">既定値、サポートされている値、新しい照合ルールなどの変更について詳しくは、「[global.json の概要](../tools/global-json.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-256">For more information about the changes including default values, supported values, and new matching rules, see [global.json overview](../tools/global-json.md).</span></span>

### <a name="smaller-garbage-collection-heap-sizes"></a><span data-ttu-id="e3f4b-257">小さいガベージ コレクションのヒープ サイズ</span><span class="sxs-lookup"><span data-stu-id="e3f4b-257">Smaller Garbage Collection heap sizes</span></span>

<span data-ttu-id="e3f4b-258">ガベージ コレクターの既定のヒープ サイズが縮小され、.NET Core のメモリ使用量が減少しました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-258">The Garbage Collector's default heap size has been reduced resulting in .NET Core using less memory.</span></span> <span data-ttu-id="e3f4b-259">この変更は、最新のプロセッサ キャッシュ サイズでは、世代 0 の割り当て予算に合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-259">This change better aligns with the generation 0 allocation budget with modern processor cache sizes.</span></span>

### <a name="garbage-collection-large-page-support"></a><span data-ttu-id="e3f4b-260">ガベージ コレクションのラージ ページのサポート</span><span class="sxs-lookup"><span data-stu-id="e3f4b-260">Garbage Collection Large Page support</span></span>

<span data-ttu-id="e3f4b-261">ラージ ページ (Linux ではヒュージ ページとも呼ばれます) は、オペレーティング システムがネイティブ ページ サイズ (多くの場合は 4K) よりも大きいメモリ領域を確立して、このようなラージ ページを要求するアプリケーションのパフォーマンスを向上できる機能です。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-261">Large Pages (also known as Huge Pages on Linux) is a feature where the operating system is able to establish memory regions larger than the native page size (often 4K) to improve performance of the application requesting these large pages.</span></span>

<span data-ttu-id="e3f4b-262">Windows 上でラージ ページを割り当てることを選択するオプトイン機能として、**GCLargePages** 設定を使用してガベージ コレクターを構成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-262">The Garbage Collector can now be configured with the **GCLargePages** setting as an opt-in feature to choose to allocate large pages on Windows.</span></span>

## <a name="windows-desktop--com"></a><span data-ttu-id="e3f4b-263">Windows デスクトップ & COM</span><span class="sxs-lookup"><span data-stu-id="e3f4b-263">Windows Desktop & COM</span></span>

### <a name="net-core-sdk-windows-installer"></a><span data-ttu-id="e3f4b-264">.NET Core SDK Windows インストーラー</span><span class="sxs-lookup"><span data-stu-id="e3f4b-264">.NET Core SDK Windows Installer</span></span>

<span data-ttu-id="e3f4b-265">Windows 用の MSI インストーラーは、.NET Core 3.0 から変更されました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-265">The MSI installer for Windows has changed starting with .NET Core 3.0.</span></span> <span data-ttu-id="e3f4b-266">SDK インストーラーは、SDK 機能帯リリースのアップグレードを実行するようになります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-266">The SDK installers will now upgrade SDK feature-band releases in place.</span></span> <span data-ttu-id="e3f4b-267">機能帯は、バージョン番号の "*パッチ*" セクションの *100* 番台のグループで定義されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-267">Feature bands are defined in the *hundreds* groups in the *patch* section of the version number.</span></span> <span data-ttu-id="e3f4b-268">たとえば、**3.0._101_** と **3.0._201_** は 2 つの異なる機能帯のバージョンですが、**3.0._101_** と **3.0._199_** は同じ機能帯に含まれます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-268">For example, **3.0._101_** and **3.0._201_** are versions in two different feature bands while **3.0._101_** and **3.0._199_** are in the same feature band.</span></span> <span data-ttu-id="e3f4b-269">また、.NET Core SDK **3.0._101_** をインストールすると、.NET Core SDK **3.0._100_** が存在する場合はマシンから削除されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-269">And, when .NET Core SDK **3.0._101_** is installed, .NET Core SDK **3.0._100_** will be removed from the machine if it exists.</span></span> <span data-ttu-id="e3f4b-270">同じマシンに .NET Core SDK **3.0._200_** をインストールすると、.NET Core SDK **3.0._101_** は削除されません。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-270">When .NET Core SDK **3.0._200_** is installed on the same machine, .NET Core SDK **3.0._101_** won't be removed.</span></span>

<span data-ttu-id="e3f4b-271">バージョン管理の詳細については、「[.NET Core をバージョン管理する方法の概要](../versions/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-271">For more information about versioning, see [Overview of how .NET Core is versioned](../versions/index.md).</span></span>

### <a name="windows-desktop"></a><span data-ttu-id="e3f4b-272">Windows デスクトップ</span><span class="sxs-lookup"><span data-stu-id="e3f4b-272">Windows desktop</span></span>

<span data-ttu-id="e3f4b-273">.NET Core 3.0 は、Windows Presentation Foundation (WPF) および Windows フォームを使用した Windows デスクトップ アプリケーションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-273">.NET Core 3.0 supports Windows desktop applications using Windows Presentation Foundation (WPF) and Windows Forms.</span></span> <span data-ttu-id="e3f4b-274">これらのフレームワークでは、Windows UI XAML ライブラリ (WinUI) の最新のコントロールと Fluent スタイルを [XAML Islands](/windows/uwp/xaml-platform/xaml-host-controls) 経由で使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-274">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="e3f4b-275">Windows デスクトップ コンポーネントは、Windows .NET Core 3.0 SDK の一部です。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-275">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="e3f4b-276">次の `dotnet` コマンドを使用して、新しい WPF または Windows フォーム アプリケーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-276">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```dotnetcli
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="e3f4b-277">Visual Studio 2019 では、.NET Core 3.0 Windows フォームと WPF 用に、**新しいプロジェクト** テンプレートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-277">Visual Studio 2019 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span>

<span data-ttu-id="e3f4b-278">既存の .NET Framework アプリケーションを移植する方法の詳細については、[WPF プロジェクトの移植](../../desktop-wpf/migration/convert-project-from-net-framework.md)と [Windows フォーム プロジェクトの移植](../porting/winforms.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-278">For more information about how to port an existing .NET Framework application, see [Port WPF projects](../../desktop-wpf/migration/convert-project-from-net-framework.md) and [Port Windows Forms projects](../porting/winforms.md).</span></span>

#### <a name="winforms-high-dpi"></a><span data-ttu-id="e3f4b-279">WinForms の高 DPI</span><span class="sxs-lookup"><span data-stu-id="e3f4b-279">WinForms high DPI</span></span>

<span data-ttu-id="e3f4b-280">.NET Core Windows フォーム アプリケーションでは、<xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType> を使用して高 DPI モードを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-280">.NET Core Windows Forms applications can set high DPI mode with <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e3f4b-281">`Application.Run` の前の `App.Manifest` や P/Invoke などの他の方法で設定を指定しない限り、`SetHighDpiMode` メソッドによって、対応する高 DPI モードが設定されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-281">The `SetHighDpiMode` method sets the corresponding high DPI mode unless the setting has been set by other means like `App.Manifest` or P/Invoke before `Application.Run`.</span></span>

<span data-ttu-id="e3f4b-282"><xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> 列挙型で表される `highDpiMode` に使用できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-282">The possible `highDpiMode` values, as expressed by the <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> enum are:</span></span>

- `DpiUnaware`
- `SystemAware`
- `PerMonitor`
- `PerMonitorV2`
- `DpiUnawareGdiScaled`

<span data-ttu-id="e3f4b-283">高 DPI モードの詳細については、「[Windows での高 DPI デスクトップ アプリケーション開発](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-283">For more information about high DPI modes, see [High DPI Desktop Application Development on Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span></span>

### <a name="create-com-components"></a><span data-ttu-id="e3f4b-284">COM コンポーネントの作成</span><span class="sxs-lookup"><span data-stu-id="e3f4b-284">Create COM components</span></span>

<span data-ttu-id="e3f4b-285">Windows 上で、COM 呼び出し可能なマネージ コンポーネントを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-285">On Windows, you can now create COM-callable managed components.</span></span> <span data-ttu-id="e3f4b-286">この機能は、COM アドイン モデルに .NET Core を使用する場合と、.NET Framework にパリティを提供する場合にも重要です。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-286">This capability is critical to use .NET Core with COM add-in models and also to provide parity with .NET Framework.</span></span>

<span data-ttu-id="e3f4b-287">COM サーバーとして *mscoree.dll* が使用されていた .NET Framework とは異なり、COM コンポーネントを構築すると、.NET Core によって *bin* ディレクトリにネイティブ ランチャー DLL が追加されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-287">Unlike .NET Framework where the *mscoree.dll* was used as the COM server, .NET Core will add a native launcher dll to the *bin* directory when you build your COM component.</span></span>

<span data-ttu-id="e3f4b-288">COM コンポーネントを作成して使用する方法の例については、[COM のデモ](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-288">For an example of how to create a COM component and consume it, see the [COM Demo](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span></span>

### <a name="windows-native-interop"></a><span data-ttu-id="e3f4b-289">Windows のネイティブ相互運用機能</span><span class="sxs-lookup"><span data-stu-id="e3f4b-289">Windows Native Interop</span></span>

<span data-ttu-id="e3f4b-290">Windows では、フラット C API、COM、および WinRT の形式で、質の高いネイティブ API を提供しています。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-290">Windows offers a rich native API in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="e3f4b-291">.NET Core は **P/Invoke** をサポートしますが、.NET Core 3.0 では **COM API の CoCreate** と **WinRT API のアクティブ化**を行う機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-291">While .NET Core supports **P/Invoke**, .NET Core 3.0 adds the ability to **CoCreate COM APIs** and **Activate WinRT APIs**.</span></span> <span data-ttu-id="e3f4b-292">コード例については、[Excel のデモ](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-292">For a code example, see the [Excel Demo](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>

### <a name="msix-deployment"></a><span data-ttu-id="e3f4b-293">MSIX のデプロイ</span><span class="sxs-lookup"><span data-stu-id="e3f4b-293">MSIX Deployment</span></span>

<span data-ttu-id="e3f4b-294">[MSIX](https://docs.microsoft.com/windows/msix/) は新しい Windows アプリケーション パッケージ形式です。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-294">[MSIX](https://docs.microsoft.com/windows/msix/) is a new Windows application package format.</span></span> <span data-ttu-id="e3f4b-295">これは、Windows 10 に .NET Core 3.0 のデスクトップ アプリケーションを展開するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-295">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="e3f4b-296">[Windows アプリケーション パッケージ プロジェクト](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net)は、Visual Studio 2019 で使用でき、[自己完結型](../deploying/index.md#self-contained-deployments-scd)の .NET Core アプリケーションを使用して、MSIX パッケージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-296">The [Windows Application Packaging Project](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019, allows you to create MSIX packages with [self-contained](../deploying/index.md#self-contained-deployments-scd) .NET Core applications.</span></span>

<span data-ttu-id="e3f4b-297">.NET Core プロジェクト ファイルの `<RuntimeIdentifiers>` プロパティで、サポートされているランタイムを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-297">The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>

```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="linux-improvements"></a><span data-ttu-id="e3f4b-298">Linux の機能強化</span><span class="sxs-lookup"><span data-stu-id="e3f4b-298">Linux improvements</span></span>

### <a name="serialport-for-linux"></a><span data-ttu-id="e3f4b-299">Linux 用 SerialPort</span><span class="sxs-lookup"><span data-stu-id="e3f4b-299">SerialPort for Linux</span></span>

<span data-ttu-id="e3f4b-300">.Net Core 3.0 では、Linux 上の <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> に対する基本サポートを提供しています。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-300">.NET Core 3.0 provides basic support for <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="e3f4b-301">以前の .NET Core では、Windows 上の `SerialPort` の使用のみをサポートしていました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-301">Previously, .NET Core only supported using `SerialPort` on Windows.</span></span>

<span data-ttu-id="e3f4b-302">Linux 上のシリアル ポートの制限付きサポートの詳細については、[GitHub 問題 #33146](https://github.com/dotnet/corefx/issues/33146) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-302">For more information about the limited support for the serial port on Linux, see [GitHub issue #33146](https://github.com/dotnet/corefx/issues/33146).</span></span>

### <a name="docker-and-cgroup-memory-limits"></a><span data-ttu-id="e3f4b-303">Docker と cgroup のメモリ制限</span><span class="sxs-lookup"><span data-stu-id="e3f4b-303">Docker and cgroup memory Limits</span></span>

<span data-ttu-id="e3f4b-304">Linux 上の Docker を使用した .NET Core 3.0 の実行は、cgroup のメモリ制限と適切に連携するようになりました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-304">Running .NET Core 3.0 on Linux with Docker works better with cgroup memory limits.</span></span> <span data-ttu-id="e3f4b-305">`docker run -m` のように、メモリ制限を使用して Docker コンテナーを実行すると、.NET Core の動作が変わります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-305">Running a Docker container with memory limits, such as with `docker run -m`, changes how .NET Core behaves.</span></span>

- <span data-ttu-id="e3f4b-306">既定のガベージ コレクター (GC) ヒープ サイズ: 最大 20 MB、またはコンテナーのメモリ制限の 75%。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-306">Default Garbage Collector (GC) heap size: maximum of 20 mb or 75% of the memory limit on the container.</span></span>
- <span data-ttu-id="e3f4b-307">明示的なサイズは、cgroup 制限の絶対数または割合として設定できます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-307">Explicit size can be set as an absolute number or percentage of cgroup limit.</span></span>
- <span data-ttu-id="e3f4b-308">GC ヒープあたりの最小予約セグメント サイズは 16 MB です。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-308">Minimum reserved segment size per GC heap is 16 mb.</span></span> <span data-ttu-id="e3f4b-309">このサイズによって、マシン上に作成されるヒープ数が減ります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-309">This size reduces the number of heaps that are created on machines.</span></span>

### <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="e3f4b-310">Raspberry Pi の GPIO サポート</span><span class="sxs-lookup"><span data-stu-id="e3f4b-310">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="e3f4b-311">GPIO プログラミングに使用できる 2 つのパッケージが NuGet にリリースされました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-311">Two packages have been released to NuGet that you can use for GPIO programming:</span></span>

- [<span data-ttu-id="e3f4b-312">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="e3f4b-312">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio)
- [<span data-ttu-id="e3f4b-313">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="e3f4b-313">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings)

<span data-ttu-id="e3f4b-314">GPIO パッケージには、*GPIO*、*SPI*、*I2C*、および *PWM* デバイス用の API が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-314">The GPIO packages include APIs for *GPIO*, *SPI*, *I2C*, and *PWM* devices.</span></span> <span data-ttu-id="e3f4b-315">IoT バインディング パッケージにはデバイス バインディングが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-315">The IoT bindings package includes device bindings.</span></span> <span data-ttu-id="e3f4b-316">詳細については、[デバイス GitHub リポジトリ](https://github.com/dotnet/iot/blob/master/src/devices/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-316">For more information, see the [devices GitHub repo](https://github.com/dotnet/iot/blob/master/src/devices/).</span></span>

### <a name="arm64-linux-support"></a><span data-ttu-id="e3f4b-317">ARM64 Linux のサポート</span><span class="sxs-lookup"><span data-stu-id="e3f4b-317">ARM64 Linux support</span></span>

<span data-ttu-id="e3f4b-318">.NET Core 3.0 では、Linux 用の ARM64 のサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-318">.NET Core 3.0 adds support for ARM64 for Linux.</span></span> <span data-ttu-id="e3f4b-319">現在、ARM64 の主なユース ケースは、IoT シナリオを使用しています。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-319">The primary use case for ARM64 is currently with IoT scenarios.</span></span> <span data-ttu-id="e3f4b-320">詳細については、[.NET Core ARM64 の状態](https://github.com/dotnet/announcements/issues/82)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-320">For more information, see [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82).</span></span>

<span data-ttu-id="e3f4b-321">[ARM64 上の .NET Core 用の Docker イメージ](https://hub.docker.com/r/microsoft/dotnet/)は、Alpine、Debian、および Ubuntu に使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-321">[Docker images for .NET Core on ARM64](https://hub.docker.com/r/microsoft/dotnet/) are available for Alpine, Debian, and Ubuntu.</span></span>

> [!NOTE]
> <span data-ttu-id="e3f4b-322">**ARM64** Windows のサポートはまだ使用できません。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-322">**ARM64** Windows support isn't yet available.</span></span>

## <a name="security"></a><span data-ttu-id="e3f4b-323">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="e3f4b-323">Security</span></span>

### <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="e3f4b-324">Linux 上の TLS 1.3 と OpenSSL 1.1.1</span><span class="sxs-lookup"><span data-stu-id="e3f4b-324">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="e3f4b-325">.NET Core では、特定の環境で使用できるようになったときに、[OpenSSL 1.1.1 の TLS 1.3 のサポート](https://www.openssl.org/blog/blog/2018/09/11/release111/)を利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-325">.NET Core now takes advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it's available in a given environment.</span></span> <span data-ttu-id="e3f4b-326">TLS 1.3 の場合:</span><span class="sxs-lookup"><span data-stu-id="e3f4b-326">With TLS 1.3:</span></span>

- <span data-ttu-id="e3f4b-327">クライアントとサーバー間に必要なラウンド トリップ回数が減るため、接続時間が改善されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-327">Connection times are improved with reduced round trips required between the client and server.</span></span>
- <span data-ttu-id="e3f4b-328">古い安全ではないさまざまな暗号化アルゴリズムが削除されたので、セキュリティが強化されました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-328">Improved security because of the removal of various obsolete and insecure cryptographic algorithms.</span></span>

<span data-ttu-id="e3f4b-329">使用できる場合、.NET Core 3.0 では Linux システム上で **OpenSSL 1.1.1**、**OpenSSL 1.1.0**、または **OpenSSL 1.0.2** が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-329">When available, .NET Core 3.0 uses **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** on a Linux system.</span></span> <span data-ttu-id="e3f4b-330">**OpenSSL 1.1.1** が使用できる場合、<xref:System.Net.Security.SslStream?displayProperty=nameWithType> 型と <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> 型の両方が **TLS 1.3** を使用します (クライアントとサーバーの両方が **TLS 1.3** をサポートしている場合)。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-330">When **OpenSSL 1.1.1** is available, both <xref:System.Net.Security.SslStream?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> types will use **TLS 1.3** (assuming both the client and server support **TLS 1.3**).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3f4b-331">Windows と macOS はまだ **TLS 1.3** をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-331">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="e3f4b-332">サポートされるようになったら、.NET Core 3.0 はこれらのオペレーティング システムで **TLS 1.3** をサポートする予定です。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-332">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

<span data-ttu-id="e3f4b-333">次の C# 8.0 の例は、<https://www.cloudflare.com> に接続している Ubuntu 18.10 上の .NET Core 3.0 を示しています。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-333">The following C# 8.0 example demonstrates .NET Core 3.0 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

[!code-csharp[TLSExample](~/samples/snippets/core/whats-new/whats-new-in-30/cs/TLS.cs#TLS)]

### <a name="cryptography-ciphers"></a><span data-ttu-id="e3f4b-334">暗号化の暗号</span><span class="sxs-lookup"><span data-stu-id="e3f4b-334">Cryptography ciphers</span></span>

<span data-ttu-id="e3f4b-335">.NET 3.0 では、**AES-GCM** および **AES-CCM** の暗号のサポートが追加され、それぞれ <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> および <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> で実装されています。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-335">.NET 3.0 adds support for **AES-GCM** and **AES-CCM** ciphers, implemented with <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> and <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> respectively.</span></span> <span data-ttu-id="e3f4b-336">これらのアルゴリズムは、いずれも [Authenticated Encryption with Association Data (AEAD) アルゴリズム](https://en.wikipedia.org/wiki/Authenticated_encryption)です。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-336">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption).</span></span>

<span data-ttu-id="e3f4b-337">次のコードは、`AesGcm` 暗号を使用してランダム データの暗号化と復号化を行う例です。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-337">The following code demonstrates using `AesGcm` cipher to encrypt and decrypt random data.</span></span>

[!code-csharp[AesGcm](~/samples/snippets/core/whats-new/whats-new-in-30/cs/Cipher.cs#AesGcm)]

### <a name="cryptographic-key-importexport"></a><span data-ttu-id="e3f4b-338">暗号化キーのインポート/エクスポート</span><span class="sxs-lookup"><span data-stu-id="e3f4b-338">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="e3f4b-339">.NET Core 3.0 は、標準形式からの非対称の公開キーと秘密キーのインポートとエクスポートをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-339">.NET Core 3.0 supports the import and export of asymmetric public and private keys from standard formats.</span></span> <span data-ttu-id="e3f4b-340">X.509 証明書を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-340">You don't need to use an X.509 certificate.</span></span>

<span data-ttu-id="e3f4b-341">*RSA*、*DSA*、*ECDsa*、*ECDiffieHellman* などのすべてのキー種類は、以下の形式をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-341">All key types, such as *RSA*, *DSA*, *ECDsa*, and *ECDiffieHellman*, support the following formats:</span></span>

- <span data-ttu-id="e3f4b-342">**公開キー**</span><span class="sxs-lookup"><span data-stu-id="e3f4b-342">**Public Key**</span></span>
  - <span data-ttu-id="e3f4b-343">X.509 SubjectPublicKeyInfo</span><span class="sxs-lookup"><span data-stu-id="e3f4b-343">X.509 SubjectPublicKeyInfo</span></span>

- <span data-ttu-id="e3f4b-344">**秘密キー**</span><span class="sxs-lookup"><span data-stu-id="e3f4b-344">**Private key**</span></span>
  - <span data-ttu-id="e3f4b-345">PKCS#8 PrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="e3f4b-345">PKCS#8 PrivateKeyInfo</span></span>
  - <span data-ttu-id="e3f4b-346">PKCS#8 EncryptedPrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="e3f4b-346">PKCS#8 EncryptedPrivateKeyInfo</span></span>

<span data-ttu-id="e3f4b-347">RSA キーは以下もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-347">RSA keys also support:</span></span>

- <span data-ttu-id="e3f4b-348">**公開キー**</span><span class="sxs-lookup"><span data-stu-id="e3f4b-348">**Public Key**</span></span>
  - <span data-ttu-id="e3f4b-349">PKCS#1 RSAPublicKey</span><span class="sxs-lookup"><span data-stu-id="e3f4b-349">PKCS#1 RSAPublicKey</span></span>

- <span data-ttu-id="e3f4b-350">**秘密キー**</span><span class="sxs-lookup"><span data-stu-id="e3f4b-350">**Private key**</span></span>
  - <span data-ttu-id="e3f4b-351">PKCS#1 RSAPrivateKey</span><span class="sxs-lookup"><span data-stu-id="e3f4b-351">PKCS#1 RSAPrivateKey</span></span>

<span data-ttu-id="e3f4b-352">エクスポートメソッドからは、DER でエンコードされたバイナリ データが生成され、インポート メソッドもそのようなデータを期待します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-352">The export methods produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="e3f4b-353">キーがテキストに適した PEM 形式で格納されている場合、呼び出し元は import メソッドを呼び出す前にコンテンツを base64 でデコードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-353">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

[!code-csharp[RSA](~/samples/snippets/core/whats-new/whats-new-in-30/cs/RSA.cs#Rsa)]

<span data-ttu-id="e3f4b-354">**PKCS#8** ファイルは <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> を使用して検査できます。また、 **PFX/PKCS#12** ファイルは <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType> を使用して検査できます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-354">**PKCS#8** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> and **PFX/PKCS#12** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e3f4b-355">**PFX/PKCS#12** ファイルは <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType> を使用して操作できます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-355">**PFX/PKCS#12** files can be manipulated with <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span></span>

## <a name="net-core-30-api-changes"></a><span data-ttu-id="e3f4b-356">.NET Core 3.0 API の変更</span><span class="sxs-lookup"><span data-stu-id="e3f4b-356">.NET Core 3.0 API changes</span></span>

### <a name="ranges-and-indices"></a><span data-ttu-id="e3f4b-357">範囲とインデックス</span><span class="sxs-lookup"><span data-stu-id="e3f4b-357">Ranges and indices</span></span>

<span data-ttu-id="e3f4b-358">新しい <xref:System.Index?displayProperty=nameWithType> 型はインデックス作成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-358">The new <xref:System.Index?displayProperty=nameWithType> type can be used for indexing.</span></span> <span data-ttu-id="e3f4b-359">先頭からカウントする `int` か、末尾からカウントするプレフィックス `^` 演算子 (C#) を使用して作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-359">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="e3f4b-360">また、<xref:System.Range?displayProperty=nameWithType> 型もあります。これは開始値と終了値の 2 つの `Index` 値から構成され、`x..y` の範囲式 (C#) で記述できます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-360">There's also the <xref:System.Range?displayProperty=nameWithType> type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="e3f4b-361">これで、`Range` を使用してインデックスを付け、スライスを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-361">You can then index with a `Range`, which produces a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

<span data-ttu-id="e3f4b-362">詳細については、[範囲とインデックスのチュートリアル](../../csharp/tutorials/ranges-indexes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-362">For more information, see the [ranges and indices tutorial](../../csharp/tutorials/ranges-indexes.md).</span></span>

### <a name="async-streams"></a><span data-ttu-id="e3f4b-363">非同期ストリーム</span><span class="sxs-lookup"><span data-stu-id="e3f4b-363">Async streams</span></span>

<span data-ttu-id="e3f4b-364"><xref:System.Collections.Generic.IAsyncEnumerable%601> 型は、<xref:System.Collections.Generic.IEnumerable%601> の新しい非同期バージョンです。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-364">The <xref:System.Collections.Generic.IAsyncEnumerable%601> type is a new asynchronous version of <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="e3f4b-365">この言語では、その要素を使用するために `IAsyncEnumerable<T>` よりも `await foreach` を行い、要素を生成するために `yield return` を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-365">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="e3f4b-366">非同期ストリームの生成の両方の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-366">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="e3f4b-367">`foreach` ステートメントは非同期であり、`yield return` を使用して呼び出し元の非同期ストリームを生成します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-367">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="e3f4b-368">(`yield return` を使用する) このパターンは、非同期ストリームを生成するモデルに推奨されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-368">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result;
    }
}
```

<span data-ttu-id="e3f4b-369">`await foreach` を実行できるだけでなく、非同期反復子を作成することもできます。たとえば、`await` と`yield` の両方を行うことができる `IAsyncEnumerable/IAsyncEnumerator` を返す反復子です。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-369">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="e3f4b-370">破棄する必要があるオブジェクトの場合は、`Stream` や `Timer` など、さまざまな BCL 型が実装する `IAsyncDisposable` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-370">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

<span data-ttu-id="e3f4b-371">詳細については、[非同期ストリームのチュートリアル](../../csharp/tutorials/generate-consume-asynchronous-stream.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-371">For more information, see the [async streams tutorial](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span></span>

### <a name="ieee-floating-point"></a><span data-ttu-id="e3f4b-372">IEEE 浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="e3f4b-372">IEEE Floating-point</span></span>

<span data-ttu-id="e3f4b-373">浮動小数点 API は、[IEEE 754-2008 リビジョン](https://en.wikipedia.org/wiki/IEEE_754-2008_revision)に準拠するように更新されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-373">Floating point APIs are being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="e3f4b-374">これらの変更の目的は、すべての**必要な**操作を公開し、それらの動作が IEEE 仕様に準拠していることを保証することです。浮動小数点の改良の詳細については、「[Floating-Point Parsing and Formatting improvements in .NET Core 3.0 (.NET Core 3.0 の浮動小数点の解析と形式の改良)](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/)」のブログ記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-374">The goal of these changes is to expose all **required** operations and ensure that they're behaviorally compliant with the IEEE spec. For more information about floating-point improvements, see the [Floating-Point Parsing and Formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.</span></span>

<span data-ttu-id="e3f4b-375">次のような解析および書式設定の修正があります。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-375">Parsing and formatting fixes include:</span></span>

- <span data-ttu-id="e3f4b-376">任意の長さの入力を正しく解析して丸める。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-376">Correctly parse and round inputs of any length.</span></span>
- <span data-ttu-id="e3f4b-377">負のゼロを正しく解析して書式設定する。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-377">Correctly parse and format negative zero.</span></span>
- <span data-ttu-id="e3f4b-378">大文字と小文字を区別しないチェックを実行し、可能な場合には省略可能な先行の `+` を許可することで、`Infinity` と `NaN` を正しく解析する。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-378">Correctly parse `Infinity` and `NaN` by doing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="e3f4b-379">新しい <xref:System.Math?displayProperty=nameWithType> API には以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-379">New <xref:System.Math?displayProperty=nameWithType> APIs include:</span></span>

- <span data-ttu-id="e3f4b-380"><xref:System.Math.BitIncrement(System.Double)> と <xref:System.Math.BitDecrement(System.Double)></span><span class="sxs-lookup"><span data-stu-id="e3f4b-380"><xref:System.Math.BitIncrement(System.Double)> and <xref:System.Math.BitDecrement(System.Double)></span></span>\
<span data-ttu-id="e3f4b-381">`nextUp` および `nextDown` の IEEE 演算に相当します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-381">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="e3f4b-382">入力よりも大きいか小さいかを比較する最小の浮動小数点をそれぞれ返します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-382">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="e3f4b-383">たとえば、`Math.BitIncrement(0.0)` は `double.Epsilon` を返します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-383">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

- <span data-ttu-id="e3f4b-384"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> と <xref:System.Math.MinMagnitude(System.Double,System.Double)></span><span class="sxs-lookup"><span data-stu-id="e3f4b-384"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> and <xref:System.Math.MinMagnitude(System.Double,System.Double)></span></span>\
<span data-ttu-id="e3f4b-385">`maxNumMag` および `minNumMag` の IEEE 演算に相当します。2 つの入力の大きさがより大きいまたはより小さい値をそれぞれ返します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-385">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="e3f4b-386">たとえば、`Math.MaxMagnitude(2.0, -3.0)` は `-3.0` を返します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-386">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

- <xref:System.Math.ILogB(System.Double)>\
<span data-ttu-id="e3f4b-387">整数値を返す `logB` IEEE 演算に相当します。入力パラメーターの 2 を底とする積分対数を返します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-387">Corresponds to the `logB` IEEE operation that returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="e3f4b-388">このメソッドは実質的に `floor(log2(x))` と同じですが、最小限の丸め誤差で実行されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-388">This method is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

- <xref:System.Math.ScaleB(System.Double,System.Int32)>\
<span data-ttu-id="e3f4b-389">整数値を受け取る `scaleB` IEEE 演算に相当します。これは実質的に `x * pow(2, n)` と同じですが、最小限の丸め誤差で実行されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-389">Corresponds to the `scaleB` IEEE operation that takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

- <xref:System.Math.Log2(System.Double)>\
<span data-ttu-id="e3f4b-390">`log2` IEEE 演算に相当します。2 を底とする対数を返します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-390">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="e3f4b-391">丸め誤差を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-391">It minimizes rounding error.</span></span>

- <xref:System.Math.FusedMultiplyAdd(System.Double,System.Double,System.Double)>\
<span data-ttu-id="e3f4b-392">`fma` IEEE 演算に相当します。融合型積和演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-392">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="e3f4b-393">つまり、単一操作として `(x * y) + z` を実行することで、丸め誤差を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-393">That is, it does `(x * y) + z` as a single operation, thereby minimizing the rounding error.</span></span> <span data-ttu-id="e3f4b-394">たとえば、`FusedMultiplyAdd(1e308, 2.0, -1e308)` では `1e308` が返されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-394">An example is `FusedMultiplyAdd(1e308, 2.0, -1e308)`, which returns `1e308`.</span></span> <span data-ttu-id="e3f4b-395">正規の `(1e308 * 2.0) - 1e308` は `double.PositiveInfinity` を返します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-395">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

- <xref:System.Math.CopySign(System.Double,System.Double)>\
<span data-ttu-id="e3f4b-396">`copySign` IEEE 演算に相当します。`x` の値を返しますが、`y` の符号と共に返されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-396">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

### <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="e3f4b-397">.NET プラットフォーム依存性</span><span class="sxs-lookup"><span data-stu-id="e3f4b-397">.NET Platform-Dependent Intrinsics</span></span>

<span data-ttu-id="e3f4b-398">特定のパフォーマンス指向 CPU 命令 (**SIMD** や **ビット操作命令**セット) にアクセスできるようにする API が追加されました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-398">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="e3f4b-399">これらの命令は、データを並列で効率的に処理するといった、特定のシナリオでパフォーマンスを大幅に向上するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-399">These instructions can help achieve significant performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span>

<span data-ttu-id="e3f4b-400">.NET ライブラリでは、必要に応じて、パフォーマンスを向上するためにこれらの命令が使用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-400">Where appropriate, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="e3f4b-401">詳細については、「[.NET Platform Dependent Intrinsics (.NET プラットフォーム依存性)](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-401">For more information, see [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md).</span></span>

### <a name="improved-net-core-version-apis"></a><span data-ttu-id="e3f4b-402">強化された .NET Core バージョン API</span><span class="sxs-lookup"><span data-stu-id="e3f4b-402">Improved .NET Core Version APIs</span></span>

<span data-ttu-id="e3f4b-403">.NET Core 3.0 以降、.NET Core に提供されているバージョン API から、期待どおりの情報が返されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-403">Starting with .NET Core 3.0, the version APIs provided with .NET Core now return the information you expect.</span></span> <span data-ttu-id="e3f4b-404">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-404">For example:</span></span>

```csharp
System.Console.WriteLine($"Environment.Version: {System.Environment.Version}");

// Old result
//   Environment.Version: 4.0.30319.42000
//
// New result
//   Environment.Version: 3.0.0
```

```csharp
System.Console.WriteLine($"RuntimeInformation.FrameworkDescription: {System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription}");

// Old result
//   RuntimeInformation.FrameworkDescription: .NET Core 4.6.27415.71
//
// New result (notice the value includes any preview release information)
//   RuntimeInformation.FrameworkDescription: .NET Core 3.0.0-preview4-27615-11
```

> [!WARNING]
> <span data-ttu-id="e3f4b-405">破壊的変更。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-405">Breaking change.</span></span> <span data-ttu-id="e3f4b-406">バージョン管理スキームが変更されたので、これは技術的には破壊的変更です。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-406">This is technically a breaking change because the versioning scheme has changed.</span></span>

### <a name="fast-built-in-json-support"></a><span data-ttu-id="e3f4b-407">高速な組み込み JSON のサポート</span><span class="sxs-lookup"><span data-stu-id="e3f4b-407">Fast built-in JSON support</span></span>

<span data-ttu-id="e3f4b-408">.NET ユーザーは、[Newtonsoft.Json](https://www.newtonsoft.com/json) や他のよく使われている JSON ライブラリに大きく依存しています。これは今後も推奨されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-408">.NET users have largely relied on [Newtonsoft.Json](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="e3f4b-409">`Newtonsoft.Json` では .NET の文字列が基本のデータ型 (内部的には UTF-16) として使用されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-409">`Newtonsoft.Json` uses .NET strings as its base datatype, which is UTF-16 under the hood.</span></span>

<span data-ttu-id="e3f4b-410">新しい組み込みの JSON サポートは、高パフォーマンス、低割り当てで、UTF-8 でエンコードされた JSON テキストを使用します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-410">The new built-in JSON support is high-performance, low allocation, and works with UTF-8 encoded JSON text.</span></span> <span data-ttu-id="e3f4b-411"><xref:System.Text.Json> 名前空間と種類の詳細については、次の記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-411">For more information about the <xref:System.Text.Json> namespace and types, see the following articles:</span></span>

* [<span data-ttu-id="e3f4b-412">.NET での JSON のシリアル化 - 概要</span><span class="sxs-lookup"><span data-stu-id="e3f4b-412">JSON serialization in .NET - overview</span></span>](../../standard/serialization/system-text-json-overview.md)
* <span data-ttu-id="e3f4b-413">[.NET で JSON をシリアル化および逆シリアル化する方法](../../standard/serialization/system-text-json-how-to.md)。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-413">[How to serialize and deserialize JSON in .NET](../../standard/serialization/system-text-json-how-to.md).</span></span>
* [<span data-ttu-id="e3f4b-414">Newtonsoft. Json から System.Text.Json に移行する方法</span><span class="sxs-lookup"><span data-stu-id="e3f4b-414">How to migrate from Newtonsoft.Json to System.Text.Json</span></span>](../../standard/serialization/system-text-json-migrate-from-newtonsoft-how-to.md)

### <a name="http2-support"></a><span data-ttu-id="e3f4b-415">HTTP/2 のサポート</span><span class="sxs-lookup"><span data-stu-id="e3f4b-415">HTTP/2 support</span></span>

<span data-ttu-id="e3f4b-416"><xref:System.Net.Http.HttpClient?displayProperty=nameWithType> 型は HTTP/2 プロトコルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-416">The <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> type supports the HTTP/2 protocol.</span></span> <span data-ttu-id="e3f4b-417">HTTP/2 が有効な場合、HTTP プロトコルのバージョンは TLS/ALPN を介してネゴシエートされ、HTTP/2 はサーバーがそれを使用することを選択した場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-417">If HTTP/2 is enabled, the HTTP protocol version is negotiated via TLS/ALPN, and HTTP/2 is used if the server elects to use it.</span></span>

<span data-ttu-id="e3f4b-418">既定のプロトコルは HTTP/1.1 のままですが、2 つの方法で HTTP/2 を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-418">The default protocol remains HTTP/1.1, but HTTP/2 can be enabled in two different ways.</span></span> <span data-ttu-id="e3f4b-419">1 つ目として、HTTP/2 を使うように HTTP 要求メッセージを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-419">First, you can set the HTTP request message to use HTTP/2:</span></span>

[!code-csharp[Http2Request](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Request)]

<span data-ttu-id="e3f4b-420">2 つ目として、既定で HTTP/2 を使うように <xref:System.Net.Http.HttpClient> を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-420">Second, you can change <xref:System.Net.Http.HttpClient> to use HTTP/2 by default:</span></span>

[!code-csharp[Http2Client](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Client)]

<span data-ttu-id="e3f4b-421">多くの場合、アプリケーションを開発しているときは、暗号化されていない接続を使います。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-421">Many times when you're developing an application, you want to use an unencrypted connection.</span></span> <span data-ttu-id="e3f4b-422">ターゲット エンドポイントで HTTP/2 が使われることがわかっている場合は、HTTP/2 用の暗号化されていない接続を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-422">If you know the target endpoint will be using HTTP/2, you can turn on unencrypted connections for HTTP/2.</span></span> <span data-ttu-id="e3f4b-423">有効にするには、`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` 環境変数を `1` に設定するか、またはアプリのコンテキストで有効にします。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-423">You can turn it on by setting the `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` environment variable to `1` or by enabling it in the app context:</span></span>

[!code-csharp[Http2Context](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#AppContext)]

## <a name="next-steps"></a><span data-ttu-id="e3f4b-424">次の手順</span><span class="sxs-lookup"><span data-stu-id="e3f4b-424">Next steps</span></span>

- [<span data-ttu-id="e3f4b-425">バージョン 2.2 から 3.0 への破壊的変更を確認する。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-425">Review the breaking changes between .NET Core 2.2 and 3.0.</span></span>](../compatibility/2.2-3.0.md)
- [<span data-ttu-id="e3f4b-426">Windows フォーム アプリ用の .NET Core 3.0 における破壊的変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="e3f4b-426">Review the breaking changes in .NET Core 3.0 for Windows Forms apps.</span></span>](../compatibility/winforms.md#net-core-30)
