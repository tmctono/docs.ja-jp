---
title: '方法 : Visual Studio を構成して Web サービスを呼び出す XAML ブラウザー アプリケーションをデバッグする'
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: 27319179a9a30c5693f47039bf1e24c59adf0e68
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424651"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="70a73-102">方法 : Visual Studio を構成して Web サービスを呼び出す XAML ブラウザー アプリケーションをデバッグする</span><span class="sxs-lookup"><span data-stu-id="70a73-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
<span data-ttu-id="70a73-103">XAML ブラウザーアプリケーション (Xbap) は、インターネットゾーンのアクセス許可セットに制限されている部分信頼セキュリティサンドボックス内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="70a73-103">XAML browser applications (XBAPs) run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="70a73-104">このアクセス許可セットは、Web サービスの呼び出しを、XBAP アプリケーションの起点サイトにある Web サービスのみに制限します。</span><span class="sxs-lookup"><span data-stu-id="70a73-104">This permission set restricts Web service calls to only Web services that are located at the XBAP application's site of origin.</span></span> <span data-ttu-id="70a73-105">ただし、XBAP が Visual Studio 2005 からデバッグされている場合、それが参照している Web サービスと同じ起点サイトであるとは見なされません。</span><span class="sxs-lookup"><span data-stu-id="70a73-105">When an XBAP is debugged from Visual Studio 2005, though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="70a73-106">これにより、XBAP が Web サービスを呼び出そうとすると、セキュリティ例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="70a73-106">This causes security exceptions to be raised when the XBAP attempts to call the Web service.</span></span> <span data-ttu-id="70a73-107">ただし、Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] プロジェクトは、デバッグ中に呼び出し元の Web サービスと同じサイトがあることをシミュレートするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="70a73-107">However, a Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="70a73-108">これにより、XBAP はセキュリティ例外を発生させることなく、Web サービスを安全に呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="70a73-108">This allows the XBAP to safely call the Web service without causing security exceptions.</span></span>

## <a name="configuring-visual-studio"></a><span data-ttu-id="70a73-109">Visual Studio の構成</span><span class="sxs-lookup"><span data-stu-id="70a73-109">Configuring Visual Studio</span></span>
 <span data-ttu-id="70a73-110">Web サービスを呼び出す XBAP をデバッグするように Visual Studio 2005 を構成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="70a73-110">To configure Visual Studio 2005 to debug an XBAP that calls a Web service:</span></span>

1. <span data-ttu-id="70a73-111">**ソリューション エクスプローラー**でプロジェクトを選択し、 **[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70a73-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="70a73-112">**プロジェクトデザイナー**で、 **[デバッグ]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="70a73-112">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="70a73-113">**[開始アクション]** セクションで、 **[外部プログラムの開始]** を選択し、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="70a73-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>

     `C:\WINDOWS\System32\PresentationHost.exe`

4. <span data-ttu-id="70a73-114">**[開始オプション]** セクションで、 **[コマンドライン引数]** ボックスに次の内容を入力します。</span><span class="sxs-lookup"><span data-stu-id="70a73-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>

     <span data-ttu-id="70a73-115">`-debug`  *ファイル名*</span><span class="sxs-lookup"><span data-stu-id="70a73-115">`-debug`  *filename*</span></span>

     <span data-ttu-id="70a73-116">**-Debug**パラメーターの*filename*値は、. xbap ファイル名です。例えば：</span><span class="sxs-lookup"><span data-stu-id="70a73-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>

     `-debug c:\example.xbap`

> [!NOTE]
> <span data-ttu-id="70a73-117">これは、Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] プロジェクトテンプレートを使用して作成されたソリューションの既定の構成です。</span><span class="sxs-lookup"><span data-stu-id="70a73-117">This is the default configuration for solutions that are created with the Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project template.</span></span>

1. <span data-ttu-id="70a73-118">**ソリューション エクスプローラー**でプロジェクトを選択し、 **[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70a73-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="70a73-119">**プロジェクトデザイナー**で、 **[デバッグ]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="70a73-119">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="70a73-120">**[開始オプション]** セクションで、次のコマンドラインパラメーターを **[コマンドライン引数]** テキストボックスに追加します。</span><span class="sxs-lookup"><span data-stu-id="70a73-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>

     <span data-ttu-id="70a73-121">`-debugSecurityZoneURL`  *URL*</span><span class="sxs-lookup"><span data-stu-id="70a73-121">`-debugSecurityZoneURL`  *URL*</span></span>

     <span data-ttu-id="70a73-122">**-Debugsecurityゾーン url**パラメーターの*url*値は、アプリケーションの元のサイトとしてシミュレートする場所の url ですが、</span><span class="sxs-lookup"><span data-stu-id="70a73-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the URL for the location that you want to simulate as being the site of origin of your application.</span></span>

 <span data-ttu-id="70a73-123">例として、次の URL の Web サービスを使用する XAML ブラウザーアプリケーション (XBAP) を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="70a73-123">As an example, consider a XAML browser application (XBAP) that uses a Web service with the following URL:</span></span>

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 <span data-ttu-id="70a73-124">この Web サービスの起点サイト URL は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="70a73-124">The site of origin URL for this Web service is:</span></span>

 `http://services.msdn.microsoft.com`

 <span data-ttu-id="70a73-125">その結果、完全な**debugsecurityゾーン url**コマンドラインパラメーターと値は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="70a73-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a><span data-ttu-id="70a73-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="70a73-126">See also</span></span>

- [<span data-ttu-id="70a73-127">WPF ホスト (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="70a73-127">WPF Host (PresentationHost.exe)</span></span>](wpf-host-presentationhost-exe.md)
