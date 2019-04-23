---
title: <udpAnnouncementEndpoint>
ms.date: 03/30/2017
ms.assetid: 5b3fa9c5-f372-4df9-a9d6-1e426063b721
ms.openlocfilehash: 04f5fb27a0da7e553ff3c0308f7fb2e2df2e0b20
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210010"
---
# <a name="udpannouncementendpoint"></a><span data-ttu-id="93fe3-101">\<udpAnnouncementEndpoint></span><span class="sxs-lookup"><span data-stu-id="93fe3-101">\<udpAnnouncementEndpoint></span></span>
<span data-ttu-id="93fe3-102">この構成要素は、UDP バインディングを使用してアナウンス メッセージを送信するためにサービスが使用する標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="93fe3-102">This configuration element defines a standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="93fe3-103">これには固定コントラクトがあり、2 つの探索のバージョンをサポートします。</span><span class="sxs-lookup"><span data-stu-id="93fe3-103">It has a fixed contract and supports two discovery versions.</span></span> <span data-ttu-id="93fe3-104">また、WS-Discovery の仕様 (WS-Discovery April 2005 または WS-Discovery V1.1) に規定された固定 UDP バインディングと既定のアドレスも備えています。</span><span class="sxs-lookup"><span data-stu-id="93fe3-104">In addition it has a fixed UDP binding and a default address value as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery version 1.1).</span></span> <span data-ttu-id="93fe3-105">アナウンス メッセージの送受信に使用するマルチキャスト アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="93fe3-105">You can specify the multicast address to use for sending and receiving the announcement messages.</span></span>  
  
<span data-ttu-id="93fe3-106">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="93fe3-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="93fe3-107">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="93fe3-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93fe3-108">構文</span><span class="sxs-lookup"><span data-stu-id="93fe3-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxAnnouncementDelay="Timespan"
                        multicastAddress="Uri"
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93fe3-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="93fe3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="93fe3-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="93fe3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93fe3-111">属性</span><span class="sxs-lookup"><span data-stu-id="93fe3-111">Attributes</span></span>  
  
|<span data-ttu-id="93fe3-112">属性</span><span class="sxs-lookup"><span data-stu-id="93fe3-112">Attribute</span></span>|<span data-ttu-id="93fe3-113">説明</span><span class="sxs-lookup"><span data-stu-id="93fe3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="93fe3-114">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="93fe3-114">discoveryVersion</span></span>|<span data-ttu-id="93fe3-115">WS-Discovery プロトコルの 2 つのバージョンのうち、1 つを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="93fe3-115">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="93fe3-116">有効値は WSDiscovery11 と WSDiscoveryApril2005 です。</span><span class="sxs-lookup"><span data-stu-id="93fe3-116">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="93fe3-117">この値は、<xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="93fe3-117">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="93fe3-118">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="93fe3-118">maxAnnouncementDelay</span></span>|<span data-ttu-id="93fe3-119">Discovery プロトコルが Hello メッセージを送信するまでの待機時間の最大値を指定する Timespan 値。</span><span class="sxs-lookup"><span data-stu-id="93fe3-119">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="93fe3-120">メッセージは送信前に 0 からこの属性値の間のランダムな時間だけ待機します。</span><span class="sxs-lookup"><span data-stu-id="93fe3-120">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="93fe3-121">この属性はランダムな短い待機時間を設定するために使用されるもので、ネットワークが機能しなくなり、すべてのサービスが同時にオンラインに戻ったときにネットワーク ストームが発生することを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="93fe3-121">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="93fe3-122">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="93fe3-122">multicastAddress</span></span>|<span data-ttu-id="93fe3-123">探索メッセージの送受信に使用するマルチキャスト アドレスを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="93fe3-123">A URI that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="93fe3-124">既定値は、プロトコル仕様に準じたマルチキャスト アドレスです。</span><span class="sxs-lookup"><span data-stu-id="93fe3-124">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|<span data-ttu-id="93fe3-125">name</span><span class="sxs-lookup"><span data-stu-id="93fe3-125">name</span></span>|<span data-ttu-id="93fe3-126">標準エンドポイントの構成名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="93fe3-126">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="93fe3-127">この名前は、サービス エンドポイントの `endpointConfiguration` 属性で使用され、標準エンドポイントと構成を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="93fe3-127">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93fe3-128">子要素</span><span class="sxs-lookup"><span data-stu-id="93fe3-128">Child Elements</span></span>  
  
|<span data-ttu-id="93fe3-129">要素</span><span class="sxs-lookup"><span data-stu-id="93fe3-129">Element</span></span>|<span data-ttu-id="93fe3-130">説明</span><span class="sxs-lookup"><span data-stu-id="93fe3-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93fe3-131">\<udpTransportSettings></span><span class="sxs-lookup"><span data-stu-id="93fe3-131">\<udpTransportSettings></span></span>](udptransportsettings.md)|<span data-ttu-id="93fe3-132">UDP エンドポイントの UDP トランスポートを構成できる設定のコレクション。</span><span class="sxs-lookup"><span data-stu-id="93fe3-132">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="93fe3-133">親要素</span><span class="sxs-lookup"><span data-stu-id="93fe3-133">Parent Elements</span></span>  
  
|<span data-ttu-id="93fe3-134">要素</span><span class="sxs-lookup"><span data-stu-id="93fe3-134">Element</span></span>|<span data-ttu-id="93fe3-135">説明</span><span class="sxs-lookup"><span data-stu-id="93fe3-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93fe3-136">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="93fe3-136">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="93fe3-137">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="93fe3-137">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="93fe3-138">例</span><span class="sxs-lookup"><span data-stu-id="93fe3-138">Example</span></span>  
 <span data-ttu-id="93fe3-139">既定のマルチキャスト アドレスを使用した UDP マルチキャスト トランスポート経由、および指定されたマルチキャスト アドレスを使用した UDP マルチキャスト トランスポート経由でアナウンスをリッスンするクライアントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="93fe3-139">The following example demonstrates a client listening for announcement over a UDP multicast transport with default multicast address, and UDP multicast transport with specified multicast address.</span></span>  
  
```xml  
<services>
  <service name="ServiceAnnouncementListener">
    <endpoint name="udpAnnouncementEndpointStandard"
              kind="udpAnnouncementEndpoint"
              bindingConfiguration="..." />
    <endpoint name="udpAnnouncementEndpoint2"
              kind="udpAnnouncementEndpoint"
              endpointConfiguration="AnnouncementConfiguration3702"
              bindingConfiguration="..." />
    ...
  </service>
</services>
<standardEndpoints>
  <udpAnnouncementEndpoint>
    <standardEndpoint name="AnnouncementConfiguration2"
                      version="WSDiscoveryApril2005"
                      multicastAddress="soap.udp://239.255.255.250:3703"/>
  </udpAnnouncementEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a><span data-ttu-id="93fe3-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="93fe3-140">See also</span></span>

- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>
