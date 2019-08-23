---
title: <announcementEndpoint>
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: aa4cd8f4d7dcfa438ede71c394f1d0b0ac6faa50
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926551"
---
# <a name="announcementendpoint"></a><span data-ttu-id="a0e5f-101">\<発表の ></span><span class="sxs-lookup"><span data-stu-id="a0e5f-101">\<announcementEndpoint></span></span>
<span data-ttu-id="a0e5f-102">この構成要素は、固定アナウンス コントラクトが設定されている標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="a0e5f-102">This configuration element defines a standard endpoint with a fixed announcement contract.</span></span> <span data-ttu-id="a0e5f-103">サービスは、サービスが開いたとき、または閉じたときにオンラインおよびオフラインのアナウンス メッセージを送信することによって、その可用性をアナウンスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a0e5f-103">A service can optionally announce its availability by sending an online and offline announcement message when it is opened or closed respectively.</span></span> <span data-ttu-id="a0e5f-104">Windows Communication Foundation (WCF) サービスでは、 [ \<servicediscovery >](servicediscovery.md)要素内のアナウンスエンドポイントを指定し、アナウンスを実行するためにアナウンス ementclient を使用します。</span><span class="sxs-lookup"><span data-stu-id="a0e5f-104">A Windows Communication Foundation (WCF) service specifies the announcement endpoints in the [\<serviceDiscovery>](servicediscovery.md) element and uses the AnnouncementClient to perform the announcements.</span></span> <span data-ttu-id="a0e5f-105">他のサービスからのアナウンスをリッスンするクライアントは、実際には WCF サービスとして機能します。そのため、[ [ \<サービス >](services.md) ] セクションで、そのクライアントのアナウンスエンドポイントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0e5f-105">A client wishing to listen for the announcement from other service is actually acting as a WCF service; thus you have to configure the announcement endpoints for that client in the [\<services>](services.md) section.</span></span>  
  
<span data-ttu-id="a0e5f-106">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a0e5f-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="a0e5f-107">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="a0e5f-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0e5f-108">構文</span><span class="sxs-lookup"><span data-stu-id="a0e5f-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0e5f-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a0e5f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a0e5f-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0e5f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0e5f-111">属性</span><span class="sxs-lookup"><span data-stu-id="a0e5f-111">Attributes</span></span>  
  
|<span data-ttu-id="a0e5f-112">属性</span><span class="sxs-lookup"><span data-stu-id="a0e5f-112">Attribute</span></span>|<span data-ttu-id="a0e5f-113">説明</span><span class="sxs-lookup"><span data-stu-id="a0e5f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a0e5f-114">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="a0e5f-114">discoveryVersion</span></span>|<span data-ttu-id="a0e5f-115">WS-Discovery プロトコルの 2 つのバージョンのうち、1 つを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="a0e5f-115">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="a0e5f-116">有効値は WSDiscovery11 と WSDiscoveryApril2005 です。</span><span class="sxs-lookup"><span data-stu-id="a0e5f-116">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="a0e5f-117">この値は、<xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="a0e5f-117">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="a0e5f-118">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="a0e5f-118">maxAnnouncementDelay</span></span>|<span data-ttu-id="a0e5f-119">Discovery プロトコルが Hello メッセージを送信するまでの待機時間の最大値を指定する Timespan 値。</span><span class="sxs-lookup"><span data-stu-id="a0e5f-119">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="a0e5f-120">メッセージは送信前に 0 からこの属性値の間のランダムな時間だけ待機します。</span><span class="sxs-lookup"><span data-stu-id="a0e5f-120">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="a0e5f-121">この属性はランダムな短い待機時間を設定するために使用されるもので、ネットワークが機能しなくなり、すべてのサービスが同時にオンラインに戻ったときにネットワーク ストームが発生することを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="a0e5f-121">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="a0e5f-122">name</span><span class="sxs-lookup"><span data-stu-id="a0e5f-122">name</span></span>|<span data-ttu-id="a0e5f-123">標準エンドポイントの構成名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="a0e5f-123">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="a0e5f-124">この名前は、サービス エンドポイントの `endpointConfiguration` 属性で使用され、標準エンドポイントと構成を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="a0e5f-124">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0e5f-125">子要素</span><span class="sxs-lookup"><span data-stu-id="a0e5f-125">Child Elements</span></span>  
 <span data-ttu-id="a0e5f-126">なし。</span><span class="sxs-lookup"><span data-stu-id="a0e5f-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a0e5f-127">親要素</span><span class="sxs-lookup"><span data-stu-id="a0e5f-127">Parent Elements</span></span>  
  
|<span data-ttu-id="a0e5f-128">要素</span><span class="sxs-lookup"><span data-stu-id="a0e5f-128">Element</span></span>|<span data-ttu-id="a0e5f-129">説明</span><span class="sxs-lookup"><span data-stu-id="a0e5f-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0e5f-130">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="a0e5f-130">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="a0e5f-131">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="a0e5f-131">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a0e5f-132">例</span><span class="sxs-lookup"><span data-stu-id="a0e5f-132">Example</span></span>  
 <span data-ttu-id="a0e5f-133">http およびピア ネットワーク経由でアナウンス メッセージをリッスンするクライアントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a0e5f-133">The following example demonstrates a client listening for announcements messages over http and peernet.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a0e5f-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0e5f-134">See also</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
