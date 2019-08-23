---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 16a485b6d0ba2584cccd08a36506582fd3930f71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947168"
---
# <a name="workflowidle"></a><span data-ttu-id="e5561-101">\<workflowIdle ></span><span class="sxs-lookup"><span data-stu-id="e5561-101">\<workflowIdle></span></span>
<span data-ttu-id="e5561-102">アイドル状態のワークフロー インスタンスのアンロードおよび永続化のタイミングを制御するサービス動作。</span><span class="sxs-lookup"><span data-stu-id="e5561-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="e5561-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e5561-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e5561-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="e5561-104">\<behaviors></span></span>  
<span data-ttu-id="e5561-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="e5561-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="e5561-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e5561-106">\<behavior></span></span>  
<span data-ttu-id="e5561-107">\<workflowIdle ></span><span class="sxs-lookup"><span data-stu-id="e5561-107">\<workflowIdle></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5561-108">構文</span><span class="sxs-lookup"><span data-stu-id="e5561-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5561-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e5561-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e5561-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5561-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5561-111">属性</span><span class="sxs-lookup"><span data-stu-id="e5561-111">Attributes</span></span>  
  
|<span data-ttu-id="e5561-112">属性</span><span class="sxs-lookup"><span data-stu-id="e5561-112">Attribute</span></span>|<span data-ttu-id="e5561-113">説明</span><span class="sxs-lookup"><span data-stu-id="e5561-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5561-114">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="e5561-114">timeToPersist</span></span>|<span data-ttu-id="e5561-115">ワークフローがアイドル状態になってから永続化されるまでの期間を指定する Timespan 値。</span><span class="sxs-lookup"><span data-stu-id="e5561-115">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="e5561-116">既定値は TimeSpan です。</span><span class="sxs-lookup"><span data-stu-id="e5561-116">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="e5561-117">継続時間は、ワークフロー インスタンスがアイドル状態になった時点から開始します。</span><span class="sxs-lookup"><span data-stu-id="e5561-117">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="e5561-118">この属性は、インスタンスを可能な限りメモリに保持しながら、ワークフローインスタンスをより積極的に永続化する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="e5561-118">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="e5561-119">この属性は、値が**timeToUnload**属性より小さい場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="e5561-119">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="e5561-120">それより大きい場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="e5561-120">If it is greater, it is ignored.</span></span> <span data-ttu-id="e5561-121">**TimeToUnload**属性によって指定された値の前にこの属性が経過した場合、ワークフローがアンロードされる前に永続化を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5561-121">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="e5561-122">これは、ワークフローを永続化するまでアンロード操作に遅延が生じる場合があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e5561-122">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="e5561-123">永続化レイヤーは一時的なエラーの再試行処理は行いますが、回復不可能なエラーに対しては例外をスローするだけです。</span><span class="sxs-lookup"><span data-stu-id="e5561-123">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="e5561-124">したがって、永続化中にスローされる例外は致命的な例外として処理され、ワークフロー インスタンスが中止されます。</span><span class="sxs-lookup"><span data-stu-id="e5561-124">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="e5561-125">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="e5561-125">timeToUnload</span></span>|<span data-ttu-id="e5561-126">ワークフローがアイドル状態からアンロードされるまでの継続時間を指定する Timespan 値。</span><span class="sxs-lookup"><span data-stu-id="e5561-126">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="e5561-127">既定値は 1 分です。</span><span class="sxs-lookup"><span data-stu-id="e5561-127">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="e5561-128">ワークフローをアンロードすることは、同時に、永続化することも意味します。</span><span class="sxs-lookup"><span data-stu-id="e5561-128">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="e5561-129">この属性が0に設定されている場合は、ワークフローがアイドル状態になった直後にワークフローインスタンスが永続化され、アンロードされます。</span><span class="sxs-lookup"><span data-stu-id="e5561-129">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="e5561-130">この属性を TimeSpan に設定すると、アンロード操作が実質的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="e5561-130">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="e5561-131">アイドル状態になったワークフロー インスタンスはアンロードされません。</span><span class="sxs-lookup"><span data-stu-id="e5561-131">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5561-132">子要素</span><span class="sxs-lookup"><span data-stu-id="e5561-132">Child Elements</span></span>  
 <span data-ttu-id="e5561-133">なし。</span><span class="sxs-lookup"><span data-stu-id="e5561-133">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5561-134">親要素</span><span class="sxs-lookup"><span data-stu-id="e5561-134">Parent Elements</span></span>  
  
|<span data-ttu-id="e5561-135">要素</span><span class="sxs-lookup"><span data-stu-id="e5561-135">Element</span></span>|<span data-ttu-id="e5561-136">説明</span><span class="sxs-lookup"><span data-stu-id="e5561-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5561-137">\<servicebehaviors の\<動作 > ></span><span class="sxs-lookup"><span data-stu-id="e5561-137">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="e5561-138">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5561-138">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5561-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5561-139">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
