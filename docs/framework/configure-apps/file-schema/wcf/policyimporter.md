---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 81f38d2a163163ca7255ca546bbddbbb58fa3a1b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094178"
---
# <a name="policyimporter"></a><span data-ttu-id="40246-101">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="40246-101">\<policyImporter></span></span>
<span data-ttu-id="40246-102">バインディングに関するカスタム ポリシー アサーションのインポートを制御するポリシー インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="40246-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="40246-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="40246-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="40246-104">\<client></span><span class="sxs-lookup"><span data-stu-id="40246-104">\<client></span></span>  
<span data-ttu-id="40246-105">\<matadata></span><span class="sxs-lookup"><span data-stu-id="40246-105">\<metadata></span></span>  
<span data-ttu-id="40246-106">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="40246-106">\<policyImporters></span></span>  
<span data-ttu-id="40246-107">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="40246-107">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40246-108">構文</span><span class="sxs-lookup"><span data-stu-id="40246-108">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40246-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="40246-109">Attributes and Elements</span></span>  
 <span data-ttu-id="40246-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="40246-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40246-111">属性</span><span class="sxs-lookup"><span data-stu-id="40246-111">Attributes</span></span>  
  
|<span data-ttu-id="40246-112">属性</span><span class="sxs-lookup"><span data-stu-id="40246-112">Attribute</span></span>|<span data-ttu-id="40246-113">説明</span><span class="sxs-lookup"><span data-stu-id="40246-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="40246-114">この要素の型です。</span><span class="sxs-lookup"><span data-stu-id="40246-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40246-115">子要素</span><span class="sxs-lookup"><span data-stu-id="40246-115">Child Elements</span></span>  
 <span data-ttu-id="40246-116">なし</span><span class="sxs-lookup"><span data-stu-id="40246-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40246-117">親要素</span><span class="sxs-lookup"><span data-stu-id="40246-117">Parent Elements</span></span>  
  
|<span data-ttu-id="40246-118">要素</span><span class="sxs-lookup"><span data-stu-id="40246-118">Element</span></span>|<span data-ttu-id="40246-119">説明</span><span class="sxs-lookup"><span data-stu-id="40246-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40246-120">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="40246-120">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="40246-121">バインディングに関するカスタム ポリシー アサーションのインポートを制御するすべてのポリシー インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="40246-121">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40246-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="40246-122">Remarks</span></span>  
 <span data-ttu-id="40246-123">ポリシー インポーターは、バインディング機能についてのカスタム ポリシー アサーションの検索、およびアサーションで必要となる機能を実装するカスタム バインド要素の結び付けに使用されます。</span><span class="sxs-lookup"><span data-stu-id="40246-123">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40246-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="40246-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="40246-125">WCF クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="40246-125">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="40246-126">クライアント</span><span class="sxs-lookup"><span data-stu-id="40246-126">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
