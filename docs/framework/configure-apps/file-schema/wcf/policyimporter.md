---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 4ef5890d52c3f2af42322f023b9a2a23cb583035
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855054"
---
# <a name="policyimporter"></a><span data-ttu-id="7e442-101">\<policyImporter ></span><span class="sxs-lookup"><span data-stu-id="7e442-101">\<policyImporter></span></span>
<span data-ttu-id="7e442-102">バインディングに関するカスタム ポリシー アサーションのインポートを制御するポリシー インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="7e442-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
<span data-ttu-id="7e442-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7e442-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7e442-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7e442-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7e442-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<クライアント >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="7e442-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="7e442-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<メタデータ >** ](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="7e442-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)</span></span>\
<span data-ttu-id="7e442-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<policyImporters >** ](policyimporters.md)</span><span class="sxs-lookup"><span data-stu-id="7e442-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<policyImporters>**](policyimporters.md)</span></span>  
<span data-ttu-id="7e442-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<policyImporter >**</span><span class="sxs-lookup"><span data-stu-id="7e442-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<policyImporter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e442-109">構文</span><span class="sxs-lookup"><span data-stu-id="7e442-109">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e442-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7e442-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7e442-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e442-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e442-112">属性</span><span class="sxs-lookup"><span data-stu-id="7e442-112">Attributes</span></span>  
  
|<span data-ttu-id="7e442-113">属性</span><span class="sxs-lookup"><span data-stu-id="7e442-113">Attribute</span></span>|<span data-ttu-id="7e442-114">説明</span><span class="sxs-lookup"><span data-stu-id="7e442-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="7e442-115">この要素の型です。</span><span class="sxs-lookup"><span data-stu-id="7e442-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e442-116">子要素</span><span class="sxs-lookup"><span data-stu-id="7e442-116">Child Elements</span></span>  
 <span data-ttu-id="7e442-117">なし</span><span class="sxs-lookup"><span data-stu-id="7e442-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e442-118">親要素</span><span class="sxs-lookup"><span data-stu-id="7e442-118">Parent Elements</span></span>  
  
|<span data-ttu-id="7e442-119">要素</span><span class="sxs-lookup"><span data-stu-id="7e442-119">Element</span></span>|<span data-ttu-id="7e442-120">説明</span><span class="sxs-lookup"><span data-stu-id="7e442-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e442-121">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="7e442-121">\<policyImporters></span></span>](policyimporters.md)|<span data-ttu-id="7e442-122">バインディングに関するカスタム ポリシー アサーションのインポートを制御するすべてのポリシー インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="7e442-122">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e442-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="7e442-123">Remarks</span></span>  
 <span data-ttu-id="7e442-124">ポリシー インポーターは、バインディング機能についてのカスタム ポリシー アサーションの検索、およびアサーションで必要となる機能を実装するカスタム バインド要素の結び付けに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7e442-124">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e442-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e442-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="7e442-126">WCF クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="7e442-126">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="7e442-127">クライアント</span><span class="sxs-lookup"><span data-stu-id="7e442-127">Clients</span></span>](../../../wcf/feature-details/clients.md)
