---
title: Windows、Linux、および macOS に .NET Core SDK をインストールする - .NET Core
description: Windows、Linux、および macOS に .NET Core をインストールする方法について説明します。 .NET Core アプリの開発に必要な依存関係を確認します。
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 4a6c8b27812e9f60e52132169dda0464c24abcc2
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740567"
---
# <a name="install-the-net-core-sdk"></a><span data-ttu-id="f6423-104">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="f6423-104">Install the .NET Core SDK</span></span>

<span data-ttu-id="f6423-105">この記事では、.NET Core SDK をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f6423-105">In this article, you'll learn how to install the .NET Core SDK.</span></span> <span data-ttu-id="f6423-106">.NET Core SDK は、.NET Core アプリとライブラリの作成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f6423-106">The .NET Core SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="f6423-107">.NET Core ランタイムは、常に SDK と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f6423-107">The .NET Core runtime is always installed with the SDK.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="f6423-108">インストーラーを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="f6423-108">Install with an installer</span></span>

<span data-ttu-id="f6423-109">Windows には、.NET Core 3.1 SDK のインストールに使用できるスタンドアロン インストーラーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f6423-109">Windows has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="f6423-110">x64 (64 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="f6423-110">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="f6423-111">x86 (32 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="f6423-111">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="f6423-112">インストーラーを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="f6423-112">Install with an installer</span></span>

<span data-ttu-id="f6423-113">macOS には、.NET Core 3.1 SDK のインストールに使用できるスタンドアロン インストーラーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f6423-113">macOS has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="f6423-114">x64 (64 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="f6423-114">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="f6423-115">パッケージ マネージャーを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="f6423-115">Install with a package manager</span></span>

<span data-ttu-id="f6423-116">多くの一般的な Linux パッケージ マネージャーを使用して、.NET Core SDK をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f6423-116">You can install the .NET Core SDK with many of the common Linux package managers.</span></span> <span data-ttu-id="f6423-117">詳細については、[Linux パッケージ マネージャー - .NET Core のインストール](linux-package-managers.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6423-117">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

<span data-ttu-id="f6423-118">パッケージ マネージャーを使用したインストールは、x64 アーキテクチャでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f6423-118">Installing with a package manager is only supported on the x64 architecture.</span></span> <span data-ttu-id="f6423-119">ARM などの別のアーキテクチャを使用して .NET Core SDK をインストールする場合は、以下の「[手動でダウンロードしてインストールする](#download-and-manually-install)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="f6423-119">If you're installing the .NET Core SDK with a different architecture, such as ARM, follow the [Download and manually install](#download-and-manually-install) instructions below.</span></span> <span data-ttu-id="f6423-120">サポートされているアーキテクチャの詳細については、「[.NET Core の依存関係と要件](dependencies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6423-120">For more information about what architectures are supported, see [.NET Core dependencies and requirements](dependencies.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="f6423-121">手動でダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="f6423-121">Download and manually install</span></span>

<span data-ttu-id="f6423-122">SDK を抽出し、.NET Core CLI コマンドをターミナルで使用できるようにするには、最初に .NET Core のバイナリ リリースを[ダウンロード](#all-net-core-downloads)します。</span><span class="sxs-lookup"><span data-stu-id="f6423-122">To extract the SDK and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="f6423-123">次に、ターミナルを開き、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f6423-123">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf dotnet-sdk-3.1.100-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="f6423-124">上記の `export` コマンドでは、それを実行したターミナル セッションでのみ .NET Core CLI コマンドを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f6423-124">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="f6423-125">シェル プロファイルを編集して、コマンドを永続的に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="f6423-125">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="f6423-126">Linux ではさまざまなシェルを使用でき、それぞれに異なるプロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="f6423-126">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="f6423-127">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f6423-127">For example:</span></span>
>
> - <span data-ttu-id="f6423-128">**Bash シェル**: *~/.bash_profile*、 *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="f6423-128">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="f6423-129">**Korn シェル**: *~/.kshrc* または *.profile*</span><span class="sxs-lookup"><span data-stu-id="f6423-129">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="f6423-130">**Z シェル**: *~/.zshrc* または *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="f6423-130">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="f6423-131">シェルの適切なソース ファイルを編集し、既存の `PATH` ステートメントの末尾に `:$HOME/dotnet` を追加します。</span><span class="sxs-lookup"><span data-stu-id="f6423-131">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="f6423-132">`PATH` ステートメントが含まれていない場合は、`export PATH=$PATH:$HOME/dotnet` を含む新しい行を追加します。</span><span class="sxs-lookup"><span data-stu-id="f6423-132">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="f6423-133">また、ファイルの末尾に `export DOTNET_ROOT=$HOME/dotnet` を追加します。</span><span class="sxs-lookup"><span data-stu-id="f6423-133">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a><span data-ttu-id="f6423-134">Visual Studio を使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="f6423-134">Install with Visual Studio</span></span>

<span data-ttu-id="f6423-135">次の表では、Visual Studio を使用して .NET Core アプリを開発している場合に、ターゲットの .NET Core SDK バージョンに基づいて最低限必要な Visual Studio のバージョンを説明します。</span><span class="sxs-lookup"><span data-stu-id="f6423-135">If you're using Visual Studio to develop .NET Core apps, the following table describes the minimum required version of Visual Studio based on the target .NET Core SDK version.</span></span>

| <span data-ttu-id="f6423-136">.NET Core SDK のバージョン</span><span class="sxs-lookup"><span data-stu-id="f6423-136">.NET Core SDK version</span></span> | <span data-ttu-id="f6423-137">Visual Studio のバージョン</span><span class="sxs-lookup"><span data-stu-id="f6423-137">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="f6423-138">3.1</span><span class="sxs-lookup"><span data-stu-id="f6423-138">3.1</span></span>                   | <span data-ttu-id="f6423-139">Visual Studio 2019 バージョン 16.4 以降。</span><span class="sxs-lookup"><span data-stu-id="f6423-139">Visual Studio 2019 version 16.4 or higher.</span></span> |
| <span data-ttu-id="f6423-140">3.0</span><span class="sxs-lookup"><span data-stu-id="f6423-140">3.0</span></span>                   | <span data-ttu-id="f6423-141">Visual Studio 2019 バージョン 16.3 以降。</span><span class="sxs-lookup"><span data-stu-id="f6423-141">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="f6423-142">2.2</span><span class="sxs-lookup"><span data-stu-id="f6423-142">2.2</span></span>                   | <span data-ttu-id="f6423-143">Visual Studio 2017 バージョン 15.9 以降。</span><span class="sxs-lookup"><span data-stu-id="f6423-143">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="f6423-144">2.1</span><span class="sxs-lookup"><span data-stu-id="f6423-144">2.1</span></span>                   | <span data-ttu-id="f6423-145">Visual Studio 2017 バージョン 15.7 以降。</span><span class="sxs-lookup"><span data-stu-id="f6423-145">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="f6423-146">Visual Studio を既にインストールしてある場合は、次の手順でバージョンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f6423-146">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="f6423-147">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="f6423-147">Open Visual Studio.</span></span>
01. <span data-ttu-id="f6423-148">**[ヘルプ]**  >  **[Microsoft Visual Studio のバージョン情報]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6423-148">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="f6423-149">**[バージョン情報]** ダイアログで、バージョン番号を確認します。</span><span class="sxs-lookup"><span data-stu-id="f6423-149">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="f6423-150">Visual Studio では、最新の .NET Core SDK とランタイムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f6423-150">Visual Studio can install the latest .NET Core SDK and runtime.</span></span>

- <span data-ttu-id="f6423-151">[Visual Studio をダウンロードします](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)。</span><span class="sxs-lookup"><span data-stu-id="f6423-151">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="f6423-152">ワークロードを選択する</span><span class="sxs-lookup"><span data-stu-id="f6423-152">Select a workload</span></span>

<span data-ttu-id="f6423-153">Visual Studio をインストールまたは変更するときは、ビルドするアプリケーションの種類に応じて、次の 1 つ以上のワークロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="f6423-153">When installing or modifying Visual Studio, select one or more of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="f6423-154">**[他のツールセット]** セクションの **[.NET Core クロスプラットフォームの開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="f6423-154">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="f6423-155">**[Web クラウド]** セクションの **[ASP.NET と Web 開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="f6423-155">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="f6423-156">**[Web クラウド]** セクションの **[Azure の開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="f6423-156">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="f6423-157">**[デスクトップとモバイル]** セクションの **[.NET デスクトップ開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="f6423-157">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="f6423-158">[![Windows Visual Studio 2019 と .NET Core ワークロード](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="f6423-158">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="f6423-159">Visual Studio for Mac を使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="f6423-159">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="f6423-160">Visual Studio for Mac では、 **[.NET Core]** ワークロードを選択すると、.NET Core SDK がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f6423-160">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="f6423-161">macOS で .NET Core の開発を始めるには、「[Visual Studio 2019 for Mac をインストールする](/visualstudio/mac/installation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6423-161">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span> <span data-ttu-id="f6423-162">最新リリースである .NET Core 3.1 の場合は、Visual Studio for Mac 8.4 Preview を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6423-162">For the latest release, .NET Core 3.1, you must use the Visual Studio for Mac 8.4 Preview.</span></span>

<span data-ttu-id="f6423-163">[![macOS Visual Studio 2019 for Mac と .NET Core ワークロード機能](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="f6423-163">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

::: zone-end

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="f6423-164">Visual Studio Code と共にインストールする</span><span class="sxs-lookup"><span data-stu-id="f6423-164">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="f6423-165">Visual Studio Code は、デスクトップ上で動作する強力で軽量なソース コード エディターです。</span><span class="sxs-lookup"><span data-stu-id="f6423-165">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="f6423-166">Visual Studio Code は、Windows、macOS、Linux で利用できます。</span><span class="sxs-lookup"><span data-stu-id="f6423-166">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="f6423-167">Visual Studio Code には、Visual Studio のような自動化された .NET Core インストーラーは付属していませんが、.NET Core のサポートを簡単に追加できます。</span><span class="sxs-lookup"><span data-stu-id="f6423-167">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="f6423-168">[Visual Studio Code をダウンロードしてインストールします](https://code.visualstudio.com/Download)。</span><span class="sxs-lookup"><span data-stu-id="f6423-168">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="f6423-169">[.NET Core SDK をダウンロードしてインストールします](https://dotnet.microsoft.com/download/dotnet-core)。</span><span class="sxs-lookup"><span data-stu-id="f6423-169">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="f6423-170">[Visual Studio Code マーケットプレースから C# 拡張機能をインストールします](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)。</span><span class="sxs-lookup"><span data-stu-id="f6423-170">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span>

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="f6423-171">PowerShell オートメーションを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="f6423-171">Install with PowerShell automation</span></span>

<span data-ttu-id="f6423-172">[dotnet-install スクリプト](../tools/dotnet-install-script.md)は、SDK のインストールの自動化および管理者以外によるインストールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f6423-172">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="f6423-173">スクリプトは、[dotnet-install スクリプト参照ページ](../tools/dotnet-install-script.md)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f6423-173">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="f6423-174">スクリプトでは、既定で最新の [長期サポート (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) バージョン (.NET Core 3.1) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f6423-174">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="f6423-175">NET Core の最新リリースをインストールするには、次のスイッチを使用してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="f6423-175">To install the current release of .NET Core, run the script with the following switch.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="f6423-176">bash オートメーションを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="f6423-176">Install with bash automation</span></span>

<span data-ttu-id="f6423-177">[dotnet-install スクリプト](../tools/dotnet-install-script.md)は、SDK のインストールの自動化および管理者以外によるインストールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f6423-177">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="f6423-178">スクリプトは、[dotnet-install スクリプト参照ページ](../tools/dotnet-install-script.md)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f6423-178">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="f6423-179">スクリプトでは、既定で最新の [長期サポート (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) バージョン (.NET Core 3.1) がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f6423-179">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="f6423-180">NET Core の最新リリースをインストールするには、次のスイッチを使用してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="f6423-180">To install the current release of .NET Core, run the script with the following switch.</span></span>

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="f6423-181">すべての .NET Core のダウンロード</span><span class="sxs-lookup"><span data-stu-id="f6423-181">All .NET Core downloads</span></span>

<span data-ttu-id="f6423-182">次のいずれかのリンクを使用して、.NET Core を直接ダウンロードしてインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="f6423-182">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="f6423-183">.NET Core 3.1 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="f6423-183">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="f6423-184">.NET Core 3.0 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="f6423-184">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="f6423-185">.NET Core 2.2 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="f6423-185">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="f6423-186">.NET Core 2.1 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="f6423-186">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="f6423-187">Docker</span><span class="sxs-lookup"><span data-stu-id="f6423-187">Docker</span></span>

<span data-ttu-id="f6423-188">コンテナーを使用すると、アプリケーションをホスト システムの他の部分から簡単に分離できます。</span><span class="sxs-lookup"><span data-stu-id="f6423-188">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="f6423-189">同じコンピューター上のコンテナーでは、カーネルだけが共有され、アプリケーションに提供されたリソースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f6423-189">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="f6423-190">.NET Core は Docker コンテナー内で実行できます。</span><span class="sxs-lookup"><span data-stu-id="f6423-190">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="f6423-191">公式の .NET Core Docker イメージは Microsoft Container Registry (MCR) に公開され、[Microsoft .NET Core の Docker Hub リポジトリ](https://hub.docker.com/_/microsoft-dotnet-core/)で見つけられます。</span><span class="sxs-lookup"><span data-stu-id="f6423-191">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="f6423-192">各リポジトリには、.NET (SDK またはランタイム) と自分が使用できる OS のさまざまな組み合わせのイメージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f6423-192">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="f6423-193">Microsoft は、特定のシナリオに対応したイメージを用意しています。</span><span class="sxs-lookup"><span data-stu-id="f6423-193">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="f6423-194">たとえば、[ASP.NET Core リポジトリ](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)には、運用環境での ASP.NET Core アプリの実行用にビルドされたイメージが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f6423-194">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="f6423-195">Docker コンテナー内で .NET Core を使用する方法の詳細については、「[.NET および Docker の概要](../docker/introduction.md)」と[サンプル](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6423-195">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f6423-196">次の手順</span><span class="sxs-lookup"><span data-stu-id="f6423-196">Next steps</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="f6423-197">[チュートリアル: Hello World チュートリアル](../tutorials/with-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="f6423-197">[Tutorial: Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="f6423-198">[チュートリアル: Visual Studio Code を使用して新しいアプリを作成する](../tutorials/with-visual-studio-code.md)。</span><span class="sxs-lookup"><span data-stu-id="f6423-198">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="f6423-199">[チュートリアル: NET Core アプリをコンテナー化する](../docker/build-container.md)。</span><span class="sxs-lookup"><span data-stu-id="f6423-199">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="f6423-200">[チュートリアル: macOS での作業を始める](../tutorials/using-on-mac-vs.md).</span><span class="sxs-lookup"><span data-stu-id="f6423-200">[Tutorial: Get started on macOS](../tutorials/using-on-mac-vs.md).</span></span>
- <span data-ttu-id="f6423-201">[チュートリアル: Visual Studio Code を使用して新しいアプリを作成する](../tutorials/with-visual-studio-code.md)。</span><span class="sxs-lookup"><span data-stu-id="f6423-201">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="f6423-202">[チュートリアル: NET Core アプリをコンテナー化する](../docker/build-container.md)。</span><span class="sxs-lookup"><span data-stu-id="f6423-202">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-linux"

- <span data-ttu-id="f6423-203">[チュートリアル: Visual Studio Code を使用して新しいアプリを作成する](../tutorials/with-visual-studio-code.md)。</span><span class="sxs-lookup"><span data-stu-id="f6423-203">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="f6423-204">[チュートリアル: NET Core アプリをコンテナー化する](../docker/build-container.md)。</span><span class="sxs-lookup"><span data-stu-id="f6423-204">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end
