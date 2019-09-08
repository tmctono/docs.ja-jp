---
title: dotnet-install スクリプト
description: .NET Core CLI ツールと共有ランタイムをインストールする dotnet-install スクリプトについて説明します。
ms.date: 01/16/2019
ms.openlocfilehash: ed1a3341e678b405ae4aca35e3b49ada89eb069a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253900"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="8fa9f-103">dotnet-install スクリプト参照</span><span class="sxs-lookup"><span data-stu-id="8fa9f-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="8fa9f-104">name</span><span class="sxs-lookup"><span data-stu-id="8fa9f-104">Name</span></span>

<span data-ttu-id="8fa9f-105">`dotnet-install.ps1` | `dotnet-install.sh` - .NET Core CLI ツールと共有ランタイムをインストールするために使うスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core CLI tools and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8fa9f-106">構文</span><span class="sxs-lookup"><span data-stu-id="8fa9f-106">Synopsis</span></span>

<span data-ttu-id="8fa9f-107">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="8fa9f-107">Windows:</span></span>

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-Runtime] [-DryRun] [-NoPath] [-Verbose] [-AzureFeed] [-UncachedFeed] [-NoCdn] [-FeedCredential] [-ProxyAddress] [-ProxyUseDefaultCredentials] [-SkipNonVersionedFiles] [-Help]`

<span data-ttu-id="8fa9f-108">macOS/Linux の場合:</span><span class="sxs-lookup"><span data-stu-id="8fa9f-108">macOS/Linux:</span></span>

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--runtime] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--uncached-feed] [--no-cdn] [--feed-credential] [--runtime-id] [--skip-non-versioned-files] [--help]`

## <a name="description"></a><span data-ttu-id="8fa9f-109">説明</span><span class="sxs-lookup"><span data-stu-id="8fa9f-109">Description</span></span>

<span data-ttu-id="8fa9f-110">`dotnet-install` スクリプトは、.NET Core CLI ツールや共有ランタイムが含まれる .NET Core SDK の非管理者インストールを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI tools and the shared runtime.</span></span>

<span data-ttu-id="8fa9f-111">[.NET Core のメインの Web サイト](https://dot.net)でホストされる安定したバージョンを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-111">We recommend that you use the stable version that is hosted on [.NET Core main website](https://dot.net).</span></span> <span data-ttu-id="8fa9f-112">スクリプトへの直接パスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-112">The direct paths to the scripts are:</span></span>

- <span data-ttu-id="8fa9f-113"><https://dot.net/v1/dotnet-install.sh> (Bash、UNIX)</span><span class="sxs-lookup"><span data-stu-id="8fa9f-113"><https://dot.net/v1/dotnet-install.sh> (bash, UNIX)</span></span>
- <span data-ttu-id="8fa9f-114"><https://dot.net/v1/dotnet-install.ps1> (PowerShell、Windows)</span><span class="sxs-lookup"><span data-stu-id="8fa9f-114"><https://dot.net/v1/dotnet-install.ps1> (Powershell, Windows)</span></span>

<span data-ttu-id="8fa9f-115">これらのスクリプトの主な有用性は、オートメーションのシナリオと管理者以外のインストールにおいてです。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-115">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="8fa9f-116">2 つのスクリプトがあります。1 つは Windows 上で動作する PowerShell スクリプトで、もう 1 つは Linux/macOS 上で動作する bash スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-116">There are two scripts: one is a PowerShell script that works on Windows, and the other is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="8fa9f-117">スクリプトの動作は両方とも同じです。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-117">Both scripts have the same behavior.</span></span> <span data-ttu-id="8fa9f-118">bash スクリプトは PowerShell のスイッチも読み取るので、Linux/macOS システムのスクリプトで PowerShell のスイッチを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-118">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

<span data-ttu-id="8fa9f-119">インストール スクリプトは CLI ビルド ドロップから ZIP/tarball ファイルをダウンロードし、既定の場所または `-InstallDir|--install-dir` で指定された場所へのインストールに進みます。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-119">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="8fa9f-120">既定では、インストール スクリプトは SDK をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-120">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="8fa9f-121">共有ランタイムの取得だけを行いたい場合は、`--runtime` 引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-121">If you wish to only obtain the shared runtime, specify the `--runtime` argument.</span></span>

<span data-ttu-id="8fa9f-122">既定では、スクリプトはインストールの場所を現在のセッションの $PATH に追加します。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-122">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="8fa9f-123">`--no-path` 引数を指定することによってこの既定の動作をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-123">Override this default behavior by specifying the `--no-path` argument.</span></span>

<span data-ttu-id="8fa9f-124">スクリプトを実行する前に、必要な[依存関係](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md)をすべてインストールします。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-124">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

<span data-ttu-id="8fa9f-125">`--version` 引数を使用して、特定のバージョンをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-125">You can install a specific version using the `--version` argument.</span></span> <span data-ttu-id="8fa9f-126">バージョンは 3 つの部分からなるバージョン (1.0.0-13232 など) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-126">The version must be specified as a three-part version (for example, 1.0.0-13232).</span></span> <span data-ttu-id="8fa9f-127">指定しない場合は、`latest` バージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-127">If not provided, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="8fa9f-128">オプション</span><span class="sxs-lookup"><span data-stu-id="8fa9f-128">Options</span></span>

- **`-Channel <CHANNEL>`**

  <span data-ttu-id="8fa9f-129">インストールのソース チャネルを指定します。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-129">Specifies the source channel for the installation.</span></span> <span data-ttu-id="8fa9f-130">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-130">The possible values are:</span></span>

  - <span data-ttu-id="8fa9f-131">`Current` - 最新リリース。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-131">`Current` - Most current release.</span></span>
  - <span data-ttu-id="8fa9f-132">`LTS` - 長期的なサポート チャネル (サポートされている最新リリース)。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-132">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="8fa9f-133">特定のリリースを表す X.Y 形式の 2 部構成のバージョン (たとえば、`2.0` または `1.0`)。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-133">Two-part version in X.Y format representing a specific release (for example, `2.0` or `1.0`).</span></span>
  - <span data-ttu-id="8fa9f-134">ブランチ名。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-134">Branch name.</span></span> <span data-ttu-id="8fa9f-135">たとえば、`release/2.0.0`、`release/2.0.0-preview2`、`master` (夜間リリース用)</span><span class="sxs-lookup"><span data-stu-id="8fa9f-135">For example, `release/2.0.0`, `release/2.0.0-preview2`, or `master` (for nightly releases).</span></span>

  <span data-ttu-id="8fa9f-136">既定値は `LTS` です。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-136">The default value is `LTS`.</span></span> <span data-ttu-id="8fa9f-137">.NET のサポート チャネルの詳細については、「[.NET Support Policy](https://www.microsoft.com/net/platform/support-policy#dotnet-core)」(.NET のサポート ポリシー) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-137">For more information on .NET support channels, see the [.NET Support Policy](https://www.microsoft.com/net/platform/support-policy#dotnet-core) page.</span></span>

- **`-Version <VERSION>`**

  <span data-ttu-id="8fa9f-138">特定のビルド バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-138">Represents a specific build version.</span></span> <span data-ttu-id="8fa9f-139">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-139">The possible values are:</span></span>

  - <span data-ttu-id="8fa9f-140">`latest` - チャネルの最新ビルド (`-Channel` オプションで使用)。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-140">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="8fa9f-141">`coherent` - チャネルの最新のコヒーレント ビルド。最新の安定版パッケージの組み合わせを使用します (ブランチ名の `-Channel` オプションで使用)。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-141">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  - <span data-ttu-id="8fa9f-142">特定のビルド バージョンを表す X.Y.Z 形式の 3 部構成のバージョン。`-Channel` オプションよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-142">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="8fa9f-143">たとえば、`2.0.0-preview2-006120` のように指定します。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-143">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="8fa9f-144">指定しない場合、`-Version` の既定値は `latest` です。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-144">If not specified, `-Version` defaults to `latest`.</span></span>

- **`-InstallDir <DIRECTORY>`**

  <span data-ttu-id="8fa9f-145">インストール パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-145">Specifies the installation path.</span></span> <span data-ttu-id="8fa9f-146">存在しない場合は、ディレクトリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-146">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="8fa9f-147">既定値は *%LocalAppData%\Microsoft\dotnet*です。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-147">The default value is *%LocalAppData%\Microsoft\dotnet*.</span></span> <span data-ttu-id="8fa9f-148">バイナリは、このディレクトリに直接配置されます。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-148">Binaries are placed directly in this directory.</span></span>

- **`-Architecture <ARCHITECTURE>`**

  <span data-ttu-id="8fa9f-149">インストールする .NET Core バイナリのアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-149">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="8fa9f-150">指定できる値は、`<auto>`、`amd64`、`x64`、`x86`、`arm64`、および `arm` です。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-150">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="8fa9f-151">既定値は `<auto>` です。これは実行中の OS アーキテクチャを示します。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-151">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-SharedRuntime`**

  > [!NOTE]
  > <span data-ttu-id="8fa9f-152">このパラメーターは非推奨であり、今後のバージョンのスクリプトでは削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-152">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="8fa9f-153">別の方法として、`Runtime` オプションを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-153">The recommended alternative is the `Runtime` option.</span></span>

  <span data-ttu-id="8fa9f-154">SDK 全体ではなく共有ランタイム ビットのみがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-154">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="8fa9f-155">これは、`-Runtime dotnet` を指定することと同じです。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-155">This is equivalent to specifying `-Runtime dotnet`.</span></span>

- **`-Runtime <RUNTIME>`**

  <span data-ttu-id="8fa9f-156">SDK 全体ではなく共有ランタイムのみがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-156">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="8fa9f-157">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-157">The possible values are:</span></span>

  - <span data-ttu-id="8fa9f-158">`dotnet` - `Microsoft.NETCore.App` 共有ランタイム。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-158">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="8fa9f-159">`aspnetcore` - `Microsoft.AspNetCore.App` 共有ランタイム。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-159">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>

- **`-DryRun`**

  <span data-ttu-id="8fa9f-160">設定すると、スクリプトでインストールは実行されません。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-160">If set, the script won't perform the installation.</span></span> <span data-ttu-id="8fa9f-161">代わりに、現在要求されているバージョンの .NET Core CLI を一貫してインストールするために使用するコマンド ラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-161">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="8fa9f-162">たとえば、バージョン `latest` を指定すると、そのバージョンのリンクが表示されるので、ビルド スクリプトで確定的にこのコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-162">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="8fa9f-163">また、自分でインストールまたはダウンロードしたい場合、バイナリの場所も表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-163">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-NoPath`**

  <span data-ttu-id="8fa9f-164">設定すると、インストール フォルダーは現在のセッションのパスにはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-164">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="8fa9f-165">既定では、スクリプトによって PATH が変更されます。その結果、インストール後すぐに CLI ツールを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-165">By default, the script modifies the PATH, which makes the CLI tools available immediately after install.</span></span>

- **`-Verbose`**

  <span data-ttu-id="8fa9f-166">診断情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-166">Displays diagnostics information.</span></span>

- **`-AzureFeed`**

  <span data-ttu-id="8fa9f-167">Azure フィードの URL をインストーラーに指定します。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-167">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="8fa9f-168">この値は変更しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-168">We recommended that you don't change this value.</span></span> <span data-ttu-id="8fa9f-169">既定値は `https://dotnetcli.azureedge.net/dotnet` です。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-169">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-UncachedFeed`**

  <span data-ttu-id="8fa9f-170">このインストーラーで使用されている、キャッシュされていないフィードの URL を変更することを許可します。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-170">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="8fa9f-171">この値は変更しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-171">We recommended that you don't change this value.</span></span>

- **`-NoCdn`**

  <span data-ttu-id="8fa9f-172">[Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) からのダウンロードを無効にし、キャッシュされていないフィードを直接使用します。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-172">Disables downloading from the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-FeedCredential`**

  <span data-ttu-id="8fa9f-173">Azure フィードに付加するクエリ文字列として使用されます。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-173">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="8fa9f-174">非公開の BLOB ストレージ アカウントを使用するように URL を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-174">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="8fa9f-175">設定すると、インストーラーで Web 要求を行うときにプロキシが使われます。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-175">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="8fa9f-176">(Windows でのみ有効)</span><span class="sxs-lookup"><span data-stu-id="8fa9f-176">(Only valid for Windows)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="8fa9f-177">設定すると、プロキシ アドレスの使用時に、インストーラーでは現在のユーザーの資格情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-177">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="8fa9f-178">(Windows でのみ有効)</span><span class="sxs-lookup"><span data-stu-id="8fa9f-178">(Only valid for Windows)</span></span>

- **`-SkipNonVersionedFiles`**

  <span data-ttu-id="8fa9f-179">*dotnet.exe* など、バージョン管理されていないファイルが既に存在する場合は、そのインストールをスキップします。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-179">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-Help`**

  <span data-ttu-id="8fa9f-180">スクリプトのヘルプを出力します。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-180">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="8fa9f-181">使用例</span><span class="sxs-lookup"><span data-stu-id="8fa9f-181">Examples</span></span>

- <span data-ttu-id="8fa9f-182">最新の長期サポート (LST) バージョンを既定の場所にインストールします。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-182">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="8fa9f-183">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="8fa9f-183">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="8fa9f-184">macOS/Linux の場合:</span><span class="sxs-lookup"><span data-stu-id="8fa9f-184">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="8fa9f-185">2\.0 チャネルから、最新バージョンを指定した場所にインストールします。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-185">Install the latest version from 2.0 channel to the specified location:</span></span>

  <span data-ttu-id="8fa9f-186">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="8fa9f-186">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli
  ```

  <span data-ttu-id="8fa9f-187">macOS/Linux の場合:</span><span class="sxs-lookup"><span data-stu-id="8fa9f-187">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 2.0 --install-dir ~/cli
  ```

- <span data-ttu-id="8fa9f-188">共有ランタイムの 1.1.0 バージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-188">Install the 1.1.0 version of the shared runtime:</span></span>

  <span data-ttu-id="8fa9f-189">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="8fa9f-189">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 1.1.0
  ```

  <span data-ttu-id="8fa9f-190">macOS/Linux の場合:</span><span class="sxs-lookup"><span data-stu-id="8fa9f-190">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 1.1.0
  ```

- <span data-ttu-id="8fa9f-191">スクリプトを入手し、会社のプロキシの背後に 2.1.2 バージョンをインストールします (Windows のみ)。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-191">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="8fa9f-192">スクリプトを入手し、.NET Core CLI の 1 行コードのサンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8fa9f-192">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="8fa9f-193">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="8fa9f-193">Windows:</span></span>

  ```powershell
  @powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="8fa9f-194">macOS/Linux の場合:</span><span class="sxs-lookup"><span data-stu-id="8fa9f-194">macOS/Linux:</span></span>

  ```bash
  curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="8fa9f-195">関連項目</span><span class="sxs-lookup"><span data-stu-id="8fa9f-195">See also</span></span>

- [<span data-ttu-id="8fa9f-196">.NET Core のリリース</span><span class="sxs-lookup"><span data-stu-id="8fa9f-196">.NET Core releases</span></span>](https://github.com/dotnet/core/releases)
- [<span data-ttu-id="8fa9f-197">.NET Core ランタイムと SDK ダウンロード アーカイブ</span><span class="sxs-lookup"><span data-stu-id="8fa9f-197">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
