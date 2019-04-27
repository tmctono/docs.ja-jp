---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: b1cec9272a1de029ab72ea4d5f36c74630e5b93a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673200"
---
# <a name="contracttypenames"></a><span data-ttu-id="0c76b-101">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="0c76b-101">\<contractTypeNames></span></span>
<span data-ttu-id="0c76b-102">検索対象サービスのコントラクト名であるコントラクト型名のリストと、サービスを検索するときに一般的に使用される条件を指定する構成セクション。</span><span class="sxs-lookup"><span data-stu-id="0c76b-102">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="0c76b-103">複数のコントラクト名が指定されると、すべてのコントラクトに一致するサービス エンドポイントのみが適用されます。</span><span class="sxs-lookup"><span data-stu-id="0c76b-103">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="0c76b-104">Windows Communication Foundation (WCF) エンドポイントがのみサポートしている 1 つのコントラクトに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0c76b-104">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="0c76b-105">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0c76b-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="0c76b-106">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="0c76b-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c76b-107">構文</span><span class="sxs-lookup"><span data-stu-id="0c76b-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c76b-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0c76b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0c76b-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0c76b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c76b-110">属性</span><span class="sxs-lookup"><span data-stu-id="0c76b-110">Attributes</span></span>  
 <span data-ttu-id="0c76b-111">なし。</span><span class="sxs-lookup"><span data-stu-id="0c76b-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0c76b-112">子要素</span><span class="sxs-lookup"><span data-stu-id="0c76b-112">Child Elements</span></span>  
  
|<span data-ttu-id="0c76b-113">要素</span><span class="sxs-lookup"><span data-stu-id="0c76b-113">Element</span></span>|<span data-ttu-id="0c76b-114">説明</span><span class="sxs-lookup"><span data-stu-id="0c76b-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c76b-115">\<add></span><span class="sxs-lookup"><span data-stu-id="0c76b-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="0c76b-116">コントラクト型名は、サービスを検索するときに一般的に使用される条件セットを参照するプロパティです。</span><span class="sxs-lookup"><span data-stu-id="0c76b-116">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0c76b-117">親要素</span><span class="sxs-lookup"><span data-stu-id="0c76b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0c76b-118">要素</span><span class="sxs-lookup"><span data-stu-id="0c76b-118">Element</span></span>|<span data-ttu-id="0c76b-119">説明</span><span class="sxs-lookup"><span data-stu-id="0c76b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c76b-120">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="0c76b-120">\<findCriteria></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/findcriteria.md)|<span data-ttu-id="0c76b-121">探索サービスの検索にクライアント アプリケーションによって使用される基準を提供する構成要素。</span><span class="sxs-lookup"><span data-stu-id="0c76b-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="0c76b-122">条件は、(探しているサービスの種類を指定して) 検索条件にグループ化することができ、検索 (検索持続期間)、終了条件。</span><span class="sxs-lookup"><span data-stu-id="0c76b-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0c76b-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c76b-123">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
