---
title: Windows、Linux、および macOS に .NET Core ランタイムをインストールする - .NET Core
description: Windows、Linux、および macOS に .NET Core をインストールする方法について説明します。 .NET Core アプリの実行に必要な依存関係を確認します。
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: a41bbdf5419585f06773583dbe82ab0d84ebaa4c
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157637"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="d73fd-104">.NET Core ランタイムのインストール</span><span class="sxs-lookup"><span data-stu-id="d73fd-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="d73fd-105">この記事では、.NET Core ランタイムをダウンロードしてインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d73fd-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="d73fd-106">.Net Core ランタイムは、.NET Core で作成されたアプリを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="d73fd-107">インストーラーを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="d73fd-107">Install with an installer</span></span>

<span data-ttu-id="d73fd-108">Windows には、.NET Core 3.1 ランタイムのインストールに使用できるスタンドアロン インストーラーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d73fd-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="d73fd-109">x64 (64 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="d73fd-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="d73fd-110">x86 (32 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="d73fd-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="d73fd-111">インストーラーを使用したインストール</span><span class="sxs-lookup"><span data-stu-id="d73fd-111">Install with an installer</span></span>

<span data-ttu-id="d73fd-112">macOS には、.NET Core 3.1 ランタイムのインストールに使用できるスタンドアロン インストーラーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d73fd-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="d73fd-113">x64 (64 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="d73fd-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="d73fd-114">手動でダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="d73fd-114">Download and manually install</span></span>

<span data-ttu-id="d73fd-115">.NET Core 用 macOS インストーラーの代わりに、ランタイムをダウンロードして手動でインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-115">As an alternative to the macOS installers for .NET Core, you can download and manually install the runtime.</span></span>

<span data-ttu-id="d73fd-116">ランタイムをインストールし、.NET Core CLI コマンドをターミナルで使用できるようにするには、最初に .NET Core のバイナリ リリースを[ダウンロード](#all-net-core-downloads)します。</span><span class="sxs-lookup"><span data-stu-id="d73fd-116">To install the runtime and enable the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="d73fd-117">次に、ターミナルを開き、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d73fd-117">Then, open a terminal and run the following commands.</span></span> <span data-ttu-id="d73fd-118">ランタイムが `~/Downloads/dotnet-runtime.pkg` ファイルにダウンロードされることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="d73fd-118">It's assumed the runtime is downloaded to the `~/Downloads/dotnet-runtime.pkg` file.</span></span>

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-runtime.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="d73fd-119">パッケージ マネージャーを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="d73fd-119">Install with a package manager</span></span>

<span data-ttu-id="d73fd-120">多くの一般的な Linux パッケージ マネージャーを使用して .NET Core ランタイムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-120">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="d73fd-121">詳細については、[Linux パッケージ マネージャー - .NET Core のインストール](linux-package-managers.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d73fd-121">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

<span data-ttu-id="d73fd-122">パッケージ マネージャーを使用したインストールは、x64 アーキテクチャでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d73fd-122">Installing it with a package manager is only supported on the x64 architecture.</span></span> <span data-ttu-id="d73fd-123">ARM などの別のアーキテクチャを使用して .NET Core ランタイムをインストールする場合は、「[手動でダウンロードしてインストールする](#download-and-manually-install)」セクションの手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="d73fd-123">If you're installing the .NET Core Runtime with a different architecture, such as ARM, follow the instructions on the [Download and manually install](#download-and-manually-install) section.</span></span> <span data-ttu-id="d73fd-124">サポートされているアーキテクチャの詳細については、「[.NET Core の依存関係と要件](dependencies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d73fd-124">For more information about what architectures are supported, see [.NET Core dependencies and requirements](dependencies.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="d73fd-125">手動でダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="d73fd-125">Download and manually install</span></span>

<span data-ttu-id="d73fd-126">ランタイムを抽出し、.NET Core CLI コマンドをターミナルで使用できるようにするには、最初に .NET Core のバイナリ リリースを[ダウンロード](#all-net-core-downloads)します。</span><span class="sxs-lookup"><span data-stu-id="d73fd-126">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="d73fd-127">次に、ターミナルを開き、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d73fd-127">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="d73fd-128">上記の `export` コマンドでは、それを実行したターミナル セッションでのみ .NET Core CLI コマンドを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d73fd-128">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="d73fd-129">シェル プロファイルを編集して、コマンドを永続的に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-129">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="d73fd-130">Linux ではさまざまなシェルを使用でき、それぞれに異なるプロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="d73fd-130">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="d73fd-131">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d73fd-131">For example:</span></span>
>
> - <span data-ttu-id="d73fd-132">**Bash シェル**: *~/.bash_profile*、 *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="d73fd-132">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="d73fd-133">**Korn シェル**: *~/.kshrc* または *.profile*</span><span class="sxs-lookup"><span data-stu-id="d73fd-133">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="d73fd-134">**Z シェル**: *~/.zshrc* または *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="d73fd-134">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="d73fd-135">シェルの適切なソース ファイルを編集し、既存の `PATH` ステートメントの末尾に `:$HOME/dotnet` を追加します。</span><span class="sxs-lookup"><span data-stu-id="d73fd-135">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="d73fd-136">`PATH` ステートメントが含まれていない場合は、`export PATH=$PATH:$HOME/dotnet` を含む新しい行を追加します。</span><span class="sxs-lookup"><span data-stu-id="d73fd-136">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="d73fd-137">また、ファイルの末尾に `export DOTNET_ROOT=$HOME/dotnet` を追加します。</span><span class="sxs-lookup"><span data-stu-id="d73fd-137">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="d73fd-138">この方法では、別々の場所に異なるバージョンをインストールして、どのアプリケーションにどれを使用するかを明示的に選択できます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-138">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="d73fd-139">PowerShell オートメーションを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="d73fd-139">Install with PowerShell automation</span></span>

<span data-ttu-id="d73fd-140">[dotnet-install スクリプト](../tools/dotnet-install-script.md)は、ランタイムの自動化および管理者以外によるインストールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-140">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="d73fd-141">スクリプトは、[dotnet-install スクリプト参照ページ](../tools/dotnet-install-script.md)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-141">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="d73fd-142">スクリプトでは、既定で最新の [長期サポート (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) バージョン (.NET Core 3.1) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-142">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="d73fd-143">`Channel` スイッチを指定することで、特定のリリースを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-143">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="d73fd-144">ランタイムをインストールするには、`Runtime` スイッチを含めます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-144">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="d73fd-145">それ以外の場合は、スクリプトによって [SDK](sdk.md) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-145">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="d73fd-146">上のコマンドでは、互換性を最大限に高めるために ASP.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d73fd-146">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="d73fd-147">ASP.NET Core ランタイムには、標準の .NET Core ランタイムも含まれています。</span><span class="sxs-lookup"><span data-stu-id="d73fd-147">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="d73fd-148">手動でダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="d73fd-148">Download and manually install</span></span>

<span data-ttu-id="d73fd-149">ランタイムを抽出し、.NET Core CLI コマンドをターミナルで使用できるようにするには、最初に .NET Core のバイナリ リリースを[ダウンロード](#all-net-core-downloads)します。</span><span class="sxs-lookup"><span data-stu-id="d73fd-149">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="d73fd-150">次に、インストール先のディレクトリ (`%USERPROFILE%\dotnet` など) を作成します。</span><span class="sxs-lookup"><span data-stu-id="d73fd-150">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="d73fd-151">最後に、ダウンロードした zip ファイルをそのディレクトリに抽出します。</span><span class="sxs-lookup"><span data-stu-id="d73fd-151">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="d73fd-152">既定では、.NET Core CLI コマンドおよびアプリでは、この方法でインストールされた .NET Core は使用されません。</span><span class="sxs-lookup"><span data-stu-id="d73fd-152">By default, .NET Core CLI commands and apps will not use .NET Core installed in this way.</span></span> <span data-ttu-id="d73fd-153">使用するには、明示的に選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d73fd-153">You have to explicitly choose to use it.</span></span> <span data-ttu-id="d73fd-154">これを行うには、アプリケーションの起動に使用する環境変数を変更します。</span><span class="sxs-lookup"><span data-stu-id="d73fd-154">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="d73fd-155">この方法では、複数のバージョンを別々の場所にインストールして、その場所を参照する環境変数を使ってアプリケーションを実行することで、アプリケーションによって使用されるインストール場所を明示的に選択できます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-155">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="d73fd-156">これらの環境変数が設定されている場合でも、.NET Core では、アプリケーションを実行するための最適なフレームワークを選択するときに、既定のグローバル インストールの場所が引き続き考慮されます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-156">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="d73fd-157">既定値は通常、インストーラーによって使用される `C:\Program Files\dotnet` です。</span><span class="sxs-lookup"><span data-stu-id="d73fd-157">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="d73fd-158">この環境変数の設定も行うことで、カスタムのインストール場所のみを使用するように、ランタイムに指示できます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-158">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="d73fd-159">bash オートメーションを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="d73fd-159">Install with bash automation</span></span>

<span data-ttu-id="d73fd-160">[dotnet-install スクリプト](../tools/dotnet-install-script.md)は、ランタイムの自動化および管理者以外によるインストールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-160">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="d73fd-161">スクリプトは、[dotnet-install スクリプト参照ページ](../tools/dotnet-install-script.md)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-161">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="d73fd-162">スクリプトでは、既定で最新の [長期サポート (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) バージョン (.NET Core 3.1) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-162">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="d73fd-163">`current` スイッチを指定することで、特定のリリースを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-163">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="d73fd-164">ランタイムをインストールするには、`runtime` スイッチを含めます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-164">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="d73fd-165">それ以外の場合は、スクリプトによって [SDK](sdk.md) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-165">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="d73fd-166">上のコマンドでは、互換性を最大限に高めるために ASP.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d73fd-166">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="d73fd-167">ASP.NET Core ランタイムには、標準の .NET Core ランタイムも含まれています。</span><span class="sxs-lookup"><span data-stu-id="d73fd-167">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="d73fd-168">すべての .NET Core のダウンロード</span><span class="sxs-lookup"><span data-stu-id="d73fd-168">All .NET Core downloads</span></span>

<span data-ttu-id="d73fd-169">次のいずれかのリンクを使用して、.NET Core を直接ダウンロードしてインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-169">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="d73fd-170">.NET Core 3.1 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="d73fd-170">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="d73fd-171">.NET Core 3.0 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="d73fd-171">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="d73fd-172">.NET Core 2.2 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="d73fd-172">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="d73fd-173">.NET Core 2.1 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="d73fd-173">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="d73fd-174">Docker</span><span class="sxs-lookup"><span data-stu-id="d73fd-174">Docker</span></span>

<span data-ttu-id="d73fd-175">コンテナーを使用すると、アプリケーションをホスト システムの他の部分から簡単に分離できます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-175">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="d73fd-176">同じコンピューター上のコンテナーでは、カーネルだけが共有され、アプリケーションに提供されたリソースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-176">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="d73fd-177">.NET Core は Docker コンテナー内で実行できます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-177">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="d73fd-178">公式の .NET Core Docker イメージは Microsoft Container Registry (MCR) に公開され、[Microsoft .NET Core の Docker Hub リポジトリ](https://hub.docker.com/_/microsoft-dotnet-core/)で見つけられます。</span><span class="sxs-lookup"><span data-stu-id="d73fd-178">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="d73fd-179">各リポジトリには、.NET (SDK またはランタイム) と自分が使用できる OS のさまざまな組み合わせのイメージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d73fd-179">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="d73fd-180">Microsoft は、特定のシナリオに対応したイメージを用意しています。</span><span class="sxs-lookup"><span data-stu-id="d73fd-180">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="d73fd-181">たとえば、[ASP.NET Core リポジトリ](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)には、運用環境での ASP.NET Core アプリの実行用にビルドされたイメージが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d73fd-181">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="d73fd-182">Docker コンテナー内で .NET Core を使用する方法の詳細については、「[.NET および Docker の概要](../docker/introduction.md)」と[サンプル](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d73fd-182">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d73fd-183">次の手順</span><span class="sxs-lookup"><span data-stu-id="d73fd-183">Next steps</span></span>

- <span data-ttu-id="d73fd-184">[.NET Core が既にインストールされているかどうかを確認する方法](how-to-detect-installed-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="d73fd-184">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
