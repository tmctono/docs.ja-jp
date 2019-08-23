---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: c46d1fb9eb853e57c7ad1b97eb9a22556cdfb7d8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913099"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="5159f-101">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="5159f-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="5159f-102">ワークフロー サービス内で未処理の例外が発生した場合のアクションを指定するためのサービス動作。</span><span class="sxs-lookup"><span data-stu-id="5159f-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="5159f-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5159f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5159f-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="5159f-104">\<behaviors></span></span>  
<span data-ttu-id="5159f-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="5159f-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="5159f-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5159f-106">\<behavior></span></span>  
<span data-ttu-id="5159f-107">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="5159f-107">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5159f-108">構文</span><span class="sxs-lookup"><span data-stu-id="5159f-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5159f-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5159f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5159f-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5159f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5159f-111">属性</span><span class="sxs-lookup"><span data-stu-id="5159f-111">Attributes</span></span>  
  
|<span data-ttu-id="5159f-112">属性</span><span class="sxs-lookup"><span data-stu-id="5159f-112">Attribute</span></span>|<span data-ttu-id="5159f-113">説明</span><span class="sxs-lookup"><span data-stu-id="5159f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5159f-114">アクション (action)</span><span class="sxs-lookup"><span data-stu-id="5159f-114">action</span></span>|<span data-ttu-id="5159f-115">未処理の例外が発生した場合のアクションを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="5159f-115">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="5159f-116">この属性は <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction> 型です。</span><span class="sxs-lookup"><span data-stu-id="5159f-116">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5159f-117">子要素</span><span class="sxs-lookup"><span data-stu-id="5159f-117">Child Elements</span></span>  
 <span data-ttu-id="5159f-118">なし。</span><span class="sxs-lookup"><span data-stu-id="5159f-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5159f-119">親要素</span><span class="sxs-lookup"><span data-stu-id="5159f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5159f-120">要素</span><span class="sxs-lookup"><span data-stu-id="5159f-120">Element</span></span>|<span data-ttu-id="5159f-121">説明</span><span class="sxs-lookup"><span data-stu-id="5159f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5159f-122">\<servicebehaviors の\<動作 > ></span><span class="sxs-lookup"><span data-stu-id="5159f-122">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="5159f-123">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="5159f-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5159f-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="5159f-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
