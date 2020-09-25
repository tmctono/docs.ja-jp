---
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: 68832c3a5bd4cc423642a6272e70cbecab86d6a8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181545"
---
# \<peerTransport>

<span data-ttu-id="85e4d-101">カスタム バインドのピア トランスポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="85e4d-101">Defines a peer transport for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerTransport>**  
  
## <a name="syntax"></a><span data-ttu-id="85e4d-102">構文</span><span class="sxs-lookup"><span data-stu-id="85e4d-102">Syntax</span></span>  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85e4d-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="85e4d-103">Attributes and Elements</span></span>  

 <span data-ttu-id="85e4d-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="85e4d-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85e4d-105">属性</span><span class="sxs-lookup"><span data-stu-id="85e4d-105">Attributes</span></span>  
  
|<span data-ttu-id="85e4d-106">属性</span><span class="sxs-lookup"><span data-stu-id="85e4d-106">Attribute</span></span>|<span data-ttu-id="85e4d-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="85e4d-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="85e4d-108">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="85e4d-108">listenIpAddress</span></span>|<span data-ttu-id="85e4d-109">ピア ノードが TCP メッセージをリッスンする IP アドレスを指定する文字列です。</span><span class="sxs-lookup"><span data-stu-id="85e4d-109">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="85e4d-110">既定では、 `null`です。</span><span class="sxs-lookup"><span data-stu-id="85e4d-110">The default is `null`.</span></span>|  
|<span data-ttu-id="85e4d-111">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="85e4d-111">maxBufferPoolSize</span></span>|<span data-ttu-id="85e4d-112">バッファー プールの最大サイズを指定する正の整数です。</span><span class="sxs-lookup"><span data-stu-id="85e4d-112">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="85e4d-113">既定値は 524288 です。</span><span class="sxs-lookup"><span data-stu-id="85e4d-113">The default is 524288.</span></span><br /><br /> <span data-ttu-id="85e4d-114">WCF の多くの部分でバッファーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="85e4d-114">Many parts of WCF use buffers.</span></span> <span data-ttu-id="85e4d-115">使用するたびに毎回バッファーを作成および破壊すると負荷が高くなります。バッファーのガベージ コレクションも同様です。</span><span class="sxs-lookup"><span data-stu-id="85e4d-115">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="85e4d-116">バッファー プールを使用すると、バッファーをプールから取得して使用し、作業が終わったらプールに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="85e4d-116">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="85e4d-117">これで、バッファーの作成と破棄のオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="85e4d-117">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="85e4d-118">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="85e4d-118">maxReceivedMessageSize</span></span>|<span data-ttu-id="85e4d-119">ヘッダーなどのメッセージの最大サイズ (バイト単位) を定義する正の整数。</span><span class="sxs-lookup"><span data-stu-id="85e4d-119">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="85e4d-120">受信側にとってメッセージが大きすぎると、メッセージの送信側は SOAP エラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="85e4d-120">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="85e4d-121">メッセージは受信者によってドロップされ、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="85e4d-121">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="85e4d-122">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="85e4d-122">The default is 65536.</span></span>|  
|<span data-ttu-id="85e4d-123">port</span><span class="sxs-lookup"><span data-stu-id="85e4d-123">port</span></span>|<span data-ttu-id="85e4d-124">このバインディングがピア チャネルの TCP メッセージを処理するネットワーク インターフェイス ポートを指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="85e4d-124">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="85e4d-125">この値の有効値の範囲は <xref:System.Net.IPEndPoint.MinPort> ～ <xref:System.Net.IPEndPoint.MaxPort> です。</span><span class="sxs-lookup"><span data-stu-id="85e4d-125">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="85e4d-126">既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="85e4d-126">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85e4d-127">子要素</span><span class="sxs-lookup"><span data-stu-id="85e4d-127">Child Elements</span></span>  
  
|<span data-ttu-id="85e4d-128">要素</span><span class="sxs-lookup"><span data-stu-id="85e4d-128">Element</span></span>|<span data-ttu-id="85e4d-129">説明</span><span class="sxs-lookup"><span data-stu-id="85e4d-129">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-peertransport.md)|<span data-ttu-id="85e4d-130">このトランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="85e4d-130">Defines the security settings for this transport.</span></span> <span data-ttu-id="85e4d-131">この要素は <xref:System.ServiceModel.Configuration.PeerSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="85e4d-131">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="85e4d-132">親要素</span><span class="sxs-lookup"><span data-stu-id="85e4d-132">Parent Elements</span></span>  
  
|<span data-ttu-id="85e4d-133">要素</span><span class="sxs-lookup"><span data-stu-id="85e4d-133">Element</span></span>|<span data-ttu-id="85e4d-134">説明</span><span class="sxs-lookup"><span data-stu-id="85e4d-134">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="85e4d-135">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="85e4d-135">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85e4d-136">解説</span><span class="sxs-lookup"><span data-stu-id="85e4d-136">Remarks</span></span>  

 <span data-ttu-id="85e4d-137">このトランスポートは、要求/応答操作を含むコントラクトと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="85e4d-137">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85e4d-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="85e4d-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="85e4d-139">トランスポート</span><span class="sxs-lookup"><span data-stu-id="85e4d-139">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="85e4d-140">トランスポートの選択</span><span class="sxs-lookup"><span data-stu-id="85e4d-140">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="85e4d-141">バインド</span><span class="sxs-lookup"><span data-stu-id="85e4d-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="85e4d-142">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="85e4d-142">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="85e4d-143">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="85e4d-143">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
