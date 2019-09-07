---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 57e9e19025db5e1fa588f073fdf30de09837a25d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399935"
---
# <a name="scopes"></a><span data-ttu-id="ff2ae-101">\<スコープ ></span><span class="sxs-lookup"><span data-stu-id="ff2ae-101">\<scopes></span></span>
<span data-ttu-id="ff2ae-102">クエリの実行中に、サービス エンドポイントのフィルター処理に使用できるカスタム スコープ URI を指定する構成要素のコレクションを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="ff2ae-102">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="ff2ae-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ff2ae-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ff2ae-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ff2ae-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ff2ae-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ff2ae-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="ff2ae-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ff2ae-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="ff2ae-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="ff2ae-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="ff2ae-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointDiscovery >** ](endpointdiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="ff2ae-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)</span></span>\
<span data-ttu-id="ff2ae-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<スコープ >**</span><span class="sxs-lookup"><span data-stu-id="ff2ae-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopes>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff2ae-110">構文</span><span class="sxs-lookup"><span data-stu-id="ff2ae-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff2ae-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ff2ae-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ff2ae-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ff2ae-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff2ae-113">属性</span><span class="sxs-lookup"><span data-stu-id="ff2ae-113">Attributes</span></span>  
 <span data-ttu-id="ff2ae-114">なし。</span><span class="sxs-lookup"><span data-stu-id="ff2ae-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ff2ae-115">子要素</span><span class="sxs-lookup"><span data-stu-id="ff2ae-115">Child Elements</span></span>  
  
|<span data-ttu-id="ff2ae-116">属性</span><span class="sxs-lookup"><span data-stu-id="ff2ae-116">Attribute</span></span>|<span data-ttu-id="ff2ae-117">説明</span><span class="sxs-lookup"><span data-stu-id="ff2ae-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="ff2ae-118">\<add></span><span class="sxs-lookup"><span data-stu-id="ff2ae-118">\<add></span></span>](add-of-scopes.md)|<span data-ttu-id="ff2ae-119">サービス検索の一致条件に使用できるエンドポイントのスコープ情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="ff2ae-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ff2ae-120">親要素</span><span class="sxs-lookup"><span data-stu-id="ff2ae-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ff2ae-121">要素</span><span class="sxs-lookup"><span data-stu-id="ff2ae-121">Element</span></span>|<span data-ttu-id="ff2ae-122">説明</span><span class="sxs-lookup"><span data-stu-id="ff2ae-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff2ae-123">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="ff2ae-123">\<endpointDiscovery></span></span>](endpointdiscovery.md)|<span data-ttu-id="ff2ae-124">エンドポイントのさまざまな探索設定を指定します (探索可能性、スコープ、メタデータに対するカスタム拡張など)。</span><span class="sxs-lookup"><span data-stu-id="ff2ae-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ff2ae-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff2ae-125">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
