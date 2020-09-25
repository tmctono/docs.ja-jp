---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 6b50c0c3db644787fe41ee58ced7eb640e7295f1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190021"
---
# \<endToEndTracing>

<span data-ttu-id="50be9-101">サービス アプリケーションの実行中にエンドツーエンドのトレースのさまざまな側面を有効または無効にするための構成要素。</span><span class="sxs-lookup"><span data-stu-id="50be9-101">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endToEndTracing>**  
  
## <a name="syntax"></a><span data-ttu-id="50be9-102">構文</span><span class="sxs-lookup"><span data-stu-id="50be9-102">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50be9-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="50be9-103">Attributes and Elements</span></span>  

 <span data-ttu-id="50be9-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="50be9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50be9-105">属性</span><span class="sxs-lookup"><span data-stu-id="50be9-105">Attributes</span></span>  
  
|<span data-ttu-id="50be9-106">属性</span><span class="sxs-lookup"><span data-stu-id="50be9-106">Attribute</span></span>|<span data-ttu-id="50be9-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="50be9-107">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="50be9-108">アクティビティのトレースが有効かどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="50be9-108">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="50be9-109">メッセージ フローのトレースが有効かどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="50be9-109">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="50be9-110">伝達属性が true に設定されているかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="50be9-110">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="50be9-111">子要素</span><span class="sxs-lookup"><span data-stu-id="50be9-111">Child Elements</span></span>  

 <span data-ttu-id="50be9-112">なし。</span><span class="sxs-lookup"><span data-stu-id="50be9-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="50be9-113">親要素</span><span class="sxs-lookup"><span data-stu-id="50be9-113">Parent Elements</span></span>  
  
|<span data-ttu-id="50be9-114">要素</span><span class="sxs-lookup"><span data-stu-id="50be9-114">Element</span></span>|<span data-ttu-id="50be9-115">説明</span><span class="sxs-lookup"><span data-stu-id="50be9-115">Description</span></span>|  
|-------------|-----------------|  
|[\<diagnostics>](diagnostics.md)|<span data-ttu-id="50be9-116">管理者が行うランタイムの検査と管理の WCF 設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="50be9-116">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="50be9-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="50be9-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="50be9-118">エンドツーエンドのトレース</span><span class="sxs-lookup"><span data-stu-id="50be9-118">End-to-End Tracing</span></span>](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)
