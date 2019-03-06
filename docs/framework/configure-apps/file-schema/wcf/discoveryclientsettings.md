---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 5b60c7281b92a487ba3ee275f7405cb82bd6cd87
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355000"
---
# <a name="discoveryclientsettings"></a><span data-ttu-id="5e954-101">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="5e954-101">\<discoveryClientSettings></span></span>
<span data-ttu-id="5e954-102">サービス探索プロセスにクライアントとして参加するためにアプリケーションが必要とする設定を格納します。</span><span class="sxs-lookup"><span data-stu-id="5e954-102">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="5e954-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5e954-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5e954-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="5e954-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e954-105">構文</span><span class="sxs-lookup"><span data-stu-id="5e954-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e954-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5e954-106">Attributes and Elements</span></span>  
 <span data-ttu-id="5e954-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5e954-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e954-108">属性</span><span class="sxs-lookup"><span data-stu-id="5e954-108">Attributes</span></span>  
  
|<span data-ttu-id="5e954-109">属性</span><span class="sxs-lookup"><span data-stu-id="5e954-109">Attribute</span></span>|<span data-ttu-id="5e954-110">説明</span><span class="sxs-lookup"><span data-stu-id="5e954-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e954-111">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="5e954-111">discoveryEndpoint</span></span>|<span data-ttu-id="5e954-112">クライアント アプリケーションが実行時に探索可能なサービスを自動的に検索し、そのアドレスを見つけることができる探索エンドポイントの名前を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="5e954-112">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5e954-113">子要素</span><span class="sxs-lookup"><span data-stu-id="5e954-113">Child Elements</span></span>  
  
|<span data-ttu-id="5e954-114">要素</span><span class="sxs-lookup"><span data-stu-id="5e954-114">Element</span></span>|<span data-ttu-id="5e954-115">説明</span><span class="sxs-lookup"><span data-stu-id="5e954-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e954-116">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="5e954-116">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="5e954-117">探索サービスの検索にクライアント アプリケーションによって使用される基準を提供する構成要素。</span><span class="sxs-lookup"><span data-stu-id="5e954-117">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="5e954-118">条件は、(探しているサービスの種類を指定して) 検索条件にグループ化することができ、検索 (検索持続期間)、終了条件。</span><span class="sxs-lookup"><span data-stu-id="5e954-118">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5e954-119">親要素</span><span class="sxs-lookup"><span data-stu-id="5e954-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5e954-120">要素</span><span class="sxs-lookup"><span data-stu-id="5e954-120">Element</span></span>|<span data-ttu-id="5e954-121">説明</span><span class="sxs-lookup"><span data-stu-id="5e954-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e954-122">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="5e954-122">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="5e954-123">アプリケーションが実行時に動的にエンドポイント アドレスを検索するクライアント プログラムとして機能するための情報を格納する標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="5e954-123">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5e954-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e954-124">See also</span></span>
- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
