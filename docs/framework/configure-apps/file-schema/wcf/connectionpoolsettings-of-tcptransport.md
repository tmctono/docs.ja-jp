---
title: <connectionPoolSettings> の <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: f9b0fff741c32c1a3d6f9461f478e89acc18114e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398098"
---
# <a name="connectionpoolsettings-of-tcptransport"></a><span data-ttu-id="7a29e-102">\<tcptransport > の\<connectionpoolsettings ></span><span class="sxs-lookup"><span data-stu-id="7a29e-102">\<connectionPoolSettings> of \<tcpTransport></span></span>
<span data-ttu-id="7a29e-103">TCP トランスポートの追加の接続プール設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="7a29e-103">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
<span data-ttu-id="7a29e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7a29e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7a29e-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7a29e-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7a29e-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="7a29e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="7a29e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="7a29e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="7a29e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="7a29e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="7a29e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<tcpTransport >** ](tcptransport.md)</span><span class="sxs-lookup"><span data-stu-id="7a29e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tcpTransport>**](tcptransport.md)</span></span>\
<span data-ttu-id="7a29e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<connectionPoolSettings >**</span><span class="sxs-lookup"><span data-stu-id="7a29e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a29e-111">構文</span><span class="sxs-lookup"><span data-stu-id="7a29e-111">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a29e-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7a29e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7a29e-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a29e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a29e-114">属性</span><span class="sxs-lookup"><span data-stu-id="7a29e-114">Attributes</span></span>  
  
|<span data-ttu-id="7a29e-115">属性</span><span class="sxs-lookup"><span data-stu-id="7a29e-115">Attribute</span></span>|<span data-ttu-id="7a29e-116">説明</span><span class="sxs-lookup"><span data-stu-id="7a29e-116">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="7a29e-117">送信チャネルに使用される接続プールの名前を定義する文字列です。</span><span class="sxs-lookup"><span data-stu-id="7a29e-117">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="7a29e-118">ストリーム配信モードでは、接続が共有されません。したがって、接続プールは無効です。</span><span class="sxs-lookup"><span data-stu-id="7a29e-118">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="7a29e-119">既定は、"default" 文字列です。</span><span class="sxs-lookup"><span data-stu-id="7a29e-119">The default is a "default" string.</span></span> <span data-ttu-id="7a29e-120">この値を変更して、特定のクライアントの接続を、個別のグループに分離できます。</span><span class="sxs-lookup"><span data-stu-id="7a29e-120">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="7a29e-121">接続が切断されるまでの最大アイドル時間を指定する正の <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="7a29e-121">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="7a29e-122">既定値は 00:02:00 です。</span><span class="sxs-lookup"><span data-stu-id="7a29e-122">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="7a29e-123">アクティブな接続が終了されるまでの時間を指定する <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="7a29e-123">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="7a29e-124">既定値は 00:05:00 です。</span><span class="sxs-lookup"><span data-stu-id="7a29e-124">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="7a29e-125">接続は、接続キャッシュに返された後、アクティブに転送中ではないときに終了します。</span><span class="sxs-lookup"><span data-stu-id="7a29e-125">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="7a29e-126">TCP トランスポートによって使用される接続キャッシュは、各エンドポイントの必要に応じて、`maxOutboundConnectionsPerEndpoint.` で設定されているキャッシュ制限内で新しい接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="7a29e-126">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="7a29e-127">そのサービスによって開始されるリモート エンドポイントへの接続の最大数を指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="7a29e-127">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="7a29e-128">制限を超えた接続は、制限内に空きができるまでキューに置かれます。</span><span class="sxs-lookup"><span data-stu-id="7a29e-128">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="7a29e-129">`idleTimeout` は、例外がスローされるまでに接続をキューに入れたままにする期間を制限します。</span><span class="sxs-lookup"><span data-stu-id="7a29e-129">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="7a29e-130">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="7a29e-130">The default is 10.</span></span><br /><br /> <span data-ttu-id="7a29e-131">この属性は、クライアントから特定のサービス エンドポイントへの接続で、同時にアクティブできる接続数を制限します。</span><span class="sxs-lookup"><span data-stu-id="7a29e-131">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="7a29e-132">この値よりも多くのアクティブなクライアント接続がある場合、サービスは、クライアントに応答しないように見える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7a29e-132">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="7a29e-133">この場合は、この値を調整して、予想される特定のエンドポイントへの同時クライアント接続の最大数より大きくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a29e-133">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7a29e-134">子要素</span><span class="sxs-lookup"><span data-stu-id="7a29e-134">Child Elements</span></span>  
 <span data-ttu-id="7a29e-135">なし。</span><span class="sxs-lookup"><span data-stu-id="7a29e-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7a29e-136">親要素</span><span class="sxs-lookup"><span data-stu-id="7a29e-136">Parent Elements</span></span>  
  
|<span data-ttu-id="7a29e-137">要素</span><span class="sxs-lookup"><span data-stu-id="7a29e-137">Element</span></span>|<span data-ttu-id="7a29e-138">説明</span><span class="sxs-lookup"><span data-stu-id="7a29e-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7a29e-139">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="7a29e-139">\<namedPipeTransport></span></span>](namedpipetransport.md)|<span data-ttu-id="7a29e-140">チャネルで名前付きパイプを使用してメッセージを転送するトランスポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="7a29e-140">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a29e-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a29e-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="7a29e-142">トランスポート</span><span class="sxs-lookup"><span data-stu-id="7a29e-142">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="7a29e-143">トランスポートの選択</span><span class="sxs-lookup"><span data-stu-id="7a29e-143">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="7a29e-144">バインディング</span><span class="sxs-lookup"><span data-stu-id="7a29e-144">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7a29e-145">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="7a29e-145">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="7a29e-146">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="7a29e-146">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="7a29e-147">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="7a29e-147">\<customBinding></span></span>](custombinding.md)
