---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: f9d7e3a4957d2a8f30724f0bfc04e58a57fc5f7d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919268"
---
# <a name="discoveryclient"></a><span data-ttu-id="6e141-101">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="6e141-101">\<discoveryClient></span></span>
<span data-ttu-id="6e141-102">クライアント アプリケーションが実行時に探索可能なサービスを自動的に検索し、そのアドレスを見つけることができるカスタム バインドを作成するための構成要素。</span><span class="sxs-lookup"><span data-stu-id="6e141-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="6e141-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6e141-103">\<system.serviceModel></span></span>  
<span data-ttu-id="6e141-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="6e141-104">\<bindings></span></span>  
<span data-ttu-id="6e141-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="6e141-105">\<customBinding></span></span>  
<span data-ttu-id="6e141-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="6e141-106">\<binding></span></span>  
<span data-ttu-id="6e141-107">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="6e141-107">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e141-108">構文</span><span class="sxs-lookup"><span data-stu-id="6e141-108">Syntax</span></span>  
  
```xml  
<discoveryClient discoveryEndpoint="String">
  <findCriteria duration="TimeSpan"
                maxResults="Integer"
                scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String"
           namespace="String" />
    </contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e141-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6e141-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6e141-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e141-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e141-111">属性</span><span class="sxs-lookup"><span data-stu-id="6e141-111">Attributes</span></span>  
  
|<span data-ttu-id="6e141-112">属性</span><span class="sxs-lookup"><span data-stu-id="6e141-112">Attribute</span></span>|<span data-ttu-id="6e141-113">説明</span><span class="sxs-lookup"><span data-stu-id="6e141-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6e141-114">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="6e141-114">discoveryEndpoint</span></span>|<span data-ttu-id="6e141-115">クライアント アプリケーションが実行時に探索可能なサービスを自動的に検索し、そのアドレスを見つけることができる探索エンドポイントの名前を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="6e141-115">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e141-116">子要素</span><span class="sxs-lookup"><span data-stu-id="6e141-116">Child Elements</span></span>  
  
|<span data-ttu-id="6e141-117">要素</span><span class="sxs-lookup"><span data-stu-id="6e141-117">Element</span></span>|<span data-ttu-id="6e141-118">説明</span><span class="sxs-lookup"><span data-stu-id="6e141-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e141-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="6e141-119">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="6e141-120">探索サービスの検索にクライアント アプリケーションによって使用される基準を提供する構成要素。</span><span class="sxs-lookup"><span data-stu-id="6e141-120">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="6e141-121">条件は、検索条件 (探しているサービスを指定します) にグループ化し、終了条件 (検索の最後の長さ) を検索できます。</span><span class="sxs-lookup"><span data-stu-id="6e141-121">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6e141-122">親要素</span><span class="sxs-lookup"><span data-stu-id="6e141-122">Parent Elements</span></span>  
  
|<span data-ttu-id="6e141-123">要素</span><span class="sxs-lookup"><span data-stu-id="6e141-123">Element</span></span>|<span data-ttu-id="6e141-124">説明</span><span class="sxs-lookup"><span data-stu-id="6e141-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e141-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="6e141-125">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="6e141-126">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="6e141-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6e141-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e141-127">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
