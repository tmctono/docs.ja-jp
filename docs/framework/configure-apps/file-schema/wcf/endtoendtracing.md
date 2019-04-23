---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 266b33e9b0386d0346a86ba8bd82cc65def4f0c2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180155"
---
# <a name="endtoendtracing"></a><span data-ttu-id="793ce-101">\<endToEndTracing ></span><span class="sxs-lookup"><span data-stu-id="793ce-101">\<endToEndTracing></span></span>
<span data-ttu-id="793ce-102">サービス アプリケーションの実行中にエンドツーエンドのトレースのさまざまな側面を有効または無効にするための構成要素。</span><span class="sxs-lookup"><span data-stu-id="793ce-102">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="793ce-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="793ce-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="793ce-104">\<診断 ></span><span class="sxs-lookup"><span data-stu-id="793ce-104">\<diagnostic></span></span>  
<span data-ttu-id="793ce-105">\<endToEndTracing ></span><span class="sxs-lookup"><span data-stu-id="793ce-105">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="793ce-106">構文</span><span class="sxs-lookup"><span data-stu-id="793ce-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="793ce-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="793ce-107">Attributes and Elements</span></span>  
 <span data-ttu-id="793ce-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="793ce-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="793ce-109">属性</span><span class="sxs-lookup"><span data-stu-id="793ce-109">Attributes</span></span>  
  
|<span data-ttu-id="793ce-110">属性</span><span class="sxs-lookup"><span data-stu-id="793ce-110">Attribute</span></span>|<span data-ttu-id="793ce-111">説明</span><span class="sxs-lookup"><span data-stu-id="793ce-111">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="793ce-112">アクティビティのトレースが有効かどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="793ce-112">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="793ce-113">メッセージ フローのトレースが有効かどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="793ce-113">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="793ce-114">伝達属性が true に設定されているかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="793ce-114">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="793ce-115">子要素</span><span class="sxs-lookup"><span data-stu-id="793ce-115">Child Elements</span></span>  
 <span data-ttu-id="793ce-116">なし。</span><span class="sxs-lookup"><span data-stu-id="793ce-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="793ce-117">親要素</span><span class="sxs-lookup"><span data-stu-id="793ce-117">Parent Elements</span></span>  
  
|<span data-ttu-id="793ce-118">要素</span><span class="sxs-lookup"><span data-stu-id="793ce-118">Element</span></span>|<span data-ttu-id="793ce-119">説明</span><span class="sxs-lookup"><span data-stu-id="793ce-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="793ce-120">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="793ce-120">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="793ce-121">管理者が行うランタイムの検査と管理の WCF 設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="793ce-121">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="793ce-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="793ce-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="793ce-123">エンドツーエンドのトレース</span><span class="sxs-lookup"><span data-stu-id="793ce-123">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
