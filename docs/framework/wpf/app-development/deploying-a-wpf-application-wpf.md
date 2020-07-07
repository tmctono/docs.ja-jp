---
title: アプリのデプロイ
description: Windows と .NET Framework が Windows Presentation Foundation (WPF) アプリケーションに使用する配置テクノロジについて説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- WPF applications [WPF], deployment
- deployment [WPF], applications
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
ms.openlocfilehash: 62904ccd47800c8340d68c223e50688902170063
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619300"
---
# <a name="deploy-a-wpf-application"></a><span data-ttu-id="5aa53-103">WPF アプリケーションを配置する</span><span class="sxs-lookup"><span data-stu-id="5aa53-103">Deploy a WPF Application</span></span>

<span data-ttu-id="5aa53-104">ビルドされた Windows Presentation Foundation (WPF) アプリケーションは、配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aa53-104">After Windows Presentation Foundation (WPF) applications are built, they need to be deployed.</span></span> <span data-ttu-id="5aa53-105">Windows および .NET Framework には、いくつかの配置テクノロジがあります。</span><span class="sxs-lookup"><span data-stu-id="5aa53-105">Windows and the .NET Framework include several deployment technologies.</span></span> <span data-ttu-id="5aa53-106">WPF アプリケーションの配置に使用される配置テクノロジは、アプリケーションの種類によって決まります。</span><span class="sxs-lookup"><span data-stu-id="5aa53-106">The deployment technology that is used to deploy a WPF application depends on the application type.</span></span> <span data-ttu-id="5aa53-107">このトピックでは、それぞれの配置テクノロジの概要と使用法を、それぞれの WPF アプリケーションの種類の配置要件に関連して説明します。</span><span class="sxs-lookup"><span data-stu-id="5aa53-107">This topic provides a brief overview of each deployment technology, and how they are used in conjunction with the deployment requirements of each WPF application type.</span></span>

<a name="Deployment_Technologies"></a>
## <a name="deployment-technologies"></a><span data-ttu-id="5aa53-108">配置テクノロジ</span><span class="sxs-lookup"><span data-stu-id="5aa53-108">Deployment Technologies</span></span>  
 <span data-ttu-id="5aa53-109">Windows および .NET Framework には、次のような、いくつかの配置テクノロジがあります。</span><span class="sxs-lookup"><span data-stu-id="5aa53-109">Windows and the .NET Framework include several deployment technologies, including:</span></span>  
  
- <span data-ttu-id="5aa53-110">XCopy による配置。</span><span class="sxs-lookup"><span data-stu-id="5aa53-110">XCopy deployment.</span></span>  
  
- <span data-ttu-id="5aa53-111">Windows インストーラーの配置。</span><span class="sxs-lookup"><span data-stu-id="5aa53-111">Windows Installer deployment.</span></span>  
  
- <span data-ttu-id="5aa53-112">ClickOnce 配置。</span><span class="sxs-lookup"><span data-stu-id="5aa53-112">ClickOnce deployment.</span></span>  
  
<a name="XCopy_Deployment"></a>
### <a name="xcopy-deployment"></a><span data-ttu-id="5aa53-113">XCopy による配置</span><span class="sxs-lookup"><span data-stu-id="5aa53-113">XCopy Deployment</span></span>  
 <span data-ttu-id="5aa53-114">XCopy による配置とは、XCopy コマンド ライン プログラムを使用して、ある場所から別の場所へファイルをコピーすることです。</span><span class="sxs-lookup"><span data-stu-id="5aa53-114">XCopy deployment refers to the use of the XCopy command-line program to copy files from one location to another.</span></span> <span data-ttu-id="5aa53-115">XCopy による配置は、次のような状況に適しています。</span><span class="sxs-lookup"><span data-stu-id="5aa53-115">XCopy deployment is suitable under the following circumstances:</span></span>  
  
- <span data-ttu-id="5aa53-116">アプリケーションは自己完結型である。</span><span class="sxs-lookup"><span data-stu-id="5aa53-116">The application is self-contained.</span></span> <span data-ttu-id="5aa53-117">実行するためにクライアントを更新する必要がない。</span><span class="sxs-lookup"><span data-stu-id="5aa53-117">It does not need to update the client to run.</span></span>  
  
- <span data-ttu-id="5aa53-118">アプリケーション ファイルをある場所から別の場所へ、たとえば、ビルド場所 (ローカル ディスク、UNC ファイル共有など) から公開場所 (Web サイト、UNC ファイル共有など) へ移動する必要がある。</span><span class="sxs-lookup"><span data-stu-id="5aa53-118">Application files must be moved from one location to another, such as from a build location (local disk, UNC file share, and so on) to a publish location (Web site, UNC file share, and so on).</span></span>  
  
- <span data-ttu-id="5aa53-119">アプリケーションはシェル統合 ([スタート] メニューのショートカット、デスクトップ アイコンなど) を必要としない。</span><span class="sxs-lookup"><span data-stu-id="5aa53-119">The application does not require shell integration (Start menu shortcut, desktop icon, and so on).</span></span>  
  
 <span data-ttu-id="5aa53-120">XCopy は、単純な配置シナリオには適していますが、複雑な配置機能が必要なシナリオには十分に対応できません。</span><span class="sxs-lookup"><span data-stu-id="5aa53-120">Although XCopy is suitable for simple deployment scenarios, it is limited when more complex deployment capabilities are required.</span></span> <span data-ttu-id="5aa53-121">特に、配置を堅牢な方法で管理する場合、XCopy を使用すると、スクリプトの作成、実行、および維持というオーバーヘッドが生じます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-121">In particular, using XCopy often incurs the overhead for creating, executing, and maintaining scripts for managing deployment in a robust way.</span></span> <span data-ttu-id="5aa53-122">さらに、XCopy は、バージョン管理、アンインストール、およびロールバックをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="5aa53-122">Furthermore, XCopy does not support versioning, uninstallation, or rollback.</span></span>  
  
<a name="Windows_Installer"></a>
### <a name="windows-installer"></a><span data-ttu-id="5aa53-123">Windows インストーラー</span><span class="sxs-lookup"><span data-stu-id="5aa53-123">Windows Installer</span></span>  
 <span data-ttu-id="5aa53-124">Windows インストーラーを使用すると、アプリケーションを自己完結型の実行可能ファイルとしてパッケージ化でき、容易にクライアントに配布して、実行できます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-124">Windows Installer allows applications to be packaged as self-contained executables that can be easily distributed to clients and run.</span></span> <span data-ttu-id="5aa53-125">さらに、Windows インストーラーは Windows と共にインストールされるため、デスクトップ、[スタート] メニュー、および [プログラム] コントロール パネルとの統合が可能です。</span><span class="sxs-lookup"><span data-stu-id="5aa53-125">Furthermore, Windows Installer is installed with Windows and enables integration with the desktop, the Start menu, and the Programs control panel.</span></span>  
  
 <span data-ttu-id="5aa53-126">Windows インストーラーでは、アプリケーションのインストールとアンインストールが単純化されますが、インストールされたアプリケーションをバージョン管理の観点から最新に保つ機能は提供されません。</span><span class="sxs-lookup"><span data-stu-id="5aa53-126">Windows Installer simplifies the installation and uninstallation of applications, but it does not provide facilities for ensuring that installed applications are kept up-to-date from a versioning standpoint.</span></span>  
  
 <span data-ttu-id="5aa53-127">Windows インストーラーの詳細については、「[Windows インストーラー配置](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5aa53-127">For more information about Windows Installer, see [Windows Installer Deployment](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span></span>
  
<a name="ClickOnce_Deployment"></a>
### <a name="clickonce-deployment"></a><span data-ttu-id="5aa53-128">ClickOnce 配置</span><span class="sxs-lookup"><span data-stu-id="5aa53-128">ClickOnce Deployment</span></span>  
 <span data-ttu-id="5aa53-129">ClickOnce を使用すると、非 Web アプリケーションを Web スタイル アプリケーションと同じように配置できます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-129">ClickOnce enables Web-style application deployment for non-Web applications.</span></span> <span data-ttu-id="5aa53-130">アプリケーションは、Web サーバーまたはファイル サーバーに公開され、これらのサーバーから配置されます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-130">Applications are published to and deployed from Web or file servers.</span></span> <span data-ttu-id="5aa53-131">ClickOnce では、Windows インストーラーによってインストールされるアプリケーションでサポートされるような広い範囲のクライアント機能がサポートされるわけではありませんが、次のような機能がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-131">Although ClickOnce does not support the full range of client features that Windows Installer-installed applications do, it does support a subset that includes the following:</span></span>  
  
- <span data-ttu-id="5aa53-132">[スタート] メニューおよび [プログラム] コントロール パネルとの統合。</span><span class="sxs-lookup"><span data-stu-id="5aa53-132">Integration with the Start menu and Programs control panel.</span></span>  
  
- <span data-ttu-id="5aa53-133">バージョン管理、ロールバック、およびアンインストール。</span><span class="sxs-lookup"><span data-stu-id="5aa53-133">Versioning, rollback, and uninstallation.</span></span>  
  
- <span data-ttu-id="5aa53-134">アプリケーションを常に配置場所から起動するオンライン インストール モード。</span><span class="sxs-lookup"><span data-stu-id="5aa53-134">Online install mode, which always launches an application from the deployment location.</span></span>  
  
- <span data-ttu-id="5aa53-135">新しいバージョンがリリースされたときの自動更新。</span><span class="sxs-lookup"><span data-stu-id="5aa53-135">Automatic updating when new versions are released.</span></span>  
  
- <span data-ttu-id="5aa53-136">ファイル拡張子の登録。</span><span class="sxs-lookup"><span data-stu-id="5aa53-136">Registration of file extensions.</span></span>  
  
 <span data-ttu-id="5aa53-137">ClickOnce の詳細については、「[ClickOnce のセキュリティと配置](/visualstudio/deployment/clickonce-security-and-deployment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5aa53-137">For more information about ClickOnce, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
<a name="Deploying_WPF_Applications"></a>
## <a name="deploying-wpf-applications"></a><span data-ttu-id="5aa53-138">WPF アプリケーションの配置</span><span class="sxs-lookup"><span data-stu-id="5aa53-138">Deploying WPF Applications</span></span>  
 <span data-ttu-id="5aa53-139">WPF アプリケーションの配置オプションは、アプリケーションの種類によって決まります。</span><span class="sxs-lookup"><span data-stu-id="5aa53-139">The deployment options for a WPF application depend on the type of application.</span></span> <span data-ttu-id="5aa53-140">配置の観点から見ると、WPF には次の 3 種類のアプリケーションがあります。</span><span class="sxs-lookup"><span data-stu-id="5aa53-140">From a deployment perspective, WPF has three significant application types:</span></span>  
  
- <span data-ttu-id="5aa53-141">スタンドアロン アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="5aa53-141">Standalone applications.</span></span>  
  
- <span data-ttu-id="5aa53-142">マークアップのみの [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="5aa53-142">Markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] applications.</span></span>  
  
- <span data-ttu-id="5aa53-143">XAML ブラウザー アプリケーション (XBAP)。</span><span class="sxs-lookup"><span data-stu-id="5aa53-143">XAML browser applications (XBAPs).</span></span>  
  
<a name="Deploying_Standalone_Applications"></a>
### <a name="deploying-standalone-applications"></a><span data-ttu-id="5aa53-144">スタンドアロン アプリケーションの配置</span><span class="sxs-lookup"><span data-stu-id="5aa53-144">Deploying Standalone Applications</span></span>  
 <span data-ttu-id="5aa53-145">スタンドアロン アプリケーションは、ClickOnce または Windows インストーラーを使用して配置されます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-145">Standalone applications are deployed using either ClickOnce or Windows Installer.</span></span> <span data-ttu-id="5aa53-146">いずれの場合も、スタンドアロン アプリケーションを実行するには、アプリケーションが完全に信頼されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aa53-146">Either way, standalone applications require full trust to run.</span></span> <span data-ttu-id="5aa53-147">Windows インストーラーを使用して配置されたスタンドアロン アプリケーションには、完全な信頼が自動的に付与されます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-147">Full trust is automatically granted to standalone applications that are deployed using Windows Installer.</span></span> <span data-ttu-id="5aa53-148">ClickOnce を使用して配置されたスタンドアロン アプリケーションには、完全な信頼は自動的に付与されません。</span><span class="sxs-lookup"><span data-stu-id="5aa53-148">Standalone applications that are deployed using ClickOnce are not automatically granted full trust.</span></span> <span data-ttu-id="5aa53-149">代わりに、スタンドアロン アプリケーションをインストールする前に、ClickOnce によって [セキュリティ警告] ダイアログが表示され、ユーザーがそれを受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aa53-149">Instead, ClickOnce displays a security warning dialog that users must accept before a standalone application is installed.</span></span> <span data-ttu-id="5aa53-150">受け入れた場合、スタンドアロン アプリケーションがインストールされ、完全な信頼が付与されます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-150">If accepted, the standalone application is installed and granted full trust.</span></span> <span data-ttu-id="5aa53-151">受け入れなかった場合、スタンドアロン アプリケーションはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="5aa53-151">If not, the standalone application is not installed.</span></span>  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>
### <a name="deploying-markup-only-xaml-applications"></a><span data-ttu-id="5aa53-152">マークアップのみの XAML アプリケーションの配置</span><span class="sxs-lookup"><span data-stu-id="5aa53-152">Deploying Markup-Only XAML Applications</span></span>  
 <span data-ttu-id="5aa53-153">マークアップのみの [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ページは、通常、HTML ページと同様に Web サーバーに公開され、Internet Explorer を使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-153">Markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages are usually published to Web servers, like HTML pages, and can be viewed using Internet Explorer.</span></span> <span data-ttu-id="5aa53-154">マークアップのみの [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ページは、部分信頼セキュリティ サンドボックス内で実行され、インターネット ゾーン アクセス許可セットによって定義された制約が適用されます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-154">Markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages run within a partial-trust security sandbox with restrictions that are defined by the Internet zone permission set.</span></span> <span data-ttu-id="5aa53-155">これにより、HTML ベースの Web アプリケーションと同等のセキュリティ サンドボックスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-155">This provides an equivalent security sandbox to HTML-based Web applications.</span></span>  
  
 <span data-ttu-id="5aa53-156">WPF アプリケーションのセキュリティの詳細については、「[セキュリティ](../security-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5aa53-156">For more information about security for WPF applications, see [Security](../security-wpf.md).</span></span>  
  
 <span data-ttu-id="5aa53-157">マークアップのみの [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ページは、XCopy または Windows インストーラーを使用してローカル ファイル システムにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-157">Markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages can be installed to the local file system by using either XCopy or Windows Installer.</span></span> <span data-ttu-id="5aa53-158">これらのページは、Internet Explorer または Windows エクスプローラーを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-158">These pages can be viewed using Internet Explorer or Windows Explorer.</span></span>  
  
 <span data-ttu-id="5aa53-159">XAML の詳細については、「[XAML の概要 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5aa53-159">For more information about XAML, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md).</span></span>  
  
<a name="Deploying_XAML_Browser_Applications"></a>
### <a name="deploying-xaml-browser-applications"></a><span data-ttu-id="5aa53-160">XAML ブラウザー アプリケーションの配置</span><span class="sxs-lookup"><span data-stu-id="5aa53-160">Deploying XAML Browser Applications</span></span>  
 <span data-ttu-id="5aa53-161">XBAP は、次の 3 つのファイルを配置する必要があるコンパイル済みのアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="5aa53-161">XBAPs are compiled applications that require the following three files to be deployed:</span></span>  
  
- <span data-ttu-id="5aa53-162">*ApplicationName*.exe:実行可能アセンブリのアプリケーション ファイル。</span><span class="sxs-lookup"><span data-stu-id="5aa53-162">*ApplicationName*.exe: The executable assembly application file.</span></span>  
  
- <span data-ttu-id="5aa53-163">*ApplicationName*.xbap:配置マニフェスト。</span><span class="sxs-lookup"><span data-stu-id="5aa53-163">*ApplicationName*.xbap: The deployment manifest.</span></span>  
  
- <span data-ttu-id="5aa53-164">*ApplicationName*.exe.manifest:アプリケーション マニフェスト。</span><span class="sxs-lookup"><span data-stu-id="5aa53-164">*ApplicationName*.exe.manifest: The application manifest.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5aa53-165">配置マニフェストおよびアプリケーション マニフェストの詳細については、「[WPF アプリケーションのビルド](building-a-wpf-application-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5aa53-165">For more information about deployment and application manifests, see [Building a WPF Application](building-a-wpf-application-wpf.md).</span></span>  
  
 <span data-ttu-id="5aa53-166">これらのファイルは、XBAP がビルドされるときに生成されます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-166">These files are produced when an XBAP is built.</span></span> <span data-ttu-id="5aa53-167">詳細については、「[方法:新しい WPF ブラウザー アプリケーション プロジェクトを作成する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5aa53-167">For more information, see [How to: Create a New WPF Browser Application Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100)).</span></span> <span data-ttu-id="5aa53-168">マークアップのみの [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ページと同様に、XBAP は、通常、Web サーバーに発行され、Internet Explorer を使用して表示されます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-168">Like markup-only [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pages, XBAPs are typically published to a Web server and viewed using Internet Explorer.</span></span>  
  
 <span data-ttu-id="5aa53-169">XBAP は、任意の配置技術を使用してクライアントに配置できます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-169">XBAPs can be deployed to clients using any of the deployment techniques.</span></span> <span data-ttu-id="5aa53-170">ただし、次の機能を備えている ClickOnce をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5aa53-170">However, ClickOnce is recommended since it provides the following capabilities:</span></span>  
  
1. <span data-ttu-id="5aa53-171">新しいバージョンが公開されたときの自動更新。</span><span class="sxs-lookup"><span data-stu-id="5aa53-171">Automatic updates when a new version is published.</span></span>  
  
2. <span data-ttu-id="5aa53-172">完全な信頼で実行する XBAP の特権の昇格。</span><span class="sxs-lookup"><span data-stu-id="5aa53-172">Elevation privileges for the XBAP running with full trust.</span></span>  
  
 <span data-ttu-id="5aa53-173">既定では、ClickOnce は、.deploy 拡張子を持つアプリケーション ファイルを公開します。</span><span class="sxs-lookup"><span data-stu-id="5aa53-173">By default, ClickOnce publishes application files with the .deploy extension.</span></span> <span data-ttu-id="5aa53-174">これは問題になる可能性がありますが、無効にできます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-174">This can be problematic, but can be disabled.</span></span> <span data-ttu-id="5aa53-175">詳細については、「[ClickOnce 配置でのサーバーおよびクライアント構成の問題](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5aa53-175">For more information, see [Server and Client Configuration Issues in ClickOnce Deployments](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments).</span></span>  
  
 <span data-ttu-id="5aa53-176">XAML ブラウザー アプリケーション (XBAP) の配置の詳細については、「[WPF XAML ブラウザー アプリケーションの概要](wpf-xaml-browser-applications-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5aa53-176">For more information about deploying XAML browser applications (XBAPs), see [WPF XAML Browser Applications Overview](wpf-xaml-browser-applications-overview.md).</span></span>  
  
<a name="Installing__NET_Framework_3_0"></a>
## <a name="installing-the-net-framework"></a><span data-ttu-id="5aa53-177">.NET Framework のインストール</span><span class="sxs-lookup"><span data-stu-id="5aa53-177">Installing the .NET Framework</span></span>  
 <span data-ttu-id="5aa53-178">WPF アプリケーションを実行するには、クライアントに Microsoft .NET Framework がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aa53-178">To run a WPF application, the Microsoft .NET Framework must be installed on the client.</span></span> <span data-ttu-id="5aa53-179">Internet Explorer では、ブラウザーでホストされる WPF アプリケーションが表示されるとき、クライアントに .NET Framework がインストールされているかどうかが自動的に検出されます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-179">Internet Explorer automatically detects whether clients are installed with .NET Framework when WPF browser-hosted applications are viewed.</span></span> <span data-ttu-id="5aa53-180">.NET Framework がインストールされていない場合は、Internet Explorer によってユーザーにインストールが求められます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-180">If the .NET Framework is not installed, Internet Explorer prompts users to install it.</span></span>  
  
 <span data-ttu-id="5aa53-181">.NET Framework がインストールされているかどうかを検出するために、Internet Explorer には、.xaml、.xps、および .application の拡張子を持つコンテンツ ファイルのフォールバック Multipurpose Internet Mail Extensions (MIME) ハンドラーとして登録されているブートストラップ アプリケーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5aa53-181">To detect whether the .NET Framework is installed, Internet Explorer includes a bootstrapper application that is registered as the fallback Multipurpose Internet Mail Extensions (MIME) handler for content files with the following extensions: .xaml, .xps, .xbap, and .application.</span></span> <span data-ttu-id="5aa53-182">これらのファイルの種類に移動するとき、.NET Framework がクライアントにインストールされていなかった場合、ブートス トラップ アプリケーションによってインストールの許可を求められます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-182">If you navigate to these file types and the .NET Framework is not installed on the client, the bootstrapper application requests permission to install it.</span></span> <span data-ttu-id="5aa53-183">許可が与えられなかった場合は、.NET Framework もアプリケーションもインストールされません。</span><span class="sxs-lookup"><span data-stu-id="5aa53-183">If permission is not provided, neither the .NET Framework nor the application is installed.</span></span>  
  
 <span data-ttu-id="5aa53-184">許可が与えられた場合、Internet Explorer では Microsoft バックグラウンド インテリジェント転送サービス (BITS) を使用して .NET Framework がダウンロードされ、インストールされます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-184">If permission is granted, Internet Explorer downloads and installs the .NET Framework using the Microsoft Background Intelligent Transfer Service (BITS).</span></span> <span data-ttu-id="5aa53-185">.NET Framework が正常にインストールされた後、最初に要求されたファイルが新しいブラウザー ウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="5aa53-185">After successful installation of the .NET Framework, the originally requested file is opened in a new browser window.</span></span>  
  
 <span data-ttu-id="5aa53-186">詳細については、「[.NET Framework およびアプリケーションの配置](../../deployment/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5aa53-186">For more information, see [Deploying the .NET Framework and Applications](../../deployment/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aa53-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="5aa53-187">See also</span></span>

- [<span data-ttu-id="5aa53-188">WPF アプリケーションのビルド</span><span class="sxs-lookup"><span data-stu-id="5aa53-188">Building a WPF Application</span></span>](building-a-wpf-application-wpf.md)
- [<span data-ttu-id="5aa53-189">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="5aa53-189">Security</span></span>](../security-wpf.md)
