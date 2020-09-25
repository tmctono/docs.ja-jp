---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: b38496b77d80fcb66b1b48485a9eef6abfd72299
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198822"
---
# \<serviceDiscovery>

<span data-ttu-id="73e5c-101">サービス エンドポイントの探索可能性を指定します。</span><span class="sxs-lookup"><span data-stu-id="73e5c-101">Specifies the discoverability of service endpoints.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceDiscovery>**  
  
## <a name="syntax"></a><span data-ttu-id="73e5c-102">構文</span><span class="sxs-lookup"><span data-stu-id="73e5c-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73e5c-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="73e5c-103">Attributes and Elements</span></span>  

 <span data-ttu-id="73e5c-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="73e5c-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73e5c-105">属性</span><span class="sxs-lookup"><span data-stu-id="73e5c-105">Attributes</span></span>  

 <span data-ttu-id="73e5c-106">なし。</span><span class="sxs-lookup"><span data-stu-id="73e5c-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="73e5c-107">子要素</span><span class="sxs-lookup"><span data-stu-id="73e5c-107">Child Elements</span></span>  
  
|<span data-ttu-id="73e5c-108">要素</span><span class="sxs-lookup"><span data-stu-id="73e5c-108">Element</span></span>|<span data-ttu-id="73e5c-109">説明</span><span class="sxs-lookup"><span data-stu-id="73e5c-109">Description</span></span>|  
|-------------|-----------------|  
|[\<announcementEndpoint>](announcementendpoint.md)|<span data-ttu-id="73e5c-110">アナウンス エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="73e5c-110">A collection of announcement endpoints.</span></span> <span data-ttu-id="73e5c-111">このセクションを使用して、アナウンス メッセージの送信に使用するエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="73e5c-111">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[\<discoveryEndpoint>](discoveryendpoint.md)|<span data-ttu-id="73e5c-112">探索エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="73e5c-112">A collection of discovery endpoints.</span></span> <span data-ttu-id="73e5c-113">このセクションを使用して、探索メッセージをリッスンするエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="73e5c-113">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="73e5c-114">親要素</span><span class="sxs-lookup"><span data-stu-id="73e5c-114">Parent Elements</span></span>  
  
|<span data-ttu-id="73e5c-115">要素</span><span class="sxs-lookup"><span data-stu-id="73e5c-115">Element</span></span>|<span data-ttu-id="73e5c-116">説明</span><span class="sxs-lookup"><span data-stu-id="73e5c-116">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="73e5c-117">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="73e5c-117">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73e5c-118">解説</span><span class="sxs-lookup"><span data-stu-id="73e5c-118">Remarks</span></span>  

 <span data-ttu-id="73e5c-119">サービスの動作構成に追加すると、この構成要素により、サービスの探索可能性はすべてのエンドポイントで有効になります。</span><span class="sxs-lookup"><span data-stu-id="73e5c-119">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="73e5c-120">または子要素を使用して、このようなエンドポイントの探索機能をさらに構成でき [\<discoveryEndpoint>](discoveryendpoint.md) [\<announcementEndpoint>](announcementendpoint.md) ます。</span><span class="sxs-lookup"><span data-stu-id="73e5c-120">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](discoveryendpoint.md) or [\<announcementEndpoint>](announcementendpoint.md) child elements.</span></span> <span data-ttu-id="73e5c-121">[\<announcementEndpoint>](announcementendpoint.md)サービスのお知らせを送信するために使用するエンドポイント構成 (オンライン/Hello およびオフライン/Bye) を指定することにより、セクションを使用してアナウンスを構成します。</span><span class="sxs-lookup"><span data-stu-id="73e5c-121">Use the [\<announcementEndpoint>](announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="73e5c-122">[\<discoveryEndpoint>](discoveryendpoint.md)探索メッセージをリッスンするエンドポイントを手動で指定するには、「」セクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="73e5c-122">Use the [\<discoveryEndpoint>](discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73e5c-123">例</span><span class="sxs-lookup"><span data-stu-id="73e5c-123">Example</span></span>  

 <span data-ttu-id="73e5c-124">次の構成例では、CalculatorService を探索可能に指定しています。また、オプションで、使用するアナウンス エンドポイントを指定しています。</span><span class="sxs-lookup"><span data-stu-id="73e5c-124">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="73e5c-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="73e5c-125">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
