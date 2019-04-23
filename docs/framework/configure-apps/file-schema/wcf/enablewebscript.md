---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: b2cdd29cda7f82ce555b0f6c1a963567b41ff81b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213000"
---
# <a name="enablewebscript"></a><span data-ttu-id="2d4d0-101">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="2d4d0-101">\<enableWebScript></span></span>
<span data-ttu-id="2d4d0-102">この要素は、ASP.NET AJAX Web ページからサービスを使用できるようにするエンドポイントの動作を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2d4d0-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="2d4d0-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2d4d0-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="2d4d0-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="2d4d0-104">\<behaviors></span></span>  
<span data-ttu-id="2d4d0-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="2d4d0-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="2d4d0-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2d4d0-106">\<behavior></span></span>  
<span data-ttu-id="2d4d0-107">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="2d4d0-107">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d4d0-108">構文</span><span class="sxs-lookup"><span data-stu-id="2d4d0-108">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d4d0-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2d4d0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2d4d0-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d4d0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d4d0-111">属性</span><span class="sxs-lookup"><span data-stu-id="2d4d0-111">Attributes</span></span>  
 <span data-ttu-id="2d4d0-112">なし。</span><span class="sxs-lookup"><span data-stu-id="2d4d0-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2d4d0-113">子要素</span><span class="sxs-lookup"><span data-stu-id="2d4d0-113">Child Elements</span></span>  
 <span data-ttu-id="2d4d0-114">なし。</span><span class="sxs-lookup"><span data-stu-id="2d4d0-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2d4d0-115">親要素</span><span class="sxs-lookup"><span data-stu-id="2d4d0-115">Parent Elements</span></span>  
  
|<span data-ttu-id="2d4d0-116">要素</span><span class="sxs-lookup"><span data-stu-id="2d4d0-116">Element</span></span>|<span data-ttu-id="2d4d0-117">説明</span><span class="sxs-lookup"><span data-stu-id="2d4d0-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d4d0-118">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2d4d0-118">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="2d4d0-119">エンドポイントの動作のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="2d4d0-119">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d4d0-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="2d4d0-120">Remarks</span></span>  
 <span data-ttu-id="2d4d0-121">この動作は、いずれかと組み合わせてのみ使用する必要があります、 [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)標準バインディングまたは[ \<webMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md)バインド要素。</span><span class="sxs-lookup"><span data-stu-id="2d4d0-121">This behavior should only be used in conjunction with either the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="2d4d0-122">この動作の詳細については、「<xref:System.ServiceModel.Description.WebScriptEnablingBehavior>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d4d0-122">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d4d0-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d4d0-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="2d4d0-124">AJAX の統合と JSON のサポート</span><span class="sxs-lookup"><span data-stu-id="2d4d0-124">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="2d4d0-125">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="2d4d0-125">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
