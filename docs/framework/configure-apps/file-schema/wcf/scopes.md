---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 8bc720238ca3039106345783381cd26134fc46b5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213078"
---
# <a name="scopes"></a><span data-ttu-id="c6961-101">\<scopes></span><span class="sxs-lookup"><span data-stu-id="c6961-101">\<scopes></span></span>
<span data-ttu-id="c6961-102">クエリの実行中に、サービス エンドポイントのフィルター処理に使用できるカスタム スコープ URI を指定する構成要素のコレクションを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="c6961-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="c6961-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c6961-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c6961-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="c6961-104">\<behaviors></span></span>  
<span data-ttu-id="c6961-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="c6961-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="c6961-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c6961-106">\<behavior></span></span>  
<span data-ttu-id="c6961-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="c6961-107">\<endpointDiscovery></span></span>  
<span data-ttu-id="c6961-108">\<scopes></span><span class="sxs-lookup"><span data-stu-id="c6961-108">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6961-109">構文</span><span class="sxs-lookup"><span data-stu-id="c6961-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6961-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c6961-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c6961-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c6961-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6961-112">属性</span><span class="sxs-lookup"><span data-stu-id="c6961-112">Attributes</span></span>  
 <span data-ttu-id="c6961-113">なし。</span><span class="sxs-lookup"><span data-stu-id="c6961-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c6961-114">子要素</span><span class="sxs-lookup"><span data-stu-id="c6961-114">Child Elements</span></span>  
  
|<span data-ttu-id="c6961-115">属性</span><span class="sxs-lookup"><span data-stu-id="c6961-115">Attribute</span></span>|<span data-ttu-id="c6961-116">説明</span><span class="sxs-lookup"><span data-stu-id="c6961-116">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="c6961-117">\<add></span><span class="sxs-lookup"><span data-stu-id="c6961-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="c6961-118">サービス検索の一致条件に使用できるエンドポイントのスコープ情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="c6961-118">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c6961-119">親要素</span><span class="sxs-lookup"><span data-stu-id="c6961-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c6961-120">要素</span><span class="sxs-lookup"><span data-stu-id="c6961-120">Element</span></span>|<span data-ttu-id="c6961-121">説明</span><span class="sxs-lookup"><span data-stu-id="c6961-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6961-122">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="c6961-122">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="c6961-123">エンドポイントのさまざまな探索設定を指定します (探索可能性、スコープ、メタデータに対するカスタム拡張など)。</span><span class="sxs-lookup"><span data-stu-id="c6961-123">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c6961-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6961-124">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
