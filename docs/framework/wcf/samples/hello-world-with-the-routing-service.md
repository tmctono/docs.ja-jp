---
title: ルーティング サービスを使用した Hello World
ms.date: 03/30/2017
ms.assetid: 0f4b0d5b-6522-4ad5-9f3a-baa78316d7d1
ms.openlocfilehash: 37d2eaffa1ca5a4cce27c4950d00987828a61196
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62006604"
---
# <a name="hello-world-with-the-routing-service"></a><span data-ttu-id="b24e9-102">ルーティング サービスを使用した Hello World</span><span class="sxs-lookup"><span data-stu-id="b24e9-102">Hello World with the Routing Service</span></span>
<span data-ttu-id="b24e9-103">このサンプルでは、Windows Communication Foundation (WCF) ルーティング サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="b24e9-103">This sample demonstrates the Windows Communication Foundation (WCF) Routing Service.</span></span> <span data-ttu-id="b24e9-104">ルーティング サービスは、WCF コンポーネント、アプリケーションでコンテンツ ベースのルーターを含めるが簡単です。</span><span class="sxs-lookup"><span data-stu-id="b24e9-104">The Routing Service is a WCF component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="b24e9-105">このサンプルでは、ルーティング サービスを使用して通信する標準の WCF 電卓のサンプルを適応します。</span><span class="sxs-lookup"><span data-stu-id="b24e9-105">This sample adapts the standard WCF Calculator Sample to communicate using the Routing Service.</span></span> <span data-ttu-id="b24e9-106">このサンプルの電卓クライアントは、ルーターによって公開されるエンドポイントにメッセージを送信するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="b24e9-106">In this sample, the Calculator client is configured to send messages to an endpoint exposed by the router.</span></span> <span data-ttu-id="b24e9-107">ルーティング サービスは、送信されてきたすべてのメッセージを受け入れ、電卓サービスに対応するエンドポイントに転送するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="b24e9-107">The Routing Service is configured to accept all messages sent to it and to forward them to an endpoint that corresponds to the Calculator service.</span></span> <span data-ttu-id="b24e9-108">したがって、クライアントから送信されたメッセージはルーターで受信され、実際の電卓サービスに再ルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b24e9-108">Thus messages sent from the client are received by the router and re-routed to the actual Calculator service.</span></span> <span data-ttu-id="b24e9-109">電卓サービスからのメッセージはルーターに送り返され、ルーターから電卓クライアントに渡されます。</span><span class="sxs-lookup"><span data-stu-id="b24e9-109">Messages from the Calculator service are sent back to the router, which in turn passes them back to the Calculator client.</span></span>

### <a name="to-use-this-sample"></a><span data-ttu-id="b24e9-110">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="b24e9-110">To use this sample</span></span>

1. <span data-ttu-id="b24e9-111">Visual Studio 2012 を使用して、HelloRoutingService.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="b24e9-111">Using Visual Studio 2012, open HelloRoutingService.sln.</span></span>

2. <span data-ttu-id="b24e9-112">F5 キーを押すか、Ctrl キーと Shift キーを押しながら B キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b24e9-112">Press F5 or CTRL+SHIFT+B.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b24e9-113">F5 キーを押した場合は、電卓クライアントが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="b24e9-113">If you press F5, the Calculator Client automatically starts.</span></span> <span data-ttu-id="b24e9-114">Ctrl キーと Shift キーを押しながら B キーを押した (ビルドする) 場合は、次のアプリケーションを手動で開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b24e9-114">If you press CTRL+SHIFT+B (build), you must start following applications yourself.</span></span>
    >
    > 1. <span data-ttu-id="b24e9-115">電卓クライアント (./CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="b24e9-115">Calculator client (./CalculatorClient/bin/client.exe</span></span>
    > 2. <span data-ttu-id="b24e9-116">電卓サービス (./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="b24e9-116">Calculator service (./CalculatorService/bin/service.exe)</span></span>
    > 3. <span data-ttu-id="b24e9-117">ルーティング サービス (./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="b24e9-117">Routing service (./RoutingService/bin/RoutingService.exe)</span></span>

3. <span data-ttu-id="b24e9-118">Enter キーを押してクライアントを起動します。</span><span class="sxs-lookup"><span data-stu-id="b24e9-118">Press ENTER to start the client.</span></span>

     <span data-ttu-id="b24e9-119">次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b24e9-119">You should see the following output:</span></span>

    ```console
     Add(100,15.99) = 115.99

     Subtract(145,76.54) = 68.46

     Multiply(9,81.25) = 731.25

     Divide(22,7) = 3.14285714285714
    ```

## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="b24e9-120">コードまたは App.Config で構成可能</span><span class="sxs-lookup"><span data-stu-id="b24e9-120">Configurable via Code or App.Config</span></span>
 <span data-ttu-id="b24e9-121">サンプルは、提供された時点では、App.config ファイルを使用してルーターの動作を定義するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="b24e9-121">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="b24e9-122">App.config ファイルの名前を別の名前に変更して認識されないようにし、ConfigureRouterViaCode() に対するメソッド呼び出しのコメントを解除することもできます。</span><span class="sxs-lookup"><span data-stu-id="b24e9-122">You can also change the name of the App.config file to something else so that it is not recognized and uncomment the method call to ConfigureRouterViaCode().</span></span> <span data-ttu-id="b24e9-123">どちらの方法でも、ルーターの動作は同じになります。</span><span class="sxs-lookup"><span data-stu-id="b24e9-123">Either method results in the same behavior from the router.</span></span>

### <a name="scenario"></a><span data-ttu-id="b24e9-124">シナリオ</span><span class="sxs-lookup"><span data-stu-id="b24e9-124">Scenario</span></span>
 <span data-ttu-id="b24e9-125">このサンプルでは、基本的なメッセージ ポンプとして機能するルーターを示します。</span><span class="sxs-lookup"><span data-stu-id="b24e9-125">This sample demonstrates the router acting as a basic message pump.</span></span> <span data-ttu-id="b24e9-126">ルーティング サービスは、構成済みの一連の送信先エンドポイントに直接メッセージを渡すように構成された透過的なプロキシ ノードとして機能します。</span><span class="sxs-lookup"><span data-stu-id="b24e9-126">The routing service acts as a transparent proxy node configured to pass messages directly to a preconfigured set of destination endpoints.</span></span>

### <a name="real-world-scenario"></a><span data-ttu-id="b24e9-127">実際のシナリオ</span><span class="sxs-lookup"><span data-stu-id="b24e9-127">Real World Scenario</span></span>
 <span data-ttu-id="b24e9-128">Contoso では、サービスの名前指定、アドレス指定、構成、およびセキュリティに関する柔軟性を高めるために、</span><span class="sxs-lookup"><span data-stu-id="b24e9-128">Contoso wants to increase the flexibility it has in the naming, addressing, configuration, and security of its services.</span></span> <span data-ttu-id="b24e9-129">基本的なメッセージ ポンプをサービスの前に配置して、それをエンドポイントとして公開しています。</span><span class="sxs-lookup"><span data-stu-id="b24e9-129">To do this, they place a basic message pump in front of their services to act as a public facing endpoint.</span></span> <span data-ttu-id="b24e9-130">これにより、実際のサービスの前にセキュリティが追加され、スケールアウトされたソリューションやサービスのバージョン管理を後で簡単に実装できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b24e9-130">This allows them to place additional security in front of their actual services and make it easier to implement scaled out solutions or service versioning at a later date.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="b24e9-131">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="b24e9-131">The samples may already be installed on your computer.</span></span> <span data-ttu-id="b24e9-132">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b24e9-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b24e9-133">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="b24e9-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b24e9-134">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="b24e9-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\HelloRoutingService`  
  
## <a name="see-also"></a><span data-ttu-id="b24e9-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="b24e9-135">See also</span></span>

- [<span data-ttu-id="b24e9-136">AppFabric のホストおよび永続化のサンプル</span><span class="sxs-lookup"><span data-stu-id="b24e9-136">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
