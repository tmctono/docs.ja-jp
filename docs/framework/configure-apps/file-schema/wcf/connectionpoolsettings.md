---
title: <connectionPoolSettings>
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: 842173c7bd9673a1e08c93d5ed650a42b9d979e5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400478"
---
# \<connectionPoolSettings>
<span data-ttu-id="ac2a7-101">名前付きパイプ バインディングの追加の接続プール設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="ac2a7-101">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedPipeTransport>**](namedpipetransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="ac2a7-102">構文</span><span class="sxs-lookup"><span data-stu-id="ac2a7-102">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac2a7-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ac2a7-103">Attributes and Elements</span></span>  
 <span data-ttu-id="ac2a7-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ac2a7-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac2a7-105">属性</span><span class="sxs-lookup"><span data-stu-id="ac2a7-105">Attributes</span></span>  
  
|<span data-ttu-id="ac2a7-106">属性</span><span class="sxs-lookup"><span data-stu-id="ac2a7-106">Attribute</span></span>|<span data-ttu-id="ac2a7-107">説明</span><span class="sxs-lookup"><span data-stu-id="ac2a7-107">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="ac2a7-108">送信チャネルに使用される接続プールの名前を定義する文字列です。</span><span class="sxs-lookup"><span data-stu-id="ac2a7-108">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="ac2a7-109">ストリーム配信モードでは、接続が共有されません。したがって、接続プールは無効です。</span><span class="sxs-lookup"><span data-stu-id="ac2a7-109">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="ac2a7-110">既定は、"default" 文字列です。</span><span class="sxs-lookup"><span data-stu-id="ac2a7-110">The default is a "default" string.</span></span> <span data-ttu-id="ac2a7-111">この値を変更して、特定のクライアントの接続を、個別のグループに分離できます。</span><span class="sxs-lookup"><span data-stu-id="ac2a7-111">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="ac2a7-112">接続が切断されるまでの最大アイドル時間を指定する正の <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="ac2a7-112">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="ac2a7-113">既定値は 00:02:00 です。</span><span class="sxs-lookup"><span data-stu-id="ac2a7-113">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="ac2a7-114">そのサービスによって開始されるリモート エンドポイントへの接続の最大数を指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="ac2a7-114">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="ac2a7-115">制限を超えた接続は、制限内に空きができるまでキューに置かれます。</span><span class="sxs-lookup"><span data-stu-id="ac2a7-115">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="ac2a7-116">`idleTimeout` は、例外がスローされるまでに接続をキューに入れたままにする期間を制限します。</span><span class="sxs-lookup"><span data-stu-id="ac2a7-116">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="ac2a7-117">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="ac2a7-117">The default is 10.</span></span><br /><br /> <span data-ttu-id="ac2a7-118">この属性は、クライアントから特定のサービス エンドポイントへの接続で、同時にアクティブできる接続数を制限します。</span><span class="sxs-lookup"><span data-stu-id="ac2a7-118">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="ac2a7-119">この値よりも多くのアクティブなクライアント接続がある場合、サービスは、クライアントに応答しないように見える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ac2a7-119">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="ac2a7-120">この場合は、この値を調整して、予想される特定のエンドポイントへの同時クライアント接続の最大数より大きくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac2a7-120">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac2a7-121">子要素</span><span class="sxs-lookup"><span data-stu-id="ac2a7-121">Child Elements</span></span>  
 <span data-ttu-id="ac2a7-122">なし。</span><span class="sxs-lookup"><span data-stu-id="ac2a7-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ac2a7-123">親要素</span><span class="sxs-lookup"><span data-stu-id="ac2a7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ac2a7-124">要素</span><span class="sxs-lookup"><span data-stu-id="ac2a7-124">Element</span></span>|<span data-ttu-id="ac2a7-125">Description</span><span class="sxs-lookup"><span data-stu-id="ac2a7-125">Description</span></span>|  
|-------------|-----------------|  
|[\<namedPipeTransport>](namedpipetransport.md)|<span data-ttu-id="ac2a7-126">チャネルで名前付きパイプを使用してメッセージを転送するトランスポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="ac2a7-126">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ac2a7-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac2a7-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ac2a7-128">トランスポート</span><span class="sxs-lookup"><span data-stu-id="ac2a7-128">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="ac2a7-129">トランスポートの選択</span><span class="sxs-lookup"><span data-stu-id="ac2a7-129">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="ac2a7-130">バインド</span><span class="sxs-lookup"><span data-stu-id="ac2a7-130">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ac2a7-131">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="ac2a7-131">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ac2a7-132">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="ac2a7-132">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
