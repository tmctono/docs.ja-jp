---
title: <add> の <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 24f1478b99aef909ae93f87a70be257e9ba10d7a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926749"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="bed83-102">\<add> of \<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="bed83-102">\<add> of \<contractTypeNames></span></span>
<span data-ttu-id="bed83-103">検索対象サービスのコントラクト名と、サービスを検索するときに一般的に使用される条件を指定する構成要素。</span><span class="sxs-lookup"><span data-stu-id="bed83-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="bed83-104">複数のコントラクト名が指定されると、すべてのコントラクトに一致するサービス エンドポイントのみが適用されます。</span><span class="sxs-lookup"><span data-stu-id="bed83-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="bed83-105">Windows Communication Foundation (WCF) では、エンドポイントでサポートされるコントラクトは1つだけであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bed83-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="bed83-106">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bed83-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="bed83-107">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="bed83-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bed83-108">構文</span><span class="sxs-lookup"><span data-stu-id="bed83-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bed83-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bed83-109">Attributes and Elements</span></span>  
 <span data-ttu-id="bed83-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bed83-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bed83-111">属性</span><span class="sxs-lookup"><span data-stu-id="bed83-111">Attributes</span></span>  
  
|<span data-ttu-id="bed83-112">属性</span><span class="sxs-lookup"><span data-stu-id="bed83-112">Attribute</span></span>|<span data-ttu-id="bed83-113">説明</span><span class="sxs-lookup"><span data-stu-id="bed83-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bed83-114">name</span><span class="sxs-lookup"><span data-stu-id="bed83-114">name</span></span>|<span data-ttu-id="bed83-115">コントラクト型の名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="bed83-115">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="bed83-116">名前空間</span><span class="sxs-lookup"><span data-stu-id="bed83-116">namespace</span></span>|<span data-ttu-id="bed83-117">コントラクト型の名前空間を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="bed83-117">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bed83-118">子要素</span><span class="sxs-lookup"><span data-stu-id="bed83-118">Child Elements</span></span>  
 <span data-ttu-id="bed83-119">なし</span><span class="sxs-lookup"><span data-stu-id="bed83-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bed83-120">親要素</span><span class="sxs-lookup"><span data-stu-id="bed83-120">Parent Elements</span></span>  
  
|<span data-ttu-id="bed83-121">要素</span><span class="sxs-lookup"><span data-stu-id="bed83-121">Element</span></span>|<span data-ttu-id="bed83-122">説明</span><span class="sxs-lookup"><span data-stu-id="bed83-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bed83-123">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="bed83-123">\<contractTypeNames></span></span>](contracttypenames.md)|<span data-ttu-id="bed83-124">コントラクトの型名のコレクション。</span><span class="sxs-lookup"><span data-stu-id="bed83-124">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bed83-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="bed83-125">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
