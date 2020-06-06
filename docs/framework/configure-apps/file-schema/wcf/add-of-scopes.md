---
title: <add> の <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: bcde6b18c34dccf1716c809dddeb45b1b4da90f0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398303"
---
# <a name="add-of-scopes"></a><span data-ttu-id="f4ed3-102">\<add> の \<scopes></span><span class="sxs-lookup"><span data-stu-id="f4ed3-102">\<add> of \<scopes></span></span>
<span data-ttu-id="f4ed3-103">クエリの実行中に、サービス エンドポイントのフィルター処理に使用できるカスタム スコープ URI を追加します。</span><span class="sxs-lookup"><span data-stu-id="f4ed3-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopes>**](scopes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="f4ed3-104">構文</span><span class="sxs-lookup"><span data-stu-id="f4ed3-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f4ed3-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f4ed3-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f4ed3-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f4ed3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f4ed3-107">属性</span><span class="sxs-lookup"><span data-stu-id="f4ed3-107">Attributes</span></span>  
  
|<span data-ttu-id="f4ed3-108">属性</span><span class="sxs-lookup"><span data-stu-id="f4ed3-108">Attribute</span></span>|<span data-ttu-id="f4ed3-109">説明</span><span class="sxs-lookup"><span data-stu-id="f4ed3-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f4ed3-110">scope</span><span class="sxs-lookup"><span data-stu-id="f4ed3-110">scope</span></span>|<span data-ttu-id="f4ed3-111">サービス検索の一致条件に使用できるエンドポイントのスコープ情報を格納する URI。</span><span class="sxs-lookup"><span data-stu-id="f4ed3-111">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f4ed3-112">子要素</span><span class="sxs-lookup"><span data-stu-id="f4ed3-112">Child Elements</span></span>  
 <span data-ttu-id="f4ed3-113">なし。</span><span class="sxs-lookup"><span data-stu-id="f4ed3-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f4ed3-114">親要素</span><span class="sxs-lookup"><span data-stu-id="f4ed3-114">Parent Elements</span></span>  
  
|<span data-ttu-id="f4ed3-115">要素</span><span class="sxs-lookup"><span data-stu-id="f4ed3-115">Element</span></span>|<span data-ttu-id="f4ed3-116">Description</span><span class="sxs-lookup"><span data-stu-id="f4ed3-116">Description</span></span>|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|<span data-ttu-id="f4ed3-117">クエリの実行中に、サービス エンドポイントのフィルター処理に使用できるカスタム スコープ URI を指定する構成要素のコレクションを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="f4ed3-117">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f4ed3-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4ed3-118">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
