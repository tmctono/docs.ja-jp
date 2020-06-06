---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: c67e5b9e82b96e27ce73512680bd4236b26ef4dd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855452"
---
# \<contractTypeNames>
<span data-ttu-id="a6ea4-101">検索対象サービスのコントラクト名であるコントラクト型名のリストと、サービスを検索するときに一般的に使用される条件を指定する構成セクション。</span><span class="sxs-lookup"><span data-stu-id="a6ea4-101">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="a6ea4-102">複数のコントラクト名が指定されると、すべてのコントラクトに一致するサービス エンドポイントのみが適用されます。</span><span class="sxs-lookup"><span data-stu-id="a6ea4-102">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="a6ea4-103">Windows Communication Foundation (WCF) では、エンドポイントでサポートされるコントラクトは1つだけであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a6ea4-103">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<contractTypeNames>**  
  
## <a name="syntax"></a><span data-ttu-id="a6ea4-104">構文</span><span class="sxs-lookup"><span data-stu-id="a6ea4-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6ea4-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a6ea4-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a6ea4-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6ea4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6ea4-107">属性</span><span class="sxs-lookup"><span data-stu-id="a6ea4-107">Attributes</span></span>  
 <span data-ttu-id="a6ea4-108">なし。</span><span class="sxs-lookup"><span data-stu-id="a6ea4-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a6ea4-109">子要素</span><span class="sxs-lookup"><span data-stu-id="a6ea4-109">Child Elements</span></span>  
  
|<span data-ttu-id="a6ea4-110">要素</span><span class="sxs-lookup"><span data-stu-id="a6ea4-110">Element</span></span>|<span data-ttu-id="a6ea4-111">説明</span><span class="sxs-lookup"><span data-stu-id="a6ea4-111">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](contracttypenames.md)|<span data-ttu-id="a6ea4-112">コントラクト型名は、サービスを検索するときに一般的に使用される条件セットを参照するプロパティです。</span><span class="sxs-lookup"><span data-stu-id="a6ea4-112">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a6ea4-113">親要素</span><span class="sxs-lookup"><span data-stu-id="a6ea4-113">Parent Elements</span></span>  
  
|<span data-ttu-id="a6ea4-114">要素</span><span class="sxs-lookup"><span data-stu-id="a6ea4-114">Element</span></span>|<span data-ttu-id="a6ea4-115">説明</span><span class="sxs-lookup"><span data-stu-id="a6ea4-115">Description</span></span>|  
|-------------|-----------------|  
|[\<findCriteria>](findcriteria.md)|<span data-ttu-id="a6ea4-116">探索サービスの検索にクライアント アプリケーションによって使用される基準を提供する構成要素。</span><span class="sxs-lookup"><span data-stu-id="a6ea4-116">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="a6ea4-117">基準は、(探しているサービスを指定する) 検索条件と (検索をどのくらい続けるかを指定する) 検索終了条件にグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="a6ea4-117">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a6ea4-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6ea4-118">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
