---
title: Windows、Linux、および macOS に .NET Core ランタイムをインストールする - .NET Core
description: Windows、Linux、および macOS に .NET Core をインストールする方法について説明します。 .NET Core アプリの実行に必要な依存関係を確認します。
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: d36909e06bd9a3de0940c4c1b2b9eacbf9cafe7f
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740590"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="e8bf1-104">.NET Core ランタイムのインストール</span><span class="sxs-lookup"><span data-stu-id="e8bf1-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="e8bf1-105">この記事では、.NET Core ランタイムをダウンロードしてインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="e8bf1-106">.Net Core ランタイムは、.NET Core で作成されたアプリを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="e8bf1-107">インストーラーを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="e8bf1-107">Install with an installer</span></span>

<span data-ttu-id="e8bf1-108">Windows には、.NET Core 3.1 ランタイムのインストールに使用できるスタンドアロン インストーラーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="e8bf1-109">x64 (64 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="e8bf1-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="e8bf1-110">x86 (32 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="e8bf1-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="e8bf1-111">インストーラーを使用したインストール</span><span class="sxs-lookup"><span data-stu-id="e8bf1-111">Install with an installer</span></span>

<span data-ttu-id="e8bf1-112">macOS には、.NET Core 3.1 ランタイムのインストールに使用できるスタンドアロン インストーラーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="e8bf1-113">x64 (64 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="e8bf1-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="e8bf1-114">パッケージ マネージャーを使用したインストール</span><span class="sxs-lookup"><span data-stu-id="e8bf1-114">Install with a package manager</span></span>

<span data-ttu-id="e8bf1-115">多くの一般的な Linux パッケージ マネージャーを使用して .NET Core ランタイムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-115">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="e8bf1-116">詳細については、[Linux パッケージ マネージャー - .NET Core のインストール](linux-package-managers.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-116">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

<span data-ttu-id="e8bf1-117">パッケージ マネージャーを使用したインストールは、x64 アーキテクチャでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-117">Installing it with a package manager is only supported on the x64 architecture.</span></span> <span data-ttu-id="e8bf1-118">ARM などの別のアーキテクチャを使用して .NET Core ランタイムをインストールする場合は、「[手動でダウンロードしてインストールする](#download-and-manually-install)」セクションの手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-118">If you're installing the .NET Core Runtime with a different architecture, such as ARM, follow the instructions on the [Download and manually install](#download-and-manually-install) section.</span></span> <span data-ttu-id="e8bf1-119">サポートされているアーキテクチャの詳細については、「[.NET Core の依存関係と要件](dependencies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-119">For more information about what architectures are supported, see [.NET Core dependencies and requirements](dependencies.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="e8bf1-120">手動でダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="e8bf1-120">Download and manually install</span></span>

<span data-ttu-id="e8bf1-121">ランタイムを抽出し、.NET Core CLI コマンドをターミナルで使用できるようにするには、最初に .NET Core のバイナリ リリースを[ダウンロード](#all-net-core-downloads)します。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-121">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="e8bf1-122">次に、ターミナルを開き、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-122">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="e8bf1-123">上記の `export` コマンドでは、それを実行したターミナル セッションでのみ .NET Core CLI コマンドを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-123">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="e8bf1-124">シェル プロファイルを編集して、コマンドを永続的に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-124">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="e8bf1-125">Linux ではさまざまなシェルを使用でき、それぞれに異なるプロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-125">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="e8bf1-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-126">For example:</span></span>
>
> - <span data-ttu-id="e8bf1-127">**Bash シェル**: *~/.bash_profile*、 *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="e8bf1-127">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="e8bf1-128">**Korn シェル**: *~/.kshrc* または *.profile*</span><span class="sxs-lookup"><span data-stu-id="e8bf1-128">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="e8bf1-129">**Z シェル**: *~/.zshrc* または *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="e8bf1-129">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
> 
> <span data-ttu-id="e8bf1-130">シェルの適切なソース ファイルを編集し、既存の `PATH` ステートメントの末尾に `:$HOME/dotnet` を追加します。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-130">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="e8bf1-131">`PATH` ステートメントが含まれていない場合は、`export PATH=$PATH:$HOME/dotnet` を含む新しい行を追加します。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-131">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="e8bf1-132">また、ファイルの末尾に `export DOTNET_ROOT=$HOME/dotnet` を追加します。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-132">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="e8bf1-133">PowerShell オートメーションを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="e8bf1-133">Install with PowerShell automation</span></span>

<span data-ttu-id="e8bf1-134">[dotnet-install スクリプト](../tools/dotnet-install-script.md)は、ランタイムの自動化および管理者以外によるインストールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-134">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="e8bf1-135">スクリプトは、[dotnet-install スクリプト参照ページ](../tools/dotnet-install-script.md)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-135">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="e8bf1-136">スクリプトでは、既定で最新の [長期サポート (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) バージョン (.NET Core 3.1) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-136">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="e8bf1-137">`Channel` スイッチを指定することで、特定のリリースを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-137">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="e8bf1-138">ランタイムをインストールするには、`Runtime` スイッチを含めます。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-138">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="e8bf1-139">それ以外の場合は、スクリプトによって [SDK](sdk.md) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-139">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="e8bf1-140">上のコマンドでは、互換性を最大限に高めるために ASP.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-140">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="e8bf1-141">ASP.NET Core ランタイムには、標準の .NET Core ランタイムも含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-141">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="e8bf1-142">bash オートメーションを使用したインストール</span><span class="sxs-lookup"><span data-stu-id="e8bf1-142">Install with bash automation</span></span>

<span data-ttu-id="e8bf1-143">[dotnet-install スクリプト](../tools/dotnet-install-script.md)は、ランタイムの自動化および管理者以外によるインストールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-143">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="e8bf1-144">スクリプトは、[dotnet-install スクリプト参照ページ](../tools/dotnet-install-script.md)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-144">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="e8bf1-145">スクリプトでは、既定で最新の [長期サポート (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) バージョン (.NET Core 3.1) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-145">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="e8bf1-146">`current` スイッチを指定することで、特定のリリースを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-146">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="e8bf1-147">ランタイムをインストールするには、`runtime` スイッチを含めます。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-147">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="e8bf1-148">それ以外の場合は、スクリプトによって [SDK](sdk.md) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-148">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="e8bf1-149">上のコマンドでは、互換性を最大限に高めるために ASP.NET Core ランタイムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-149">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="e8bf1-150">ASP.NET Core ランタイムには、標準の .NET Core ランタイムも含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-150">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="e8bf1-151">すべての .NET Core のダウンロード</span><span class="sxs-lookup"><span data-stu-id="e8bf1-151">All .NET Core downloads</span></span>

<span data-ttu-id="e8bf1-152">次のいずれかのリンクを使用して、.NET Core を直接ダウンロードしてインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-152">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="e8bf1-153">.NET Core 3.1 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="e8bf1-153">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="e8bf1-154">.NET Core 3.0 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="e8bf1-154">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="e8bf1-155">.NET Core 2.2 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="e8bf1-155">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="e8bf1-156">.NET Core 2.1 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="e8bf1-156">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="e8bf1-157">Docker</span><span class="sxs-lookup"><span data-stu-id="e8bf1-157">Docker</span></span>

<span data-ttu-id="e8bf1-158">コンテナーを使用すると、アプリケーションをホスト システムの他の部分から簡単に分離できます。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-158">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="e8bf1-159">同じコンピューター上のコンテナーでは、カーネルだけが共有され、アプリケーションに提供されたリソースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-159">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="e8bf1-160">.NET Core は Docker コンテナー内で実行できます。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-160">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="e8bf1-161">公式の .NET Core Docker イメージは Microsoft Container Registry (MCR) に公開され、[Microsoft .NET Core の Docker Hub リポジトリ](https://hub.docker.com/_/microsoft-dotnet-core/)で見つけられます。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-161">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="e8bf1-162">各リポジトリには、.NET (SDK またはランタイム) と自分が使用できる OS のさまざまな組み合わせのイメージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-162">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="e8bf1-163">Microsoft は、特定のシナリオに対応したイメージを用意しています。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-163">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="e8bf1-164">たとえば、[ASP.NET Core リポジトリ](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)には、運用環境での ASP.NET Core アプリの実行用にビルドされたイメージが用意されています。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-164">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="e8bf1-165">Docker コンテナー内で .NET Core を使用する方法の詳細については、「[.NET および Docker の概要](../docker/introduction.md)」と[サンプル](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-165">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="e8bf1-166">次の手順</span><span class="sxs-lookup"><span data-stu-id="e8bf1-166">Next steps</span></span>

- <span data-ttu-id="e8bf1-167">[.NET Core が既にインストールされているかどうかを確認する方法](how-to-detect-installed-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="e8bf1-167">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
