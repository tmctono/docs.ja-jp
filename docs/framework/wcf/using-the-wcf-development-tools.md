---
title: WCF 開発ツールの使用
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: e9a398ac6914582d299658e3e45d17ea5468917d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712091"
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="e9cc4-102">WCF 開発ツールの使用</span><span class="sxs-lookup"><span data-stu-id="e9cc4-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="e9cc4-103">このセクションでは、WCFservice の開発に役立つ Visual Studio 開発ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e9cc4-103">This section describes the Visual Studio development tools that can assist you in developing your WCFservice.</span></span>  
  
 <span data-ttu-id="e9cc4-104">基盤として、Visual Studio テンプレートを使用して、独自のサービスを迅速に構築し、WCF サービスの自動ホストと WCF テスト クライアントを使用して、サービスをデバッグおよびテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="e9cc4-104">You can use the Visual Studio templates as a foundation to quickly build your own service, then use WCF Service Auto Host and WCF Test Client to debug and test your service.</span></span> <span data-ttu-id="e9cc4-105">これらのツールによって、高速でシームレスなデバッグとテストのサイクルが実現し、初期の段階においてホスト モデルのコミットが必要なくなります。</span><span class="sxs-lookup"><span data-stu-id="e9cc4-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="e9cc4-106">WCF の開発者用ツール</span><span class="sxs-lookup"><span data-stu-id="e9cc4-106">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="e9cc4-107">WCF Visual Studio テンプレート</span><span class="sxs-lookup"><span data-stu-id="e9cc4-107">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 <span data-ttu-id="e9cc4-108">Visual Studio で、定義済みの Visual Studio プロジェクトと項目テンプレートを使用すると、WCF サービスや周辺アプリケーションを迅速に構築します。</span><span class="sxs-lookup"><span data-stu-id="e9cc4-108">You can use the predefined Visual Studio project and item templates in Visual Studio to quickly build WCF services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="e9cc4-109">WCF サービス ホスト (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="e9cc4-109">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="e9cc4-110">WCF サービスの自動ホスト (WcfSvcHost.exe) を使用すると、自動的にホストし、実装したサービスをテストするには、(F5) Visual Studio デバッガーを起動できます。</span><span class="sxs-lookup"><span data-stu-id="e9cc4-110">The WCF Service Auto Host (WcfSvcHost.exe) allows you to launch the Visual Studio debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="e9cc4-111">WCF テスト クライアント (wcfTestClient.exe) または独自のクライアントを検出して潜在的なエラーを修正するを使用してサービスをテストできます。</span><span class="sxs-lookup"><span data-stu-id="e9cc4-111">You can then test the service using the WCF Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="e9cc4-112">WCF のテスト用クライアント (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="e9cc4-112">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 <span data-ttu-id="e9cc4-113">WCF テスト クライアント (WcfTestClient.exe) は、任意の型のパラメーターを入力し、サービス、およびサービスの応答を送り返しますビューへの入力を送信するための GUI ツールです。</span><span class="sxs-lookup"><span data-stu-id="e9cc4-113">WCF Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="e9cc4-114">テストを行う WCF サービスの自動ホストと組み合わせたときに、シームレスにサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="e9cc4-114">It provides a seamless service testing experience when combined with WCF Service Auto Host.</span></span>  
  
 [<span data-ttu-id="e9cc4-115">XML からのデータ型クラスの生成</span><span class="sxs-lookup"><span data-stu-id="e9cc4-115">Generating Data Type Classes from XML</span></span>](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="e9cc4-116">クリップボードに格納されている XML データは、コード ページに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e9cc4-116">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="e9cc4-117">データで定義されているクラスは、コード型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="e9cc4-117">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="e9cc4-118">管理特権を必要としないツールの使用</span><span class="sxs-lookup"><span data-stu-id="e9cc4-118">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="e9cc4-119">WCF サービスの開発を管理者特権のないユーザーを有効にする ACL (アクセス制御リスト) は、名前空間の作成"http://+:8731/Design_Time_Addresses"Visual Studio のインストール中にします。</span><span class="sxs-lookup"><span data-stu-id="e9cc4-119">To enable users without administrator privilege to develop WCF services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of Visual Studio.</span></span> <span data-ttu-id="e9cc4-120">この ACL は (UI) に設定され、コンピューターにログオンしているすべての対話ユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e9cc4-120">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="e9cc4-121">管理者は、この ACL にユーザーを追加または削除したり、追加のポートを開いたりできます。この ACL によって、既定の構成で、WCF テンプレートまたは WF テンプレートでデータを送受信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e9cc4-121">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="e9cc4-122">また、ユーザーが管理者特権を与えずに WCF サービスの自動ホスト (wcfSvcHost.exe) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e9cc4-122">It also enables users to use the WCF Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="e9cc4-123">システム特権のある管理者アカウントで [!INCLUDE[wv](../../../includes/wv-md.md)] の Netsh.exe ツールを使用すると、アクセスを変更できます。</span><span class="sxs-lookup"><span data-stu-id="e9cc4-123">You can modify access using the Netsh.exe tool in [!INCLUDE[wv](../../../includes/wv-md.md)] under the elevated administrator account.</span></span> <span data-ttu-id="e9cc4-124">Netsh.exe の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e9cc4-124">The following is an example of using Netsh.exe.</span></span>  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 <span data-ttu-id="e9cc4-125">Netsh.exe の詳細については、[Netsh.exe ツールとコマンド ライン スイッチを使用する方法](https://go.microsoft.com/fwlink/?LinkId=97877)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9cc4-125">For more information about Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](https://go.microsoft.com/fwlink/?LinkId=97877).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9cc4-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9cc4-126">See also</span></span>
- [<span data-ttu-id="e9cc4-127">WCF Visual Studio テンプレート</span><span class="sxs-lookup"><span data-stu-id="e9cc4-127">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)
- [<span data-ttu-id="e9cc4-128">WCF サービス ホスト (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="e9cc4-128">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
- [<span data-ttu-id="e9cc4-129">WCF のテスト用クライアント (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="e9cc4-129">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
