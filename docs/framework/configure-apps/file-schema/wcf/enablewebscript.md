---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: b2cdd29cda7f82ce555b0f6c1a963567b41ff81b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673252"
---
# <a name="enablewebscript"></a><span data-ttu-id="21a2f-101">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="21a2f-101">\<enableWebScript></span></span>
<span data-ttu-id="21a2f-102">この要素は、ASP.NET AJAX Web ページからサービスを使用できるようにするエンドポイントの動作を有効にします。</span><span class="sxs-lookup"><span data-stu-id="21a2f-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="21a2f-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="21a2f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="21a2f-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="21a2f-104">\<behaviors></span></span>  
<span data-ttu-id="21a2f-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="21a2f-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="21a2f-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="21a2f-106">\<behavior></span></span>  
<span data-ttu-id="21a2f-107">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="21a2f-107">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21a2f-108">構文</span><span class="sxs-lookup"><span data-stu-id="21a2f-108">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21a2f-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="21a2f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="21a2f-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="21a2f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21a2f-111">属性</span><span class="sxs-lookup"><span data-stu-id="21a2f-111">Attributes</span></span>  
 <span data-ttu-id="21a2f-112">なし。</span><span class="sxs-lookup"><span data-stu-id="21a2f-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="21a2f-113">子要素</span><span class="sxs-lookup"><span data-stu-id="21a2f-113">Child Elements</span></span>  
 <span data-ttu-id="21a2f-114">なし。</span><span class="sxs-lookup"><span data-stu-id="21a2f-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="21a2f-115">親要素</span><span class="sxs-lookup"><span data-stu-id="21a2f-115">Parent Elements</span></span>  
  
|<span data-ttu-id="21a2f-116">要素</span><span class="sxs-lookup"><span data-stu-id="21a2f-116">Element</span></span>|<span data-ttu-id="21a2f-117">説明</span><span class="sxs-lookup"><span data-stu-id="21a2f-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21a2f-118">\<behavior></span><span class="sxs-lookup"><span data-stu-id="21a2f-118">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="21a2f-119">エンドポイントの動作のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="21a2f-119">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21a2f-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="21a2f-120">Remarks</span></span>  
 <span data-ttu-id="21a2f-121">この動作は、いずれかと組み合わせてのみ使用する必要があります、 [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)標準バインディングまたは[ \<webMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md)バインド要素。</span><span class="sxs-lookup"><span data-stu-id="21a2f-121">This behavior should only be used in conjunction with either the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="21a2f-122">この動作の詳細については、「<xref:System.ServiceModel.Description.WebScriptEnablingBehavior>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21a2f-122">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21a2f-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="21a2f-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="21a2f-124">AJAX の統合と JSON のサポート</span><span class="sxs-lookup"><span data-stu-id="21a2f-124">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="21a2f-125">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="21a2f-125">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
