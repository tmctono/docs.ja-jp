---
title: dotnet-install スクリプト
description: .NET Core SDK と共有ランタイムをインストールするための dotnet-install スクリプトについて学習します。
ms.date: 01/23/2020
ms.openlocfilehash: 169991ac4cd24ccab90634ff265c3ae5b603f8e9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734207"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="1d386-103">dotnet-install スクリプト リファレンス</span><span class="sxs-lookup"><span data-stu-id="1d386-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="1d386-104">名前</span><span class="sxs-lookup"><span data-stu-id="1d386-104">Name</span></span>

<span data-ttu-id="1d386-105">`dotnet-install.ps1` | `dotnet-install.sh` - .NET Core SDK と共有ランタイムをインストールするために使うスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="1d386-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core SDK and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1d386-106">構文</span><span class="sxs-lookup"><span data-stu-id="1d386-106">Synopsis</span></span>

<span data-ttu-id="1d386-107">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="1d386-107">Windows:</span></span>

```powershell
dotnet-install.ps1 [-Channel] [-Version] [-JSonFile] [-InstallDir] [-Architecture]
    [-Runtime] [-DryRun] [-NoPath] [-Verbose] [-AzureFeed] [-UncachedFeed] [-NoCdn] [-FeedCredential]
    [-ProxyAddress] [-ProxyUseDefaultCredentials] [-SkipNonVersionedFiles] [-Help]
```

<span data-ttu-id="1d386-108">Linux または macOS の場合:</span><span class="sxs-lookup"><span data-stu-id="1d386-108">Linux/macOs:</span></span>

```bash
dotnet-install.sh [--channel] [--version] [--jsonfile] [--install-dir] [--architecture]
    [--runtime] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--uncached-feed] [--no-cdn] [--feed-credential]
    [--runtime-id] [--skip-non-versioned-files] [--help]
```

## <a name="description"></a><span data-ttu-id="1d386-109">説明</span><span class="sxs-lookup"><span data-stu-id="1d386-109">Description</span></span>

<span data-ttu-id="1d386-110">`dotnet-install` スクリプトは、.NET Core CLI ツールや共有ランタイムが含まれる .NET Core SDK の非管理者インストールを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1d386-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI tools and the shared runtime.</span></span>

<span data-ttu-id="1d386-111">安定したバージョンのスクリプトを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1d386-111">We recommend that you use the stable version of the scripts:</span></span>

- <span data-ttu-id="1d386-112">Bash (Linux、macOS): <https://dot.net/v1/dotnet-install.sh></span><span class="sxs-lookup"><span data-stu-id="1d386-112">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span></span>
- <span data-ttu-id="1d386-113">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span><span class="sxs-lookup"><span data-stu-id="1d386-113">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span></span>

<span data-ttu-id="1d386-114">これらのスクリプトの主な有用性は、オートメーションのシナリオと管理者以外のインストールにおいてです。</span><span class="sxs-lookup"><span data-stu-id="1d386-114">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="1d386-115">2 つのスクリプトがあります。1 つは Windows 上で動作する PowerShell スクリプトで、もう 1 つは Linux/macOS 上で動作する bash スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="1d386-115">There are two scripts: one is a PowerShell script that works on Windows, and the other is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="1d386-116">スクリプトの動作は両方とも同じです。</span><span class="sxs-lookup"><span data-stu-id="1d386-116">Both scripts have the same behavior.</span></span> <span data-ttu-id="1d386-117">bash スクリプトは PowerShell のスイッチも読み取るので、Linux/macOS システムのスクリプトで PowerShell のスイッチを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="1d386-117">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

<span data-ttu-id="1d386-118">インストール スクリプトは CLI ビルド ドロップから ZIP/tarball ファイルをダウンロードし、既定の場所または `-InstallDir|--install-dir` で指定された場所へのインストールに進みます。</span><span class="sxs-lookup"><span data-stu-id="1d386-118">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="1d386-119">既定では、インストール スクリプトは SDK をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="1d386-119">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="1d386-120">共有ランタイムの取得だけを行いたい場合は、`-Runtime|--runtime` 引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="1d386-120">If you wish to only obtain the shared runtime, specify the `-Runtime|--runtime` argument.</span></span>

<span data-ttu-id="1d386-121">既定では、スクリプトはインストールの場所を現在のセッションの $PATH に追加します。</span><span class="sxs-lookup"><span data-stu-id="1d386-121">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="1d386-122">`-NoPath|--no-path` 引数を指定することによってこの既定の動作をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="1d386-122">Override this default behavior by specifying the `-NoPath|--no-path` argument.</span></span>

<span data-ttu-id="1d386-123">スクリプトを実行する前に、必要な[依存関係](../install/dependencies.md)をすべてインストールします。</span><span class="sxs-lookup"><span data-stu-id="1d386-123">Before running the script, install the required [dependencies](../install/dependencies.md).</span></span>

<span data-ttu-id="1d386-124">`-Version|--version` 引数を使用して、特定のバージョンをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="1d386-124">You can install a specific version using the `-Version|--version` argument.</span></span> <span data-ttu-id="1d386-125">バージョンは 3 つの部分からなるバージョン (`2.1.0` など) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d386-125">The version must be specified as a three-part version (for example, `2.1.0`).</span></span> <span data-ttu-id="1d386-126">指定しない場合は、`latest` バージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1d386-126">If not provided, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="1d386-127">オプション</span><span class="sxs-lookup"><span data-stu-id="1d386-127">Options</span></span>

- **`-Channel|--channel <CHANNEL>`**

  <span data-ttu-id="1d386-128">インストールのソース チャネルを指定します。</span><span class="sxs-lookup"><span data-stu-id="1d386-128">Specifies the source channel for the installation.</span></span> <span data-ttu-id="1d386-129">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1d386-129">The possible values are:</span></span>

  - <span data-ttu-id="1d386-130">`Current` - 最新リリース。</span><span class="sxs-lookup"><span data-stu-id="1d386-130">`Current` - Most current release.</span></span>
  - <span data-ttu-id="1d386-131">`LTS` - 長期的なサポート チャネル (サポートされている最新リリース)。</span><span class="sxs-lookup"><span data-stu-id="1d386-131">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="1d386-132">特定のリリースを表す X.Y 形式の 2 部構成のバージョン (たとえば、`2.1` または `3.0`)。</span><span class="sxs-lookup"><span data-stu-id="1d386-132">Two-part version in X.Y format representing a specific release (for example, `2.1` or `3.0`).</span></span>
  - <span data-ttu-id="1d386-133">ブランチ名: たとえば、`release/3.1.1xx` または `master` (夜間リリース用)</span><span class="sxs-lookup"><span data-stu-id="1d386-133">Branch name: for example, `release/3.1.1xx` or `master` (for nightly releases).</span></span> <span data-ttu-id="1d386-134">プレビュー チャネルからバージョンをインストールするには、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="1d386-134">Use this option to install a version from a preview channel.</span></span> <span data-ttu-id="1d386-135">「[インストーラーとバイナリ](https://github.com/dotnet/core-sdk#installers-and-binaries)」に記載されているチャネルの名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="1d386-135">Use the name of the channel as listed in [Installers and Binaries](https://github.com/dotnet/core-sdk#installers-and-binaries).</span></span>

  <span data-ttu-id="1d386-136">既定値は `LTS` です。</span><span class="sxs-lookup"><span data-stu-id="1d386-136">The default value is `LTS`.</span></span> <span data-ttu-id="1d386-137">.NET のサポート チャネルの詳細については、「[.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)」(.NET のサポート ポリシー) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d386-137">For more information on .NET support channels, see the [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) page.</span></span>

- **`-Version|--version <VERSION>`**

  <span data-ttu-id="1d386-138">特定のビルド バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="1d386-138">Represents a specific build version.</span></span> <span data-ttu-id="1d386-139">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1d386-139">The possible values are:</span></span>

  - <span data-ttu-id="1d386-140">`latest` - チャネルの最新ビルド (`-Channel` オプションで使用)。</span><span class="sxs-lookup"><span data-stu-id="1d386-140">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="1d386-141">`coherent` - チャネルの最新のコヒーレント ビルド。最新の安定版パッケージの組み合わせを使用します (ブランチ名の `-Channel` オプションで使用)。</span><span class="sxs-lookup"><span data-stu-id="1d386-141">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  - <span data-ttu-id="1d386-142">特定のビルド バージョンを表す X.Y.Z 形式の 3 部構成のバージョン。`-Channel` オプションよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="1d386-142">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="1d386-143">たとえば、`2.0.0-preview2-006120` のように指定します。</span><span class="sxs-lookup"><span data-stu-id="1d386-143">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="1d386-144">指定しない場合、`-Version` の既定値は `latest` です。</span><span class="sxs-lookup"><span data-stu-id="1d386-144">If not specified, `-Version` defaults to `latest`.</span></span>

- **`-JSonFile|--jsonfile <JSONFILE>`**

  <span data-ttu-id="1d386-145">SDK バージョンを決定するために使用される [global.json](global-json.md) ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="1d386-145">Specifies a path to a [global.json](global-json.md) file that will be used to determine the SDK version.</span></span> <span data-ttu-id="1d386-146">*global.json* ファイルには `sdk:version` の値が必要です。</span><span class="sxs-lookup"><span data-stu-id="1d386-146">The *global.json* file must have a value for `sdk:version`.</span></span>

- **`-InstallDir|--install-dir <DIRECTORY>`**

  <span data-ttu-id="1d386-147">インストール パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="1d386-147">Specifies the installation path.</span></span> <span data-ttu-id="1d386-148">存在しない場合は、ディレクトリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1d386-148">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="1d386-149">既定値は *%LocalAppData%\Microsoft\dotnet*です。</span><span class="sxs-lookup"><span data-stu-id="1d386-149">The default value is *%LocalAppData%\Microsoft\dotnet*.</span></span> <span data-ttu-id="1d386-150">バイナリは、このディレクトリに直接配置されます。</span><span class="sxs-lookup"><span data-stu-id="1d386-150">Binaries are placed directly in this directory.</span></span>

- **`-Architecture|--architecture <ARCHITECTURE>`**

  <span data-ttu-id="1d386-151">インストールする .NET Core バイナリのアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="1d386-151">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="1d386-152">指定できる値は、`<auto>`、`amd64`、`x64`、`x86`、`arm64`、および `arm` です。</span><span class="sxs-lookup"><span data-stu-id="1d386-152">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="1d386-153">既定値は `<auto>` です。これは実行中の OS アーキテクチャを示します。</span><span class="sxs-lookup"><span data-stu-id="1d386-153">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > <span data-ttu-id="1d386-154">このパラメーターは非推奨であり、今後のバージョンのスクリプトでは削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1d386-154">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="1d386-155">別の方法として、`-Runtime|--runtime` オプションを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1d386-155">The recommended alternative is the `-Runtime|--runtime` option.</span></span>

  <span data-ttu-id="1d386-156">SDK 全体ではなく共有ランタイム ビットのみがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="1d386-156">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="1d386-157">このオプションは、`-Runtime|--runtime dotnet` を指定することと同じです。</span><span class="sxs-lookup"><span data-stu-id="1d386-157">This option is equivalent to specifying `-Runtime|--runtime dotnet`.</span></span>

- **`-Runtime|--runtime <RUNTIME>`**

  <span data-ttu-id="1d386-158">SDK 全体ではなく共有ランタイムのみがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="1d386-158">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="1d386-159">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1d386-159">The possible values are:</span></span>

  - <span data-ttu-id="1d386-160">`dotnet` - `Microsoft.NETCore.App` 共有ランタイム。</span><span class="sxs-lookup"><span data-stu-id="1d386-160">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="1d386-161">`aspnetcore` - `Microsoft.AspNetCore.App` 共有ランタイム。</span><span class="sxs-lookup"><span data-stu-id="1d386-161">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>
  - <span data-ttu-id="1d386-162">`windowsdesktop` - `Microsoft.WindowsDesktop.App` 共有ランタイム。</span><span class="sxs-lookup"><span data-stu-id="1d386-162">`windowsdesktop` - the `Microsoft.WindowsDesktop.App` shared runtime.</span></span>

- **`-DryRun|--dry-run`**

  <span data-ttu-id="1d386-163">設定すると、スクリプトでインストールは実行されません。</span><span class="sxs-lookup"><span data-stu-id="1d386-163">If set, the script won't perform the installation.</span></span> <span data-ttu-id="1d386-164">代わりに、現在要求されているバージョンの .NET Core CLI を一貫してインストールするために使用するコマンド ラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d386-164">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="1d386-165">たとえば、バージョン `latest` を指定すると、そのバージョンのリンクが表示されるので、ビルド スクリプトで確定的にこのコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d386-165">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="1d386-166">また、自分でインストールまたはダウンロードしたい場合、バイナリの場所も表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d386-166">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-NoPath|--no-path`**

  <span data-ttu-id="1d386-167">設定すると、インストール フォルダーは現在のセッションのパスにはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="1d386-167">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="1d386-168">既定では、スクリプトによって PATH が変更されます。その結果、インストール後すぐに CLI ツールを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1d386-168">By default, the script modifies the PATH, which makes the CLI tools available immediately after install.</span></span>

- **`-Verbose|--verbose`**

  <span data-ttu-id="1d386-169">診断情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="1d386-169">Displays diagnostics information.</span></span>

- **`-AzureFeed|--azure-feed`**

  <span data-ttu-id="1d386-170">Azure フィードの URL をインストーラーに指定します。</span><span class="sxs-lookup"><span data-stu-id="1d386-170">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="1d386-171">この値は変更しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1d386-171">We recommended that you don't change this value.</span></span> <span data-ttu-id="1d386-172">既定値は `https://dotnetcli.azureedge.net/dotnet` です。</span><span class="sxs-lookup"><span data-stu-id="1d386-172">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-UncachedFeed|--uncached-feed`**

  <span data-ttu-id="1d386-173">このインストーラーで使用されている、キャッシュされていないフィードの URL を変更することを許可します。</span><span class="sxs-lookup"><span data-stu-id="1d386-173">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="1d386-174">この値は変更しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1d386-174">We recommended that you don't change this value.</span></span>

- **`-NoCdn|--no-cdn`**

  <span data-ttu-id="1d386-175">[Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) からのダウンロードを無効にし、キャッシュされていないフィードを直接使用します。</span><span class="sxs-lookup"><span data-stu-id="1d386-175">Disables downloading from the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-FeedCredential|--feed-credential`**

  <span data-ttu-id="1d386-176">Azure フィードに付加するクエリ文字列として使用されます。</span><span class="sxs-lookup"><span data-stu-id="1d386-176">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="1d386-177">非公開の BLOB ストレージ アカウントを使用するように URL を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="1d386-177">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`--runtime-id`**

  <span data-ttu-id="1d386-178">ツールのインストール先の[ランタイム識別子](../rid-catalog.md)を指定します。</span><span class="sxs-lookup"><span data-stu-id="1d386-178">Specifies the [runtime identifier](../rid-catalog.md) for which the tools are being installed.</span></span> <span data-ttu-id="1d386-179">Portable Linux には `linux-x64` を使用します。</span><span class="sxs-lookup"><span data-stu-id="1d386-179">Use `linux-x64` for portable Linux.</span></span> <span data-ttu-id="1d386-180">(Linux または macOS でのみ有効)</span><span class="sxs-lookup"><span data-stu-id="1d386-180">(Only valid for Linux/macOS)</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="1d386-181">設定すると、インストーラーで Web 要求を行うときにプロキシが使われます。</span><span class="sxs-lookup"><span data-stu-id="1d386-181">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="1d386-182">(Windows でのみ有効)</span><span class="sxs-lookup"><span data-stu-id="1d386-182">(Only valid for Windows)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="1d386-183">設定すると、プロキシ アドレスの使用時に、インストーラーでは現在のユーザーの資格情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1d386-183">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="1d386-184">(Windows でのみ有効)</span><span class="sxs-lookup"><span data-stu-id="1d386-184">(Only valid for Windows)</span></span>

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  <span data-ttu-id="1d386-185">*dotnet.exe* など、バージョン管理されていないファイルが既に存在する場合は、そのインストールをスキップします。</span><span class="sxs-lookup"><span data-stu-id="1d386-185">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-Help|--help`**

  <span data-ttu-id="1d386-186">スクリプトのヘルプを出力します。</span><span class="sxs-lookup"><span data-stu-id="1d386-186">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="1d386-187">使用例</span><span class="sxs-lookup"><span data-stu-id="1d386-187">Examples</span></span>

- <span data-ttu-id="1d386-188">最新の長期サポート (LST) バージョンを既定の場所にインストールします。</span><span class="sxs-lookup"><span data-stu-id="1d386-188">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="1d386-189">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="1d386-189">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="1d386-190">macOS/Linux の場合:</span><span class="sxs-lookup"><span data-stu-id="1d386-190">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="1d386-191">3\.1 チャネルから、最新バージョンを指定した場所にインストールします。</span><span class="sxs-lookup"><span data-stu-id="1d386-191">Install the latest version from 3.1 channel to the specified location:</span></span>

  <span data-ttu-id="1d386-192">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="1d386-192">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 3.1 -InstallDir C:\cli
  ```

  <span data-ttu-id="1d386-193">macOS/Linux の場合:</span><span class="sxs-lookup"><span data-stu-id="1d386-193">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 3.1 --install-dir ~/cli
  ```

- <span data-ttu-id="1d386-194">共有ランタイムの 3.0.0 バージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="1d386-194">Install the 3.0.0 version of the shared runtime:</span></span>

  <span data-ttu-id="1d386-195">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="1d386-195">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 3.0.0
  ```

  <span data-ttu-id="1d386-196">macOS/Linux の場合:</span><span class="sxs-lookup"><span data-stu-id="1d386-196">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 3.0.0
  ```

- <span data-ttu-id="1d386-197">スクリプトを入手し、会社のプロキシの背後に 2.1.2 バージョンをインストールします (Windows のみ)。</span><span class="sxs-lookup"><span data-stu-id="1d386-197">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="1d386-198">スクリプトを入手し、.NET Core CLI の 1 行コードのサンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="1d386-198">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="1d386-199">Windows の場合:</span><span class="sxs-lookup"><span data-stu-id="1d386-199">Windows:</span></span>

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="1d386-200">macOS/Linux の場合:</span><span class="sxs-lookup"><span data-stu-id="1d386-200">macOS/Linux:</span></span>

  ```bash
  curl -ssl https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="1d386-201">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d386-201">See also</span></span>

- [<span data-ttu-id="1d386-202">.NET Core のリリース</span><span class="sxs-lookup"><span data-stu-id="1d386-202">.NET Core releases</span></span>](https://github.com/dotnet/core/releases)
- [<span data-ttu-id="1d386-203">.NET Core ランタイムと SDK ダウンロード アーカイブ</span><span class="sxs-lookup"><span data-stu-id="1d386-203">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
