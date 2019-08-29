---
title: .NET Core 3.0 の新機能
description: .NET Core 3.0 の新機能について説明します。
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 08/21/2019
ms.openlocfilehash: 5f9d7026b270a010d2ba5d4b1165728a100ab6ed
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922559"
---
# <a name="whats-new-in-net-core-30-preview-8"></a><span data-ttu-id="e4d37-103">.NET Core 3.0 (Preview 8) の新機能</span><span class="sxs-lookup"><span data-stu-id="e4d37-103">What's new in .NET Core 3.0 (Preview 8)</span></span>

<span data-ttu-id="e4d37-104">この記事では、.NET Core 3.0 (Preview 8 まで) の新機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-104">This article describes what is new in .NET Core 3.0 (through preview 8).</span></span> <span data-ttu-id="e4d37-105">最も大きな強化点の 1 つは、Windows デスクトップ アプリケーションのサポートです (Windows のみ)。</span><span class="sxs-lookup"><span data-stu-id="e4d37-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="e4d37-106">.NET Core 3.0 SDK コンポーネントの Windows デスクトップを使用して、Windows フォームおよび Windows Presentation Foundation (WPF) アプリケーションを移植することができます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-106">By using the .NET Core 3.0 SDK component Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="e4d37-107">誤解のないように言うと、Windows Desktop コンポーネントは Windows でのみサポートされており、Windows にのみ含まれています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="e4d37-108">詳細については、この記事で後述する「[Windows デスクトップ](#windows-desktop)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4d37-108">For more information, see the [Windows desktop](#windows-desktop) section later in this article.</span></span>

<span data-ttu-id="e4d37-109">.NET Core 3.0 では C# 8.0 のサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-109">.NET Core 3.0 adds support for C# 8.0.</span></span> <span data-ttu-id="e4d37-110">[最新リリースの Visual Studio Preview](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+preview) または OmniSharp 拡張機能を含む Visual Studio Code を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e4d37-110">It's highly recommended that you use the [latest release of Visual Studio Preview](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+preview), or Visual Studio Code with the OmniSharp extension.</span></span>

<span data-ttu-id="e4d37-111">[.NET Core 3.0 Preview 8 を今すぐダウンロード](https://aka.ms/netcore3download)して Windows、macOS、または Linux 上で使い始めましょう。</span><span class="sxs-lookup"><span data-stu-id="e4d37-111">[Download and get started with .NET Core 3.0 preview 8](https://aka.ms/netcore3download) right now on Windows, macOS, or Linux.</span></span>

<span data-ttu-id="e4d37-112">各プレビュー リリースの詳細については、次の発表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4d37-112">For more information about each preview release, see the following announcements:</span></span>

- [<span data-ttu-id="e4d37-113">.NET Core 3.0 Preview 8 の発表</span><span class="sxs-lookup"><span data-stu-id="e4d37-113">.NET Core 3.0 Preview 8 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-8/)
- [<span data-ttu-id="e4d37-114">.NET Core 3.0 Preview 7 の発表</span><span class="sxs-lookup"><span data-stu-id="e4d37-114">.NET Core 3.0 Preview 7 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-7/)
- [<span data-ttu-id="e4d37-115">.NET Core 3.0 Preview 6 の発表</span><span class="sxs-lookup"><span data-stu-id="e4d37-115">.NET Core 3.0 Preview 6 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-6/)
- [<span data-ttu-id="e4d37-116">.NET Core 3.0 Preview 5 の発表</span><span class="sxs-lookup"><span data-stu-id="e4d37-116">.NET Core 3.0 Preview 5 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-5/)
- [<span data-ttu-id="e4d37-117">.NET Core 3.0 Preview 4 の発表</span><span class="sxs-lookup"><span data-stu-id="e4d37-117">.NET Core 3.0 Preview 4 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-4/)
- [<span data-ttu-id="e4d37-118">.NET Core 3.0 Preview 3 の発表</span><span class="sxs-lookup"><span data-stu-id="e4d37-118">.NET Core 3.0 Preview 3 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-3/)
- [<span data-ttu-id="e4d37-119">.NET Core 3.0 Preview 2 の発表</span><span class="sxs-lookup"><span data-stu-id="e4d37-119">.NET Core 3.0 Preview 2 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-2/)
- [<span data-ttu-id="e4d37-120">.NET Core 3.0 Preview 1 の発表</span><span class="sxs-lookup"><span data-stu-id="e4d37-120">.NET Core 3.0 Preview 1 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/)

## <a name="production-supported-preview"></a><span data-ttu-id="e4d37-121">運用環境でサポートされているプレビュー</span><span class="sxs-lookup"><span data-stu-id="e4d37-121">Production supported preview</span></span>

<span data-ttu-id="e4d37-122">.NET Core Preview 8 は、Microsoft による運用の準備ができていると見なされており、完全にサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-122">.NET Core Preview 8 is considered production ready by Microsoft and is fully supported.</span></span> <span data-ttu-id="e4d37-123">Preview 7 以降、リリースでは、新機能を追加するのではなく、.NET Core 3.0 を洗練させることに焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-123">Starting with preview 7, releases will focus on polishing .NET Core 3.0 instead of adding new features.</span></span> <span data-ttu-id="e4d37-124">Preview 8 で変更された内容の詳細については、[Preview 8 の発表](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-8/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4d37-124">For more information about what has changed in preview 8, see the [preview 8 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-8/).</span></span>

<span data-ttu-id="e4d37-125">以前のプレビュー リリースを使用している場合は、"Go Live" のサポートを継続するために Preview 8 に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-125">If you're using a previous preview release, you must move to Preview 8 for continued "Go Live" support.</span></span>

## <a name="net-core-sdk-windows-installer"></a><span data-ttu-id="e4d37-126">.NET Core SDK Windows インストーラー</span><span class="sxs-lookup"><span data-stu-id="e4d37-126">.NET Core SDK Windows Installer</span></span>

<span data-ttu-id="e4d37-127">Windows 用の MSI インストーラーは、.NET Core 3.0 から変更されました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-127">The MSI installer for Windows has changed starting with .NET Core 3.0.</span></span> <span data-ttu-id="e4d37-128">SDK インストーラーは、SDK 機能帯リリースのアップグレードを実行するようになります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-128">The SDK installers will now upgrade SDK feature-band releases in place.</span></span> <span data-ttu-id="e4d37-129">機能帯は、バージョン番号の "*パッチ*" セクションの *100* 番台のグループで定義されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-129">Feature bands are defined in the *hundreds* groups in the *patch* section of the version number.</span></span> <span data-ttu-id="e4d37-130">たとえば、**3.0._101_** と **3.0._201_** は 2 つの異なる機能帯のバージョンですが、**3.0._101_** と **3.0._199_** は同じ機能帯に含まれます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-130">For example, **3.0._101_** and **3.0._201_** are versions in two different feature bands while **3.0._101_** and **3.0._199_** are in the same feature band.</span></span> <span data-ttu-id="e4d37-131">また、.NET Core SDK **3.0._101_** をインストールすると、.NET Core SDK **3.0._100_** が存在する場合はマシンから削除されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-131">And, when .NET Core SDK **3.0._101_** is installed, .NET Core SDK **3.0._100_** will be removed from the machine if it exists.</span></span> <span data-ttu-id="e4d37-132">同じマシンに .NET Core SDK **3.0._200_** をインストールすると、.NET Core SDK **3.0._101_** は削除されません。</span><span class="sxs-lookup"><span data-stu-id="e4d37-132">When .NET Core SDK **3.0._200_** is installed on the same machine, .NET Core SDK **3.0._101_** won't be removed.</span></span>

<span data-ttu-id="e4d37-133">バージョン管理の詳細については、「[.NET Core をバージョン管理する方法の概要](../versions/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4d37-133">For more information about versioning, see [Overview of how .NET Core is versioned](../versions/index.md).</span></span>

## <a name="c-80-preview"></a><span data-ttu-id="e4d37-134">C# 8.0 Preview</span><span class="sxs-lookup"><span data-stu-id="e4d37-134">C# 8.0 preview</span></span>

<span data-ttu-id="e4d37-135">.NET Core 3.0 は C# 8 Preview をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-135">.NET Core 3.0 supports C# 8 preview.</span></span> <span data-ttu-id="e4d37-136">C# 8.0 の機能の詳細については、「[C# 8.0 の新機能](../../csharp/whats-new/csharp-8.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4d37-136">For more information about C# 8.0 features, see [What's new in C# 8.0](../../csharp/whats-new/csharp-8.md).</span></span>

## <a name="net-standard-21"></a><span data-ttu-id="e4d37-137">.NET Standard 2.1</span><span class="sxs-lookup"><span data-stu-id="e4d37-137">.NET Standard 2.1</span></span>

<span data-ttu-id="e4d37-138">.NET Core 3.0 は **.NET Standard 2.1** をサポートしていますが、既定の `dotnet new classlib` テンプレートでは、 **.NET Standard 2.0** をターゲットとするプロジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-138">Even though .NET Core 3.0 supports **.NET Standard 2.1**, the default `dotnet new classlib` template generates a project that targets **.NET Standard 2.0**.</span></span> <span data-ttu-id="e4d37-139">**.NET Standard 2.1** をターゲットにするには、プロジェクト ファイルを編集して `TargetFramework` プロパティを `netstandard2.1` に変更します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-139">To target **.NET Standard 2.1**, edit your project file and change the `TargetFramework` property to `netstandard2.1`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="e4d37-140">Visual Studio を使用している場合、Visual Studio 2017 では **.NET Standard 2.1** または **.NET Core 3.0** がサポートされていないため、[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) が必要です。</span><span class="sxs-lookup"><span data-stu-id="e4d37-140">If you're using Visual Studio, you need [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), as Visual Studio 2017 doesn't support **.NET Standard 2.1** or **.NET Core 3.0**.</span></span>

## <a name="improved-net-core-version-apis"></a><span data-ttu-id="e4d37-141">強化された .NET Core バージョン API</span><span class="sxs-lookup"><span data-stu-id="e4d37-141">Improved .NET Core Version APIs</span></span>

<span data-ttu-id="e4d37-142">.NET Core 3.0 以降、.NET Core に提供されているバージョン API から、期待どおりの情報が返されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-142">Starting with .NET Core 3.0, the version APIs provided with .NET Core now return the information you expect.</span></span> <span data-ttu-id="e4d37-143">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-143">For example:</span></span>

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
// New result
//   RuntimeInformation.FrameworkDescription: .NET Core 3.0.0-preview4-27615-11
```

> [!WARNING]
> <span data-ttu-id="e4d37-144">破壊的変更。</span><span class="sxs-lookup"><span data-stu-id="e4d37-144">Breaking change.</span></span> <span data-ttu-id="e4d37-145">バージョン管理スキームが変更されたので、これは技術的には破壊的変更です。</span><span class="sxs-lookup"><span data-stu-id="e4d37-145">This is technically a breaking change because the versioning scheme has changed.</span></span>

## <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="e4d37-146">.NET プラットフォーム依存性</span><span class="sxs-lookup"><span data-stu-id="e4d37-146">.NET Platform-Dependent Intrinsics</span></span>

<span data-ttu-id="e4d37-147">特定のパフォーマンス指向 CPU 命令 (**SIMD** や **ビット操作命令**セット) にアクセスできるようにする API が追加されました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-147">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="e4d37-148">これらの命令は、データを並列で効率的に処理するといった、特定のシナリオでパフォーマンスを大幅に向上するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-148">These instructions can help achieve significant performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span>

<span data-ttu-id="e4d37-149">.NET ライブラリでは、必要に応じて、パフォーマンスを向上するためにこれらの命令が使用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-149">Where appropriate, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="e4d37-150">詳細については、「[.NET Platform Dependent Intrinsics (.NET プラットフォーム依存性)](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4d37-150">For more information, see [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md).</span></span>

## <a name="default-executables"></a><span data-ttu-id="e4d37-151">既定の実行可能ファイル</span><span class="sxs-lookup"><span data-stu-id="e4d37-151">Default executables</span></span>

<span data-ttu-id="e4d37-152">.NET Core では、既定で[フレームワーク依存の実行可能ファイル](../deploying/index.md#framework-dependent-executables-fde)が作成されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-152">.NET Core now builds [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="e4d37-153">この動作は、グローバルにインストールされているバージョンの .NET Core を使用するアプリケーションの新機能です。</span><span class="sxs-lookup"><span data-stu-id="e4d37-153">This behavior is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="e4d37-154">以前は、[自己完結型の配置](../deploying/index.md#self-contained-deployments-scd)でのみ実行可能ファイルが生成されました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-154">Previously, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="e4d37-155">`dotnet build` または `dotnet publish` の実行中に、使用している SDK の環境およびプラットフォームと一致する実行可能ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-155">During `dotnet build` or `dotnet publish`, an executable is created that matches the environment and platform of the SDK you're using.</span></span> <span data-ttu-id="e4d37-156">これらの実行可能ファイルでは、次のような他のネイティブ実行可能ファイルと同じことを期待できます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-156">You can expect the same things with these executables as you would other native executables, such as:</span></span>

- <span data-ttu-id="e4d37-157">実行可能ファイルはダブルクリックすることができます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-157">You can double-click on the executable.</span></span>
- <span data-ttu-id="e4d37-158">Windows では `myapp.exe`、Linux と macOS では`./myapp` など、コマンド プロンプトからアプリケーションを直接起動できます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-158">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

## <a name="single-file-executables"></a><span data-ttu-id="e4d37-159">単一ファイルの実行可能ファイル</span><span class="sxs-lookup"><span data-stu-id="e4d37-159">Single-file executables</span></span>

<span data-ttu-id="e4d37-160">`dotnet publish` コマンドは、プラットフォーム固有の単一ファイルの実行可能ファイルにアプリをパッケージ化することをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e4d37-160">The `dotnet publish` command supports packaging your app into a platform-specific single-file executable.</span></span> <span data-ttu-id="e4d37-161">実行可能ファイルは自己展開型であり、アプリの実行に必要なすべての依存関係 (ネイティブを含む) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-161">The executable is self-extracting and contains all dependencies (including native) that are required to run your app.</span></span> <span data-ttu-id="e4d37-162">アプリを初めて実行すると、アプリ名とビルド ID に基づいてアプリケーションがディレクトリに抽出されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-162">When the app is first run, the application is extracted to a directory based on the app name and build identifier.</span></span> <span data-ttu-id="e4d37-163">アプリケーションを再実行すると、起動は速くなります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-163">Startup is faster when the application is run again.</span></span> <span data-ttu-id="e4d37-164">新しいバージョンが使用されない限り、アプリケーションは自身を 2 回抽出する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="e4d37-164">The application doesn't need to extract itself a second time unless a new version was used.</span></span>

<span data-ttu-id="e4d37-165">単一ファイルの実行可能ファイルを発行するには、プロジェクト内またはコマンド ラインで `dotnet publish` コマンドを使用して `PublishSingleFile` を設定します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-165">To publish a single-file executable, set the `PublishSingleFile` in your project or on the command line with the `dotnet publish` command:</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>win10-x64</RuntimeIdentifier>
  <PublishSingleFile>true</PublishSingleFile>
</PropertyGroup>
```

<span data-ttu-id="e4d37-166">または</span><span class="sxs-lookup"><span data-stu-id="e4d37-166">-or-</span></span>

```console
dotnet publish -r win10-x64 /p:PublishSingleFile=true
```

<span data-ttu-id="e4d37-167">単一ファイルの発行の詳細については、[単一ファイル バンドラー設計のドキュメント](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4d37-167">For more information about single-file publishing, see the [single-file bundler design document](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).</span></span>

## <a name="assembly-linking"></a><span data-ttu-id="e4d37-168">アセンブリのリンク</span><span class="sxs-lookup"><span data-stu-id="e4d37-168">Assembly linking</span></span>

<span data-ttu-id="e4d37-169">.NET Core 3.0 SDK に付属するツールを使うと、IL を分析し、未使用のアセンブリをトリミングすることによって、アプリのサイズを減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-169">The .NET core 3.0 SDK comes with a tool that can reduce the size of apps by analyzing IL and trimming unused assemblies.</span></span>

<span data-ttu-id="e4d37-170">自己完結型アプリには、コードの実行に必要なものがすべて含まれるので、ホスト コンピューターに .NET をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e4d37-170">Self-contained apps include everything needed to run your code, without requiring .NET to be installed on the host computer.</span></span> <span data-ttu-id="e4d37-171">ただし、多くの場合、アプリが機能するにはフレームワークの小さなサブセットのみが必要であり、使用されていない他のライブラリは削除できます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-171">However, many times the app only requires a small subset of the framework to function, and other unused libraries could be removed.</span></span>

<span data-ttu-id="e4d37-172">.NET Core には、[IL リンカー](https://github.com/mono/linker) ツールを使ってアプリの IL をスキャンする設定が含まれるようになっています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-172">.NET Core now includes a setting that will use the [IL linker](https://github.com/mono/linker) tool to scan the IL of your app.</span></span> <span data-ttu-id="e4d37-173">このツールでは、必要なコードが検出された後、使われていないライブラリがトリミングされます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-173">this tool detects what code is required, and then trims unused libraries.</span></span> <span data-ttu-id="e4d37-174">このツールを使うと、一部のアプリの展開サイズを大幅に削減できます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-174">This tool can significantly reduce the deployment size of some apps.</span></span>

<span data-ttu-id="e4d37-175">このツールを有効にするには、プロジェクトで `<PublishTrimmed>` 設定を追加し、自己完結型アプリを発行します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-175">To enable this tool, add the `<PublishTrimmed>` setting in your project and publish a self-contained app:</span></span>

```xml
<PropertyGroup>
  <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

```console
dotnet publish -r <rid> -c Release
```

<span data-ttu-id="e4d37-176">たとえば、含まれている基本的な "hello world" という新しいコンソール プロジェクト テンプレートは、発行されるときに、サイズが約 70 MB になります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-176">As an example, the basic "hello world" new console project template that is included, when published, hits about 70 MB in size.</span></span> <span data-ttu-id="e4d37-177">`<PublishTrimmed>` を使うことにより、そのサイズが約 30 MB に減ります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-177">By using `<PublishTrimmed>`, that size is reduced to about 30 MB.</span></span>

<span data-ttu-id="e4d37-178">考慮すべき重要なこととして、リフレクションまたは関連する動的機能を使っているアプリケーションまたはフレームワーク (ASP.NET Core と WPF を含む) では、トリミングすると壊れることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-178">It's important to consider that applications or frameworks (including ASP.NET Core and WPF) that use reflection or related dynamic features, will often break when trimmed.</span></span> <span data-ttu-id="e4d37-179">このような破損が発生するのは、リンカーはこの動的な動作を認識しておらず、リフレクションに必要なフレームワークの種類を判断できないためです。</span><span class="sxs-lookup"><span data-stu-id="e4d37-179">This breakage occurs because the linker doesn't know about this dynamic behavior and can't determine which framework types are required for reflection.</span></span> <span data-ttu-id="e4d37-180">IL リンカー ツールは、このシナリオを認識するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-180">The IL Linker tool can be configured to be aware of this scenario.</span></span>

<span data-ttu-id="e4d37-181">何よりも、必ずトリミング後のアプリをテストしてください。</span><span class="sxs-lookup"><span data-stu-id="e4d37-181">Above all else, be sure to test your app after trimming.</span></span>

<span data-ttu-id="e4d37-182">IL リンカー ツールについて詳しくは、[ドキュメント](https://aka.ms/dotnet-illink)または [mono/linker]( https://github.com/mono/linker) リポジトリをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e4d37-182">For more information about the IL Linker tool, see the [documentation](https://aka.ms/dotnet-illink) or visit the [mono/linker]( https://github.com/mono/linker) repo.</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="e4d37-183">階層型コンパイル</span><span class="sxs-lookup"><span data-stu-id="e4d37-183">Tiered compilation</span></span>

<span data-ttu-id="e4d37-184">.NET Core 3.0 では、[階層型コンパイル](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) (TC) が既定で有効になりました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-184">[Tiered compilation](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) (TC) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="e4d37-185">この機能により、ランタイムが状況に応じて Just-In-Time (JIT) コンパイラを使用してパフォーマンスを向上できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-185">This feature enables the runtime to more adaptively use the Just-In-Time (JIT) compiler to get better performance.</span></span>

<span data-ttu-id="e4d37-186">TC の主な利点は、低品質で高速な階層または高品質で低速な階層を使った (再) JIT メソッドが可能になることです。</span><span class="sxs-lookup"><span data-stu-id="e4d37-186">The main benefit of TC is to enable (re-)jitting methods with a lower-quality-but-faster tier or a higher-quality-but-slower tier.</span></span> <span data-ttu-id="e4d37-187">これは、起動から安定した状態まで、さまざまな実行段階を経るときに、アプリケーションのパフォーマンスを向上するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-187">This helps increase performance of an application as it goes through various stages of execution, from startup through steady-state.</span></span> <span data-ttu-id="e4d37-188">これは、すべてのメソッドが 1 つの方法 (高品質階層と同じ) でコンパイルされ、起動時のパフォーマンスよりも安定した状態に偏っている非 TC アプローチとは対照的です。</span><span class="sxs-lookup"><span data-stu-id="e4d37-188">This contrasts with the non-TC approach, where every method is compiled a single way (the same as the high-quality tier), which is biased to steady-state over startup performance.</span></span>

<span data-ttu-id="e4d37-189">Quick JIT (階層 0 の JIT 済みコード) を有効にするには、プロジェクト ファイルで次の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-189">To enable Quick JIT (tier 0 jitted code), use this setting in your project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>true</TieredCompilationQuickJit>
</PropertyGroup>
```

<span data-ttu-id="e4d37-190">TC を完全に無効にするには、プロジェクト ファイルでこの設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-190">To disable TC completely, use this setting in your project file:</span></span>

```xml
<TieredCompilation>false</TieredCompilation>
```

## <a name="readytorun-images"></a><span data-ttu-id="e4d37-191">ReadyToRun イメージ</span><span class="sxs-lookup"><span data-stu-id="e4d37-191">ReadyToRun images</span></span>

<span data-ttu-id="e4d37-192">アプリケーション アセンブリを ReadyToRun (R2R) 形式としてコンパイルすることで、.NET Core アプリケーションの起動時間を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-192">You can improve the startup time of your .NET Core application by compiling your application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="e4d37-193">R2R とは、Ahead-Of-Time (AOT) コンパイルの一種です。</span><span class="sxs-lookup"><span data-stu-id="e4d37-193">R2R is a form of ahead-of-time (AOT) compilation.</span></span>

<span data-ttu-id="e4d37-194">R2R バイナリでは、アプリケーションの読み込み時に Just-In-Time (JIT) コンパイラで行う必要がある作業量を減らすことにより、起動時のパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-194">R2R binaries improve startup performance by reducing the amount of work the just-in-time (JIT) compiler needs to do as your application loads.</span></span> <span data-ttu-id="e4d37-195">バイナリには、JIT で生成されるものと似たネイティブ コードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-195">The binaries contain similar native code compared to what the JIT would produce.</span></span> <span data-ttu-id="e4d37-196">ただし、R2R バイナリは、中間言語 (IL) コード (一部のシナリオでまだ必要です) と同じコードのネイティブ バージョンの両方が含まれるため、大きくなります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-196">However, R2R binaries are larger because they contain both intermediate language (IL) code, which is still needed for some scenarios, and the native version of the same code.</span></span> <span data-ttu-id="e4d37-197">R2R は、Linux x64 や Windows x64 などの特定のランタイム環境 (RID) をターゲットとする自己完結型アプリを発行するときにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-197">R2R is only available when you publish a self-contained app that targets specific runtime environments (RID) such as Linux x64 or Windows x64.</span></span>

<span data-ttu-id="e4d37-198">ReadyToRun としてプロジェクトをコンパイルするには、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="e4d37-198">To compile your project as ReadyToRun, do the following:</span></span>

01. <span data-ttu-id="e4d37-199">`<PublishReadyToRun>` 設定をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-199">Add the `<PublishReadyToRun>` setting to your project</span></span>

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

01. <span data-ttu-id="e4d37-200">自己完結型アプリを発行します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-200">Publish a self-contained app.</span></span> <span data-ttu-id="e4d37-201">たとえば、次のコマンドでは、Windows の 64 ビット版向けの自己完結型アプリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-201">For example, this command creates a self-contained app for the 64-bit version of Windows:</span></span>

    ```console
    dotnet publish -c Release -r win-x64 --self-contained true
    ```

### <a name="cross-platformarchitecture-restrictions"></a><span data-ttu-id="e4d37-202">クロス プラットフォーム/アーキテクチャの制限</span><span class="sxs-lookup"><span data-stu-id="e4d37-202">Cross platform/architecture restrictions</span></span>

<span data-ttu-id="e4d37-203">現在、ReadyToRun コンパイラではクロスターゲットはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e4d37-203">The ReadyToRun compiler doesn't currently support cross-targeting.</span></span> <span data-ttu-id="e4d37-204">特定のターゲットに対してコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-204">You must compile on a given target.</span></span> <span data-ttu-id="e4d37-205">たとえば、Windows x64 用の R2R イメージが必要な場合は、その環境で publish コマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-205">For example, if you want R2R images for Windows x64, you need to run the publish command on that environment.</span></span>

<span data-ttu-id="e4d37-206">クロスターゲットに対する例外:</span><span class="sxs-lookup"><span data-stu-id="e4d37-206">Exceptions to cross-targeting:</span></span>

- <span data-ttu-id="e4d37-207">Windows x64 を使って、Windows ARM32、ARM64、x86 のイメージをコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-207">Windows x64 can be used to compile Windows ARM32, ARM64, and x86 images.</span></span>
- <span data-ttu-id="e4d37-208">Windows x86 を使って、Windows ARM32 のイメージをコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-208">Windows x86 can be used to compile Windows ARM32 images.</span></span>
- <span data-ttu-id="e4d37-209">Linux x64 を使って、Linux ARM32 と ARM64 のイメージをコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-209">Linux x64 can be used to compile Linux ARM32 and ARM64 images.</span></span>

## <a name="build-copies-dependencies"></a><span data-ttu-id="e4d37-210">ビルドによる依存関係のコピー</span><span class="sxs-lookup"><span data-stu-id="e4d37-210">Build copies dependencies</span></span>

<span data-ttu-id="e4d37-211">`dotnet build` コマンドでは、アプリケーションの NuGet 依存関係が NuGet キャッシュからビルド出力フォルダーにコピーされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-211">The `dotnet build` command now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="e4d37-212">以前は、依存関係のコピーは `dotnet publish` の一部としてのみ行われていました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-212">Previously, dependencies were only copied as part of `dotnet publish`.</span></span>

<span data-ttu-id="e4d37-213">リンクや razor ページの発行など、まだ発行が必要な操作がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-213">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>

## <a name="local-tools"></a><span data-ttu-id="e4d37-214">ローカル ツール</span><span class="sxs-lookup"><span data-stu-id="e4d37-214">Local tools</span></span>

<span data-ttu-id="e4d37-215">.NET Core 3.0 にローカル ツールが導入されました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-215">.NET Core 3.0 introduces local tools.</span></span> <span data-ttu-id="e4d37-216">ローカル ツールは[グローバル ツール](../tools/global-tools.md)に似ていますが、ディスク上の特定の場所に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-216">Local tools are similar to [global tools](../tools/global-tools.md) but are associated with a particular location on disk.</span></span> <span data-ttu-id="e4d37-217">ローカル ツールはグローバルには使用できず、NuGet パッケージとして配布されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-217">Local tools aren't available globally and are distributed as NuGet packages.</span></span>

> [!WARNING]
> <span data-ttu-id="e4d37-218">.NET Core 3.0 Preview 1 で `dotnet tool restore` や `dotnet tool install` の実行などのローカル ツールを試した場合は、ローカル ツールのキャッシュ フォルダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-218">If you tried local tools in .NET Core 3.0 Preview 1, such as running `dotnet tool restore` or `dotnet tool install`, delete the local tools cache folder.</span></span> <span data-ttu-id="e4d37-219">そうしないと、ローカル ツールは新しいリリースで動作しません。</span><span class="sxs-lookup"><span data-stu-id="e4d37-219">Otherwise, local tools won't work on any newer release.</span></span> <span data-ttu-id="e4d37-220">このフォルダーは次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-220">This folder is located at:</span></span>
>
> <span data-ttu-id="e4d37-221">macOS、Linux の場合: `rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="e4d37-221">On macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
> <span data-ttu-id="e4d37-222">Windows の場合: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="e4d37-222">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>

<span data-ttu-id="e4d37-223">ローカル ツールは、現在のディレクトリ内のマニフェスト ファイル名 `dotnet-tools.json` に依存しています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-223">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="e4d37-224">このマニフェスト ファイルは、ツールをそのフォルダー下で使用できるように定義します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-224">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="e4d37-225">コードを使用するすべての人が確実に同じツールを復元して使用できるように、自分のコードと一緒にマニフェスト ファイルを配布することができます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-225">You can distribute the manifest file with your code to ensure that anyone who works with your code can restore and use the same tools.</span></span>

<span data-ttu-id="e4d37-226">グローバル ツールとローカル ツールの両方で、ランタイムの互換バージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="e4d37-226">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="e4d37-227">現在 NuGet.org 上にある多くのツールは、.NET Core Runtime 2.1 をターゲットとしています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-227">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="e4d37-228">グローバルにまたはローカルにこのようなツールをインストールするには、[NET Core 2.1 ランタイム](https://dotnet.microsoft.com/download/dotnet-core/2.1)をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-228">To install these tools globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

## <a name="major-version-roll-forward"></a><span data-ttu-id="e4d37-229">メジャーバージョンのロールフォワード</span><span class="sxs-lookup"><span data-stu-id="e4d37-229">Major-version Roll Forward</span></span>

<span data-ttu-id="e4d37-230">.NET Core 3.0 では、アプリを最新メジャー バージョンの .NET Core にロールフォワードできるようにするオプトイン機能が導入されました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-230">.NET Core 3.0 introduces an opt-in feature that allows your app to roll forward to the latest major version of .NET Core.</span></span> <span data-ttu-id="e4d37-231">さらに、ロールフォワードをアプリに適用する方法を制御する新しい設定が追加されました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-231">Additionally, a new setting has been added to control how roll forward is applied to your app.</span></span> <span data-ttu-id="e4d37-232">これは、以下の方法で構成できます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-232">This can be configured in the following ways:</span></span>

- <span data-ttu-id="e4d37-233">プロジェクト ファイルのプロパティ: `RollForward`</span><span class="sxs-lookup"><span data-stu-id="e4d37-233">Project file property: `RollForward`</span></span>
- <span data-ttu-id="e4d37-234">ランタイム構成ファイルのプロパティ: `rollForward`</span><span class="sxs-lookup"><span data-stu-id="e4d37-234">Runtime configuration file property: `rollForward`</span></span>
- <span data-ttu-id="e4d37-235">環境変数: `DOTNET_ROLL_FORWARD`</span><span class="sxs-lookup"><span data-stu-id="e4d37-235">Environment variable: `DOTNET_ROLL_FORWARD`</span></span>
- <span data-ttu-id="e4d37-236">コマンドライン引数: `--roll-forward`</span><span class="sxs-lookup"><span data-stu-id="e4d37-236">Command-line argument: `--roll-forward`</span></span>

<span data-ttu-id="e4d37-237">次の値のいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-237">One of the following values must be specified.</span></span> <span data-ttu-id="e4d37-238">設定を省略すると、**Minor** が既定値になります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-238">If the setting is omitted, **Minor** is the default.</span></span>

- <span data-ttu-id="e4d37-239">**LatestPatch**</span><span class="sxs-lookup"><span data-stu-id="e4d37-239">**LatestPatch**</span></span>\
<span data-ttu-id="e4d37-240">最新のパッチ バージョンにロールフォワードします。</span><span class="sxs-lookup"><span data-stu-id="e4d37-240">Roll forward to the highest patch version.</span></span> <span data-ttu-id="e4d37-241">これで、マイナー バージョンのロールフォワードが無効になります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-241">This disables minor version roll forward.</span></span>
- <span data-ttu-id="e4d37-242">**Minor**</span><span class="sxs-lookup"><span data-stu-id="e4d37-242">**Minor**</span></span>\
<span data-ttu-id="e4d37-243">要求されたマイナー バージョンが見つからない場合は、それよりも高い最小マイナー バージョンにロールフォワードします。</span><span class="sxs-lookup"><span data-stu-id="e4d37-243">Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="e4d37-244">要求されたマイナー バージョンが存在する場合は、**LatestPatch** ポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-244">If the requested minor version is present, then the **LatestPatch** policy is used.</span></span>
- <span data-ttu-id="e4d37-245">**Major**</span><span class="sxs-lookup"><span data-stu-id="e4d37-245">**Major**</span></span>\
<span data-ttu-id="e4d37-246">要求されたメジャー バージョンが見つからない場合は、それよりも高い最小メジャー バージョンで最小マイナー バージョンにロールフォワードします。</span><span class="sxs-lookup"><span data-stu-id="e4d37-246">Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="e4d37-247">要求されたメジャー バージョンが存在する場合は、**Minor** ポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-247">If the requested major version is present, then the **Minor** policy is used.</span></span>
- <span data-ttu-id="e4d37-248">**LatestMinor**</span><span class="sxs-lookup"><span data-stu-id="e4d37-248">**LatestMinor**</span></span>\
<span data-ttu-id="e4d37-249">要求されたマイナー バージョンが存在する場合でも、最上位のマイナー バージョンにロールフォワードします。</span><span class="sxs-lookup"><span data-stu-id="e4d37-249">Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="e4d37-250">コンポーネント ホスティング シナリオを対象としています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-250">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="e4d37-251">**LatestMajor**</span><span class="sxs-lookup"><span data-stu-id="e4d37-251">**LatestMajor**</span></span>\
<span data-ttu-id="e4d37-252">要求されたメジャーが存在する場合でも、最上位のメジャー バージョンで最上位のマイナー バージョンにロールフォワードします。</span><span class="sxs-lookup"><span data-stu-id="e4d37-252">Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="e4d37-253">コンポーネント ホスティング シナリオを対象としています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-253">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="e4d37-254">**Disable**</span><span class="sxs-lookup"><span data-stu-id="e4d37-254">**Disable**</span></span>\
<span data-ttu-id="e4d37-255">ロールフォワードしません。</span><span class="sxs-lookup"><span data-stu-id="e4d37-255">Don't roll forward.</span></span> <span data-ttu-id="e4d37-256">指定されたバージョンにのみバインドします。</span><span class="sxs-lookup"><span data-stu-id="e4d37-256">Only bind to specified version.</span></span> <span data-ttu-id="e4d37-257">このポリシーは、最新のパッチにロールフォワードする機能が無効になるため、一般的な使用にはお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="e4d37-257">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="e4d37-258">この値はテスト用にのみ推奨されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-258">This value is only recommended for testing.</span></span>

<span data-ttu-id="e4d37-259">**Disable** の設定を除くすべての設定では、利用できる最新のパッチ バージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-259">Besides the **Disable** setting, all settings will use the highest available patch version.</span></span>

## <a name="windows-desktop"></a><span data-ttu-id="e4d37-260">Windows デスクトップ</span><span class="sxs-lookup"><span data-stu-id="e4d37-260">Windows desktop</span></span>

<span data-ttu-id="e4d37-261">.NET Core 3.0 は、Windows Presentation Foundation (WPF) および Windows フォームを使用した Windows デスクトップ アプリケーションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-261">.NET Core 3.0 supports Windows desktop applications using Windows Presentation Foundation (WPF) and Windows Forms.</span></span> <span data-ttu-id="e4d37-262">これらのフレームワークでは、Windows UI XAML ライブラリ (WinUI) の最新のコントロールと Fluent スタイルを [XAML Islands](/windows/uwp/xaml-platform/xaml-host-controls) 経由で使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-262">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="e4d37-263">Windows デスクトップ コンポーネントは、Windows .NET Core 3.0 SDK の一部です。</span><span class="sxs-lookup"><span data-stu-id="e4d37-263">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="e4d37-264">次の `dotnet` コマンドを使用して、新しい WPF または Windows フォーム アプリケーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-264">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```console
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="e4d37-265">Visual Studio 2019 では、.NET Core 3.0 Windows フォームと WPF 用に、**新しいプロジェクト** テンプレートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-265">Visual Studio 2019 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span>

<span data-ttu-id="e4d37-266">既存の .NET Framework アプリケーションを移植する方法の詳細については、[WPF プロジェクトの移植](../porting/wpf.md)と [Windows フォーム プロジェクトの移植](../porting/winforms.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4d37-266">For more information about how to port an existing .NET Framework application, see [Port WPF projects](../porting/wpf.md) and [Port Windows Forms projects](../porting/winforms.md).</span></span>

## <a name="com-callable-components---windows-desktop"></a><span data-ttu-id="e4d37-267">COM 呼び出し可能コンポーネント - Windows デスクトップ</span><span class="sxs-lookup"><span data-stu-id="e4d37-267">COM-callable components - Windows Desktop</span></span>

<span data-ttu-id="e4d37-268">Windows 上で、COM 呼び出し可能なマネージ コンポーネントを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-268">On Windows, you can now create COM-callable managed components.</span></span> <span data-ttu-id="e4d37-269">この機能は、COM アドイン モデルに .NET Core を使用する場合と、.NET Framework にパリティを提供する場合にも重要です。</span><span class="sxs-lookup"><span data-stu-id="e4d37-269">This capability is critical to use .NET Core with COM add-in models and also to provide parity with .NET Framework.</span></span>

<span data-ttu-id="e4d37-270">COM サーバーとして *mscoree.dll* が使用されていた .NET Framework とは異なり、COM コンポーネントを構築すると、.NET Core によって *bin* ディレクトリにネイティブ ランチャー DLL が追加されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-270">Unlike .NET Framework where the *mscoree.dll* was used as the COM server, .NET Core will add a native launcher dll to the *bin* directory when you build your COM component.</span></span>

<span data-ttu-id="e4d37-271">COM コンポーネントを作成して使用する方法の例については、[COM のデモ](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4d37-271">For an example of how to create a COM component and consume it, see the [COM Demo](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span></span>

## <a name="msix-deployment---windows-desktop"></a><span data-ttu-id="e4d37-272">MSIX の展開 - Windows デスクトップ</span><span class="sxs-lookup"><span data-stu-id="e4d37-272">MSIX Deployment - Windows Desktop</span></span>

<span data-ttu-id="e4d37-273">[MSIX](https://docs.microsoft.com/windows/msix/) は新しい Windows アプリケーション パッケージ形式です。</span><span class="sxs-lookup"><span data-stu-id="e4d37-273">[MSIX](https://docs.microsoft.com/windows/msix/) is a new Windows application package format.</span></span> <span data-ttu-id="e4d37-274">これは、Windows 10 に .NET Core 3.0 のデスクトップ アプリケーションを展開するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-274">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="e4d37-275">[Windows アプリケーション パッケージ プロジェクト](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net)は、Visual Studio 2019 で使用でき、[自己完結型](../deploying/index.md#self-contained-deployments-scd)の .NET Core アプリケーションを使用して、MSIX パッケージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-275">The [Windows Application Packaging Project](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019, allows you to create MSIX packages with [self-contained](../deploying/index.md#self-contained-deployments-scd) .NET Core applications.</span></span>

<span data-ttu-id="e4d37-276">.NET Core プロジェクト ファイルの `<RuntimeIdentifiers>` プロパティで、サポートされているランタイムを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-276">The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>

```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="winforms-high-dpi"></a><span data-ttu-id="e4d37-277">WinForms の高 DPI</span><span class="sxs-lookup"><span data-stu-id="e4d37-277">WinForms high DPI</span></span>

<span data-ttu-id="e4d37-278">.NET Core Windows フォーム アプリケーションでは、<xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType> を使用して高 DPI モードを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-278">.NET Core Windows Forms applications can set high DPI mode with <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e4d37-279">`Application.Run` の前の `App.Manifest` や P/Invoke などの他の方法で設定を指定しない限り、`SetHighDpiMode` メソッドによって、対応する高 DPI モードが設定されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-279">The `SetHighDpiMode` method sets the corresponding high DPI mode unless the setting has been set by other means like `App.Manifest` or P/Invoke before `Application.Run`.</span></span>

<span data-ttu-id="e4d37-280"><xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> 列挙型で表される `highDpiMode` に使用できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e4d37-280">The possible `highDpiMode` values, as expressed by the <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> enum are:</span></span>

- `DpiUnaware`
- `SystemAware`
- `PerMonitor`
- `PerMonitorV2`
- `DpiUnawareGdiScaled`

<span data-ttu-id="e4d37-281">高 DPI モードの詳細については、「[Windows での高 DPI デスクトップ アプリケーション開発](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e4d37-281">For more information about high DPI modes, see [High DPI Desktop Application Development on Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span></span>

## <a name="ranges-and-indices"></a><span data-ttu-id="e4d37-282">範囲とインデックス</span><span class="sxs-lookup"><span data-stu-id="e4d37-282">Ranges and indices</span></span>

<span data-ttu-id="e4d37-283">新しい <xref:System.Index?displayProperty=nameWithType> 型はインデックス作成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-283">The new <xref:System.Index?displayProperty=nameWithType> type can be used for indexing.</span></span> <span data-ttu-id="e4d37-284">先頭からカウントする `int` か、末尾からカウントするプレフィックス `^` 演算子 (C#) を使用して作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-284">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="e4d37-285">また、<xref:System.Range?displayProperty=nameWithType> 型もあります。これは開始値と終了値の 2 つの `Index` 値から構成され、`x..y` の範囲式 (C#) で記述できます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-285">There's also the <xref:System.Range?displayProperty=nameWithType> type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="e4d37-286">これで、`Range` を使用してインデックスを付け、スライスを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-286">You can then index with a `Range`, which produces a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

<span data-ttu-id="e4d37-287">詳細については、[範囲とインデックスのチュートリアル](../../csharp/tutorials/ranges-indexes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4d37-287">For more information, see the [ranges and indices tutorial](../../csharp/tutorials/ranges-indexes.md).</span></span>

## <a name="async-streams"></a><span data-ttu-id="e4d37-288">非同期ストリーム</span><span class="sxs-lookup"><span data-stu-id="e4d37-288">Async streams</span></span>

<span data-ttu-id="e4d37-289"><xref:System.Collections.Generic.IAsyncEnumerable%601> 型は、<xref:System.Collections.Generic.IEnumerable%601> の新しい非同期バージョンです。</span><span class="sxs-lookup"><span data-stu-id="e4d37-289">The <xref:System.Collections.Generic.IAsyncEnumerable%601> type is a new asynchronous version of <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="e4d37-290">この言語では、その要素を使用するために `IAsyncEnumerable<T>` よりも `await foreach` を行い、要素を生成するために `yield return` を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-290">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="e4d37-291">非同期ストリームの生成の両方の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-291">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="e4d37-292">`foreach` ステートメントは非同期であり、`yield return` を使用して呼び出し元の非同期ストリームを生成します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-292">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="e4d37-293">(`yield return` を使用する) このパターンは、非同期ストリームを生成するモデルに推奨されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-293">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result;
    }
}
```

<span data-ttu-id="e4d37-294">`await foreach` を実行できるだけでなく、非同期反復子を作成することもできます。たとえば、`await` と`yield` の両方を行うことができる `IAsyncEnumerable/IAsyncEnumerator` を返す反復子です。</span><span class="sxs-lookup"><span data-stu-id="e4d37-294">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="e4d37-295">破棄する必要があるオブジェクトの場合は、`Stream` や `Timer` など、さまざまな BCL 型が実装する `IAsyncDisposable` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-295">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

<span data-ttu-id="e4d37-296">詳細については、[非同期ストリームのチュートリアル](../../csharp/tutorials/generate-consume-asynchronous-stream.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4d37-296">For more information, see the [async streams tutorial](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span></span>

## <a name="ieee-floating-point-improvements"></a><span data-ttu-id="e4d37-297">IEEE 浮動小数点の改良</span><span class="sxs-lookup"><span data-stu-id="e4d37-297">IEEE Floating-point improvements</span></span>

<span data-ttu-id="e4d37-298">浮動小数点 API は、[IEEE 754-2008 リビジョン](https://en.wikipedia.org/wiki/IEEE_754-2008_revision)に準拠するように更新されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-298">Floating point APIs are being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="e4d37-299">これらの変更の目的は、すべての**必要な**操作を公開し、それらの動作が IEEE 仕様に準拠していることを保証することです。浮動小数点の改良の詳細については、「[Floating-Point Parsing and Formatting improvements in .NET Core 3.0 (.NET Core 3.0 の浮動小数点の解析と形式の改良)](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/)」のブログ記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4d37-299">The goal of these changes is to expose all **required** operations and ensure that they're behaviorally compliant with the IEEE spec. For more information about floating-point improvements, see the [Floating-Point Parsing and Formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.</span></span>

<span data-ttu-id="e4d37-300">次のような解析および書式設定の修正があります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-300">Parsing and formatting fixes include:</span></span>

- <span data-ttu-id="e4d37-301">任意の長さの入力を正しく解析して丸める。</span><span class="sxs-lookup"><span data-stu-id="e4d37-301">Correctly parse and round inputs of any length.</span></span>
- <span data-ttu-id="e4d37-302">負のゼロを正しく解析して書式設定する。</span><span class="sxs-lookup"><span data-stu-id="e4d37-302">Correctly parse and format negative zero.</span></span>
- <span data-ttu-id="e4d37-303">大文字と小文字を区別しないチェックを実行し、可能な場合には省略可能な先行の `+` を許可することで、`Infinity` と `NaN` を正しく解析する。</span><span class="sxs-lookup"><span data-stu-id="e4d37-303">Correctly parse `Infinity` and `NaN` by doing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="e4d37-304">新しい <xref:System.Math?displayProperty=nameWithType> API には以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-304">New <xref:System.Math?displayProperty=nameWithType> APIs include:</span></span>

- <span data-ttu-id="e4d37-305"><xref:System.Math.BitIncrement(System.Double)> と <xref:System.Math.BitDecrement(System.Double)></span><span class="sxs-lookup"><span data-stu-id="e4d37-305"><xref:System.Math.BitIncrement(System.Double)> and <xref:System.Math.BitDecrement(System.Double)></span></span>\
<span data-ttu-id="e4d37-306">`nextUp` および `nextDown` の IEEE 演算に相当します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-306">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="e4d37-307">入力よりも大きいか小さいかを比較する最小の浮動小数点をそれぞれ返します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-307">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="e4d37-308">たとえば、`Math.BitIncrement(0.0)` は `double.Epsilon` を返します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-308">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

- <span data-ttu-id="e4d37-309"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> と <xref:System.Math.MinMagnitude(System.Double,System.Double)></span><span class="sxs-lookup"><span data-stu-id="e4d37-309"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> and <xref:System.Math.MinMagnitude(System.Double,System.Double)></span></span>\
<span data-ttu-id="e4d37-310">`maxNumMag` および `minNumMag` の IEEE 演算に相当します。2 つの入力の大きさがより大きいまたはより小さい値をそれぞれ返します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-310">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="e4d37-311">たとえば、`Math.MaxMagnitude(2.0, -3.0)` は `-3.0` を返します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-311">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

- <xref:System.Math.ILogB(System.Double)>\
<span data-ttu-id="e4d37-312">整数値を返す `logB` IEEE 演算に相当します。入力パラメーターの 2 を底とする積分対数を返します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-312">Corresponds to the `logB` IEEE operation that returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="e4d37-313">このメソッドは実質的に `floor(log2(x))` と同じですが、最小限の丸め誤差で実行されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-313">This method is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

- <xref:System.Math.ScaleB(System.Double,System.Int32)>\
<span data-ttu-id="e4d37-314">整数値を受け取る `scaleB` IEEE 演算に相当します。これは実質的に `x * pow(2, n)` と同じですが、最小限の丸め誤差で実行されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-314">Corresponds to the `scaleB` IEEE operation that takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

- <xref:System.Math.Log2(System.Double)>\
<span data-ttu-id="e4d37-315">`log2` IEEE 演算に相当します。2 を底とする対数を返します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-315">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="e4d37-316">丸め誤差を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-316">It minimizes rounding error.</span></span>

- <xref:System.Math.FusedMultiplyAdd(System.Double,System.Double,System.Double)>\
<span data-ttu-id="e4d37-317">`fma` IEEE 演算に相当します。融合型積和演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-317">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="e4d37-318">つまり、単一操作として `(x * y) + z` を実行することで、丸め誤差を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-318">That is, it does `(x * y) + z` as a single operation, thereby minimizing the rounding error.</span></span> <span data-ttu-id="e4d37-319">例では、`FusedMultiplyAdd(1e308, 2.0, -1e308)` は `1e308` を返します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-319">An example would be `FusedMultiplyAdd(1e308, 2.0, -1e308)` which returns `1e308`.</span></span> <span data-ttu-id="e4d37-320">正規の `(1e308 * 2.0) - 1e308` は `double.PositiveInfinity` を返します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-320">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

- <xref:System.Math.CopySign(System.Double,System.Double)>\
<span data-ttu-id="e4d37-321">`copySign` IEEE 演算に相当します。`x` の値を返しますが、`y` の符号と共に返されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-321">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

## <a name="fast-built-in-json-support"></a><span data-ttu-id="e4d37-322">高速な組み込み JSON のサポート</span><span class="sxs-lookup"><span data-stu-id="e4d37-322">Fast built-in JSON support</span></span>

<span data-ttu-id="e4d37-323">.NET ユーザーは、[**Json.NET**](https://www.newtonsoft.com/json) や他のよく使われている JSON ライブラリに大きく依存しています。これは今後も推奨されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-323">.NET users have largely relied on [**Json.NET**](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="e4d37-324">**Json.NET** では .NET の文字列が基本のデータ型 (内部的には UTF-16) として使用されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-324">**Json.NET** uses .NET strings as its base datatype, which is UTF-16 under the hood.</span></span>

<span data-ttu-id="e4d37-325">新しい組み込みの JSON サポートは、高パフォーマンス、低割り当てで、`Span<byte>` に基づいています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-325">The new built-in JSON support is high-performance, low allocation, and based on `Span<byte>`.</span></span> <span data-ttu-id="e4d37-326">3 つの新しい JSON 関連の主な型が、.NET Core 3.0 の <xref:System.Text.Json?displayProperty=nameWithType> 名前空間に追加されました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-326">Three new main JSON-related types have been added to .NET Core 3.0 the <xref:System.Text.Json?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="e4d37-327">これらの型は、単純な従来の CLR オブジェクト (POCO) のシリアル化と逆シリアル化を "*まだ*" サポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e4d37-327">These types don't *yet* support plain old CLR object (POCO) serialization and deserialization.</span></span>

### <a name="utf8jsonreader"></a><span data-ttu-id="e4d37-328">Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="e4d37-328">Utf8JsonReader</span></span>

<span data-ttu-id="e4d37-329"><xref:System.Text.Json.Utf8JsonReader?displayProperty=nameWithType> は、UTF-8 でエンコードされた JSON テキスト用の高パフォーマンス、低割り当て、転送のみのリーダーです。`ReadOnlySpan<byte>` から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-329"><xref:System.Text.Json.Utf8JsonReader?displayProperty=nameWithType> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="e4d37-330">`Utf8JsonReader` は基本的で低レベルの型であり、カスタム パーサーとデシリアライザーを構築するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-330">The `Utf8JsonReader` is a foundational, low-level type, that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="e4d37-331">新しい `Utf8JsonReader` を使用して JSON ペイロードを読み取る処理は、**Json.NET** のリーダーを使用する場合より 2 倍高速です。</span><span class="sxs-lookup"><span data-stu-id="e4d37-331">Reading through a JSON payload using the new `Utf8JsonReader` is 2x faster than using the reader from **Json.NET**.</span></span> <span data-ttu-id="e4d37-332">JSON トークンを (UTF-16) 文字列として実現する必要が出てくるまでは割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="e4d37-332">It doesn't allocate until you need to actualize JSON tokens as (UTF-16) strings.</span></span>

<span data-ttu-id="e4d37-333">Visual Studio Code で作成された [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) ファイルを読み取る例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-333">Here is an example of reading through the [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) file created by Visual Studio Code:</span></span>

[!CODE-csharp[Utf8JsonReader](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#PrintJson)]

[!CODE-csharp[Utf8JsonReader](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#PrintJsonCall)]

### <a name="utf8jsonwriter"></a><span data-ttu-id="e4d37-334">Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="e4d37-334">Utf8JsonWriter</span></span>

<span data-ttu-id="e4d37-335"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> は、`String`、`Int32`、`DateTime` のような一般的な.NET 型から UTF-8 でエンコードされた JSON テキストを書き込むための、ハイパフォーマンス、非キャッシュ、前方参照専用の方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-335"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> provides a high-performance, non-cached, forward-only way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="e4d37-336">リーダーと同様に、ライターは基本的で低レベルの型であり、カスタム シリアライザーを構築するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-336">Like the reader, the writer is a foundational, low-level type, that can be used to build custom serializers.</span></span> <span data-ttu-id="e4d37-337">新しい `Utf8JsonWriter` を使用して JSON ペイロードを書き込むと、**Json.NET** からライターを使用するよりも 30 - 80% 高速になり、割り当てが行われません。</span><span class="sxs-lookup"><span data-stu-id="e4d37-337">Writing a JSON payload using the new `Utf8JsonWriter` is 30-80% faster than using the writer from **Json.NET** and doesn't allocate.</span></span>

### <a name="jsondocument"></a><span data-ttu-id="e4d37-338">JsonDocument</span><span class="sxs-lookup"><span data-stu-id="e4d37-338">JsonDocument</span></span>

<span data-ttu-id="e4d37-339"><xref:System.Text.Json.JsonDocument?displayProperty=nameWithType> は、`Utf8JsonReader` に基づいています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-339"><xref:System.Text.Json.JsonDocument?displayProperty=nameWithType> is built on top of the `Utf8JsonReader`.</span></span> <span data-ttu-id="e4d37-340">`JsonDocument` は、JSON データを解析し、ランダム アクセスと列挙型をサポートするためにクエリできる読み取り専用ドキュメント オブジェクト モデル (DOM) をビルドする機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-340">The `JsonDocument` provides the ability to parse JSON data and build a read-only Document Object Model (DOM) that can be queried to support random access and enumeration.</span></span> <span data-ttu-id="e4d37-341">データを作成する JSON 要素には、`RootElement` というプロパティとして `JsonDocument` によって公開される <xref:System.Text.Json.JsonElement> 型を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-341">The JSON elements that compose the data can be accessed via the <xref:System.Text.Json.JsonElement> type that is exposed by the `JsonDocument` as a property called `RootElement`.</span></span> <span data-ttu-id="e4d37-342">`JsonElement` には、JSON 配列とオブジェクト列挙子とともに、JSON テキストを一般的な .NET 型に変換する API が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-342">The `JsonElement` contains the JSON array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="e4d37-343">一般的な JSON ペイロードを解析し、`JsonDocument` を使用してそのメンバーすべてにアクセスすると、適度にサイズ指定された (つまり 1 MB 未満) データに対する割り当てがほとんどない **Json.NET** よりも 2 - 3 倍高速になります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-343">Parsing a typical JSON payload and accessing all its members using the `JsonDocument` is 2-3x faster than **Json.NET** with little allocations for data that is reasonably sized (that is, < 1 MB).</span></span>

<span data-ttu-id="e4d37-344">出発点として使用できる `JsonDocument` および `JsonElement` の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-344">Here is a sample usage of the `JsonDocument` and `JsonElement` that can be used as a starting point:</span></span>

[!CODE-csharp[JsonDocument](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#ReadJson)]

<span data-ttu-id="e4d37-345">Visual Studio Code で作成された [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) ファイルを読み取る C# 8.0 の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-345">Here is a C# 8.0 example of reading through the [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) file created by Visual Studio Code:</span></span>

[!CODE-csharp[JsonDocument](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#ReadJsonCall)]

### <a name="jsonserializer"></a><span data-ttu-id="e4d37-346">JsonSerializer</span><span class="sxs-lookup"><span data-stu-id="e4d37-346">JsonSerializer</span></span>

<span data-ttu-id="e4d37-347"><xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> は <xref:System.Text.Json.Utf8JsonReader> と <xref:System.Text.Json.Utf8JsonWriter> に基づいて構築されており、JSON ドキュメントやフラグメントを操作する際に高速で低メモリのシリアル化オプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-347"><xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> is built on top of <xref:System.Text.Json.Utf8JsonReader> and <xref:System.Text.Json.Utf8JsonWriter> to provide a fast, low-memory serialization option when working with JSON documents and fragments.</span></span>

<span data-ttu-id="e4d37-348">オブジェクトを JSON にシリアル化する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-348">Here is an example of serializing an object to JSON:</span></span>

[!CODE-csharp[JsonSerializer](~/samples/snippets/core/whats-new/whats-new-in-30/cs/JSON.cs#JsonSerialize)]

<span data-ttu-id="e4d37-349">JSON 文字列をオブジェクトに逆シリアル化する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-349">Here is an example of deserializing a JSON string to an object.</span></span> <span data-ttu-id="e4d37-350">前の例で生成された JSON 文字列を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-350">You can use the JSON string produced by the previous example:</span></span>

[!CODE-csharp[JsonDeserializer](~/samples/snippets/core/whats-new/whats-new-in-30/cs/JSON.cs#JsonDeserialize)]

## <a name="interop-improvements"></a><span data-ttu-id="e4d37-351">相互運用性の機能強化</span><span class="sxs-lookup"><span data-stu-id="e4d37-351">Interop improvements</span></span>

<span data-ttu-id="e4d37-352">.NET Core 3.0 では、ネイティブ API の相互運用性が強化されました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-352">.NET Core 3.0 improves native API interop.</span></span>

### <a name="type-nativelibrary"></a><span data-ttu-id="e4d37-353">型:NativeLibrary</span><span class="sxs-lookup"><span data-stu-id="e4d37-353">Type: NativeLibrary</span></span>

<span data-ttu-id="e4d37-354"><xref:System.Runtime.InteropServices.NativeLibrary?displayProperty=nameWithType> には、(.NET Core P/Invoke と同じ読み込みロジックを使用して) ネイティブ ライブラリを読み込み、`getSymbol` などの関連するヘルパー関数を指定するためのカプセル化機能があります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-354"><xref:System.Runtime.InteropServices.NativeLibrary?displayProperty=nameWithType> provides an encapsulation for loading a native library (using the same load logic as .NET Core P/Invoke) and providing the relevant helper functions such as `getSymbol`.</span></span> <span data-ttu-id="e4d37-355">コード例については、[DLLMap のデモ](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4d37-355">For a code example, see the [DLLMap Demo](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin).</span></span>

### <a name="windows-native-interop"></a><span data-ttu-id="e4d37-356">Windows のネイティブ相互運用機能</span><span class="sxs-lookup"><span data-stu-id="e4d37-356">Windows Native Interop</span></span>

<span data-ttu-id="e4d37-357">Windows では、フラット C API、COM、および WinRT の形式で、質の高いネイティブ API を提供しています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-357">Windows offers a rich native API in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="e4d37-358">.NET Core は **P/Invoke** をサポートしますが、.NET Core 3.0 では **COM API の CoCreate** と **WinRT API のアクティブ化**を行う機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-358">While .NET Core supports **P/Invoke**, .NET Core 3.0 adds the ability to **CoCreate COM APIs** and **Activate WinRT APIs**.</span></span> <span data-ttu-id="e4d37-359">コード例については、[Excel のデモ](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4d37-359">For a code example, see the [Excel Demo](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>

## <a name="http2-support"></a><span data-ttu-id="e4d37-360">HTTP/2 のサポート</span><span class="sxs-lookup"><span data-stu-id="e4d37-360">HTTP/2 support</span></span>

<span data-ttu-id="e4d37-361"><xref:System.Net.Http.HttpClient?displayProperty=nameWithType> 型は HTTP/2 プロトコルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-361">The <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> type supports the HTTP/2 protocol.</span></span> <span data-ttu-id="e4d37-362">HTTP/2 が有効な場合、HTTP プロトコルのバージョンは TLS/ALPN を介してネゴシエートされ、HTTP/2 はサーバーがそれを使用することを選択した場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-362">If HTTP/2 is enabled, the HTTP protocol version is negotiated via TLS/ALPN, and HTTP/2 is used if the server elects to use it.</span></span>

<span data-ttu-id="e4d37-363">既定のプロトコルは HTTP/1.1 のままですが、2 つの方法で HTTP/2 を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-363">The default protocol remains HTTP/1.1, but HTTP/2 can be enabled in two different ways.</span></span> <span data-ttu-id="e4d37-364">1 つ目として、HTTP/2 を使うように HTTP 要求メッセージを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-364">First, you can set the HTTP request message to use HTTP/2:</span></span>

[!CODE-csharp[Http2Request](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Request)]

<span data-ttu-id="e4d37-365">2 つ目として、既定で HTTP/2 を使うように <xref:System.Net.Http.HttpClient> を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-365">Second, you can change <xref:System.Net.Http.HttpClient> to use HTTP/2 by default:</span></span>

[!CODE-csharp[Http2Client](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Client)]

<span data-ttu-id="e4d37-366">多くの場合、アプリケーションを開発しているときは、暗号化されていない接続を使います。</span><span class="sxs-lookup"><span data-stu-id="e4d37-366">Many times when you're developing an application, you want to use an unencrypted connection.</span></span> <span data-ttu-id="e4d37-367">ターゲット エンドポイントで HTTP/2 が使われることがわかっている場合は、HTTP/2 用の暗号化されていない接続を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-367">If you know the target endpoint will be using HTTP/2, you can turn on unencrypted connections for HTTP/2.</span></span> <span data-ttu-id="e4d37-368">有効にするには、`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` 環境変数を `1` に設定するか、またはアプリのコンテキストで有効にします。</span><span class="sxs-lookup"><span data-stu-id="e4d37-368">You can turn it on by setting the `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` environment variable to `1` or by enabling it in the app context:</span></span>

[!CODE-csharp[Http2Context](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#AppContext)]

## <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="e4d37-369">Linux 上の TLS 1.3 と OpenSSL 1.1.1</span><span class="sxs-lookup"><span data-stu-id="e4d37-369">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="e4d37-370">.NET Core では、特定の環境で使用できるようになったときに、[OpenSSL 1.1.1 の TLS 1.3 のサポート](https://www.openssl.org/blog/blog/2018/09/11/release111/)を利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-370">.NET Core now takes advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it's available in a given environment.</span></span> <span data-ttu-id="e4d37-371">TLS 1.3 の場合:</span><span class="sxs-lookup"><span data-stu-id="e4d37-371">With TLS 1.3:</span></span>

- <span data-ttu-id="e4d37-372">クライアントとサーバー間に必要なラウンド トリップ回数が減るため、接続時間が改善されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-372">Connection times are improved with reduced round trips required between the client and server.</span></span>
- <span data-ttu-id="e4d37-373">古い安全ではないさまざまな暗号化アルゴリズムが削除されたので、セキュリティが強化されました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-373">Improved security because of the removal of various obsolete and insecure cryptographic algorithms.</span></span>

<span data-ttu-id="e4d37-374">使用できる場合、.NET Core 3.0 では Linux システム上で **OpenSSL 1.1.1**、**OpenSSL 1.1.0**、または **OpenSSL 1.0.2** が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-374">When available, .NET Core 3.0 uses **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** on a Linux system.</span></span> <span data-ttu-id="e4d37-375">**OpenSSL 1.1.1** が使用できる場合、<xref:System.Net.Security.SslStream?displayProperty=nameWithType> 型と <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> 型の両方が **TLS 1.3** を使用します (クライアントとサーバーの両方が **TLS 1.3** をサポートしている場合)。</span><span class="sxs-lookup"><span data-stu-id="e4d37-375">When **OpenSSL 1.1.1** is available, both <xref:System.Net.Security.SslStream?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> types will use **TLS 1.3** (assuming both the client and server support **TLS 1.3**).</span></span>

>[!IMPORTANT]
><span data-ttu-id="e4d37-376">Windows と macOS はまだ **TLS 1.3** をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e4d37-376">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="e4d37-377">サポートされるようになったら、.NET Core 3.0 はこれらのオペレーティング システムで **TLS 1.3** をサポートする予定です。</span><span class="sxs-lookup"><span data-stu-id="e4d37-377">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

<span data-ttu-id="e4d37-378">次の C# 8.0 の例は、<https://www.cloudflare.com> に接続している Ubuntu 18.10 上の .NET Core 3.0 を示しています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-378">The following C# 8.0 example demonstrates .NET Core 3.0 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

[!CODE-csharp[TLSExample](~/samples/snippets/core/whats-new/whats-new-in-30/cs/TLS.cs#TLS)]

## <a name="cryptography-ciphers"></a><span data-ttu-id="e4d37-379">暗号化の暗号</span><span class="sxs-lookup"><span data-stu-id="e4d37-379">Cryptography ciphers</span></span>

<span data-ttu-id="e4d37-380">.NET 3.0 では、**AES-GCM** および **AES-CCM** の暗号のサポートが追加され、それぞれ <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> および <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> で実装されています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-380">.NET 3.0 adds support for **AES-GCM** and **AES-CCM** ciphers, implemented with <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> and <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> respectively.</span></span> <span data-ttu-id="e4d37-381">これらのアルゴリズムは、いずれも [Authenticated Encryption with Association Data (AEAD) アルゴリズム](https://en.wikipedia.org/wiki/Authenticated_encryption)です。</span><span class="sxs-lookup"><span data-stu-id="e4d37-381">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption).</span></span>

<span data-ttu-id="e4d37-382">次のコードは、`AesGcm` 暗号を使用してランダム データの暗号化と復号化を行う例です。</span><span class="sxs-lookup"><span data-stu-id="e4d37-382">The following code demonstrates using `AesGcm` cipher to encrypt and decrypt random data.</span></span>

[!CODE-csharp[AesGcm](~/samples/snippets/core/whats-new/whats-new-in-30/cs/Cipher.cs#AesGcm)]

## <a name="cryptographic-key-importexport"></a><span data-ttu-id="e4d37-383">暗号化キーのインポート/エクスポート</span><span class="sxs-lookup"><span data-stu-id="e4d37-383">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="e4d37-384">.NET Core 3.0 は、標準形式からの非対称の公開キーと秘密キーのインポートとエクスポートをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-384">.NET Core 3.0 supports the import and export of asymmetric public and private keys from standard formats.</span></span> <span data-ttu-id="e4d37-385">X.509 証明書を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e4d37-385">You don't need to use an X.509 certificate.</span></span>

<span data-ttu-id="e4d37-386">*RSA*、*DSA*、*ECDsa*、*ECDiffieHellman* などのすべてのキー種類は、以下の形式をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e4d37-386">All key types, such as *RSA*, *DSA*, *ECDsa*, and *ECDiffieHellman*, support the following formats:</span></span>

- <span data-ttu-id="e4d37-387">**公開キー**</span><span class="sxs-lookup"><span data-stu-id="e4d37-387">**Public Key**</span></span>
  - <span data-ttu-id="e4d37-388">X.509 SubjectPublicKeyInfo</span><span class="sxs-lookup"><span data-stu-id="e4d37-388">X.509 SubjectPublicKeyInfo</span></span>

- <span data-ttu-id="e4d37-389">**秘密キー**</span><span class="sxs-lookup"><span data-stu-id="e4d37-389">**Private key**</span></span>
  - <span data-ttu-id="e4d37-390">PKCS#8 PrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="e4d37-390">PKCS#8 PrivateKeyInfo</span></span>
  - <span data-ttu-id="e4d37-391">PKCS#8 EncryptedPrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="e4d37-391">PKCS#8 EncryptedPrivateKeyInfo</span></span>

<span data-ttu-id="e4d37-392">RSA キーは以下もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-392">RSA keys also support:</span></span>

- <span data-ttu-id="e4d37-393">**公開キー**</span><span class="sxs-lookup"><span data-stu-id="e4d37-393">**Public Key**</span></span>
  - <span data-ttu-id="e4d37-394">PKCS#1 RSAPublicKey</span><span class="sxs-lookup"><span data-stu-id="e4d37-394">PKCS#1 RSAPublicKey</span></span>

- <span data-ttu-id="e4d37-395">**秘密キー**</span><span class="sxs-lookup"><span data-stu-id="e4d37-395">**Private key**</span></span>
  - <span data-ttu-id="e4d37-396">PKCS#1 RSAPrivateKey</span><span class="sxs-lookup"><span data-stu-id="e4d37-396">PKCS#1 RSAPrivateKey</span></span>

<span data-ttu-id="e4d37-397">エクスポートメソッドからは、DER でエンコードされたバイナリ データが生成され、インポート メソッドもそのようなデータを期待します。</span><span class="sxs-lookup"><span data-stu-id="e4d37-397">The export methods produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="e4d37-398">キーがテキストに適した PEM 形式で格納されている場合、呼び出し元は import メソッドを呼び出す前にコンテンツを base64 でデコードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-398">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

[!CODE-csharp[RSA](~/samples/snippets/core/whats-new/whats-new-in-30/cs/RSA.cs#Rsa)]

<span data-ttu-id="e4d37-399">**PKCS#8** ファイルは <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> を使用して検査できます。また、 **PFX/PKCS#12** ファイルは <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType> を使用して検査できます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-399">**PKCS#8** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> and **PFX/PKCS#12** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e4d37-400">**PFX/PKCS#12** ファイルは <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType> を使用して操作できます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-400">**PFX/PKCS#12** files can be manipulated with <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span></span>

## <a name="serialport-for-linux"></a><span data-ttu-id="e4d37-401">Linux 用 SerialPort</span><span class="sxs-lookup"><span data-stu-id="e4d37-401">SerialPort for Linux</span></span>

<span data-ttu-id="e4d37-402">.Net Core 3.0 では、Linux 上の <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> に対する基本サポートを提供しています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-402">.NET Core 3.0 provides basic support for <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="e4d37-403">以前の .NET Core では、Windows 上の `SerialPort` の使用のみをサポートしていました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-403">Previously, .NET Core only supported using `SerialPort` on Windows.</span></span>

<span data-ttu-id="e4d37-404">Linux 上のシリアル ポートの制限付きサポートの詳細については、[GitHub 問題 #33146](https://github.com/dotnet/corefx/issues/33146) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4d37-404">For more information about the limited support for the serial port on Linux, see [GitHub issue #33146](https://github.com/dotnet/corefx/issues/33146).</span></span>

## <a name="docker-and-cgroup-memory-limits"></a><span data-ttu-id="e4d37-405">Docker と cgroup のメモリ制限</span><span class="sxs-lookup"><span data-stu-id="e4d37-405">Docker and cgroup memory Limits</span></span>

<span data-ttu-id="e4d37-406">Preview 3 以降、Linux 上の Docker を使用した .NET Core 3.0 の実行は、cgroup のメモリ制限と適切に連携するようになりました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-406">Starting with Preview 3, running .NET Core 3.0 on Linux with Docker works better with cgroup memory limits.</span></span> <span data-ttu-id="e4d37-407">`docker run -m` のように、メモリ制限を使用して Docker コンテナーを実行すると、.NET Core の動作が変わります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-407">Running a Docker container with memory limits, such as with `docker run -m`, changes how .NET Core behaves.</span></span>

- <span data-ttu-id="e4d37-408">既定のガベージ コレクター (GC) ヒープ サイズ: 最大 20 MB、またはコンテナーのメモリ制限の 75%。</span><span class="sxs-lookup"><span data-stu-id="e4d37-408">Default Garbage Collector (GC) heap size: maximum of 20 mb or 75% of the memory limit on the container.</span></span>
- <span data-ttu-id="e4d37-409">明示的なサイズは、cgroup 制限の絶対数または割合として設定できます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-409">Explicit size can be set as an absolute number or percentage of cgroup limit.</span></span>
- <span data-ttu-id="e4d37-410">GC ヒープあたりの最小予約セグメント サイズは 16 MB です。</span><span class="sxs-lookup"><span data-stu-id="e4d37-410">Minimum reserved segment size per GC heap is 16 mb.</span></span> <span data-ttu-id="e4d37-411">このサイズによって、マシン上に作成されるヒープ数が減ります。</span><span class="sxs-lookup"><span data-stu-id="e4d37-411">This size reduces the number of heaps that are created on machines.</span></span>

## <a name="smaller-garbage-collection-heap-sizes"></a><span data-ttu-id="e4d37-412">小さいガベージ コレクションのヒープ サイズ</span><span class="sxs-lookup"><span data-stu-id="e4d37-412">Smaller Garbage Collection heap sizes</span></span>

<span data-ttu-id="e4d37-413">ガベージ コレクターの既定のヒープ サイズが縮小され、.NET Core のメモリ使用量が減少しました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-413">The Garbage Collector's default heap size has been reduced resulting in .NET Core using less memory.</span></span> <span data-ttu-id="e4d37-414">この変更は、最新のプロセッサ キャッシュ サイズでは、世代 0 の割り当て予算に合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="e4d37-414">This change better aligns with the generation 0 allocation budget with modern processor cache sizes.</span></span>

## <a name="garbage-collection-large-page-support"></a><span data-ttu-id="e4d37-415">ガベージ コレクションのラージ ページのサポート</span><span class="sxs-lookup"><span data-stu-id="e4d37-415">Garbage Collection Large Page support</span></span>

<span data-ttu-id="e4d37-416">ラージ ページ (Linux ではヒュージ ページとも呼ばれます) は、オペレーティング システムがネイティブ ページ サイズ (多くの場合は 4K) よりも大きいメモリ領域を確立して、このようなラージ ページを要求するアプリケーションのパフォーマンスを向上できる機能です。</span><span class="sxs-lookup"><span data-stu-id="e4d37-416">Large Pages (also known as Huge Pages on Linux) is a feature where the operating system is able to establish memory regions larger than the native page size (often 4K) to improve performance of the application requesting these large pages.</span></span>

<span data-ttu-id="e4d37-417">Windows 上でラージ ページを割り当てることを選択するオプトイン機能として、**GCLargePages** 設定を使用してガベージ コレクターを構成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-417">The Garbage Collector can now be configured with the **GCLargePages** setting as an opt-in feature to choose to allocate large pages on Windows.</span></span>

## <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="e4d37-418">Raspberry Pi の GPIO サポート</span><span class="sxs-lookup"><span data-stu-id="e4d37-418">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="e4d37-419">GPIO プログラミングに使用できる 2 つのパッケージが NuGet にリリースされました。</span><span class="sxs-lookup"><span data-stu-id="e4d37-419">Two packages have been released to NuGet that you can use for GPIO programming:</span></span>

- [<span data-ttu-id="e4d37-420">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="e4d37-420">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio)
- [<span data-ttu-id="e4d37-421">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="e4d37-421">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings)

<span data-ttu-id="e4d37-422">GPIO パッケージには、*GPIO*、*SPI*、*I2C*、および *PWM* デバイス用の API が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-422">The GPIO packages include APIs for *GPIO*, *SPI*, *I2C*, and *PWM* devices.</span></span> <span data-ttu-id="e4d37-423">IoT バインディング パッケージにはデバイス バインディングが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-423">The IoT bindings package includes device bindings.</span></span> <span data-ttu-id="e4d37-424">詳細については、[デバイス GitHub リポジトリ](https://github.com/dotnet/iot/blob/master/src/devices/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4d37-424">For more information, see the [devices GitHub repo](https://github.com/dotnet/iot/blob/master/src/devices/).</span></span>

## <a name="arm64-linux-support"></a><span data-ttu-id="e4d37-425">ARM64 Linux のサポート</span><span class="sxs-lookup"><span data-stu-id="e4d37-425">ARM64 Linux support</span></span>

<span data-ttu-id="e4d37-426">.NET Core 3.0 では、Linux 用の ARM64 のサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-426">.NET Core 3.0 adds support for ARM64 for Linux.</span></span> <span data-ttu-id="e4d37-427">現在、ARM64 の主なユース ケースは、IoT シナリオを使用しています。</span><span class="sxs-lookup"><span data-stu-id="e4d37-427">The primary use case for ARM64 is currently with IoT scenarios.</span></span> <span data-ttu-id="e4d37-428">詳細については、[.NET Core ARM64 の状態](https://github.com/dotnet/announcements/issues/82)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4d37-428">For more information, see [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82).</span></span>

<span data-ttu-id="e4d37-429">[ARM64 上の .NET Core 用の Docker イメージ](https://hub.docker.com/r/microsoft/dotnet/)は、Alpine、Debian、および Ubuntu に使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4d37-429">[Docker images for .NET Core on ARM64](https://hub.docker.com/r/microsoft/dotnet/) are available for Alpine, Debian, and Ubuntu.</span></span>

> [!NOTE]
> <span data-ttu-id="e4d37-430">**ARM64** Windows のサポートはまだ使用できません。</span><span class="sxs-lookup"><span data-stu-id="e4d37-430">**ARM64** Windows support isn't yet available.</span></span>
