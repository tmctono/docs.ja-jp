---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 123f58ee3d77bf605db21fa0d9537b3196d56468
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919114"
---
# <a name="enablewebscript"></a><span data-ttu-id="210fa-101">\<enableWebScript ></span><span class="sxs-lookup"><span data-stu-id="210fa-101">\<enableWebScript></span></span>
<span data-ttu-id="210fa-102">この要素は、ASP.NET AJAX Web ページからサービスを使用できるようにするエンドポイントの動作を有効にします。</span><span class="sxs-lookup"><span data-stu-id="210fa-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="210fa-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="210fa-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="210fa-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="210fa-104">\<behaviors></span></span>  
<span data-ttu-id="210fa-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="210fa-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="210fa-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="210fa-106">\<behavior></span></span>  
<span data-ttu-id="210fa-107">\<enableWebScript ></span><span class="sxs-lookup"><span data-stu-id="210fa-107">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="210fa-108">構文</span><span class="sxs-lookup"><span data-stu-id="210fa-108">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="210fa-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="210fa-109">Attributes and Elements</span></span>  
 <span data-ttu-id="210fa-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="210fa-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="210fa-111">属性</span><span class="sxs-lookup"><span data-stu-id="210fa-111">Attributes</span></span>  
 <span data-ttu-id="210fa-112">なし。</span><span class="sxs-lookup"><span data-stu-id="210fa-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="210fa-113">子要素</span><span class="sxs-lookup"><span data-stu-id="210fa-113">Child Elements</span></span>  
 <span data-ttu-id="210fa-114">なし。</span><span class="sxs-lookup"><span data-stu-id="210fa-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="210fa-115">親要素</span><span class="sxs-lookup"><span data-stu-id="210fa-115">Parent Elements</span></span>  
  
|<span data-ttu-id="210fa-116">要素</span><span class="sxs-lookup"><span data-stu-id="210fa-116">Element</span></span>|<span data-ttu-id="210fa-117">説明</span><span class="sxs-lookup"><span data-stu-id="210fa-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="210fa-118">\<behavior></span><span class="sxs-lookup"><span data-stu-id="210fa-118">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="210fa-119">エンドポイントの動作のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="210fa-119">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="210fa-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="210fa-120">Remarks</span></span>  
 <span data-ttu-id="210fa-121">この動作は、 [ \<webHttpBinding >](webhttpbinding.md)標準[ \<](webmessageencoding.md)バインディング、または webMessageEncoding > binding 要素と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="210fa-121">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="210fa-122">この動作の詳細については、「<xref:System.ServiceModel.Description.WebScriptEnablingBehavior>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="210fa-122">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="210fa-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="210fa-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="210fa-124">AJAX の統合と JSON のサポート</span><span class="sxs-lookup"><span data-stu-id="210fa-124">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="210fa-125">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="210fa-125">\<webHttp></span></span>](webhttp.md)
