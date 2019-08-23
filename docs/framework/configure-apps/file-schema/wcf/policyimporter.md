---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 273bd0d5e68a661c639b82264b440b83d8127427
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933791"
---
# <a name="policyimporter"></a><span data-ttu-id="06bf5-101">\<policyImporter ></span><span class="sxs-lookup"><span data-stu-id="06bf5-101">\<policyImporter></span></span>
<span data-ttu-id="06bf5-102">バインディングに関するカスタム ポリシー アサーションのインポートを制御するポリシー インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="06bf5-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="06bf5-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="06bf5-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="06bf5-104">\<client></span><span class="sxs-lookup"><span data-stu-id="06bf5-104">\<client></span></span>  
<span data-ttu-id="06bf5-105">\<matadata></span><span class="sxs-lookup"><span data-stu-id="06bf5-105">\<metadata></span></span>  
<span data-ttu-id="06bf5-106">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="06bf5-106">\<policyImporters></span></span>  
<span data-ttu-id="06bf5-107">\<policyImporter ></span><span class="sxs-lookup"><span data-stu-id="06bf5-107">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06bf5-108">構文</span><span class="sxs-lookup"><span data-stu-id="06bf5-108">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06bf5-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="06bf5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="06bf5-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="06bf5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06bf5-111">属性</span><span class="sxs-lookup"><span data-stu-id="06bf5-111">Attributes</span></span>  
  
|<span data-ttu-id="06bf5-112">属性</span><span class="sxs-lookup"><span data-stu-id="06bf5-112">Attribute</span></span>|<span data-ttu-id="06bf5-113">説明</span><span class="sxs-lookup"><span data-stu-id="06bf5-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="06bf5-114">この要素の型です。</span><span class="sxs-lookup"><span data-stu-id="06bf5-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06bf5-115">子要素</span><span class="sxs-lookup"><span data-stu-id="06bf5-115">Child Elements</span></span>  
 <span data-ttu-id="06bf5-116">なし</span><span class="sxs-lookup"><span data-stu-id="06bf5-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06bf5-117">親要素</span><span class="sxs-lookup"><span data-stu-id="06bf5-117">Parent Elements</span></span>  
  
|<span data-ttu-id="06bf5-118">要素</span><span class="sxs-lookup"><span data-stu-id="06bf5-118">Element</span></span>|<span data-ttu-id="06bf5-119">説明</span><span class="sxs-lookup"><span data-stu-id="06bf5-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06bf5-120">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="06bf5-120">\<policyImporters></span></span>](policyimporters.md)|<span data-ttu-id="06bf5-121">バインディングに関するカスタム ポリシー アサーションのインポートを制御するすべてのポリシー インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="06bf5-121">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06bf5-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="06bf5-122">Remarks</span></span>  
 <span data-ttu-id="06bf5-123">ポリシー インポーターは、バインディング機能についてのカスタム ポリシー アサーションの検索、およびアサーションで必要となる機能を実装するカスタム バインド要素の結び付けに使用されます。</span><span class="sxs-lookup"><span data-stu-id="06bf5-123">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06bf5-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="06bf5-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="06bf5-125">WCF クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="06bf5-125">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="06bf5-126">クライアント</span><span class="sxs-lookup"><span data-stu-id="06bf5-126">Clients</span></span>](../../../wcf/feature-details/clients.md)
