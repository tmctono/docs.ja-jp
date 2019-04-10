---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 1101d021f3c7436c4f45a22a48e50f6d1553f753
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226873"
---
# <a name="websocketsettings"></a><span data-ttu-id="9253d-101">\<webSocketSettings ></span><span class="sxs-lookup"><span data-stu-id="9253d-101">\<webSocketSettings></span></span>
<span data-ttu-id="9253d-102">Web ソケット設定を指定するために使用される構成要素。</span><span class="sxs-lookup"><span data-stu-id="9253d-102">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="9253d-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9253d-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="9253d-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="9253d-104">\<bindings></span></span>  
<span data-ttu-id="9253d-105">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9253d-105">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9253d-106">構文</span><span class="sxs-lookup"><span data-stu-id="9253d-106">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="Boolean"
                       disablePayloadMasking="Boolean"
                       keepAliveInterval="TimeSpan"
                       maxPendingConnections="Integer"
                       receiveBufferSize="Integer"
                       sendBufferSize="Integer"
                       subProtocol="String"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9253d-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9253d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="9253d-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9253d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9253d-109">属性</span><span class="sxs-lookup"><span data-stu-id="9253d-109">Attributes</span></span>  
  
|<span data-ttu-id="9253d-110">属性</span><span class="sxs-lookup"><span data-stu-id="9253d-110">Attribute</span></span>|<span data-ttu-id="9253d-111">説明</span><span class="sxs-lookup"><span data-stu-id="9253d-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9253d-112">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="9253d-112">createNotificationOnConnection</span></span>|<span data-ttu-id="9253d-113">通知を接続時に送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9253d-113">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="9253d-114">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="9253d-114">disablePayloadMasking</span></span>|<span data-ttu-id="9253d-115">Web ソケットのマスクが無効であるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9253d-115">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="9253d-116">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="9253d-116">keepAliveInterval</span></span>|<span data-ttu-id="9253d-117">接続維持の間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="9253d-117">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="9253d-118">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="9253d-118">maxPendingConnections</span></span>|<span data-ttu-id="9253d-119">サービスでのディスパッチを待機している接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9253d-119">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="9253d-120">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="9253d-120">receiveBufferSize</span></span>|<span data-ttu-id="9253d-121">受信バッファーのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="9253d-121">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="9253d-122">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="9253d-122">sendBufferSize</span></span>|<span data-ttu-id="9253d-123">送信バッファーのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="9253d-123">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="9253d-124">subProtocol</span><span class="sxs-lookup"><span data-stu-id="9253d-124">subProtocol</span></span>|<span data-ttu-id="9253d-125">Web ソケットのサブプロトコルを指定します。</span><span class="sxs-lookup"><span data-stu-id="9253d-125">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="9253d-126">transportUsage</span><span class="sxs-lookup"><span data-stu-id="9253d-126">transportUsage</span></span>|<span data-ttu-id="9253d-127">Web ソケットを使用するタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="9253d-127">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="9253d-128">transportUsage 属性</span><span class="sxs-lookup"><span data-stu-id="9253d-128">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="9253d-129">[値]</span><span class="sxs-lookup"><span data-stu-id="9253d-129">Value</span></span>|<span data-ttu-id="9253d-130">説明</span><span class="sxs-lookup"><span data-stu-id="9253d-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9253d-131">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="9253d-131">WhenDuplex</span></span>|<span data-ttu-id="9253d-132">コントラクトが双方向の場合に、Web ソケット プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="9253d-132">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="9253d-133">Always</span><span class="sxs-lookup"><span data-stu-id="9253d-133">Always</span></span>|<span data-ttu-id="9253d-134">コントラクトにかかわらず、常にWeb ソケット プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="9253d-134">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="9253d-135">Never</span><span class="sxs-lookup"><span data-stu-id="9253d-135">Never</span></span>|<span data-ttu-id="9253d-136">Web ソケット プロトコルを使用しません。</span><span class="sxs-lookup"><span data-stu-id="9253d-136">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9253d-137">子要素</span><span class="sxs-lookup"><span data-stu-id="9253d-137">Child Elements</span></span>  
 <span data-ttu-id="9253d-138">なし</span><span class="sxs-lookup"><span data-stu-id="9253d-138">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9253d-139">親要素</span><span class="sxs-lookup"><span data-stu-id="9253d-139">Parent Elements</span></span>  
  
|<span data-ttu-id="9253d-140">要素</span><span class="sxs-lookup"><span data-stu-id="9253d-140">Element</span></span>|<span data-ttu-id="9253d-141">説明</span><span class="sxs-lookup"><span data-stu-id="9253d-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9253d-142">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9253d-142">\<netHttpBinding></span></span>|<span data-ttu-id="9253d-143">NetHttpBinding を指定します。</span><span class="sxs-lookup"><span data-stu-id="9253d-143">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9253d-144">例</span><span class="sxs-lookup"><span data-stu-id="9253d-144">Example</span></span>  
 <span data-ttu-id="9253d-145">次の例は、使用する方法を示します、 \<webSocketSettings > 要素。</span><span class="sxs-lookup"><span data-stu-id="9253d-145">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="true"
                       disablePayloadMasking="false"
                       keepAliveInterval="00:10:00"
                       maxPendingConnections="100"
                       receiveBufferSize="1000"
                       sendBufferSize="1000"
                       subProtocol="Soap"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="see-also"></a><span data-ttu-id="9253d-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="9253d-146">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="9253d-147">バインディング</span><span class="sxs-lookup"><span data-stu-id="9253d-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="9253d-148">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="9253d-148">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9253d-149">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="9253d-149">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9253d-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="9253d-150">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
