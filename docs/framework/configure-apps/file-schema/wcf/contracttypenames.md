---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: 12f9d4eca02ae3b306646826667c4eafef51a95c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919374"
---
# <a name="contracttypenames"></a><span data-ttu-id="2e619-101">\<contractTypeNames ></span><span class="sxs-lookup"><span data-stu-id="2e619-101">\<contractTypeNames></span></span>
<span data-ttu-id="2e619-102">検索対象サービスのコントラクト名であるコントラクト型名のリストと、サービスを検索するときに一般的に使用される条件を指定する構成セクション。</span><span class="sxs-lookup"><span data-stu-id="2e619-102">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="2e619-103">複数のコントラクト名が指定されると、すべてのコントラクトに一致するサービス エンドポイントのみが適用されます。</span><span class="sxs-lookup"><span data-stu-id="2e619-103">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="2e619-104">Windows Communication Foundation (WCF) では、エンドポイントでサポートされるコントラクトは1つだけであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2e619-104">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="2e619-105">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2e619-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="2e619-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="2e619-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e619-107">構文</span><span class="sxs-lookup"><span data-stu-id="2e619-107">Syntax</span></span>  
  
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
              <add name="String"
                   namespace="String" />
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e619-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2e619-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2e619-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2e619-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e619-110">属性</span><span class="sxs-lookup"><span data-stu-id="2e619-110">Attributes</span></span>  
 <span data-ttu-id="2e619-111">なし。</span><span class="sxs-lookup"><span data-stu-id="2e619-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2e619-112">子要素</span><span class="sxs-lookup"><span data-stu-id="2e619-112">Child Elements</span></span>  
  
|<span data-ttu-id="2e619-113">要素</span><span class="sxs-lookup"><span data-stu-id="2e619-113">Element</span></span>|<span data-ttu-id="2e619-114">説明</span><span class="sxs-lookup"><span data-stu-id="2e619-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e619-115">\<add></span><span class="sxs-lookup"><span data-stu-id="2e619-115">\<add></span></span>](contracttypenames.md)|<span data-ttu-id="2e619-116">コントラクト型名は、サービスを検索するときに一般的に使用される条件セットを参照するプロパティです。</span><span class="sxs-lookup"><span data-stu-id="2e619-116">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2e619-117">親要素</span><span class="sxs-lookup"><span data-stu-id="2e619-117">Parent Elements</span></span>  
  
|<span data-ttu-id="2e619-118">要素</span><span class="sxs-lookup"><span data-stu-id="2e619-118">Element</span></span>|<span data-ttu-id="2e619-119">説明</span><span class="sxs-lookup"><span data-stu-id="2e619-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e619-120">\<findCriteria ></span><span class="sxs-lookup"><span data-stu-id="2e619-120">\<findCriteria></span></span>](findcriteria.md)|<span data-ttu-id="2e619-121">探索サービスの検索にクライアント アプリケーションによって使用される基準を提供する構成要素。</span><span class="sxs-lookup"><span data-stu-id="2e619-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="2e619-122">条件は、検索条件 (探しているサービスを指定します) にグループ化し、終了条件 (検索の最後の長さ) を検索できます。</span><span class="sxs-lookup"><span data-stu-id="2e619-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2e619-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e619-123">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
