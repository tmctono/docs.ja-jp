---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: a99edd3a62a40c2efbc63a166b8c0b0d124e8a72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936274"
---
# <a name="servicediscovery"></a><span data-ttu-id="ba493-101">\<serviceDiscovery ></span><span class="sxs-lookup"><span data-stu-id="ba493-101">\<serviceDiscovery></span></span>
<span data-ttu-id="ba493-102">サービス エンドポイントの探索可能性を指定します。</span><span class="sxs-lookup"><span data-stu-id="ba493-102">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="ba493-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ba493-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="ba493-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="ba493-104">\<behaviors></span></span>  
<span data-ttu-id="ba493-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="ba493-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="ba493-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ba493-106">\<behavior></span></span>  
<span data-ttu-id="ba493-107">\<serviceDiscovery ></span><span class="sxs-lookup"><span data-stu-id="ba493-107">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba493-108">構文</span><span class="sxs-lookup"><span data-stu-id="ba493-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </announcementEndpoints>
        <discoveryEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </discoveryEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba493-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ba493-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ba493-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ba493-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba493-111">属性</span><span class="sxs-lookup"><span data-stu-id="ba493-111">Attributes</span></span>  
 <span data-ttu-id="ba493-112">なし。</span><span class="sxs-lookup"><span data-stu-id="ba493-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ba493-113">子要素</span><span class="sxs-lookup"><span data-stu-id="ba493-113">Child Elements</span></span>  
  
|<span data-ttu-id="ba493-114">要素</span><span class="sxs-lookup"><span data-stu-id="ba493-114">Element</span></span>|<span data-ttu-id="ba493-115">説明</span><span class="sxs-lookup"><span data-stu-id="ba493-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba493-116">\<発表の ></span><span class="sxs-lookup"><span data-stu-id="ba493-116">\<announcementEndpoint></span></span>](announcementendpoint.md)|<span data-ttu-id="ba493-117">アナウンス エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="ba493-117">A collection of announcement endpoints.</span></span> <span data-ttu-id="ba493-118">このセクションを使用して、アナウンス メッセージの送信に使用するエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="ba493-118">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="ba493-119">\<discoveryEndpoint ></span><span class="sxs-lookup"><span data-stu-id="ba493-119">\<discoveryEndpoint></span></span>](discoveryendpoint.md)|<span data-ttu-id="ba493-120">探索エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="ba493-120">A collection of discovery endpoints.</span></span> <span data-ttu-id="ba493-121">このセクションを使用して、探索メッセージをリッスンするエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="ba493-121">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba493-122">親要素</span><span class="sxs-lookup"><span data-stu-id="ba493-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ba493-123">要素</span><span class="sxs-lookup"><span data-stu-id="ba493-123">Element</span></span>|<span data-ttu-id="ba493-124">説明</span><span class="sxs-lookup"><span data-stu-id="ba493-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba493-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ba493-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="ba493-126">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="ba493-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba493-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="ba493-127">Remarks</span></span>  
 <span data-ttu-id="ba493-128">サービスの動作構成に追加すると、この構成要素により、サービスの探索可能性はすべてのエンドポイントで有効になります。</span><span class="sxs-lookup"><span data-stu-id="ba493-128">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="ba493-129">このようなエンドポイントの探索機能をさらに構成するには、 [ \<discoveryendpoint >](discoveryendpoint.md)または[ \<発表者 >](announcementendpoint.md)子要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="ba493-129">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](discoveryendpoint.md) or [\<announcementEndpoint>](announcementendpoint.md) child elements.</span></span> <span data-ttu-id="ba493-130">サービスのお知らせを送信するために使用するエンドポイント構成 (オンライン/Hello およびオフライン/Bye) を指定してアナウンスを構成するには、[ [ \<発表](announcementendpoint.md)者の >] セクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="ba493-130">Use the [\<announcementEndpoint>](announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="ba493-131">探索メッセージをリッスンするエンドポイントを手動で指定するには、 [ \<discoveryendpoint >](discoveryendpoint.md)セクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="ba493-131">Use the [\<discoveryEndpoint>](discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba493-132">例</span><span class="sxs-lookup"><span data-stu-id="ba493-132">Example</span></span>  
 <span data-ttu-id="ba493-133">次の構成例では、CalculatorService を探索可能に指定しています。また、オプションで、使用するアナウンス エンドポイントを指定しています。</span><span class="sxs-lookup"><span data-stu-id="ba493-133">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    ...
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="udpEndpoint"
                    kind="udpAnnouncementEndpoint" />
        </announcementEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="ba493-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba493-134">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
