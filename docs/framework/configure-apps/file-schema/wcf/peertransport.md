---
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: 6765259f290047a4199a422b4ad0cced2ffee9ae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179830"
---
# <a name="peertransport"></a><span data-ttu-id="ccc72-101">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="ccc72-101">\<peerTransport></span></span>
<span data-ttu-id="ccc72-102">カスタム バインドのピア トランスポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-102">Defines a peer transport for a custom binding.</span></span>  
  
 <span data-ttu-id="ccc72-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ccc72-103">\<system.serviceModel></span></span>  
<span data-ttu-id="ccc72-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ccc72-104">\<bindings></span></span>  
<span data-ttu-id="ccc72-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ccc72-105">\<customBinding></span></span>  
<span data-ttu-id="ccc72-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="ccc72-106">\<binding></span></span>  
<span data-ttu-id="ccc72-107">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="ccc72-107">\<peerTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccc72-108">構文</span><span class="sxs-lookup"><span data-stu-id="ccc72-108">Syntax</span></span>  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ccc72-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ccc72-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ccc72-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ccc72-111">属性</span><span class="sxs-lookup"><span data-stu-id="ccc72-111">Attributes</span></span>  
  
|<span data-ttu-id="ccc72-112">属性</span><span class="sxs-lookup"><span data-stu-id="ccc72-112">Attribute</span></span>|<span data-ttu-id="ccc72-113">説明</span><span class="sxs-lookup"><span data-stu-id="ccc72-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ccc72-114">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="ccc72-114">listenIpAddress</span></span>|<span data-ttu-id="ccc72-115">ピア ノードが TCP メッセージをリッスンする IP アドレスを指定する文字列です。</span><span class="sxs-lookup"><span data-stu-id="ccc72-115">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="ccc72-116">既定値は、`null` です。</span><span class="sxs-lookup"><span data-stu-id="ccc72-116">The default is `null`.</span></span>|  
|<span data-ttu-id="ccc72-117">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="ccc72-117">maxBufferPoolSize</span></span>|<span data-ttu-id="ccc72-118">バッファー プールの最大サイズを指定する正の整数です。</span><span class="sxs-lookup"><span data-stu-id="ccc72-118">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="ccc72-119">既定値は 524288 です。</span><span class="sxs-lookup"><span data-stu-id="ccc72-119">The default is 524288.</span></span><br /><br /> <span data-ttu-id="ccc72-120">WCF の多くの部分でバッファーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-120">Many parts of WCF use buffers.</span></span> <span data-ttu-id="ccc72-121">使用するたびに毎回バッファーを作成および破壊すると負荷が高くなります。バッファーのガベージ コレクションも同様です。</span><span class="sxs-lookup"><span data-stu-id="ccc72-121">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="ccc72-122">バッファー プールを使用すると、バッファーをプールから取得して使用し、作業が終わったらプールに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-122">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="ccc72-123">これで、バッファーの作成と破棄のオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-123">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="ccc72-124">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="ccc72-124">maxReceivedMessageSize</span></span>|<span data-ttu-id="ccc72-125">ヘッダーなどのメッセージの最大サイズ (バイト単位) を定義する正の整数。</span><span class="sxs-lookup"><span data-stu-id="ccc72-125">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="ccc72-126">受信側にとってメッセージが大きすぎると、メッセージの送信側は SOAP エラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ccc72-126">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="ccc72-127">メッセージは受信者によってドロップされ、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-127">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="ccc72-128">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="ccc72-128">The default is 65536.</span></span>|  
|<span data-ttu-id="ccc72-129">ポート</span><span class="sxs-lookup"><span data-stu-id="ccc72-129">port</span></span>|<span data-ttu-id="ccc72-130">このバインディングがピア チャネルの TCP メッセージを処理するネットワーク インターフェイス ポートを指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="ccc72-130">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="ccc72-131">この値の有効値の範囲は <xref:System.Net.IPEndPoint.MinPort> ～ <xref:System.Net.IPEndPoint.MaxPort> です。</span><span class="sxs-lookup"><span data-stu-id="ccc72-131">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="ccc72-132">既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="ccc72-132">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ccc72-133">子要素</span><span class="sxs-lookup"><span data-stu-id="ccc72-133">Child Elements</span></span>  
  
|<span data-ttu-id="ccc72-134">要素</span><span class="sxs-lookup"><span data-stu-id="ccc72-134">Element</span></span>|<span data-ttu-id="ccc72-135">説明</span><span class="sxs-lookup"><span data-stu-id="ccc72-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ccc72-136">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="ccc72-136">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="ccc72-137">このトランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-137">Defines the security settings for this transport.</span></span> <span data-ttu-id="ccc72-138">この要素は <xref:System.ServiceModel.Configuration.PeerSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="ccc72-138">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ccc72-139">親要素</span><span class="sxs-lookup"><span data-stu-id="ccc72-139">Parent Elements</span></span>  
  
|<span data-ttu-id="ccc72-140">要素</span><span class="sxs-lookup"><span data-stu-id="ccc72-140">Element</span></span>|<span data-ttu-id="ccc72-141">説明</span><span class="sxs-lookup"><span data-stu-id="ccc72-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ccc72-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="ccc72-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="ccc72-143">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-143">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccc72-144">Remarks</span><span class="sxs-lookup"><span data-stu-id="ccc72-144">Remarks</span></span>  
 <span data-ttu-id="ccc72-145">このトランスポートは、要求/応答操作を含むコントラクトと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="ccc72-145">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccc72-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="ccc72-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ccc72-147">トランスポート</span><span class="sxs-lookup"><span data-stu-id="ccc72-147">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="ccc72-148">トランスポートの選択</span><span class="sxs-lookup"><span data-stu-id="ccc72-148">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="ccc72-149">バインディング</span><span class="sxs-lookup"><span data-stu-id="ccc72-149">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="ccc72-150">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="ccc72-150">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ccc72-151">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="ccc72-151">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="ccc72-152">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ccc72-152">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
