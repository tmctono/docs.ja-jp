---
title: <udpAnnouncementEndpoint>
ms.date: 03/30/2017
ms.assetid: 5b3fa9c5-f372-4df9-a9d6-1e426063b721
ms.openlocfilehash: 8dabf8845126705d082d080b643688ed62883f39
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854917"
---
# \<udpAnnouncementEndpoint>
<span data-ttu-id="40ab6-101">この構成要素は、UDP バインディングを使用してアナウンス メッセージを送信するためにサービスが使用する標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="40ab6-101">This configuration element defines a standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="40ab6-102">これには固定コントラクトがあり、2 つの探索のバージョンをサポートします。</span><span class="sxs-lookup"><span data-stu-id="40ab6-102">It has a fixed contract and supports two discovery versions.</span></span> <span data-ttu-id="40ab6-103">また、WS-Discovery の仕様 (WS-Discovery April 2005 または WS-Discovery V1.1) に規定された固定 UDP バインディングと既定のアドレスも備えています。</span><span class="sxs-lookup"><span data-stu-id="40ab6-103">In addition it has a fixed UDP binding and a default address value as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery version 1.1).</span></span> <span data-ttu-id="40ab6-104">アナウンス メッセージの送受信に使用するマルチキャスト アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="40ab6-104">You can specify the multicast address to use for sending and receiving the announcement messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<udpAnnouncementEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="40ab6-105">構文</span><span class="sxs-lookup"><span data-stu-id="40ab6-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40ab6-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="40ab6-106">Attributes and Elements</span></span>  
 <span data-ttu-id="40ab6-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="40ab6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40ab6-108">属性</span><span class="sxs-lookup"><span data-stu-id="40ab6-108">Attributes</span></span>  
  
|<span data-ttu-id="40ab6-109">属性</span><span class="sxs-lookup"><span data-stu-id="40ab6-109">Attribute</span></span>|<span data-ttu-id="40ab6-110">説明</span><span class="sxs-lookup"><span data-stu-id="40ab6-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="40ab6-111">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="40ab6-111">discoveryVersion</span></span>|<span data-ttu-id="40ab6-112">WS-Discovery プロトコルの 2 つのバージョンのうち、1 つを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="40ab6-112">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="40ab6-113">有効値は WSDiscovery11 と WSDiscoveryApril2005 です。</span><span class="sxs-lookup"><span data-stu-id="40ab6-113">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="40ab6-114">この値は、<xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="40ab6-114">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="40ab6-115">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="40ab6-115">maxAnnouncementDelay</span></span>|<span data-ttu-id="40ab6-116">Discovery プロトコルが Hello メッセージを送信するまでの待機時間の最大値を指定する Timespan 値。</span><span class="sxs-lookup"><span data-stu-id="40ab6-116">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="40ab6-117">メッセージは送信前に 0 からこの属性値の間のランダムな時間だけ待機します。</span><span class="sxs-lookup"><span data-stu-id="40ab6-117">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="40ab6-118">この属性はランダムな短い待機時間を設定するために使用されるもので、ネットワークが機能しなくなり、すべてのサービスが同時にオンラインに戻ったときにネットワーク ストームが発生することを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="40ab6-118">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="40ab6-119">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="40ab6-119">multicastAddress</span></span>|<span data-ttu-id="40ab6-120">探索メッセージの送受信に使用するマルチキャスト アドレスを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="40ab6-120">A URI that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="40ab6-121">既定値は、プロトコル仕様に準じたマルチキャスト アドレスです。</span><span class="sxs-lookup"><span data-stu-id="40ab6-121">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|<span data-ttu-id="40ab6-122">name</span><span class="sxs-lookup"><span data-stu-id="40ab6-122">name</span></span>|<span data-ttu-id="40ab6-123">標準エンドポイントの構成名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="40ab6-123">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="40ab6-124">この名前は、サービス エンドポイントの `endpointConfiguration` 属性で使用され、標準エンドポイントと構成を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="40ab6-124">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40ab6-125">子要素</span><span class="sxs-lookup"><span data-stu-id="40ab6-125">Child Elements</span></span>  
  
|<span data-ttu-id="40ab6-126">要素</span><span class="sxs-lookup"><span data-stu-id="40ab6-126">Element</span></span>|<span data-ttu-id="40ab6-127">Description</span><span class="sxs-lookup"><span data-stu-id="40ab6-127">Description</span></span>|  
|-------------|-----------------|  
|[\<udpTransportSettings>](udptransportsettings.md)|<span data-ttu-id="40ab6-128">UDP エンドポイントの UDP トランスポートを構成できる設定のコレクション。</span><span class="sxs-lookup"><span data-stu-id="40ab6-128">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="40ab6-129">親要素</span><span class="sxs-lookup"><span data-stu-id="40ab6-129">Parent Elements</span></span>  
  
|<span data-ttu-id="40ab6-130">要素</span><span class="sxs-lookup"><span data-stu-id="40ab6-130">Element</span></span>|<span data-ttu-id="40ab6-131">Description</span><span class="sxs-lookup"><span data-stu-id="40ab6-131">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="40ab6-132">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="40ab6-132">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="40ab6-133">例</span><span class="sxs-lookup"><span data-stu-id="40ab6-133">Example</span></span>  
 <span data-ttu-id="40ab6-134">既定のマルチキャスト アドレスを使用した UDP マルチキャスト トランスポート経由、および指定されたマルチキャスト アドレスを使用した UDP マルチキャスト トランスポート経由でアナウンスをリッスンするクライアントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="40ab6-134">The following example demonstrates a client listening for announcement over a UDP multicast transport with default multicast address, and UDP multicast transport with specified multicast address.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="40ab6-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="40ab6-135">See also</span></span>

- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>
