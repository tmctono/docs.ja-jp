---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: fa87a1b0961425d6a9bc84769bef6e87cbc2ce96
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732561"
---
# <a name="websocketsettings"></a><span data-ttu-id="10856-101">\<webSocketSettings ></span><span class="sxs-lookup"><span data-stu-id="10856-101">\<webSocketSettings></span></span>
<span data-ttu-id="10856-102">Web ソケット設定を指定するために使用される構成要素。</span><span class="sxs-lookup"><span data-stu-id="10856-102">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="10856-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="10856-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="10856-104">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="10856-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="10856-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="10856-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="10856-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netHttpBinding >** ](nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="10856-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="10856-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="10856-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="10856-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**webSocketSettings >**</span><span class="sxs-lookup"><span data-stu-id="10856-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webSocketSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10856-109">構文</span><span class="sxs-lookup"><span data-stu-id="10856-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10856-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="10856-110">Attributes and Elements</span></span>  
 <span data-ttu-id="10856-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="10856-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10856-112">属性</span><span class="sxs-lookup"><span data-stu-id="10856-112">Attributes</span></span>  
  
|<span data-ttu-id="10856-113">属性</span><span class="sxs-lookup"><span data-stu-id="10856-113">Attribute</span></span>|<span data-ttu-id="10856-114">説明</span><span class="sxs-lookup"><span data-stu-id="10856-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="10856-115">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="10856-115">createNotificationOnConnection</span></span>|<span data-ttu-id="10856-116">通知を接続時に送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="10856-116">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="10856-117">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="10856-117">disablePayloadMasking</span></span>|<span data-ttu-id="10856-118">Web ソケットのマスクが無効であるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="10856-118">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="10856-119">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="10856-119">keepAliveInterval</span></span>|<span data-ttu-id="10856-120">接続維持の間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="10856-120">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="10856-121">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="10856-121">maxPendingConnections</span></span>|<span data-ttu-id="10856-122">サービスでのディスパッチを待機している接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="10856-122">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="10856-123">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="10856-123">receiveBufferSize</span></span>|<span data-ttu-id="10856-124">受信バッファーのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="10856-124">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="10856-125">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="10856-125">sendBufferSize</span></span>|<span data-ttu-id="10856-126">送信バッファーのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="10856-126">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="10856-127">subProtocol</span><span class="sxs-lookup"><span data-stu-id="10856-127">subProtocol</span></span>|<span data-ttu-id="10856-128">Web ソケットのサブプロトコルを指定します。</span><span class="sxs-lookup"><span data-stu-id="10856-128">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="10856-129">transportUsage</span><span class="sxs-lookup"><span data-stu-id="10856-129">transportUsage</span></span>|<span data-ttu-id="10856-130">Web ソケットを使用するタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="10856-130">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="10856-131">transportUsage 属性</span><span class="sxs-lookup"><span data-stu-id="10856-131">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="10856-132">[値]</span><span class="sxs-lookup"><span data-stu-id="10856-132">Value</span></span>|<span data-ttu-id="10856-133">説明</span><span class="sxs-lookup"><span data-stu-id="10856-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="10856-134">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="10856-134">WhenDuplex</span></span>|<span data-ttu-id="10856-135">コントラクトが双方向の場合に、Web ソケット プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="10856-135">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="10856-136">Always</span><span class="sxs-lookup"><span data-stu-id="10856-136">Always</span></span>|<span data-ttu-id="10856-137">コントラクトにかかわらず、常にWeb ソケット プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="10856-137">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="10856-138">Never</span><span class="sxs-lookup"><span data-stu-id="10856-138">Never</span></span>|<span data-ttu-id="10856-139">Web ソケット プロトコルを使用しません。</span><span class="sxs-lookup"><span data-stu-id="10856-139">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10856-140">子要素</span><span class="sxs-lookup"><span data-stu-id="10856-140">Child Elements</span></span>  
 <span data-ttu-id="10856-141">None</span><span class="sxs-lookup"><span data-stu-id="10856-141">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="10856-142">親要素</span><span class="sxs-lookup"><span data-stu-id="10856-142">Parent Elements</span></span>  
  
|<span data-ttu-id="10856-143">要素</span><span class="sxs-lookup"><span data-stu-id="10856-143">Element</span></span>|<span data-ttu-id="10856-144">説明</span><span class="sxs-lookup"><span data-stu-id="10856-144">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="10856-145">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="10856-145">\<netHttpBinding></span></span>|<span data-ttu-id="10856-146">NetHttpBinding を指定します。</span><span class="sxs-lookup"><span data-stu-id="10856-146">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="10856-147">例</span><span class="sxs-lookup"><span data-stu-id="10856-147">Example</span></span>  
 <span data-ttu-id="10856-148">次の例は、\<webSocketSettings > 要素の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="10856-148">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="10856-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="10856-149">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="10856-150">バインディング</span><span class="sxs-lookup"><span data-stu-id="10856-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="10856-151">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="10856-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="10856-152">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="10856-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="10856-153">\<binding ></span><span class="sxs-lookup"><span data-stu-id="10856-153">\<binding></span></span>](bindings.md)
