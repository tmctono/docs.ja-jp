---
title: WCF 開発ツールの使用
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 27cefb1ca1f4748f0d074ffdcd47cd6faa29da00
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320271"
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="a0354-102">WCF 開発ツールの使用</span><span class="sxs-lookup"><span data-stu-id="a0354-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="a0354-103">このセクションでは、WCFservice の開発に役立つ Visual Studio 開発ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a0354-103">This section describes the Visual Studio development tools that can assist you in developing your WCFservice.</span></span>  
  
 <span data-ttu-id="a0354-104">Visual Studio テンプレートを基礎として使用して、独自のサービスをすばやく構築し、WCF サービスの自動ホストと WCF テストクライアントを使用してサービスをデバッグおよびテストできます。</span><span class="sxs-lookup"><span data-stu-id="a0354-104">You can use the Visual Studio templates as a foundation to quickly build your own service, then use WCF Service Auto Host and WCF Test Client to debug and test your service.</span></span> <span data-ttu-id="a0354-105">これらのツールによって、高速でシームレスなデバッグとテストのサイクルが実現し、初期の段階でホスト モデルにコミットする必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="a0354-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  
 
 > [!NOTE]
 > <span data-ttu-id="a0354-106">Visual Studio 2017 以降では、WCF 開発ツールは既定でインストールされません。</span><span class="sxs-lookup"><span data-stu-id="a0354-106">Starting with Visual Studio 2017, the WCF development tools are not installed by default.</span></span> <span data-ttu-id="a0354-107">これらの機能を使用するには、Visual Studio インストーラーで Windows Communication Foundation コンポーネントが選択されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0354-107">In order to use these features, you must ensure the Windows Communication Foundation component is selected in the Visual Studio installer.</span></span>
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="a0354-108">WCF の開発者用ツール</span><span class="sxs-lookup"><span data-stu-id="a0354-108">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="a0354-109">WCF Visual Studio テンプレート</span><span class="sxs-lookup"><span data-stu-id="a0354-109">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)  
  
 <span data-ttu-id="a0354-110">Visual Studio の事前定義された Visual Studio プロジェクトと項目テンプレートを使用して、WCF サービスとその周辺アプリケーションをすばやく構築できます。</span><span class="sxs-lookup"><span data-stu-id="a0354-110">You can use the predefined Visual Studio project and item templates in Visual Studio to quickly build WCF services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="a0354-111">WCF サービス ホスト (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="a0354-111">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="a0354-112">WCF サービスの自動ホスト (Wcfsvchost.exe) を使用すると、Visual Studio デバッガー (F5) を起動して、実装したサービスを自動的にホストおよびテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="a0354-112">The WCF Service Auto Host (WcfSvcHost.exe) allows you to launch the Visual Studio debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="a0354-113">その後、WCF テストクライアント (Wcftestclient.exe) または独自のクライアントを使用してサービスをテストし、潜在的なエラーを見つけて修正することができます。</span><span class="sxs-lookup"><span data-stu-id="a0354-113">You can then test the service using the WCF Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="a0354-114">WCF のテスト用クライアント (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="a0354-114">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)  
  
 <span data-ttu-id="a0354-115">WCF テストクライアント (Wcftestclient.exe) は、任意の型のパラメーターを入力し、その入力をサービスに送信し、サービスから返される応答を表示するための GUI ツールです。</span><span class="sxs-lookup"><span data-stu-id="a0354-115">WCF Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="a0354-116">WCF サービスの自動ホストと組み合わせると、シームレスなサービステストエクスペリエンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="a0354-116">It provides a seamless service testing experience when combined with WCF Service Auto Host.</span></span>  
  
 [<span data-ttu-id="a0354-117">XML からのデータ型クラスの生成</span><span class="sxs-lookup"><span data-stu-id="a0354-117">Generating Data Type Classes from XML</span></span>](generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="a0354-118">クリップボードに格納されている XML データは、コード ページに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="a0354-118">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="a0354-119">データで定義されているクラスは、コード型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="a0354-119">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="a0354-120">管理特権を必要としないツールの使用</span><span class="sxs-lookup"><span data-stu-id="a0354-120">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="a0354-121">管理者特権を持たないユーザーが WCF サービスを開発できるようにするには、Visual Studio のインストール時に、名前空間 "http://+:8731/Design_Time_Addresses" に対して ACL (Access Control リスト) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a0354-121">To enable users without administrator privilege to develop WCF services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of Visual Studio.</span></span> <span data-ttu-id="a0354-122">この ACL は (UI) に設定され、コンピューターにログオンしているすべての対話ユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a0354-122">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="a0354-123">管理者は、この ACL にユーザーを追加または削除したり、追加のポートを開いたりできます。この ACL によって、既定の構成で、WCF テンプレートまたは WF テンプレートでデータを送受信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a0354-123">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="a0354-124">また、ユーザーは、管理者特権を付与せずに、WCF サービスの自動ホスト (Wcfsvchost.exe) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a0354-124">It also enables users to use the WCF Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="a0354-125">システム特権のある管理者アカウントで [!INCLUDE[wv](../../../includes/wv-md.md)] の Netsh.exe ツールを使用すると、アクセスを変更できます。</span><span class="sxs-lookup"><span data-stu-id="a0354-125">You can modify access using the Netsh.exe tool in [!INCLUDE[wv](../../../includes/wv-md.md)] under the elevated administrator account.</span></span> <span data-ttu-id="a0354-126">Netsh.exe の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a0354-126">The following is an example of using Netsh.exe.</span></span>  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 <span data-ttu-id="a0354-127">Netsh.exe の詳細については、「 [Netsh.exe ツールとコマンドラインスイッチの使用方法](https://go.microsoft.com/fwlink/?LinkId=97877)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0354-127">For more information about Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](https://go.microsoft.com/fwlink/?LinkId=97877).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0354-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0354-128">See also</span></span>

- [<span data-ttu-id="a0354-129">WCF Visual Studio テンプレート</span><span class="sxs-lookup"><span data-stu-id="a0354-129">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)
- [<span data-ttu-id="a0354-130">WCF サービス ホスト (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="a0354-130">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)
- [<span data-ttu-id="a0354-131">WCF のテスト用クライアント (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="a0354-131">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)
