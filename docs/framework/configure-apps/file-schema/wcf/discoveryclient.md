---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 71305720cad0206ec3dabb1863e2f1cd72eb85f0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739040"
---
# <a name="discoveryclient"></a><span data-ttu-id="c9de1-101">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="c9de1-101">\<discoveryClient></span></span>
<span data-ttu-id="c9de1-102">クライアント アプリケーションが実行時に探索可能なサービスを自動的に検索し、そのアドレスを見つけることができるカスタム バインドを作成するための構成要素。</span><span class="sxs-lookup"><span data-stu-id="c9de1-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="c9de1-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c9de1-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c9de1-104">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="c9de1-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c9de1-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="c9de1-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="c9de1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="c9de1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="c9de1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="c9de1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="c9de1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**discoveryClient >**</span><span class="sxs-lookup"><span data-stu-id="c9de1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClient>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9de1-109">構文</span><span class="sxs-lookup"><span data-stu-id="c9de1-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9de1-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c9de1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c9de1-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9de1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9de1-112">属性</span><span class="sxs-lookup"><span data-stu-id="c9de1-112">Attributes</span></span>  
  
|<span data-ttu-id="c9de1-113">属性</span><span class="sxs-lookup"><span data-stu-id="c9de1-113">Attribute</span></span>|<span data-ttu-id="c9de1-114">説明</span><span class="sxs-lookup"><span data-stu-id="c9de1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c9de1-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="c9de1-115">discoveryEndpoint</span></span>|<span data-ttu-id="c9de1-116">クライアント アプリケーションが実行時に探索可能なサービスを自動的に検索し、そのアドレスを見つけることができる探索エンドポイントの名前を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="c9de1-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c9de1-117">子要素</span><span class="sxs-lookup"><span data-stu-id="c9de1-117">Child Elements</span></span>  
  
|<span data-ttu-id="c9de1-118">要素</span><span class="sxs-lookup"><span data-stu-id="c9de1-118">Element</span></span>|<span data-ttu-id="c9de1-119">説明</span><span class="sxs-lookup"><span data-stu-id="c9de1-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9de1-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="c9de1-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="c9de1-121">探索サービスの検索にクライアント アプリケーションによって使用される基準を提供する構成要素。</span><span class="sxs-lookup"><span data-stu-id="c9de1-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="c9de1-122">条件は、検索条件 (探しているサービスを指定します) にグループ化し、終了条件 (検索の最後の長さ) を検索できます。</span><span class="sxs-lookup"><span data-stu-id="c9de1-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c9de1-123">親要素</span><span class="sxs-lookup"><span data-stu-id="c9de1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c9de1-124">要素</span><span class="sxs-lookup"><span data-stu-id="c9de1-124">Element</span></span>|<span data-ttu-id="c9de1-125">説明</span><span class="sxs-lookup"><span data-stu-id="c9de1-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9de1-126">\<binding ></span><span class="sxs-lookup"><span data-stu-id="c9de1-126">\<binding></span></span>](bindings.md)|<span data-ttu-id="c9de1-127">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="c9de1-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c9de1-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9de1-128">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
