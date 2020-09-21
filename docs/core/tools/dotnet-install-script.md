---
title: dotnet-install スクリプト
description: .NET Core SDK と共有ランタイムをインストールするための dotnet-install スクリプトについて学習します。
ms.date: 04/30/2020
ms.openlocfilehash: 8f27b8a7794e84e6e2b288d6cc2ec33ffcb7600f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538043"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="dbc6b-103">dotnet-install スクリプト リファレンス</span><span class="sxs-lookup"><span data-stu-id="dbc6b-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="dbc6b-104">名前</span><span class="sxs-lookup"><span data-stu-id="dbc6b-104">Name</span></span>

<span data-ttu-id="dbc6b-105">`dotnet-install.ps1` | `dotnet-install.sh` - .NET Core SDK と共有ランタイムをインストールするために使うスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core SDK and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="dbc6b-106">構文</span><span class="sxs-lookup"><span data-stu-id="dbc6b-106">Synopsis</span></span>

<span data-ttu-id="dbc6b-107">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="dbc6b-107">Windows:</span></span>

```powershell
dotnet-install.ps1 [-Architecture <ARCHITECTURE>] [-AzureFeed]
    [-Channel <CHANNEL>] [-DryRun] [-FeedCredential]
    [-InstallDir <DIRECTORY>] [-JSonFile <JSONFILE>]
    [-NoCdn] [-NoPath] [-ProxyAddress] [-ProxyBypassList <LIST_OF_URLS>]
    [-ProxyUseDefaultCredentials] [-Runtime <RUNTIME>]
    [-SkipNonVersionedFiles] [-UncachedFeed] [-Verbose]
    [-Version <VERSION>]

Get-Help ./dotnet-install.ps1
```

<span data-ttu-id="dbc6b-108">Linux/macOS:</span><span class="sxs-lookup"><span data-stu-id="dbc6b-108">Linux/macOS:</span></span>

```bash
dotnet-install.sh  [--architecture <ARCHITECTURE>] [--azure-feed]
    [--channel <CHANNEL>] [--dry-run] [--feed-credential]
    [--install-dir <DIRECTORY>] [--jsonfile <JSONFILE>]
    [--no-cdn] [--no-path] [--runtime <RUNTIME>] [--runtime-id <RID>]
    [--skip-non-versioned-files] [--uncached-feed] [--verbose]
    [--version <VERSION>]

dotnet-install.sh --help
```

<span data-ttu-id="dbc6b-109">bash スクリプトは PowerShell のスイッチも読み取るので、Linux/macOS システムのスクリプトで PowerShell のスイッチを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-109">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

## <a name="description"></a><span data-ttu-id="dbc6b-110">説明</span><span class="sxs-lookup"><span data-stu-id="dbc6b-110">Description</span></span>

<span data-ttu-id="dbc6b-111">`dotnet-install` スクリプトによって、.NET Core CLI や共有ランタイムを含む .NET Core SDK の非管理者インストールが実行されます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-111">The `dotnet-install` scripts perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI and the shared runtime.</span></span> <span data-ttu-id="dbc6b-112">次の 2 つのスクリプトがあります。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-112">There are two scripts:</span></span>

* <span data-ttu-id="dbc6b-113">Windows 上で動作する PowerShell スクリプト。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-113">A PowerShell script that works on Windows.</span></span>
* <span data-ttu-id="dbc6b-114">Linux/macOS で動作する bash スクリプト。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-114">A bash script that works on Linux/macOS.</span></span>

### <a name="purpose"></a><span data-ttu-id="dbc6b-115">目的</span><span class="sxs-lookup"><span data-stu-id="dbc6b-115">Purpose</span></span>

 <span data-ttu-id="dbc6b-116">このスクリプトの用途は本来、次のような継続的インテグレーション (CI) シナリオ向けとして意図されています。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-116">The intended use of the scripts is for Continuous Integration (CI) scenarios, where:</span></span>

* <span data-ttu-id="dbc6b-117">ユーザーの操作と管理者権限なしで SDK をインストールする必要がある。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-117">The SDK needs to be installed without user interaction and without admin rights.</span></span>
* <span data-ttu-id="dbc6b-118">SDK インストールを複数の CI 実行間で保持する必要がない。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-118">The SDK installation doesn't need to persist across multiple CI runs.</span></span>

  <span data-ttu-id="dbc6b-119">イベントの一般的なシーケンス:</span><span class="sxs-lookup"><span data-stu-id="dbc6b-119">The typical sequence of events:</span></span>
  * <span data-ttu-id="dbc6b-120">CI がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-120">CI is triggered.</span></span>
  * <span data-ttu-id="dbc6b-121">CI により、これらのスクリプトの 1 つを利用して SDK がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-121">CI installs the SDK using one of these scripts.</span></span>
  * <span data-ttu-id="dbc6b-122">CI でその作業が完了し、SDK インストールを含む、一時的なデータが消去されます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-122">CI finishes its work and clears temporary data including the SDK installation.</span></span>

<span data-ttu-id="dbc6b-123">開発環境を設定するか、アプリを実行するには、これらのスクリプトではなく、インストーラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-123">To set up a development environment or to run apps, use the installers rather than these scripts.</span></span>

### <a name="recommended-version"></a><span data-ttu-id="dbc6b-124">推奨されるバージョン</span><span class="sxs-lookup"><span data-stu-id="dbc6b-124">Recommended version</span></span>

<span data-ttu-id="dbc6b-125">安定したバージョンのスクリプトを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-125">We recommend that you use the stable version of the scripts:</span></span>

- <span data-ttu-id="dbc6b-126">Bash (Linux、macOS): <https://dot.net/v1/dotnet-install.sh></span><span class="sxs-lookup"><span data-stu-id="dbc6b-126">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span></span>
- <span data-ttu-id="dbc6b-127">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span><span class="sxs-lookup"><span data-stu-id="dbc6b-127">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span></span>

### <a name="script-behavior"></a><span data-ttu-id="dbc6b-128">スクリプトの動作</span><span class="sxs-lookup"><span data-stu-id="dbc6b-128">Script behavior</span></span>

<span data-ttu-id="dbc6b-129">スクリプトの動作は両方とも同じです。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-129">Both scripts have the same behavior.</span></span> <span data-ttu-id="dbc6b-130">CLI ビルド ドロップから ZIP/tarball ファイルをダウンロードし、既定の場所または `-InstallDir|--install-dir` で指定された場所へのインストールに進みます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-130">They download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span>

<span data-ttu-id="dbc6b-131">既定では、インストール スクリプトは SDK をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-131">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="dbc6b-132">共有ランタイムの取得だけを行いたい場合は、`-Runtime|--runtime` 引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-132">If you wish to only obtain the shared runtime, specify the `-Runtime|--runtime` argument.</span></span>

<span data-ttu-id="dbc6b-133">既定では、スクリプトはインストールの場所を現在のセッションの $PATH に追加します。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-133">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="dbc6b-134">`-NoPath|--no-path` 引数を指定することによってこの既定の動作をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-134">Override this default behavior by specifying the `-NoPath|--no-path` argument.</span></span> <span data-ttu-id="dbc6b-135">スクリプトでは、`DOTNET_ROOT` 環境変数は設定されません。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-135">The script doesn't set the `DOTNET_ROOT` environment variable.</span></span>

<span data-ttu-id="dbc6b-136">スクリプトを実行する前に、必要な[依存関係](../install/windows.md#dependencies)をすべてインストールします。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-136">Before running the script, install the required [dependencies](../install/windows.md#dependencies).</span></span>

<span data-ttu-id="dbc6b-137">`-Version|--version` 引数を使用して、特定のバージョンをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-137">You can install a specific version using the `-Version|--version` argument.</span></span> <span data-ttu-id="dbc6b-138">バージョンには 3 つの部分からなるバージョン番号 (`2.1.0` など) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-138">The version must be specified as a three-part version number, such as `2.1.0`.</span></span> <span data-ttu-id="dbc6b-139">バージョンが指定されていない場合、スクリプトでは `latest` バージョンがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-139">If the version isn't specified, the script installs the `latest` version.</span></span>

<span data-ttu-id="dbc6b-140">インストール スクリプトでは、Windows 上のレジストリは更新されません。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-140">The install scripts do not update the registry on Windows.</span></span> <span data-ttu-id="dbc6b-141">zip 形式のバイナリがダウンロードされて、フォルダーにコピーされるだけです。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-141">They just download the zipped binaries and copy them to a folder.</span></span> <span data-ttu-id="dbc6b-142">レジストリ キーの値を更新する必要がある場合は、.NET Core インストーラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-142">If you want registry key values to be updated, use the .NET Core installers.</span></span>

## <a name="options"></a><span data-ttu-id="dbc6b-143">オプション</span><span class="sxs-lookup"><span data-stu-id="dbc6b-143">Options</span></span>

- **`-Architecture|--architecture <ARCHITECTURE>`**

  <span data-ttu-id="dbc6b-144">インストールする .NET Core バイナリのアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-144">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="dbc6b-145">指定できる値は、`<auto>`、`amd64`、`x64`、`x86`、`arm64`、および `arm` です。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-145">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="dbc6b-146">既定値は `<auto>` です。これは実行中の OS アーキテクチャを示します。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-146">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-AzureFeed|--azure-feed`**

  <span data-ttu-id="dbc6b-147">Azure フィードの URL をインストーラーに指定します。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-147">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="dbc6b-148">この値は変更しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-148">We recommended that you don't change this value.</span></span> <span data-ttu-id="dbc6b-149">既定値は `https://dotnetcli.azureedge.net/dotnet` です。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-149">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-Channel|--channel <CHANNEL>`**

  <span data-ttu-id="dbc6b-150">インストールのソース チャネルを指定します。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-150">Specifies the source channel for the installation.</span></span> <span data-ttu-id="dbc6b-151">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-151">The possible values are:</span></span>

  - <span data-ttu-id="dbc6b-152">`Current` - 最新リリース。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-152">`Current` - Most current release.</span></span>
  - <span data-ttu-id="dbc6b-153">`LTS` - 長期的なサポート チャネル (サポートされている最新リリース)。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-153">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="dbc6b-154">特定のリリースを表す X.Y 形式の 2 部構成のバージョン (たとえば、`2.1` または `3.0`)。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-154">Two-part version in X.Y format representing a specific release (for example, `2.1` or `3.0`).</span></span>
  - <span data-ttu-id="dbc6b-155">ブランチ名: たとえば、`release/3.1.1xx` または `master` (夜間リリース用)</span><span class="sxs-lookup"><span data-stu-id="dbc6b-155">Branch name: for example, `release/3.1.1xx` or `master` (for nightly releases).</span></span> <span data-ttu-id="dbc6b-156">プレビュー チャネルからバージョンをインストールするには、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-156">Use this option to install a version from a preview channel.</span></span> <span data-ttu-id="dbc6b-157">「[インストーラーとバイナリ](https://github.com/dotnet/core-sdk#installers-and-binaries)」に記載されているチャネルの名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-157">Use the name of the channel as listed in [Installers and Binaries](https://github.com/dotnet/core-sdk#installers-and-binaries).</span></span>

  <span data-ttu-id="dbc6b-158">既定値は `LTS` です。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-158">The default value is `LTS`.</span></span> <span data-ttu-id="dbc6b-159">.NET のサポート チャネルの詳細については、「[.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)」(.NET のサポート ポリシー) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-159">For more information on .NET support channels, see the [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) page.</span></span>

- **`-DryRun|--dry-run`**

  <span data-ttu-id="dbc6b-160">設定すると、スクリプトでインストールは実行されません。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-160">If set, the script won't perform the installation.</span></span> <span data-ttu-id="dbc6b-161">代わりに、現在要求されているバージョンの .NET Core CLI を一貫してインストールするために使用するコマンド ラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-161">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="dbc6b-162">たとえば、バージョン `latest` を指定すると、そのバージョンのリンクが表示されるので、ビルド スクリプトで確定的にこのコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-162">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="dbc6b-163">また、自分でインストールまたはダウンロードしたい場合、バイナリの場所も表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-163">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-FeedCredential|--feed-credential`**

  <span data-ttu-id="dbc6b-164">Azure フィードに付加するクエリ文字列として使用されます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-164">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="dbc6b-165">非公開の BLOB ストレージ アカウントを使用するように URL を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-165">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`--help`**

  <span data-ttu-id="dbc6b-166">スクリプトのヘルプを出力します。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-166">Prints out help for the script.</span></span> <span data-ttu-id="dbc6b-167">bash スクリプトのみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-167">Applies only to bash script.</span></span> <span data-ttu-id="dbc6b-168">PowerShell の場合、`Get-Help ./dotnet-install.ps1` を使用します。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-168">For PowerShell, use `Get-Help ./dotnet-install.ps1`.</span></span>

- **`-InstallDir|--install-dir <DIRECTORY>`**

  <span data-ttu-id="dbc6b-169">インストール パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-169">Specifies the installation path.</span></span> <span data-ttu-id="dbc6b-170">存在しない場合は、ディレクトリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-170">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="dbc6b-171">既定値は、 *%LocalAppData%\Microsoft\dotnet* (Windows) または */usr/share/dotnet* (Linux と macOS) です。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-171">The default value is *%LocalAppData%\Microsoft\dotnet* on Windows and */usr/share/dotnet* on Linux/macOS.</span></span> <span data-ttu-id="dbc6b-172">バイナリは、このディレクトリに直接配置されます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-172">Binaries are placed directly in this directory.</span></span>

- **`-JSonFile|--jsonfile <JSONFILE>`**

  <span data-ttu-id="dbc6b-173">SDK バージョンを決定するために使用される [global.json](global-json.md) ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-173">Specifies a path to a [global.json](global-json.md) file that will be used to determine the SDK version.</span></span> <span data-ttu-id="dbc6b-174">*global.json* ファイルには `sdk:version` の値が必要です。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-174">The *global.json* file must have a value for `sdk:version`.</span></span>

- **`-NoCdn|--no-cdn`**

  <span data-ttu-id="dbc6b-175">[Azure Content Delivery Network (CDN)](/azure/cdn/cdn-overview) からのダウンロードを無効にし、キャッシュされていないフィードを直接使用します。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-175">Disables downloading from the [Azure Content Delivery Network (CDN)](/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-NoPath|--no-path`**

  <span data-ttu-id="dbc6b-176">設定すると、インストール フォルダーは現在のセッションのパスにはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-176">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="dbc6b-177">既定では、スクリプトによって PATH が変更されます。これにより、インストール後すぐに .NET Core CLI を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-177">By default, the script modifies the PATH, which makes the .NET Core CLI available immediately after install.</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="dbc6b-178">設定すると、インストーラーで Web 要求を行うときにプロキシが使われます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-178">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="dbc6b-179">(Windows でのみ有効)。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-179">(Only valid for Windows.)</span></span>

- **`-ProxyBypassList <LIST_OF_URLS>`**

  <span data-ttu-id="dbc6b-180">`ProxyAddress` で設定されている場合、プロキシをバイパスする URL をコンマ区切りの一覧で提供します。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-180">If set with `ProxyAddress`, provides a list of comma-separated urls that will bypass the proxy.</span></span> <span data-ttu-id="dbc6b-181">(Windows でのみ有効)。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-181">(Only valid for Windows.)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="dbc6b-182">設定すると、プロキシ アドレスの使用時に、インストーラーでは現在のユーザーの資格情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-182">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="dbc6b-183">(Windows でのみ有効)。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-183">(Only valid for Windows.)</span></span>

- **`-Runtime|--runtime <RUNTIME>`**

  <span data-ttu-id="dbc6b-184">SDK 全体ではなく共有ランタイムのみがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-184">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="dbc6b-185">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-185">The possible values are:</span></span>

  - <span data-ttu-id="dbc6b-186">`dotnet` - `Microsoft.NETCore.App` 共有ランタイム。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-186">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="dbc6b-187">`aspnetcore` - `Microsoft.AspNetCore.App` 共有ランタイム。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-187">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>
  - <span data-ttu-id="dbc6b-188">`windowsdesktop` - `Microsoft.WindowsDesktop.App` 共有ランタイム。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-188">`windowsdesktop` - the `Microsoft.WindowsDesktop.App` shared runtime.</span></span>

- **`--runtime-id <RID>`**

  <span data-ttu-id="dbc6b-189">ツールのインストール先の[ランタイム識別子](../rid-catalog.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-189">Specifies the [runtime identifier](../rid-catalog.md) for which the tools are being installed.</span></span> <span data-ttu-id="dbc6b-190">Portable Linux には `linux-x64` を使用します。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-190">Use `linux-x64` for portable Linux.</span></span> <span data-ttu-id="dbc6b-191">(Linux または macOS でのみ有効)。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-191">(Only valid for Linux/macOS.)</span></span>

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > <span data-ttu-id="dbc6b-192">このパラメーターは非推奨であり、今後のバージョンのスクリプトでは削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-192">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="dbc6b-193">別の方法として、`-Runtime|--runtime` オプションを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-193">The recommended alternative is the `-Runtime|--runtime` option.</span></span>

  <span data-ttu-id="dbc6b-194">SDK 全体ではなく共有ランタイム ビットのみがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-194">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="dbc6b-195">このオプションは、`-Runtime|--runtime dotnet` を指定することと同じです。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-195">This option is equivalent to specifying `-Runtime|--runtime dotnet`.</span></span>

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  <span data-ttu-id="dbc6b-196">*dotnet.exe* など、バージョン管理されていないファイルが既に存在する場合は、そのインストールをスキップします。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-196">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-UncachedFeed|--uncached-feed`**

  <span data-ttu-id="dbc6b-197">このインストーラーで使用されている、キャッシュされていないフィードの URL を変更することを許可します。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-197">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="dbc6b-198">この値は変更しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-198">We recommended that you don't change this value.</span></span>

- **`-Verbose|--verbose`**

  <span data-ttu-id="dbc6b-199">診断情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-199">Displays diagnostics information.</span></span>

- **`-Version|--version <VERSION>`**

  <span data-ttu-id="dbc6b-200">特定のビルド バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-200">Represents a specific build version.</span></span> <span data-ttu-id="dbc6b-201">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-201">The possible values are:</span></span>

  - <span data-ttu-id="dbc6b-202">`latest` - チャネルの最新ビルド (`-Channel` オプションで使用)。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-202">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="dbc6b-203">`coherent` - チャネルの最新のコヒーレント ビルド。最新の安定版パッケージの組み合わせを使用します (ブランチ名の `-Channel` オプションで使用)。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-203">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  - <span data-ttu-id="dbc6b-204">特定のビルド バージョンを表す X.Y.Z 形式の 3 部構成のバージョン。`-Channel` オプションよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-204">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="dbc6b-205">たとえば、`2.0.0-preview2-006120` のように指定します。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-205">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="dbc6b-206">指定しない場合、`-Version` の既定値は `latest` です。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-206">If not specified, `-Version` defaults to `latest`.</span></span>

## <a name="examples"></a><span data-ttu-id="dbc6b-207">使用例</span><span class="sxs-lookup"><span data-stu-id="dbc6b-207">Examples</span></span>

- <span data-ttu-id="dbc6b-208">最新の長期サポート (LST) バージョンを既定の場所にインストールします。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-208">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="dbc6b-209">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="dbc6b-209">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="dbc6b-210">macOS/Linux の場合:</span><span class="sxs-lookup"><span data-stu-id="dbc6b-210">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="dbc6b-211">3\.1 チャネルから、最新バージョンを指定した場所にインストールします。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-211">Install the latest version from 3.1 channel to the specified location:</span></span>

  <span data-ttu-id="dbc6b-212">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="dbc6b-212">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 3.1 -InstallDir C:\cli
  ```

  <span data-ttu-id="dbc6b-213">macOS/Linux の場合:</span><span class="sxs-lookup"><span data-stu-id="dbc6b-213">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 3.1 --install-dir ~/cli
  ```

- <span data-ttu-id="dbc6b-214">共有ランタイムの 3.0.0 バージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-214">Install the 3.0.0 version of the shared runtime:</span></span>

  <span data-ttu-id="dbc6b-215">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="dbc6b-215">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 3.0.0
  ```

  <span data-ttu-id="dbc6b-216">macOS/Linux の場合:</span><span class="sxs-lookup"><span data-stu-id="dbc6b-216">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 3.0.0
  ```

- <span data-ttu-id="dbc6b-217">スクリプトを入手し、会社のプロキシの背後に 2.1.2 バージョンをインストールします (Windows のみ)。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-217">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="dbc6b-218">スクリプトを入手し、.NET Core CLI の 1 行コードのサンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="dbc6b-218">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="dbc6b-219">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="dbc6b-219">Windows:</span></span>

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="dbc6b-220">macOS/Linux の場合:</span><span class="sxs-lookup"><span data-stu-id="dbc6b-220">macOS/Linux:</span></span>

  ```bash
  curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="dbc6b-221">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbc6b-221">See also</span></span>

- [<span data-ttu-id="dbc6b-222">.NET Core のリリース</span><span class="sxs-lookup"><span data-stu-id="dbc6b-222">.NET Core releases</span></span>](https://github.com/dotnet/core/releases)
- [<span data-ttu-id="dbc6b-223">.NET Core ランタイムと SDK ダウンロード アーカイブ</span><span class="sxs-lookup"><span data-stu-id="dbc6b-223">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
