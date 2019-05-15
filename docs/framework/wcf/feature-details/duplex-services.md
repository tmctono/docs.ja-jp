---
title: 双方向サービス
ms.date: 05/09/2018
dev_langs:
- csharp
- vb
ms.assetid: 396b875a-d203-4ebe-a3a1-6a330d962e95
ms.openlocfilehash: 5fef151fe9149e2693ee217e7be642427162322d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636280"
---
# <a name="duplex-services"></a><span data-ttu-id="2fb89-102">双方向サービス</span><span class="sxs-lookup"><span data-stu-id="2fb89-102">Duplex Services</span></span>

<span data-ttu-id="2fb89-103">双方向サービス コントラクトは、両方のエンドポイントが互いに独立してメッセージを送信できるメッセージ交換パターンです。</span><span class="sxs-lookup"><span data-stu-id="2fb89-103">A duplex service contract is a message exchange pattern in which both endpoints can send messages to the other independently.</span></span> <span data-ttu-id="2fb89-104">双方向サービスでは、クライアントのエンドポイントにメッセージを返信できるため、イベントのような動作を実現できます。</span><span class="sxs-lookup"><span data-stu-id="2fb89-104">A duplex service, therefore, can send messages back to the client endpoint, providing event-like behavior.</span></span> <span data-ttu-id="2fb89-105">双方向通信は、クライアントがサービスに接続し、サービスからクライアントにメッセージを返信できるチャネルがサービスに提供されると発生します。</span><span class="sxs-lookup"><span data-stu-id="2fb89-105">Duplex communication occurs when a client connects to a service and provides the service with a channel on which the service can send messages back to the client.</span></span> <span data-ttu-id="2fb89-106">双方向サービスにおけるイベントのような動作は、セッション内でのみ機能することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2fb89-106">Note that the event-like behavior of duplex services only works within a session.</span></span>

<span data-ttu-id="2fb89-107">双方向コントラクトを作成するには、インターフェイスのペアを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fb89-107">To create a duplex contract you create a pair of interfaces.</span></span> <span data-ttu-id="2fb89-108">最初のインターフェイスは、クライアントから呼び出すことのできる操作を記述したサービス コントラクト インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="2fb89-108">The first is the service contract interface that describes the operations that a client can invoke.</span></span> <span data-ttu-id="2fb89-109">サービス コントラクトを指定する必要があります、*コールバック コントラクト*で、<xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="2fb89-109">That service contract must specify a *callback contract* in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="2fb89-110">このコールバック コントラクトが、サービスがクライアント エンドポイントで呼び出すことのできる操作を定義するインターフェイスになります。</span><span class="sxs-lookup"><span data-stu-id="2fb89-110">The callback contract is the interface that defines the operations that the service can call on the client endpoint.</span></span> <span data-ttu-id="2fb89-111">双方向コントラクトではセッションは必要ありませんが、システム指定の二重バインディングではセッションを利用します。</span><span class="sxs-lookup"><span data-stu-id="2fb89-111">A duplex contract does not require a session, although the system-provided duplex bindings make use of them.</span></span>

<span data-ttu-id="2fb89-112">双方向コントラクトの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2fb89-112">The following is an example of a duplex contract.</span></span>

[!code-csharp[c_DuplexServices#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#0)]
[!code-vb[c_DuplexServices#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#0)]

<span data-ttu-id="2fb89-113">`CalculatorService` クラスは、プライマリ `ICalculatorDuplex` インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="2fb89-113">The `CalculatorService` class implements the primary `ICalculatorDuplex` interface.</span></span> <span data-ttu-id="2fb89-114">このサービスは <xref:System.ServiceModel.InstanceContextMode.PerSession> インスタンス モードを使用して、各セッションの結果を保持します。</span><span class="sxs-lookup"><span data-stu-id="2fb89-114">The service uses the <xref:System.ServiceModel.InstanceContextMode.PerSession> instance mode to maintain the result for each session.</span></span> <span data-ttu-id="2fb89-115">`Callback` というプライベート プロパティを使用して、クライアントへのコールバック チャネルにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="2fb89-115">A private property named `Callback` accesses the callback channel to the client.</span></span> <span data-ttu-id="2fb89-116">次のサンプル コードに示すように、サービスはこのコールバックを使用し、コールバック インターフェイスを介してメッセージをクライアントに返信します。</span><span class="sxs-lookup"><span data-stu-id="2fb89-116">The service uses the callback for sending messages back to the client through the callback interface, as shown in the following sample code.</span></span>

[!code-csharp[c_DuplexServices#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/service.cs#1)]
[!code-vb[c_DuplexServices#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/service.vb#1)]

<span data-ttu-id="2fb89-117">クライアントは、サービスからのメッセージを受信するために、双方向コントラクトのコールバック インターフェイスを実装するクラスを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fb89-117">The client must provide a class that implements the callback interface of the duplex contract, for receiving messages from the service.</span></span> <span data-ttu-id="2fb89-118">次のサンプル コードに、`CallbackHandler` インターフェイスを実装する `ICalculatorDuplexCallback` クラスを示します。</span><span class="sxs-lookup"><span data-stu-id="2fb89-118">The following sample code shows a `CallbackHandler` class that implements the `ICalculatorDuplexCallback` interface.</span></span>

[!code-csharp[c_DuplexServices#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#2)]
[!code-vb[c_DuplexServices#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#2)]

<span data-ttu-id="2fb89-119">双方向コントラクトでは、用に生成される WCF クライアントを<xref:System.ServiceModel.InstanceContext>構築時に提供するクラス。</span><span class="sxs-lookup"><span data-stu-id="2fb89-119">The WCF client that is generated for a duplex contract requires a <xref:System.ServiceModel.InstanceContext> class to be provided upon construction.</span></span> <span data-ttu-id="2fb89-120">この <xref:System.ServiceModel.InstanceContext> クラスが、コールバック インターフェイスを実装するオブジェクトのサイトとして使用され、サービスから返信されるメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="2fb89-120">This <xref:System.ServiceModel.InstanceContext> class is used as the site for an object that implements the callback interface and handles messages that are sent back from the service.</span></span> <span data-ttu-id="2fb89-121"><xref:System.ServiceModel.InstanceContext> クラスは、`CallbackHandler` クラスのインスタンスを使用して構築されます。</span><span class="sxs-lookup"><span data-stu-id="2fb89-121">An <xref:System.ServiceModel.InstanceContext> class is constructed with an instance of the `CallbackHandler` class.</span></span> <span data-ttu-id="2fb89-122">このオブジェクトは、コールバック インターフェイスでサービスからクライアントに送信されるメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="2fb89-122">This object handles messages sent from the service to the client on the callback interface.</span></span>

[!code-csharp[c_DuplexServices#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_duplexservices/cs/client.cs#3)]
[!code-vb[c_DuplexServices#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_duplexservices/vb/client.vb#3)]

<span data-ttu-id="2fb89-123">サービスの構成は、セッション通信と双方向通信の両方をサポートするバインディングを提供するように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fb89-123">The configuration for the service must be set up to provide a binding that supports both session communication and duplex communication.</span></span> <span data-ttu-id="2fb89-124">`wsDualHttpBinding` 要素はセッション通信をサポートし、どちらの方向にも HTTP 接続が 1 つ用意される双方向 HTTP 接続を提供して双方向通信を実現します。</span><span class="sxs-lookup"><span data-stu-id="2fb89-124">The `wsDualHttpBinding` element supports session communication and allows duplex communication by providing dual HTTP connections, one for each direction.</span></span>

<span data-ttu-id="2fb89-125">クライアントで、サーバーがクライアントへの接続に使用するアドレスを構成する必要があります。次のサンプル構成を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fb89-125">On the client, you must configure an address that the server can use to connect to the client, as shown in the following sample configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="2fb89-126">非双方向クライアントがセキュリティで保護されたメッセージ交換を使用して認証に失敗した場合、通常、<xref:System.ServiceModel.Security.MessageSecurityException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="2fb89-126">Non-duplex clients that fail to authenticate using a secure conversation typically throw a <xref:System.ServiceModel.Security.MessageSecurityException>.</span></span> <span data-ttu-id="2fb89-127">ただし、セキュリティで保護されたメッセージ交換を使用する双方向クライアントが認証に失敗した場合、クライアントは代わりに <xref:System.TimeoutException> を受信します。</span><span class="sxs-lookup"><span data-stu-id="2fb89-127">However, if a duplex client that uses a secure conversation fails to authenticate, the client receives a <xref:System.TimeoutException> instead.</span></span>

<span data-ttu-id="2fb89-128">`WSHttpBinding` 要素を使用するクライアントとサービスを作成しても、クライアントのコールバック エンドポイントが含まれていない場合は、次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="2fb89-128">If you create a client/service using the `WSHttpBinding` element and you do not include the client callback endpoint, you will receive the following error.</span></span>

```
HTTP could not register URL
htp://+:80/Temporary_Listen_Addresses/<guid> because TCP port 80 is being used by another application.
```

<span data-ttu-id="2fb89-129">次のサンプル コード方法を示します、クライアントを指定するエンドポイント アドレス プログラムを使用します。</span><span class="sxs-lookup"><span data-stu-id="2fb89-129">The following sample code shows how to specify the client endpoint address programmatically.</span></span>

```csharp
WSDualHttpBinding binding = new WSDualHttpBinding();
EndpointAddress endptadr = new EndpointAddress("http://localhost:12000/DuplexTestUsingCode/Server");
binding.ClientBaseAddress = new Uri("http://localhost:8000/DuplexTestUsingCode/Client/");
```

```vb
Dim binding As New WSDualHttpBinding()
Dim endptadr As New EndpointAddress("http://localhost:12000/DuplexTestUsingCode/Server")
binding.ClientBaseAddress = New Uri("http://localhost:8000/DuplexTestUsingCode/Client/")
```

<span data-ttu-id="2fb89-130">次のサンプル コードは、構成でクライアントのエンドポイント アドレスを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2fb89-130">The following sample code shows how to specify the client endpoint address in configuration.</span></span>

```xml
<client>
    <endpoint name ="ServerEndpoint"
          address="http://localhost:12000/DuplexTestUsingConfig/Server"
          bindingConfiguration="WSDualHttpBinding_IDuplexTest"
            binding="wsDualHttpBinding"
           contract="IDuplexTest" />
</client>
<bindings>
    <wsDualHttpBinding>
        <binding name="WSDualHttpBinding_IDuplexTest"
          clientBaseAddress="http://localhost:8000/myClient/" >
            <security mode="None"/>
         </binding>
    </wsDualHttpBinding>
</bindings>
```

> [!WARNING]
> <span data-ttu-id="2fb89-131">双方向のモデルには、サービスまたはクライアントがそのチャネルを閉じるときに自動的に検出しません。</span><span class="sxs-lookup"><span data-stu-id="2fb89-131">The duplex model doesn't automatically detect when a service or client closes its channel.</span></span> <span data-ttu-id="2fb89-132">したがって、クライアントが予期せず終了した場合は既定では、サービス通知されません、またはサービスが予期せず終了した場合、クライアントは通知されません。</span><span class="sxs-lookup"><span data-stu-id="2fb89-132">So if a client unexpectedly terminates, by default the service will not be notified, or if a service unexpectedly terminates, the client will not be notified.</span></span> <span data-ttu-id="2fb89-133">切断されているサービスを使用する場合、<xref:System.ServiceModel.CommunicationException>例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="2fb89-133">If you use a service that is disconnected, the <xref:System.ServiceModel.CommunicationException> exception is raised.</span></span> <span data-ttu-id="2fb89-134">クライアントとサービスは、独自のプロトコルを実装して、互いに通知するように選択できます。</span><span class="sxs-lookup"><span data-stu-id="2fb89-134">Clients and services can implement their own protocol to notify each other if they so choose.</span></span> <span data-ttu-id="2fb89-135">エラー処理の詳細については、次を参照してください[WCF エラー処理。](../wcf-error-handling.md)</span><span class="sxs-lookup"><span data-stu-id="2fb89-135">For more information on error handling, see [WCF Error Handling](../wcf-error-handling.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="2fb89-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="2fb89-136">See also</span></span>

- [<span data-ttu-id="2fb89-137">二重</span><span class="sxs-lookup"><span data-stu-id="2fb89-137">Duplex</span></span>](../samples/duplex.md)
- [<span data-ttu-id="2fb89-138">クライアントのランタイム動作の指定</span><span class="sxs-lookup"><span data-stu-id="2fb89-138">Specifying Client Run-Time Behavior</span></span>](../specifying-client-run-time-behavior.md)
- [<span data-ttu-id="2fb89-139">方法: チャネル ファクトリを作成し、使用して作成および管理チャネル</span><span class="sxs-lookup"><span data-stu-id="2fb89-139">How to: Create a Channel Factory and Use it to Create and Manage Channels</span></span>](how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels.md)
