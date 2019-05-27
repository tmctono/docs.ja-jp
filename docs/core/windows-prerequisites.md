---
title: Windows における .NET Core の前提条件
description: Windows コンピューターで .NET Core アプリケーションを開発および実行する場合に必要な依存関係について説明します。
ms.custom: updateeachvsrelease
ms.date: 04/08/2019
ms.openlocfilehash: 423a333edf5b2946a28855352adf2915642b1eae
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2019
ms.locfileid: "66051968"
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="12917-103">Windows における .NET Core の前提条件</span><span class="sxs-lookup"><span data-stu-id="12917-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="12917-104">この記事では、Windows 上で .NET Core アプリケーションを実行するためにサポートされる OS のバージョンについて説明します。</span><span class="sxs-lookup"><span data-stu-id="12917-104">This article shows the supported OS versions in order to run .NET Core applications on Windows.</span></span> <span data-ttu-id="12917-105">後述のサポート対象 OS のバージョンと依存関係は、Windows で .NET Core アプリを開発する次の 3 つの方法に適用されます。</span><span class="sxs-lookup"><span data-stu-id="12917-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="12917-106">コマンド ライン</span><span class="sxs-lookup"><span data-stu-id="12917-106">Command line</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="12917-107">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="12917-107">Visual Studio</span></span>](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)
* [<span data-ttu-id="12917-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="12917-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

<span data-ttu-id="12917-109">また、Visual Studio 2017 を使用して Windows 上で開発している場合、.NET Core 開発でサポートされている最小バージョンの詳細については、「[Visual Studio 2017 の前提条件](#prerequisites-with-visual-studio-2017)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="12917-109">Also, if you're developing on Windows using Visual Studio 2017, the [Prerequisites with Visual Studio 2017](#prerequisites-with-visual-studio-2017) section goes in more detail about minimum versions supported for .NET Core development.</span></span>

## <a name="net-core-supported-windows-versions"></a><span data-ttu-id="12917-110">.NET Core がサポートされている Windows バージョン</span><span class="sxs-lookup"><span data-stu-id="12917-110">.NET Core supported Windows versions</span></span>

<span data-ttu-id="12917-111">.NET Core は、次のバージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="12917-111">.NET Core is supported on the following versions of:</span></span>

* <span data-ttu-id="12917-112">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="12917-112">Windows 7 SP1</span></span>
* <span data-ttu-id="12917-113">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="12917-113">Windows 8.1</span></span>
* <span data-ttu-id="12917-114">Windows 10 Anniversary Update (バージョン 1607) 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="12917-114">Windows 10 Anniversary Update (version 1607) or later versions</span></span>
* <span data-ttu-id="12917-115">Windows Server 2008 R2 SP1 (フル サーバーまたは Server Core)</span><span class="sxs-lookup"><span data-stu-id="12917-115">Windows Server 2008 R2 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="12917-116">Windows Server 2012 SP1 (フル サーバーまたは Server Core)</span><span class="sxs-lookup"><span data-stu-id="12917-116">Windows Server 2012 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="12917-117">Windows Server 2012 R2 (フル サーバーまたは Server Core)</span><span class="sxs-lookup"><span data-stu-id="12917-117">Windows Server 2012 R2 (Full Server or Server Core)</span></span>
* <span data-ttu-id="12917-118">Windows Server 2016 以降のバージョン (フル サーバー、Server Core、または Nano Server)</span><span class="sxs-lookup"><span data-stu-id="12917-118">Windows Server 2016 or later versions (Full Server, Server Core, or Nano Server)</span></span>

## <a name="net-core-supported-operating-systems"></a><span data-ttu-id="12917-119">.NET Core がサポートされたオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="12917-119">.NET Core supported operating systems</span></span>

<span data-ttu-id="12917-120">次の記事では、.NET Core がサポートされたオペレーティング システム (バージョンごと) の完全な一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="12917-120">The following articles have a complete list of .NET Core supported operating systems per version:</span></span>

* [<span data-ttu-id="12917-121">.NET Core 3.0 (Preview)</span><span class="sxs-lookup"><span data-stu-id="12917-121">.NET Core 3.0 (Preview)</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)
* [<span data-ttu-id="12917-122">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="12917-122">.NET Core 2.2</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [<span data-ttu-id="12917-123">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="12917-123">.NET Core 2.1</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)
* [<span data-ttu-id="12917-124">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="12917-124">.NET Core 1.0</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)

<span data-ttu-id="12917-125">ダウンロード リンクと詳細については、最新バージョンをダウンロードするには [.NET ダウンロード](https://dotnet.microsoft.com/download)、以前のバージョンについて [.NET ダウンロードのアーカイブ](https://dotnet.microsoft.com/download/archives#dotnet-core)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="12917-125">For download links and more information, see [.NET downloads](https://dotnet.microsoft.com/download) to download the latest version or [.NET downloads archive](https://dotnet.microsoft.com/download/archives#dotnet-core) for older versions.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="12917-126">.NET Core の依存関係</span><span class="sxs-lookup"><span data-stu-id="12917-126">.NET Core dependencies</span></span>

<span data-ttu-id="12917-127">.NET Core 1.1 以前のバージョンを Windows 10 と Windows Server 2016 よりも前の Windows バージョンで実行する場合、Visual C++ 再頒布可能パッケージが必要です。</span><span class="sxs-lookup"><span data-stu-id="12917-127">.NET Core 1.1 and earlier versions require the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="12917-128">この依存関係は、.NET Core インストーラーにより自動でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="12917-128">This dependency is automatically installed by the .NET Core installer.</span></span>

<span data-ttu-id="12917-129">次の場合には、[Microsoft Visual C++ 2015 再頒布可能パッケージ Update 3](https://www.microsoft.com/download/details.aspx?id=52685) を手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="12917-129">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="12917-130">[インストーラー スクリプト](./tools/dotnet-install-script.md)を使用して .NET Core をインストールする。</span><span class="sxs-lookup"><span data-stu-id="12917-130">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="12917-131">自己完結型の .NET Core アプリケーションを展開する。</span><span class="sxs-lookup"><span data-stu-id="12917-131">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="12917-132">ソースから製品をビルドする。</span><span class="sxs-lookup"><span data-stu-id="12917-132">Building the product from source.</span></span>
* <span data-ttu-id="12917-133">*.zip* ファイルを使用して .NET Core をインストールする。</span><span class="sxs-lookup"><span data-stu-id="12917-133">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="12917-134">これにはビルド/CI/CD サーバーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="12917-134">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="12917-135">**Windows 8.1 以前のバージョン、または Windows Server 2012 R2 以前のバージョンの場合:**</span><span class="sxs-lookup"><span data-stu-id="12917-135">**For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:**</span></span>
>
> <span data-ttu-id="12917-136">Windows のインストールが最新であり、Windows Update から修正プログラム [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) をインストールしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="12917-136">Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows), which can be installed through Windows Update.</span></span> <span data-ttu-id="12917-137">この更新プログラムがインストールされていない場合は、.NET Core アプリケーションを起動するときに、次のようなエラーが表示されます。`The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span><span class="sxs-lookup"><span data-stu-id="12917-137">If you don't have this update installed, you'll see an error like the following when you launch a .NET Core application: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span></span>
>
> <span data-ttu-id="12917-138">**Windows 7 または Windows Server 2008 R2 の場合:**</span><span class="sxs-lookup"><span data-stu-id="12917-138">**For Windows 7 or Windows Server 2008 R2:**</span></span>
>
> <span data-ttu-id="12917-139">KB2999226 に加え、[KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) もインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="12917-139">In addition to KB2999226, make sure you also have [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installed.</span></span> <span data-ttu-id="12917-140">この更新プログラムがインストールされていない場合は、.NET Core アプリケーションを起動するときに、次のようなエラーが表示されます。`The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`</span><span class="sxs-lookup"><span data-stu-id="12917-140">If you don't have this update installed, you'll see an error similar to the following when you launch a .NET Core application: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span></span>

## <a name="prerequisites-for-net-core-30-preview-3"></a><span data-ttu-id="12917-141">.NET Core 3.0 Preview 3 の前提条件</span><span class="sxs-lookup"><span data-stu-id="12917-141">Prerequisites for .NET Core 3.0 Preview 3</span></span>

<span data-ttu-id="12917-142">.NET Core 3.0 Preview 3 の前提条件は、.NET Core の他のバージョンと同じです。</span><span class="sxs-lookup"><span data-stu-id="12917-142">.NET Core 3.0 Preview 3 has the same prerequisites as other versions of .NET Core.</span></span> <span data-ttu-id="12917-143">ただし、Visual Studio を使用して .NET Core 3.0 プロジェクトを作成する場合は、[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12917-143">However, if you want to use Visual Studio to create .NET Core 3.0 projects, you must use the [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span></span> <span data-ttu-id="12917-144">Visual Studio 2019 は、Visual Studio の他のバージョンと競合することなく、side-by-side でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="12917-144">Visual Studio 2019 can be installed side-by-side with other versions of Visual Studio without conflict.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="12917-145">Visual Studio 2017 の前提条件</span><span class="sxs-lookup"><span data-stu-id="12917-145">Prerequisites with Visual Studio 2017</span></span>
    
<span data-ttu-id="12917-146">.NET Core SDK を使用して .NET Core アプリケーションを開発する場合は、好きなエディターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="12917-146">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="12917-147">Visual Studio 2017 では、Windows 上に .NET Core アプリ用の統合開発環境が提供されます。</span><span class="sxs-lookup"><span data-stu-id="12917-147">Visual Studio 2017 provides an integrated development environment for .NET Core apps on Windows.</span></span>

<span data-ttu-id="12917-148">Visual Studio 2017 での変更の詳細については、[リリース ノート](/visualstudio/releasenotes/vs2017-relnotes)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12917-148">You can read more about the changes in Visual Studio 2017 in the [release notes](/visualstudio/releasenotes/vs2017-relnotes).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="12917-149">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="12917-149">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="12917-150">Visual Studio 2017 で .NET Core 2.2 SDK を使用して .NET Core アプリを開発するには:</span><span class="sxs-lookup"><span data-stu-id="12917-150">To develop .NET Core apps in Visual Studio 2017 using the .NET Core 2.2 SDK:</span></span>

 1. <span data-ttu-id="12917-151">(**[その他のツールセット]** セクションで) **[.NET Core クロスプラットフォームの開発]** ワークロードを選択して、[Visual Studio 2017 バージョン 15.9.0 以降をダウンロードしてインストール](/visualstudio/install/install-visual-studio)します。</span><span class="sxs-lookup"><span data-stu-id="12917-151">[Download and install Visual Studio 2017 version 15.9.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![".NET Core クロスプラットフォームの開発" ワークロードが選択された状態の Visual Studio 2017 インストールのスクリーン ショット](./media/windows-prerequisites/vs-2017-workloads.jpg)

<span data-ttu-id="12917-153">**.NET Core クロスプラットフォーム開発**ツールセットをインストールすると、通常、Visual Studio には以前のバージョンの .NET Core SDK がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="12917-153">After the **.NET Core cross-platform development** toolset is installed, Visual Studio usually installs a previous version of the .NET Core SDK.</span></span>
<span data-ttu-id="12917-154">たとえば、ワークロードをインストールすると、Visual Studio 2017 15.9 には既定で .NET Core 2.1 SDK が使用されます。</span><span class="sxs-lookup"><span data-stu-id="12917-154">For example, Visual Studio 2017 15.9 uses .NET Core 2.1 SDK by default after the workload is installed.</span></span>

<span data-ttu-id="12917-155">.NET Core 2.2 SDK を使用するように Visual Studio を更新するには:</span><span class="sxs-lookup"><span data-stu-id="12917-155">To update Visual Studio to use .NET Core 2.2 SDK:</span></span>

 1. <span data-ttu-id="12917-156">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="12917-156">Install the [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download).</span></span>

 1. <span data-ttu-id="12917-157">プロジェクトで最新の .NET Core ランタイムを使用する場合は、次の手順を使用して、既存または新規の .NET Core プロジェクトを .NET Core 2.2 に再ターゲットします。</span><span class="sxs-lookup"><span data-stu-id="12917-157">If you want your project to use the latest .NET Core runtime, retarget existing or new .NET Core projects to .NET Core 2.2 using the following instructions:</span></span>

    * <span data-ttu-id="12917-158">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12917-158">On the **Project** menu, choose **Properties**.</span></span>
    * <span data-ttu-id="12917-159">**[ターゲット フレームワーク]** 選択メニューで、値を **[.NET Core 2.2]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="12917-159">In the **Target framework** selection menu, set the value to **.NET Core 2.2**.</span></span>

![ターゲット フレームワーク メニュー項目で [.NET Core 2.2] が選択された Visual Studio 2017 のアプリケーション プロジェクト プロパティのスクリーンショット](./media/windows-prerequisites/targeting-dotnet-core.jpg)

<span data-ttu-id="12917-161">Visual Studio が .NET Core 2.2 SDK で構成されている場合は、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="12917-161">Once you have Visual Studio configured with .NET Core 2.2 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="12917-162">既存の .NET Core 1.x および 2.x プロジェクトを開き、ビルドし、実行する。</span><span class="sxs-lookup"><span data-stu-id="12917-162">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="12917-163">.NET Core 1.x および 2.x プロジェクトを .NET Core 2.2 に再ターゲットし、ビルドし、実行する。</span><span class="sxs-lookup"><span data-stu-id="12917-163">Retarget .NET Core 1.x and 2.x projects to .NET Core 2.2, build, and run.</span></span>
* <span data-ttu-id="12917-164">.NET Core 2.2 の新しいプロジェクトを作成する。</span><span class="sxs-lookup"><span data-stu-id="12917-164">Create new .NET Core 2.2 projects.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="12917-165">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="12917-165">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="12917-166">Visual Studio で .NET Core 1.x アプリを開発するには、(**[その他のツールセット]** セクションで) **[.NET Core クロスプラットフォームの開発]** ワークロードを選択して、[Visual Studio 2017 をダウンロードしてインストール](/visualstudio/install/install-visual-studio)します。</span><span class="sxs-lookup"><span data-stu-id="12917-166">To develop .NET Core 1.x apps in Visual Studio, [download and install Visual Studio 2017](/visualstudio/install/install-visual-studio) with the **".NET Core cross-platform development"** workload (in the **Other Toolsets** section) selected.</span></span>

![".NET Core クロスプラットフォームの開発" ワークロードが選択された状態の Visual Studio 2017 インストールのスクリーン ショット](./media/windows-prerequisites/vs-workloads.jpg)

> [!IMPORTANT]
> <span data-ttu-id="12917-168">.NET Core 1.x の開発に Visual Studio 2015 を使用することはできますが、次の理由からお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="12917-168">It's possible to use Visual Studio 2015 for .NET Core 1.x development, but it's not recommended for the following reasons:</span></span>
  > * <span data-ttu-id="12917-169">.NET Core Tooling は、サポートされていないプレビュー バージョンです。</span><span class="sxs-lookup"><span data-stu-id="12917-169">The .NET Core tooling is a preview version, which is not supported.</span></span>
  > * <span data-ttu-id="12917-170">プロジェクトは、非推奨の project.json ベースです。</span><span class="sxs-lookup"><span data-stu-id="12917-170">The projects are project.json-based, which is deprecated.</span></span>
>
> <span data-ttu-id="12917-171">プロジェクト形式の変更の詳細については、[変更点の概要](./tools/cli-msbuild-architecture.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="12917-171">For more information about the project format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>

---

<a name="vs-mapping"></a>

> [!TIP]
> <span data-ttu-id="12917-172">お使いの Visual Studio バージョンを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="12917-172">To verify your Visual Studio version:</span></span>
>
> * <span data-ttu-id="12917-173">**[ヘルプ]** メニューの **[About Microsoft Visual Studio]** (Microsoft Visual Studio のバージョン情報) を選択します。</span><span class="sxs-lookup"><span data-stu-id="12917-173">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
> * <span data-ttu-id="12917-174">**[Microsoft Visual Studio のバージョン情報]** ダイアログで、バージョン番号を確認します。</span><span class="sxs-lookup"><span data-stu-id="12917-174">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>
>   * <span data-ttu-id="12917-175">.NET Core 3.0 Preview 3 アプリの場合は、Visual Studio 2019 バージョン 16.0 以降です。</span><span class="sxs-lookup"><span data-stu-id="12917-175">For .NET Core 3.0 Preview 3 apps, Visual Studio 2019 version 16.0 or higher.</span></span>
>   * <span data-ttu-id="12917-176">.NET Core 2.2 アプリの場合は、Visual Studio 2017 バージョン 15.9 以降です。</span><span class="sxs-lookup"><span data-stu-id="12917-176">For .NET Core 2.2 apps, Visual Studio 2017 version 15.9 or higher.</span></span>
>   * <span data-ttu-id="12917-177">.NET Core 2.1 アプリの場合は、Visual Studio 2017 バージョン 15.7 以降です。</span><span class="sxs-lookup"><span data-stu-id="12917-177">For .NET Core 2.1 apps, Visual Studio 2017 version 15.7 or higher.</span></span>
>   * <span data-ttu-id="12917-178">.NET Core 1.x アプリの場合は、Visual Studio 2017 バージョン 15.0 以降です。</span><span class="sxs-lookup"><span data-stu-id="12917-178">For .NET Core 1.x apps, Visual Studio 2017 version 15.0 or higher.</span></span>
