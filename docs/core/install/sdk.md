---
title: Windows、Linux、および macOS に .NET Core SDK をインストールする - .NET Core
description: Windows、Linux、および macOS に .NET Core をインストールする方法について説明します。 .NET Core アプリの開発に必要な依存関係を確認します。
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 0aa323533dd9136372c2bbc330c9c3056fdf428c
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157572"
---
# <a name="install-the-net-core-sdk"></a><span data-ttu-id="aeac3-104">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="aeac3-104">Install the .NET Core SDK</span></span>

<span data-ttu-id="aeac3-105">この記事では、.NET Core SDK をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aeac3-105">In this article, you'll learn how to install the .NET Core SDK.</span></span> <span data-ttu-id="aeac3-106">.NET Core SDK は、.NET Core アプリとライブラリの作成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-106">The .NET Core SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="aeac3-107">.NET Core ランタイムは、常に SDK と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-107">The .NET Core runtime is always installed with the SDK.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="aeac3-108">インストーラーを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="aeac3-108">Install with an installer</span></span>

<span data-ttu-id="aeac3-109">Windows には、.NET Core 3.1 SDK のインストールに使用できるスタンドアロン インストーラーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="aeac3-109">Windows has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="aeac3-110">x64 (64 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="aeac3-110">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="aeac3-111">x86 (32 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="aeac3-111">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="aeac3-112">インストーラーを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="aeac3-112">Install with an installer</span></span>

<span data-ttu-id="aeac3-113">macOS には、.NET Core 3.1 SDK のインストールに使用できるスタンドアロン インストーラーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="aeac3-113">macOS has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="aeac3-114">x64 (64 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="aeac3-114">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="aeac3-115">手動でダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="aeac3-115">Download and manually install</span></span>

<span data-ttu-id="aeac3-116">.NET Core 用 macOS インストーラーの代わりに、SDK をダウンロードして手動でインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-116">As an alternative to the macOS installers for .NET Core, you can download and manually install the SDK.</span></span>

<span data-ttu-id="aeac3-117">SDK を抽出し、.NET Core CLI コマンドをターミナルで使用できるようにするには、最初に .NET Core のバイナリ リリースを[ダウンロード](#all-net-core-downloads)します。</span><span class="sxs-lookup"><span data-stu-id="aeac3-117">To extract the SDK and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="aeac3-118">次に、ターミナルを開き、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aeac3-118">Then, open a terminal and run the following commands.</span></span> <span data-ttu-id="aeac3-119">ランタイムが `~/Downloads/dotnet-sdk.pkg` ファイルにダウンロードされることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="aeac3-119">It's assumed the runtime is downloaded to the `~/Downloads/dotnet-sdk.pkg` file.</span></span>

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-sdk.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="aeac3-120">パッケージ マネージャーを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="aeac3-120">Install with a package manager</span></span>

<span data-ttu-id="aeac3-121">多くの一般的な Linux パッケージ マネージャーを使用して、.NET Core SDK をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-121">You can install the .NET Core SDK with many of the common Linux package managers.</span></span> <span data-ttu-id="aeac3-122">詳細については、[Linux パッケージ マネージャー - .NET Core のインストール](linux-package-managers.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aeac3-122">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

<span data-ttu-id="aeac3-123">パッケージ マネージャーを使用したインストールは、x64 アーキテクチャでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="aeac3-123">Installing with a package manager is only supported on the x64 architecture.</span></span> <span data-ttu-id="aeac3-124">ARM などの別のアーキテクチャを使用して .NET Core SDK をインストールする場合は、以下の「[手動でダウンロードしてインストールする](#download-and-manually-install)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="aeac3-124">If you're installing the .NET Core SDK with a different architecture, such as ARM, follow the [Download and manually install](#download-and-manually-install) instructions below.</span></span> <span data-ttu-id="aeac3-125">サポートされているアーキテクチャの詳細については、「[.NET Core の依存関係と要件](dependencies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aeac3-125">For more information about what architectures are supported, see [.NET Core dependencies and requirements](dependencies.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="aeac3-126">手動でダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="aeac3-126">Download and manually install</span></span>

<span data-ttu-id="aeac3-127">SDK を抽出し、.NET Core CLI コマンドをターミナルで使用できるようにするには、最初に .NET Core のバイナリ リリースを[ダウンロード](#all-net-core-downloads)します。</span><span class="sxs-lookup"><span data-stu-id="aeac3-127">To extract the SDK and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="aeac3-128">次に、ターミナルを開き、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="aeac3-128">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf dotnet-sdk-3.1.100-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="aeac3-129">上記の `export` コマンドでは、それを実行したターミナル セッションでのみ .NET Core CLI コマンドを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="aeac3-129">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="aeac3-130">シェル プロファイルを編集して、コマンドを永続的に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-130">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="aeac3-131">Linux ではさまざまなシェルを使用でき、それぞれに異なるプロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="aeac3-131">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="aeac3-132">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="aeac3-132">For example:</span></span>
>
> - <span data-ttu-id="aeac3-133">**Bash シェル**: *~/.bash_profile*、 *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="aeac3-133">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="aeac3-134">**Korn シェル**: *~/.kshrc* または *.profile*</span><span class="sxs-lookup"><span data-stu-id="aeac3-134">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="aeac3-135">**Z シェル**: *~/.zshrc* または *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="aeac3-135">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="aeac3-136">シェルの適切なソース ファイルを編集し、既存の `PATH` ステートメントの末尾に `:$HOME/dotnet` を追加します。</span><span class="sxs-lookup"><span data-stu-id="aeac3-136">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="aeac3-137">`PATH` ステートメントが含まれていない場合は、`export PATH=$PATH:$HOME/dotnet` を含む新しい行を追加します。</span><span class="sxs-lookup"><span data-stu-id="aeac3-137">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="aeac3-138">また、ファイルの末尾に `export DOTNET_ROOT=$HOME/dotnet` を追加します。</span><span class="sxs-lookup"><span data-stu-id="aeac3-138">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a><span data-ttu-id="aeac3-139">Visual Studio を使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="aeac3-139">Install with Visual Studio</span></span>

<span data-ttu-id="aeac3-140">次の表では、Visual Studio を使用して .NET Core アプリを開発している場合に、ターゲットの .NET Core SDK バージョンに基づいて最低限必要な Visual Studio のバージョンを説明します。</span><span class="sxs-lookup"><span data-stu-id="aeac3-140">If you're using Visual Studio to develop .NET Core apps, the following table describes the minimum required version of Visual Studio based on the target .NET Core SDK version.</span></span>

| <span data-ttu-id="aeac3-141">.NET Core SDK のバージョン</span><span class="sxs-lookup"><span data-stu-id="aeac3-141">.NET Core SDK version</span></span> | <span data-ttu-id="aeac3-142">Visual Studio のバージョン</span><span class="sxs-lookup"><span data-stu-id="aeac3-142">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="aeac3-143">3.1</span><span class="sxs-lookup"><span data-stu-id="aeac3-143">3.1</span></span>                   | <span data-ttu-id="aeac3-144">Visual Studio 2019 バージョン 16.4 以降。</span><span class="sxs-lookup"><span data-stu-id="aeac3-144">Visual Studio 2019 version 16.4 or higher.</span></span> |
| <span data-ttu-id="aeac3-145">3.0</span><span class="sxs-lookup"><span data-stu-id="aeac3-145">3.0</span></span>                   | <span data-ttu-id="aeac3-146">Visual Studio 2019 バージョン 16.3 以降。</span><span class="sxs-lookup"><span data-stu-id="aeac3-146">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="aeac3-147">2.2</span><span class="sxs-lookup"><span data-stu-id="aeac3-147">2.2</span></span>                   | <span data-ttu-id="aeac3-148">Visual Studio 2017 バージョン 15.9 以降。</span><span class="sxs-lookup"><span data-stu-id="aeac3-148">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="aeac3-149">2.1</span><span class="sxs-lookup"><span data-stu-id="aeac3-149">2.1</span></span>                   | <span data-ttu-id="aeac3-150">Visual Studio 2017 バージョン 15.7 以降。</span><span class="sxs-lookup"><span data-stu-id="aeac3-150">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="aeac3-151">Visual Studio を既にインストールしてある場合は、次の手順でバージョンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-151">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="aeac3-152">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-152">Open Visual Studio.</span></span>
01. <span data-ttu-id="aeac3-153">**[ヘルプ]**  >  **[Microsoft Visual Studio のバージョン情報]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aeac3-153">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="aeac3-154">**[バージョン情報]** ダイアログで、バージョン番号を確認します。</span><span class="sxs-lookup"><span data-stu-id="aeac3-154">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="aeac3-155">Visual Studio では、最新の .NET Core SDK とランタイムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-155">Visual Studio can install the latest .NET Core SDK and runtime.</span></span>

- <span data-ttu-id="aeac3-156">[Visual Studio をダウンロードします](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)。</span><span class="sxs-lookup"><span data-stu-id="aeac3-156">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="aeac3-157">ワークロードを選択する</span><span class="sxs-lookup"><span data-stu-id="aeac3-157">Select a workload</span></span>

<span data-ttu-id="aeac3-158">Visual Studio をインストールまたは変更するときは、ビルドするアプリケーションの種類に応じて、次の 1 つ以上のワークロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="aeac3-158">When installing or modifying Visual Studio, select one or more of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="aeac3-159">**[他のツールセット]** セクションの **[.NET Core クロスプラットフォームの開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="aeac3-159">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="aeac3-160">**[Web クラウド]** セクションの **[ASP.NET と Web 開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="aeac3-160">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="aeac3-161">**[Web クラウド]** セクションの **[Azure の開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="aeac3-161">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="aeac3-162">**[デスクトップとモバイル]** セクションの **[.NET デスクトップ開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="aeac3-162">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="aeac3-163">[![Windows Visual Studio 2019 と .NET Core ワークロード](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="aeac3-163">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="aeac3-164">手動でダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="aeac3-164">Download and manually install</span></span>

<span data-ttu-id="aeac3-165">ランタイムを抽出し、.NET Core CLI コマンドをターミナルで使用できるようにするには、最初に .NET Core のバイナリ リリースを[ダウンロード](#all-net-core-downloads)します。</span><span class="sxs-lookup"><span data-stu-id="aeac3-165">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="aeac3-166">次に、インストール先のディレクトリ (`%USERPROFILE%\dotnet` など) を作成します。</span><span class="sxs-lookup"><span data-stu-id="aeac3-166">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="aeac3-167">最後に、ダウンロードした zip ファイルをそのディレクトリに抽出します。</span><span class="sxs-lookup"><span data-stu-id="aeac3-167">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="aeac3-168">既定では、.NET Core CLI コマンドおよびアプリでは、この方法でインストールされた .NET Core は使用されません。</span><span class="sxs-lookup"><span data-stu-id="aeac3-168">By default, .NET Core CLI commands and apps will not use .NET Core installed in this way.</span></span> <span data-ttu-id="aeac3-169">使用するには、明示的に選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeac3-169">You have to explicitly choose to use it.</span></span> <span data-ttu-id="aeac3-170">これを行うには、アプリケーションの起動に使用する環境変数を変更します。</span><span class="sxs-lookup"><span data-stu-id="aeac3-170">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="aeac3-171">この方法では、複数のバージョンを別々の場所にインストールして、その場所を参照する環境変数を使ってアプリケーションを実行することで、アプリケーションによって使用されるインストール場所を明示的に選択できます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-171">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="aeac3-172">これらの環境変数が設定されている場合でも、.NET Core では、アプリケーションを実行するための最適なフレームワークを選択するときに、既定のグローバル インストールの場所が引き続き考慮されます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-172">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="aeac3-173">既定値は通常、インストーラーによって使用される `C:\Program Files\dotnet` です。</span><span class="sxs-lookup"><span data-stu-id="aeac3-173">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="aeac3-174">この環境変数の設定も行うことで、カスタムのインストール場所のみを使用するように、ランタイムに指示できます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-174">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="aeac3-175">Visual Studio for Mac を使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="aeac3-175">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="aeac3-176">Visual Studio for Mac では、 **[.NET Core]** ワークロードを選択すると、.NET Core SDK がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-176">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="aeac3-177">macOS で .NET Core の開発を始めるには、「[Visual Studio 2019 for Mac をインストールする](/visualstudio/mac/installation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aeac3-177">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span> <span data-ttu-id="aeac3-178">最新リリースである .NET Core 3.1 の場合は、Visual Studio for Mac 8.4 Preview を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeac3-178">For the latest release, .NET Core 3.1, you must use the Visual Studio for Mac 8.4 Preview.</span></span>

<span data-ttu-id="aeac3-179">[![macOS Visual Studio 2019 for Mac と .NET Core ワークロード機能](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="aeac3-179">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

::: zone-end

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="aeac3-180">Visual Studio Code と共にインストールする</span><span class="sxs-lookup"><span data-stu-id="aeac3-180">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="aeac3-181">Visual Studio Code は、デスクトップ上で動作する強力で軽量なソース コード エディターです。</span><span class="sxs-lookup"><span data-stu-id="aeac3-181">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="aeac3-182">Visual Studio Code は、Windows、macOS、Linux で利用できます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-182">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="aeac3-183">Visual Studio Code には、Visual Studio のような自動化された .NET Core インストーラーは付属していませんが、.NET Core のサポートを簡単に追加できます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-183">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="aeac3-184">[Visual Studio Code をダウンロードしてインストールします](https://code.visualstudio.com/Download)。</span><span class="sxs-lookup"><span data-stu-id="aeac3-184">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="aeac3-185">[.NET Core SDK をダウンロードしてインストールします](https://dotnet.microsoft.com/download/dotnet-core)。</span><span class="sxs-lookup"><span data-stu-id="aeac3-185">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="aeac3-186">[Visual Studio Code マーケットプレースから C# 拡張機能をインストールします](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)。</span><span class="sxs-lookup"><span data-stu-id="aeac3-186">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span>

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="aeac3-187">PowerShell オートメーションを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="aeac3-187">Install with PowerShell automation</span></span>

<span data-ttu-id="aeac3-188">[dotnet-install スクリプト](../tools/dotnet-install-script.md)は、SDK のインストールの自動化および管理者以外によるインストールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-188">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="aeac3-189">スクリプトは、[dotnet-install スクリプト参照ページ](../tools/dotnet-install-script.md)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-189">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="aeac3-190">スクリプトでは、既定で最新の [長期サポート (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) バージョン (.NET Core 3.1) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-190">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="aeac3-191">NET Core の最新リリースをインストールするには、次のスイッチを使用してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="aeac3-191">To install the current release of .NET Core, run the script with the following switch.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="aeac3-192">bash オートメーションを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="aeac3-192">Install with bash automation</span></span>

<span data-ttu-id="aeac3-193">[dotnet-install スクリプト](../tools/dotnet-install-script.md)は、SDK のインストールの自動化および管理者以外によるインストールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-193">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="aeac3-194">スクリプトは、[dotnet-install スクリプト参照ページ](../tools/dotnet-install-script.md)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-194">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="aeac3-195">スクリプトでは、既定で最新の [長期サポート (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) バージョン (.NET Core 3.1) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-195">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="aeac3-196">NET Core の最新リリースをインストールするには、次のスイッチを使用してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="aeac3-196">To install the current release of .NET Core, run the script with the following switch.</span></span>

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="aeac3-197">すべての .NET Core のダウンロード</span><span class="sxs-lookup"><span data-stu-id="aeac3-197">All .NET Core downloads</span></span>

<span data-ttu-id="aeac3-198">次のいずれかのリンクを使用して、.NET Core を直接ダウンロードしてインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-198">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="aeac3-199">.NET Core 3.1 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="aeac3-199">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="aeac3-200">.NET Core 3.0 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="aeac3-200">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="aeac3-201">.NET Core 2.2 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="aeac3-201">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="aeac3-202">.NET Core 2.1 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="aeac3-202">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="aeac3-203">Docker</span><span class="sxs-lookup"><span data-stu-id="aeac3-203">Docker</span></span>

<span data-ttu-id="aeac3-204">コンテナーを使用すると、アプリケーションをホスト システムの他の部分から簡単に分離できます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-204">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="aeac3-205">同じコンピューター上のコンテナーでは、カーネルだけが共有され、アプリケーションに提供されたリソースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-205">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="aeac3-206">.NET Core は Docker コンテナー内で実行できます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-206">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="aeac3-207">公式の .NET Core Docker イメージは Microsoft Container Registry (MCR) に公開され、[Microsoft .NET Core の Docker Hub リポジトリ](https://hub.docker.com/_/microsoft-dotnet-core/)で見つけられます。</span><span class="sxs-lookup"><span data-stu-id="aeac3-207">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="aeac3-208">各リポジトリには、.NET (SDK またはランタイム) と自分が使用できる OS のさまざまな組み合わせのイメージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="aeac3-208">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="aeac3-209">Microsoft は、特定のシナリオに対応したイメージを用意しています。</span><span class="sxs-lookup"><span data-stu-id="aeac3-209">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="aeac3-210">たとえば、[ASP.NET Core リポジトリ](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)には、運用環境での ASP.NET Core アプリの実行用にビルドされたイメージが用意されています。</span><span class="sxs-lookup"><span data-stu-id="aeac3-210">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="aeac3-211">Docker コンテナー内で .NET Core を使用する方法の詳細については、「[.NET および Docker の概要](../docker/introduction.md)」と[サンプル](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aeac3-211">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="aeac3-212">次の手順</span><span class="sxs-lookup"><span data-stu-id="aeac3-212">Next steps</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="aeac3-213">[チュートリアル: Hello World チュートリアル](../tutorials/with-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="aeac3-213">[Tutorial: Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="aeac3-214">[チュートリアル: Visual Studio Code を使用して新しいアプリを作成する](../tutorials/with-visual-studio-code.md)。</span><span class="sxs-lookup"><span data-stu-id="aeac3-214">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="aeac3-215">[チュートリアル: NET Core アプリをコンテナー化する](../docker/build-container.md)。</span><span class="sxs-lookup"><span data-stu-id="aeac3-215">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="aeac3-216">[macOS Catalina の公証に対応する](macos-notarization-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="aeac3-216">[Working with macOS Catalina notarization](macos-notarization-issues.md).</span></span>
- <span data-ttu-id="aeac3-217">[チュートリアル: macOS での作業を始める](../tutorials/using-on-mac-vs.md).</span><span class="sxs-lookup"><span data-stu-id="aeac3-217">[Tutorial: Get started on macOS](../tutorials/using-on-mac-vs.md).</span></span>
- <span data-ttu-id="aeac3-218">[チュートリアル: Visual Studio Code を使用して新しいアプリを作成する](../tutorials/with-visual-studio-code.md)。</span><span class="sxs-lookup"><span data-stu-id="aeac3-218">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="aeac3-219">[チュートリアル: NET Core アプリをコンテナー化する](../docker/build-container.md)。</span><span class="sxs-lookup"><span data-stu-id="aeac3-219">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-linux"

- <span data-ttu-id="aeac3-220">[チュートリアル: Visual Studio Code を使用して新しいアプリを作成する](../tutorials/with-visual-studio-code.md)。</span><span class="sxs-lookup"><span data-stu-id="aeac3-220">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="aeac3-221">[チュートリアル: NET Core アプリをコンテナー化する](../docker/build-container.md)。</span><span class="sxs-lookup"><span data-stu-id="aeac3-221">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end
