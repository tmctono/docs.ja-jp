---
title: <announcementEndpoint>
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: f68972cdf0e55f92fd4856aff912f00db7c62be4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201617"
---
# \<announcementEndpoint>

<span data-ttu-id="86b02-101">この構成要素は、固定アナウンス コントラクトが設定されている標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="86b02-101">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="86b02-102">サービスは、サービスが開いたとき、または閉じたときにオンラインおよびオフラインのアナウンス メッセージを送信することによって、その可用性をアナウンスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="86b02-102">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="86b02-103">Windows Communication Foundation (WCF) サービスでは、要素内のアナウンスエンドポイントを指定 [\<serviceDiscovery>](servicediscovery.md) し、アナウンスメント Ementclient を使用してアナウンスを実行します。</span><span class="sxs-lookup"><span data-stu-id="86b02-103">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="86b02-104">他のサービスからのアナウンスをリッスンするクライアントは、実際には WCF サービスとして機能します。そのため、「」セクションで、そのクライアントのアナウンスエンドポイントを構成する必要があり [\<services>](services.md) ます。</span><span class="sxs-lookup"><span data-stu-id="86b02-104">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](services.md) section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<announcementEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="86b02-105">構文</span><span class="sxs-lookup"><span data-stu-id="86b02-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxAnnouncementDelay="Timespan"
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86b02-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="86b02-106">Attributes and Elements</span></span>  

 <span data-ttu-id="86b02-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="86b02-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86b02-108">属性</span><span class="sxs-lookup"><span data-stu-id="86b02-108">Attributes</span></span>  
  
|<span data-ttu-id="86b02-109">属性</span><span class="sxs-lookup"><span data-stu-id="86b02-109">Attribute</span></span>|<span data-ttu-id="86b02-110">[説明]</span><span class="sxs-lookup"><span data-stu-id="86b02-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="86b02-111">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="86b02-111">discoveryVersion</span></span>|<span data-ttu-id="86b02-112">WS-Discovery プロトコルの 2 つのバージョンのうち、1 つを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="86b02-112">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="86b02-113">有効値は WSDiscovery11 と WSDiscoveryApril2005 です。</span><span class="sxs-lookup"><span data-stu-id="86b02-113">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="86b02-114">この値は、<xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="86b02-114">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="86b02-115">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="86b02-115">maxAnnouncementDelay</span></span>|<span data-ttu-id="86b02-116">Discovery プロトコルが Hello メッセージを送信するまでの待機時間の最大値を指定する Timespan 値。</span><span class="sxs-lookup"><span data-stu-id="86b02-116">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="86b02-117">メッセージは送信前に 0 からこの属性値の間のランダムな時間だけ待機します。</span><span class="sxs-lookup"><span data-stu-id="86b02-117">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="86b02-118">この属性はランダムな短い待機時間を設定するために使用されるもので、ネットワークが機能しなくなり、すべてのサービスが同時にオンラインに戻ったときにネットワーク ストームが発生することを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="86b02-118">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="86b02-119">name</span><span class="sxs-lookup"><span data-stu-id="86b02-119">name</span></span>|<span data-ttu-id="86b02-120">標準エンドポイントの構成名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="86b02-120">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="86b02-121">この名前は、サービス エンドポイントの `endpointConfiguration` 属性で使用され、標準エンドポイントと構成を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="86b02-121">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="86b02-122">子要素</span><span class="sxs-lookup"><span data-stu-id="86b02-122">Child Elements</span></span>  

 <span data-ttu-id="86b02-123">なし。</span><span class="sxs-lookup"><span data-stu-id="86b02-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="86b02-124">親要素</span><span class="sxs-lookup"><span data-stu-id="86b02-124">Parent Elements</span></span>  
  
|<span data-ttu-id="86b02-125">要素</span><span class="sxs-lookup"><span data-stu-id="86b02-125">Element</span></span>|<span data-ttu-id="86b02-126">説明</span><span class="sxs-lookup"><span data-stu-id="86b02-126">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="86b02-127">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="86b02-127">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="86b02-128">例</span><span class="sxs-lookup"><span data-stu-id="86b02-128">Example</span></span>  

 <span data-ttu-id="86b02-129">http およびピア ネットワーク経由でアナウンス メッセージをリッスンするクライアントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="86b02-129">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
```xml  
<services>
  <service name="ServiceAnnouncementListener">
    <endpoint name="httpAnnouncementEndpoint"
              kind="announcementEndpoint"
              binding="basicHttpBinding"
              address="announcements" />
    <endpoint name="peerNetAnnouncementEndpoint"
              kind="announcementEndpoint"
              binding="peerTcpBinding"
              address="net.p2p://discoveryMesh/multicast"
              bindingConfiguration="discoveryPeerTcpBindingConfig" />
  ...
  </service>
</services>

<standardEndpoints>
  <announcementEndpoint>
    <standardEndpoint name="httpAnnouncementEndpoint"
                      version="WSDiscoveryApril2005" />
    <standardEndpoint name="peerNetAnnouncementEndpoint"
                      version="WSDiscoveryApril2005" />
  </announcementEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a><span data-ttu-id="86b02-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="86b02-130">See also</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
