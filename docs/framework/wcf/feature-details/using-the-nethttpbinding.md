---
title: NetHttpBinding の使用
ms.date: 03/30/2017
ms.assetid: fe134acf-ceca-49de-84a9-05a37e3841f1
ms.openlocfilehash: 5090cfdfeb068acda1e1092e408f3cd747c574c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121018"
---
# <a name="using-the-nethttpbinding"></a><span data-ttu-id="75b57-102">NetHttpBinding の使用</span><span class="sxs-lookup"><span data-stu-id="75b57-102">Using the NetHttpBinding</span></span>
<xref:System.ServiceModel.NetHttpBinding> <span data-ttu-id="75b57-103">HTTP や WebSocket のサービスを使用するために設計されたバインドと既定でバイナリ エンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="75b57-103">is a binding designed for consuming HTTP or WebSocket services and uses binary encoding by default.</span></span> <xref:System.ServiceModel.NetHttpBinding> <span data-ttu-id="75b57-104">要求/応答コントラクトまたは双方向コントラクトと共に使用するかどうかを検出し、一致するように動作の変更 - 双方向コントラクトの要求/応答コントラクトと Websocket の HTTP が使用されます。</span><span class="sxs-lookup"><span data-stu-id="75b57-104">will detect whether it is used with a request-reply contract or duplex contract and change its behavior to match - it will use HTTP for request-reply contracts and WebSockets for duplex contracts.</span></span> <span data-ttu-id="75b57-105">この動作は、<xref:System.ServiceModel.Channels.WebSocketTransportUsage> 設定を使用してオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="75b57-105">This behavior can be overridden using the <xref:System.ServiceModel.Channels.WebSocketTransportUsage> setting:</span></span>  
  
1. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.Always> <span data-ttu-id="75b57-106">-これは、要求/応答コントラクトにも使用される websocket です。</span><span class="sxs-lookup"><span data-stu-id="75b57-106">- This forces WebSockets to be used even for request-reply contracts.</span></span>  
  
2. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.Never> <span data-ttu-id="75b57-107">-これは Websocket が使用することを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="75b57-107">- This prevents WebSockets from being used.</span></span> <span data-ttu-id="75b57-108">この設定で二重のコントラクトを使用しようとすると、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="75b57-108">Attempting to use a duplex contract with this setting will result in an exception.</span></span>  
  
3. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.WhenDuplex> <span data-ttu-id="75b57-109">-これにより、既定値は、し、前述のように動作します。</span><span class="sxs-lookup"><span data-stu-id="75b57-109">- This is the default value and behaves as described above.</span></span>  
  
 <xref:System.ServiceModel.NetHttpBinding> <span data-ttu-id="75b57-110">HTTP モードと WebSocket モードの両方で信頼できるセッションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="75b57-110">supports reliable sessions in both HTTP mode and WebSocket mode.</span></span> <span data-ttu-id="75b57-111">WebSocket モードでは、セッションがトランスポートによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="75b57-111">In WebSocket mode sessions are provided by the transport.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="75b57-112"><xref:System.ServiceModel.NetHttpBinding> を使用していて、バインドの TransferMode が TransferMode.Streamed に設定されている場合、大きいストリームによってデッドロックが発生する可能性があり、呼び出しがタイムアウトします。</span><span class="sxs-lookup"><span data-stu-id="75b57-112">When using the <xref:System.ServiceModel.NetHttpBinding> and the binding’s TransferMode is set to TransferMode.Streamed, large streams may cause a deadlock and the call will timeout.</span></span> <span data-ttu-id="75b57-113">この問題を回避するには、小さいメッセージを送信するか、TransferMode.Buffered を使用してください。</span><span class="sxs-lookup"><span data-stu-id="75b57-113">To work around this issue send smaller messages or use TransferMode.Buffered.</span></span>  
  
## <a name="configuring-a-service-to-use-nethttpbinding"></a><span data-ttu-id="75b57-114">NetHttpBinding を使用するサービスの構成</span><span class="sxs-lookup"><span data-stu-id="75b57-114">Configuring a Service to use NetHttpBinding</span></span>  
 <span data-ttu-id="75b57-115"><xref:System.ServiceModel.NetHttpBinding> は、他のバインドと同様に構成できます。</span><span class="sxs-lookup"><span data-stu-id="75b57-115">The <xref:System.ServiceModel.NetHttpBinding> can be configured the same as any other binding.</span></span> <span data-ttu-id="75b57-116">次の構成スニペットは、<xref:System.ServiceModel.NetHttpBinding> を使用して WCF サービスを構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="75b57-116">The following configuration snippet illustrates how to configure a WCF service with <xref:System.ServiceModel.NetHttpBinding>.</span></span>  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="WcfService1.Service1">  
        <endpoint address=""  
                  binding="netHttpBinding"  
                  contract="WcfService1.IService1"/>  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange"/>  
      </service>  
    </services>  
    <bindings>  
      <netHttpBinding>  
        <binding name="My_NetHttpBindingConfig">  
          <webSocketSettings transportUsage="WhenDuplex"/>  
        </binding>  
      </netHttpBinding>  
    </bindings>  
    ...
  </system.serviceModel>  
```  
  
 <span data-ttu-id="75b57-117">次のコード スニペットは、コードで <xref:System.ServiceModel.NetHttpBinding> を追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="75b57-117">The following code snippet shows how to add the <xref:System.ServiceModel.NetHttpBinding> in code.</span></span>  
  
```csharp  
ServiceHost svchost = new ServiceHost(typeof(Service1), baseAddress);  
            NetHttpBinding binding = new NetHttpBinding();  
            svchost.AddServiceEndpoint(typeof(IService1), binding, address);   
        }  
```  
  
## <a name="see-also"></a><span data-ttu-id="75b57-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="75b57-118">See also</span></span>

- [<span data-ttu-id="75b57-119">サービスのバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="75b57-119">Configuring Bindings for Services</span></span>](../../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)
- [<span data-ttu-id="75b57-120">バインディング</span><span class="sxs-lookup"><span data-stu-id="75b57-120">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)
- [<span data-ttu-id="75b57-121">システム標準のバインディング</span><span class="sxs-lookup"><span data-stu-id="75b57-121">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
- [<span data-ttu-id="75b57-122">双方向サービス</span><span class="sxs-lookup"><span data-stu-id="75b57-122">Duplex Services</span></span>](../../../../docs/framework/wcf/feature-details/duplex-services.md)
