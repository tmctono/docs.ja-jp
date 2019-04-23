---
title: '方法: Visual Studio を構成して Web サービスを呼び出す XAML ブラウザー アプリケーションをデバッグする'
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: dcaabf9ecd47bc88095e92aa8ed28ad5f13fd1dc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314374"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="a5d5f-102">方法: Visual Studio を構成して Web サービスを呼び出す XAML ブラウザー アプリケーションをデバッグする</span><span class="sxs-lookup"><span data-stu-id="a5d5f-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] <span data-ttu-id="a5d5f-103">インターネット ゾーン アクセス許可のセットに制限されている部分信頼セキュリティ サンド ボックス内で実行します。</span><span class="sxs-lookup"><span data-stu-id="a5d5f-103">run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="a5d5f-104">このアクセス許可セットのみであるサービスを Web に Web サービス呼び出しを制限する、[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]アプリケーションの起点サイト。</span><span class="sxs-lookup"><span data-stu-id="a5d5f-104">This permission set restricts Web service calls to only Web services that are located at the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] application's site of origin.</span></span> <span data-ttu-id="a5d5f-105">ときに、[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]は、デバッグ、Visual Studio 2005 とは見なされません起点のサイトと同じように、Web サービスが参照にします。</span><span class="sxs-lookup"><span data-stu-id="a5d5f-105">When an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] is debugged from Visual Studio 2005, though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="a5d5f-106">ときに発生します。 このエラーの原因のセキュリティ例外、 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] Web サービスを呼び出すしようとしています。</span><span class="sxs-lookup"><span data-stu-id="a5d5f-106">This causes security exceptions to be raised when the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] attempts to call the Web service.</span></span> <span data-ttu-id="a5d5f-107">ただし、Visual Studio 2005[!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)]プロジェクトは、デバッグ中に呼び出す Web サービスと同じサイトの配信元をシミュレートするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="a5d5f-107">However, a Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="a5d5f-108">これにより、[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]を安全にセキュリティ例外を発生させることがなく、Web サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a5d5f-108">This allows the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] to safely call the Web service without causing security exceptions.</span></span>

## <a name="configuring-visual-studio"></a><span data-ttu-id="a5d5f-109">Visual Studio の構成</span><span class="sxs-lookup"><span data-stu-id="a5d5f-109">Configuring Visual Studio</span></span>
 <span data-ttu-id="a5d5f-110">デバッグを Visual Studio 2005 を構成する、 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] Web サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a5d5f-110">To configure Visual Studio 2005 to debug an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that calls a Web service:</span></span>

1. <span data-ttu-id="a5d5f-111">**ソリューション エクスプ ローラー**でプロジェクトを選択し、 **[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5d5f-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="a5d5f-112">**プロジェクト デザイナー**、クリックして、**デバッグ**タブ。</span><span class="sxs-lookup"><span data-stu-id="a5d5f-112">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="a5d5f-113">**開始動作**セクションで、**外部プログラムの開始**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="a5d5f-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>

     `C:\WINDOWS\System32\PresentationHost.exe`

4. <span data-ttu-id="a5d5f-114">**開始オプション**セクションで、次の点を入力してください、**コマンドライン引数**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="a5d5f-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>

     <span data-ttu-id="a5d5f-115">`-debug`  *filename*</span><span class="sxs-lookup"><span data-stu-id="a5d5f-115">`-debug`  *filename*</span></span>

     <span data-ttu-id="a5d5f-116">*ファイル名*の値、 **-デバッグ**パラメーターが .xbap ファイル名。 例。</span><span class="sxs-lookup"><span data-stu-id="a5d5f-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>

     `-debug c:\example.xbap`

> [!NOTE]
>  <span data-ttu-id="a5d5f-117">これは、Visual Studio 2005 で作成したソリューションの既定の構成は、[!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)]プロジェクト テンプレート。</span><span class="sxs-lookup"><span data-stu-id="a5d5f-117">This is the default configuration for solutions that are created with the Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project template.</span></span>

1. <span data-ttu-id="a5d5f-118">**ソリューション エクスプ ローラー**でプロジェクトを選択し、 **[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5d5f-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="a5d5f-119">**プロジェクト デザイナー**、クリックして、**デバッグ**タブ。</span><span class="sxs-lookup"><span data-stu-id="a5d5f-119">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="a5d5f-120">**開始オプション**セクションで、次のコマンド ライン パラメーターを追加、**コマンドライン引数**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="a5d5f-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>

     <span data-ttu-id="a5d5f-121">`-debugSecurityZoneURL`  *URL*</span><span class="sxs-lookup"><span data-stu-id="a5d5f-121">`-debugSecurityZoneURL`  *URL*</span></span>

     <span data-ttu-id="a5d5f-122">*URL*値、 **- debugSecurityZoneURL**パラメーターは、[!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)]の場所として、アプリケーションの起点のサイトをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="a5d5f-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] for the location that you want to simulate as being the site of origin of your application.</span></span>

 <span data-ttu-id="a5d5f-123">たとえばを検討してください、[!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]に次の Web サービスを使用する[!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a5d5f-123">As an example, consider a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that uses a Web service with the following [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span></span>

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 <span data-ttu-id="a5d5f-124">起点サイト[!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]この Web サービスは。</span><span class="sxs-lookup"><span data-stu-id="a5d5f-124">The site of origin [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] for this Web service is:</span></span>

 `http://services.msdn.microsoft.com`

 <span data-ttu-id="a5d5f-125">その結果、完全な **- debugSecurityZoneURL**コマンド ライン パラメーターと値には。</span><span class="sxs-lookup"><span data-stu-id="a5d5f-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a><span data-ttu-id="a5d5f-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5d5f-126">See also</span></span>

- [<span data-ttu-id="a5d5f-127">WPF ホスト (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="a5d5f-127">WPF Host (PresentationHost.exe)</span></span>](wpf-host-presentationhost-exe.md)
