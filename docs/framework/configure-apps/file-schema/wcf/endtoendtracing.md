---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 1a274f15800c6a132994a2437943c83982de9de0
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855296"
---
# <a name="endtoendtracing"></a><span data-ttu-id="fe41a-101">\<endToEndTracing ></span><span class="sxs-lookup"><span data-stu-id="fe41a-101">\<endToEndTracing></span></span>
<span data-ttu-id="fe41a-102">サービス アプリケーションの実行中にエンドツーエンドのトレースのさまざまな側面を有効または無効にするための構成要素。</span><span class="sxs-lookup"><span data-stu-id="fe41a-102">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
<span data-ttu-id="fe41a-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fe41a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fe41a-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fe41a-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fe41a-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<診断 >** ](diagnostics.md)</span><span class="sxs-lookup"><span data-stu-id="fe41a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)</span></span>\
<span data-ttu-id="fe41a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<endToEndTracing >**</span><span class="sxs-lookup"><span data-stu-id="fe41a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endToEndTracing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe41a-107">構文</span><span class="sxs-lookup"><span data-stu-id="fe41a-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe41a-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="fe41a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fe41a-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe41a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe41a-110">属性</span><span class="sxs-lookup"><span data-stu-id="fe41a-110">Attributes</span></span>  
  
|<span data-ttu-id="fe41a-111">属性</span><span class="sxs-lookup"><span data-stu-id="fe41a-111">Attribute</span></span>|<span data-ttu-id="fe41a-112">説明</span><span class="sxs-lookup"><span data-stu-id="fe41a-112">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="fe41a-113">アクティビティのトレースが有効かどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="fe41a-113">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="fe41a-114">メッセージ フローのトレースが有効かどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="fe41a-114">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="fe41a-115">伝達属性が true に設定されているかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="fe41a-115">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fe41a-116">子要素</span><span class="sxs-lookup"><span data-stu-id="fe41a-116">Child Elements</span></span>  
 <span data-ttu-id="fe41a-117">なし。</span><span class="sxs-lookup"><span data-stu-id="fe41a-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fe41a-118">親要素</span><span class="sxs-lookup"><span data-stu-id="fe41a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="fe41a-119">要素</span><span class="sxs-lookup"><span data-stu-id="fe41a-119">Element</span></span>|<span data-ttu-id="fe41a-120">説明</span><span class="sxs-lookup"><span data-stu-id="fe41a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fe41a-121">\<診断 ></span><span class="sxs-lookup"><span data-stu-id="fe41a-121">\<diagnostics></span></span>](diagnostics.md)|<span data-ttu-id="fe41a-122">管理者が行うランタイムの検査と管理の WCF 設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="fe41a-122">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fe41a-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe41a-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="fe41a-124">エンドツーエンドのトレース</span><span class="sxs-lookup"><span data-stu-id="fe41a-124">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)
