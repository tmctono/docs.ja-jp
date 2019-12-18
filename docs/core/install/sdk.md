---
title: Windows、Linux、および macOS に .NET Core SDK をインストールする - .NET Core
description: Windows、Linux、および macOS に .NET Core をインストールする方法について説明します。 .NET Core アプリの開発に必要な依存関係を確認します。
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 1f7efaedaa1a0be90f7b619f954bdf78eecafa07
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "74999063"
---
# <a name="install-the-net-core-sdk"></a><span data-ttu-id="02b0d-104">.NET Core SDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="02b0d-104">Install the .NET Core SDK</span></span>

<span data-ttu-id="02b0d-105">この記事では、.NET Core SDK をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="02b0d-105">In this article, you'll learn how to install the .NET Core SDK.</span></span> <span data-ttu-id="02b0d-106">.NET Core SDK は、.NET Core アプリとライブラリの作成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="02b0d-106">The .NET Core SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="02b0d-107">.NET Core ランタイムは、常に SDK と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="02b0d-107">The .NET Core runtime is always installed with the SDK.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="02b0d-108">インストーラーを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="02b0d-108">Install with an installer</span></span>

<span data-ttu-id="02b0d-109">Windows には、.NET Core 3.1 SDK のインストールに使用できるスタンドアロン インストーラーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="02b0d-109">Windows has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="02b0d-110">x64 (64 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="02b0d-110">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="02b0d-111">x86 (32 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="02b0d-111">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="02b0d-112">インストーラーを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="02b0d-112">Install with an installer</span></span>

<span data-ttu-id="02b0d-113">macOS には、.NET Core 3.1 SDK のインストールに使用できるスタンドアロン インストーラーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="02b0d-113">macOS has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="02b0d-114">x64 (64 ビット) CPU</span><span class="sxs-lookup"><span data-stu-id="02b0d-114">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="02b0d-115">パッケージ マネージャーを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="02b0d-115">Install with a package manager</span></span>

<span data-ttu-id="02b0d-116">多くの一般的な Linux パッケージ マネージャーを使用して、.NET Core SDK をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="02b0d-116">You can install the .NET Core SDK with many of the common Linux package managers.</span></span> <span data-ttu-id="02b0d-117">詳細については、[Linux パッケージ マネージャー - .NET Core のインストール](linux-package-managers.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02b0d-117">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="02b0d-118">手動でダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="02b0d-118">Download and manually install</span></span>

<span data-ttu-id="02b0d-119">SDK を抽出し、コマンドをターミナルで使用できるようにするには、最初に .NET Core のバイナリ リリースを[ダウンロード](#all-net-core-downloads)します。</span><span class="sxs-lookup"><span data-stu-id="02b0d-119">To extract the SDK and make the commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="02b0d-120">次に、ターミナルを開き、以下のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="02b0d-120">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf dotnet-sdk-3.1.100-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="02b0d-121">上記のコマンドでは、それを実行したターミナル セッションでのみ、.NET SDK コマンドを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="02b0d-121">The above commands will only make the .NET SDK commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="02b0d-122">シェル プロファイルを編集して、コマンドを永続的に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="02b0d-122">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="02b0d-123">Linux ではさまざまなシェルを使用でき、それぞれに異なるプロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="02b0d-123">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="02b0d-124">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="02b0d-124">For example:</span></span>
>
> - <span data-ttu-id="02b0d-125">**Bash シェル**: *~/.bash_profile*、 *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="02b0d-125">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="02b0d-126">**Korn シェル**: *~/.kshrc* または *.profile*</span><span class="sxs-lookup"><span data-stu-id="02b0d-126">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="02b0d-127">**Z シェル**: *~/.zshrc* または *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="02b0d-127">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
> 
> <span data-ttu-id="02b0d-128">シェルの適切なソース ファイルを編集し、既存の `PATH` ステートメントの末尾に `:$HOME/dotnet` を追加します。</span><span class="sxs-lookup"><span data-stu-id="02b0d-128">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="02b0d-129">`PATH` ステートメントが含まれていない場合は、`export PATH=$PATH:$HOME/dotnet` を含む新しい行を追加します。</span><span class="sxs-lookup"><span data-stu-id="02b0d-129">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="02b0d-130">また、ファイルの末尾に `export DOTNET_ROOT=$HOME/dotnet` を追加します。</span><span class="sxs-lookup"><span data-stu-id="02b0d-130">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a><span data-ttu-id="02b0d-131">Visual Studio を使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="02b0d-131">Install with Visual Studio</span></span>

<span data-ttu-id="02b0d-132">次の表では、Visual Studio を使用して .NET Core アプリを開発している場合に、ターゲットの .NET Core SDK バージョンに基づいて最低限必要な Visual Studio のバージョンを説明します。</span><span class="sxs-lookup"><span data-stu-id="02b0d-132">If you're using Visual Studio to develop .NET Core apps, the following table describes the minimum required version of Visual Studio based on the target .NET Core SDK version.</span></span>

| <span data-ttu-id="02b0d-133">.NET Core SDK のバージョン</span><span class="sxs-lookup"><span data-stu-id="02b0d-133">.NET Core SDK version</span></span> | <span data-ttu-id="02b0d-134">Visual Studio のバージョン</span><span class="sxs-lookup"><span data-stu-id="02b0d-134">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="02b0d-135">3.1</span><span class="sxs-lookup"><span data-stu-id="02b0d-135">3.1</span></span>                   | <span data-ttu-id="02b0d-136">Visual Studio 2019 バージョン 16.4 以降。</span><span class="sxs-lookup"><span data-stu-id="02b0d-136">Visual Studio 2019 version 16.4 or higher.</span></span> |
| <span data-ttu-id="02b0d-137">3.0</span><span class="sxs-lookup"><span data-stu-id="02b0d-137">3.0</span></span>                   | <span data-ttu-id="02b0d-138">Visual Studio 2019 バージョン 16.3 以降。</span><span class="sxs-lookup"><span data-stu-id="02b0d-138">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="02b0d-139">2.2</span><span class="sxs-lookup"><span data-stu-id="02b0d-139">2.2</span></span>                   | <span data-ttu-id="02b0d-140">Visual Studio 2017 バージョン 15.9 以降。</span><span class="sxs-lookup"><span data-stu-id="02b0d-140">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="02b0d-141">2.1</span><span class="sxs-lookup"><span data-stu-id="02b0d-141">2.1</span></span>                   | <span data-ttu-id="02b0d-142">Visual Studio 2017 バージョン 15.7 以降。</span><span class="sxs-lookup"><span data-stu-id="02b0d-142">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="02b0d-143">Visual Studio を既にインストールしてある場合は、次の手順でバージョンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="02b0d-143">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="02b0d-144">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="02b0d-144">Open Visual Studio.</span></span>
01. <span data-ttu-id="02b0d-145">**[ヘルプ]**  >  **[Microsoft Visual Studio のバージョン情報]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="02b0d-145">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="02b0d-146">**[バージョン情報]** ダイアログで、バージョン番号を確認します。</span><span class="sxs-lookup"><span data-stu-id="02b0d-146">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="02b0d-147">Visual Studio では、最新の .NET Core SDK とランタイムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="02b0d-147">Visual Studio can install the latest .NET Core SDK and runtime.</span></span>

- <span data-ttu-id="02b0d-148">[Visual Studio をダウンロードします](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)。</span><span class="sxs-lookup"><span data-stu-id="02b0d-148">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="02b0d-149">ワークロードを選択する</span><span class="sxs-lookup"><span data-stu-id="02b0d-149">Select a workload</span></span>

<span data-ttu-id="02b0d-150">Visual Studio をインストールまたは変更するときは、ビルドするアプリケーションの種類に応じて、次のいずれかのワークロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="02b0d-150">When installing or modifying Visual Studio, select one of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="02b0d-151">**[他のツールセット]** セクションの **[.NET Core クロスプラットフォームの開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="02b0d-151">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="02b0d-152">**[Web クラウド]** セクションの **[ASP.NET と Web 開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="02b0d-152">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="02b0d-153">**[Web クラウド]** セクションの **[Azure の開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="02b0d-153">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="02b0d-154">**[デスクトップとモバイル]** セクションの **[.NET デスクトップ開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="02b0d-154">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="02b0d-155">[![Windows Visual Studio 2019 と .NET Core ワークロード](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="02b0d-155">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="02b0d-156">Visual Studio for Mac を使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="02b0d-156">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="02b0d-157">Visual Studio for Mac では、 **[.NET Core]** ワークロードを選択すると、.NET Core SDK がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="02b0d-157">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="02b0d-158">macOS で .NET Core の開発を始めるには、「[Visual Studio 2019 for Mac をインストールする](/visualstudio/mac/installation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02b0d-158">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span> <span data-ttu-id="02b0d-159">最新リリースである .NET Core 3.1 の場合は、Visual Studio for Mac 8.4 Preview を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02b0d-159">For the latest release, .NET Core 3.1, you must use the Visual Studio for Mac 8.4 Preview.</span></span>

<span data-ttu-id="02b0d-160">[![macOS Visual Studio 2019 for Mac と .NET Core ワークロード機能](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="02b0d-160">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

::: zone-end

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="02b0d-161">Visual Studio Code と共にインストールする</span><span class="sxs-lookup"><span data-stu-id="02b0d-161">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="02b0d-162">Visual Studio Code は、デスクトップ上で動作する強力で軽量なソース コード エディターです。</span><span class="sxs-lookup"><span data-stu-id="02b0d-162">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="02b0d-163">Visual Studio Code は、Windows、macOS、Linux で利用できます。</span><span class="sxs-lookup"><span data-stu-id="02b0d-163">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="02b0d-164">Visual Studio Code には、Visual Studio のような自動化された .NET Core インストーラーは付属していませんが、.NET Core のサポートを簡単に追加できます。</span><span class="sxs-lookup"><span data-stu-id="02b0d-164">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="02b0d-165">[Visual Studio Code をダウンロードしてインストールします](https://code.visualstudio.com/Download)。</span><span class="sxs-lookup"><span data-stu-id="02b0d-165">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="02b0d-166">[.NET Core SDK をダウンロードしてインストールします](https://dotnet.microsoft.com/download/dotnet-core)。</span><span class="sxs-lookup"><span data-stu-id="02b0d-166">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="02b0d-167">[Visual Studio Code マーケットプレースから C# 拡張機能をインストールします](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)。</span><span class="sxs-lookup"><span data-stu-id="02b0d-167">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span>

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="02b0d-168">PowerShell オートメーションを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="02b0d-168">Install with PowerShell automation</span></span>

<span data-ttu-id="02b0d-169">[dotnet-install スクリプト](../tools/dotnet-install-script.md)は、SDK のインストールの自動化および管理者以外によるインストールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="02b0d-169">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="02b0d-170">スクリプトは、[dotnet-install スクリプト参照ページ](../tools/dotnet-install-script.md)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="02b0d-170">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="02b0d-171">スクリプトでは、最新の[長期サポート (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) バージョン (.NET Core 2.1) が既定でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="02b0d-171">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 2.1.</span></span> <span data-ttu-id="02b0d-172">NET Core の最新リリースをインストールするには、次のスイッチを使用してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="02b0d-172">To install the current release of .NET Core, run the script with the following switch.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="02b0d-173">bash オートメーションを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="02b0d-173">Install with bash automation</span></span>

<span data-ttu-id="02b0d-174">[dotnet-install スクリプト](../tools/dotnet-install-script.md)は、SDK のインストールの自動化および管理者以外によるインストールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="02b0d-174">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="02b0d-175">スクリプトは、[dotnet-install スクリプト参照ページ](../tools/dotnet-install-script.md)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="02b0d-175">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="02b0d-176">スクリプトでは、最新の[長期サポート (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) バージョン (.NET Core 2.1) が既定でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="02b0d-176">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 2.1.</span></span> <span data-ttu-id="02b0d-177">NET Core の最新リリースをインストールするには、次のスイッチを使用してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="02b0d-177">To install the current release of .NET Core, run the script with the following switch.</span></span>

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="02b0d-178">すべての .NET Core のダウンロード</span><span class="sxs-lookup"><span data-stu-id="02b0d-178">All .NET Core downloads</span></span>

<span data-ttu-id="02b0d-179">次のいずれかのリンクを使用して、.NET Core を直接ダウンロードしてインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="02b0d-179">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="02b0d-180">.NET Core 3.1 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="02b0d-180">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="02b0d-181">.NET Core 3.0 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="02b0d-181">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="02b0d-182">.NET Core 2.2 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="02b0d-182">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="02b0d-183">.NET Core 2.1 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="02b0d-183">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="02b0d-184">Docker</span><span class="sxs-lookup"><span data-stu-id="02b0d-184">Docker</span></span>

<span data-ttu-id="02b0d-185">コンテナーを使用すると、アプリケーションをホスト システムの他の部分から簡単に分離できます。</span><span class="sxs-lookup"><span data-stu-id="02b0d-185">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="02b0d-186">同じコンピューター上のコンテナーでは、カーネルだけが共有され、アプリケーションに提供されたリソースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="02b0d-186">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="02b0d-187">.NET Core は Docker コンテナー内で実行できます。</span><span class="sxs-lookup"><span data-stu-id="02b0d-187">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="02b0d-188">公式の .NET Core Docker イメージは Microsoft Container Registry (MCR) に公開され、[Microsoft .NET Core の Docker Hub リポジトリ](https://hub.docker.com/_/microsoft-dotnet-core/)で見つけられます。</span><span class="sxs-lookup"><span data-stu-id="02b0d-188">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="02b0d-189">各リポジトリには、.NET (SDK またはランタイム) と自分が使用できる OS のさまざまな組み合わせのイメージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="02b0d-189">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="02b0d-190">Microsoft は、特定のシナリオに対応したイメージを用意しています。</span><span class="sxs-lookup"><span data-stu-id="02b0d-190">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="02b0d-191">たとえば、[ASP.NET Core リポジトリ](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)には、運用環境での ASP.NET Core アプリの実行用にビルドされたイメージが用意されています。</span><span class="sxs-lookup"><span data-stu-id="02b0d-191">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="02b0d-192">Docker コンテナー内で .NET Core を使用する方法の詳細については、「[.NET および Docker の概要](../docker/introduction.md)」と[サンプル](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02b0d-192">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="02b0d-193">次の手順</span><span class="sxs-lookup"><span data-stu-id="02b0d-193">Next steps</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="02b0d-194">[チュートリアル: C# Hello World チュートリアル](../tutorials/with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="02b0d-194">[Tutorial: C# Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="02b0d-195">[チュートリアル: Visual Basic Hello World チュートリアル](../tutorials/vb-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="02b0d-195">[Tutorial: Visual Basic Hello World tutorial](../tutorials/vb-with-visual-studio.md).</span></span>
- <span data-ttu-id="02b0d-196">[チュートリアル: Visual Studio Code を使用して新しいアプリを作成する](../tutorials/with-visual-studio-code.md)。</span><span class="sxs-lookup"><span data-stu-id="02b0d-196">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="02b0d-197">[チュートリアル: NET Core アプリをコンテナー化する](../docker/build-container.md)。</span><span class="sxs-lookup"><span data-stu-id="02b0d-197">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="02b0d-198">[チュートリアル: macOS での作業を始める](../tutorials/using-on-mac-vs.md).</span><span class="sxs-lookup"><span data-stu-id="02b0d-198">[Tutorial: Get started on macOS](../tutorials/using-on-mac-vs.md).</span></span>
- <span data-ttu-id="02b0d-199">[チュートリアル: Visual Studio Code を使用して新しいアプリを作成する](../tutorials/with-visual-studio-code.md)。</span><span class="sxs-lookup"><span data-stu-id="02b0d-199">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="02b0d-200">[チュートリアル: NET Core アプリをコンテナー化する](../docker/build-container.md)。</span><span class="sxs-lookup"><span data-stu-id="02b0d-200">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-linux"

- <span data-ttu-id="02b0d-201">[チュートリアル: Visual Studio Code を使用して新しいアプリを作成する](../tutorials/with-visual-studio-code.md)。</span><span class="sxs-lookup"><span data-stu-id="02b0d-201">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="02b0d-202">[チュートリアル: NET Core アプリをコンテナー化する](../docker/build-container.md)。</span><span class="sxs-lookup"><span data-stu-id="02b0d-202">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end
