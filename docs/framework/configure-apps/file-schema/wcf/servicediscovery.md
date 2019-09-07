---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 7ac067e84f2a4d2724e3d8f2d0af9b220fd15538
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399648"
---
# <a name="servicediscovery"></a><span data-ttu-id="98a8a-101">\<serviceDiscovery ></span><span class="sxs-lookup"><span data-stu-id="98a8a-101">\<serviceDiscovery></span></span>
<span data-ttu-id="98a8a-102">サービス エンドポイントの探索可能性を指定します。</span><span class="sxs-lookup"><span data-stu-id="98a8a-102">Specifies the discoverability of service endpoints.</span></span>  
  
<span data-ttu-id="98a8a-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="98a8a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="98a8a-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="98a8a-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="98a8a-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="98a8a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="98a8a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="98a8a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="98a8a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="98a8a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="98a8a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceDiscovery >**</span><span class="sxs-lookup"><span data-stu-id="98a8a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceDiscovery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98a8a-109">構文</span><span class="sxs-lookup"><span data-stu-id="98a8a-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="98a8a-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="98a8a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="98a8a-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="98a8a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="98a8a-112">属性</span><span class="sxs-lookup"><span data-stu-id="98a8a-112">Attributes</span></span>  
 <span data-ttu-id="98a8a-113">なし。</span><span class="sxs-lookup"><span data-stu-id="98a8a-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="98a8a-114">子要素</span><span class="sxs-lookup"><span data-stu-id="98a8a-114">Child Elements</span></span>  
  
|<span data-ttu-id="98a8a-115">要素</span><span class="sxs-lookup"><span data-stu-id="98a8a-115">Element</span></span>|<span data-ttu-id="98a8a-116">説明</span><span class="sxs-lookup"><span data-stu-id="98a8a-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="98a8a-117">\<発表の ></span><span class="sxs-lookup"><span data-stu-id="98a8a-117">\<announcementEndpoint></span></span>](announcementendpoint.md)|<span data-ttu-id="98a8a-118">アナウンス エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="98a8a-118">A collection of announcement endpoints.</span></span> <span data-ttu-id="98a8a-119">このセクションを使用して、アナウンス メッセージの送信に使用するエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="98a8a-119">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="98a8a-120">\<discoveryEndpoint ></span><span class="sxs-lookup"><span data-stu-id="98a8a-120">\<discoveryEndpoint></span></span>](discoveryendpoint.md)|<span data-ttu-id="98a8a-121">探索エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="98a8a-121">A collection of discovery endpoints.</span></span> <span data-ttu-id="98a8a-122">このセクションを使用して、探索メッセージをリッスンするエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="98a8a-122">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="98a8a-123">親要素</span><span class="sxs-lookup"><span data-stu-id="98a8a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="98a8a-124">要素</span><span class="sxs-lookup"><span data-stu-id="98a8a-124">Element</span></span>|<span data-ttu-id="98a8a-125">説明</span><span class="sxs-lookup"><span data-stu-id="98a8a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="98a8a-126">\<behavior></span><span class="sxs-lookup"><span data-stu-id="98a8a-126">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="98a8a-127">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="98a8a-127">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98a8a-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="98a8a-128">Remarks</span></span>  
 <span data-ttu-id="98a8a-129">サービスの動作構成に追加すると、この構成要素により、サービスの探索可能性はすべてのエンドポイントで有効になります。</span><span class="sxs-lookup"><span data-stu-id="98a8a-129">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="98a8a-130">このようなエンドポイントの探索機能をさらに構成するには、 [ \<discoveryendpoint >](discoveryendpoint.md)または[ \<発表者 >](announcementendpoint.md)子要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="98a8a-130">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](discoveryendpoint.md) or [\<announcementEndpoint>](announcementendpoint.md) child elements.</span></span> <span data-ttu-id="98a8a-131">サービスのお知らせを送信するために使用するエンドポイント構成 (オンライン/Hello およびオフライン/Bye) を指定してアナウンスを構成するには、[ [ \<発表](announcementendpoint.md)者の >] セクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="98a8a-131">Use the [\<announcementEndpoint>](announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="98a8a-132">探索メッセージをリッスンするエンドポイントを手動で指定するには、 [ \<discoveryendpoint >](discoveryendpoint.md)セクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="98a8a-132">Use the [\<discoveryEndpoint>](discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98a8a-133">例</span><span class="sxs-lookup"><span data-stu-id="98a8a-133">Example</span></span>  
 <span data-ttu-id="98a8a-134">次の構成例では、CalculatorService を探索可能に指定しています。また、オプションで、使用するアナウンス エンドポイントを指定しています。</span><span class="sxs-lookup"><span data-stu-id="98a8a-134">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="98a8a-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="98a8a-135">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
