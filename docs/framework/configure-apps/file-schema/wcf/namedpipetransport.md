---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: 00631ad88d771ed8f45638f28c84df05917fd3a0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736588"
---
# \<namedPipeTransport>
<span data-ttu-id="8d616-101">チャネルがカスタム バインドに含まれているときに名前付きパイプを使用してメッセージを転送するトランスポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="8d616-101">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedPipeTransport>**  
  
## <a name="syntax"></a><span data-ttu-id="8d616-102">構文</span><span class="sxs-lookup"><span data-stu-id="8d616-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d616-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8d616-103">Attributes and Elements</span></span>  
<span data-ttu-id="8d616-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d616-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d616-105">属性</span><span class="sxs-lookup"><span data-stu-id="8d616-105">Attributes</span></span>  
<span data-ttu-id="8d616-106">なし。</span><span class="sxs-lookup"><span data-stu-id="8d616-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8d616-107">子要素</span><span class="sxs-lookup"><span data-stu-id="8d616-107">Child Elements</span></span>  
  
|<span data-ttu-id="8d616-108">要素</span><span class="sxs-lookup"><span data-stu-id="8d616-108">Element</span></span>|<span data-ttu-id="8d616-109">説明</span><span class="sxs-lookup"><span data-stu-id="8d616-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8d616-110">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="8d616-110">ChannelInitializationTimeout</span></span>|<span data-ttu-id="8d616-111">接続が切断されるまでのチャネルの初期化ステータスの最大時間を決定する <xref:System.TimeSpan> を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="8d616-111">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="8d616-112">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="8d616-112">ConnectionBufferSize</span></span>|<span data-ttu-id="8d616-113">クライアントまたサービスからネットワークでシリアル化されたメッセージのチャンクを転送するために使用されるバッファーのサイズを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="8d616-113">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="8d616-114">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="8d616-114">hostNameComparisonMode</span></span>|<span data-ttu-id="8d616-115">URI で一致する場合にサービスに到達するためにホスト名を使用するかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="8d616-115">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="8d616-116">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="8d616-116">manualAddressing</span></span>|<span data-ttu-id="8d616-117">メッセージの手動アドレス指定が必要かどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="8d616-117">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="8d616-118">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="8d616-118">maxBufferPoolSize</span></span>|<span data-ttu-id="8d616-119">トランスポートが使用するバッファー プールの最大サイズ (バイト単位) を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="8d616-119">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="8d616-120">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="8d616-120">maxBufferSize</span></span>|<span data-ttu-id="8d616-121">使用するバッファーの最大サイズを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="8d616-121">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="8d616-122">ストリーム メッセージの場合、この値は少なくともメッセージ ヘッダーで使用できる最大サイズにする必要があります。これは、バッファー モードで読み取られます。</span><span class="sxs-lookup"><span data-stu-id="8d616-122">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="8d616-123">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="8d616-123">maxOutputDelay</span></span>|<span data-ttu-id="8d616-124">メッセージのチャンクまたは完全なメッセージを、送信前にメモリ内のバッファーに残したままにできる最長期間を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="8d616-124">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="8d616-125">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="8d616-125">maxPendingAccepts</span></span>|<span data-ttu-id="8d616-126">サービスへの受信接続を処理するためにサービスがリスナーで待機できるチャネルの最大数を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="8d616-126">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="8d616-127">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="8d616-127">maxPendingConnections</span></span>|<span data-ttu-id="8d616-128">サービスでディスパッチを待機している最大接続数を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="8d616-128">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="8d616-129">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="8d616-129">maxReceivedMessageSize</span></span>|<span data-ttu-id="8d616-130">受信できるメッセージの最大サイズをバイト単位で取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="8d616-130">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="8d616-131">transferMode</span><span class="sxs-lookup"><span data-stu-id="8d616-131">transferMode</span></span>|<span data-ttu-id="8d616-132">接続指向のトランスポートでメッセージをバッファーするか、ストリーム配信するかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="8d616-132">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="8d616-133">\<connectionPoolSettings>の\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="8d616-133">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](connectionpoolsettings.md)|<span data-ttu-id="8d616-134">名前付きパイプ バインディングの追加の接続プール設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d616-134">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8d616-135">親要素</span><span class="sxs-lookup"><span data-stu-id="8d616-135">Parent Elements</span></span>  
  
|<span data-ttu-id="8d616-136">要素</span><span class="sxs-lookup"><span data-stu-id="8d616-136">Element</span></span>|<span data-ttu-id="8d616-137">説明</span><span class="sxs-lookup"><span data-stu-id="8d616-137">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="8d616-138">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="8d616-138">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d616-139">解説</span><span class="sxs-lookup"><span data-stu-id="8d616-139">Remarks</span></span>  
<span data-ttu-id="8d616-140">このトランスポートは、"net.pipe://hostname/path" の形式の URI を使用します。</span><span class="sxs-lookup"><span data-stu-id="8d616-140">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="8d616-141">他の URI コンポーネントは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="8d616-141">Other URI components are optional.</span></span>  
  
<span data-ttu-id="8d616-142">`namedPipeTransport` 要素は、名前付きパイプ トランスポート プロトコルを実装するカスタム バインディングを作成する場合の開始点となります。</span><span class="sxs-lookup"><span data-stu-id="8d616-142">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="8d616-143">このトランスポートは、コンピューター上での WCF (Windows Communication Foundation) 間の通信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8d616-143">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d616-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d616-144">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="8d616-145">トランスポート</span><span class="sxs-lookup"><span data-stu-id="8d616-145">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="8d616-146">トランスポートの選択</span><span class="sxs-lookup"><span data-stu-id="8d616-146">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="8d616-147">バインド</span><span class="sxs-lookup"><span data-stu-id="8d616-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8d616-148">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="8d616-148">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="8d616-149">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="8d616-149">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
