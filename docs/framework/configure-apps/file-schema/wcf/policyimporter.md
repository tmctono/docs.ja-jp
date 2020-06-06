---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 4ef5890d52c3f2af42322f023b9a2a23cb583035
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855054"
---
# \<policyImporter>
<span data-ttu-id="63041-101">バインディングに関するカスタム ポリシー アサーションのインポートを制御するポリシー インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="63041-101">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<policyImporters>**](policyimporters.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<policyImporter>**  
  
## <a name="syntax"></a><span data-ttu-id="63041-102">構文</span><span class="sxs-lookup"><span data-stu-id="63041-102">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63041-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="63041-103">Attributes and Elements</span></span>  
 <span data-ttu-id="63041-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="63041-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63041-105">属性</span><span class="sxs-lookup"><span data-stu-id="63041-105">Attributes</span></span>  
  
|<span data-ttu-id="63041-106">属性</span><span class="sxs-lookup"><span data-stu-id="63041-106">Attribute</span></span>|<span data-ttu-id="63041-107">説明</span><span class="sxs-lookup"><span data-stu-id="63041-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="63041-108">この要素の型です。</span><span class="sxs-lookup"><span data-stu-id="63041-108">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63041-109">子要素</span><span class="sxs-lookup"><span data-stu-id="63041-109">Child Elements</span></span>  
 <span data-ttu-id="63041-110">なし</span><span class="sxs-lookup"><span data-stu-id="63041-110">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="63041-111">親要素</span><span class="sxs-lookup"><span data-stu-id="63041-111">Parent Elements</span></span>  
  
|<span data-ttu-id="63041-112">要素</span><span class="sxs-lookup"><span data-stu-id="63041-112">Element</span></span>|<span data-ttu-id="63041-113">Description</span><span class="sxs-lookup"><span data-stu-id="63041-113">Description</span></span>|  
|-------------|-----------------|  
|[\<policyImporters>](policyimporters.md)|<span data-ttu-id="63041-114">バインディングに関するカスタム ポリシー アサーションのインポートを制御するすべてのポリシー インポーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="63041-114">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63041-115">解説</span><span class="sxs-lookup"><span data-stu-id="63041-115">Remarks</span></span>  
 <span data-ttu-id="63041-116">ポリシー インポーターは、バインディング機能についてのカスタム ポリシー アサーションの検索、およびアサーションで必要となる機能を実装するカスタム バインド要素の結び付けに使用されます。</span><span class="sxs-lookup"><span data-stu-id="63041-116">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63041-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="63041-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="63041-118">WCF クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="63041-118">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="63041-119">クライアント</span><span class="sxs-lookup"><span data-stu-id="63041-119">Clients</span></span>](../../../wcf/feature-details/clients.md)
