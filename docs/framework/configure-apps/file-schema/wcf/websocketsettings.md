---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 6cfddfb9ebfc7c3447af977e14738baabebc8fe9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177852"
---
# \<webSocketSettings>

<span data-ttu-id="40150-101">Web ソケット設定を指定するために使用される構成要素。</span><span class="sxs-lookup"><span data-stu-id="40150-101">A configuration element used to specify Web Socket settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webSocketSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="40150-102">構文</span><span class="sxs-lookup"><span data-stu-id="40150-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40150-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="40150-103">Attributes and Elements</span></span>  

 <span data-ttu-id="40150-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="40150-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40150-105">属性</span><span class="sxs-lookup"><span data-stu-id="40150-105">Attributes</span></span>  
  
|<span data-ttu-id="40150-106">属性</span><span class="sxs-lookup"><span data-stu-id="40150-106">Attribute</span></span>|<span data-ttu-id="40150-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="40150-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="40150-108">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="40150-108">createNotificationOnConnection</span></span>|<span data-ttu-id="40150-109">通知を接続時に送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="40150-109">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="40150-110">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="40150-110">disablePayloadMasking</span></span>|<span data-ttu-id="40150-111">Web ソケットのマスクが無効であるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="40150-111">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="40150-112">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="40150-112">keepAliveInterval</span></span>|<span data-ttu-id="40150-113">接続維持の間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="40150-113">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="40150-114">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="40150-114">maxPendingConnections</span></span>|<span data-ttu-id="40150-115">サービスでのディスパッチを待機している接続の最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="40150-115">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="40150-116">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="40150-116">receiveBufferSize</span></span>|<span data-ttu-id="40150-117">受信バッファーのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="40150-117">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="40150-118">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="40150-118">sendBufferSize</span></span>|<span data-ttu-id="40150-119">送信バッファーのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="40150-119">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="40150-120">subProtocol</span><span class="sxs-lookup"><span data-stu-id="40150-120">subProtocol</span></span>|<span data-ttu-id="40150-121">Web ソケットのサブプロトコルを指定します。</span><span class="sxs-lookup"><span data-stu-id="40150-121">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="40150-122">transportUsage</span><span class="sxs-lookup"><span data-stu-id="40150-122">transportUsage</span></span>|<span data-ttu-id="40150-123">Web ソケットを使用するタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="40150-123">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="40150-124">transportUsage 属性</span><span class="sxs-lookup"><span data-stu-id="40150-124">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="40150-125">値</span><span class="sxs-lookup"><span data-stu-id="40150-125">Value</span></span>|<span data-ttu-id="40150-126">[説明]</span><span class="sxs-lookup"><span data-stu-id="40150-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="40150-127">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="40150-127">WhenDuplex</span></span>|<span data-ttu-id="40150-128">コントラクトが双方向の場合に、Web ソケット プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="40150-128">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="40150-129">Always (常に)</span><span class="sxs-lookup"><span data-stu-id="40150-129">Always</span></span>|<span data-ttu-id="40150-130">コントラクトにかかわらず、常にWeb ソケット プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="40150-130">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="40150-131">行わない</span><span class="sxs-lookup"><span data-stu-id="40150-131">Never</span></span>|<span data-ttu-id="40150-132">Web ソケット プロトコルを使用しません。</span><span class="sxs-lookup"><span data-stu-id="40150-132">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40150-133">子要素</span><span class="sxs-lookup"><span data-stu-id="40150-133">Child Elements</span></span>  

 <span data-ttu-id="40150-134">None</span><span class="sxs-lookup"><span data-stu-id="40150-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40150-135">親要素</span><span class="sxs-lookup"><span data-stu-id="40150-135">Parent Elements</span></span>  
  
|<span data-ttu-id="40150-136">要素</span><span class="sxs-lookup"><span data-stu-id="40150-136">Element</span></span>|<span data-ttu-id="40150-137">説明</span><span class="sxs-lookup"><span data-stu-id="40150-137">Description</span></span>|  
|-------------|-----------------|  
|\<netHttpBinding>|<span data-ttu-id="40150-138">NetHttpBinding を指定します。</span><span class="sxs-lookup"><span data-stu-id="40150-138">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="40150-139">例</span><span class="sxs-lookup"><span data-stu-id="40150-139">Example</span></span>  

 <span data-ttu-id="40150-140">\<webSocketSettings> 要素を使用する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="40150-140">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="40150-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="40150-141">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="40150-142">バインド</span><span class="sxs-lookup"><span data-stu-id="40150-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="40150-143">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="40150-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="40150-144">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="40150-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
