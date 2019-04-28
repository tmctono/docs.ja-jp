---
title: <announcementEndpoint>
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: 4f3cf2748acc75b0ec83732664c5f97114f3663a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701256"
---
# <a name="announcementendpoint"></a><span data-ttu-id="1ca01-101">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="1ca01-101">\<announcementEndpoint></span></span>
<span data-ttu-id="1ca01-102">この構成要素は、固定アナウンス コントラクトが設定されている標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="1ca01-102">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="1ca01-103">サービスは、サービスが開いたとき、または閉じたときにオンラインおよびオフラインのアナウンス メッセージを送信することによって、その可用性をアナウンスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1ca01-103">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="1ca01-104">Windows Communication Foundation (WCF) サービスでアナウンス エンドポイントを指定します、 [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md)要素と、AnnouncementClient お知らせの実行を使用します。</span><span class="sxs-lookup"><span data-stu-id="1ca01-104">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="1ca01-105">しようとするその他のサービスからのアナウンスをリッスンするようにクライアントが、WCF サービスとして機能する実際にはクライアントのアナウンス エンドポイントを構成する必要があるため、 [ \<services >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)セクション。</span><span class="sxs-lookup"><span data-stu-id="1ca01-105">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) section.</span></span>  
  
<span data-ttu-id="1ca01-106">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1ca01-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="1ca01-107">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="1ca01-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ca01-108">構文</span><span class="sxs-lookup"><span data-stu-id="1ca01-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ca01-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1ca01-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1ca01-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ca01-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ca01-111">属性</span><span class="sxs-lookup"><span data-stu-id="1ca01-111">Attributes</span></span>  
  
|<span data-ttu-id="1ca01-112">属性</span><span class="sxs-lookup"><span data-stu-id="1ca01-112">Attribute</span></span>|<span data-ttu-id="1ca01-113">説明</span><span class="sxs-lookup"><span data-stu-id="1ca01-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1ca01-114">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="1ca01-114">discoveryVersion</span></span>|<span data-ttu-id="1ca01-115">WS-Discovery プロトコルの 2 つのバージョンのうち、1 つを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="1ca01-115">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="1ca01-116">有効値は WSDiscovery11 と WSDiscoveryApril2005 です。</span><span class="sxs-lookup"><span data-stu-id="1ca01-116">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="1ca01-117">この値は、<xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="1ca01-117">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="1ca01-118">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="1ca01-118">maxAnnouncementDelay</span></span>|<span data-ttu-id="1ca01-119">Discovery プロトコルが Hello メッセージを送信するまでの待機時間の最大値を指定する Timespan 値。</span><span class="sxs-lookup"><span data-stu-id="1ca01-119">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="1ca01-120">メッセージは送信前に 0 からこの属性値の間のランダムな時間だけ待機します。</span><span class="sxs-lookup"><span data-stu-id="1ca01-120">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="1ca01-121">この属性はランダムな短い待機時間を設定するために使用されるもので、ネットワークが機能しなくなり、すべてのサービスが同時にオンラインに戻ったときにネットワーク ストームが発生することを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="1ca01-121">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="1ca01-122">name</span><span class="sxs-lookup"><span data-stu-id="1ca01-122">name</span></span>|<span data-ttu-id="1ca01-123">標準エンドポイントの構成名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="1ca01-123">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="1ca01-124">この名前は、サービス エンドポイントの `endpointConfiguration` 属性で使用され、標準エンドポイントと構成を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="1ca01-124">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ca01-125">子要素</span><span class="sxs-lookup"><span data-stu-id="1ca01-125">Child Elements</span></span>  
 <span data-ttu-id="1ca01-126">なし。</span><span class="sxs-lookup"><span data-stu-id="1ca01-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1ca01-127">親要素</span><span class="sxs-lookup"><span data-stu-id="1ca01-127">Parent Elements</span></span>  
  
|<span data-ttu-id="1ca01-128">要素</span><span class="sxs-lookup"><span data-stu-id="1ca01-128">Element</span></span>|<span data-ttu-id="1ca01-129">説明</span><span class="sxs-lookup"><span data-stu-id="1ca01-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ca01-130">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="1ca01-130">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="1ca01-131">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="1ca01-131">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1ca01-132">例</span><span class="sxs-lookup"><span data-stu-id="1ca01-132">Example</span></span>  
 <span data-ttu-id="1ca01-133">http およびピア ネットワーク経由でアナウンス メッセージをリッスンするクライアントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1ca01-133">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1ca01-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ca01-134">See also</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
