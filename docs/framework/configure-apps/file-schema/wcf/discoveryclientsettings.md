---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 0b014a9d797ded61949a374486824ee3ebc34661
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136254"
---
# <a name="discoveryclientsettings"></a><span data-ttu-id="af060-101">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="af060-101">\<discoveryClientSettings></span></span>
<span data-ttu-id="af060-102">サービス探索プロセスにクライアントとして参加するためにアプリケーションが必要とする設定を格納します。</span><span class="sxs-lookup"><span data-stu-id="af060-102">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="af060-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="af060-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="af060-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="af060-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af060-105">構文</span><span class="sxs-lookup"><span data-stu-id="af060-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af060-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="af060-106">Attributes and Elements</span></span>  
 <span data-ttu-id="af060-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="af060-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af060-108">属性</span><span class="sxs-lookup"><span data-stu-id="af060-108">Attributes</span></span>  
  
|<span data-ttu-id="af060-109">属性</span><span class="sxs-lookup"><span data-stu-id="af060-109">Attribute</span></span>|<span data-ttu-id="af060-110">説明</span><span class="sxs-lookup"><span data-stu-id="af060-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="af060-111">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="af060-111">discoveryEndpoint</span></span>|<span data-ttu-id="af060-112">クライアント アプリケーションが実行時に探索可能なサービスを自動的に検索し、そのアドレスを見つけることができる探索エンドポイントの名前を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="af060-112">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af060-113">子要素</span><span class="sxs-lookup"><span data-stu-id="af060-113">Child Elements</span></span>  
  
|<span data-ttu-id="af060-114">要素</span><span class="sxs-lookup"><span data-stu-id="af060-114">Element</span></span>|<span data-ttu-id="af060-115">説明</span><span class="sxs-lookup"><span data-stu-id="af060-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af060-116">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="af060-116">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="af060-117">探索サービスの検索にクライアント アプリケーションによって使用される基準を提供する構成要素。</span><span class="sxs-lookup"><span data-stu-id="af060-117">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="af060-118">条件は、(探しているサービスの種類を指定して) 検索条件にグループ化することができ、検索 (検索持続期間)、終了条件。</span><span class="sxs-lookup"><span data-stu-id="af060-118">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="af060-119">親要素</span><span class="sxs-lookup"><span data-stu-id="af060-119">Parent Elements</span></span>  
  
|<span data-ttu-id="af060-120">要素</span><span class="sxs-lookup"><span data-stu-id="af060-120">Element</span></span>|<span data-ttu-id="af060-121">説明</span><span class="sxs-lookup"><span data-stu-id="af060-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af060-122">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="af060-122">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="af060-123">アプリケーションが実行時に動的にエンドポイント アドレスを検索するクライアント プログラムとして機能するための情報を格納する標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="af060-123">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af060-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="af060-124">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
