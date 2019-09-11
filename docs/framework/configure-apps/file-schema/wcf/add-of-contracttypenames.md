---
title: <add> の <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 696752470aa39c2bcc66a1337f84119031742ae9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850539"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="efefa-102">\<add> of \<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="efefa-102">\<add> of \<contractTypeNames></span></span>
<span data-ttu-id="efefa-103">検索対象サービスのコントラクト名と、サービスを検索するときに一般的に使用される条件を指定する構成要素。</span><span class="sxs-lookup"><span data-stu-id="efefa-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="efefa-104">複数のコントラクト名が指定されると、すべてのコントラクトに一致するサービス エンドポイントのみが適用されます。</span><span class="sxs-lookup"><span data-stu-id="efefa-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="efefa-105">Windows Communication Foundation (WCF) では、エンドポイントでサポートされるコントラクトは1つだけであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="efefa-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
<span data-ttu-id="efefa-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="efefa-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="efefa-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="efefa-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="efefa-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="efefa-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="efefa-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dynamicEndpoint >** ](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="efefa-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="efefa-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<standardEndpoint >** </span><span class="sxs-lookup"><span data-stu-id="efefa-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="efefa-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<discoveryClientSettings >** ](discoveryclientsettings.md)</span><span class="sxs-lookup"><span data-stu-id="efefa-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)</span></span>\
<span data-ttu-id="efefa-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<findCriteria >** ](findcriteria.md)</span><span class="sxs-lookup"><span data-stu-id="efefa-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)</span></span>\
<span data-ttu-id="efefa-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<contractTypeNames >** ](contracttypenames.md)</span><span class="sxs-lookup"><span data-stu-id="efefa-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<contractTypeNames>**](contracttypenames.md)</span></span>\
<span data-ttu-id="efefa-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の追加**</span><span class="sxs-lookup"><span data-stu-id="efefa-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efefa-115">構文</span><span class="sxs-lookup"><span data-stu-id="efefa-115">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String" namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="efefa-116">属性および要素</span><span class="sxs-lookup"><span data-stu-id="efefa-116">Attributes and Elements</span></span>  
 <span data-ttu-id="efefa-117">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="efefa-117">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="efefa-118">属性</span><span class="sxs-lookup"><span data-stu-id="efefa-118">Attributes</span></span>  
  
|<span data-ttu-id="efefa-119">属性</span><span class="sxs-lookup"><span data-stu-id="efefa-119">Attribute</span></span>|<span data-ttu-id="efefa-120">説明</span><span class="sxs-lookup"><span data-stu-id="efefa-120">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="efefa-121">name</span><span class="sxs-lookup"><span data-stu-id="efefa-121">name</span></span>|<span data-ttu-id="efefa-122">コントラクト型の名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="efefa-122">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="efefa-123">名前空間</span><span class="sxs-lookup"><span data-stu-id="efefa-123">namespace</span></span>|<span data-ttu-id="efefa-124">コントラクト型の名前空間を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="efefa-124">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="efefa-125">子要素</span><span class="sxs-lookup"><span data-stu-id="efefa-125">Child Elements</span></span>  
 <span data-ttu-id="efefa-126">なし</span><span class="sxs-lookup"><span data-stu-id="efefa-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="efefa-127">親要素</span><span class="sxs-lookup"><span data-stu-id="efefa-127">Parent Elements</span></span>  
  
|<span data-ttu-id="efefa-128">要素</span><span class="sxs-lookup"><span data-stu-id="efefa-128">Element</span></span>|<span data-ttu-id="efefa-129">説明</span><span class="sxs-lookup"><span data-stu-id="efefa-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="efefa-130">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="efefa-130">\<contractTypeNames></span></span>](contracttypenames.md)|<span data-ttu-id="efefa-131">コントラクトの型名のコレクション。</span><span class="sxs-lookup"><span data-stu-id="efefa-131">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="efefa-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="efefa-132">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
