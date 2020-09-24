---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 63f46753da13469147b378f373de9888a007bf52
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162219"
---
# \<scopes>

<span data-ttu-id="e6a00-101">クエリの実行中に、サービス エンドポイントのフィルター処理に使用できるカスタム スコープ URI を指定する構成要素のコレクションを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="e6a00-101">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopes>**  
  
## <a name="syntax"></a><span data-ttu-id="e6a00-102">構文</span><span class="sxs-lookup"><span data-stu-id="e6a00-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6a00-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e6a00-103">Attributes and Elements</span></span>  

 <span data-ttu-id="e6a00-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6a00-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6a00-105">属性</span><span class="sxs-lookup"><span data-stu-id="e6a00-105">Attributes</span></span>  

 <span data-ttu-id="e6a00-106">なし。</span><span class="sxs-lookup"><span data-stu-id="e6a00-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e6a00-107">子要素</span><span class="sxs-lookup"><span data-stu-id="e6a00-107">Child Elements</span></span>  
  
|<span data-ttu-id="e6a00-108">属性</span><span class="sxs-lookup"><span data-stu-id="e6a00-108">Attribute</span></span>|<span data-ttu-id="e6a00-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="e6a00-109">Description</span></span>|  
|---------------|-----------------|  
|[\<add>](add-of-scopes.md)|<span data-ttu-id="e6a00-110">サービス検索の一致条件に使用できるエンドポイントのスコープ情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="e6a00-110">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e6a00-111">親要素</span><span class="sxs-lookup"><span data-stu-id="e6a00-111">Parent Elements</span></span>  
  
|<span data-ttu-id="e6a00-112">要素</span><span class="sxs-lookup"><span data-stu-id="e6a00-112">Element</span></span>|<span data-ttu-id="e6a00-113">説明</span><span class="sxs-lookup"><span data-stu-id="e6a00-113">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointDiscovery>](endpointdiscovery.md)|<span data-ttu-id="e6a00-114">エンドポイントのさまざまな探索設定を指定します (探索可能性、スコープ、メタデータに対するカスタム拡張など)。</span><span class="sxs-lookup"><span data-stu-id="e6a00-114">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e6a00-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6a00-115">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
