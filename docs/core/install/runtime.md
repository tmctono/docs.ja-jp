---
title: Windows、Linux、および macOS に .NET Core ランタイムをインストールする - .NET Core
description: Windows、Linux、および macOS に .NET Core をインストールする方法について説明します。 .NET Core アプリの実行に必要な依存関係を確認します。
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: ba50eb222d9eab6bffbb8ebfdf0ecf47951ce719
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543522"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="5605a-104">.NET Core ランタイムのインストール</span><span class="sxs-lookup"><span data-stu-id="5605a-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="5605a-105">この記事では、.NET Core ランタイムをダウンロードしてインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5605a-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="5605a-106">.Net Core ランタイムは、.NET Core で作成されたアプリを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5605a-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="5605a-107">インストーラーを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="5605a-107">Install with an installer</span></span>

<span data-ttu-id="5605a-108">Windows には、.NET Core 3.1 ランタイムのインストールに使用できるスタンドアロン インストーラーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5605a-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="5605a-109">x64 (64 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="5605a-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="5605a-110">x86 (32 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="5605a-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="5605a-111">インストーラーを使用したインストール</span><span class="sxs-lookup"><span data-stu-id="5605a-111">Install with an installer</span></span>

<span data-ttu-id="5605a-112">macOS には、.NET Core 3.1 ランタイムのインストールに使用できるスタンドアロン インストーラーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5605a-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="5605a-113">x64 (64 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="5605a-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="5605a-114">パッケージ マネージャーを使用したインストール</span><span class="sxs-lookup"><span data-stu-id="5605a-114">Install with a package manager</span></span>

<span data-ttu-id="5605a-115">多くの一般的な Linux パッケージ マネージャーを使用して .NET Core ランタイムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="5605a-115">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="5605a-116">詳細については、[Linux パッケージ マネージャー - .NET Core のインストール](linux-package-managers.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5605a-116">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

<span data-ttu-id="5605a-117">パッケージ マネージャーを使用したインストールは、x64 アーキテクチャでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5605a-117">Installing it with a package manager is only supported on the x64 architecture.</span></span> <span data-ttu-id="5605a-118">ARM などの別のアーキテクチャを使用して .NET Core ランタイムをインストールする場合は、「[手動でダウンロードしてインストールする](#download-and-manually-install)」セクションの手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="5605a-118">If you're installing the .NET Core Runtime with a different architecture, such as ARM, follow the instructions on the [Download and manually install](#download-and-manually-install) section.</span></span> <span data-ttu-id="5605a-119">サポートされているアーキテクチャの詳細については、「[.NET Core の依存関係と要件](dependencies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5605a-119">For more information about what architectures are supported, see [.NET Core dependencies and requirements](dependencies.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="5605a-120">手動でダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="5605a-120">Download and manually install</span></span>

<span data-ttu-id="5605a-121">ランタイムを抽出し、.NET Core CLI コマンドをターミナルで使用できるようにするには、最初に .NET Core のバイナリ リリースを[ダウンロード](#all-net-core-downloads)します。</span><span class="sxs-lookup"><span data-stu-id="5605a-121">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="5605a-122">次に、ターミナルを開き、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5605a-122">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="5605a-123">上記の `export` コマンドでは、それを実行したターミナル セッションでのみ .NET Core CLI コマンドを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5605a-123">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="5605a-124">シェル プロファイルを編集して、コマンドを永続的に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="5605a-124">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="5605a-125">Linux ではさまざまなシェルを使用でき、それぞれに異なるプロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="5605a-125">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="5605a-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5605a-126">For example:</span></span>
>
> - <span data-ttu-id="5605a-127">**Bash シェル**: *~/.bash_profile*、 *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="5605a-127">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="5605a-128">**Korn シェル**: *~/.kshrc* または *.profile*</span><span class="sxs-lookup"><span data-stu-id="5605a-128">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="5605a-129">**Z シェル**: *~/.zshrc* または *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="5605a-129">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
> 
> <span data-ttu-id="5605a-130">シェルの適切なソース ファイルを編集し、既存の `PATH` ステートメントの末尾に `:$HOME/dotnet` を追加します。</span><span class="sxs-lookup"><span data-stu-id="5605a-130">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="5605a-131">`PATH` ステートメントが含まれていない場合は、`export PATH=$PATH:$HOME/dotnet` を含む新しい行を追加します。</span><span class="sxs-lookup"><span data-stu-id="5605a-131">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="5605a-132">また、ファイルの末尾に `export DOTNET_ROOT=$HOME/dotnet` を追加します。</span><span class="sxs-lookup"><span data-stu-id="5605a-132">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="5605a-133">この方法では、別々の場所に異なるバージョンをインストールして、どのアプリケーションにどれを使用するかを明示的に選択できます。</span><span class="sxs-lookup"><span data-stu-id="5605a-133">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="5605a-134">PowerShell オートメーションを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="5605a-134">Install with PowerShell automation</span></span>

<span data-ttu-id="5605a-135">[dotnet-install スクリプト](../tools/dotnet-install-script.md)は、ランタイムの自動化および管理者以外によるインストールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="5605a-135">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="5605a-136">スクリプトは、[dotnet-install スクリプト参照ページ](../tools/dotnet-install-script.md)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="5605a-136">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="5605a-137">スクリプトでは、既定で最新の [長期サポート (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) バージョン (.NET Core 3.1) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="5605a-137">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="5605a-138">`Channel` スイッチを指定することで、特定のリリースを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5605a-138">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="5605a-139">ランタイムをインストールするには、`Runtime` スイッチを含めます。</span><span class="sxs-lookup"><span data-stu-id="5605a-139">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="5605a-140">それ以外の場合は、スクリプトによって [SDK](sdk.md) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="5605a-140">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="5605a-141">上のコマンドでは、互換性を最大限に高めるために ASP.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5605a-141">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="5605a-142">ASP.NET Core ランタイムには、標準の .NET Core ランタイムも含まれています。</span><span class="sxs-lookup"><span data-stu-id="5605a-142">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="5605a-143">手動でダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="5605a-143">Download and manually install</span></span>

<span data-ttu-id="5605a-144">ランタイムを抽出し、.NET Core CLI コマンドをターミナルで使用できるようにするには、最初に .NET Core のバイナリ リリースを[ダウンロード](#all-net-core-downloads)します。</span><span class="sxs-lookup"><span data-stu-id="5605a-144">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="5605a-145">次に、インストール先のディレクトリ (`%USERPROFILE%\dotnet` など) を作成します。</span><span class="sxs-lookup"><span data-stu-id="5605a-145">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="5605a-146">最後に、ダウンロードした zip ファイルをそのディレクトリに抽出します。</span><span class="sxs-lookup"><span data-stu-id="5605a-146">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="5605a-147">既定では、.NET Core CLI コマンドおよびアプリでは、この方法でインストールされた .NET Core は使用されません。</span><span class="sxs-lookup"><span data-stu-id="5605a-147">By default, .NET Core CLI commands and apps will not use .NET Core installed in this way.</span></span> <span data-ttu-id="5605a-148">使用するには、明示的に選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5605a-148">You have to explicitly choose to use it.</span></span> <span data-ttu-id="5605a-149">これを行うには、アプリケーションの起動に使用する環境変数を変更します。</span><span class="sxs-lookup"><span data-stu-id="5605a-149">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="5605a-150">この方法では、複数のバージョンを別々の場所にインストールして、その場所を参照する環境変数を使ってアプリケーションを実行することで、アプリケーションによって使用されるインストール場所を明示的に選択できます。</span><span class="sxs-lookup"><span data-stu-id="5605a-150">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="5605a-151">これらの環境変数が設定されている場合でも、.NET Core では、アプリケーションを実行するための最適なフレームワークを選択するときに、既定のグローバル インストールの場所が引き続き考慮されます。</span><span class="sxs-lookup"><span data-stu-id="5605a-151">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="5605a-152">既定値は通常、インストーラーによって使用される `C:\Program Files\dotnet` です。</span><span class="sxs-lookup"><span data-stu-id="5605a-152">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="5605a-153">この環境変数の設定も行うことで、カスタムのインストール場所のみを使用するように、ランタイムに指示できます。</span><span class="sxs-lookup"><span data-stu-id="5605a-153">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="5605a-154">bash オートメーションを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="5605a-154">Install with bash automation</span></span>

<span data-ttu-id="5605a-155">[dotnet-install スクリプト](../tools/dotnet-install-script.md)は、ランタイムの自動化および管理者以外によるインストールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="5605a-155">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="5605a-156">スクリプトは、[dotnet-install スクリプト参照ページ](../tools/dotnet-install-script.md)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="5605a-156">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="5605a-157">スクリプトでは、既定で最新の [長期サポート (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) バージョン (.NET Core 3.1) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="5605a-157">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="5605a-158">`current` スイッチを指定することで、特定のリリースを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5605a-158">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="5605a-159">ランタイムをインストールするには、`runtime` スイッチを含めます。</span><span class="sxs-lookup"><span data-stu-id="5605a-159">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="5605a-160">それ以外の場合は、スクリプトによって [SDK](sdk.md) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="5605a-160">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="5605a-161">上のコマンドでは、互換性を最大限に高めるために ASP.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5605a-161">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="5605a-162">ASP.NET Core ランタイムには、標準の .NET Core ランタイムも含まれています。</span><span class="sxs-lookup"><span data-stu-id="5605a-162">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="5605a-163">すべての .NET Core のダウンロード</span><span class="sxs-lookup"><span data-stu-id="5605a-163">All .NET Core downloads</span></span>

<span data-ttu-id="5605a-164">次のいずれかのリンクを使用して、.NET Core を直接ダウンロードしてインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="5605a-164">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="5605a-165">.NET Core 3.1 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="5605a-165">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="5605a-166">.NET Core 3.0 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="5605a-166">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="5605a-167">.NET Core 2.2 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="5605a-167">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="5605a-168">.NET Core 2.1 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="5605a-168">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="5605a-169">Docker</span><span class="sxs-lookup"><span data-stu-id="5605a-169">Docker</span></span>

<span data-ttu-id="5605a-170">コンテナーを使用すると、アプリケーションをホスト システムの他の部分から簡単に分離できます。</span><span class="sxs-lookup"><span data-stu-id="5605a-170">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="5605a-171">同じコンピューター上のコンテナーでは、カーネルだけが共有され、アプリケーションに提供されたリソースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="5605a-171">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="5605a-172">.NET Core は Docker コンテナー内で実行できます。</span><span class="sxs-lookup"><span data-stu-id="5605a-172">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="5605a-173">公式の .NET Core Docker イメージは Microsoft Container Registry (MCR) に公開され、[Microsoft .NET Core の Docker Hub リポジトリ](https://hub.docker.com/_/microsoft-dotnet-core/)で見つけられます。</span><span class="sxs-lookup"><span data-stu-id="5605a-173">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="5605a-174">各リポジトリには、.NET (SDK またはランタイム) と自分が使用できる OS のさまざまな組み合わせのイメージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5605a-174">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="5605a-175">Microsoft は、特定のシナリオに対応したイメージを用意しています。</span><span class="sxs-lookup"><span data-stu-id="5605a-175">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="5605a-176">たとえば、[ASP.NET Core リポジトリ](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)には、運用環境での ASP.NET Core アプリの実行用にビルドされたイメージが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5605a-176">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="5605a-177">Docker コンテナー内で .NET Core を使用する方法の詳細については、「[.NET および Docker の概要](../docker/introduction.md)」と[サンプル](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5605a-177">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5605a-178">次の手順</span><span class="sxs-lookup"><span data-stu-id="5605a-178">Next steps</span></span>

- <span data-ttu-id="5605a-179">[.NET Core が既にインストールされているかどうかを確認する方法](how-to-detect-installed-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="5605a-179">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
