---
title: Windows における .NET Core の前提条件
description: Windows コンピューターで .NET Core アプリケーションを開発および実行する場合に必要な依存関係について説明します。
f1_keywords:
- NETSDK1045
ms.custom: updateeachvsrelease
ms.date: 09/20/2019
ms.openlocfilehash: b1557e6910cb6d0b6d7e2b3ce2aec97d3715fec7
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591669"
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="63b66-103">Windows における .NET Core の前提条件</span><span class="sxs-lookup"><span data-stu-id="63b66-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="63b66-104">この記事では、Windows 上で .NET Core アプリケーションを実行するためにサポートされる OS のバージョンについて説明します。</span><span class="sxs-lookup"><span data-stu-id="63b66-104">This article shows the supported OS versions in order to run .NET Core applications on Windows.</span></span> <span data-ttu-id="63b66-105">後述のサポート対象 OS のバージョンと依存関係は、Windows で .NET Core アプリを開発する次の 3 つの方法に適用されます。</span><span class="sxs-lookup"><span data-stu-id="63b66-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="63b66-106">コマンド ライン</span><span class="sxs-lookup"><span data-stu-id="63b66-106">Command line</span></span>](./tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="63b66-107">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="63b66-107">Visual Studio</span></span>](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)
* [<span data-ttu-id="63b66-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="63b66-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

<span data-ttu-id="63b66-109">また、Visual Studio を使用して Windows 上で開発している場合、.NET Core 開発でサポートされている最小バージョンの詳細については、「[Visual Studio で .NET Core アプリを開発するための前提条件](#prerequisites-to-develop-net-core-apps-with-visual-studio)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b66-109">Also, if you're developing on Windows using Visual Studio, the [Prerequisites to develop .NET Core apps with Visual Studio](#prerequisites-to-develop-net-core-apps-with-visual-studio) section goes in more detail about minimum versions supported for .NET Core development.</span></span>

## <a name="net-core-supported-operating-systems"></a><span data-ttu-id="63b66-110">.NET Core がサポートされたオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="63b66-110">.NET Core supported operating systems</span></span>

<span data-ttu-id="63b66-111">次の記事では、.NET Core がサポートされたオペレーティング システム (バージョンごと) の完全な一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="63b66-111">The following articles have a complete list of .NET Core supported operating systems per version:</span></span>

* [<span data-ttu-id="63b66-112">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="63b66-112">.NET Core 3.0</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)
* [<span data-ttu-id="63b66-113">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="63b66-113">.NET Core 2.2</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [<span data-ttu-id="63b66-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="63b66-114">.NET Core 2.1</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)

<span data-ttu-id="63b66-115">ダウンロード リンクと詳細については、最新バージョンをダウンロードするには [.NET ダウンロード](https://dotnet.microsoft.com/download)、以前のバージョンについて [.NET ダウンロードのアーカイブ](https://dotnet.microsoft.com/download/archives#dotnet-core)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63b66-115">For download links and more information, see [.NET downloads](https://dotnet.microsoft.com/download) to download the latest version or [.NET downloads archive](https://dotnet.microsoft.com/download/archives#dotnet-core) for older versions.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="63b66-116">.NET Core の依存関係</span><span class="sxs-lookup"><span data-stu-id="63b66-116">.NET Core dependencies</span></span>

<span data-ttu-id="63b66-117">次の場合には、[Microsoft Visual C++ 2015 再頒布可能パッケージ Update 3](https://www.microsoft.com/download/details.aspx?id=52685) を手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="63b66-117">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="63b66-118">[インストーラー スクリプト](./tools/dotnet-install-script.md)を使用して .NET Core をインストールする。</span><span class="sxs-lookup"><span data-stu-id="63b66-118">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="63b66-119">自己完結型の .NET Core アプリケーションを展開する。</span><span class="sxs-lookup"><span data-stu-id="63b66-119">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="63b66-120">ソースから製品をビルドする。</span><span class="sxs-lookup"><span data-stu-id="63b66-120">Building the product from source.</span></span>
* <span data-ttu-id="63b66-121">*.zip* ファイルを使用して .NET Core をインストールする。</span><span class="sxs-lookup"><span data-stu-id="63b66-121">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="63b66-122">これにはビルド/CI/CD サーバーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="63b66-122">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="63b66-123">**Windows 8.1 以前のバージョン、または Windows Server 2012 R2 以前のバージョンの場合:**</span><span class="sxs-lookup"><span data-stu-id="63b66-123">**For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:**</span></span>
>
> <span data-ttu-id="63b66-124">Windows のインストールが最新であり、Windows Update から修正プログラム [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) をインストールしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="63b66-124">Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows), which can be installed through Windows Update.</span></span> <span data-ttu-id="63b66-125">この更新プログラムがインストールされていない場合は、.NET Core アプリケーションを起動するときに、次のようなエラーが表示されます。`The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span><span class="sxs-lookup"><span data-stu-id="63b66-125">If you don't have this update installed, you'll see an error like the following when you launch a .NET Core application: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span></span>
>
> <span data-ttu-id="63b66-126">**Windows 7 または Windows Server 2008 R2 の場合:**</span><span class="sxs-lookup"><span data-stu-id="63b66-126">**For Windows 7 or Windows Server 2008 R2:**</span></span>
>
> <span data-ttu-id="63b66-127">KB2999226 に加え、[KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) もインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="63b66-127">In addition to KB2999226, make sure you also have [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installed.</span></span> <span data-ttu-id="63b66-128">この更新プログラムがインストールされていない場合は、.NET Core アプリケーションを起動するときに、次のようなエラーが表示されます。`The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`</span><span class="sxs-lookup"><span data-stu-id="63b66-128">If you don't have this update installed, you'll see an error similar to the following when you launch a .NET Core application: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span></span>

## <a name="prerequisites-to-develop-net-core-apps-with-visual-studio"></a><span data-ttu-id="63b66-129">Visual Studio で .NET Core アプリを開発するための前提条件</span><span class="sxs-lookup"><span data-stu-id="63b66-129">Prerequisites to develop .NET Core apps with Visual Studio</span></span>
    
<span data-ttu-id="63b66-130">.NET Core SDK を使用して .NET Core アプリケーションを開発するには任意のエディターを使用できますが、Visual Studio 2017 以降のバージョンでは、Windows での .NET Core アプリ用の統合開発環境が提供されています。</span><span class="sxs-lookup"><span data-stu-id="63b66-130">Even though you can use any editor to develop .NET Core applications using the .NET Core SDK, Visual Studio 2017 and later versions provide an integrated development environment for .NET Core apps on Windows.</span></span>

<a name="vs-mapping"></a>

<span data-ttu-id="63b66-131">.NET Core の各バージョンには、最低限必要な Visual Studio のバージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="63b66-131">Each .NET Core version has a minimum version of Visual Studio required.</span></span> <span data-ttu-id="63b66-132">お使いの Visual Studio バージョンを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="63b66-132">To verify your Visual Studio version:</span></span>

* <span data-ttu-id="63b66-133">**[ヘルプ]** メニューの **[About Microsoft Visual Studio]** (Microsoft Visual Studio のバージョン情報) を選択します。</span><span class="sxs-lookup"><span data-stu-id="63b66-133">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
* <span data-ttu-id="63b66-134">**[Microsoft Visual Studio のバージョン情報]** ダイアログで、バージョン番号を確認します。</span><span class="sxs-lookup"><span data-stu-id="63b66-134">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>

<span data-ttu-id="63b66-135">次の表では、各 SDK の最小バージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="63b66-135">The following table lists the minimum version for each SDK:</span></span>

| <span data-ttu-id="63b66-136">.NET Core SDK のバージョン</span><span class="sxs-lookup"><span data-stu-id="63b66-136">.NET Core SDK version</span></span> | <span data-ttu-id="63b66-137">Visual Studio のバージョン</span><span class="sxs-lookup"><span data-stu-id="63b66-137">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="63b66-138">3.0</span><span class="sxs-lookup"><span data-stu-id="63b66-138">3.0</span></span>                   | <span data-ttu-id="63b66-139">Visual Studio 2019 バージョン 16.3 以降。</span><span class="sxs-lookup"><span data-stu-id="63b66-139">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="63b66-140">2.2</span><span class="sxs-lookup"><span data-stu-id="63b66-140">2.2</span></span>                   | <span data-ttu-id="63b66-141">Visual Studio 2017 バージョン 15.9 以降。</span><span class="sxs-lookup"><span data-stu-id="63b66-141">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="63b66-142">2.1</span><span class="sxs-lookup"><span data-stu-id="63b66-142">2.1</span></span>                   | <span data-ttu-id="63b66-143">Visual Studio 2017 バージョン 15.7 以降。</span><span class="sxs-lookup"><span data-stu-id="63b66-143">Visual Studio 2017 version 15.7 or higher.</span></span> |
| <span data-ttu-id="63b66-144">1.x</span><span class="sxs-lookup"><span data-stu-id="63b66-144">1.x</span></span>                   | <span data-ttu-id="63b66-145">Visual Studio 2017 バージョン 15.0 以降。</span><span class="sxs-lookup"><span data-stu-id="63b66-145">Visual Studio 2017 version 15.0 or higher.</span></span> |

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="63b66-146">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="63b66-146">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="63b66-147">Visual Studio 2019 で .NET Core 3.0 SDK を使用して .NET Core アプリを開発するには:</span><span class="sxs-lookup"><span data-stu-id="63b66-147">To develop .NET Core apps in Visual Studio 2019 using the .NET Core 3.0 SDK:</span></span>

* <span data-ttu-id="63b66-148">[Visual Studio 2019 バージョン 16.3 以降をダウンロードしてインストール](/visualstudio/install/install-visual-studio)し、ビルドしているアプリケーションの種類に応じて、.NET Core SDK が含まれる次のいずれかのワークロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="63b66-148">[Download and install Visual Studio 2019 version 16.3 or higher](/visualstudio/install/install-visual-studio) and select one of the following workloads that includes the .NET Core SDK, depending on the kind of application you're building:</span></span>

  * <span data-ttu-id="63b66-149">**[他のツールセット]** セクションの **[.NET Core クロスプラットフォームの開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="63b66-149">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
  * <span data-ttu-id="63b66-150">**[Web クラウド]** セクションの **[ASP.NET と Web 開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="63b66-150">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
  * <span data-ttu-id="63b66-151">**[Windows]** セクションの **[.NET デスクトップ開発]** ワークロード。</span><span class="sxs-lookup"><span data-stu-id="63b66-151">The **NET desktop development** workload in the **Windows** section.</span></span>

<span data-ttu-id="63b66-152">次の図では、Visual Studio UI で **[.NET Core クロスプラットフォームの開発]** ワークロードが選択されています。</span><span class="sxs-lookup"><span data-stu-id="63b66-152">The following image shows the **.NET Core cross-platform development** workload selected in the Visual Studio UI:</span></span>

![".NET Core クロスプラットフォームの開発" ワークロードが選択された状態の Visual Studio 2019 インストールのスクリーンショット](./media/windows-prerequisites/vs-2019-workloads.jpg)

<span data-ttu-id="63b66-154">これらのいずれかのワークロードをインストールした後は、Visual Studio 2019 16.3 では .NET Core 3.0 SDK が既定で使用されます。</span><span class="sxs-lookup"><span data-stu-id="63b66-154">Visual Studio 2019 16.3 uses .NET Core 3.0 SDK by default after any of these workloads are installed.</span></span>

<span data-ttu-id="63b66-155">既存のプロジェクトで最新の .NET Core ランタイムを使用する場合は、次の手順を使用して、既存の各 .NET Core プロジェクトのターゲットを .NET Core 3.0 に再設定します。</span><span class="sxs-lookup"><span data-stu-id="63b66-155">If you want your existing projects to use the latest .NET Core runtime, retarget each existing .NET Core project to .NET Core 3.0 using the following instructions:</span></span>

* <span data-ttu-id="63b66-156">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63b66-156">On the **Project** menu, choose **Properties**.</span></span>
* <span data-ttu-id="63b66-157">**[ターゲット フレームワーク]** 選択メニューで、値を **[.NET Core 3.0]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="63b66-157">In the **Target framework** selection menu, set the value to **.NET Core 3.0**.</span></span>

![ターゲット フレームワーク メニュー項目で [.NET Core 3.0] が選択された Visual Studio 2019 のアプリケーション プロジェクト プロパティのスクリーンショット](./media/windows-prerequisites/target-dotnet-core-3-0.jpg)

<span data-ttu-id="63b66-159">Visual Studio が .NET Core 3.0 SDK で構成されている場合は、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="63b66-159">Once you have Visual Studio configured with .NET Core 3.0 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="63b66-160">既存の .NET Core 1.x および 2.x プロジェクトを開き、ビルドし、実行する。</span><span class="sxs-lookup"><span data-stu-id="63b66-160">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="63b66-161">.NET Core 1.x および 2.x プロジェクトのターゲットを .NET Core 3.0 に再設定し、ビルドし、実行する。</span><span class="sxs-lookup"><span data-stu-id="63b66-161">Retarget .NET Core 1.x and 2.x projects to .NET Core 3.0, build, and run.</span></span>
* <span data-ttu-id="63b66-162">.NET Core 3.0 の新しいプロジェクトを作成する。</span><span class="sxs-lookup"><span data-stu-id="63b66-162">Create new .NET Core 3.0 projects.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="63b66-163">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="63b66-163">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="63b66-164">Visual Studio 2017 で .NET Core 2.2 SDK を使用して .NET Core アプリを開発するには:</span><span class="sxs-lookup"><span data-stu-id="63b66-164">To develop .NET Core apps in Visual Studio 2017 using the .NET Core 2.2 SDK:</span></span>

* <span data-ttu-id="63b66-165">( **[他のツールセット]** セクションで) **[.NET Core クロスプラットフォームの開発]** ワークロードを選択して、[Visual Studio 2019 バージョン 16.3 以降をダウンロードしてインストール](/visualstudio/install/install-visual-studio)します。</span><span class="sxs-lookup"><span data-stu-id="63b66-165">[Download and install Visual Studio 2019 version 16.3 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>
* <span data-ttu-id="63b66-166">( **[その他のツールセット]** セクションで) **[.NET Core クロスプラットフォームの開発]** ワークロードを選択して、[Visual Studio 2017 バージョン 15.9.0 以降をダウンロードしてインストール](/visualstudio/install/install-visual-studio)します。</span><span class="sxs-lookup"><span data-stu-id="63b66-166">[Download and install Visual Studio 2017 version 15.9.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![".NET Core クロスプラットフォームの開発" ワークロードが選択された状態の Visual Studio 2017 インストールのスクリーン ショット](./media/windows-prerequisites/vs-2017-workloads.jpg)

<span data-ttu-id="63b66-168">**.NET Core クロスプラットフォーム開発**ツールセットをインストールすると、通常、Visual Studio には以前のバージョンの .NET Core SDK がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="63b66-168">After the **.NET Core cross-platform development** toolset is installed, Visual Studio usually installs a previous version of the .NET Core SDK.</span></span>
<span data-ttu-id="63b66-169">たとえば、ワークロードをインストールすると、Visual Studio 2017 15.9 には既定で .NET Core 2.1 SDK が使用されます。</span><span class="sxs-lookup"><span data-stu-id="63b66-169">For example, Visual Studio 2017 15.9 uses .NET Core 2.1 SDK by default after the workload is installed.</span></span>

<span data-ttu-id="63b66-170">.NET Core 2.2 SDK を使用するように Visual Studio を更新するには:</span><span class="sxs-lookup"><span data-stu-id="63b66-170">To update Visual Studio to use .NET Core 2.2 SDK:</span></span>

 1. <span data-ttu-id="63b66-171">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="63b66-171">Install the [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download).</span></span>

 1. <span data-ttu-id="63b66-172">プロジェクトで最新の .NET Core ランタイムを使用する場合は、次の手順を使用して、既存または新規の各 .NET Core プロジェクトのターゲットを .NET Core 2.2 に再設定します。</span><span class="sxs-lookup"><span data-stu-id="63b66-172">If you want your project to use the latest .NET Core runtime, retarget each existing or new .NET Core project to .NET Core 2.2 using the following instructions:</span></span>

    * <span data-ttu-id="63b66-173">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63b66-173">On the **Project** menu, choose **Properties**.</span></span>
    * <span data-ttu-id="63b66-174">**[ターゲット フレームワーク]** 選択メニューで、値を **[.NET Core 2.2]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="63b66-174">In the **Target framework** selection menu, set the value to **.NET Core 2.2**.</span></span>

![ターゲット フレームワーク メニュー項目で [.NET Core 2.2] が選択された Visual Studio 2017 のアプリケーション プロジェクト プロパティのスクリーンショット](./media/windows-prerequisites/targeting-dotnet-core.jpg)

<span data-ttu-id="63b66-176">Visual Studio が .NET Core 2.2 SDK で構成されている場合は、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="63b66-176">Once you have Visual Studio configured with .NET Core 2.2 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="63b66-177">既存の .NET Core 1.x および 2.x プロジェクトを開き、ビルドし、実行する。</span><span class="sxs-lookup"><span data-stu-id="63b66-177">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="63b66-178">.NET Core 1.x および 2.x プロジェクトを .NET Core 2.2 に再ターゲットし、ビルドし、実行する。</span><span class="sxs-lookup"><span data-stu-id="63b66-178">Retarget .NET Core 1.x and 2.x projects to .NET Core 2.2, build, and run.</span></span>
* <span data-ttu-id="63b66-179">.NET Core 2.2 の新しいプロジェクトを作成する。</span><span class="sxs-lookup"><span data-stu-id="63b66-179">Create new .NET Core 2.2 projects.</span></span>

---
