---
title: <add> の <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 696752470aa39c2bcc66a1337f84119031742ae9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850539"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="7f6b4-102">\<add> の \<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="7f6b4-102">\<add> of \<contractTypeNames></span></span>
<span data-ttu-id="7f6b4-103">検索対象サービスのコントラクト名と、サービスを検索するときに一般的に使用される条件を指定する構成要素。</span><span class="sxs-lookup"><span data-stu-id="7f6b4-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="7f6b4-104">複数のコントラクト名が指定されると、すべてのコントラクトに一致するサービス エンドポイントのみが適用されます。</span><span class="sxs-lookup"><span data-stu-id="7f6b4-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="7f6b4-105">Windows Communication Foundation (WCF) では、エンドポイントでサポートされるコントラクトは1つだけであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7f6b4-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<contractTypeNames>**](contracttypenames.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="7f6b4-106">構文</span><span class="sxs-lookup"><span data-stu-id="7f6b4-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f6b4-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7f6b4-107">Attributes and Elements</span></span>  
 <span data-ttu-id="7f6b4-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f6b4-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f6b4-109">属性</span><span class="sxs-lookup"><span data-stu-id="7f6b4-109">Attributes</span></span>  
  
|<span data-ttu-id="7f6b4-110">属性</span><span class="sxs-lookup"><span data-stu-id="7f6b4-110">Attribute</span></span>|<span data-ttu-id="7f6b4-111">説明</span><span class="sxs-lookup"><span data-stu-id="7f6b4-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7f6b4-112">name</span><span class="sxs-lookup"><span data-stu-id="7f6b4-112">name</span></span>|<span data-ttu-id="7f6b4-113">コントラクト型の名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="7f6b4-113">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="7f6b4-114">namespace</span><span class="sxs-lookup"><span data-stu-id="7f6b4-114">namespace</span></span>|<span data-ttu-id="7f6b4-115">コントラクト型の名前空間を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="7f6b4-115">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f6b4-116">子要素</span><span class="sxs-lookup"><span data-stu-id="7f6b4-116">Child Elements</span></span>  
 <span data-ttu-id="7f6b4-117">なし</span><span class="sxs-lookup"><span data-stu-id="7f6b4-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7f6b4-118">親要素</span><span class="sxs-lookup"><span data-stu-id="7f6b4-118">Parent Elements</span></span>  
  
|<span data-ttu-id="7f6b4-119">要素</span><span class="sxs-lookup"><span data-stu-id="7f6b4-119">Element</span></span>|<span data-ttu-id="7f6b4-120">Description</span><span class="sxs-lookup"><span data-stu-id="7f6b4-120">Description</span></span>|  
|-------------|-----------------|  
|[\<contractTypeNames>](contracttypenames.md)|<span data-ttu-id="7f6b4-121">コントラクトの型名のコレクション。</span><span class="sxs-lookup"><span data-stu-id="7f6b4-121">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7f6b4-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f6b4-122">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
