---
title: <add> の <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: c29e47f688118e34fbdb4deb396c930d478f0582
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673603"
---
# <a name="add-of-scopes"></a><span data-ttu-id="02ae3-102">\<追加 > の\<スコープ ></span><span class="sxs-lookup"><span data-stu-id="02ae3-102">\<add> of \<scopes></span></span>
<span data-ttu-id="02ae3-103">クエリの実行中に、サービス エンドポイントのフィルター処理に使用できるカスタム スコープ URI を追加します。</span><span class="sxs-lookup"><span data-stu-id="02ae3-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="02ae3-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="02ae3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="02ae3-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="02ae3-105">\<behaviors></span></span>  
<span data-ttu-id="02ae3-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="02ae3-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="02ae3-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="02ae3-107">\<behavior></span></span>  
<span data-ttu-id="02ae3-108">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="02ae3-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="02ae3-109">\<scopes></span><span class="sxs-lookup"><span data-stu-id="02ae3-109">\<scopes></span></span>  
<span data-ttu-id="02ae3-110">\<add></span><span class="sxs-lookup"><span data-stu-id="02ae3-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02ae3-111">構文</span><span class="sxs-lookup"><span data-stu-id="02ae3-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02ae3-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="02ae3-112">Attributes and Elements</span></span>  
 <span data-ttu-id="02ae3-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="02ae3-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02ae3-114">属性</span><span class="sxs-lookup"><span data-stu-id="02ae3-114">Attributes</span></span>  
  
|<span data-ttu-id="02ae3-115">属性</span><span class="sxs-lookup"><span data-stu-id="02ae3-115">Attribute</span></span>|<span data-ttu-id="02ae3-116">説明</span><span class="sxs-lookup"><span data-stu-id="02ae3-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02ae3-117">スコープ</span><span class="sxs-lookup"><span data-stu-id="02ae3-117">scope</span></span>|<span data-ttu-id="02ae3-118">サービス検索の一致条件に使用できるエンドポイントのスコープ情報を格納する URI。</span><span class="sxs-lookup"><span data-stu-id="02ae3-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02ae3-119">子要素</span><span class="sxs-lookup"><span data-stu-id="02ae3-119">Child Elements</span></span>  
 <span data-ttu-id="02ae3-120">なし。</span><span class="sxs-lookup"><span data-stu-id="02ae3-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02ae3-121">親要素</span><span class="sxs-lookup"><span data-stu-id="02ae3-121">Parent Elements</span></span>  
  
|<span data-ttu-id="02ae3-122">要素</span><span class="sxs-lookup"><span data-stu-id="02ae3-122">Element</span></span>|<span data-ttu-id="02ae3-123">説明</span><span class="sxs-lookup"><span data-stu-id="02ae3-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02ae3-124">\<scopes></span><span class="sxs-lookup"><span data-stu-id="02ae3-124">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="02ae3-125">クエリの実行中に、サービス エンドポイントのフィルター処理に使用できるカスタム スコープ URI を指定する構成要素のコレクションを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="02ae3-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="02ae3-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="02ae3-126">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
