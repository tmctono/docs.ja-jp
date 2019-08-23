---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 2783796166d56be3d4983ab09a60d62491699fe3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925860"
---
# <a name="discoveryclientsettings"></a><span data-ttu-id="d9ace-101">\<discoveryClientSettings ></span><span class="sxs-lookup"><span data-stu-id="d9ace-101">\<discoveryClientSettings></span></span>
<span data-ttu-id="d9ace-102">サービス探索プロセスにクライアントとして参加するためにアプリケーションが必要とする設定を格納します。</span><span class="sxs-lookup"><span data-stu-id="d9ace-102">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="d9ace-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d9ace-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d9ace-104">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="d9ace-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9ace-105">構文</span><span class="sxs-lookup"><span data-stu-id="d9ace-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9ace-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d9ace-106">Attributes and Elements</span></span>  
 <span data-ttu-id="d9ace-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d9ace-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9ace-108">属性</span><span class="sxs-lookup"><span data-stu-id="d9ace-108">Attributes</span></span>  
  
|<span data-ttu-id="d9ace-109">属性</span><span class="sxs-lookup"><span data-stu-id="d9ace-109">Attribute</span></span>|<span data-ttu-id="d9ace-110">説明</span><span class="sxs-lookup"><span data-stu-id="d9ace-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d9ace-111">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="d9ace-111">discoveryEndpoint</span></span>|<span data-ttu-id="d9ace-112">クライアント アプリケーションが実行時に探索可能なサービスを自動的に検索し、そのアドレスを見つけることができる探索エンドポイントの名前を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="d9ace-112">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d9ace-113">子要素</span><span class="sxs-lookup"><span data-stu-id="d9ace-113">Child Elements</span></span>  
  
|<span data-ttu-id="d9ace-114">要素</span><span class="sxs-lookup"><span data-stu-id="d9ace-114">Element</span></span>|<span data-ttu-id="d9ace-115">説明</span><span class="sxs-lookup"><span data-stu-id="d9ace-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9ace-116">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="d9ace-116">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="d9ace-117">探索サービスの検索にクライアント アプリケーションによって使用される基準を提供する構成要素。</span><span class="sxs-lookup"><span data-stu-id="d9ace-117">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="d9ace-118">条件は、検索条件 (探しているサービスを指定します) にグループ化し、終了条件 (検索の最後の長さ) を検索できます。</span><span class="sxs-lookup"><span data-stu-id="d9ace-118">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d9ace-119">親要素</span><span class="sxs-lookup"><span data-stu-id="d9ace-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d9ace-120">要素</span><span class="sxs-lookup"><span data-stu-id="d9ace-120">Element</span></span>|<span data-ttu-id="d9ace-121">説明</span><span class="sxs-lookup"><span data-stu-id="d9ace-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9ace-122">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="d9ace-122">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="d9ace-123">アプリケーションが実行時に動的にエンドポイント アドレスを検索するクライアント プログラムとして機能するための情報を格納する標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="d9ace-123">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d9ace-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9ace-124">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
