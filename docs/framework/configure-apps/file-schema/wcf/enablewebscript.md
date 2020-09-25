---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 11378e6cc8cbe8e631fd77ab74c91a616099df52
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190086"
---
# \<enableWebScript>

<span data-ttu-id="e9067-101">この要素は、ASP.NET AJAX Web ページからサービスを使用できるようにするエンドポイントの動作を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e9067-101">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<enableWebScript>**  
  
## <a name="syntax"></a><span data-ttu-id="e9067-102">構文</span><span class="sxs-lookup"><span data-stu-id="e9067-102">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9067-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e9067-103">Attributes and Elements</span></span>  

 <span data-ttu-id="e9067-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e9067-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9067-105">属性</span><span class="sxs-lookup"><span data-stu-id="e9067-105">Attributes</span></span>  

 <span data-ttu-id="e9067-106">なし。</span><span class="sxs-lookup"><span data-stu-id="e9067-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e9067-107">子要素</span><span class="sxs-lookup"><span data-stu-id="e9067-107">Child Elements</span></span>  

 <span data-ttu-id="e9067-108">なし。</span><span class="sxs-lookup"><span data-stu-id="e9067-108">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9067-109">親要素</span><span class="sxs-lookup"><span data-stu-id="e9067-109">Parent Elements</span></span>  
  
|<span data-ttu-id="e9067-110">要素</span><span class="sxs-lookup"><span data-stu-id="e9067-110">Element</span></span>|<span data-ttu-id="e9067-111">説明</span><span class="sxs-lookup"><span data-stu-id="e9067-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="e9067-112">エンドポイントの動作のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="e9067-112">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9067-113">解説</span><span class="sxs-lookup"><span data-stu-id="e9067-113">Remarks</span></span>  

 <span data-ttu-id="e9067-114">この動作は、 [\<webHttpBinding>](webhttpbinding.md) 標準バインディングまたはバインディング要素と組み合わせて使用する必要があり [\<webMessageEncoding>](webmessageencoding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="e9067-114">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="e9067-115">この動作の詳細については、「<xref:System.ServiceModel.Description.WebScriptEnablingBehavior>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9067-115">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9067-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9067-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="e9067-117">AJAX の統合と JSON のサポート</span><span class="sxs-lookup"><span data-stu-id="e9067-117">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttp>](webhttp.md)
