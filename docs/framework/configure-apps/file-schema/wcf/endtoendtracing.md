---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 1a274f15800c6a132994a2437943c83982de9de0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855296"
---
# \<endToEndTracing>
<span data-ttu-id="4bf0c-101">サービス アプリケーションの実行中にエンドツーエンドのトレースのさまざまな側面を有効または無効にするための構成要素。</span><span class="sxs-lookup"><span data-stu-id="4bf0c-101">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endToEndTracing>**  
  
## <a name="syntax"></a><span data-ttu-id="4bf0c-102">構文</span><span class="sxs-lookup"><span data-stu-id="4bf0c-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4bf0c-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4bf0c-103">Attributes and Elements</span></span>  
 <span data-ttu-id="4bf0c-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4bf0c-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4bf0c-105">属性</span><span class="sxs-lookup"><span data-stu-id="4bf0c-105">Attributes</span></span>  
  
|<span data-ttu-id="4bf0c-106">属性</span><span class="sxs-lookup"><span data-stu-id="4bf0c-106">Attribute</span></span>|<span data-ttu-id="4bf0c-107">説明</span><span class="sxs-lookup"><span data-stu-id="4bf0c-107">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="4bf0c-108">アクティビティのトレースが有効かどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="4bf0c-108">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="4bf0c-109">メッセージ フローのトレースが有効かどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="4bf0c-109">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="4bf0c-110">伝達属性が true に設定されているかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="4bf0c-110">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4bf0c-111">子要素</span><span class="sxs-lookup"><span data-stu-id="4bf0c-111">Child Elements</span></span>  
 <span data-ttu-id="4bf0c-112">なし。</span><span class="sxs-lookup"><span data-stu-id="4bf0c-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4bf0c-113">親要素</span><span class="sxs-lookup"><span data-stu-id="4bf0c-113">Parent Elements</span></span>  
  
|<span data-ttu-id="4bf0c-114">要素</span><span class="sxs-lookup"><span data-stu-id="4bf0c-114">Element</span></span>|<span data-ttu-id="4bf0c-115">Description</span><span class="sxs-lookup"><span data-stu-id="4bf0c-115">Description</span></span>|  
|-------------|-----------------|  
|[\<diagnostics>](diagnostics.md)|<span data-ttu-id="4bf0c-116">管理者が行うランタイムの検査と管理の WCF 設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="4bf0c-116">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4bf0c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="4bf0c-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="4bf0c-118">エンドツーエンドのトレース</span><span class="sxs-lookup"><span data-stu-id="4bf0c-118">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)
