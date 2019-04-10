---
title: <add> (行中)  <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: c29e47f688118e34fbdb4deb396c930d478f0582
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187085"
---
# <a name="add-of-scopes"></a><span data-ttu-id="cedbd-102">\<追加 > の\<スコープ ></span><span class="sxs-lookup"><span data-stu-id="cedbd-102">\<add> of \<scopes></span></span>
<span data-ttu-id="cedbd-103">クエリの実行中に、サービス エンドポイントのフィルター処理に使用できるカスタム スコープ URI を追加します。</span><span class="sxs-lookup"><span data-stu-id="cedbd-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="cedbd-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="cedbd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cedbd-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="cedbd-105">\<behaviors></span></span>  
<span data-ttu-id="cedbd-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="cedbd-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="cedbd-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="cedbd-107">\<behavior></span></span>  
<span data-ttu-id="cedbd-108">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="cedbd-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="cedbd-109">\<scopes></span><span class="sxs-lookup"><span data-stu-id="cedbd-109">\<scopes></span></span>  
<span data-ttu-id="cedbd-110">\<add></span><span class="sxs-lookup"><span data-stu-id="cedbd-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cedbd-111">構文</span><span class="sxs-lookup"><span data-stu-id="cedbd-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cedbd-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cedbd-112">Attributes and Elements</span></span>  
 <span data-ttu-id="cedbd-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cedbd-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cedbd-114">属性</span><span class="sxs-lookup"><span data-stu-id="cedbd-114">Attributes</span></span>  
  
|<span data-ttu-id="cedbd-115">属性</span><span class="sxs-lookup"><span data-stu-id="cedbd-115">Attribute</span></span>|<span data-ttu-id="cedbd-116">説明</span><span class="sxs-lookup"><span data-stu-id="cedbd-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cedbd-117">スコープ</span><span class="sxs-lookup"><span data-stu-id="cedbd-117">scope</span></span>|<span data-ttu-id="cedbd-118">サービス検索の一致条件に使用できるエンドポイントのスコープ情報を格納する URI。</span><span class="sxs-lookup"><span data-stu-id="cedbd-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cedbd-119">子要素</span><span class="sxs-lookup"><span data-stu-id="cedbd-119">Child Elements</span></span>  
 <span data-ttu-id="cedbd-120">なし。</span><span class="sxs-lookup"><span data-stu-id="cedbd-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cedbd-121">親要素</span><span class="sxs-lookup"><span data-stu-id="cedbd-121">Parent Elements</span></span>  
  
|<span data-ttu-id="cedbd-122">要素</span><span class="sxs-lookup"><span data-stu-id="cedbd-122">Element</span></span>|<span data-ttu-id="cedbd-123">説明</span><span class="sxs-lookup"><span data-stu-id="cedbd-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cedbd-124">\<scopes></span><span class="sxs-lookup"><span data-stu-id="cedbd-124">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="cedbd-125">クエリの実行中に、サービス エンドポイントのフィルター処理に使用できるカスタム スコープ URI を指定する構成要素のコレクションを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="cedbd-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cedbd-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="cedbd-126">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
