---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: fd7dc38e229b6135f91fc159596ed1669d43701a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228238"
---
# <a name="namedpipetransport"></a><span data-ttu-id="dd07b-101">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="dd07b-101">\<namedPipeTransport></span></span>
<span data-ttu-id="dd07b-102">チャネルがカスタム バインドに含まれているときに名前付きパイプを使用してメッセージを転送するトランスポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="dd07b-102">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="dd07b-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="dd07b-103">\<system.serviceModel></span></span>  
<span data-ttu-id="dd07b-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="dd07b-104">\<bindings></span></span>  
<span data-ttu-id="dd07b-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="dd07b-105">\<customBinding></span></span>  
<span data-ttu-id="dd07b-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="dd07b-106">\<binding></span></span>  
<span data-ttu-id="dd07b-107">\<namePipeTransport></span><span class="sxs-lookup"><span data-stu-id="dd07b-107">\<namePipeTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd07b-108">構文</span><span class="sxs-lookup"><span data-stu-id="dd07b-108">Syntax</span></span>  
  
```xml  
<namedPipeTransport channelInitializationTimeout="TimeSpan"
                    connectionBufferSize="Integer"
                    hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
                    manualAddressing="Boolean"
                    maxBufferPoolSize="Integer"
                    maxBufferSize="Integer"
                    maxOutputDelay="TimeSpan"
                    maxPendingAccepts="Integer"
                    maxPendingConnections="Integer"
                    maxReceivedMessageSize="Integer"
                    transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpopint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd07b-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="dd07b-109">Attributes and Elements</span></span>  
<span data-ttu-id="dd07b-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd07b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd07b-111">属性</span><span class="sxs-lookup"><span data-stu-id="dd07b-111">Attributes</span></span>  
<span data-ttu-id="dd07b-112">なし。</span><span class="sxs-lookup"><span data-stu-id="dd07b-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dd07b-113">子要素</span><span class="sxs-lookup"><span data-stu-id="dd07b-113">Child Elements</span></span>  
  
|<span data-ttu-id="dd07b-114">要素</span><span class="sxs-lookup"><span data-stu-id="dd07b-114">Element</span></span>|<span data-ttu-id="dd07b-115">説明</span><span class="sxs-lookup"><span data-stu-id="dd07b-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dd07b-116">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="dd07b-116">ChannelInitializationTimeout</span></span>|<span data-ttu-id="dd07b-117">取得または設定します、<xref:System.TimeSpan>チャネルができるの初期化ステータス切断されるまで最大時間を決定します。</span><span class="sxs-lookup"><span data-stu-id="dd07b-117">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="dd07b-118">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="dd07b-118">ConnectionBufferSize</span></span>|<span data-ttu-id="dd07b-119">クライアントまたサービスからネットワークでシリアル化されたメッセージのチャンクを転送するために使用されるバッファーのサイズを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="dd07b-119">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="dd07b-120">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="dd07b-120">hostNameComparisonMode</span></span>|<span data-ttu-id="dd07b-121">URI で一致する場合にサービスに到達するためにホスト名を使用するかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="dd07b-121">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="dd07b-122">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="dd07b-122">manualAddressing</span></span>|<span data-ttu-id="dd07b-123">メッセージの手動アドレス指定が必要かどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="dd07b-123">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="dd07b-124">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="dd07b-124">maxBufferPoolSize</span></span>|<span data-ttu-id="dd07b-125">取得またはトランスポートで使用するバッファー プールのバイト単位で最大のサイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="dd07b-125">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="dd07b-126">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="dd07b-126">maxBufferSize</span></span>|<span data-ttu-id="dd07b-127">使用するバッファーの最大サイズを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="dd07b-127">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="dd07b-128">ストリーム メッセージの場合、この値は少なくともメッセージ ヘッダーで使用できる最大サイズにする必要があります。これは、バッファー モードで読み取られます。</span><span class="sxs-lookup"><span data-stu-id="dd07b-128">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="dd07b-129">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="dd07b-129">maxOutputDelay</span></span>|<span data-ttu-id="dd07b-130">メッセージのチャンクまたは完全なメッセージを、送信前にメモリ内のバッファーに残したままにできる最長期間を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="dd07b-130">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="dd07b-131">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="dd07b-131">maxPendingAccepts</span></span>|<span data-ttu-id="dd07b-132">取得またはサービスは、サービスへの着信接続を処理するためのリスナーで待機できるチャネルの最大数を設定します。</span><span class="sxs-lookup"><span data-stu-id="dd07b-132">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="dd07b-133">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="dd07b-133">maxPendingConnections</span></span>|<span data-ttu-id="dd07b-134">サービスでディスパッチを待機している最大接続数を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="dd07b-134">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="dd07b-135">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="dd07b-135">maxReceivedMessageSize</span></span>|<span data-ttu-id="dd07b-136">取得し、受信できるをバイト単位で、メッセージの最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="dd07b-136">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="dd07b-137">transferMode</span><span class="sxs-lookup"><span data-stu-id="dd07b-137">transferMode</span></span>|<span data-ttu-id="dd07b-138">接続指向のトランスポートでメッセージをバッファーするか、ストリーム配信するかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="dd07b-138">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="dd07b-139">\<connectionPoolSettings > の\<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="dd07b-139">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|<span data-ttu-id="dd07b-140">名前付きパイプ バインディングの追加の接続プール設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd07b-140">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dd07b-141">親要素</span><span class="sxs-lookup"><span data-stu-id="dd07b-141">Parent Elements</span></span>  
  
|<span data-ttu-id="dd07b-142">要素</span><span class="sxs-lookup"><span data-stu-id="dd07b-142">Element</span></span>|<span data-ttu-id="dd07b-143">説明</span><span class="sxs-lookup"><span data-stu-id="dd07b-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd07b-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="dd07b-144">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="dd07b-145">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="dd07b-145">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd07b-146">Remarks</span><span class="sxs-lookup"><span data-stu-id="dd07b-146">Remarks</span></span>  
<span data-ttu-id="dd07b-147">このトランスポートは、"net.pipe://hostname/path" の形式の URI を使用します。</span><span class="sxs-lookup"><span data-stu-id="dd07b-147">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="dd07b-148">他の URI コンポーネントは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="dd07b-148">Other URI components are optional.</span></span>  
  
<span data-ttu-id="dd07b-149">`namedPipeTransport` 要素は、名前付きパイプ トランスポート プロトコルを実装するカスタム バインディングを作成する場合の開始点となります。</span><span class="sxs-lookup"><span data-stu-id="dd07b-149">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="dd07b-150">このトランスポートは、コンピューター上での WCF (Windows Communication Foundation) 間の通信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="dd07b-150">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd07b-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd07b-151">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="dd07b-152">トランスポート</span><span class="sxs-lookup"><span data-stu-id="dd07b-152">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="dd07b-153">トランスポートの選択</span><span class="sxs-lookup"><span data-stu-id="dd07b-153">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="dd07b-154">バインディング</span><span class="sxs-lookup"><span data-stu-id="dd07b-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="dd07b-155">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="dd07b-155">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="dd07b-156">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="dd07b-156">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="dd07b-157">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="dd07b-157">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
