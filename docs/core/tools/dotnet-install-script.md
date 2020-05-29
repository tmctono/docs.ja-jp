---
title: dotnet-install スクリプト
description: .NET Core SDK と共有ランタイムをインストールするための dotnet-install スクリプトについて学習します。
ms.date: 04/30/2020
ms.openlocfilehash: 9f5cef9cfcca1d8b344021efe803c063a7393f8e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802725"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="51db1-103">dotnet-install スクリプト リファレンス</span><span class="sxs-lookup"><span data-stu-id="51db1-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="51db1-104">名前</span><span class="sxs-lookup"><span data-stu-id="51db1-104">Name</span></span>

<span data-ttu-id="51db1-105">`dotnet-install.ps1` | `dotnet-install.sh` - .NET Core SDK と共有ランタイムをインストールするために使うスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="51db1-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core SDK and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="51db1-106">構文</span><span class="sxs-lookup"><span data-stu-id="51db1-106">Synopsis</span></span>

<span data-ttu-id="51db1-107">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="51db1-107">Windows:</span></span>

```powershell
dotnet-install.ps1 [-Architecture <ARCHITECTURE>] [-AzureFeed]
    [-Channel <CHANNEL>] [-DryRun] [-FeedCredential]
    [-InstallDir <DIRECTORY>] [-JSonFile <JSONFILE>]
    [-NoCdn] [-NoPath] [-ProxyAddress]
    [-ProxyUseDefaultCredentials] [-Runtime <RUNTIME>]
    [-SkipNonVersionedFiles] [-UncachedFeed] [-Verbose]
    [-Version <VERSION>]

dotnet-install.ps1 -Help
```

<span data-ttu-id="51db1-108">Linux/macOS:</span><span class="sxs-lookup"><span data-stu-id="51db1-108">Linux/macOS:</span></span>

```bash
dotnet-install.sh  [--architecture <ARCHITECTURE>] [--azure-feed]
    [--channel <CHANNEL>] [--dry-run] [--feed-credential]
    [--install-dir <DIRECTORY>] [--jsonfile <JSONFILE>]
    [--no-cdn] [--no-path] [--runtime <RUNTIME>] [--runtime-id <RID>]
    [--skip-non-versioned-files] [--uncached-feed] [--verbose]
    [--version <VERSION>]

dotnet-install.sh --help
```

## <a name="description"></a><span data-ttu-id="51db1-109">説明</span><span class="sxs-lookup"><span data-stu-id="51db1-109">Description</span></span>

<span data-ttu-id="51db1-110">`dotnet-install` スクリプトは、.NET Core CLI や共有ランタイムを含む .NET Core SDK の非管理者インストールを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="51db1-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI and the shared runtime.</span></span>

<span data-ttu-id="51db1-111">安定したバージョンのスクリプトを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="51db1-111">We recommend that you use the stable version of the scripts:</span></span>

- <span data-ttu-id="51db1-112">Bash (Linux、macOS): <https://dot.net/v1/dotnet-install.sh></span><span class="sxs-lookup"><span data-stu-id="51db1-112">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span></span>
- <span data-ttu-id="51db1-113">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span><span class="sxs-lookup"><span data-stu-id="51db1-113">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span></span>

<span data-ttu-id="51db1-114">これらのスクリプトの主な有用性は、オートメーションのシナリオと管理者以外のインストールにおいてです。</span><span class="sxs-lookup"><span data-stu-id="51db1-114">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="51db1-115">2 つのスクリプトがあります。1 つは Windows 上で動作する PowerShell スクリプトで、もう 1 つは Linux/macOS 上で動作する bash スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="51db1-115">There are two scripts: one is a PowerShell script that works on Windows, and the other is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="51db1-116">スクリプトの動作は両方とも同じです。</span><span class="sxs-lookup"><span data-stu-id="51db1-116">Both scripts have the same behavior.</span></span> <span data-ttu-id="51db1-117">bash スクリプトは PowerShell のスイッチも読み取るので、Linux/macOS システムのスクリプトで PowerShell のスイッチを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="51db1-117">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

<span data-ttu-id="51db1-118">インストール スクリプトは CLI ビルド ドロップから ZIP/tarball ファイルをダウンロードし、既定の場所または `-InstallDir|--install-dir` で指定された場所へのインストールに進みます。</span><span class="sxs-lookup"><span data-stu-id="51db1-118">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="51db1-119">既定では、インストール スクリプトは SDK をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="51db1-119">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="51db1-120">共有ランタイムの取得だけを行いたい場合は、`-Runtime|--runtime` 引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="51db1-120">If you wish to only obtain the shared runtime, specify the `-Runtime|--runtime` argument.</span></span>

<span data-ttu-id="51db1-121">既定では、スクリプトはインストールの場所を現在のセッションの $PATH に追加します。</span><span class="sxs-lookup"><span data-stu-id="51db1-121">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="51db1-122">`-NoPath|--no-path` 引数を指定することによってこの既定の動作をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="51db1-122">Override this default behavior by specifying the `-NoPath|--no-path` argument.</span></span>

<span data-ttu-id="51db1-123">スクリプトを実行する前に、必要な[依存関係](../install/dependencies.md)をすべてインストールします。</span><span class="sxs-lookup"><span data-stu-id="51db1-123">Before running the script, install the required [dependencies](../install/dependencies.md).</span></span>

<span data-ttu-id="51db1-124">`-Version|--version` 引数を使用して、特定のバージョンをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="51db1-124">You can install a specific version using the `-Version|--version` argument.</span></span> <span data-ttu-id="51db1-125">バージョンは 3 つの部分からなるバージョン (`2.1.0` など) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51db1-125">The version must be specified as a three-part version (for example, `2.1.0`).</span></span> <span data-ttu-id="51db1-126">指定しない場合は、`latest` バージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="51db1-126">If not provided, it uses the `latest` version.</span></span>

<span data-ttu-id="51db1-127">インストール スクリプトでは、Windows 上のレジストリは更新されません。</span><span class="sxs-lookup"><span data-stu-id="51db1-127">The install scripts do not update the registry on Windows.</span></span> <span data-ttu-id="51db1-128">zip 形式のバイナリがダウンロードされて、フォルダーにコピーされるだけです。</span><span class="sxs-lookup"><span data-stu-id="51db1-128">They just download the zipped binaries and copy them to a folder.</span></span> <span data-ttu-id="51db1-129">レジストリ キーの値を更新する必要がある場合は、.NET Core インストーラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="51db1-129">If you want registry key values to be updated, use the .NET Core installers.</span></span>

## <a name="options"></a><span data-ttu-id="51db1-130">オプション</span><span class="sxs-lookup"><span data-stu-id="51db1-130">Options</span></span>

- **`-Architecture|--architecture <ARCHITECTURE>`**

  <span data-ttu-id="51db1-131">インストールする .NET Core バイナリのアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="51db1-131">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="51db1-132">指定できる値は、`<auto>`、`amd64`、`x64`、`x86`、`arm64`、および `arm` です。</span><span class="sxs-lookup"><span data-stu-id="51db1-132">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="51db1-133">既定値は `<auto>` です。これは実行中の OS アーキテクチャを示します。</span><span class="sxs-lookup"><span data-stu-id="51db1-133">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-AzureFeed|--azure-feed`**

  <span data-ttu-id="51db1-134">Azure フィードの URL をインストーラーに指定します。</span><span class="sxs-lookup"><span data-stu-id="51db1-134">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="51db1-135">この値は変更しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="51db1-135">We recommended that you don't change this value.</span></span> <span data-ttu-id="51db1-136">既定値は `https://dotnetcli.azureedge.net/dotnet` です。</span><span class="sxs-lookup"><span data-stu-id="51db1-136">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-Channel|--channel <CHANNEL>`**

  <span data-ttu-id="51db1-137">インストールのソース チャネルを指定します。</span><span class="sxs-lookup"><span data-stu-id="51db1-137">Specifies the source channel for the installation.</span></span> <span data-ttu-id="51db1-138">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="51db1-138">The possible values are:</span></span>

  - <span data-ttu-id="51db1-139">`Current` - 最新リリース。</span><span class="sxs-lookup"><span data-stu-id="51db1-139">`Current` - Most current release.</span></span>
  - <span data-ttu-id="51db1-140">`LTS` - 長期的なサポート チャネル (サポートされている最新リリース)。</span><span class="sxs-lookup"><span data-stu-id="51db1-140">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="51db1-141">特定のリリースを表す X.Y 形式の 2 部構成のバージョン (たとえば、`2.1` または `3.0`)。</span><span class="sxs-lookup"><span data-stu-id="51db1-141">Two-part version in X.Y format representing a specific release (for example, `2.1` or `3.0`).</span></span>
  - <span data-ttu-id="51db1-142">ブランチ名: たとえば、`release/3.1.1xx` または `master` (夜間リリース用)</span><span class="sxs-lookup"><span data-stu-id="51db1-142">Branch name: for example, `release/3.1.1xx` or `master` (for nightly releases).</span></span> <span data-ttu-id="51db1-143">プレビュー チャネルからバージョンをインストールするには、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="51db1-143">Use this option to install a version from a preview channel.</span></span> <span data-ttu-id="51db1-144">「[インストーラーとバイナリ](https://github.com/dotnet/core-sdk#installers-and-binaries)」に記載されているチャネルの名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="51db1-144">Use the name of the channel as listed in [Installers and Binaries](https://github.com/dotnet/core-sdk#installers-and-binaries).</span></span>

  <span data-ttu-id="51db1-145">既定値は `LTS` です。</span><span class="sxs-lookup"><span data-stu-id="51db1-145">The default value is `LTS`.</span></span> <span data-ttu-id="51db1-146">.NET のサポート チャネルの詳細については、「[.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)」(.NET のサポート ポリシー) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="51db1-146">For more information on .NET support channels, see the [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) page.</span></span>

- **`-DryRun|--dry-run`**

  <span data-ttu-id="51db1-147">設定すると、スクリプトでインストールは実行されません。</span><span class="sxs-lookup"><span data-stu-id="51db1-147">If set, the script won't perform the installation.</span></span> <span data-ttu-id="51db1-148">代わりに、現在要求されているバージョンの .NET Core CLI を一貫してインストールするために使用するコマンド ラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51db1-148">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="51db1-149">たとえば、バージョン `latest` を指定すると、そのバージョンのリンクが表示されるので、ビルド スクリプトで確定的にこのコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="51db1-149">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="51db1-150">また、自分でインストールまたはダウンロードしたい場合、バイナリの場所も表示されます。</span><span class="sxs-lookup"><span data-stu-id="51db1-150">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-FeedCredential|--feed-credential`**

  <span data-ttu-id="51db1-151">Azure フィードに付加するクエリ文字列として使用されます。</span><span class="sxs-lookup"><span data-stu-id="51db1-151">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="51db1-152">非公開の BLOB ストレージ アカウントを使用するように URL を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="51db1-152">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`-Help|--help`**

  <span data-ttu-id="51db1-153">スクリプトのヘルプを出力します。</span><span class="sxs-lookup"><span data-stu-id="51db1-153">Prints out help for the script.</span></span>

- **`-InstallDir|--install-dir <DIRECTORY>`**

  <span data-ttu-id="51db1-154">インストール パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="51db1-154">Specifies the installation path.</span></span> <span data-ttu-id="51db1-155">存在しない場合は、ディレクトリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="51db1-155">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="51db1-156">既定値は、 *%LocalAppData%\Microsoft\dotnet* (Windows) または */usr/share/dotnet* (Linux と macOS) です。</span><span class="sxs-lookup"><span data-stu-id="51db1-156">The default value is *%LocalAppData%\Microsoft\dotnet* on Windows and */usr/share/dotnet* on Linux/macOS.</span></span> <span data-ttu-id="51db1-157">バイナリは、このディレクトリに直接配置されます。</span><span class="sxs-lookup"><span data-stu-id="51db1-157">Binaries are placed directly in this directory.</span></span>

- **`-JSonFile|--jsonfile <JSONFILE>`**

  <span data-ttu-id="51db1-158">SDK バージョンを決定するために使用される [global.json](global-json.md) ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="51db1-158">Specifies a path to a [global.json](global-json.md) file that will be used to determine the SDK version.</span></span> <span data-ttu-id="51db1-159">*global.json* ファイルには `sdk:version` の値が必要です。</span><span class="sxs-lookup"><span data-stu-id="51db1-159">The *global.json* file must have a value for `sdk:version`.</span></span>

- **`-NoCdn|--no-cdn`**

  <span data-ttu-id="51db1-160">[Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) からのダウンロードを無効にし、キャッシュされていないフィードを直接使用します。</span><span class="sxs-lookup"><span data-stu-id="51db1-160">Disables downloading from the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-NoPath|--no-path`**

  <span data-ttu-id="51db1-161">設定すると、インストール フォルダーは現在のセッションのパスにはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="51db1-161">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="51db1-162">既定では、スクリプトによって PATH が変更されます。これにより、インストール後すぐに .NET Core CLI を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="51db1-162">By default, the script modifies the PATH, which makes the .NET Core CLI available immediately after install.</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="51db1-163">設定すると、インストーラーで Web 要求を行うときにプロキシが使われます。</span><span class="sxs-lookup"><span data-stu-id="51db1-163">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="51db1-164">(Windows でのみ有効)。</span><span class="sxs-lookup"><span data-stu-id="51db1-164">(Only valid for Windows.)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="51db1-165">設定すると、プロキシ アドレスの使用時に、インストーラーでは現在のユーザーの資格情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="51db1-165">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="51db1-166">(Windows でのみ有効)。</span><span class="sxs-lookup"><span data-stu-id="51db1-166">(Only valid for Windows.)</span></span>

- **`-Runtime|--runtime <RUNTIME>`**

  <span data-ttu-id="51db1-167">SDK 全体ではなく共有ランタイムのみがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="51db1-167">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="51db1-168">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="51db1-168">The possible values are:</span></span>

  - <span data-ttu-id="51db1-169">`dotnet` - `Microsoft.NETCore.App` 共有ランタイム。</span><span class="sxs-lookup"><span data-stu-id="51db1-169">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="51db1-170">`aspnetcore` - `Microsoft.AspNetCore.App` 共有ランタイム。</span><span class="sxs-lookup"><span data-stu-id="51db1-170">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>
  - <span data-ttu-id="51db1-171">`windowsdesktop` - `Microsoft.WindowsDesktop.App` 共有ランタイム。</span><span class="sxs-lookup"><span data-stu-id="51db1-171">`windowsdesktop` - the `Microsoft.WindowsDesktop.App` shared runtime.</span></span>

- **`--runtime-id <RID>`**

  <span data-ttu-id="51db1-172">ツールのインストール先の[ランタイム識別子](../rid-catalog.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="51db1-172">Specifies the [runtime identifier](../rid-catalog.md) for which the tools are being installed.</span></span> <span data-ttu-id="51db1-173">Portable Linux には `linux-x64` を使用します。</span><span class="sxs-lookup"><span data-stu-id="51db1-173">Use `linux-x64` for portable Linux.</span></span> <span data-ttu-id="51db1-174">(Linux または macOS でのみ有効)。</span><span class="sxs-lookup"><span data-stu-id="51db1-174">(Only valid for Linux/macOS.)</span></span>

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > <span data-ttu-id="51db1-175">このパラメーターは非推奨であり、今後のバージョンのスクリプトでは削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="51db1-175">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="51db1-176">別の方法として、`-Runtime|--runtime` オプションを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="51db1-176">The recommended alternative is the `-Runtime|--runtime` option.</span></span>

  <span data-ttu-id="51db1-177">SDK 全体ではなく共有ランタイム ビットのみがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="51db1-177">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="51db1-178">このオプションは、`-Runtime|--runtime dotnet` を指定することと同じです。</span><span class="sxs-lookup"><span data-stu-id="51db1-178">This option is equivalent to specifying `-Runtime|--runtime dotnet`.</span></span>

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  <span data-ttu-id="51db1-179">*dotnet.exe* など、バージョン管理されていないファイルが既に存在する場合は、そのインストールをスキップします。</span><span class="sxs-lookup"><span data-stu-id="51db1-179">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-UncachedFeed|--uncached-feed`**

  <span data-ttu-id="51db1-180">このインストーラーで使用されている、キャッシュされていないフィードの URL を変更することを許可します。</span><span class="sxs-lookup"><span data-stu-id="51db1-180">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="51db1-181">この値は変更しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="51db1-181">We recommended that you don't change this value.</span></span>

- **`-Verbose|--verbose`**

  <span data-ttu-id="51db1-182">診断情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="51db1-182">Displays diagnostics information.</span></span>

- **`-Version|--version <VERSION>`**

  <span data-ttu-id="51db1-183">特定のビルド バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="51db1-183">Represents a specific build version.</span></span> <span data-ttu-id="51db1-184">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="51db1-184">The possible values are:</span></span>

  - <span data-ttu-id="51db1-185">`latest` - チャネルの最新ビルド (`-Channel` オプションで使用)。</span><span class="sxs-lookup"><span data-stu-id="51db1-185">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="51db1-186">`coherent` - チャネルの最新のコヒーレント ビルド。最新の安定版パッケージの組み合わせを使用します (ブランチ名の `-Channel` オプションで使用)。</span><span class="sxs-lookup"><span data-stu-id="51db1-186">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  - <span data-ttu-id="51db1-187">特定のビルド バージョンを表す X.Y.Z 形式の 3 部構成のバージョン。`-Channel` オプションよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="51db1-187">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="51db1-188">たとえば、`2.0.0-preview2-006120` のように指定します。</span><span class="sxs-lookup"><span data-stu-id="51db1-188">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="51db1-189">指定しない場合、`-Version` の既定値は `latest` です。</span><span class="sxs-lookup"><span data-stu-id="51db1-189">If not specified, `-Version` defaults to `latest`.</span></span>

## <a name="examples"></a><span data-ttu-id="51db1-190">使用例</span><span class="sxs-lookup"><span data-stu-id="51db1-190">Examples</span></span>

- <span data-ttu-id="51db1-191">最新の長期サポート (LST) バージョンを既定の場所にインストールします。</span><span class="sxs-lookup"><span data-stu-id="51db1-191">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="51db1-192">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="51db1-192">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="51db1-193">macOS/Linux の場合:</span><span class="sxs-lookup"><span data-stu-id="51db1-193">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="51db1-194">3\.1 チャネルから、最新バージョンを指定した場所にインストールします。</span><span class="sxs-lookup"><span data-stu-id="51db1-194">Install the latest version from 3.1 channel to the specified location:</span></span>

  <span data-ttu-id="51db1-195">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="51db1-195">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 3.1 -InstallDir C:\cli
  ```

  <span data-ttu-id="51db1-196">macOS/Linux の場合:</span><span class="sxs-lookup"><span data-stu-id="51db1-196">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 3.1 --install-dir ~/cli
  ```

- <span data-ttu-id="51db1-197">共有ランタイムの 3.0.0 バージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="51db1-197">Install the 3.0.0 version of the shared runtime:</span></span>

  <span data-ttu-id="51db1-198">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="51db1-198">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 3.0.0
  ```

  <span data-ttu-id="51db1-199">macOS/Linux の場合:</span><span class="sxs-lookup"><span data-stu-id="51db1-199">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 3.0.0
  ```

- <span data-ttu-id="51db1-200">スクリプトを入手し、会社のプロキシの背後に 2.1.2 バージョンをインストールします (Windows のみ)。</span><span class="sxs-lookup"><span data-stu-id="51db1-200">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="51db1-201">スクリプトを入手し、.NET Core CLI の 1 行コードのサンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="51db1-201">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="51db1-202">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="51db1-202">Windows:</span></span>

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="51db1-203">macOS/Linux の場合:</span><span class="sxs-lookup"><span data-stu-id="51db1-203">macOS/Linux:</span></span>

  ```bash
  curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="51db1-204">関連項目</span><span class="sxs-lookup"><span data-stu-id="51db1-204">See also</span></span>

- [<span data-ttu-id="51db1-205">.NET Core のリリース</span><span class="sxs-lookup"><span data-stu-id="51db1-205">.NET Core releases</span></span>](https://github.com/dotnet/core/releases)
- [<span data-ttu-id="51db1-206">.NET Core ランタイムと SDK ダウンロード アーカイブ</span><span class="sxs-lookup"><span data-stu-id="51db1-206">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
