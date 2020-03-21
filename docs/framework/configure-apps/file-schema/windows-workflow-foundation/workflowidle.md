---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: d9eb182ef9c35d2e4c6f5d434e6b200ae2e7ca26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151846"
---
# <a name="workflowidle"></a><span data-ttu-id="1bd3b-101">\<ワークフローアイドル></span><span class="sxs-lookup"><span data-stu-id="1bd3b-101">\<workflowIdle></span></span>
<span data-ttu-id="1bd3b-102">アイドル状態のワークフロー インスタンスのアンロードおよび永続化のタイミングを制御するサービス動作。</span><span class="sxs-lookup"><span data-stu-id="1bd3b-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="1bd3b-103">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1bd3b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1bd3b-104">&nbsp;&nbsp;[**\<システム。サービスモデル>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1bd3b-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="1bd3b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<動作>**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1bd3b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="1bd3b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<サービス動作>**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1bd3b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="1bd3b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<動作>**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1bd3b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="1bd3b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ワークフローアイドル>**</span><span class="sxs-lookup"><span data-stu-id="1bd3b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowIdle>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bd3b-109">構文</span><span class="sxs-lookup"><span data-stu-id="1bd3b-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowIdle timeToPersist="TimeSpan"
                    timeToUnload="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1bd3b-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1bd3b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1bd3b-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1bd3b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1bd3b-112">属性</span><span class="sxs-lookup"><span data-stu-id="1bd3b-112">Attributes</span></span>  
  
|<span data-ttu-id="1bd3b-113">属性</span><span class="sxs-lookup"><span data-stu-id="1bd3b-113">Attribute</span></span>|<span data-ttu-id="1bd3b-114">説明</span><span class="sxs-lookup"><span data-stu-id="1bd3b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1bd3b-115">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="1bd3b-115">timeToPersist</span></span>|<span data-ttu-id="1bd3b-116">ワークフローがアイドル状態から永続化されるまでの継続時間を指定する Timespan 値。</span><span class="sxs-lookup"><span data-stu-id="1bd3b-116">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="1bd3b-117">既定値は TimeSpan.MaxValue です。</span><span class="sxs-lookup"><span data-stu-id="1bd3b-117">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="1bd3b-118">継続時間は、ワークフロー インスタンスがアイドル状態になった時点から開始します。</span><span class="sxs-lookup"><span data-stu-id="1bd3b-118">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="1bd3b-119">この属性は、ワークフロー インスタンスを、可能な限り長くメモリに保持しながら、積極的に永続化しようとする場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1bd3b-119">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="1bd3b-120">この属性は、その値が**timeToUnload**属性より小さい場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="1bd3b-120">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="1bd3b-121">それより大きい場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="1bd3b-121">If it is greater, it is ignored.</span></span> <span data-ttu-id="1bd3b-122">この属性が**timeToUnload**属性で指定された値より前に経過した場合、ワークフローがアンロードされる前に永続化が完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bd3b-122">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="1bd3b-123">これは、ワークフローを永続化するまでアンロード操作に遅延が生じる場合があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="1bd3b-123">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="1bd3b-124">永続化レイヤーは一時的なエラーの再試行処理は行いますが、回復不可能なエラーに対しては例外をスローするだけです。</span><span class="sxs-lookup"><span data-stu-id="1bd3b-124">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="1bd3b-125">したがって、永続化中にスローされる例外は致命的な例外として処理され、ワークフロー インスタンスが中止されます。</span><span class="sxs-lookup"><span data-stu-id="1bd3b-125">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="1bd3b-126">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="1bd3b-126">timeToUnload</span></span>|<span data-ttu-id="1bd3b-127">ワークフローがアイドル状態からアンロードされるまでの継続時間を指定する Timespan 値。</span><span class="sxs-lookup"><span data-stu-id="1bd3b-127">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="1bd3b-128">既定値は 1 分です。</span><span class="sxs-lookup"><span data-stu-id="1bd3b-128">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="1bd3b-129">ワークフローをアンロードすることは、同時に、永続化することも意味します。</span><span class="sxs-lookup"><span data-stu-id="1bd3b-129">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="1bd3b-130">この属性をゼロに設定した場合は、ワークフローがアイドル状態になった直後に、ワークフロー インスタンスが永続化され、アンロードされます。</span><span class="sxs-lookup"><span data-stu-id="1bd3b-130">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="1bd3b-131">この属性を TimeSpan.MaxValue に設定すると、アンロード操作を事実上、無効にします。</span><span class="sxs-lookup"><span data-stu-id="1bd3b-131">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="1bd3b-132">アイドル状態になったワークフロー インスタンスはアンロードされません。</span><span class="sxs-lookup"><span data-stu-id="1bd3b-132">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1bd3b-133">子要素</span><span class="sxs-lookup"><span data-stu-id="1bd3b-133">Child Elements</span></span>  
 <span data-ttu-id="1bd3b-134">[なし] :</span><span class="sxs-lookup"><span data-stu-id="1bd3b-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1bd3b-135">親要素</span><span class="sxs-lookup"><span data-stu-id="1bd3b-135">Parent Elements</span></span>  
  
|<span data-ttu-id="1bd3b-136">要素</span><span class="sxs-lookup"><span data-stu-id="1bd3b-136">Element</span></span>|<span data-ttu-id="1bd3b-137">説明</span><span class="sxs-lookup"><span data-stu-id="1bd3b-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1bd3b-138">\<サービスの\<動作>></span><span class="sxs-lookup"><span data-stu-id="1bd3b-138">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="1bd3b-139">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="1bd3b-139">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1bd3b-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bd3b-140">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
