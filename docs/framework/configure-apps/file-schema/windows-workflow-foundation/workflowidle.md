---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 1d8ddaf5d69d87ff6112b5cbb285f0ccfda724e2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397534"
---
# <a name="workflowidle"></a><span data-ttu-id="8e9ef-101">\<workflowIdle ></span><span class="sxs-lookup"><span data-stu-id="8e9ef-101">\<workflowIdle></span></span>
<span data-ttu-id="8e9ef-102">アイドル状態のワークフロー インスタンスのアンロードおよび永続化のタイミングを制御するサービス動作。</span><span class="sxs-lookup"><span data-stu-id="8e9ef-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="8e9ef-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8e9ef-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8e9ef-104">&nbsp;&nbsp;[ **\<system.ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="8e9ef-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="8e9ef-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="8e9ef-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="8e9ef-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="8e9ef-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="8e9ef-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="8e9ef-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="8e9ef-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<workflowIdle >**</span><span class="sxs-lookup"><span data-stu-id="8e9ef-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowIdle>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e9ef-109">構文</span><span class="sxs-lookup"><span data-stu-id="8e9ef-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e9ef-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8e9ef-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8e9ef-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8e9ef-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e9ef-112">属性</span><span class="sxs-lookup"><span data-stu-id="8e9ef-112">Attributes</span></span>  
  
|<span data-ttu-id="8e9ef-113">属性</span><span class="sxs-lookup"><span data-stu-id="8e9ef-113">Attribute</span></span>|<span data-ttu-id="8e9ef-114">説明</span><span class="sxs-lookup"><span data-stu-id="8e9ef-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e9ef-115">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="8e9ef-115">timeToPersist</span></span>|<span data-ttu-id="8e9ef-116">ワークフローがアイドル状態になってから永続化されるまでの期間を指定する Timespan 値。</span><span class="sxs-lookup"><span data-stu-id="8e9ef-116">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="8e9ef-117">既定値は TimeSpan です。</span><span class="sxs-lookup"><span data-stu-id="8e9ef-117">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="8e9ef-118">継続時間は、ワークフロー インスタンスがアイドル状態になった時点から開始します。</span><span class="sxs-lookup"><span data-stu-id="8e9ef-118">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="8e9ef-119">この属性は、インスタンスを可能な限りメモリに保持しながら、ワークフローインスタンスをより積極的に永続化する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="8e9ef-119">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="8e9ef-120">この属性は、値が**timeToUnload**属性より小さい場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="8e9ef-120">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="8e9ef-121">それより大きい場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="8e9ef-121">If it is greater, it is ignored.</span></span> <span data-ttu-id="8e9ef-122">**TimeToUnload**属性によって指定された値の前にこの属性が経過した場合、ワークフローがアンロードされる前に永続化を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e9ef-122">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="8e9ef-123">これは、ワークフローを永続化するまでアンロード操作に遅延が生じる場合があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8e9ef-123">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="8e9ef-124">永続化レイヤーは一時的なエラーの再試行処理は行いますが、回復不可能なエラーに対しては例外をスローするだけです。</span><span class="sxs-lookup"><span data-stu-id="8e9ef-124">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="8e9ef-125">したがって、永続化中にスローされる例外は致命的な例外として処理され、ワークフロー インスタンスが中止されます。</span><span class="sxs-lookup"><span data-stu-id="8e9ef-125">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="8e9ef-126">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="8e9ef-126">timeToUnload</span></span>|<span data-ttu-id="8e9ef-127">ワークフローがアイドル状態からアンロードされるまでの継続時間を指定する Timespan 値。</span><span class="sxs-lookup"><span data-stu-id="8e9ef-127">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="8e9ef-128">既定値は 1 分です。</span><span class="sxs-lookup"><span data-stu-id="8e9ef-128">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="8e9ef-129">ワークフローをアンロードすることは、同時に、永続化することも意味します。</span><span class="sxs-lookup"><span data-stu-id="8e9ef-129">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="8e9ef-130">この属性が0に設定されている場合は、ワークフローがアイドル状態になった直後にワークフローインスタンスが永続化され、アンロードされます。</span><span class="sxs-lookup"><span data-stu-id="8e9ef-130">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="8e9ef-131">この属性を TimeSpan に設定すると、アンロード操作が実質的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="8e9ef-131">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="8e9ef-132">アイドル状態になったワークフロー インスタンスはアンロードされません。</span><span class="sxs-lookup"><span data-stu-id="8e9ef-132">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e9ef-133">子要素</span><span class="sxs-lookup"><span data-stu-id="8e9ef-133">Child Elements</span></span>  
 <span data-ttu-id="8e9ef-134">なし。</span><span class="sxs-lookup"><span data-stu-id="8e9ef-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e9ef-135">親要素</span><span class="sxs-lookup"><span data-stu-id="8e9ef-135">Parent Elements</span></span>  
  
|<span data-ttu-id="8e9ef-136">要素</span><span class="sxs-lookup"><span data-stu-id="8e9ef-136">Element</span></span>|<span data-ttu-id="8e9ef-137">説明</span><span class="sxs-lookup"><span data-stu-id="8e9ef-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e9ef-138">\<servicebehaviors の\<動作 > ></span><span class="sxs-lookup"><span data-stu-id="8e9ef-138">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="8e9ef-139">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="8e9ef-139">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e9ef-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e9ef-140">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
