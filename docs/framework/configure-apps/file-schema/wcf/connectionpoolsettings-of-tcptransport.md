---
title: <connectionPoolSettings> の <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: 53523fd550ecad931bfb2af5eb9beb71c60d44f8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176007"
---
# <a name="connectionpoolsettings-of-tcptransport"></a><span data-ttu-id="eb607-102">\<connectionPoolSettings> の \<tcpTransport></span><span class="sxs-lookup"><span data-stu-id="eb607-102">\<connectionPoolSettings> of \<tcpTransport></span></span>

<span data-ttu-id="eb607-103">TCP トランスポートの追加の接続プール設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb607-103">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tcpTransport>**](tcptransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="eb607-104">構文</span><span class="sxs-lookup"><span data-stu-id="eb607-104">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb607-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="eb607-105">Attributes and Elements</span></span>  

 <span data-ttu-id="eb607-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="eb607-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb607-107">属性</span><span class="sxs-lookup"><span data-stu-id="eb607-107">Attributes</span></span>  
  
|<span data-ttu-id="eb607-108">属性</span><span class="sxs-lookup"><span data-stu-id="eb607-108">Attribute</span></span>|<span data-ttu-id="eb607-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="eb607-109">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="eb607-110">送信チャネルに使用される接続プールの名前を定義する文字列です。</span><span class="sxs-lookup"><span data-stu-id="eb607-110">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="eb607-111">ストリーム配信モードでは、接続が共有されません。したがって、接続プールは無効です。</span><span class="sxs-lookup"><span data-stu-id="eb607-111">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="eb607-112">既定は、"default" 文字列です。</span><span class="sxs-lookup"><span data-stu-id="eb607-112">The default is a "default" string.</span></span> <span data-ttu-id="eb607-113">この値を変更して、特定のクライアントの接続を、個別のグループに分離できます。</span><span class="sxs-lookup"><span data-stu-id="eb607-113">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="eb607-114">接続が切断されるまでの最大アイドル時間を指定する正の <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="eb607-114">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="eb607-115">既定値は 00:02:00 です。</span><span class="sxs-lookup"><span data-stu-id="eb607-115">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="eb607-116">アクティブな接続が終了されるまでの時間を指定する <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="eb607-116">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="eb607-117">既定値は 00:05:00 です。</span><span class="sxs-lookup"><span data-stu-id="eb607-117">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="eb607-118">接続は、接続キャッシュに返された後、アクティブに転送中ではないときに終了します。</span><span class="sxs-lookup"><span data-stu-id="eb607-118">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="eb607-119">TCP トランスポートによって使用される接続キャッシュは、各エンドポイントの必要に応じて、`maxOutboundConnectionsPerEndpoint.` で設定されているキャッシュ制限内で新しい接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="eb607-119">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="eb607-120">そのサービスによって開始されるリモート エンドポイントへの接続の最大数を指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="eb607-120">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="eb607-121">制限を超えた接続は、制限内に空きができるまでキューに置かれます。</span><span class="sxs-lookup"><span data-stu-id="eb607-121">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="eb607-122">`idleTimeout` は、例外がスローされるまでに接続をキューに入れたままにする期間を制限します。</span><span class="sxs-lookup"><span data-stu-id="eb607-122">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="eb607-123">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="eb607-123">The default is 10.</span></span><br /><br /> <span data-ttu-id="eb607-124">この属性は、クライアントから特定のサービス エンドポイントへの接続で、同時にアクティブできる接続数を制限します。</span><span class="sxs-lookup"><span data-stu-id="eb607-124">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="eb607-125">この値よりも多くのアクティブなクライアント接続がある場合、サービスは、クライアントに応答しないように見える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eb607-125">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="eb607-126">この場合は、この値を調整して、予想される特定のエンドポイントへの同時クライアント接続の最大数より大きくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb607-126">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb607-127">子要素</span><span class="sxs-lookup"><span data-stu-id="eb607-127">Child Elements</span></span>  

 <span data-ttu-id="eb607-128">なし。</span><span class="sxs-lookup"><span data-stu-id="eb607-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb607-129">親要素</span><span class="sxs-lookup"><span data-stu-id="eb607-129">Parent Elements</span></span>  
  
|<span data-ttu-id="eb607-130">要素</span><span class="sxs-lookup"><span data-stu-id="eb607-130">Element</span></span>|<span data-ttu-id="eb607-131">説明</span><span class="sxs-lookup"><span data-stu-id="eb607-131">Description</span></span>|  
|-------------|-----------------|  
|[\<namedPipeTransport>](namedpipetransport.md)|<span data-ttu-id="eb607-132">チャネルで名前付きパイプを使用してメッセージを転送するトランスポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="eb607-132">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb607-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb607-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="eb607-134">トランスポート</span><span class="sxs-lookup"><span data-stu-id="eb607-134">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="eb607-135">トランスポートの選択</span><span class="sxs-lookup"><span data-stu-id="eb607-135">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="eb607-136">バインド</span><span class="sxs-lookup"><span data-stu-id="eb607-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="eb607-137">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="eb607-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="eb607-138">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="eb607-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
