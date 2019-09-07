---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 20c0057c80b668df97379d0168bb7c005d9927ce
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400384"
---
# <a name="enablewebscript"></a><span data-ttu-id="7beb0-101">\<enableWebScript ></span><span class="sxs-lookup"><span data-stu-id="7beb0-101">\<enableWebScript></span></span>
<span data-ttu-id="7beb0-102">この要素は、ASP.NET AJAX Web ページからサービスを使用できるようにするエンドポイントの動作を有効にします。</span><span class="sxs-lookup"><span data-stu-id="7beb0-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
<span data-ttu-id="7beb0-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7beb0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7beb0-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7beb0-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7beb0-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7beb0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="7beb0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7beb0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="7beb0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7beb0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="7beb0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<enableWebScript >**</span><span class="sxs-lookup"><span data-stu-id="7beb0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<enableWebScript>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7beb0-109">構文</span><span class="sxs-lookup"><span data-stu-id="7beb0-109">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7beb0-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7beb0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7beb0-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7beb0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7beb0-112">属性</span><span class="sxs-lookup"><span data-stu-id="7beb0-112">Attributes</span></span>  
 <span data-ttu-id="7beb0-113">なし。</span><span class="sxs-lookup"><span data-stu-id="7beb0-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7beb0-114">子要素</span><span class="sxs-lookup"><span data-stu-id="7beb0-114">Child Elements</span></span>  
 <span data-ttu-id="7beb0-115">なし。</span><span class="sxs-lookup"><span data-stu-id="7beb0-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7beb0-116">親要素</span><span class="sxs-lookup"><span data-stu-id="7beb0-116">Parent Elements</span></span>  
  
|<span data-ttu-id="7beb0-117">要素</span><span class="sxs-lookup"><span data-stu-id="7beb0-117">Element</span></span>|<span data-ttu-id="7beb0-118">説明</span><span class="sxs-lookup"><span data-stu-id="7beb0-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7beb0-119">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7beb0-119">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="7beb0-120">エンドポイントの動作のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="7beb0-120">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7beb0-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="7beb0-121">Remarks</span></span>  
 <span data-ttu-id="7beb0-122">この動作は、 [ \<webHttpBinding >](webhttpbinding.md)標準[ \<](webmessageencoding.md)バインディング、または webMessageEncoding > binding 要素と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7beb0-122">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="7beb0-123">この動作の詳細については、「<xref:System.ServiceModel.Description.WebScriptEnablingBehavior>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7beb0-123">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7beb0-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="7beb0-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="7beb0-125">AJAX の統合と JSON のサポート</span><span class="sxs-lookup"><span data-stu-id="7beb0-125">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="7beb0-126">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="7beb0-126">\<webHttp></span></span>](webhttp.md)
