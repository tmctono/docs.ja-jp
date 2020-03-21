---
title: WCF 開発ツールの使用
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 82bb7e225492bcdba4d2e611de405a09571355c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183077"
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="2d773-102">WCF 開発ツールの使用</span><span class="sxs-lookup"><span data-stu-id="2d773-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="2d773-103">このセクションでは、WCF サービスの開発に役立つ Visual Studio 開発ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2d773-103">This section describes the Visual Studio development tools that can assist you in developing your WCFservice.</span></span>  
  
 <span data-ttu-id="2d773-104">Visual Studio テンプレートを基盤として使用して、独自のサービスをすばやく構築し、WCF サービスの自動ホストと WCF テスト クライアントを使用してサービスをデバッグおよびテストできます。</span><span class="sxs-lookup"><span data-stu-id="2d773-104">You can use the Visual Studio templates as a foundation to quickly build your own service, then use WCF Service Auto Host and WCF Test Client to debug and test your service.</span></span> <span data-ttu-id="2d773-105">これらのツールによって、高速でシームレスなデバッグとテストのサイクルが実現し、初期の段階でホスト モデルにコミットする必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="2d773-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  

 > [!NOTE]
 > <span data-ttu-id="2d773-106">Visual Studio 2017 以降では、WCF 開発ツールは既定ではインストールされません。</span><span class="sxs-lookup"><span data-stu-id="2d773-106">Starting with Visual Studio 2017, the WCF development tools are not installed by default.</span></span> <span data-ttu-id="2d773-107">これらの機能を使用するには、Visual Studio インストーラーで Windows コミュニケーションファウンデーション コンポーネントが選択されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d773-107">In order to use these features, you must ensure the Windows Communication Foundation component is selected in the Visual Studio installer.</span></span>
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="2d773-108">WCF の開発者用ツール</span><span class="sxs-lookup"><span data-stu-id="2d773-108">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="2d773-109">WCF Visual Studio テンプレート</span><span class="sxs-lookup"><span data-stu-id="2d773-109">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)  
  
 <span data-ttu-id="2d773-110">定義済みの Visual Studio プロジェクトテンプレートと項目テンプレートを使用して、WCF サービスと周辺アプリケーションをすばやく構築できます。</span><span class="sxs-lookup"><span data-stu-id="2d773-110">You can use the predefined Visual Studio project and item templates in Visual Studio to quickly build WCF services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="2d773-111">WCF サービス ホスト (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="2d773-111">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="2d773-112">WCF サービスの自動ホスト (WcfSvcHost.exe) を使用すると、Visual Studio デバッガー (F5) を起動して、実装したサービスを自動的にホストおよびテストできます。</span><span class="sxs-lookup"><span data-stu-id="2d773-112">The WCF Service Auto Host (WcfSvcHost.exe) allows you to launch the Visual Studio debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="2d773-113">その後、WCF テスト クライアント (wcfTestClient.exe) または独自のクライアントを使用してサービスをテストし、潜在的なエラーを見つけて修正できます。</span><span class="sxs-lookup"><span data-stu-id="2d773-113">You can then test the service using the WCF Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="2d773-114">WCF のテスト用クライアント (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="2d773-114">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)  
  
 <span data-ttu-id="2d773-115">WCF テスト クライアント (WcfTestClient.exe) は、任意の型のパラメーターを入力し、その入力をサービスに送信し、サービスが返送する応答を表示できるようにする GUI ツールです。</span><span class="sxs-lookup"><span data-stu-id="2d773-115">WCF Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="2d773-116">WCF サービスの自動ホストと組み合わせた場合、シームレスなサービス テスト エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="2d773-116">It provides a seamless service testing experience when combined with WCF Service Auto Host.</span></span>  
  
 [<span data-ttu-id="2d773-117">XML からのデータ型クラスの生成</span><span class="sxs-lookup"><span data-stu-id="2d773-117">Generating Data Type Classes from XML</span></span>](generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="2d773-118">クリップボードに格納されている XML データは、コード ページに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="2d773-118">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="2d773-119">データで定義されているクラスは、コード型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="2d773-119">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="2d773-120">管理特権を必要としないツールの使用</span><span class="sxs-lookup"><span data-stu-id="2d773-120">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="2d773-121">管理者特権を持たないユーザーが WCF サービスを開発できるようにするには、Visual Studio のインストール中に名前空間http://+:8731/Design_Time_Addresses"" に対して ACL (アクセス制御リスト) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="2d773-121">To enable users without administrator privilege to develop WCF services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of Visual Studio.</span></span> <span data-ttu-id="2d773-122">この ACL は (UI) に設定され、コンピューターにログオンしているすべての対話ユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2d773-122">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="2d773-123">管理者は、この ACL にユーザーを追加または削除したり、追加のポートを開いたりできます。この ACL によって、既定の構成で、WCF テンプレートまたは WF テンプレートでデータを送受信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2d773-123">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="2d773-124">また、ユーザーは、管理者特権を付与せずに、WCF サービスの自動ホスト (wcfSvcHost.exe) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2d773-124">It also enables users to use the WCF Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="2d773-125">管理者特権の管理者アカウントで Windows Vista の Netsh.exe ツールを使用してアクセスを変更できます。</span><span class="sxs-lookup"><span data-stu-id="2d773-125">You can modify access using the Netsh.exe tool in Windows Vista under the elevated administrator account.</span></span> <span data-ttu-id="2d773-126">Netsh.exe の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2d773-126">The following is an example of using Netsh.exe.</span></span>  
  
```console  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 <span data-ttu-id="2d773-127">Netsh.exe の詳細については、「 [Netsh.exe ツールおよびコマンド ライン スイッチの使用方法](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d773-127">For more information about Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d773-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d773-128">See also</span></span>

- [<span data-ttu-id="2d773-129">WCF Visual Studio テンプレート</span><span class="sxs-lookup"><span data-stu-id="2d773-129">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)
- [<span data-ttu-id="2d773-130">WCF サービス ホスト (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="2d773-130">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)
- [<span data-ttu-id="2d773-131">WCF のテスト用クライアント (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="2d773-131">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)
