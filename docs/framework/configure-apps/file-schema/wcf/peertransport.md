---
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: 1ad05fd9125ecc8b3d5797e0dd335adbf808db84
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933844"
---
# <a name="peertransport"></a><span data-ttu-id="4c028-101">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="4c028-101">\<peerTransport></span></span>
<span data-ttu-id="4c028-102">カスタム バインドのピア トランスポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="4c028-102">Defines a peer transport for a custom binding.</span></span>  
  
 <span data-ttu-id="4c028-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4c028-103">\<system.serviceModel></span></span>  
<span data-ttu-id="4c028-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="4c028-104">\<bindings></span></span>  
<span data-ttu-id="4c028-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4c028-105">\<customBinding></span></span>  
<span data-ttu-id="4c028-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="4c028-106">\<binding></span></span>  
<span data-ttu-id="4c028-107">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="4c028-107">\<peerTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c028-108">構文</span><span class="sxs-lookup"><span data-stu-id="4c028-108">Syntax</span></span>  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c028-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4c028-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4c028-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c028-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c028-111">属性</span><span class="sxs-lookup"><span data-stu-id="4c028-111">Attributes</span></span>  
  
|<span data-ttu-id="4c028-112">属性</span><span class="sxs-lookup"><span data-stu-id="4c028-112">Attribute</span></span>|<span data-ttu-id="4c028-113">説明</span><span class="sxs-lookup"><span data-stu-id="4c028-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4c028-114">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="4c028-114">listenIpAddress</span></span>|<span data-ttu-id="4c028-115">ピア ノードが TCP メッセージをリッスンする IP アドレスを指定する文字列です。</span><span class="sxs-lookup"><span data-stu-id="4c028-115">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="4c028-116">既定値は、`null` です。</span><span class="sxs-lookup"><span data-stu-id="4c028-116">The default is `null`.</span></span>|  
|<span data-ttu-id="4c028-117">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="4c028-117">maxBufferPoolSize</span></span>|<span data-ttu-id="4c028-118">バッファー プールの最大サイズを指定する正の整数です。</span><span class="sxs-lookup"><span data-stu-id="4c028-118">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="4c028-119">既定値は 524288 です。</span><span class="sxs-lookup"><span data-stu-id="4c028-119">The default is 524288.</span></span><br /><br /> <span data-ttu-id="4c028-120">WCF の多くの部分でバッファーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="4c028-120">Many parts of WCF use buffers.</span></span> <span data-ttu-id="4c028-121">使用するたびに毎回バッファーを作成および破壊すると負荷が高くなります。バッファーのガベージ コレクションも同様です。</span><span class="sxs-lookup"><span data-stu-id="4c028-121">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="4c028-122">バッファー プールを使用すると、バッファーをプールから取得して使用し、作業が終わったらプールに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="4c028-122">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="4c028-123">これで、バッファーの作成と破棄のオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="4c028-123">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="4c028-124">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="4c028-124">maxReceivedMessageSize</span></span>|<span data-ttu-id="4c028-125">ヘッダーなどのメッセージの最大サイズ (バイト単位) を定義する正の整数。</span><span class="sxs-lookup"><span data-stu-id="4c028-125">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="4c028-126">受信側にとってメッセージが大きすぎると、メッセージの送信側は SOAP エラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="4c028-126">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="4c028-127">メッセージは受信者によってドロップされ、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4c028-127">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="4c028-128">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="4c028-128">The default is 65536.</span></span>|  
|<span data-ttu-id="4c028-129">ポート</span><span class="sxs-lookup"><span data-stu-id="4c028-129">port</span></span>|<span data-ttu-id="4c028-130">このバインディングがピア チャネルの TCP メッセージを処理するネットワーク インターフェイス ポートを指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="4c028-130">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="4c028-131">この値の有効値の範囲は <xref:System.Net.IPEndPoint.MinPort> ～ <xref:System.Net.IPEndPoint.MaxPort> です。</span><span class="sxs-lookup"><span data-stu-id="4c028-131">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="4c028-132">既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="4c028-132">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c028-133">子要素</span><span class="sxs-lookup"><span data-stu-id="4c028-133">Child Elements</span></span>  
  
|<span data-ttu-id="4c028-134">要素</span><span class="sxs-lookup"><span data-stu-id="4c028-134">Element</span></span>|<span data-ttu-id="4c028-135">説明</span><span class="sxs-lookup"><span data-stu-id="4c028-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c028-136">\<security></span><span class="sxs-lookup"><span data-stu-id="4c028-136">\<security></span></span>](security-of-peertransport.md)|<span data-ttu-id="4c028-137">このトランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="4c028-137">Defines the security settings for this transport.</span></span> <span data-ttu-id="4c028-138">この要素は <xref:System.ServiceModel.Configuration.PeerSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="4c028-138">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4c028-139">親要素</span><span class="sxs-lookup"><span data-stu-id="4c028-139">Parent Elements</span></span>  
  
|<span data-ttu-id="4c028-140">要素</span><span class="sxs-lookup"><span data-stu-id="4c028-140">Element</span></span>|<span data-ttu-id="4c028-141">説明</span><span class="sxs-lookup"><span data-stu-id="4c028-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c028-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="4c028-142">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="4c028-143">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="4c028-143">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c028-144">Remarks</span><span class="sxs-lookup"><span data-stu-id="4c028-144">Remarks</span></span>  
 <span data-ttu-id="4c028-145">このトランスポートは、要求/応答操作を含むコントラクトと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4c028-145">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c028-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c028-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="4c028-147">トランスポート</span><span class="sxs-lookup"><span data-stu-id="4c028-147">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="4c028-148">トランスポートの選択</span><span class="sxs-lookup"><span data-stu-id="4c028-148">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="4c028-149">バインディング</span><span class="sxs-lookup"><span data-stu-id="4c028-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4c028-150">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="4c028-150">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4c028-151">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="4c028-151">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="4c028-152">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4c028-152">\<customBinding></span></span>](custombinding.md)
