---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 929c5d170bfc27160e3e15b8bd2f9f26e0ed8975
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855412"
---
# <a name="discoveryclientsettings"></a><span data-ttu-id="7d3e8-101">\<discoveryClientSettings ></span><span class="sxs-lookup"><span data-stu-id="7d3e8-101">\<discoveryClientSettings></span></span>
<span data-ttu-id="7d3e8-102">サービス探索プロセスにクライアントとして参加するためにアプリケーションが必要とする設定を格納します。</span><span class="sxs-lookup"><span data-stu-id="7d3e8-102">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="7d3e8-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7d3e8-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7d3e8-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7d3e8-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7d3e8-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="7d3e8-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="7d3e8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dynamicEndpoint >** ](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="7d3e8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="7d3e8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<standardEndpoint >** </span><span class="sxs-lookup"><span data-stu-id="7d3e8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="7d3e8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<discoveryClientSettings >**</span><span class="sxs-lookup"><span data-stu-id="7d3e8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClientSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d3e8-109">構文</span><span class="sxs-lookup"><span data-stu-id="7d3e8-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d3e8-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7d3e8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7d3e8-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d3e8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d3e8-112">属性</span><span class="sxs-lookup"><span data-stu-id="7d3e8-112">Attributes</span></span>  
  
|<span data-ttu-id="7d3e8-113">属性</span><span class="sxs-lookup"><span data-stu-id="7d3e8-113">Attribute</span></span>|<span data-ttu-id="7d3e8-114">説明</span><span class="sxs-lookup"><span data-stu-id="7d3e8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7d3e8-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="7d3e8-115">discoveryEndpoint</span></span>|<span data-ttu-id="7d3e8-116">クライアント アプリケーションが実行時に探索可能なサービスを自動的に検索し、そのアドレスを見つけることができる探索エンドポイントの名前を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="7d3e8-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d3e8-117">子要素</span><span class="sxs-lookup"><span data-stu-id="7d3e8-117">Child Elements</span></span>  
  
|<span data-ttu-id="7d3e8-118">要素</span><span class="sxs-lookup"><span data-stu-id="7d3e8-118">Element</span></span>|<span data-ttu-id="7d3e8-119">説明</span><span class="sxs-lookup"><span data-stu-id="7d3e8-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d3e8-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="7d3e8-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="7d3e8-121">探索サービスの検索にクライアント アプリケーションによって使用される基準を提供する構成要素。</span><span class="sxs-lookup"><span data-stu-id="7d3e8-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="7d3e8-122">条件は、検索条件 (探しているサービスを指定します) にグループ化し、終了条件 (検索の最後の長さ) を検索できます。</span><span class="sxs-lookup"><span data-stu-id="7d3e8-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7d3e8-123">親要素</span><span class="sxs-lookup"><span data-stu-id="7d3e8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7d3e8-124">要素</span><span class="sxs-lookup"><span data-stu-id="7d3e8-124">Element</span></span>|<span data-ttu-id="7d3e8-125">説明</span><span class="sxs-lookup"><span data-stu-id="7d3e8-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d3e8-126">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="7d3e8-126">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="7d3e8-127">アプリケーションが実行時に動的にエンドポイント アドレスを検索するクライアント プログラムとして機能するための情報を格納する標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="7d3e8-127">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7d3e8-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d3e8-128">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
