---
title: <add> の <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: b190cb72e21d47bdc62aab2daba0f6eea1ee04ac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926630"
---
# <a name="add-of-scopes"></a><span data-ttu-id="8387f-102">\<スコープの > \<を追加する ></span><span class="sxs-lookup"><span data-stu-id="8387f-102">\<add> of \<scopes></span></span>
<span data-ttu-id="8387f-103">クエリの実行中に、サービス エンドポイントのフィルター処理に使用できるカスタム スコープ URI を追加します。</span><span class="sxs-lookup"><span data-stu-id="8387f-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="8387f-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8387f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8387f-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="8387f-105">\<behaviors></span></span>  
<span data-ttu-id="8387f-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="8387f-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="8387f-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8387f-107">\<behavior></span></span>  
<span data-ttu-id="8387f-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="8387f-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="8387f-109">\<スコープ ></span><span class="sxs-lookup"><span data-stu-id="8387f-109">\<scopes></span></span>  
<span data-ttu-id="8387f-110">\<add></span><span class="sxs-lookup"><span data-stu-id="8387f-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8387f-111">構文</span><span class="sxs-lookup"><span data-stu-id="8387f-111">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI" />
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8387f-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8387f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8387f-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8387f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8387f-114">属性</span><span class="sxs-lookup"><span data-stu-id="8387f-114">Attributes</span></span>  
  
|<span data-ttu-id="8387f-115">属性</span><span class="sxs-lookup"><span data-stu-id="8387f-115">Attribute</span></span>|<span data-ttu-id="8387f-116">説明</span><span class="sxs-lookup"><span data-stu-id="8387f-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8387f-117">スコープ (scope)</span><span class="sxs-lookup"><span data-stu-id="8387f-117">scope</span></span>|<span data-ttu-id="8387f-118">サービス検索の一致条件に使用できるエンドポイントのスコープ情報を格納する URI。</span><span class="sxs-lookup"><span data-stu-id="8387f-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8387f-119">子要素</span><span class="sxs-lookup"><span data-stu-id="8387f-119">Child Elements</span></span>  
 <span data-ttu-id="8387f-120">なし。</span><span class="sxs-lookup"><span data-stu-id="8387f-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8387f-121">親要素</span><span class="sxs-lookup"><span data-stu-id="8387f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8387f-122">要素</span><span class="sxs-lookup"><span data-stu-id="8387f-122">Element</span></span>|<span data-ttu-id="8387f-123">説明</span><span class="sxs-lookup"><span data-stu-id="8387f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8387f-124">\<スコープ ></span><span class="sxs-lookup"><span data-stu-id="8387f-124">\<scopes></span></span>](scopes.md)|<span data-ttu-id="8387f-125">クエリの実行中に、サービス エンドポイントのフィルター処理に使用できるカスタム スコープ URI を指定する構成要素のコレクションを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="8387f-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8387f-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="8387f-126">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
