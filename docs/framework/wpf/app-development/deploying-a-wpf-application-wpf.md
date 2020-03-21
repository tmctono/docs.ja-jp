---
title: アプリのデプロイ
ms.date: 03/30/2017
helpviewer_keywords:
- WPF applications [WPF], deployment
- deployment [WPF], applications
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
ms.openlocfilehash: 54d14503a0f65bb50f2dfb14d40af3b47d51589c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186313"
---
# <a name="deploy-a-wpf-application"></a><span data-ttu-id="13225-102">WPF アプリケーションを展開する</span><span class="sxs-lookup"><span data-stu-id="13225-102">Deploy a WPF Application</span></span>

<span data-ttu-id="13225-103">Windows プレゼンテーション ファンデーション (WPF) アプリケーションをビルドした後、展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13225-103">After Windows Presentation Foundation (WPF) applications are built, they need to be deployed.</span></span> <span data-ttu-id="13225-104">Windows と .NET Framework には、いくつかの展開テクノロジが含まれています。</span><span class="sxs-lookup"><span data-stu-id="13225-104">Windows and the .NET Framework include several deployment technologies.</span></span> <span data-ttu-id="13225-105">WPF アプリケーションの展開に使用される配置テクノロジは、アプリケーションの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="13225-105">The deployment technology that is used to deploy a WPF application depends on the application type.</span></span> <span data-ttu-id="13225-106">このトピックでは、各展開テクノロジの概要と、各 WPF アプリケーションの種類の展開要件と共に使用する方法について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="13225-106">This topic provides a brief overview of each deployment technology, and how they are used in conjunction with the deployment requirements of each WPF application type.</span></span>

<a name="Deployment_Technologies"></a>
## <a name="deployment-technologies"></a><span data-ttu-id="13225-107">配置テクノロジ</span><span class="sxs-lookup"><span data-stu-id="13225-107">Deployment Technologies</span></span>  
 <span data-ttu-id="13225-108">Windows と .NET Framework には、次のようないくつかの展開テクノロジが含まれています。</span><span class="sxs-lookup"><span data-stu-id="13225-108">Windows and the .NET Framework include several deployment technologies, including:</span></span>  
  
- <span data-ttu-id="13225-109">XCopy による配置。</span><span class="sxs-lookup"><span data-stu-id="13225-109">XCopy deployment.</span></span>  
  
- <span data-ttu-id="13225-110">Windows インストーラーの配置。</span><span class="sxs-lookup"><span data-stu-id="13225-110">Windows Installer deployment.</span></span>  
  
- <span data-ttu-id="13225-111">ClickOnce 配置。</span><span class="sxs-lookup"><span data-stu-id="13225-111">ClickOnce deployment.</span></span>  
  
<a name="XCopy_Deployment"></a>
### <a name="xcopy-deployment"></a><span data-ttu-id="13225-112">XCopy による配置</span><span class="sxs-lookup"><span data-stu-id="13225-112">XCopy Deployment</span></span>  
 <span data-ttu-id="13225-113">XCopy による配置とは、XCopy コマンド ライン プログラムを使用して、ある場所から別の場所へファイルをコピーすることです。</span><span class="sxs-lookup"><span data-stu-id="13225-113">XCopy deployment refers to the use of the XCopy command-line program to copy files from one location to another.</span></span> <span data-ttu-id="13225-114">XCopy による配置は、次のような状況に適しています。</span><span class="sxs-lookup"><span data-stu-id="13225-114">XCopy deployment is suitable under the following circumstances:</span></span>  
  
- <span data-ttu-id="13225-115">アプリケーションは自己完結型である。</span><span class="sxs-lookup"><span data-stu-id="13225-115">The application is self-contained.</span></span> <span data-ttu-id="13225-116">実行するためにクライアントを更新する必要がない。</span><span class="sxs-lookup"><span data-stu-id="13225-116">It does not need to update the client to run.</span></span>  
  
- <span data-ttu-id="13225-117">アプリケーション ファイルは、ビルド場所 (ローカル ディスク、UNC ファイル共有など) から発行場所 (Web サイト、UNC ファイル共有など) に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13225-117">Application files must be moved from one location to another, such as from a build location (local disk, UNC file share, and so on) to a publish location (Web site, UNC file share, and so on).</span></span>  
  
- <span data-ttu-id="13225-118">アプリケーションはシェル統合 ([スタート] メニューのショートカット、デスクトップ アイコンなど) を必要としない。</span><span class="sxs-lookup"><span data-stu-id="13225-118">The application does not require shell integration (Start menu shortcut, desktop icon, and so on).</span></span>  
  
 <span data-ttu-id="13225-119">XCopy は、単純な配置シナリオには適していますが、複雑な配置機能が必要なシナリオには十分に対応できません。</span><span class="sxs-lookup"><span data-stu-id="13225-119">Although XCopy is suitable for simple deployment scenarios, it is limited when more complex deployment capabilities are required.</span></span> <span data-ttu-id="13225-120">特に、配置を堅牢な方法で管理する場合、XCopy を使用すると、スクリプトの作成、実行、および維持というオーバーヘッドが生じます。</span><span class="sxs-lookup"><span data-stu-id="13225-120">In particular, using XCopy often incurs the overhead for creating, executing, and maintaining scripts for managing deployment in a robust way.</span></span> <span data-ttu-id="13225-121">さらに、XCopy は、バージョン管理、アンインストール、およびロールバックをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="13225-121">Furthermore, XCopy does not support versioning, uninstallation, or rollback.</span></span>  
  
<a name="Windows_Installer"></a>
### <a name="windows-installer"></a><span data-ttu-id="13225-122">Windows インストーラー</span><span class="sxs-lookup"><span data-stu-id="13225-122">Windows Installer</span></span>  
 <span data-ttu-id="13225-123">Windows インストーラを使用すると、アプリケーションを自己完結型の実行可能ファイルとしてパッケージ化し、クライアントに簡単に配布して実行できます。</span><span class="sxs-lookup"><span data-stu-id="13225-123">Windows Installer allows applications to be packaged as self-contained executables that can be easily distributed to clients and run.</span></span> <span data-ttu-id="13225-124">さらに、Windows インストーラは Windows と共にインストールされ、デスクトップ、スタート メニュー、およびコントロール パネルの [プログラム] との統合が可能になります。</span><span class="sxs-lookup"><span data-stu-id="13225-124">Furthermore, Windows Installer is installed with Windows and enables integration with the desktop, the Start menu, and the Programs control panel.</span></span>  
  
 <span data-ttu-id="13225-125">Windows インストーラは、アプリケーションのインストールとアンインストールを簡略化しますが、インストールされているアプリケーションをバージョン管理の観点から最新の状態に保つ機能は提供しません。</span><span class="sxs-lookup"><span data-stu-id="13225-125">Windows Installer simplifies the installation and uninstallation of applications, but it does not provide facilities for ensuring that installed applications are kept up-to-date from a versioning standpoint.</span></span>  
  
 <span data-ttu-id="13225-126">Windows インストーラの詳細については、「 [Windows インストーラの展開](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13225-126">For more information about Windows Installer, see [Windows Installer Deployment](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span></span>
  
<a name="ClickOnce_Deployment"></a>
### <a name="clickonce-deployment"></a><span data-ttu-id="13225-127">ClickOnce の配置</span><span class="sxs-lookup"><span data-stu-id="13225-127">ClickOnce Deployment</span></span>  
 <span data-ttu-id="13225-128">ClickOnce は、Web スタイル以外のアプリケーションに対する Web スタイルのアプリケーションの配置を有効にします。</span><span class="sxs-lookup"><span data-stu-id="13225-128">ClickOnce enables Web-style application deployment for non-Web applications.</span></span> <span data-ttu-id="13225-129">アプリケーションは、Web サーバーまたはファイル サーバーに公開され、これらのサーバーから配置されます。</span><span class="sxs-lookup"><span data-stu-id="13225-129">Applications are published to and deployed from Web or file servers.</span></span> <span data-ttu-id="13225-130">ClickOnce は、Windows インストーラでインストールされたアプリケーションが実行するクライアント機能の完全な範囲をサポートしていませんが、次のようなサブセットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="13225-130">Although ClickOnce does not support the full range of client features that Windows Installer-installed applications do, it does support a subset that includes the following:</span></span>  
  
- <span data-ttu-id="13225-131">[スタート] メニューおよび [プログラム] コントロール パネルとの統合。</span><span class="sxs-lookup"><span data-stu-id="13225-131">Integration with the Start menu and Programs control panel.</span></span>  
  
- <span data-ttu-id="13225-132">バージョン管理、ロールバック、およびアンインストール。</span><span class="sxs-lookup"><span data-stu-id="13225-132">Versioning, rollback, and uninstallation.</span></span>  
  
- <span data-ttu-id="13225-133">アプリケーションを常に配置場所から起動するオンライン インストール モード。</span><span class="sxs-lookup"><span data-stu-id="13225-133">Online install mode, which always launches an application from the deployment location.</span></span>  
  
- <span data-ttu-id="13225-134">新しいバージョンがリリースされたときの自動更新。</span><span class="sxs-lookup"><span data-stu-id="13225-134">Automatic updating when new versions are released.</span></span>  
  
- <span data-ttu-id="13225-135">ファイル拡張子の登録。</span><span class="sxs-lookup"><span data-stu-id="13225-135">Registration of file extensions.</span></span>  
  
 <span data-ttu-id="13225-136">ClickOnce の詳細については、「 [ClickOnce のセキュリティと配置](/visualstudio/deployment/clickonce-security-and-deployment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13225-136">For more information about ClickOnce, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
<a name="Deploying_WPF_Applications"></a>
## <a name="deploying-wpf-applications"></a><span data-ttu-id="13225-137">WPF アプリケーションの配置</span><span class="sxs-lookup"><span data-stu-id="13225-137">Deploying WPF Applications</span></span>  
 <span data-ttu-id="13225-138">WPF アプリケーションの配置オプションは、アプリケーションの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="13225-138">The deployment options for a WPF application depend on the type of application.</span></span> <span data-ttu-id="13225-139">展開の観点から見ると、WPF には次の 3 つの重要なアプリケーションの種類があります。</span><span class="sxs-lookup"><span data-stu-id="13225-139">From a deployment perspective, WPF has three significant application types:</span></span>  
  
- <span data-ttu-id="13225-140">スタンドアロン アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="13225-140">Standalone applications.</span></span>  
  
- <span data-ttu-id="13225-141">マークアップのみの [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="13225-141">Markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] applications.</span></span>  
  
- <span data-ttu-id="13225-142">XAML ブラウザー アプリケーション (XBaPs)</span><span class="sxs-lookup"><span data-stu-id="13225-142">XAML browser applications (XBAPs).</span></span>  
  
<a name="Deploying_Standalone_Applications"></a>
### <a name="deploying-standalone-applications"></a><span data-ttu-id="13225-143">スタンドアロン アプリケーションの配置</span><span class="sxs-lookup"><span data-stu-id="13225-143">Deploying Standalone Applications</span></span>  
 <span data-ttu-id="13225-144">スタンドアロン アプリケーションは、ClickOnce または Windows インストーラーを使用して展開されます。</span><span class="sxs-lookup"><span data-stu-id="13225-144">Standalone applications are deployed using either ClickOnce or Windows Installer.</span></span> <span data-ttu-id="13225-145">いずれの場合も、スタンドアロン アプリケーションを実行するには、アプリケーションが完全に信頼されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="13225-145">Either way, standalone applications require full trust to run.</span></span> <span data-ttu-id="13225-146">完全な信頼は、Windows インストーラを使用して展開されるスタンドアロン アプリケーションに自動的に付与されます。</span><span class="sxs-lookup"><span data-stu-id="13225-146">Full trust is automatically granted to standalone applications that are deployed using Windows Installer.</span></span> <span data-ttu-id="13225-147">ClickOnce を使用して配置されたスタンドアロン アプリケーションには、自動的に完全な信頼が付与されません。</span><span class="sxs-lookup"><span data-stu-id="13225-147">Standalone applications that are deployed using ClickOnce are not automatically granted full trust.</span></span> <span data-ttu-id="13225-148">代わりに、スタンドアロン アプリケーションをインストールする前にユーザーが受け入れる必要があるセキュリティ警告ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="13225-148">Instead, ClickOnce displays a security warning dialog that users must accept before a standalone application is installed.</span></span> <span data-ttu-id="13225-149">受け入れた場合、スタンドアロン アプリケーションがインストールされ、完全な信頼が付与されます。</span><span class="sxs-lookup"><span data-stu-id="13225-149">If accepted, the standalone application is installed and granted full trust.</span></span> <span data-ttu-id="13225-150">受け入れなかった場合、スタンドアロン アプリケーションはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="13225-150">If not, the standalone application is not installed.</span></span>  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>
### <a name="deploying-markup-only-xaml-applications"></a><span data-ttu-id="13225-151">マークアップのみの XAML アプリケーションの配置</span><span class="sxs-lookup"><span data-stu-id="13225-151">Deploying Markup-Only XAML Applications</span></span>  
 <span data-ttu-id="13225-152">マークアップのみの[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]ページは、通常 HTML ページなどの Web サーバーに発行され、Internet Explorer を使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="13225-152">Markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages are usually published to Web servers, like HTML pages, and can be viewed using Internet Explorer.</span></span> <span data-ttu-id="13225-153">マークアップのみの [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ページは、部分信頼セキュリティ サンドボックス内で実行され、インターネット ゾーン アクセス許可セットによって定義された制約が適用されます。</span><span class="sxs-lookup"><span data-stu-id="13225-153">Markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages run within a partial-trust security sandbox with restrictions that are defined by the Internet zone permission set.</span></span> <span data-ttu-id="13225-154">これにより、HTML ベースの Web アプリケーションと同等のセキュリティサンドボックスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="13225-154">This provides an equivalent security sandbox to HTML-based Web applications.</span></span>  
  
 <span data-ttu-id="13225-155">WPF アプリケーションのセキュリティの詳細については、「[セキュリティ](../security-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13225-155">For more information about security for WPF applications, see [Security](../security-wpf.md).</span></span>  
  
 <span data-ttu-id="13225-156">マークアップのみの[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]ページは、XCopy または Windows インストーラを使用してローカル ファイル システムにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="13225-156">Markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages can be installed to the local file system by using either XCopy or Windows Installer.</span></span> <span data-ttu-id="13225-157">これらのページは、インターネット エクスプローラまたはエクスプローラを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="13225-157">These pages can be viewed using Internet Explorer or Windows Explorer.</span></span>  
  
 <span data-ttu-id="13225-158">XAML の詳細については、「[XAML の概要 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13225-158">For more information about XAML, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md).</span></span>  
  
<a name="Deploying_XAML_Browser_Applications"></a>
### <a name="deploying-xaml-browser-applications"></a><span data-ttu-id="13225-159">XAML ブラウザー アプリケーションの配置</span><span class="sxs-lookup"><span data-stu-id="13225-159">Deploying XAML Browser Applications</span></span>  
 <span data-ttu-id="13225-160">XBaps は、次の 3 つのファイルをデプロイする必要があるコンパイル済みアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="13225-160">XBAPs are compiled applications that require the following three files to be deployed:</span></span>  
  
- <span data-ttu-id="13225-161">*ApplicationName*.exe: 実行可能アセンブリのアプリケーション ファイル。</span><span class="sxs-lookup"><span data-stu-id="13225-161">*ApplicationName*.exe: The executable assembly application file.</span></span>  
  
- <span data-ttu-id="13225-162">*ApplicationName*.xbap: 配置マニフェスト。</span><span class="sxs-lookup"><span data-stu-id="13225-162">*ApplicationName*.xbap: The deployment manifest.</span></span>  
  
- <span data-ttu-id="13225-163">*ApplicationName*.exe.manifest: アプリケーション マニフェスト。</span><span class="sxs-lookup"><span data-stu-id="13225-163">*ApplicationName*.exe.manifest: The application manifest.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="13225-164">配置マニフェストおよびアプリケーション マニフェストの詳細については、「[WPF アプリケーションのビルド](building-a-wpf-application-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13225-164">For more information about deployment and application manifests, see [Building a WPF Application](building-a-wpf-application-wpf.md).</span></span>  
  
 <span data-ttu-id="13225-165">これらのファイルは、XBAP が構築されるときに生成されます。</span><span class="sxs-lookup"><span data-stu-id="13225-165">These files are produced when an XBAP is built.</span></span> <span data-ttu-id="13225-166">詳細については、「[方法: 新しい WPF ブラウザー アプリケーション プロジェクトを作成する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13225-166">For more information, see [How to: Create a New WPF Browser Application Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100)).</span></span> <span data-ttu-id="13225-167">マークアップのみの[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]ページと同様に、XBaap は通常 Web サーバーに公開され、Internet Explorer を使用して表示されます。</span><span class="sxs-lookup"><span data-stu-id="13225-167">Like markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages, XBAPs are typically published to a Web server and viewed using Internet Explorer.</span></span>  
  
 <span data-ttu-id="13225-168">XBaPs は、任意の展開手法を使用してクライアントに展開できます。</span><span class="sxs-lookup"><span data-stu-id="13225-168">XBAPs can be deployed to clients using any of the deployment techniques.</span></span> <span data-ttu-id="13225-169">ただし、次の機能を提供するため、ClickOnce をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="13225-169">However, ClickOnce is recommended since it provides the following capabilities:</span></span>  
  
1. <span data-ttu-id="13225-170">新しいバージョンが公開されたときの自動更新。</span><span class="sxs-lookup"><span data-stu-id="13225-170">Automatic updates when a new version is published.</span></span>  
  
2. <span data-ttu-id="13225-171">完全信頼で実行されている XBAP の昇格特権。</span><span class="sxs-lookup"><span data-stu-id="13225-171">Elevation privileges for the XBAP running with full trust.</span></span>  
  
 <span data-ttu-id="13225-172">既定では、ClickOnce は、.deploy 拡張子を持つアプリケーション ファイルを公開します。</span><span class="sxs-lookup"><span data-stu-id="13225-172">By default, ClickOnce publishes application files with the .deploy extension.</span></span> <span data-ttu-id="13225-173">これは問題になる可能性がありますが、無効にできます。</span><span class="sxs-lookup"><span data-stu-id="13225-173">This can be problematic, but can be disabled.</span></span> <span data-ttu-id="13225-174">詳細については、「[ClickOnce 配置でのサーバーおよびクライアント構成の問題](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13225-174">For more information, see [Server and Client Configuration Issues in ClickOnce Deployments](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments).</span></span>  
  
 <span data-ttu-id="13225-175">XAML ブラウザー アプリケーション (XAPS) の展開の詳細については、「 [WPF XAML ブラウザー アプリケーションの概要](wpf-xaml-browser-applications-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13225-175">For more information about deploying XAML browser applications (XBAPs), see [WPF XAML Browser Applications Overview](wpf-xaml-browser-applications-overview.md).</span></span>  
  
<a name="Installing__NET_Framework_3_0"></a>
## <a name="installing-the-net-framework"></a><span data-ttu-id="13225-176">.NET Framework のインストール</span><span class="sxs-lookup"><span data-stu-id="13225-176">Installing the .NET Framework</span></span>  
 <span data-ttu-id="13225-177">WPF アプリケーションを実行するには、クライアントに Microsoft .NET Framework をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="13225-177">To run a WPF application, the Microsoft .NET Framework must be installed on the client.</span></span> <span data-ttu-id="13225-178">WPF ブラウザー でホストされているアプリケーションを表示すると、クライアントが .NET Framework と共にインストールされているかどうかが自動的に検出されます。</span><span class="sxs-lookup"><span data-stu-id="13225-178">Internet Explorer automatically detects whether clients are installed with .NET Framework when WPF browser-hosted applications are viewed.</span></span> <span data-ttu-id="13225-179">.NET Framework がインストールされていない場合は、インストールを求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="13225-179">If the .NET Framework is not installed, Internet Explorer prompts users to install it.</span></span>  
  
 <span data-ttu-id="13225-180">.NET Framework がインストールされているかどうかを検出するために、Internet Explorer には、次の拡張子を持つコンテンツ ファイルのフォールバック多目的インターネット メール拡張機能 (MIME) ハンドラーとして登録されているブートストラップ アプリケーションが含まれています。、および .アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="13225-180">To detect whether the .NET Framework is installed, Internet Explorer includes a bootstrapper application that is registered as the fallback Multipurpose Internet Mail Extensions (MIME) handler for content files with the following extensions: .xaml, .xps, .xbap, and .application.</span></span> <span data-ttu-id="13225-181">これらのファイルの種類に移動し、.NET Framework がクライアントにインストールされていない場合、ブートストラップ アプリケーションはインストールのアクセス許可を要求します。</span><span class="sxs-lookup"><span data-stu-id="13225-181">If you navigate to these file types and the .NET Framework is not installed on the client, the bootstrapper application requests permission to install it.</span></span> <span data-ttu-id="13225-182">アクセス許可が与えられる場合は、.NET Framework もアプリケーションもインストールされません。</span><span class="sxs-lookup"><span data-stu-id="13225-182">If permission is not provided, neither the .NET Framework nor the application is installed.</span></span>  
  
 <span data-ttu-id="13225-183">アクセス許可が与えられている場合、Internet Explorer は、Microsoft バックグラウンド インテリジェント転送サービス (BITS) を使用して .NET Framework をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="13225-183">If permission is granted, Internet Explorer downloads and installs the .NET Framework using the Microsoft Background Intelligent Transfer Service (BITS).</span></span> <span data-ttu-id="13225-184">.NET Framework のインストールが成功すると、最初に要求されたファイルが新しいブラウザー ウィンドウで開かれます。</span><span class="sxs-lookup"><span data-stu-id="13225-184">After successful installation of the .NET Framework, the originally requested file is opened in a new browser window.</span></span>  
  
 <span data-ttu-id="13225-185">詳細については、「[.NET Framework およびアプリケーションの配置](../../deployment/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13225-185">For more information, see [Deploying the .NET Framework and Applications](../../deployment/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13225-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="13225-186">See also</span></span>

- [<span data-ttu-id="13225-187">WPF アプリケーションのビルド</span><span class="sxs-lookup"><span data-stu-id="13225-187">Building a WPF Application</span></span>](building-a-wpf-application-wpf.md)
- [<span data-ttu-id="13225-188">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="13225-188">Security</span></span>](../security-wpf.md)
