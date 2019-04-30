---
title: '方法: 探索プロキシをテストする'
ms.date: 03/30/2017
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
ms.openlocfilehash: 856b86241299585b80d58c6d37582463736a5935
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972914"
---
# <a name="how-to-test-the-discovery-proxy"></a><span data-ttu-id="98039-102">方法: 探索プロキシをテストする</span><span class="sxs-lookup"><span data-stu-id="98039-102">How to: Test the Discovery Proxy</span></span>
<span data-ttu-id="98039-103">これは、探索プロキシの実装方法に関する 4 つのトピックのうちの 4 番目のトピックです。</span><span class="sxs-lookup"><span data-stu-id="98039-103">This is the fourth of four topics that shows how to implement a discovery proxy.</span></span> <span data-ttu-id="98039-104">前のトピックで[方法。探索プロキシを使用して、サービスを検索するクライアント アプリケーションの実装](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)、探索プロキシを使用して、サービスを検索して、サービスを呼び出している WCF クライアント アプリケーションを実装します。</span><span class="sxs-lookup"><span data-stu-id="98039-104">In the previous topic, [How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), you implemented a WCF client application that uses the discovery proxy to find a service and then calls the service.</span></span> <span data-ttu-id="98039-105">このトピックでは、探索プロキシ、サービス、およびクライアント アプリケーションが予期したとおりに動作することを確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="98039-105">This topic describes how to verify the discovery proxy, the service, and the client application work as expected.</span></span>  
  
### <a name="run-the-discovery-proxy"></a><span data-ttu-id="98039-106">探索プロキシの実行</span><span class="sxs-lookup"><span data-stu-id="98039-106">Run the Discovery Proxy</span></span>  
  
1. <span data-ttu-id="98039-107">管理者としてコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="98039-107">Open a command prompt as an administrator.</span></span>  
  
2. <span data-ttu-id="98039-108">示すダイアログが表示されます。Windows ファイアウォールには、このプログラムの一部の機能がブロックされています。</span><span class="sxs-lookup"><span data-stu-id="98039-108">You may see a dialog that says: Windows Firewall has blocked some features of this program.</span></span> <span data-ttu-id="98039-109">このメッセージを表示する場合は、クリックして、**ブロック解除**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="98039-109">If you see this message, click the **Unblock** button.</span></span>  
  
3. <span data-ttu-id="98039-110">コマンド プロンプトから、探索プロキシ DiscoveryProxy.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="98039-110">Within the command prompt, run the discovery proxy, DiscoveryProxy.exe.</span></span>  
  
4. <span data-ttu-id="98039-111">「`Proxy started. Hit Enter to exit`」というテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="98039-111">The application should display the following text: `Proxy started. Hit Enter to exit`.</span></span>  
  
### <a name="run-the-discoverable-service"></a><span data-ttu-id="98039-112">探索サービスの実行</span><span class="sxs-lookup"><span data-stu-id="98039-112">Run the Discoverable Service</span></span>  
  
1. <span data-ttu-id="98039-113">管理者としてコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="98039-113">Open a command prompt as an administrator.</span></span>  
  
2. <span data-ttu-id="98039-114">コマンド プロンプトから、探索サービス Service.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="98039-114">Within the command prompt, run the Service.exe discoverable service.</span></span>  
  
3. <span data-ttu-id="98039-115">DiscoveryProxy.exe により、次のテキストが表示:`******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******`します。</span><span class="sxs-lookup"><span data-stu-id="98039-115">The DiscoveryProxy.exe should display the following text: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span></span>  
  
### <a name="run-the-client-application"></a><span data-ttu-id="98039-116">クライアント アプリケーションの実行</span><span class="sxs-lookup"><span data-stu-id="98039-116">Run the Client Application</span></span>  
  
1. <span data-ttu-id="98039-117">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="98039-117">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="98039-118">コマンド プロンプトから、client.exe アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="98039-118">Within the command prompt, run the client.exe application.</span></span>  
  
3. <span data-ttu-id="98039-119">数秒後に、クライアント アプリケーションは、次のテキストを表示します。サービスのエンドポイントに接続します。</span><span class="sxs-lookup"><span data-stu-id="98039-119">After a few seconds the client application displays the following text: Connecting to [Service-Endpoint].</span></span>  
  
4. <span data-ttu-id="98039-120">Service.exe し、次のテキストが表示されます。受信した要求を案内するには、私は応答します。</span><span class="sxs-lookup"><span data-stu-id="98039-120">The service.exe should then display the following text: Greeting request received, I will respond.</span></span>  
  
5. <span data-ttu-id="98039-121">Client.exe し、次のテキストが表示されます。こんにちは Client!</span><span class="sxs-lookup"><span data-stu-id="98039-121">The client.exe should then display the following text: Hello Client!</span></span>  
  
### <a name="shut-down-the-applications"></a><span data-ttu-id="98039-122">アプリケーションのシャットダウン</span><span class="sxs-lookup"><span data-stu-id="98039-122">Shut Down the Applications</span></span>  
  
1. <span data-ttu-id="98039-123">クライアント アプリケーションをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="98039-123">Shut down the client application.</span></span>  
  
2. <span data-ttu-id="98039-124">サービスをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="98039-124">Shut down the service.</span></span> <span data-ttu-id="98039-125">探索プロキシにより、次のテキストが表示されます。`******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`</span><span class="sxs-lookup"><span data-stu-id="98039-125">The discovery proxy displays the following text: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span></span>  
  
3. <span data-ttu-id="98039-126">探索プロキシをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="98039-126">Shut down the discovery proxy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98039-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="98039-127">See also</span></span>

- [<span data-ttu-id="98039-128">WCF Discovery の概要</span><span class="sxs-lookup"><span data-stu-id="98039-128">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)
- [<span data-ttu-id="98039-129">方法: 探索プロキシを実装します。</span><span class="sxs-lookup"><span data-stu-id="98039-129">How to: Implement a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)
- [<span data-ttu-id="98039-130">方法: 探索プロキシで登録される探索可能なサービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="98039-130">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)
- [<span data-ttu-id="98039-131">方法: 探索プロキシを使用して、サービスを検索するクライアント アプリケーションを実装します。</span><span class="sxs-lookup"><span data-stu-id="98039-131">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)
