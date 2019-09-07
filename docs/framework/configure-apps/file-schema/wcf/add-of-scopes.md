---
title: <add> の <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: bcde6b18c34dccf1716c809dddeb45b1b4da90f0
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398303"
---
# <a name="add-of-scopes"></a><span data-ttu-id="93af8-102">\<スコープの > \<を追加する ></span><span class="sxs-lookup"><span data-stu-id="93af8-102">\<add> of \<scopes></span></span>
<span data-ttu-id="93af8-103">クエリの実行中に、サービス エンドポイントのフィルター処理に使用できるカスタム スコープ URI を追加します。</span><span class="sxs-lookup"><span data-stu-id="93af8-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="93af8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="93af8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="93af8-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="93af8-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="93af8-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="93af8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="93af8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="93af8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="93af8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="93af8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="93af8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointDiscovery >** ](endpointdiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="93af8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)</span></span>\
<span data-ttu-id="93af8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<スコープ >** ](scopes.md)</span><span class="sxs-lookup"><span data-stu-id="93af8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopes>**](scopes.md)</span></span>\
<span data-ttu-id="93af8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の追加**</span><span class="sxs-lookup"><span data-stu-id="93af8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93af8-112">構文</span><span class="sxs-lookup"><span data-stu-id="93af8-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93af8-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="93af8-113">Attributes and Elements</span></span>  
 <span data-ttu-id="93af8-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="93af8-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93af8-115">属性</span><span class="sxs-lookup"><span data-stu-id="93af8-115">Attributes</span></span>  
  
|<span data-ttu-id="93af8-116">属性</span><span class="sxs-lookup"><span data-stu-id="93af8-116">Attribute</span></span>|<span data-ttu-id="93af8-117">説明</span><span class="sxs-lookup"><span data-stu-id="93af8-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="93af8-118">スコープ (scope)</span><span class="sxs-lookup"><span data-stu-id="93af8-118">scope</span></span>|<span data-ttu-id="93af8-119">サービス検索の一致条件に使用できるエンドポイントのスコープ情報を格納する URI。</span><span class="sxs-lookup"><span data-stu-id="93af8-119">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93af8-120">子要素</span><span class="sxs-lookup"><span data-stu-id="93af8-120">Child Elements</span></span>  
 <span data-ttu-id="93af8-121">なし。</span><span class="sxs-lookup"><span data-stu-id="93af8-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93af8-122">親要素</span><span class="sxs-lookup"><span data-stu-id="93af8-122">Parent Elements</span></span>  
  
|<span data-ttu-id="93af8-123">要素</span><span class="sxs-lookup"><span data-stu-id="93af8-123">Element</span></span>|<span data-ttu-id="93af8-124">説明</span><span class="sxs-lookup"><span data-stu-id="93af8-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93af8-125">\<スコープ ></span><span class="sxs-lookup"><span data-stu-id="93af8-125">\<scopes></span></span>](scopes.md)|<span data-ttu-id="93af8-126">クエリの実行中に、サービス エンドポイントのフィルター処理に使用できるカスタム スコープ URI を指定する構成要素のコレクションを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="93af8-126">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="93af8-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="93af8-127">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
