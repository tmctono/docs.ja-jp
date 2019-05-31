---
title: .NET Core 3.0 の新機能
description: .NET Core 3.0 の新機能について説明します。
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 05/06/2019
ms.openlocfilehash: 8d6ff6bc55384281119600f2323212441c1815e9
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452472"
---
# <a name="whats-new-in-net-core-30-preview-5"></a><span data-ttu-id="b6b5f-103">.NET Core 3.0 (Preview 5) の新機能</span><span class="sxs-lookup"><span data-stu-id="b6b5f-103">What's new in .NET Core 3.0 (Preview 5)</span></span>

<span data-ttu-id="b6b5f-104">この記事では、.NET Core 3.0 (Preview 5 まで) の新機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-104">This article describes what is new in .NET Core 3.0 (through preview 5).</span></span> <span data-ttu-id="b6b5f-105">最も大きな強化点の 1 つは、Windows デスクトップ アプリケーションのサポートです (Windows のみ)。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="b6b5f-106">.NET Core 3.0 SDK コンポーネントの Windows デスクトップを使用して、Windows フォームおよび Windows Presentation Foundation (WPF) アプリケーションを移植することができます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-106">By using the .NET Core 3.0 SDK component Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="b6b5f-107">誤解のないように言うと、Windows Desktop コンポーネントは Windows でのみサポートされており、Windows にのみ含まれています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="b6b5f-108">詳細については、この記事で後述する「[Windows デスクトップ](#windows-desktop)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-108">For more information, see the [Windows desktop](#windows-desktop) section later in this article.</span></span>

<span data-ttu-id="b6b5f-109">.NET Core 3.0 では C# 8.0 のサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-109">.NET Core 3.0 adds support for C# 8.0.</span></span> <span data-ttu-id="b6b5f-110">最新リリースの Visual Studio 2019 Update 1 Preview または OmniSharp 拡張機能を含む VSCode を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-110">It's highly recommended that you use the latest release of Visual Studio 2019 Update 1 Preview or VSCode with the OmniSharp extension.</span></span>

<span data-ttu-id="b6b5f-111">[.NET Core 3.0 Preview 5 を今すぐダウンロード](https://aka.ms/netcore3download)して Windows、Mac、Linux 上で使い始めましょう。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-111">[Download and get started with .NET Core 3.0 Preview 5](https://aka.ms/netcore3download) right now on Windows, Mac, and Linux.</span></span>

<span data-ttu-id="b6b5f-112">各プレビュー リリースの詳細については、次の発表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-112">For more information about each preview release, see the following announcements:</span></span>

- [<span data-ttu-id="b6b5f-113">.NET Core 3.0 Preview 5 の発表</span><span class="sxs-lookup"><span data-stu-id="b6b5f-113">.NET Core 3.0 Preview 5 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-5/)
- [<span data-ttu-id="b6b5f-114">.NET Core 3.0 Preview 4 の発表</span><span class="sxs-lookup"><span data-stu-id="b6b5f-114">.NET Core 3.0 Preview 4 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-4/)
- [<span data-ttu-id="b6b5f-115">.NET Core 3.0 Preview 3 の発表</span><span class="sxs-lookup"><span data-stu-id="b6b5f-115">.NET Core 3.0 Preview 3 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-3/)
- [<span data-ttu-id="b6b5f-116">.NET Core 3.0 Preview 2 の発表</span><span class="sxs-lookup"><span data-stu-id="b6b5f-116">.NET Core 3.0 Preview 2 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-2/)
- [<span data-ttu-id="b6b5f-117">.NET Core 3.0 Preview 1 の発表</span><span class="sxs-lookup"><span data-stu-id="b6b5f-117">.NET Core 3.0 Preview 1 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/)

## <a name="net-core-sdk-windows-installer"></a><span data-ttu-id="b6b5f-118">.NET Core SDK Windows インストーラー</span><span class="sxs-lookup"><span data-stu-id="b6b5f-118">.NET Core SDK Windows Installer</span></span>

<span data-ttu-id="b6b5f-119">Windows 用の MSI インストーラーは、.NET Core 3.0 から変更されました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-119">The MSI installer for Windows has changed starting with .NET Core 3.0.</span></span> <span data-ttu-id="b6b5f-120">SDK インストーラーは、SDK 機能帯リリースのアップグレードを実行するようになります。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-120">The SDK installers will now upgrade SDK feature-band releases in place.</span></span> <span data-ttu-id="b6b5f-121">機能帯は、バージョン番号の "*パッチ*" セクションの *100* 番台のグループで定義されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-121">Feature bands are defined in the *hundreds* groups in the *patch* section of the version number.</span></span> <span data-ttu-id="b6b5f-122">たとえば、**3.0.\*101**\* と **3.0.\*201**\* は 2 つの異なる機能帯のバージョンですが、**3.0.\*101**\* と **3.0.\*199**\* は同じ機能帯に含まれます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-122">For example, **3.0.\*101**\* and **3.0.\*201**\* are versions in two different feature bands while **3.0.\*101**\* and **3.0.\*199**\* are in the same feature band.</span></span> <span data-ttu-id="b6b5f-123">また、.NET Core SDK **3.0.\*101**\* をインストールすると、.NET Core SDK **3.0.\*100**\* が存在する場合はマシンから削除されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-123">And, when .NET Core SDK **3.0.\*101**\* is installed, .NET Core SDK **3.0.\*100**\* will be removed from the machine if it exists.</span></span> <span data-ttu-id="b6b5f-124">同じマシンに .NET Core SDK **3.0.\*200**\* をインストールすると、.NET Core SDK **3.0.\*101**\* は削除されません。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-124">When .NET Core SDK **3.0.\*200**\* is installed on the same machine, .NET Core SDK **3.0.\*101**\* won't be removed.</span></span>

<span data-ttu-id="b6b5f-125">バージョン管理の詳細については、「[.NET Core をバージョン管理する方法の概要](../versions/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-125">For more information about versioning, see [Overview of how .NET Core is versioned](../versions/index.md).</span></span>

## <a name="c-80-preview"></a><span data-ttu-id="b6b5f-126">C# 8.0 Preview</span><span class="sxs-lookup"><span data-stu-id="b6b5f-126">C# 8.0 preview</span></span>

<span data-ttu-id="b6b5f-127">.NET Core 3.0 は C# 8 Preview をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-127">.NET Core 3.0 supports C# 8 preview.</span></span> <span data-ttu-id="b6b5f-128">C# 8.0 の機能の詳細については、「[C# 8.0 の新機能](../../csharp/whats-new/csharp-8.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-128">For more information about C# 8.0 features, see [What's new in C# 8.0](../../csharp/whats-new/csharp-8.md).</span></span>

## <a name="net-standard-21"></a><span data-ttu-id="b6b5f-129">.NET Standard 2.1</span><span class="sxs-lookup"><span data-stu-id="b6b5f-129">.NET Standard 2.1</span></span>

<span data-ttu-id="b6b5f-130">.NET Core 3.0 は **.NET Standard 2.1** をサポートしていますが、既定の `dotnet new classlib` テンプレートでは、 **.NET Standard 2.0** をターゲットとするプロジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-130">Even though .NET Core 3.0 supports **.NET Standard 2.1**, the default `dotnet new classlib` template generates a project that targets **.NET Standard 2.0**.</span></span> <span data-ttu-id="b6b5f-131">**.NET Standard 2.1** をターゲットにするには、プロジェクト ファイルを編集して `TargetFramework` プロパティを `netstandard2.1` に変更します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-131">To target **.NET Standard 2.1**, edit your project file and change the `TargetFramework` property to `netstandard2.1`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
 
  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
  </PropertyGroup>
 
</Project>
```

<span data-ttu-id="b6b5f-132">Visual Studio を使用している場合、Visual Studio 2017 では **.NET Standard 2.1** または **.NET Core 3.0** がサポートされていないため、Visual Studio 2019 が必要です。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-132">If you're using Visual Studio, you need Visual Studio 2019, as Visual Studio 2017 doesn't support **.NET Standard 2.1** or **.NET Core 3.0**.</span></span> <span data-ttu-id="b6b5f-133">[Visual Studio 2019 Update 1 Preview](https://visualstudio.microsoft.com/vs/preview/) を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-133">We highly recommend that you use [Visual Studio 2019 Update 1 Preview](https://visualstudio.microsoft.com/vs/preview/).</span></span>

## <a name="improved-net-core-version-apis"></a><span data-ttu-id="b6b5f-134">強化された .NET Core バージョン API</span><span class="sxs-lookup"><span data-stu-id="b6b5f-134">Improved .NET Core Version APIs</span></span>

<span data-ttu-id="b6b5f-135">.NET Core 3.0 以降、.NET Core に提供されているバージョン API から、期待どおりの情報が返されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-135">Starting with .NET Core 3.0, the version APIs provided with .NET Core now return the information you expect.</span></span> <span data-ttu-id="b6b5f-136">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-136">For example:</span></span>

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
> <span data-ttu-id="b6b5f-137">破壊的変更。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-137">Breaking change.</span></span> <span data-ttu-id="b6b5f-138">バージョン管理スキームが変更されたので、これは技術的には破壊的変更です。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-138">This is technically a breaking change because the versioning scheme has changed.</span></span>

## <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="b6b5f-139">.NET プラットフォーム依存性</span><span class="sxs-lookup"><span data-stu-id="b6b5f-139">.NET Platform-Dependent Intrinsics</span></span>

<span data-ttu-id="b6b5f-140">特定のパフォーマンス指向 CPU 命令 (**SIMD** や **ビット操作命令**セット) にアクセスできるようにする API が追加されました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-140">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="b6b5f-141">これらの命令は、データを並列で効率的に処理するといった、特定のシナリオでパフォーマンスを大幅に向上するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-141">These instructions can help achieve significant performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span> 

<span data-ttu-id="b6b5f-142">.NET ライブラリでは、必要に応じて、パフォーマンスを向上するためにこれらの命令が使用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-142">Where appropriate, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="b6b5f-143">詳細については、「[.NET Platform Dependent Intrinsics (.NET プラットフォーム依存性)](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-143">For more information, see [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md).</span></span>

## <a name="default-executables"></a><span data-ttu-id="b6b5f-144">既定の実行可能ファイル</span><span class="sxs-lookup"><span data-stu-id="b6b5f-144">Default executables</span></span>

<span data-ttu-id="b6b5f-145">.NET Core では、既定で[フレームワーク依存の実行可能ファイル](../deploying/index.md#framework-dependent-executables-fde)が作成されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-145">.NET Core now builds [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="b6b5f-146">この動作は、グローバルにインストールされているバージョンの .NET Core を使用するアプリケーションの新機能です。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-146">This behavior is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="b6b5f-147">以前は、[自己完結型の配置](../deploying/index.md#self-contained-deployments-scd)でのみ実行可能ファイルが生成されました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-147">Previously, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="b6b5f-148">`dotnet build` または `dotnet publish` の実行中に、使用している SDK の環境およびプラットフォームと一致する実行可能ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-148">During `dotnet build` or `dotnet publish`, an executable is created that matches the environment and platform of the SDK you're using.</span></span> <span data-ttu-id="b6b5f-149">これらの実行可能ファイルでは、次のような他のネイティブ実行可能ファイルと同じことを期待できます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-149">You can expect the same things with these executables as you would other native executables, such as:</span></span>

* <span data-ttu-id="b6b5f-150">実行可能ファイルはダブルクリックすることができます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-150">You can double-click on the executable.</span></span>
* <span data-ttu-id="b6b5f-151">Windows では `myapp.exe`、Linux と macOS では`./myapp` など、コマンド プロンプトからアプリケーションを直接起動できます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-151">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

## <a name="single-file-executables"></a><span data-ttu-id="b6b5f-152">単一ファイルの実行可能ファイル</span><span class="sxs-lookup"><span data-stu-id="b6b5f-152">Single-file executables</span></span>

<span data-ttu-id="b6b5f-153">`dotnet publish` コマンドは、プラットフォーム固有の単一ファイルの実行可能ファイルにアプリをパッケージ化することをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-153">The `dotnet publish` command supports packaging your app into a platform-specific single-file executable.</span></span> <span data-ttu-id="b6b5f-154">実行可能ファイルは自己展開型であり、アプリの実行に必要なすべての依存関係 (ネイティブを含む) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-154">The executable is self-extracting and contains all dependencies (including native) that are required to run your app.</span></span> <span data-ttu-id="b6b5f-155">アプリを初めて実行すると、アプリ名とビルド ID に基づいてアプリケーションがディレクトリに抽出されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-155">When the app is first run, the application is extracted to a directory based on the app name and build identifier.</span></span> <span data-ttu-id="b6b5f-156">アプリケーションを再実行すると、起動は速くなります。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-156">Startup is faster when the application is run again.</span></span> <span data-ttu-id="b6b5f-157">新しいバージョンが使用されない限り、アプリケーションは自身を 2 回抽出する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-157">The application doesn't need to extract itself a second time unless a new version was used.</span></span>

<span data-ttu-id="b6b5f-158">単一ファイルの実行可能ファイルを発行するには、プロジェクト内またはコマンド ラインで `dotnet publish` コマンドを使用して `PublishSingleFile` を設定します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-158">To publish a single-file executable, set the `PublishSingleFile` in your project or on the command line with the `dotnet publish` command:</span></span>

```console
dotnet publish -r win10-x64 /p:PublishSingleFile=true
```

<span data-ttu-id="b6b5f-159">単一ファイルの発行の詳細については、[単一ファイル バンドラー設計のドキュメント](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-159">For more information about single-file publishing, see the [single-file bundler design document](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="b6b5f-160">階層型コンパイル</span><span class="sxs-lookup"><span data-stu-id="b6b5f-160">Tiered compilation</span></span>

<span data-ttu-id="b6b5f-161">.NET Core 3.0 では、[階層型コンパイル](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) (TC) が既定で有効になりました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-161">[Tiered compilation](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) (TC) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="b6b5f-162">この機能により、ランタイムが状況に応じて Just-In-Time (JIT) コンパイラを使用してパフォーマンスを向上できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-162">This feature enables the runtime to more adaptively use the Just-In-Time (JIT) compiler to get better performance.</span></span>

<span data-ttu-id="b6b5f-163">TC の主な利点は、(再) JIT メソッドとして、低速でもコード生成は高速なもの、または高品質でもコード生成は低速なもの有効にできることです。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-163">The main benefit of TC is to enable (re-)jitting methods with slower-but-faster to produce code or higher-quality-but-slower to produce code.</span></span> <span data-ttu-id="b6b5f-164">これは、起動から安定した状態まで、さまざまな実行段階を経るときに、アプリケーションのパフォーマンスを向上するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-164">This helps increase performance of an application as it goes through various stages of execution, from startup through steady-state.</span></span> <span data-ttu-id="b6b5f-165">これは、すべてのメソッドが 1 つの方法 (高品質階層と同じ) でコンパイルされ、起動時のパフォーマンスよりも安定した状態に偏っている非 TC アプローチとは対照的です。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-165">This contrasts with the non-TC approach, where every method is compiled a single way (the same as the high-quality tier), which is biased to steady-state over startup performance.</span></span>

<span data-ttu-id="b6b5f-166">Quick JIT (階層 0 の JIT 済みコード) を有効にするには、プロジェクト ファイルで次の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-166">To enable Quick JIT (tier 0 jitted code), use this setting in your project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>true</TieredCompilationQuickJit>
</PropertyGroup>
```

<span data-ttu-id="b6b5f-167">TC を完全に無効にするには、プロジェクト ファイルでこの設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-167">To disable TC completely, use this setting in your project file:</span></span>

```xml
<TieredCompilation>false</TieredCompilation>
```

## <a name="build-copies-dependencies"></a><span data-ttu-id="b6b5f-168">ビルドによる依存関係のコピー</span><span class="sxs-lookup"><span data-stu-id="b6b5f-168">Build copies dependencies</span></span>

<span data-ttu-id="b6b5f-169">`dotnet build` コマンドでは、アプリケーションの NuGet 依存関係が NuGet キャッシュからビルド出力フォルダーにコピーされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-169">The `dotnet build` command now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="b6b5f-170">以前は、依存関係のコピーは `dotnet publish` の一部としてのみ行われていました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-170">Previously, dependencies were only copied as part of `dotnet publish`.</span></span>

<span data-ttu-id="b6b5f-171">リンクや razor ページの発行など、まだ発行が必要な操作がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-171">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>

## <a name="local-tools"></a><span data-ttu-id="b6b5f-172">ローカル ツール</span><span class="sxs-lookup"><span data-stu-id="b6b5f-172">Local tools</span></span>

<span data-ttu-id="b6b5f-173">.NET Core 3.0 にローカル ツールが導入されました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-173">.NET Core 3.0 introduces local tools.</span></span> <span data-ttu-id="b6b5f-174">ローカル ツールは[グローバル ツール](../tools/global-tools.md)に似ていますが、ディスク上の特定の場所に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-174">Local tools are similar to [global tools](../tools/global-tools.md) but are associated with a particular location on disk.</span></span> <span data-ttu-id="b6b5f-175">ローカル ツールはグローバルには使用できず、NuGet パッケージとして配布されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-175">Local tools aren't available globally and are distributed as NuGet packages.</span></span>

> [!WARNING]
> <span data-ttu-id="b6b5f-176">.NET Core 3.0 Preview 1 で `dotnet tool restore` や `dotnet tool install` の実行などのローカル ツールを試した場合は、ローカル ツールのキャッシュ フォルダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-176">If you tried local tools in .NET Core 3.0 Preview 1, such as running `dotnet tool restore` or `dotnet tool install`, delete the local tools cache folder.</span></span> <span data-ttu-id="b6b5f-177">そうしないと、ローカル ツールは新しいリリースで動作しません。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-177">Otherwise, local tools won't work on any newer release.</span></span> <span data-ttu-id="b6b5f-178">このフォルダーは次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-178">This folder is located at:</span></span>
>
> <span data-ttu-id="b6b5f-179">macOS、Linux の場合: `rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="b6b5f-179">On macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
> <span data-ttu-id="b6b5f-180">Windows の場合: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="b6b5f-180">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>

<span data-ttu-id="b6b5f-181">ローカル ツールは、現在のディレクトリ内のマニフェスト ファイル名 `dotnet-tools.json` に依存しています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-181">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="b6b5f-182">このマニフェスト ファイルは、ツールをそのフォルダー下で使用できるように定義します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-182">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="b6b5f-183">コードを使用するすべての人が確実に同じツールを復元して使用できるように、自分のコードと一緒にマニフェスト ファイルを配布することができます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-183">You can distribute the manifest file with your code to ensure that anyone who works with your code can restore and use the same tools.</span></span>

<span data-ttu-id="b6b5f-184">グローバル ツールとローカル ツールの両方で、ランタイムの互換バージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-184">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="b6b5f-185">現在 NuGet.org 上にある多くのツールは、.NET Core Runtime 2.1 をターゲットとしています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-185">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="b6b5f-186">グローバルにまたはローカルにこのようなツールをインストールするには、[NET Core 2.1 ランタイム](https://dotnet.microsoft.com/download/dotnet-core/2.1)をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-186">To install these tools globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

## <a name="major-version-roll-forward"></a><span data-ttu-id="b6b5f-187">メジャーバージョンのロールフォワード</span><span class="sxs-lookup"><span data-stu-id="b6b5f-187">Major-version Roll Forward</span></span>

<span data-ttu-id="b6b5f-188">.NET Core 3.0 では、アプリを最新メジャー バージョンの .NET Core にロールフォワードできるようにするオプトイン機能が導入されました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-188">.NET Core 3.0 introduces an opt-in feature that allows your app to roll forward to the latest major version of .NET Core.</span></span> <span data-ttu-id="b6b5f-189">さらに、ロールフォワードをアプリに適用する方法を制御する新しい設定が追加されました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-189">Additionally, a new setting has been added to control how roll forward is applied to your app.</span></span> <span data-ttu-id="b6b5f-190">これは、以下の方法で構成できます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-190">This can be configured in the following ways:</span></span>

- <span data-ttu-id="b6b5f-191">プロジェクト ファイルのプロパティ: `RollForward`</span><span class="sxs-lookup"><span data-stu-id="b6b5f-191">Project file property: `RollForward`</span></span>
- <span data-ttu-id="b6b5f-192">ランタイム構成ファイルのプロパティ: `rollForward`</span><span class="sxs-lookup"><span data-stu-id="b6b5f-192">Runtime configuration file property: `rollForward`</span></span>
- <span data-ttu-id="b6b5f-193">環境変数: `DOTNET_ROLL_FORWARD`</span><span class="sxs-lookup"><span data-stu-id="b6b5f-193">Environment variable: `DOTNET_ROLL_FORWARD`</span></span>
- <span data-ttu-id="b6b5f-194">コマンドライン引数: `--roll-forward`</span><span class="sxs-lookup"><span data-stu-id="b6b5f-194">Command-line argument: `--roll-forward`</span></span>

<span data-ttu-id="b6b5f-195">次の値のいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-195">One of the following values must be specified.</span></span> <span data-ttu-id="b6b5f-196">設定を省略すると、**Minor** が既定値になります。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-196">If the setting is omitted, **Minor** is the default.</span></span>

- <span data-ttu-id="b6b5f-197">**LatestPatch**\\</span><span class="sxs-lookup"><span data-stu-id="b6b5f-197">**LatestPatch**\\</span></span>
<span data-ttu-id="b6b5f-198">最新のパッチ バージョンにロールフォワードします。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-198">Roll forward to the highest patch version.</span></span> <span data-ttu-id="b6b5f-199">これで、マイナー バージョンのロールフォワードが無効になります。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-199">This disables minor version roll forward.</span></span>
- <span data-ttu-id="b6b5f-200">**Minor**\\</span><span class="sxs-lookup"><span data-stu-id="b6b5f-200">**Minor**\\</span></span>
<span data-ttu-id="b6b5f-201">要求されたマイナー バージョンが見つからない場合は、それよりも高い最小マイナー バージョンにロールフォワードします。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-201">Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="b6b5f-202">要求されたマイナー バージョンが存在する場合は、**LatestPatch** ポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-202">If the requested minor version is present, then the **LatestPatch** policy is used.</span></span>
- <span data-ttu-id="b6b5f-203">**Major**\\</span><span class="sxs-lookup"><span data-stu-id="b6b5f-203">**Major**\\</span></span>
<span data-ttu-id="b6b5f-204">要求されたメジャー バージョンが見つからない場合は、それよりも高い最小メジャー バージョンで最小マイナー バージョンにロールフォワードします。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-204">Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="b6b5f-205">要求されたメジャー バージョンが存在する場合は、**Minor** ポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-205">If the requested major version is present, then the **Minor** policy is used.</span></span>
- <span data-ttu-id="b6b5f-206">**LatestMinor**\\</span><span class="sxs-lookup"><span data-stu-id="b6b5f-206">**LatestMinor**\\</span></span>
<span data-ttu-id="b6b5f-207">要求されたマイナー バージョンが存在する場合でも、最上位のマイナー バージョンにロールフォワードします。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-207">Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="b6b5f-208">コンポーネント ホスティング シナリオを対象としています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-208">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="b6b5f-209">**LatestMajor**\\</span><span class="sxs-lookup"><span data-stu-id="b6b5f-209">**LatestMajor**\\</span></span>
<span data-ttu-id="b6b5f-210">要求されたメジャーが存在する場合でも、最上位のメジャー バージョンで最上位のマイナー バージョンにロールフォワードします。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-210">Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="b6b5f-211">コンポーネント ホスティング シナリオを対象としています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-211">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="b6b5f-212">**Disable**\\</span><span class="sxs-lookup"><span data-stu-id="b6b5f-212">**Disable**\\</span></span>
<span data-ttu-id="b6b5f-213">ロールフォワードしません。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-213">Don't roll forward.</span></span> <span data-ttu-id="b6b5f-214">指定されたバージョンにのみバインドします。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-214">Only bind to specified version.</span></span> <span data-ttu-id="b6b5f-215">このポリシーは、最新のパッチにロールフォワードする機能が無効になるため、一般的な使用にはお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-215">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="b6b5f-216">この値はテスト用にのみ推奨されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-216">This value is only recommended for testing.</span></span>

<span data-ttu-id="b6b5f-217">**Disable** の設定を除くすべての設定では、利用できる最新のパッチ バージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-217">Besides the **Disable** setting, all settings will use the highest available patch version.</span></span>

## <a name="windows-desktop"></a><span data-ttu-id="b6b5f-218">Windows デスクトップ</span><span class="sxs-lookup"><span data-stu-id="b6b5f-218">Windows desktop</span></span>

<span data-ttu-id="b6b5f-219">.NET Core 3.0 は、Windows Presentation Foundation (WPF) および Windows フォームを使用した Windows デスクトップ アプリケーションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-219">.NET Core 3.0 supports Windows desktop applications using Windows Presentation Foundation (WPF) and Windows Forms.</span></span> <span data-ttu-id="b6b5f-220">これらのフレームワークでは、Windows UI XAML ライブラリ (WinUI) の最新のコントロールと Fluent スタイルを [XAML Islands](/windows/uwp/xaml-platform/xaml-host-controls) 経由で使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-220">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="b6b5f-221">Windows デスクトップ コンポーネントは、Windows .NET Core 3.0 SDK の一部です。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-221">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="b6b5f-222">次の `dotnet` コマンドを使用して、新しい WPF または Windows フォーム アプリケーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-222">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```console
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="b6b5f-223">Visual Studio 2019 では、.NET Core 3.0 Windows フォームと WPF 用に、**新しいプロジェクト** テンプレートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-223">Visual Studio 2019 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span>

<span data-ttu-id="b6b5f-224">既存の .NET Framework アプリケーションを移植する方法の詳細については、[WPF プロジェクトの移植](../porting/wpf.md)と [Windows フォーム プロジェクトの移植](../porting/winforms.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-224">For more information about how to port an existing .NET Framework application, see [Port WPF projects](../porting/wpf.md) and [Port Windows Forms projects](../porting/winforms.md).</span></span>

## <a name="com-callable-components---windows-desktop"></a><span data-ttu-id="b6b5f-225">COM 呼び出し可能コンポーネント - Windows デスクトップ</span><span class="sxs-lookup"><span data-stu-id="b6b5f-225">COM-callable components - Windows Desktop</span></span>

<span data-ttu-id="b6b5f-226">Windows 上で、COM 呼び出し可能なマネージ コンポーネントを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-226">On Windows, you can now create COM-callable managed components.</span></span> <span data-ttu-id="b6b5f-227">この機能は、COM アドイン モデルに .NET Core を使用する場合と、.NET Framework にパリティを提供する場合にも重要です。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-227">This capability is critical to use .NET Core with COM add-in models and also to provide parity with .NET Framework.</span></span>

<span data-ttu-id="b6b5f-228">COM サーバーとして *mscoree.dll* が使用されていた .NET Framework とは異なり、COM コンポーネントを構築すると、.NET Core によって *bin* ディレクトリにネイティブ ランチャー DLL が追加されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-228">Unlike .NET Framework where the *mscoree.dll* was used as the COM server, .NET Core will add a native launcher dll to the *bin* directory when you build your COM component.</span></span>

<span data-ttu-id="b6b5f-229">COM コンポーネントを作成して使用する方法の例については、[COM のデモ](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-229">For an example of how to create a COM component and consume it, see the [COM Demo](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span></span>

## <a name="msix-deployment---windows-desktop"></a><span data-ttu-id="b6b5f-230">MSIX の展開 - Windows デスクトップ</span><span class="sxs-lookup"><span data-stu-id="b6b5f-230">MSIX Deployment - Windows Desktop</span></span>

<span data-ttu-id="b6b5f-231">[MSIX](https://docs.microsoft.com/windows/msix/) は新しい Windows アプリケーション パッケージ形式です。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-231">[MSIX](https://docs.microsoft.com/windows/msix/) is a new Windows application package format.</span></span> <span data-ttu-id="b6b5f-232">これは、Windows 10 に .NET Core 3.0 のデスクトップ アプリケーションを展開するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-232">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="b6b5f-233">[Windows アプリケーション パッケージ プロジェクト](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net)は、Visual Studio 2019 で使用でき、[自己完結型](../deploying/index.md#self-contained-deployments-scd)の .NET Core アプリケーションを使用して、MSIX パッケージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-233">The [Windows Application Packaging Project](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019, allows you to create MSIX packages with [self-contained](../deploying/index.md#self-contained-deployments-scd) .NET Core applications.</span></span>

<span data-ttu-id="b6b5f-234">.NET Core プロジェクト ファイルの `<RuntimeIdentifiers>` プロパティで、サポートされているランタイムを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-234">The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>

```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="winforms-highdpi"></a><span data-ttu-id="b6b5f-235">WinForms HighDPI</span><span class="sxs-lookup"><span data-stu-id="b6b5f-235">WinForms HighDPI</span></span>

<span data-ttu-id="b6b5f-236">.NET Core Windows フォーム アプリケーションでは、<xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType> を使用して高 DPI モードを設定できます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-236">.NET Core Windows Forms applications can set High DPI mode with <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b6b5f-237">`Application.Run` の前の `App.Manifest` や P/Invoke などの他の方法で設定を指定しない限り、`SetHighDpiMode` メソッドによって、対応する高 DPI モードが設定されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-237">The `SetHighDpiMode` method sets the corresponding High DPI mode unless the setting has been set by other means like `App.Manifest` or P/Invoke before `Application.Run`.</span></span>

<span data-ttu-id="b6b5f-238"><xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> 列挙型で表される `highDpiMode` に使用できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-238">The possible `highDpiMode` values, as expressed by the <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> enum are:</span></span>

* `DpiUnaware`
* `SystemAware`
* `PerMonitor`
* `PerMonitorV2`
* `DpiUnawareGdiScaled`

<span data-ttu-id="b6b5f-239">高 DPI モードの詳細については、「[High DPI Desktop Application Development on Windows (Windows での高 DPI デスクトップ アプリケーション開発)](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-239">For more information about High DPI modes, see [High DPI Desktop Application Development on Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span></span>

### <a name="ranges-and-indices"></a><span data-ttu-id="b6b5f-240">範囲とインデックス</span><span class="sxs-lookup"><span data-stu-id="b6b5f-240">Ranges and indices</span></span>

<span data-ttu-id="b6b5f-241">新しい <xref:System.Index?displayProperty=nameWithType> 型はインデックス作成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-241">The new <xref:System.Index?displayProperty=nameWithType> type can be used for indexing.</span></span> <span data-ttu-id="b6b5f-242">先頭からカウントする `int` か、末尾からカウントするプレフィックス `^` 演算子 (C#) を使用して作成することができます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-242">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="b6b5f-243">また、<xref:System.Range?displayProperty=nameWithType> 型もあります。これは開始値と終了値の 2 つの `Index` 値から構成され、`x..y` の範囲式 (C#) で記述できます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-243">There's also the <xref:System.Range?displayProperty=nameWithType> type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="b6b5f-244">これで、`Range` を使用してインデックスを付け、スライスを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-244">You can then index with a `Range`, which produces a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

<span data-ttu-id="b6b5f-245">詳細については、[範囲とインデックスのチュートリアル](../../csharp/tutorials/ranges-indexes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-245">For more information, see the [ranges and indices tutorial](../../csharp/tutorials/ranges-indexes.md).</span></span>

### <a name="async-streams"></a><span data-ttu-id="b6b5f-246">非同期ストリーム</span><span class="sxs-lookup"><span data-stu-id="b6b5f-246">Async streams</span></span>

<span data-ttu-id="b6b5f-247"><xref:System.Collections.Generic.IAsyncEnumerable%601> 型は、<xref:System.Collections.Generic.IEnumerable%601> の新しい非同期バージョンです。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-247">The <xref:System.Collections.Generic.IAsyncEnumerable%601> type is a new asynchronous version of <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="b6b5f-248">この言語では、その要素を使用するために `IAsyncEnumerable<T>` よりも `await foreach` を行い、要素を生成するために `yield return` を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-248">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="b6b5f-249">非同期ストリームの生成の両方の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-249">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="b6b5f-250">`foreach` ステートメントは非同期であり、`yield return` を使用して呼び出し元の非同期ストリームを生成します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-250">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="b6b5f-251">(`yield return` を使用する) このパターンは、非同期ストリームを生成するモデルに推奨されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-251">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result; 
    }
}
```

<span data-ttu-id="b6b5f-252">`await foreach` を実行できるだけでなく、非同期反復子を作成することもできます。たとえば、`await` と`yield` の両方を行うことができる `IAsyncEnumerable/IAsyncEnumerator` を返す反復子です。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-252">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="b6b5f-253">破棄する必要があるオブジェクトの場合は、`Stream` や `Timer` など、さまざまな BCL 型が実装する `IAsyncDisposable` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-253">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

<span data-ttu-id="b6b5f-254">詳細については、[非同期ストリームのチュートリアル](../../csharp/tutorials/generate-consume-asynchronous-stream.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-254">For more information, see the [async streams tutorial](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span></span>

## <a name="ieee-floating-point-improvements"></a><span data-ttu-id="b6b5f-255">IEEE 浮動小数点の改良</span><span class="sxs-lookup"><span data-stu-id="b6b5f-255">IEEE Floating-point improvements</span></span>

<span data-ttu-id="b6b5f-256">浮動小数点 API は、[IEEE 754-2008 リビジョン](https://en.wikipedia.org/wiki/IEEE_754-2008_revision)に準拠するように更新されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-256">Floating point APIs are being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="b6b5f-257">これらの変更の目的は、すべての**必要な**操作を公開し、それらの動作が IEEE 仕様に準拠していることを保証することです。浮動小数点の改良の詳細については、「[Floating-Point Parsing and Formatting improvements in .NET Core 3.0 (.NET Core 3.0 の浮動小数点の解析と形式の改良)](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/)」のブログ記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-257">The goal of these changes is to expose all **required** operations and ensure that they're behaviorally compliant with the IEEE spec. For more information about floating-point improvements, see the [Floating-Point Parsing and Formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.</span></span>

<span data-ttu-id="b6b5f-258">次のような解析および書式設定の修正があります。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-258">Parsing and formatting fixes include:</span></span>

* <span data-ttu-id="b6b5f-259">任意の長さの入力を正しく解析して丸める。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-259">Correctly parse and round inputs of any length.</span></span>
* <span data-ttu-id="b6b5f-260">負のゼロを正しく解析して書式設定する。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-260">Correctly parse and format negative zero.</span></span>
* <span data-ttu-id="b6b5f-261">大文字と小文字を区別しないチェックを実行し、可能な場合には省略可能な先行の `+` を許可することで、`Infinity` と `NaN` を正しく解析する。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-261">Correctly parse `Infinity` and `NaN` by doing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="b6b5f-262">新しい <xref:System.Math?displayProperty=nameWithType> API には以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-262">New <xref:System.Math?displayProperty=nameWithType> APIs include:</span></span>

* <span data-ttu-id="b6b5f-263"><xref:System.Math.BitIncrement(System.Double)> と <xref:System.Math.BitDecrement(System.Double)>\\</span><span class="sxs-lookup"><span data-stu-id="b6b5f-263"><xref:System.Math.BitIncrement(System.Double)> and <xref:System.Math.BitDecrement(System.Double)>\\</span></span>
<span data-ttu-id="b6b5f-264">`nextUp` および `nextDown` の IEEE 演算に相当します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-264">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="b6b5f-265">入力よりも大きいか小さいかを比較する最小の浮動小数点をそれぞれ返します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-265">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="b6b5f-266">たとえば、`Math.BitIncrement(0.0)` は `double.Epsilon` を返します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-266">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

* <span data-ttu-id="b6b5f-267"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> と <xref:System.Math.MinMagnitude(System.Double,System.Double)>\\</span><span class="sxs-lookup"><span data-stu-id="b6b5f-267"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> and <xref:System.Math.MinMagnitude(System.Double,System.Double)>\\</span></span>
<span data-ttu-id="b6b5f-268">`maxNumMag` および `minNumMag` の IEEE 演算に相当します。2 つの入力の大きさがより大きいまたはより小さい値をそれぞれ返します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-268">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="b6b5f-269">たとえば、`Math.MaxMagnitude(2.0, -3.0)` は `-3.0` を返します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-269">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

* <xref:System.Math.ILogB(System.Double)>\
<span data-ttu-id="b6b5f-270">整数値を返す `logB` IEEE 演算に相当します。入力パラメーターの 2 を底とする積分対数を返します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-270">Corresponds to the `logB` IEEE operation that returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="b6b5f-271">このメソッドは実質的に `floor(log2(x))` と同じですが、最小限の丸め誤差で実行されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-271">This method is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

* <xref:System.Math.ScaleB(System.Double,System.Int32)>\
<span data-ttu-id="b6b5f-272">整数値を受け取る `scaleB` IEEE 演算に相当します。これは実質的に `x * pow(2, n)` と同じですが、最小限の丸め誤差で実行されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-272">Corresponds to the `scaleB` IEEE operation that takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

* <xref:System.Math.Log2(System.Double)>\
<span data-ttu-id="b6b5f-273">`log2` IEEE 演算に相当します。2 を底とする対数を返します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-273">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="b6b5f-274">丸め誤差を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-274">It minimizes rounding error.</span></span>

* <xref:System.Math.FusedMultiplyAdd(System.Double,System.Double,System.Double)>\
<span data-ttu-id="b6b5f-275">`fma` IEEE 演算に相当します。融合型積和演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-275">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="b6b5f-276">つまり、単一操作として `(x * y) + z` を実行することで、丸め誤差を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-276">That is, it does `(x * y) + z` as a single operation, there-by minimizing the rounding error.</span></span> <span data-ttu-id="b6b5f-277">例では、`FusedMultiplyAdd(1e308, 2.0, -1e308)` は `1e308` を返します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-277">An example would be `FusedMultiplyAdd(1e308, 2.0, -1e308)` which returns `1e308`.</span></span> <span data-ttu-id="b6b5f-278">正規の `(1e308 * 2.0) - 1e308` は `double.PositiveInfinity` を返します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-278">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

* <xref:System.Math.CopySign(System.Double,System.Double)>\
<span data-ttu-id="b6b5f-279">`copySign` IEEE 演算に相当します。`x` の値を返しますが、`y` の符号と共に返されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-279">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

## <a name="fast-built-in-json-support"></a><span data-ttu-id="b6b5f-280">高速な組み込み JSON のサポート</span><span class="sxs-lookup"><span data-stu-id="b6b5f-280">Fast built-in JSON support</span></span>

<span data-ttu-id="b6b5f-281">.NET ユーザーは、[**Json.NET**](https://www.newtonsoft.com/json) や他のよく使われている JSON ライブラリに大きく依存しています。これは今後も推奨されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-281">.NET users have largely relied on [**Json.NET**](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="b6b5f-282">**Json.NET** では .NET の文字列が基本のデータ型 (内部的には UTF-16) として使用されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-282">**Json.NET** uses .NET strings as its base datatype, which is UTF-16 under the hood.</span></span>

<span data-ttu-id="b6b5f-283">新しい組み込みの JSON サポートは、高パフォーマンス、低割り当てで、`Span<byte>` に基づいています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-283">The new built-in JSON support is high-performance, low allocation, and based on `Span<byte>`.</span></span> <span data-ttu-id="b6b5f-284">3 つの新しい JSON 関連の主な型が、.NET Core 3.0 の <xref:System.Text.Json?displayProperty=nameWithType> 名前空間に追加されました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-284">Three new main JSON-related types have been added to .NET Core 3.0 the <xref:System.Text.Json?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="b6b5f-285">これらの型は、単純な従来の CLR オブジェクト (POCO) のシリアル化と逆シリアル化を "*まだ*" サポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-285">These types don't *yet* support plain old CLR object (POCO) serialization and deserialization.</span></span>

### <a name="utf8jsonreader"></a><span data-ttu-id="b6b5f-286">Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="b6b5f-286">Utf8JsonReader</span></span>

<span data-ttu-id="b6b5f-287"><xref:System.Text.Json.Utf8JsonReader?displayProperty=nameWithType> は、UTF-8 でエンコードされた JSON テキスト用の高パフォーマンス、低割り当て、転送のみのリーダーです。`ReadOnlySpan<byte>` から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-287"><xref:System.Text.Json.Utf8JsonReader?displayProperty=nameWithType> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="b6b5f-288">`Utf8JsonReader` は基本的で低レベルの型であり、カスタム パーサーとデシリアライザーを構築するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-288">The `Utf8JsonReader` is a foundational, low-level type, that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="b6b5f-289">新しい `Utf8JsonReader` を使用して JSON ペイロードを読み取る処理は、**Json.NET** のリーダーを使用する場合より 2 倍高速です。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-289">Reading through a JSON payload using the new `Utf8JsonReader` is 2x faster than using the reader from **Json.NET**.</span></span> <span data-ttu-id="b6b5f-290">JSON トークンを (UTF-16) 文字列として実現する必要が出てくるまでは割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-290">It doesn't allocate until you need to actualize JSON tokens as (UTF-16) strings.</span></span>

<span data-ttu-id="b6b5f-291">Visual Studio Code で作成された [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) ファイルを読み取る例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-291">Here is an example of reading through the [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) file created by Visual Studio Code:</span></span>

[!CODE-csharp[Utf8JsonReader](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#PrintJson)]

[!CODE-csharp[Utf8JsonReader](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#PrintJsonCall)]

### <a name="utf8jsonwriter"></a><span data-ttu-id="b6b5f-292">Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="b6b5f-292">Utf8JsonWriter</span></span>

<span data-ttu-id="b6b5f-293"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> は、`String`、`Int32`、`DateTime` のような一般的な.NET 型から UTF-8 でエンコードされた JSON テキストを書き込むための、ハイパフォーマンス、非キャッシュ、前方参照専用の方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-293"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> provides a high-performance, non-cached, forward-only way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="b6b5f-294">リーダーと同様に、ライターは基本的で低レベルの型であり、カスタム シリアライザーを構築するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-294">Like the reader, the writer is a foundational, low-level type, that can be used to build custom serializers.</span></span> <span data-ttu-id="b6b5f-295">新しい `Utf8JsonWriter` を使用して JSON ペイロードを書き込むと、**Json.NET** からライターを使用するよりも 30 - 80% 高速になり、割り当てが行われません。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-295">Writing a JSON payload using the new `Utf8JsonWriter` is 30-80% faster than using the writer from **Json.NET** and doesn't allocate.</span></span>

### <a name="jsondocument"></a><span data-ttu-id="b6b5f-296">JsonDocument</span><span class="sxs-lookup"><span data-stu-id="b6b5f-296">JsonDocument</span></span>

<span data-ttu-id="b6b5f-297"><xref:System.Text.Json.JsonDocument?displayProperty=nameWithType> は、`Utf8JsonReader` に基づいています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-297"><xref:System.Text.Json.JsonDocument?displayProperty=nameWithType> is built on top of the `Utf8JsonReader`.</span></span> <span data-ttu-id="b6b5f-298">`JsonDocument` は、JSON データを解析し、ランダム アクセスと列挙型をサポートするためにクエリできる読み取り専用ドキュメント オブジェクト モデル (DOM) をビルドする機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-298">The `JsonDocument` provides the ability to parse JSON data and build a read-only Document Object Model (DOM) that can be queried to support random access and enumeration.</span></span> <span data-ttu-id="b6b5f-299">データを作成する JSON 要素には、`RootElement` というプロパティとして `JsonDocument` によって公開される <xref:System.Text.Json.JsonElement> 型を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-299">The JSON elements that compose the data can be accessed via the <xref:System.Text.Json.JsonElement> type that is exposed by the `JsonDocument` as a property called `RootElement`.</span></span> <span data-ttu-id="b6b5f-300">`JsonElement` には、JSON 配列とオブジェクト列挙子とともに、JSON テキストを一般的な .NET 型に変換する API が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-300">The `JsonElement` contains the JSON array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="b6b5f-301">一般的な JSON ペイロードを解析し、`JsonDocument` を使用してそのメンバーすべてにアクセスすると、適度にサイズ指定された (つまり 1 MB 未満) データに対する割り当てがほとんどない **Json.NET** よりも 2 - 3 倍高速になります。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-301">Parsing a typical JSON payload and accessing all its members using the `JsonDocument` is 2-3x faster than **Json.NET** with little allocations for data that is reasonably sized (that is, < 1 MB).</span></span>

<span data-ttu-id="b6b5f-302">出発点として使用できる `JsonDocument` および `JsonElement` の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-302">Here is a sample usage of the `JsonDocument` and `JsonElement` that can be used as a starting point:</span></span>

<span data-ttu-id="b6b5f-303">Visual Studio Code で作成された [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) ファイルを読み取る C# 8.0 の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-303">Here is a C# 8.0 example of reading through the [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) file created by Visual Studio Code:</span></span>

[!CODE-csharp[JsonDocument](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#ReadJson)]

[!CODE-csharp[JsonDocument](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#ReadJsonCall)]

### <a name="jsonserializer"></a><span data-ttu-id="b6b5f-304">JsonSerializer</span><span class="sxs-lookup"><span data-stu-id="b6b5f-304">JsonSerializer</span></span>

<span data-ttu-id="b6b5f-305"><xref:System.Text.Json.Serialization.JsonSerializer?displayProperty=nameWithType> は <xref:System.Text.Json.Utf8JsonReader> と <xref:System.Text.Json.Utf8JsonWriter> に基づいて構築されており、JSON ドキュメントとフラグメントを使用するときに高速で低メモリのシリアル化オプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-305"><xref:System.Text.Json.Serialization.JsonSerializer?displayProperty=nameWithType> is built on top of <xref:System.Text.Json.Utf8JsonReader> and <xref:System.Text.Json.Utf8JsonWriter> to provide a fast low-memory serialization option when working with JSON documents and fragments.</span></span>

<span data-ttu-id="b6b5f-306">確認: この記事への移植例については https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/docs/SerializerProgrammingModel.md</span><span class="sxs-lookup"><span data-stu-id="b6b5f-306">EXAMINE: https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/docs/SerializerProgrammingModel.md for an example to port to this article</span></span>

<span data-ttu-id="b6b5f-307">オブジェクトを JSON にシリアル化する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-307">Here is an example of serializing an object to JSON:</span></span>

[!CODE-csharp[JsonSerializer](~/samples/snippets/core/whats-new/whats-new-in-30/cs/JSON.cs#JsonSerialize)]

<span data-ttu-id="b6b5f-308">JSON 文字列をオブジェクトに逆シリアル化する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-308">Here is an example of deserializing a JSON string to an object.</span></span> <span data-ttu-id="b6b5f-309">前の例で生成された JSON 文字列を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-309">You can use the JSON string produced by the previous example:</span></span>

[!CODE-csharp[JsonDeserializer](~/samples/snippets/core/whats-new/whats-new-in-30/cs/JSON.cs#JsonDeserialize)]

## <a name="interop-improvements"></a><span data-ttu-id="b6b5f-310">相互運用性の機能強化</span><span class="sxs-lookup"><span data-stu-id="b6b5f-310">Interop improvements</span></span>

<span data-ttu-id="b6b5f-311">.NET Core 3.0 では、ネイティブ API の相互運用性が強化されました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-311">.NET Core 3.0 improves native API interop.</span></span>

### <a name="type-nativelibrary"></a><span data-ttu-id="b6b5f-312">型:NativeLibrary</span><span class="sxs-lookup"><span data-stu-id="b6b5f-312">Type: NativeLibrary</span></span>

<span data-ttu-id="b6b5f-313"><xref:System.Runtime.InteropServices.NativeLibrary?displayProperty=nameWithType> には、(.NET Core P/Invoke と同じ読み込みロジックを使用して) ネイティブ ライブラリを読み込み、`getSymbol` などの関連するヘルパー関数を指定するためのカプセル化機能があります。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-313"><xref:System.Runtime.InteropServices.NativeLibrary?displayProperty=nameWithType> provides an encapsulation for loading a native library (using the same load logic as .NET Core P/Invoke) and providing the relevant helper functions such as `getSymbol`.</span></span> <span data-ttu-id="b6b5f-314">コード例については、[DLLMap のデモ](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-314">For a code example, see the [DLLMap Demo](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin).</span></span>

### <a name="windows-native-interop"></a><span data-ttu-id="b6b5f-315">Windows のネイティブ相互運用機能</span><span class="sxs-lookup"><span data-stu-id="b6b5f-315">Windows Native Interop</span></span>

<span data-ttu-id="b6b5f-316">Windows では、フラット C API、COM、および WinRT の形式で、質の高いネイティブ API を提供しています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-316">Windows offers a rich native API in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="b6b5f-317">.NET Core は **P/Invoke** をサポートしますが、.NET Core 3.0 では **COM API の CoCreate** と **WinRT API のアクティブ化**を行う機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-317">While .NET Core supports **P/Invoke**, .NET Core 3.0 adds the ability to **CoCreate COM APIs** and **Activate WinRT APIs**.</span></span> <span data-ttu-id="b6b5f-318">コード例については、[Excel のデモ](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-318">For a code example, see the [Excel Demo](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>

## <a name="http2-support"></a><span data-ttu-id="b6b5f-319">HTTP/2 のサポート</span><span class="sxs-lookup"><span data-stu-id="b6b5f-319">HTTP/2 support</span></span>

<span data-ttu-id="b6b5f-320"><xref:System.Net.Http.HttpClient?displayProperty=nameWithType> 型は HTTP/2 プロトコルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-320">The <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> type supports the HTTP/2 protocol.</span></span> <span data-ttu-id="b6b5f-321">サポートは現在無効ですが、<xref:System.Net.Http.HttpClient> を使用する前に `AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2Support", true);` を呼び出すことで有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-321">Support is currently disabled but can be turned on by calling `AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2Support", true);` before you use <xref:System.Net.Http.HttpClient>.</span></span> <span data-ttu-id="b6b5f-322">アプリを実行する前に `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` 環境変数を `true` に設定することで HTTP/2 のサポートを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-322">You can also enable HTTP/2 support by setting the `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` environment variable to `true` before you run your app.</span></span>

<span data-ttu-id="b6b5f-323">HTTP/2 が有効な場合、HTTP プロトコルのバージョンは TLS/ALPN を介してネゴシエートされ、HTTP/2 はサーバーがそれを使用することを選択した場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-323">If HTTP/2 is enabled, the HTTP protocol version will be negotiated via TLS/ALPN, and HTTP/2 will only be used if the server selects to use it.</span></span>

## <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="b6b5f-324">Linux 上の TLS 1.3 と OpenSSL 1.1.1</span><span class="sxs-lookup"><span data-stu-id="b6b5f-324">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="b6b5f-325">.NET Core では、特定の環境で使用できるようになったときに、[OpenSSL 1.1.1 の TLS 1.3 のサポート](https://www.openssl.org/blog/blog/2018/09/11/release111/)を利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-325">.NET Core now takes advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it's available in a given environment.</span></span> <span data-ttu-id="b6b5f-326">TLS 1.3 の場合:</span><span class="sxs-lookup"><span data-stu-id="b6b5f-326">With TLS 1.3:</span></span>

* <span data-ttu-id="b6b5f-327">クライアントとサーバー間に必要なラウンド トリップ回数が減るため、接続時間が改善されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-327">Connection times are improved with reduced round trips required between the client and server.</span></span>
* <span data-ttu-id="b6b5f-328">古い安全ではないさまざまな暗号化アルゴリズムが削除されたので、セキュリティが強化されました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-328">Improved security because of the removal of various obsolete and insecure cryptographic algorithms.</span></span>

<span data-ttu-id="b6b5f-329">使用できる場合、.NET Core 3.0 では Linux システム上で **OpenSSL 1.1.1**、**OpenSSL 1.1.0**、または **OpenSSL 1.0.2** が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-329">When available, .NET Core 3.0 uses **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** on a Linux system.</span></span> <span data-ttu-id="b6b5f-330">**OpenSSL 1.1.1** が使用できる場合、<xref:System.Net.Security.SslStream?displayProperty=nameWithType> 型と <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> 型の両方が **TLS 1.3** を使用します (クライアントとサーバーの両方が **TLS 1.3** をサポートしている場合)。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-330">When **OpenSSL 1.1.1** is available, both <xref:System.Net.Security.SslStream?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> types will use **TLS 1.3** (assuming both the client and server support **TLS 1.3**).</span></span>

>[!IMPORTANT]
><span data-ttu-id="b6b5f-331">Windows と macOS はまだ **TLS 1.3** をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-331">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="b6b5f-332">サポートされるようになったら、.NET Core 3.0 はこれらのオペレーティング システムで **TLS 1.3** をサポートする予定です。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-332">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

<span data-ttu-id="b6b5f-333">次の C# 8.0 の例は、<https://www.cloudflare.com> に接続している Ubuntu 18.10 上の .NET Core 3.0 を示しています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-333">The following C# 8.0 example demonstrates .NET Core 3.0 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

[!CODE-csharp[TLSExample](~/samples/snippets/core/whats-new/whats-new-in-30/cs/TLS.cs#TLS)]

## <a name="cryptography-ciphers"></a><span data-ttu-id="b6b5f-334">暗号化の暗号</span><span class="sxs-lookup"><span data-stu-id="b6b5f-334">Cryptography ciphers</span></span>

<span data-ttu-id="b6b5f-335">.NET 3.0 では、**AES-GCM** および **AES-CCM** の暗号のサポートが追加され、それぞれ <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> および <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> で実装されています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-335">.NET 3.0 adds support for **AES-GCM** and **AES-CCM** ciphers, implemented with <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> and <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> respectively.</span></span> <span data-ttu-id="b6b5f-336">これらのアルゴリズムは、いずれも [Authenticated Encryption with Association Data (AEAD) アルゴリズム](https://en.wikipedia.org/wiki/Authenticated_encryption)です。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-336">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption).</span></span>

<span data-ttu-id="b6b5f-337">次のコードは、`AesGcm` 暗号を使用してランダム データの暗号化と復号化を行う例です。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-337">The following code demonstrates using `AesGcm` cipher to encrypt and decrypt random data.</span></span>

[!CODE-csharp[AesGcm](~/samples/snippets/core/whats-new/whats-new-in-30/cs/Cipher.cs#AesGcm)]

## <a name="cryptographic-key-importexport"></a><span data-ttu-id="b6b5f-338">暗号化キーのインポート/エクスポート</span><span class="sxs-lookup"><span data-stu-id="b6b5f-338">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="b6b5f-339">.NET Core 3.0 は、標準形式からの非対称の公開キーと秘密キーのインポートとエクスポートをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-339">.NET Core 3.0 supports the import and export of asymmetric public and private keys from standard formats.</span></span> <span data-ttu-id="b6b5f-340">X.509 証明書を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-340">You don't need to use an X.509 certificate.</span></span>

<span data-ttu-id="b6b5f-341">*RSA*、*DSA*、*ECDsa*、*ECDiffieHellman* などのすべてのキー種類は、以下の形式をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-341">All key types, such as *RSA*, *DSA*, *ECDsa*, and *ECDiffieHellman*, support the following formats:</span></span>

* <span data-ttu-id="b6b5f-342">**公開キー**</span><span class="sxs-lookup"><span data-stu-id="b6b5f-342">**Public Key**</span></span>
  * <span data-ttu-id="b6b5f-343">X.509 SubjectPublicKeyInfo</span><span class="sxs-lookup"><span data-stu-id="b6b5f-343">X.509 SubjectPublicKeyInfo</span></span>

* <span data-ttu-id="b6b5f-344">**秘密キー**</span><span class="sxs-lookup"><span data-stu-id="b6b5f-344">**Private key**</span></span>
  * <span data-ttu-id="b6b5f-345">PKCS#8 PrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="b6b5f-345">PKCS#8 PrivateKeyInfo</span></span>
  * <span data-ttu-id="b6b5f-346">PKCS#8 EncryptedPrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="b6b5f-346">PKCS#8 EncryptedPrivateKeyInfo</span></span>

<span data-ttu-id="b6b5f-347">RSA キーは以下もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-347">RSA keys also support:</span></span>

* <span data-ttu-id="b6b5f-348">**公開キー**</span><span class="sxs-lookup"><span data-stu-id="b6b5f-348">**Public Key**</span></span>
  * <span data-ttu-id="b6b5f-349">PKCS#1 RSAPublicKey</span><span class="sxs-lookup"><span data-stu-id="b6b5f-349">PKCS#1 RSAPublicKey</span></span>

* <span data-ttu-id="b6b5f-350">**秘密キー**</span><span class="sxs-lookup"><span data-stu-id="b6b5f-350">**Private key**</span></span>
  * <span data-ttu-id="b6b5f-351">PKCS#1 RSAPrivateKey</span><span class="sxs-lookup"><span data-stu-id="b6b5f-351">PKCS#1 RSAPrivateKey</span></span>

<span data-ttu-id="b6b5f-352">エクスポートメソッドからは、DER でエンコードされたバイナリ データが生成され、インポート メソッドもそのようなデータを期待します。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-352">The export methods produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="b6b5f-353">キーがテキストに適した PEM 形式で格納されている場合、呼び出し元は import メソッドを呼び出す前にコンテンツを base64 でデコードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-353">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

[!CODE-csharp[RSA](~/samples/snippets/core/whats-new/whats-new-in-30/cs/RSA.cs#Rsa)]

<span data-ttu-id="b6b5f-354">**PKCS#8** ファイルは <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> を使用して検査できます。また、 **PFX/PKCS#12** ファイルは <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType> を使用して検査できます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-354">**PKCS#8** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> and **PFX/PKCS#12** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b6b5f-355">**PFX/PKCS#12** ファイルは <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType> を使用して操作できます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-355">**PFX/PKCS#12** files can be manipulated with <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span></span>

## <a name="serialport-for-linux"></a><span data-ttu-id="b6b5f-356">Linux 用 SerialPort</span><span class="sxs-lookup"><span data-stu-id="b6b5f-356">SerialPort for Linux</span></span>

<span data-ttu-id="b6b5f-357">.NET Core 3.0 は Linux 上で <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-357">.NET Core 3.0 supports <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="b6b5f-358">以前の .NET Core では、Windows 上の `SerialPort` の使用のみをサポートしていました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-358">Previously, .NET Core only supported using `SerialPort` on Windows.</span></span>

## <a name="docker-and-cgroup-memory-limits"></a><span data-ttu-id="b6b5f-359">Docker と cgroup のメモリ制限</span><span class="sxs-lookup"><span data-stu-id="b6b5f-359">Docker and cgroup memory Limits</span></span>

<span data-ttu-id="b6b5f-360">Preview 3 以降、Linux 上の Docker を使用した .NET Core 3.0 の実行は、cgroup のメモリ制限と適切に連携するようになりました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-360">Starting with Preview 3, running .NET Core 3.0 on Linux with Docker works better with cgroup memory limits.</span></span> <span data-ttu-id="b6b5f-361">`docker run -m` のように、メモリ制限を使用して Docker コンテナーを実行すると、.NET Core の動作が変わります。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-361">Running a Docker container with memory limits, such as with `docker run -m`, changes how .NET Core behaves.</span></span>

* <span data-ttu-id="b6b5f-362">既定のガベージ コレクター (GC) ヒープ サイズ: 最大 20 MB、またはコンテナーのメモリ制限の 75%。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-362">Default Garbage Collector (GC) heap size: maximum of 20 mb or 75% of the memory limit on the container.</span></span>
* <span data-ttu-id="b6b5f-363">明示的なサイズは、cgroup 制限の絶対数または割合として設定できます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-363">Explicit size can be set as an absolute number or percentage of cgroup limit.</span></span>
* <span data-ttu-id="b6b5f-364">GC ヒープあたりの最小予約セグメント サイズは 16 MB です。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-364">Minimum reserved segment size per GC heap is 16 mb.</span></span> <span data-ttu-id="b6b5f-365">このサイズによって、マシン上に作成されるヒープ数が減ります。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-365">This size reduces the number of heaps that are created on machines.</span></span>

## <a name="smaller-garbage-collection-heap-sizes"></a><span data-ttu-id="b6b5f-366">小さいガベージ コレクションのヒープ サイズ</span><span class="sxs-lookup"><span data-stu-id="b6b5f-366">Smaller Garbage Collection heap sizes</span></span>

<span data-ttu-id="b6b5f-367">ガベージ コレクターの既定のヒープ サイズが縮小され、.NET Core のメモリ使用量が減少しました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-367">The Garbage Collector's default heap size has been reduced resulting in .NET Core using less memory.</span></span> <span data-ttu-id="b6b5f-368">この変更は、最新のプロセッサ キャッシュ サイズでは、世代 0 の割り当て予算に合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-368">This change better aligns with the generation 0 allocation budget with modern processor cache sizes.</span></span>

## <a name="garbage-collection-large-page-support"></a><span data-ttu-id="b6b5f-369">ガベージ コレクションのラージ ページのサポート</span><span class="sxs-lookup"><span data-stu-id="b6b5f-369">Garbage Collection Large Page support</span></span>

<span data-ttu-id="b6b5f-370">ラージ ページ (Linux ではヒュージ ページとも呼ばれます) は、オペレーティング システムがネイティブ ページ サイズ (多くの場合は 4K) よりも大きいメモリ領域を確立して、このようなラージ ページを要求するアプリケーションのパフォーマンスを向上できる機能です。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-370">Large Pages (also known as Huge Pages on Linux) is a feature where the operating system is able to establish memory regions larger than the native page size (often 4K) to improve performance of the application requesting these large pages.</span></span>

<span data-ttu-id="b6b5f-371">Windows 上でラージ ページを割り当てることを選択するオプトイン機能として、**GCLargePages** 設定を使用してガベージ コレクターを構成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-371">The Garbage Collector can now be configured with the **GCLargePages** setting as an opt-in feature to choose to allocate large pages on Windows.</span></span>

## <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="b6b5f-372">Raspberry Pi の GPIO サポート</span><span class="sxs-lookup"><span data-stu-id="b6b5f-372">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="b6b5f-373">GPIO プログラミングに使用できる 2 つのパッケージが NuGet にリリースされました。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-373">Two packages have been released to NuGet that you can use for GPIO programming:</span></span>

* [<span data-ttu-id="b6b5f-374">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="b6b5f-374">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio)
* [<span data-ttu-id="b6b5f-375">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="b6b5f-375">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings)

<span data-ttu-id="b6b5f-376">GPIO パッケージには、*GPIO*、*SPI*、*I2C*、および *PWM* デバイス用の API が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-376">The GPIO packages include APIs for *GPIO*, *SPI*, *I2C*, and *PWM* devices.</span></span> <span data-ttu-id="b6b5f-377">IoT バインディング パッケージにはデバイス バインディングが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-377">The IoT bindings package includes device bindings.</span></span> <span data-ttu-id="b6b5f-378">詳細については、[デバイス GitHub リポジトリ](https://github.com/dotnet/iot/blob/master/src/devices/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-378">For more information, see the [devices GitHub repo](https://github.com/dotnet/iot/blob/master/src/devices/).</span></span>

## <a name="arm64-linux-support"></a><span data-ttu-id="b6b5f-379">ARM64 Linux のサポート</span><span class="sxs-lookup"><span data-stu-id="b6b5f-379">ARM64 Linux support</span></span>

<span data-ttu-id="b6b5f-380">.NET Core 3.0 では、Linux 用の ARM64 のサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-380">.NET Core 3.0 adds support for ARM64 for Linux.</span></span> <span data-ttu-id="b6b5f-381">現在、ARM64 の主なユース ケースは、IoT シナリオを使用しています。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-381">The primary use case for ARM64 is currently with IoT scenarios.</span></span> <span data-ttu-id="b6b5f-382">詳細については、[.NET Core ARM64 の状態](https://github.com/dotnet/announcements/issues/82)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-382">For more information, see [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82).</span></span>

<span data-ttu-id="b6b5f-383">[ARM64 上の .NET Core 用の Docker イメージ](https://hub.docker.com/r/microsoft/dotnet/)は、Alpine、Debian、および Ubuntu に使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-383">[Docker images for .NET Core on ARM64](https://hub.docker.com/r/microsoft/dotnet/) are available for Alpine, Debian, and Ubuntu.</span></span>

> [!NOTE]
> <span data-ttu-id="b6b5f-384">**ARM64** Windows のサポートはまだ使用できません。</span><span class="sxs-lookup"><span data-stu-id="b6b5f-384">**ARM64** Windows support isn't yet available.</span></span>
