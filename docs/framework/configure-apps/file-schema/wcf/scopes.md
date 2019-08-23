---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: dd6513930798e9e1ab263f75c9350511c2dcdcd5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935182"
---
# <a name="scopes"></a><span data-ttu-id="e7057-101">\<スコープ ></span><span class="sxs-lookup"><span data-stu-id="e7057-101">\<scopes></span></span>
<span data-ttu-id="e7057-102">クエリの実行中に、サービス エンドポイントのフィルター処理に使用できるカスタム スコープ URI を指定する構成要素のコレクションを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="e7057-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="e7057-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e7057-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e7057-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="e7057-104">\<behaviors></span></span>  
<span data-ttu-id="e7057-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="e7057-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="e7057-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e7057-106">\<behavior></span></span>  
<span data-ttu-id="e7057-107">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="e7057-107">\<endpointDiscovery></span></span>  
<span data-ttu-id="e7057-108">\<スコープ ></span><span class="sxs-lookup"><span data-stu-id="e7057-108">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7057-109">構文</span><span class="sxs-lookup"><span data-stu-id="e7057-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7057-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e7057-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e7057-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e7057-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7057-112">属性</span><span class="sxs-lookup"><span data-stu-id="e7057-112">Attributes</span></span>  
 <span data-ttu-id="e7057-113">なし。</span><span class="sxs-lookup"><span data-stu-id="e7057-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e7057-114">子要素</span><span class="sxs-lookup"><span data-stu-id="e7057-114">Child Elements</span></span>  
  
|<span data-ttu-id="e7057-115">属性</span><span class="sxs-lookup"><span data-stu-id="e7057-115">Attribute</span></span>|<span data-ttu-id="e7057-116">説明</span><span class="sxs-lookup"><span data-stu-id="e7057-116">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="e7057-117">\<add></span><span class="sxs-lookup"><span data-stu-id="e7057-117">\<add></span></span>](add-of-scopes.md)|<span data-ttu-id="e7057-118">サービス検索の一致条件に使用できるエンドポイントのスコープ情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="e7057-118">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e7057-119">親要素</span><span class="sxs-lookup"><span data-stu-id="e7057-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e7057-120">要素</span><span class="sxs-lookup"><span data-stu-id="e7057-120">Element</span></span>|<span data-ttu-id="e7057-121">説明</span><span class="sxs-lookup"><span data-stu-id="e7057-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7057-122">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="e7057-122">\<endpointDiscovery></span></span>](endpointdiscovery.md)|<span data-ttu-id="e7057-123">エンドポイントのさまざまな探索設定を指定します (探索可能性、スコープ、メタデータに対するカスタム拡張など)。</span><span class="sxs-lookup"><span data-stu-id="e7057-123">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e7057-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7057-124">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
