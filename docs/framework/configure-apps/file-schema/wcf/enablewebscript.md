---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 20c0057c80b668df97379d0168bb7c005d9927ce
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400384"
---
# \<enableWebScript>
<span data-ttu-id="cbaf8-101">この要素は、ASP.NET AJAX Web ページからサービスを使用できるようにするエンドポイントの動作を有効にします。</span><span class="sxs-lookup"><span data-stu-id="cbaf8-101">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<enableWebScript>**  
  
## <a name="syntax"></a><span data-ttu-id="cbaf8-102">構文</span><span class="sxs-lookup"><span data-stu-id="cbaf8-102">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cbaf8-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cbaf8-103">Attributes and Elements</span></span>  
 <span data-ttu-id="cbaf8-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cbaf8-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cbaf8-105">属性</span><span class="sxs-lookup"><span data-stu-id="cbaf8-105">Attributes</span></span>  
 <span data-ttu-id="cbaf8-106">なし。</span><span class="sxs-lookup"><span data-stu-id="cbaf8-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cbaf8-107">子要素</span><span class="sxs-lookup"><span data-stu-id="cbaf8-107">Child Elements</span></span>  
 <span data-ttu-id="cbaf8-108">[なし] :</span><span class="sxs-lookup"><span data-stu-id="cbaf8-108">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cbaf8-109">親要素</span><span class="sxs-lookup"><span data-stu-id="cbaf8-109">Parent Elements</span></span>  
  
|<span data-ttu-id="cbaf8-110">要素</span><span class="sxs-lookup"><span data-stu-id="cbaf8-110">Element</span></span>|<span data-ttu-id="cbaf8-111">説明</span><span class="sxs-lookup"><span data-stu-id="cbaf8-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="cbaf8-112">エンドポイントの動作のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="cbaf8-112">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbaf8-113">解説</span><span class="sxs-lookup"><span data-stu-id="cbaf8-113">Remarks</span></span>  
 <span data-ttu-id="cbaf8-114">この動作は、 [\<webHttpBinding>](webhttpbinding.md) 標準バインディングまたはバインディング要素と組み合わせて使用する必要があり [\<webMessageEncoding>](webmessageencoding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="cbaf8-114">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="cbaf8-115">この動作の詳細については、「<xref:System.ServiceModel.Description.WebScriptEnablingBehavior>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbaf8-115">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbaf8-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbaf8-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="cbaf8-117">AJAX の統合と JSON のサポート</span><span class="sxs-lookup"><span data-stu-id="cbaf8-117">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttp>](webhttp.md)
