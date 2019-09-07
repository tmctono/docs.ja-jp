---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: e5f1d49e0e3bb5f52c5e18577d556d25539434a9
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400162"
---
# <a name="namedpipetransport"></a><span data-ttu-id="99171-101">\<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="99171-101">\<namedPipeTransport></span></span>
<span data-ttu-id="99171-102">チャネルがカスタム バインドに含まれているときに名前付きパイプを使用してメッセージを転送するトランスポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="99171-102">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="99171-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="99171-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="99171-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="99171-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="99171-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="99171-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="99171-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="99171-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="99171-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="99171-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="99171-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<namedPipeTransport >**</span><span class="sxs-lookup"><span data-stu-id="99171-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedPipeTransport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99171-109">構文</span><span class="sxs-lookup"><span data-stu-id="99171-109">Syntax</span></span>  
  
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
                          maxOutboundConnectionsPerEndpoint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99171-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="99171-110">Attributes and Elements</span></span>  
<span data-ttu-id="99171-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="99171-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99171-112">属性</span><span class="sxs-lookup"><span data-stu-id="99171-112">Attributes</span></span>  
<span data-ttu-id="99171-113">なし。</span><span class="sxs-lookup"><span data-stu-id="99171-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="99171-114">子要素</span><span class="sxs-lookup"><span data-stu-id="99171-114">Child Elements</span></span>  
  
|<span data-ttu-id="99171-115">要素</span><span class="sxs-lookup"><span data-stu-id="99171-115">Element</span></span>|<span data-ttu-id="99171-116">説明</span><span class="sxs-lookup"><span data-stu-id="99171-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="99171-117">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="99171-117">ChannelInitializationTimeout</span></span>|<span data-ttu-id="99171-118">チャネルが切断さ<xref:System.TimeSpan>れるまでの初期化ステータスの最大時間を決定するを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="99171-118">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="99171-119">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="99171-119">ConnectionBufferSize</span></span>|<span data-ttu-id="99171-120">クライアントまたサービスからネットワークでシリアル化されたメッセージのチャンクを転送するために使用されるバッファーのサイズを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="99171-120">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="99171-121">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="99171-121">hostNameComparisonMode</span></span>|<span data-ttu-id="99171-122">URI で一致する場合にサービスに到達するためにホスト名を使用するかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="99171-122">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="99171-123">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="99171-123">manualAddressing</span></span>|<span data-ttu-id="99171-124">メッセージの手動アドレス指定が必要かどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="99171-124">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="99171-125">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="99171-125">maxBufferPoolSize</span></span>|<span data-ttu-id="99171-126">トランスポートで使用されるバッファープールの最大サイズ (バイト単位) を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="99171-126">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="99171-127">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="99171-127">maxBufferSize</span></span>|<span data-ttu-id="99171-128">使用するバッファーの最大サイズを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="99171-128">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="99171-129">ストリーム メッセージの場合、この値は少なくともメッセージ ヘッダーで使用できる最大サイズにする必要があります。これは、バッファー モードで読み取られます。</span><span class="sxs-lookup"><span data-stu-id="99171-129">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="99171-130">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="99171-130">maxOutputDelay</span></span>|<span data-ttu-id="99171-131">メッセージのチャンクまたは完全なメッセージを、送信前にメモリ内のバッファーに残したままにできる最長期間を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="99171-131">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="99171-132">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="99171-132">maxPendingAccepts</span></span>|<span data-ttu-id="99171-133">サービスがサービスへの着信接続を処理するためにリスナーで待機できるチャネルの最大数を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="99171-133">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="99171-134">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="99171-134">maxPendingConnections</span></span>|<span data-ttu-id="99171-135">サービスでディスパッチを待機している最大接続数を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="99171-135">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="99171-136">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="99171-136">maxReceivedMessageSize</span></span>|<span data-ttu-id="99171-137">受信できるメッセージの最大サイズをバイト単位で取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="99171-137">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="99171-138">transferMode</span><span class="sxs-lookup"><span data-stu-id="99171-138">transferMode</span></span>|<span data-ttu-id="99171-139">接続指向のトランスポートでメッセージをバッファーするか、ストリーム配信するかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="99171-139">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="99171-140">\<namedPipeTransport > の\<connectionpoolsettings ></span><span class="sxs-lookup"><span data-stu-id="99171-140">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](connectionpoolsettings.md)|<span data-ttu-id="99171-141">名前付きパイプ バインディングの追加の接続プール設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="99171-141">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="99171-142">親要素</span><span class="sxs-lookup"><span data-stu-id="99171-142">Parent Elements</span></span>  
  
|<span data-ttu-id="99171-143">要素</span><span class="sxs-lookup"><span data-stu-id="99171-143">Element</span></span>|<span data-ttu-id="99171-144">説明</span><span class="sxs-lookup"><span data-stu-id="99171-144">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99171-145">\<binding></span><span class="sxs-lookup"><span data-stu-id="99171-145">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="99171-146">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="99171-146">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99171-147">Remarks</span><span class="sxs-lookup"><span data-stu-id="99171-147">Remarks</span></span>  
<span data-ttu-id="99171-148">このトランスポートは、"net.pipe://hostname/path" の形式の URI を使用します。</span><span class="sxs-lookup"><span data-stu-id="99171-148">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="99171-149">他の URI コンポーネントは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="99171-149">Other URI components are optional.</span></span>  
  
<span data-ttu-id="99171-150">`namedPipeTransport` 要素は、名前付きパイプ トランスポート プロトコルを実装するカスタム バインディングを作成する場合の開始点となります。</span><span class="sxs-lookup"><span data-stu-id="99171-150">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="99171-151">このトランスポートは、コンピューター上での WCF (Windows Communication Foundation) 間の通信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="99171-151">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99171-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="99171-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="99171-153">トランスポート</span><span class="sxs-lookup"><span data-stu-id="99171-153">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="99171-154">トランスポートの選択</span><span class="sxs-lookup"><span data-stu-id="99171-154">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="99171-155">バインディング</span><span class="sxs-lookup"><span data-stu-id="99171-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="99171-156">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="99171-156">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="99171-157">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="99171-157">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="99171-158">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="99171-158">\<customBinding></span></span>](custombinding.md)
