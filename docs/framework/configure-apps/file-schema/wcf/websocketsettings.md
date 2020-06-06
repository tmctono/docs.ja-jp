---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: fa87a1b0961425d6a9bc84769bef6e87cbc2ce96
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732561"
---
# \<webSocketSettings>
<span data-ttu-id="acc48-101">Web ソケット設定を指定するために使用される構成要素。</span><span class="sxs-lookup"><span data-stu-id="acc48-101">A configuration element used to specify Web Socket settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webSocketSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="acc48-102">構文</span><span class="sxs-lookup"><span data-stu-id="acc48-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="acc48-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="acc48-103">Attributes and Elements</span></span>  
 <span data-ttu-id="acc48-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="acc48-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="acc48-105">属性</span><span class="sxs-lookup"><span data-stu-id="acc48-105">Attributes</span></span>  
  
|<span data-ttu-id="acc48-106">属性</span><span class="sxs-lookup"><span data-stu-id="acc48-106">Attribute</span></span>|<span data-ttu-id="acc48-107">説明</span><span class="sxs-lookup"><span data-stu-id="acc48-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="acc48-108">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="acc48-108">createNotificationOnConnection</span></span>|<span data-ttu-id="acc48-109">通知を接続時に送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="acc48-109">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="acc48-110">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="acc48-110">disablePayloadMasking</span></span>|<span data-ttu-id="acc48-111">Web ソケットのマスクが無効であるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="acc48-111">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="acc48-112">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="acc48-112">keepAliveInterval</span></span>|<span data-ttu-id="acc48-113">接続維持の間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="acc48-113">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="acc48-114">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="acc48-114">maxPendingConnections</span></span>|<span data-ttu-id="acc48-115">サービスでのディスパッチを待機している接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="acc48-115">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="acc48-116">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="acc48-116">receiveBufferSize</span></span>|<span data-ttu-id="acc48-117">受信バッファーのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="acc48-117">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="acc48-118">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="acc48-118">sendBufferSize</span></span>|<span data-ttu-id="acc48-119">送信バッファーのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="acc48-119">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="acc48-120">subProtocol</span><span class="sxs-lookup"><span data-stu-id="acc48-120">subProtocol</span></span>|<span data-ttu-id="acc48-121">Web ソケットのサブプロトコルを指定します。</span><span class="sxs-lookup"><span data-stu-id="acc48-121">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="acc48-122">transportUsage</span><span class="sxs-lookup"><span data-stu-id="acc48-122">transportUsage</span></span>|<span data-ttu-id="acc48-123">Web ソケットを使用するタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="acc48-123">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="acc48-124">transportUsage 属性</span><span class="sxs-lookup"><span data-stu-id="acc48-124">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="acc48-125">値</span><span class="sxs-lookup"><span data-stu-id="acc48-125">Value</span></span>|<span data-ttu-id="acc48-126">Description</span><span class="sxs-lookup"><span data-stu-id="acc48-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="acc48-127">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="acc48-127">WhenDuplex</span></span>|<span data-ttu-id="acc48-128">コントラクトが双方向の場合に、Web ソケット プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="acc48-128">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="acc48-129">Always (常に)</span><span class="sxs-lookup"><span data-stu-id="acc48-129">Always</span></span>|<span data-ttu-id="acc48-130">コントラクトにかかわらず、常にWeb ソケット プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="acc48-130">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="acc48-131">行わない</span><span class="sxs-lookup"><span data-stu-id="acc48-131">Never</span></span>|<span data-ttu-id="acc48-132">Web ソケット プロトコルを使用しません。</span><span class="sxs-lookup"><span data-stu-id="acc48-132">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="acc48-133">子要素</span><span class="sxs-lookup"><span data-stu-id="acc48-133">Child Elements</span></span>  
 <span data-ttu-id="acc48-134">なし</span><span class="sxs-lookup"><span data-stu-id="acc48-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="acc48-135">親要素</span><span class="sxs-lookup"><span data-stu-id="acc48-135">Parent Elements</span></span>  
  
|<span data-ttu-id="acc48-136">要素</span><span class="sxs-lookup"><span data-stu-id="acc48-136">Element</span></span>|<span data-ttu-id="acc48-137">Description</span><span class="sxs-lookup"><span data-stu-id="acc48-137">Description</span></span>|  
|-------------|-----------------|  
|\<netHttpBinding>|<span data-ttu-id="acc48-138">NetHttpBinding を指定します。</span><span class="sxs-lookup"><span data-stu-id="acc48-138">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="acc48-139">例</span><span class="sxs-lookup"><span data-stu-id="acc48-139">Example</span></span>  
 <span data-ttu-id="acc48-140">\<webSocketSettings> 要素を使用する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="acc48-140">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="acc48-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="acc48-141">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="acc48-142">バインド</span><span class="sxs-lookup"><span data-stu-id="acc48-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="acc48-143">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="acc48-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="acc48-144">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="acc48-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
