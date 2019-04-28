---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 81f38d2a163163ca7255ca546bbddbbb58fa3a1b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783185"
---
# <a name="policyimporter"></a><span data-ttu-id="49f0b-101">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="49f0b-101">\<policyImporter></span></span>
<span data-ttu-id="49f0b-102">バインディングに関するカスタム ポリシー アサーションのインポートを制御するポリシー インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="49f0b-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="49f0b-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="49f0b-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="49f0b-104">\<client></span><span class="sxs-lookup"><span data-stu-id="49f0b-104">\<client></span></span>  
<span data-ttu-id="49f0b-105">\<matadata></span><span class="sxs-lookup"><span data-stu-id="49f0b-105">\<metadata></span></span>  
<span data-ttu-id="49f0b-106">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="49f0b-106">\<policyImporters></span></span>  
<span data-ttu-id="49f0b-107">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="49f0b-107">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49f0b-108">構文</span><span class="sxs-lookup"><span data-stu-id="49f0b-108">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49f0b-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="49f0b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="49f0b-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="49f0b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49f0b-111">属性</span><span class="sxs-lookup"><span data-stu-id="49f0b-111">Attributes</span></span>  
  
|<span data-ttu-id="49f0b-112">属性</span><span class="sxs-lookup"><span data-stu-id="49f0b-112">Attribute</span></span>|<span data-ttu-id="49f0b-113">説明</span><span class="sxs-lookup"><span data-stu-id="49f0b-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="49f0b-114">この要素の型です。</span><span class="sxs-lookup"><span data-stu-id="49f0b-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="49f0b-115">子要素</span><span class="sxs-lookup"><span data-stu-id="49f0b-115">Child Elements</span></span>  
 <span data-ttu-id="49f0b-116">なし</span><span class="sxs-lookup"><span data-stu-id="49f0b-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="49f0b-117">親要素</span><span class="sxs-lookup"><span data-stu-id="49f0b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="49f0b-118">要素</span><span class="sxs-lookup"><span data-stu-id="49f0b-118">Element</span></span>|<span data-ttu-id="49f0b-119">説明</span><span class="sxs-lookup"><span data-stu-id="49f0b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49f0b-120">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="49f0b-120">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="49f0b-121">バインディングに関するカスタム ポリシー アサーションのインポートを制御するすべてのポリシー インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="49f0b-121">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49f0b-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="49f0b-122">Remarks</span></span>  
 <span data-ttu-id="49f0b-123">ポリシー インポーターは、バインディング機能についてのカスタム ポリシー アサーションの検索、およびアサーションで必要となる機能を実装するカスタム バインド要素の結び付けに使用されます。</span><span class="sxs-lookup"><span data-stu-id="49f0b-123">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49f0b-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="49f0b-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="49f0b-125">WCF クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="49f0b-125">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="49f0b-126">クライアント</span><span class="sxs-lookup"><span data-stu-id="49f0b-126">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
