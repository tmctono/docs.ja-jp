---
title: Windows、Linux、および macOS に .NET Core SDK をインストールする - .NET Core
description: Windows、Linux、および macOS に .NET Core をインストールする方法について説明します。 .NET Core アプリの開発に必要な依存関係を確認します。
author: thraka
ms.author: adegeo
ms.date: 05/04/2020
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 9b170765740600641f96056adc08ff0b69a03338
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768315"
---
# <a name="install-the-net-core-sdk"></a><span data-ttu-id="0f70c-104">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="0f70c-104">Install the .NET Core SDK</span></span>

<span data-ttu-id="0f70c-105">この記事では、.NET Core SDK をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0f70c-105">In this article, you'll learn how to install the .NET Core SDK.</span></span> <span data-ttu-id="0f70c-106">.NET Core SDK は、.NET Core アプリとライブラリの作成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-106">The .NET Core SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="0f70c-107">.NET Core ランタイムは、常に SDK と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-107">The .NET Core runtime is always installed with the SDK.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="0f70c-108">インストーラーを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="0f70c-108">Install with an installer</span></span>

<span data-ttu-id="0f70c-109">Windows には、.NET Core 3.1 SDK のインストールに使用できるスタンドアロン インストーラーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="0f70c-109">Windows has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="0f70c-110">x64 (64 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="0f70c-110">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="0f70c-111">x86 (32 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="0f70c-111">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="0f70c-112">インストーラーを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="0f70c-112">Install with an installer</span></span>

<span data-ttu-id="0f70c-113">macOS には、.NET Core 3.1 SDK のインストールに使用できるスタンドアロン インストーラーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="0f70c-113">macOS has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="0f70c-114">x64 (64 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="0f70c-114">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="0f70c-115">手動でダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="0f70c-115">Download and manually install</span></span>

<span data-ttu-id="0f70c-116">.NET Core 用 macOS インストーラーの代わりに、SDK をダウンロードして手動でインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-116">As an alternative to the macOS installers for .NET Core, you can download and manually install the SDK.</span></span>

<span data-ttu-id="0f70c-117">SDK を抽出し、.NET Core CLI コマンドをターミナルで使用できるようにするには、最初に .NET Core のバイナリ リリースを[ダウンロード](#all-net-core-downloads)します。</span><span class="sxs-lookup"><span data-stu-id="0f70c-117">To extract the SDK and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="0f70c-118">次に、ターミナルを開き、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0f70c-118">Then, open a terminal and run the following commands.</span></span> <span data-ttu-id="0f70c-119">ランタイムが `~/Downloads/dotnet-sdk.pkg` ファイルにダウンロードされることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0f70c-119">It's assumed the runtime is downloaded to the `~/Downloads/dotnet-sdk.pkg` file.</span></span>

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-sdk.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-on-linux"></a><span data-ttu-id="0f70c-120">Linux にインストールする</span><span class="sxs-lookup"><span data-stu-id="0f70c-120">Install on Linux</span></span>

<span data-ttu-id="0f70c-121">この記事は間もなく削除されます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-121">This article will be removed soon.</span></span> <span data-ttu-id="0f70c-122">現在、「[Linux に .NET Core をインストールする](linux.md)」に置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="0f70c-122">It is currently replaced by [Install .NET Core on Linux](linux.md).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a><span data-ttu-id="0f70c-123">Visual Studio を使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="0f70c-123">Install with Visual Studio</span></span>

<span data-ttu-id="0f70c-124">次の表では、Visual Studio を使用して .NET Core アプリを開発している場合に、ターゲットの .NET Core SDK バージョンに基づいて最低限必要な Visual Studio のバージョンを説明します。</span><span class="sxs-lookup"><span data-stu-id="0f70c-124">If you're using Visual Studio to develop .NET Core apps, the following table describes the minimum required version of Visual Studio based on the target .NET Core SDK version.</span></span>

| <span data-ttu-id="0f70c-125">.NET Core SDK のバージョン</span><span class="sxs-lookup"><span data-stu-id="0f70c-125">.NET Core SDK version</span></span> | <span data-ttu-id="0f70c-126">Visual Studio のバージョン</span><span class="sxs-lookup"><span data-stu-id="0f70c-126">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="0f70c-127">3.1</span><span class="sxs-lookup"><span data-stu-id="0f70c-127">3.1</span></span>                   | <span data-ttu-id="0f70c-128">Visual Studio 2019 バージョン 16.4 以降。</span><span class="sxs-lookup"><span data-stu-id="0f70c-128">Visual Studio 2019 version 16.4 or higher.</span></span> |
| <span data-ttu-id="0f70c-129">3.0</span><span class="sxs-lookup"><span data-stu-id="0f70c-129">3.0</span></span>                   | <span data-ttu-id="0f70c-130">Visual Studio 2019 バージョン 16.3 以降。</span><span class="sxs-lookup"><span data-stu-id="0f70c-130">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="0f70c-131">2.2</span><span class="sxs-lookup"><span data-stu-id="0f70c-131">2.2</span></span>                   | <span data-ttu-id="0f70c-132">Visual Studio 2017 バージョン 15.9 以降。</span><span class="sxs-lookup"><span data-stu-id="0f70c-132">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="0f70c-133">2.1</span><span class="sxs-lookup"><span data-stu-id="0f70c-133">2.1</span></span>                   | <span data-ttu-id="0f70c-134">Visual Studio 2017 バージョン 15.7 以降。</span><span class="sxs-lookup"><span data-stu-id="0f70c-134">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="0f70c-135">Visual Studio を既にインストールしてある場合は、次の手順でバージョンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-135">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="0f70c-136">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-136">Open Visual Studio.</span></span>
01. <span data-ttu-id="0f70c-137">**[ヘルプ]**  >  **[Microsoft Visual Studio のバージョン情報]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f70c-137">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="0f70c-138">**[バージョン情報]** ダイアログで、バージョン番号を確認します。</span><span class="sxs-lookup"><span data-stu-id="0f70c-138">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="0f70c-139">Visual Studio では、最新の .NET Core SDK とランタイムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-139">Visual Studio can install the latest .NET Core SDK and runtime.</span></span>

- <span data-ttu-id="0f70c-140">[Visual Studio をダウンロードします](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)。</span><span class="sxs-lookup"><span data-stu-id="0f70c-140">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="0f70c-141">ワークロードを選択する</span><span class="sxs-lookup"><span data-stu-id="0f70c-141">Select a workload</span></span>

<span data-ttu-id="0f70c-142">Visual Studio をインストールまたは変更するときは、ビルドするアプリケーションの種類に応じて、次の 1 つ以上のワークロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f70c-142">When installing or modifying Visual Studio, select one or more of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="0f70c-143">**[他のツールセット]** セクションの **[.NET Core クロスプラットフォームの開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="0f70c-143">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="0f70c-144">**[Web クラウド]** セクションの **[ASP.NET と Web 開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="0f70c-144">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="0f70c-145">**[Web クラウド]** セクションの **[Azure の開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="0f70c-145">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="0f70c-146">**[デスクトップとモバイル]** セクションの **[.NET デスクトップ開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="0f70c-146">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="0f70c-147">[![Windows Visual Studio 2019 と .NET Core ワークロード](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="0f70c-147">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="0f70c-148">手動でダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="0f70c-148">Download and manually install</span></span>

<span data-ttu-id="0f70c-149">ランタイムを抽出し、.NET Core CLI コマンドをターミナルで使用できるようにするには、最初に .NET Core のバイナリ リリースを[ダウンロード](#all-net-core-downloads)します。</span><span class="sxs-lookup"><span data-stu-id="0f70c-149">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="0f70c-150">次に、インストール先のディレクトリ (`%USERPROFILE%\dotnet` など) を作成します。</span><span class="sxs-lookup"><span data-stu-id="0f70c-150">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="0f70c-151">最後に、ダウンロードした zip ファイルをそのディレクトリに抽出します。</span><span class="sxs-lookup"><span data-stu-id="0f70c-151">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="0f70c-152">既定では、.NET Core CLI コマンドおよびアプリでは、この方法でインストールされた .NET Core は使用されません。使用することを明示的に選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f70c-152">By default, .NET Core CLI commands and apps won't use .NET Core installed in this way and you must explicitly choose to use it.</span></span> <span data-ttu-id="0f70c-153">これを行うには、アプリケーションの起動に使用する環境変数を変更します。</span><span class="sxs-lookup"><span data-stu-id="0f70c-153">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="0f70c-154">この方法では、複数のバージョンを別々の場所にインストールして、その場所を参照する環境変数を使ってアプリケーションを実行することで、アプリケーションによって使用されるインストール場所を明示的に選択できます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-154">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="0f70c-155">これらの環境変数が設定されている場合でも、.NET Core では、アプリケーションを実行するための最適なフレームワークを選択するときに、既定のグローバル インストールの場所が引き続き考慮されます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-155">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="0f70c-156">既定値は通常、インストーラーによって使用される `C:\Program Files\dotnet` です。</span><span class="sxs-lookup"><span data-stu-id="0f70c-156">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="0f70c-157">この環境変数の設定も行うことで、カスタムのインストール場所のみを使用するように、ランタイムに指示できます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-157">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="0f70c-158">Visual Studio for Mac を使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="0f70c-158">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="0f70c-159">Visual Studio for Mac では、 **[.NET Core]** ワークロードを選択すると、.NET Core SDK がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-159">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="0f70c-160">macOS で .NET Core の開発を始めるには、「[Visual Studio 2019 for Mac をインストールする](/visualstudio/mac/installation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f70c-160">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span> <span data-ttu-id="0f70c-161">最新リリースである .NET Core 3.1 の場合は、Visual Studio for Mac 8.4 Preview を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f70c-161">For the latest release, .NET Core 3.1, you must use the Visual Studio for Mac 8.4 Preview.</span></span>

<span data-ttu-id="0f70c-162">[![macOS Visual Studio 2019 for Mac と .NET Core ワークロード機能](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="0f70c-162">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

::: zone-end

::: zone pivot="os-windows,os-macos"

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="0f70c-163">Visual Studio Code と共にインストールする</span><span class="sxs-lookup"><span data-stu-id="0f70c-163">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="0f70c-164">Visual Studio Code は、デスクトップ上で動作する強力で軽量なソース コード エディターです。</span><span class="sxs-lookup"><span data-stu-id="0f70c-164">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="0f70c-165">Visual Studio Code は、Windows、macOS、Linux で利用できます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-165">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="0f70c-166">Visual Studio Code には、Visual Studio のような自動化された .NET Core インストーラーは付属していませんが、.NET Core のサポートを簡単に追加できます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-166">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="0f70c-167">[Visual Studio Code をダウンロードしてインストールします](https://code.visualstudio.com/Download)。</span><span class="sxs-lookup"><span data-stu-id="0f70c-167">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="0f70c-168">[.NET Core SDK をダウンロードしてインストールします](https://dotnet.microsoft.com/download/dotnet-core)。</span><span class="sxs-lookup"><span data-stu-id="0f70c-168">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="0f70c-169">[Visual Studio Code マーケットプレースから C# 拡張機能をインストールします](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)。</span><span class="sxs-lookup"><span data-stu-id="0f70c-169">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="0f70c-170">PowerShell オートメーションを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="0f70c-170">Install with PowerShell automation</span></span>

<span data-ttu-id="0f70c-171">[dotnet-install スクリプト](../tools/dotnet-install-script.md)は、SDK のインストールの自動化および管理者以外によるインストールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-171">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="0f70c-172">スクリプトは、[dotnet-install スクリプト参照ページ](../tools/dotnet-install-script.md)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-172">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="0f70c-173">スクリプトでは、既定で最新の [長期サポート (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) バージョン (.NET Core 3.1) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-173">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="0f70c-174">NET Core の最新リリースをインストールするには、次のスイッチを使用してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="0f70c-174">To install the current release of .NET Core, run the script with the following switch.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="0f70c-175">bash オートメーションを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="0f70c-175">Install with bash automation</span></span>

<span data-ttu-id="0f70c-176">[dotnet-install スクリプト](../tools/dotnet-install-script.md)は、SDK のインストールの自動化および管理者以外によるインストールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-176">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="0f70c-177">スクリプトは、[dotnet-install スクリプト参照ページ](../tools/dotnet-install-script.md)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-177">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="0f70c-178">スクリプトでは、既定で最新の [長期サポート (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) バージョン (.NET Core 3.1) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-178">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="0f70c-179">NET Core の最新リリースをインストールするには、次のスイッチを使用してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="0f70c-179">To install the current release of .NET Core, run the script with the following switch.</span></span>

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="0f70c-180">すべての .NET Core のダウンロード</span><span class="sxs-lookup"><span data-stu-id="0f70c-180">All .NET Core downloads</span></span>

<span data-ttu-id="0f70c-181">次のいずれかのリンクを使用して、.NET Core を直接ダウンロードしてインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-181">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="0f70c-182">.NET Core 3.1 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="0f70c-182">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="0f70c-183">.NET Core 3.0 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="0f70c-183">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="0f70c-184">.NET Core 2.2 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="0f70c-184">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="0f70c-185">.NET Core 2.1 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="0f70c-185">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="0f70c-186">Docker</span><span class="sxs-lookup"><span data-stu-id="0f70c-186">Docker</span></span>

<span data-ttu-id="0f70c-187">コンテナーを使用すると、アプリケーションをホスト システムの他の部分から簡単に分離できます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-187">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="0f70c-188">同じコンピューター上のコンテナーでは、カーネルだけが共有され、アプリケーションに提供されたリソースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-188">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="0f70c-189">.NET Core は Docker コンテナー内で実行できます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-189">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="0f70c-190">公式の .NET Core Docker イメージは Microsoft Container Registry (MCR) に公開され、[Microsoft .NET Core の Docker Hub リポジトリ](https://hub.docker.com/_/microsoft-dotnet-core/)で見つけられます。</span><span class="sxs-lookup"><span data-stu-id="0f70c-190">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="0f70c-191">各リポジトリには、.NET (SDK またはランタイム) と自分が使用できる OS のさまざまな組み合わせのイメージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0f70c-191">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="0f70c-192">Microsoft は、特定のシナリオに対応したイメージを用意しています。</span><span class="sxs-lookup"><span data-stu-id="0f70c-192">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="0f70c-193">たとえば、[ASP.NET Core リポジトリ](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)には、運用環境での ASP.NET Core アプリの実行用にビルドされたイメージが用意されています。</span><span class="sxs-lookup"><span data-stu-id="0f70c-193">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="0f70c-194">Docker コンテナー内で .NET Core を使用する方法の詳細については、「[.NET および Docker の概要](../docker/introduction.md)」と[サンプル](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f70c-194">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0f70c-195">次の手順</span><span class="sxs-lookup"><span data-stu-id="0f70c-195">Next steps</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="0f70c-196">[チュートリアル: Hello World チュートリアル](../tutorials/with-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="0f70c-196">[Tutorial: Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="0f70c-197">[チュートリアル: Visual Studio Code を使用して新しいアプリを作成する](../tutorials/with-visual-studio-code.md)。</span><span class="sxs-lookup"><span data-stu-id="0f70c-197">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="0f70c-198">[チュートリアル: NET Core アプリをコンテナー化する](../docker/build-container.md)。</span><span class="sxs-lookup"><span data-stu-id="0f70c-198">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="0f70c-199">[macOS Catalina の公証に対応する](macos-notarization-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="0f70c-199">[Working with macOS Catalina notarization](macos-notarization-issues.md).</span></span>
- <span data-ttu-id="0f70c-200">[チュートリアル: macOS での作業を始める](../tutorials/using-on-mac-vs.md).</span><span class="sxs-lookup"><span data-stu-id="0f70c-200">[Tutorial: Get started on macOS](../tutorials/using-on-mac-vs.md).</span></span>
- <span data-ttu-id="0f70c-201">[チュートリアル: Visual Studio Code を使用して新しいアプリを作成する](../tutorials/with-visual-studio-code.md)。</span><span class="sxs-lookup"><span data-stu-id="0f70c-201">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="0f70c-202">[チュートリアル: NET Core アプリをコンテナー化する](../docker/build-container.md)。</span><span class="sxs-lookup"><span data-stu-id="0f70c-202">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-linux"

- <span data-ttu-id="0f70c-203">[チュートリアル: Visual Studio Code を使用して新しいアプリを作成する](../tutorials/with-visual-studio-code.md)。</span><span class="sxs-lookup"><span data-stu-id="0f70c-203">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="0f70c-204">[チュートリアル: NET Core アプリをコンテナー化する](../docker/build-container.md)。</span><span class="sxs-lookup"><span data-stu-id="0f70c-204">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end
