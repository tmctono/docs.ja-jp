---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 790e852eb515e19afc324f6e1c25db81ed22999c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148673"
---
# \<workflowIdle>

<span data-ttu-id="2a363-101">アイドル状態のワークフロー インスタンスのアンロードおよび永続化のタイミングを制御するサービス動作。</span><span class="sxs-lookup"><span data-stu-id="2a363-101">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowIdle>**  
  
## <a name="syntax"></a><span data-ttu-id="2a363-102">構文</span><span class="sxs-lookup"><span data-stu-id="2a363-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a363-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2a363-103">Attributes and Elements</span></span>  

 <span data-ttu-id="2a363-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2a363-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a363-105">属性</span><span class="sxs-lookup"><span data-stu-id="2a363-105">Attributes</span></span>  
  
|<span data-ttu-id="2a363-106">属性</span><span class="sxs-lookup"><span data-stu-id="2a363-106">Attribute</span></span>|<span data-ttu-id="2a363-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="2a363-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2a363-108">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="2a363-108">timeToPersist</span></span>|<span data-ttu-id="2a363-109">ワークフローがアイドル状態から永続化されるまでの継続時間を指定する Timespan 値。</span><span class="sxs-lookup"><span data-stu-id="2a363-109">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="2a363-110">既定値は TimeSpan.MaxValue です。</span><span class="sxs-lookup"><span data-stu-id="2a363-110">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="2a363-111">継続時間は、ワークフロー インスタンスがアイドル状態になった時点から開始します。</span><span class="sxs-lookup"><span data-stu-id="2a363-111">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="2a363-112">この属性は、ワークフロー インスタンスを、可能な限り長くメモリに保持しながら、積極的に永続化しようとする場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2a363-112">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="2a363-113">この属性は、値が **timeToUnload** 属性より小さい場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="2a363-113">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="2a363-114">それより大きい場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="2a363-114">If it is greater, it is ignored.</span></span> <span data-ttu-id="2a363-115">**TimeToUnload**属性によって指定された値の前にこの属性が経過した場合、ワークフローがアンロードされる前に永続化を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a363-115">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="2a363-116">これは、ワークフローを永続化するまでアンロード操作に遅延が生じる場合があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2a363-116">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="2a363-117">永続化レイヤーは一時的なエラーの再試行処理は行いますが、回復不可能なエラーに対しては例外をスローするだけです。</span><span class="sxs-lookup"><span data-stu-id="2a363-117">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="2a363-118">したがって、永続化中にスローされる例外は致命的な例外として処理され、ワークフロー インスタンスが中止されます。</span><span class="sxs-lookup"><span data-stu-id="2a363-118">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="2a363-119">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="2a363-119">timeToUnload</span></span>|<span data-ttu-id="2a363-120">ワークフローがアイドル状態からアンロードされるまでの継続時間を指定する Timespan 値。</span><span class="sxs-lookup"><span data-stu-id="2a363-120">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="2a363-121">既定値は 1 分です。</span><span class="sxs-lookup"><span data-stu-id="2a363-121">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="2a363-122">ワークフローをアンロードすることは、同時に、永続化することも意味します。</span><span class="sxs-lookup"><span data-stu-id="2a363-122">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="2a363-123">この属性をゼロに設定した場合は、ワークフローがアイドル状態になった直後に、ワークフロー インスタンスが永続化され、アンロードされます。</span><span class="sxs-lookup"><span data-stu-id="2a363-123">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="2a363-124">この属性を TimeSpan.MaxValue に設定すると、アンロード操作を事実上、無効にします。</span><span class="sxs-lookup"><span data-stu-id="2a363-124">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="2a363-125">アイドル状態になったワークフロー インスタンスはアンロードされません。</span><span class="sxs-lookup"><span data-stu-id="2a363-125">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a363-126">子要素</span><span class="sxs-lookup"><span data-stu-id="2a363-126">Child Elements</span></span>  

 <span data-ttu-id="2a363-127">なし。</span><span class="sxs-lookup"><span data-stu-id="2a363-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2a363-128">親要素</span><span class="sxs-lookup"><span data-stu-id="2a363-128">Parent Elements</span></span>  
  
|<span data-ttu-id="2a363-129">要素</span><span class="sxs-lookup"><span data-stu-id="2a363-129">Element</span></span>|<span data-ttu-id="2a363-130">説明</span><span class="sxs-lookup"><span data-stu-id="2a363-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a363-131">\<serviceBehaviors> の \<behavior></span><span class="sxs-lookup"><span data-stu-id="2a363-131">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="2a363-132">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a363-132">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2a363-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a363-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
