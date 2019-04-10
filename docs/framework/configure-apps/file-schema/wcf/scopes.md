---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 8bc720238ca3039106345783381cd26134fc46b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213078"
---
# <a name="scopes"></a><span data-ttu-id="97b5d-101">\<scopes></span><span class="sxs-lookup"><span data-stu-id="97b5d-101">\<scopes></span></span>
<span data-ttu-id="97b5d-102">クエリの実行中に、サービス エンドポイントのフィルター処理に使用できるカスタム スコープ URI を指定する構成要素のコレクションを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="97b5d-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="97b5d-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="97b5d-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="97b5d-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="97b5d-104">\<behaviors></span></span>  
<span data-ttu-id="97b5d-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="97b5d-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="97b5d-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="97b5d-106">\<behavior></span></span>  
<span data-ttu-id="97b5d-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="97b5d-107">\<endpointDiscovery></span></span>  
<span data-ttu-id="97b5d-108">\<scopes></span><span class="sxs-lookup"><span data-stu-id="97b5d-108">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97b5d-109">構文</span><span class="sxs-lookup"><span data-stu-id="97b5d-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97b5d-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="97b5d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="97b5d-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="97b5d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97b5d-112">属性</span><span class="sxs-lookup"><span data-stu-id="97b5d-112">Attributes</span></span>  
 <span data-ttu-id="97b5d-113">なし。</span><span class="sxs-lookup"><span data-stu-id="97b5d-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="97b5d-114">子要素</span><span class="sxs-lookup"><span data-stu-id="97b5d-114">Child Elements</span></span>  
  
|<span data-ttu-id="97b5d-115">属性</span><span class="sxs-lookup"><span data-stu-id="97b5d-115">Attribute</span></span>|<span data-ttu-id="97b5d-116">説明</span><span class="sxs-lookup"><span data-stu-id="97b5d-116">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="97b5d-117">\<add></span><span class="sxs-lookup"><span data-stu-id="97b5d-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="97b5d-118">サービス検索の一致条件に使用できるエンドポイントのスコープ情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="97b5d-118">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="97b5d-119">親要素</span><span class="sxs-lookup"><span data-stu-id="97b5d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="97b5d-120">要素</span><span class="sxs-lookup"><span data-stu-id="97b5d-120">Element</span></span>|<span data-ttu-id="97b5d-121">説明</span><span class="sxs-lookup"><span data-stu-id="97b5d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97b5d-122">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="97b5d-122">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="97b5d-123">エンドポイントのさまざまな探索設定を指定します (探索可能性、スコープ、メタデータに対するカスタム拡張など)。</span><span class="sxs-lookup"><span data-stu-id="97b5d-123">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="97b5d-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="97b5d-124">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
