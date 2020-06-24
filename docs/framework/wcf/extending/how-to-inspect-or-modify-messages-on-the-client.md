---
title: '方法: クライアントのメッセージを検査または変更する'
description: 適切なインターフェイスを実装することによって、WCF クライアントまたはサービス全体で受信または送信メッセージを検査または変更する方法について説明します。
ms.date: 03/30/2017
ms.assetid: b8256335-f1c2-419f-b862-9f220ccad84c
ms.openlocfilehash: 6f6a3d20d7f3a9fb79de5cd3e29096e270d0f188
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247508"
---
# <a name="how-to-inspect-or-modify-messages-on-the-client"></a><span data-ttu-id="028ec-103">方法: クライアントのメッセージを検査または変更する</span><span class="sxs-lookup"><span data-stu-id="028ec-103">How to: Inspect or Modify Messages on the Client</span></span>
<span data-ttu-id="028ec-104">を実装 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> してクライアントランタイムに挿入することによって、WCF クライアント全体の受信メッセージまたは送信メッセージを検査または変更できます。</span><span class="sxs-lookup"><span data-stu-id="028ec-104">You can inspect or modify the incoming or outgoing messages across a WCF client by implementing a <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> and inserting it into the client runtime.</span></span> <span data-ttu-id="028ec-105">詳細については、「[クライアントの拡張](extending-clients.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="028ec-105">For more information, see [Extending Clients](extending-clients.md).</span></span> <span data-ttu-id="028ec-106">サービスの同等の機能は、<xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType> です。</span><span class="sxs-lookup"><span data-stu-id="028ec-106">The equivalent feature on the service is the <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>.</span></span> <span data-ttu-id="028ec-107">完全なコード例については、[メッセージインスペクター](../samples/message-inspectors.md)のサンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="028ec-107">For a complete code example see the [Message Inspectors](../samples/message-inspectors.md) sample.</span></span>  
  
### <a name="to-inspect-or-modify-messages"></a><span data-ttu-id="028ec-108">メッセージを検査または変更するには</span><span class="sxs-lookup"><span data-stu-id="028ec-108">To inspect or modify messages</span></span>  
  
1. <span data-ttu-id="028ec-109"><xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="028ec-109">Implement the <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> interface.</span></span>  
  
2. <span data-ttu-id="028ec-110">クライアント メッセージ インスペクターを挿入するスコープに応じて、<xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> または <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> を実装します。</span><span class="sxs-lookup"><span data-stu-id="028ec-110">Implement a <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> depending upon the scope at which you want to insert the client message inspector.</span></span> <span data-ttu-id="028ec-111"><xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>エンドポイントレベルで動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="028ec-111"><xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> allows you to change behavior at the endpoint level.</span></span> <span data-ttu-id="028ec-112"><xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>では、コントラクトレベルでの動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="028ec-112"><xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> allows you to change behavior at the contract level.</span></span>  
  
3. <span data-ttu-id="028ec-113"><xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> で <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> メソッドまたは <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> メソッドを呼び出す前に、動作を追加します。</span><span class="sxs-lookup"><span data-stu-id="028ec-113">Insert the behavior prior to calling the <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> or the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="028ec-114">詳細については、「動作を使用した[ランタイムの構成と拡張](configuring-and-extending-the-runtime-with-behaviors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="028ec-114">For details, see [Configuring and Extending the Runtime with Behaviors](configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="028ec-115">例</span><span class="sxs-lookup"><span data-stu-id="028ec-115">Example</span></span>  
 <span data-ttu-id="028ec-116">下のコード例では、次の項目を順番に示しています。</span><span class="sxs-lookup"><span data-stu-id="028ec-116">The following code examples show, in order:</span></span>  
  
- <span data-ttu-id="028ec-117">クライアント インスペクター実装</span><span class="sxs-lookup"><span data-stu-id="028ec-117">A client inspector implementation.</span></span>  
  
- <span data-ttu-id="028ec-118">インスペクターを挿入するエンドポイント動作</span><span class="sxs-lookup"><span data-stu-id="028ec-118">An endpoint behavior that inserts the inspector.</span></span>  
  
- <span data-ttu-id="028ec-119">構成ファイルで動作を追加できるようにする <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> 派生クラス。</span><span class="sxs-lookup"><span data-stu-id="028ec-119">A <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>- derived class that allows you to add the behavior in a configuration file.</span></span>  
  
- <span data-ttu-id="028ec-120">クライアント メッセージ インスペクターをクライアント ランタイムに挿入するエンドポイント動作を追加する構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="028ec-120">A configuration file that adds the endpoint behavior which inserts the client message inspector into the client runtime.</span></span>  
  
```csharp  
// Client message inspector  
public class SimpleMessageInspector : IClientMessageInspector  
{  
    public void AfterReceiveReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
    {  
        // Implement this method to inspect/modify messages after a message  
        // is received but prior to passing it back to the client
        Console.WriteLine("AfterReceiveReply called");  
    }  
  
    public object BeforeSendRequest(ref System.ServiceModel.Channels.Message request, IClientChannel channel)  
    {  
        // Implement this method to inspect/modify messages before they
        // are sent to the service  
        Console.WriteLine("BeforeSendRequest called");  
        return null;  
    }  
}  
```  
  
```csharp  
// Endpoint behavior  
public class SimpleEndpointBehavior : IEndpointBehavior  
{  
    public void AddBindingParameters(ServiceEndpoint endpoint, System.ServiceModel.Channels.BindingParameterCollection bindingParameters)  
    {  
         // No implementation necessary  
    }  
  
    public void ApplyClientBehavior(ServiceEndpoint endpoint, ClientRuntime clientRuntime)  
    {  
        clientRuntime.MessageInspectors.Add(new SimpleMessageInspector());  
    }  
  
    public void ApplyDispatchBehavior(ServiceEndpoint endpoint, EndpointDispatcher endpointDispatcher)  
    {  
         // No implementation necessary  
    }  
  
    public void Validate(ServiceEndpoint endpoint)  
    {  
         // No implementation necessary  
    }  
}  
```  
  
```csharp  
// Configuration element
public class SimpleBehaviorExtensionElement : BehaviorExtensionElement  
{  
    public override Type BehaviorType  
    {  
        get { return typeof(SimpleEndpointBehavior); }  
    }  
  
    protected override object CreateBehavior()  
    {  
         // Create the  endpoint behavior that will insert the message  
         // inspector into the client runtime  
        return new SimpleEndpointBehavior();  
    }  
}  
```  
  
```xml
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <system.serviceModel>  
        <client>  
            <endpoint address="http://localhost:8080/SimpleService/"
                      binding="wsHttpBinding"
                      behaviorConfiguration="clientInspectorsAdded"
                      contract="ServiceReference1.IService1"  
                      name="WSHttpBinding_IService1"/>  
        </client>  
  
      <behaviors>  
        <endpointBehaviors>  
          <behavior name="clientInspectorsAdded">  
            <simpleBehaviorExtension />  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>  
      <extensions>  
        <behaviorExtensions>  
          <add  
            name="simpleBehaviorExtension"  
            type="SimpleServiceLib.SimpleBehaviorExtensionElement, Host, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
        </behaviorExtensions>  
      </extensions>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="028ec-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="028ec-121">See also</span></span>

- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>
- [<span data-ttu-id="028ec-122">動作を使用したランタイムの構成と拡張</span><span class="sxs-lookup"><span data-stu-id="028ec-122">Configuring and Extending the Runtime with Behaviors</span></span>](configuring-and-extending-the-runtime-with-behaviors.md)
