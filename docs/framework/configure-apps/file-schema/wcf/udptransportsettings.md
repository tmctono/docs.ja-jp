---
title: <udpTransportSettings>
ms.date: 03/30/2017
ms.assetid: 842d92e9-6199-4ec5-b2d1-58533054e1f0
ms.openlocfilehash: bb2ec84caa79f33e1e469592d0eca63d8f461dac
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854863"
---
# \<udpTransportSettings>
<span data-ttu-id="e6a74-101">この構成要素は、の UDP トランスポート設定を公開 [\<udpDiscoveryEndpoint>](udpdiscoveryendpoint.md) します。</span><span class="sxs-lookup"><span data-stu-id="e6a74-101">This configuration element exposes UDP transport settings for [\<udpDiscoveryEndpoint>](udpdiscoveryendpoint.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<udpDiscoveryEndpoint>**](udpdiscoveryendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<updTransportSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="e6a74-102">構文</span><span class="sxs-lookup"><span data-stu-id="e6a74-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint>
        <updTransportSettings duplicateMessageHistoryLength="Integer"
                              maxBufferPoolSize="Integer"
                              maxMulticastRetransmitCount="Integer"
                              maxPendingMessageCount="Integer"
                              maxReceivedMessageSize="Integer"
                              maxUnicastRetransmitCount="Integer"
                              multicastInterfaceId="String"
                              socketReceiveBufferSize="Integer"
                              timeToLive="Integer" />
      </standardEndpoint>
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6a74-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e6a74-103">Attributes and Elements</span></span>  
 <span data-ttu-id="e6a74-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6a74-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6a74-105">属性</span><span class="sxs-lookup"><span data-stu-id="e6a74-105">Attributes</span></span>  
  
|<span data-ttu-id="e6a74-106">属性</span><span class="sxs-lookup"><span data-stu-id="e6a74-106">Attribute</span></span>|<span data-ttu-id="e6a74-107">説明</span><span class="sxs-lookup"><span data-stu-id="e6a74-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e6a74-108">duplicateMessageHistoryLength</span><span class="sxs-lookup"><span data-stu-id="e6a74-108">duplicateMessageHistoryLength</span></span>|<span data-ttu-id="e6a74-109">重複するメッセージを特定するためにトランスポートによって使用されるメッセージ ハッシュの最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="e6a74-109">An integer that specifies the maximum number of message hashes used by the transport for identifying duplicate messages.</span></span>  <span data-ttu-id="e6a74-110">重複の検出は、TransportManager レベルで実行されます。</span><span class="sxs-lookup"><span data-stu-id="e6a74-110">Duplicate detection will be done at the TransportManager level.</span></span> <span data-ttu-id="e6a74-111">このプロパティを 0 に設定すると、重複の検出は無効になります。</span><span class="sxs-lookup"><span data-stu-id="e6a74-111">Setting this property to 0 disables duplicate detection.</span></span><br /><br /> <span data-ttu-id="e6a74-112">この属性を使用して、システムの管理者や開発者は重複するメッセージの検出アルゴリズムをオフにできます。</span><span class="sxs-lookup"><span data-stu-id="e6a74-112">This attribute allows system administrators or developers to turn off duplicate message detection algorithms.</span></span> <span data-ttu-id="e6a74-113">これは、独自の重複検出アルゴリズムを実行する場合に望ましいことがあります。</span><span class="sxs-lookup"><span data-stu-id="e6a74-113">This may be desirable if you want to implement your own duplicate detection algorithm.</span></span><br /><br /> <span data-ttu-id="e6a74-114">既定値は 4112 です。</span><span class="sxs-lookup"><span data-stu-id="e6a74-114">The default is 4112.</span></span>|  
|<span data-ttu-id="e6a74-115">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="e6a74-115">maxBufferPoolSize</span></span>|<span data-ttu-id="e6a74-116">トランスポートによって使用されるバッファー プールの最大サイズを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="e6a74-116">An integer that specifies the maximum size of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="e6a74-117">maxMulticastRetransmitCount</span><span class="sxs-lookup"><span data-stu-id="e6a74-117">maxMulticastRetransmitCount</span></span>|<span data-ttu-id="e6a74-118">メッセージを (最初に送信した後に) 再送信する最大回数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="e6a74-118">An integer that specifies the maximum number of times the message should be retransmitted (in addition to the first send).</span></span><br /><br /> <span data-ttu-id="e6a74-119">既定値は 2 です。</span><span class="sxs-lookup"><span data-stu-id="e6a74-119">The default is 2.</span></span>|  
|<span data-ttu-id="e6a74-120">maxPendingMessageCount</span><span class="sxs-lookup"><span data-stu-id="e6a74-120">maxPendingMessageCount</span></span>|<span data-ttu-id="e6a74-121">受信して、各チャネル インスタンスの InputQueue からまだ削除していないメッセージの最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="e6a74-121">An integer that specifies the maximum number of messages that have been received but not yet removed from the InputQueue for an individual channel instance.</span></span>  <span data-ttu-id="e6a74-122">InputQueue が保留メッセージ数の上限に達すると、メッセージは削除されます。</span><span class="sxs-lookup"><span data-stu-id="e6a74-122">If the InputQueue has hit its pending message count limit, the message will be dropped.</span></span><br /><br /> <span data-ttu-id="e6a74-123">既定値は 32 です。</span><span class="sxs-lookup"><span data-stu-id="e6a74-123">The default is 32.</span></span>|  
|<span data-ttu-id="e6a74-124">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="e6a74-124">maxReceivedMessageSize</span></span>|<span data-ttu-id="e6a74-125">バインディングで処理できるメッセージの最大サイズを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="e6a74-125">An integer that specifies the maximum size for a message that can be processed by the binding.</span></span><br /><br /> <span data-ttu-id="e6a74-126">既定値は 65507 です。</span><span class="sxs-lookup"><span data-stu-id="e6a74-126">The default value is 65507.</span></span>|  
|<span data-ttu-id="e6a74-127">maxUnicastRetransmitCount</span><span class="sxs-lookup"><span data-stu-id="e6a74-127">maxUnicastRetransmitCount</span></span>|<span data-ttu-id="e6a74-128">メッセージを (最初に送信した後に) 再送信する最大回数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="e6a74-128">An integer that specifies the maximum number of times the message should be retransmitted (in addition to the first send).</span></span>  <span data-ttu-id="e6a74-129">メッセージをユニキャスト アドレスに送信し、対応する RelatesTo ヘッダーの付いた応答メッセージを受信すると、再送信は早期に (再送信の回数が構成された回数に到達する前に) 終了することがあります。</span><span class="sxs-lookup"><span data-stu-id="e6a74-129">If the message is sent to a unicast address and a response message is received with a corresponding RelatesTo header, then retransmission may terminate early (before retransmitting the configured number of times).</span></span><br /><br /> <span data-ttu-id="e6a74-130">既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="e6a74-130">The default value is 1.</span></span>|  
|<span data-ttu-id="e6a74-131">multicastInterfaceId</span><span class="sxs-lookup"><span data-stu-id="e6a74-131">multicastInterfaceId</span></span>|<span data-ttu-id="e6a74-132">マルチホーム コンピューター上でマルチキャスト トラフィックを送受信するときに使用するネットワーク アダプターを一意に識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="e6a74-132">A string that uniquely identifies the network adapter that should be used when sending and receiving multicast traffic on multi-homed machines.</span></span> <span data-ttu-id="e6a74-133">実行時には、トランスポートは、この属性値を使用してインターフェイスのインデックスを参照します。このインデックスは、その後、`IP_MULTICAST_IF` および `IPV6_MULTICAST_IF` のソケット オプションの設定に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e6a74-133">At runtime, the transport will use this attribute value to lookup the interface index, which is then used to set the `IP_MULTICAST_IF` and `IPV6_MULTICAST_IF` socket options.</span></span>  <span data-ttu-id="e6a74-134">マルチキャスト グループに参加するときには、同じインターフェイス インデックスが使用されます (該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="e6a74-134">The same interface index will be used when joining a multicast group, if applicable.</span></span><br /><br /> <span data-ttu-id="e6a74-135">既定値は `null` です。</span><span class="sxs-lookup"><span data-stu-id="e6a74-135">The default value is `null`.</span></span>|  
|<span data-ttu-id="e6a74-136">socketReceiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="e6a74-136">socketReceiveBufferSize</span></span>|<span data-ttu-id="e6a74-137">基になる WinSock ソケットの受信バッファー サイズを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="e6a74-137">An integer that specifies the receive buffer size on the underlying WinSock socket.</span></span><br /><br /> <span data-ttu-id="e6a74-138">受信チャネルのユーザーは、バインディング上のこの属性を使用して、データ受信時のシステム動作を制御できます。</span><span class="sxs-lookup"><span data-stu-id="e6a74-138">A user of a receiving channel can use this attribute on the Binding to control how the system behaves when it receives data.</span></span>  <span data-ttu-id="e6a74-139">たとえば、受信 WCF メッセージを最大しきい値で利用するアプリケーションがある場合、この属性値よりも大きい値を使用すると、アプリケーションが処理できるようになるまで待機している間、メッセージを WinSock バッファーにスタックできます。</span><span class="sxs-lookup"><span data-stu-id="e6a74-139">For example, given an application that is consuming inbound WCF messages at the maximum threshold, using a higher value for this attribute would allow messages to stack up in the WinSock buffer while waiting for the application to be able to process them.</span></span>  <span data-ttu-id="e6a74-140">同じ状況で低い値を使用すると、メッセージが破棄される原因となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e6a74-140">Using a lower value in the same situation would result in messages getting dropped.</span></span> <span data-ttu-id="e6a74-141">この属性は、基になる WinSock ソケットオプションを公開し `SO_RCVBUF` ます。この属性値は、以上のサイズである必要があり `maxReceivedMessageSize` ます。</span><span class="sxs-lookup"><span data-stu-id="e6a74-141">This attribute exposes the underlying WinSock `SO_RCVBUF` socket option.This attribute value must be at least the size of `maxReceivedMessageSize`.</span></span>   <span data-ttu-id="e6a74-142">これをより小さい値に設定する `maxReceivedMessageSize` と、ランタイム例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="e6a74-142">Setting it to a value smaller than the `maxReceivedMessageSize` will result in a runtime exception.</span></span><br /><br /> <span data-ttu-id="e6a74-143">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="e6a74-143">The default value is 65536.</span></span>|  
|<span data-ttu-id="e6a74-144">timeToLive</span><span class="sxs-lookup"><span data-stu-id="e6a74-144">timeToLive</span></span>|<span data-ttu-id="e6a74-145">マルチキャスト パケットが走査できるネットワーク セグメント ホップの数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="e6a74-145">An integer that specifies the number of network segment hops that a multicast packet can traverse.</span></span>  <span data-ttu-id="e6a74-146">この属性は、`IP_MULTICAST_TTL` および `IP_TTL` ソケット オプションに関連付けられている機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="e6a74-146">This attribute exposes the functionality associated with the `IP_MULTICAST_TTL` and `IP_TTL` socket options.</span></span><br /><br /> <span data-ttu-id="e6a74-147">既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="e6a74-147">The default value is 1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e6a74-148">子要素</span><span class="sxs-lookup"><span data-stu-id="e6a74-148">Child Elements</span></span>  
 <span data-ttu-id="e6a74-149">なし。</span><span class="sxs-lookup"><span data-stu-id="e6a74-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e6a74-150">親要素</span><span class="sxs-lookup"><span data-stu-id="e6a74-150">Parent Elements</span></span>  
  
|<span data-ttu-id="e6a74-151">要素</span><span class="sxs-lookup"><span data-stu-id="e6a74-151">Element</span></span>|<span data-ttu-id="e6a74-152">Description</span><span class="sxs-lookup"><span data-stu-id="e6a74-152">Description</span></span>|  
|-------------|-----------------|  
|[\<udpDiscoveryEndpoint>](udpdiscoveryendpoint.md)|<span data-ttu-id="e6a74-153">固定探索コントラクトと UDP トランスポート バインディングを持つ標準エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="e6a74-153">A standard endpoint that has fixed discovery contract and UDP transport binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e6a74-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6a74-154">See also</span></span>

- <xref:System.ServiceModel.Discovery.UdpTransportSettings>
