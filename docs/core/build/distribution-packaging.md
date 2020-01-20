---
title: .NET Core の配布パッケージ
description: .NET Core を配布用にパッケージ化、名前付け、およびバージョン管理する方法について説明します。
author: tmds
ms.date: 10/09/2019
ms.openlocfilehash: cfd6003cfac5c00fc06ebc6195eccd55a0d7afe7
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740928"
---
# <a name="net-core-distribution-packaging"></a><span data-ttu-id="a8c27-103">.NET Core の配布パッケージ</span><span class="sxs-lookup"><span data-stu-id="a8c27-103">.NET Core distribution packaging</span></span>

<span data-ttu-id="a8c27-104">.NET Core はますます多くのプラットフォームで使用できるようになってきているため、.NET Core をパッケージ化し、名前を付け、バージョン管理する方法を知っていると便利です。</span><span class="sxs-lookup"><span data-stu-id="a8c27-104">As .NET Core becomes available on more and more platforms, it's useful to learn how to package, name, and version it.</span></span> <span data-ttu-id="a8c27-105">そうすることで、パッケージの管理者は、ユーザーの .NET の実行環境に左右されることなく一貫した体験が保証されるようにサポートできます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-105">This way, package maintainers can help ensure a consistent experience no matter where users choose to run .NET.</span></span> <span data-ttu-id="a8c27-106">この記事は以下のユーザーに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-106">This article is useful for users that are:</span></span>

- <span data-ttu-id="a8c27-107">ソースから .NET Core をビルドしようとしている。</span><span class="sxs-lookup"><span data-stu-id="a8c27-107">Attempting to build .NET Core from source.</span></span>
- <span data-ttu-id="a8c27-108">結果として生じるレイアウトまたは生成されるパッケージに影響する可能性がある .NET Core CLI に変更を加えたい。</span><span class="sxs-lookup"><span data-stu-id="a8c27-108">Wanting to make changes to the .NET Core CLI that could impact the resulting layout or packages produced.</span></span>

## <a name="disk-layout"></a><span data-ttu-id="a8c27-109">ディスク レイアウト</span><span class="sxs-lookup"><span data-stu-id="a8c27-109">Disk layout</span></span>

<span data-ttu-id="a8c27-110">インストールした .NET Core は複数のコンポーネントで構成されています。コンポーネントは、ファイルシステムで次のようにレイアウトされています。</span><span class="sxs-lookup"><span data-stu-id="a8c27-110">When installed, .NET Core consists of several components that are laid out as follows in the filesystem:</span></span>

```
{dotnet_root}                                     (*)
├── dotnet                       (1)
├── LICENSE.txt                  (8)
├── ThirdPartyNotices.txt        (8)
├── host                                          (*)
│   └── fxr                                       (*)
│       └── <fxr version>        (2)
├── sdk                                           (*)
│   ├── <sdk version>            (3)
│   └── NuGetFallbackFolder      (4)              (*)
├── packs                                         (*)
│   ├── Microsoft.AspNetCore.App.Ref              (*)
│   │   └── <aspnetcore ref version>     (11)
│   ├── Microsoft.NETCore.App.Ref                 (*)
│   │   └── <netcore ref version>        (12)
│   ├── Microsoft.NETCore.App.Host.<rid>          (*)
│   │   └── <apphost version>            (13)
│   ├── Microsoft.WindowsDesktop.App.Ref          (*)
│   │   └── <desktop ref version>        (14)
│   └── NETStandard.Library.Ref                   (*)
│       └── <netstandard version>        (15)
├── shared                                        (*)
│   ├── Microsoft.NETCore.App                     (*)
│   │   └── <runtime version>     (5)
│   ├── Microsoft.AspNetCore.App                  (*)
│   │   └── <aspnetcore version>  (6)
│   ├── Microsoft.AspNetCore.All                  (*)
│   │   └── <aspnetcore version>  (6)
│   └── Microsoft.WindowsDesktop.App              (*)
│       └── <desktop app version> (7)
└── templates                                     (*)
│   └── <templates version>      (17)
/
├── etc/dotnet
│       └── install_location     (16)
├── usr/share/man/man1
│       └── dotnet.1.gz          (9)
└── usr/bin
        └── dotnet               (10)
```

- <span data-ttu-id="a8c27-111">(1) **dotnet** ホスト (別名 "muxer (マルチプレクサー)") には 2 つの異なるロールがあります。アプリケーションを起動するランタイムのアクティブ化と、コマンドをディスパッチする SDK のアクティブ化です。</span><span class="sxs-lookup"><span data-stu-id="a8c27-111">(1) **dotnet** The host (also known as the "muxer") has two distinct roles: activate a runtime to launch an application, and activate an SDK to dispatch commands to it.</span></span> <span data-ttu-id="a8c27-112">ホストはネイティブの実行可能ファイルです (`dotnet.exe`)。</span><span class="sxs-lookup"><span data-stu-id="a8c27-112">The host is a native executable (`dotnet.exe`).</span></span>

<span data-ttu-id="a8c27-113">ホストは 1 つですが、他のコンポーネントのほとんどはバージョン管理されたディレクトリに入っています (2、3、5、6)。</span><span class="sxs-lookup"><span data-stu-id="a8c27-113">While there's a single host, most of the other components are in versioned directories (2,3,5,6).</span></span> <span data-ttu-id="a8c27-114">つまり、複数のバージョンが並列インストールされるので、それらをシステム上に置くことができます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-114">This means multiple versions can be present on the system since they're installed side by side.</span></span>

- <span data-ttu-id="a8c27-115">(2) **host/fxr/\<fxr バージョン>** には、ホストが使用するフレームワーク解決ロジックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-115">(2) **host/fxr/\<fxr version>** contains the framework resolution logic used by the host.</span></span> <span data-ttu-id="a8c27-116">ホストでは、インストールされている最新の hostfxr が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-116">The host uses the latest hostfxr that is installed.</span></span> <span data-ttu-id="a8c27-117">hostfxr は、.NET Core アプリケーションの実行時に適切なランタイムを選択する役割を担います。</span><span class="sxs-lookup"><span data-stu-id="a8c27-117">The hostfxr is responsible for selecting the appropriate runtime when executing a .NET Core application.</span></span> <span data-ttu-id="a8c27-118">たとえば、.NET Core 2.0.0 用としてビルドされたアプリケーションは、2.0.5 が利用できればそれを利用します。</span><span class="sxs-lookup"><span data-stu-id="a8c27-118">For example, an application built for .NET Core 2.0.0 uses the 2.0.5 runtime when it's available.</span></span> <span data-ttu-id="a8c27-119">同様に、hostfxr は開発中、適切な SDK を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8c27-119">Similarly, hostfxr selects the appropriate SDK during development.</span></span>

- <span data-ttu-id="a8c27-120">(3) **sdk/\<sdk バージョン>** SDK (別名 "ツール") は、.NET Core のライブラリやアプリケーションを記述し、ビルドするために使用されるマネージド ツールのセットです。</span><span class="sxs-lookup"><span data-stu-id="a8c27-120">(3) **sdk/\<sdk version>** The SDK (also known as "the tooling") is a set of managed tools that are used to write and build .NET Core libraries and applications.</span></span> <span data-ttu-id="a8c27-121">SDK には、.NET Core コマンドライン インターフェイス (CLI)、マネージ言語コンパイラ、MSBuild、関連するビルド タスクとターゲット、NuGet、新しいプロジェクト テンプレートなどが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a8c27-121">The SDK includes the .NET Core Command-line interface (CLI), the managed languages compilers, MSBuild, and associated build tasks and targets, NuGet, new project templates, and so on.</span></span>

- <span data-ttu-id="a8c27-122">(4) **sdk/NuGetFallbackFolder** には、`dotnet restore` や `dotnet build` の実行時など、復元操作中に SDK によって使用される NuGet パッケージのキャッシュが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a8c27-122">(4) **sdk/NuGetFallbackFolder** contains a cache of NuGet packages used by an SDK during the restore operation, such as when running `dotnet restore` or `dotnet build`.</span></span> <span data-ttu-id="a8c27-123">このフォルダーは、.NET Core 3.0 より前でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-123">This folder is only used prior to .NET Core 3.0.</span></span> <span data-ttu-id="a8c27-124">`nuget.org` からの構築済みのバイナリ アセットを含むため、ソースから作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="a8c27-124">It can't be built from source, because it contains prebuilt binary assets from `nuget.org`.</span></span>

<span data-ttu-id="a8c27-125">**共有**フォルダーには、フレームワークが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a8c27-125">The **shared** folder contains frameworks.</span></span> <span data-ttu-id="a8c27-126">共有フレームワークは、さまざまなアプリケーションで利用できるように、中央の場所で一連のライブラリを提供します。</span><span class="sxs-lookup"><span data-stu-id="a8c27-126">A shared framework provides a set of libraries at a central location so they can be used by different applications.</span></span>

- <span data-ttu-id="a8c27-127">(5) **shared/Microsoft.NETCore.App/\<runtime バージョン&gt;** このフレームワークには、.NET Core のランタイムと補助マネージド ライブラリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a8c27-127">(5) **shared/Microsoft.NETCore.App/\<runtime version>** This framework contains the .NET Core runtime and supporting managed libraries.</span></span>

- <span data-ttu-id="a8c27-128">(6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore バージョン>** には、ASP.NET Core ライブラリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-128">(6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** contains the ASP.NET Core libraries.</span></span> <span data-ttu-id="a8c27-129">`Microsoft.AspNetCore.App` の下にあるライブラリは、.NET Core プロジェクトの一部として開発され、サポートされています。</span><span class="sxs-lookup"><span data-stu-id="a8c27-129">The libraries under `Microsoft.AspNetCore.App` are developed and supported as part of the .NET Core project.</span></span> <span data-ttu-id="a8c27-130">`Microsoft.AspNetCore.All` の下にあるライブラリは、サードパーティ製ライブラリも含まれるスーパーセットです。</span><span class="sxs-lookup"><span data-stu-id="a8c27-130">The libraries under `Microsoft.AspNetCore.All` are a superset that also contains third-party libraries.</span></span>

- <span data-ttu-id="a8c27-131">(7) **shared/Microsoft.Desktop.App/\<デスクトップ アプリ バージョン>** には、Windows デスクトップ ライブラリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-131">(7) **shared/Microsoft.Desktop.App/\<desktop app version>** contains the Windows desktop libraries.</span></span> <span data-ttu-id="a8c27-132">これは、Windows 以外のプラットフォームには含まれていません。</span><span class="sxs-lookup"><span data-stu-id="a8c27-132">This isn't included on non-Windows platforms.</span></span>

- <span data-ttu-id="a8c27-133">(8) **LICENSE.txt、ThirdPartyNotices.txt** は、それぞれ .NET Core ライセンスと、.NET Core で利用されるサードパーティ ライブラリのライセンスです。</span><span class="sxs-lookup"><span data-stu-id="a8c27-133">(8) **LICENSE.txt,ThirdPartyNotices.txt** are the .NET Core license and licenses of third-party libraries used in .NET Core, respectively.</span></span>

- <span data-ttu-id="a8c27-134">(9,10) **dotnet.1.gz、dotnet** `dotnet.1.gz` は dotnet のマニュアル ページです。</span><span class="sxs-lookup"><span data-stu-id="a8c27-134">(9,10) **dotnet.1.gz, dotnet** `dotnet.1.gz` is the dotnet manual page.</span></span> <span data-ttu-id="a8c27-135">`dotnet` は dotnet host(1) のシンボリック リンクです。</span><span class="sxs-lookup"><span data-stu-id="a8c27-135">`dotnet` is a symlink to the dotnet host(1).</span></span> <span data-ttu-id="a8c27-136">これらのファイルは、システム統合のために、よく知られている場所にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-136">These files are installed at well-known locations for system integration.</span></span>

- <span data-ttu-id="a8c27-137">(11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref** には、.NET Core と ASP.NET Core のそれぞれの `x.y` バージョンの API が記述されています。</span><span class="sxs-lookup"><span data-stu-id="a8c27-137">(11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref** describe the API of an `x.y` version of .NET Core and ASP.NET Core respectively.</span></span> <span data-ttu-id="a8c27-138">これらのパックは、それのターゲット バージョンのコンパイル時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-138">These packs are used when compiling for those target versions.</span></span>

- <span data-ttu-id="a8c27-139">(13) **Microsoft.NETCore.App.Host.\<rid>** には、プラットフォーム `rid` のネイティブ バイナリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-139">(13) **Microsoft.NETCore.App.Host.\<rid>** contains a native binary for platform `rid`.</span></span> <span data-ttu-id="a8c27-140">このバイナリは、.NET Core アプリケーションをそのプラットフォームのネイティブ バイナリにコンパイルするときのテンプレートです。</span><span class="sxs-lookup"><span data-stu-id="a8c27-140">This binary is a template when compiling a .NET Core application into a native binary for that platform.</span></span>

- <span data-ttu-id="a8c27-141">(14) **Microsoft.WindowsDesktop.App.Ref** には、Windows Desktop アプリケーションの `x.y` バージョンの API が記述されています。</span><span class="sxs-lookup"><span data-stu-id="a8c27-141">(14) **Microsoft.WindowsDesktop.App.Ref** describes the API of `x.y` version of Windows Desktop applications.</span></span> <span data-ttu-id="a8c27-142">これらのファイルは、そのターゲットに対してコンパイルする場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-142">These files are used when compiling for that target.</span></span> <span data-ttu-id="a8c27-143">これは、Windows 以外のプラットフォームにはありません。</span><span class="sxs-lookup"><span data-stu-id="a8c27-143">This isn't provided on non-Windows platforms.</span></span>

- <span data-ttu-id="a8c27-144">(15) **NETStandard.Library.Ref** には、netstandard `x.y` の API が記述されています。</span><span class="sxs-lookup"><span data-stu-id="a8c27-144">(15) **NETStandard.Library.Ref** describes the netstandard `x.y` API.</span></span> <span data-ttu-id="a8c27-145">これらのファイルは、そのターゲットに対してコンパイルする場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-145">These files are used when compiling for that target.</span></span>

- <span data-ttu-id="a8c27-146">(16) **/etc/dotnet/install_location** は、`{dotnet_root}` の完全なパスを含むファイルです。</span><span class="sxs-lookup"><span data-stu-id="a8c27-146">(16) **/etc/dotnet/install_location** is a file that contains the full path for `{dotnet_root}`.</span></span> <span data-ttu-id="a8c27-147">パスの末尾は改行文字である場合があります。</span><span class="sxs-lookup"><span data-stu-id="a8c27-147">The path may end with a newline.</span></span> <span data-ttu-id="a8c27-148">ルートが `/usr/share/dotnet` の場合は、このファイルを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a8c27-148">It's not necessary to add this file when the root is `/usr/share/dotnet`.</span></span>

- <span data-ttu-id="a8c27-149">(17) **templates** には、SDK で使用されるテンプレートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-149">(17) **templates** contains the templates used by the SDK.</span></span> <span data-ttu-id="a8c27-150">たとえば、`dotnet new` はここからプロジェクト テンプレートを検索します。</span><span class="sxs-lookup"><span data-stu-id="a8c27-150">For example, `dotnet new` finds project templates here.</span></span>

<span data-ttu-id="a8c27-151">`(*)` でマークされたフォルダーは、複数のパッケージによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-151">The folders marked with `(*)` are used by multiple packages.</span></span> <span data-ttu-id="a8c27-152">一部のパッケージ形式 (たとえば、`rpm`) では、このようなフォルダーを特別に処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8c27-152">Some package formats (for example, `rpm`) require special handling of such folders.</span></span> <span data-ttu-id="a8c27-153">パッケージのメンテナンス担当者は、このことに対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8c27-153">The package maintainer must take care of this.</span></span>

## <a name="recommended-packages"></a><span data-ttu-id="a8c27-154">推奨パッケージ</span><span class="sxs-lookup"><span data-stu-id="a8c27-154">Recommended packages</span></span>

<span data-ttu-id="a8c27-155">.NET Core バージョン管理は、ランタイム コンポーネント `[major].[minor]` バージョン番号に基づきます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-155">.NET Core versioning is based on the runtime component `[major].[minor]` version numbers.</span></span>
<span data-ttu-id="a8c27-156">SDK バージョンは同じ `[major].[minor]` を利用し、SDK の機能とパッチ意味論を結合する非依存の `[patch]` が与えられます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-156">The SDK version uses the same `[major].[minor]` and has an independent `[patch]` that combines feature and patch semantics for the SDK.</span></span>
<span data-ttu-id="a8c27-157">次に例を示します。SDK バージョン 2.2.302 は、2.2 ランタイム対応の SDK の第 3 機能リリースの第 2 パッチ リリースです。</span><span class="sxs-lookup"><span data-stu-id="a8c27-157">For example: SDK version 2.2.302 is the second patch release of the third feature release of the SDK that supports the 2.2 runtime.</span></span> <span data-ttu-id="a8c27-158">バージョン管理のしくみの詳細については、[.NET Core のバージョン管理の概要](../versions/index.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8c27-158">For more information about how versioning works, see [.NET Core versioning overview](../versions/index.md).</span></span>

<span data-ttu-id="a8c27-159">パッケージには、その名前にバージョン番号の一部が含まれているものもあります。</span><span class="sxs-lookup"><span data-stu-id="a8c27-159">Some of the packages include part of the version number in their name.</span></span> <span data-ttu-id="a8c27-160">それによって、特定のバージョンをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-160">This allows you to install a specific version.</span></span>
<span data-ttu-id="a8c27-161">バージョンの残りの部分はバージョン名には含まれていません。</span><span class="sxs-lookup"><span data-stu-id="a8c27-161">The rest of the version isn't included in the version name.</span></span> <span data-ttu-id="a8c27-162">それによって、OS パッケージ マネージャーはパッケージを更新できます (セキュリティ修正の自動インストールなど)。</span><span class="sxs-lookup"><span data-stu-id="a8c27-162">This allows the OS package manager to update the packages (for example, automatically installing security fixes).</span></span> <span data-ttu-id="a8c27-163">サポートされるパッケージ マネージャーは Linux 固有です。</span><span class="sxs-lookup"><span data-stu-id="a8c27-163">Supported package managers are Linux specific.</span></span>

<span data-ttu-id="a8c27-164">推奨するパッケージを、以下に示します。</span><span class="sxs-lookup"><span data-stu-id="a8c27-164">The following lists the recommended packages:</span></span>

- <span data-ttu-id="a8c27-165">`dotnet-sdk-[major].[minor]`: 特定のランタイム用に最新の sdk をインストールします</span><span class="sxs-lookup"><span data-stu-id="a8c27-165">`dotnet-sdk-[major].[minor]` - Installs the latest sdk for specific runtime</span></span>
  - <span data-ttu-id="a8c27-166">**バージョン:** \<ランタイム バージョン></span><span class="sxs-lookup"><span data-stu-id="a8c27-166">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="a8c27-167">**例:** dotnet-sdk-2.1</span><span class="sxs-lookup"><span data-stu-id="a8c27-167">**Example:** dotnet-sdk-2.1</span></span>
  - <span data-ttu-id="a8c27-168">**内容:** (3),(4)</span><span class="sxs-lookup"><span data-stu-id="a8c27-168">**Contains:** (3),(4)</span></span>
  - <span data-ttu-id="a8c27-169">**依存関係:** `dotnet-runtime-[major].[minor]`、`aspnetcore-runtime-[major].[minor]`、`dotnet-targeting-pack-[major].[minor]`、`aspnetcore-targeting-pack-[major].[minor]`、`netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`、`dotnet-apphost-pack-[major].[minor]`、`dotnet-templates-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="a8c27-169">**Dependencies:** `dotnet-runtime-[major].[minor]`, `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`</span></span>

- <span data-ttu-id="a8c27-170">`aspnetcore-runtime-[major].[minor]`: 特定の ASP.NET Core ランタイムをインストールします</span><span class="sxs-lookup"><span data-stu-id="a8c27-170">`aspnetcore-runtime-[major].[minor]` - Installs a specific ASP.NET Core runtime</span></span>
  - <span data-ttu-id="a8c27-171">**バージョン:** \<aspnetcore ランタイム バージョン></span><span class="sxs-lookup"><span data-stu-id="a8c27-171">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="a8c27-172">**例:** aspnetcore-runtime-2.1</span><span class="sxs-lookup"><span data-stu-id="a8c27-172">**Example:** aspnetcore-runtime-2.1</span></span>
  - <span data-ttu-id="a8c27-173">**内容:** (6)</span><span class="sxs-lookup"><span data-stu-id="a8c27-173">**Contains:** (6)</span></span>
  - <span data-ttu-id="a8c27-174">**依存関係:** `dotnet-runtime-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="a8c27-174">**Dependencies:** `dotnet-runtime-[major].[minor]`</span></span>

- <span data-ttu-id="a8c27-175">`dotnet-runtime-deps-[major].[minor]` _(省略可能)_ : 自己完結型アプリケーションを実行する依存関係をインストールします</span><span class="sxs-lookup"><span data-stu-id="a8c27-175">`dotnet-runtime-deps-[major].[minor]` _(Optional)_ - Installs the dependencies for running self-contained applications</span></span>
  - <span data-ttu-id="a8c27-176">**バージョン:** \<ランタイム バージョン></span><span class="sxs-lookup"><span data-stu-id="a8c27-176">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="a8c27-177">**例:** dotnet-runtime-deps-2.1</span><span class="sxs-lookup"><span data-stu-id="a8c27-177">**Example:** dotnet-runtime-deps-2.1</span></span>
  - <span data-ttu-id="a8c27-178">**依存関係:** _ディストリビューション固有の依存関係_</span><span class="sxs-lookup"><span data-stu-id="a8c27-178">**Dependencies:** _distribution-specific dependencies_</span></span>

- <span data-ttu-id="a8c27-179">`dotnet-runtime-[major].[minor]`: 特定のランタイムをインストールします</span><span class="sxs-lookup"><span data-stu-id="a8c27-179">`dotnet-runtime-[major].[minor]` - Installs a specific runtime</span></span>
  - <span data-ttu-id="a8c27-180">**バージョン:** \<ランタイム バージョン></span><span class="sxs-lookup"><span data-stu-id="a8c27-180">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="a8c27-181">**例:** dotnet-runtime-2.1</span><span class="sxs-lookup"><span data-stu-id="a8c27-181">**Example:** dotnet-runtime-2.1</span></span>
  - <span data-ttu-id="a8c27-182">**内容:** (5)</span><span class="sxs-lookup"><span data-stu-id="a8c27-182">**Contains:** (5)</span></span>
  - <span data-ttu-id="a8c27-183">**依存関係:** `dotnet-hostfxr-[major].[minor]`, `dotnet-runtime-deps-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="a8c27-183">**Dependencies:** `dotnet-hostfxr-[major].[minor]`, `dotnet-runtime-deps-[major].[minor]`</span></span>

- <span data-ttu-id="a8c27-184">`dotnet-hostfxr-[major].[minor]`: 依存関係</span><span class="sxs-lookup"><span data-stu-id="a8c27-184">`dotnet-hostfxr-[major].[minor]` - dependency</span></span>
  - <span data-ttu-id="a8c27-185">**バージョン:** \<ランタイム バージョン></span><span class="sxs-lookup"><span data-stu-id="a8c27-185">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="a8c27-186">**例:**  dotnet-hostfxr-3.0</span><span class="sxs-lookup"><span data-stu-id="a8c27-186">**Example:** dotnet-hostfxr-3.0</span></span>
  - <span data-ttu-id="a8c27-187">**内容:** (2)</span><span class="sxs-lookup"><span data-stu-id="a8c27-187">**Contains:** (2)</span></span>
  - <span data-ttu-id="a8c27-188">**依存関係:** `dotnet-host`</span><span class="sxs-lookup"><span data-stu-id="a8c27-188">**Dependencies:** `dotnet-host`</span></span>

- <span data-ttu-id="a8c27-189">`dotnet-host`: 依存関係</span><span class="sxs-lookup"><span data-stu-id="a8c27-189">`dotnet-host` - dependency</span></span>
  - <span data-ttu-id="a8c27-190">**バージョン:** \<ランタイム バージョン></span><span class="sxs-lookup"><span data-stu-id="a8c27-190">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="a8c27-191">**例:** dotnet-host</span><span class="sxs-lookup"><span data-stu-id="a8c27-191">**Example:** dotnet-host</span></span>
  - <span data-ttu-id="a8c27-192">**内容:** (1)、(8)、(9)、(10)、(16)</span><span class="sxs-lookup"><span data-stu-id="a8c27-192">**Contains:** (1),(8),(9),(10),(16)</span></span>

- <span data-ttu-id="a8c27-193">`dotnet-apphost-pack-[major].[minor]`: 依存関係</span><span class="sxs-lookup"><span data-stu-id="a8c27-193">`dotnet-apphost-pack-[major].[minor]` - dependency</span></span>
  - <span data-ttu-id="a8c27-194">**バージョン:** \<ランタイム バージョン></span><span class="sxs-lookup"><span data-stu-id="a8c27-194">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="a8c27-195">**内容:** (13)</span><span class="sxs-lookup"><span data-stu-id="a8c27-195">**Contains:** (13)</span></span>

- <span data-ttu-id="a8c27-196">`dotnet-targeting-pack-[major].[minor]`: 最新ではないランタイムを対象にできます</span><span class="sxs-lookup"><span data-stu-id="a8c27-196">`dotnet-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="a8c27-197">**バージョン:** \<ランタイム バージョン></span><span class="sxs-lookup"><span data-stu-id="a8c27-197">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="a8c27-198">**内容:** (12)</span><span class="sxs-lookup"><span data-stu-id="a8c27-198">**Contains:** (12)</span></span>

- <span data-ttu-id="a8c27-199">`aspnetcore-targeting-pack-[major].[minor]`: 最新ではないランタイムを対象にできます</span><span class="sxs-lookup"><span data-stu-id="a8c27-199">`aspnetcore-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="a8c27-200">**バージョン:** \<aspnetcore ランタイム バージョン></span><span class="sxs-lookup"><span data-stu-id="a8c27-200">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="a8c27-201">**内容:** (11)</span><span class="sxs-lookup"><span data-stu-id="a8c27-201">**Contains:** (11)</span></span>

- <span data-ttu-id="a8c27-202">`netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`: netstandard バージョンを対象にできます</span><span class="sxs-lookup"><span data-stu-id="a8c27-202">`netstandard-targeting-pack-[netstandard_major].[netstandard_minor]` - Allows targeting a netstandard version</span></span>
  - <span data-ttu-id="a8c27-203">**バージョン:** \<sdk バージョン></span><span class="sxs-lookup"><span data-stu-id="a8c27-203">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="a8c27-204">**内容:** (15)</span><span class="sxs-lookup"><span data-stu-id="a8c27-204">**Contains:** (15)</span></span>

- `dotnet-templates-[major].[minor]`
  - <span data-ttu-id="a8c27-205">**バージョン:** \<sdk バージョン></span><span class="sxs-lookup"><span data-stu-id="a8c27-205">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="a8c27-206">**内容:** (15)</span><span class="sxs-lookup"><span data-stu-id="a8c27-206">**Contains:** (15)</span></span>

<span data-ttu-id="a8c27-207">`dotnet-runtime-deps-[major].[minor]` では、_ディストリビューション固有の依存関係_を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8c27-207">The `dotnet-runtime-deps-[major].[minor]` requires understanding the _distro-specific dependencies_.</span></span> <span data-ttu-id="a8c27-208">ディストリビューションのビルド システムは、これを自動的に得ることができる可能性があるため、このパッケージは省略可能です。これらの場合、これらの依存関係は `dotnet-runtime-[major].[minor]` パッケージに直接追加されます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-208">Because the distro build system may be able to derive this automatically, the package is optional, in which case these dependencies are added directly to the `dotnet-runtime-[major].[minor]` package.</span></span>

<span data-ttu-id="a8c27-209">パッケージの内容がバージョン付きフォルダーにある場合、`[major].[minor]` のパッケージ名はバージョン付きのフォルダー名と同じになります。</span><span class="sxs-lookup"><span data-stu-id="a8c27-209">When package content is under a versioned folder, the package name `[major].[minor]` match the versioned folder name.</span></span> <span data-ttu-id="a8c27-210">`netstandard-targeting-pack-[netstandard_major].[netstandard_minor]` を除くすべてのパッケージでは、これは .NET Core バージョンとも同じになります。</span><span class="sxs-lookup"><span data-stu-id="a8c27-210">For all packages, except the `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, this also matches with the .NET Core version.</span></span>

<span data-ttu-id="a8c27-211">パッケージ間の依存関係では、バージョン要件_以上_を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8c27-211">Dependencies between packages should use an _equal or greater than_ version requirement.</span></span> <span data-ttu-id="a8c27-212">たとえば、`dotnet-sdk-2.2:2.2.401` には `aspnetcore-runtime-2.2 >= 2.2.6` が必要です。</span><span class="sxs-lookup"><span data-stu-id="a8c27-212">For example, `dotnet-sdk-2.2:2.2.401` requires `aspnetcore-runtime-2.2 >= 2.2.6`.</span></span> <span data-ttu-id="a8c27-213">これにより、ユーザーはルート パッケージ (たとえば、`dnf update dotnet-sdk-2.2`) を使用してインストールをアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-213">This makes it possible for the user to upgrade their installation via a root package (for example, `dnf update dotnet-sdk-2.2`).</span></span>

<span data-ttu-id="a8c27-214">ほとんどのディストリビューションで、ソースからビルドするすべての成果物を必要とします。</span><span class="sxs-lookup"><span data-stu-id="a8c27-214">Most distributions require all artifacts to be built from source.</span></span> <span data-ttu-id="a8c27-215">これはパッケージにいくつかの影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-215">This has some impact on the packages:</span></span>

- <span data-ttu-id="a8c27-216">`shared/Microsoft.AspNetCore.All` の下にあるサードパーティ製ライブラリは、ソースから簡単にビルドできません。</span><span class="sxs-lookup"><span data-stu-id="a8c27-216">The third-party libraries under `shared/Microsoft.AspNetCore.All` can't be easily built from source.</span></span> <span data-ttu-id="a8c27-217">そのため、そのフォルダーは `aspnetcore-runtime` パッケージから除外されます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-217">So that folder is omitted from the `aspnetcore-runtime` package.</span></span>

- <span data-ttu-id="a8c27-218">`NuGetFallbackFolder` は `nuget.org` からバイナリ成果物を利用して入力されます。</span><span class="sxs-lookup"><span data-stu-id="a8c27-218">The `NuGetFallbackFolder` is populated using binary artifacts from `nuget.org`.</span></span> <span data-ttu-id="a8c27-219">空のままにしてください。</span><span class="sxs-lookup"><span data-stu-id="a8c27-219">It should remain empty.</span></span>

<span data-ttu-id="a8c27-220">複数の `dotnet-sdk` パッケージで `NuGetFallbackFolder` に同じファイルが提供されることがあります。</span><span class="sxs-lookup"><span data-stu-id="a8c27-220">Multiple `dotnet-sdk` packages may provide the same files for the `NuGetFallbackFolder`.</span></span> <span data-ttu-id="a8c27-221">パッケージ マネージャーの問題を回避するには、これらのファイルを同じにします (チェックサム、変更日など)。</span><span class="sxs-lookup"><span data-stu-id="a8c27-221">To avoid issues with the package manager, these files should be identical (checksum, modification date, and so on).</span></span>

## <a name="building-packages"></a><span data-ttu-id="a8c27-222">パッケージをビルドする</span><span class="sxs-lookup"><span data-stu-id="a8c27-222">Building packages</span></span>

<span data-ttu-id="a8c27-223">[dotnet/source-build](https://github.com/dotnet/source-build) リポジトリには、.NET Core SDK のソース ターボールとそのすべてのコンポーネントをビルドする方法があります。</span><span class="sxs-lookup"><span data-stu-id="a8c27-223">The [dotnet/source-build](https://github.com/dotnet/source-build) repository provides instructions on how to build a source tarball of the .NET Core SDK and all its components.</span></span> <span data-ttu-id="a8c27-224">この source-build リポジトリの出力は、この記事の最初のセクションで説明したレイアウトに一致します。</span><span class="sxs-lookup"><span data-stu-id="a8c27-224">The output of the source-build repository matches the layout described in the first section of this article.</span></span>
