---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: 1a7c839a5ff8fac9470aea71a4886d9000086e9e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398620"
---
# <a name="states"></a><span data-ttu-id="3e217-101">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="3e217-101">\<states></span></span>
<span data-ttu-id="3e217-102">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="3e217-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="3e217-103">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e217-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="3e217-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3e217-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3e217-105">&nbsp;&nbsp;[ **\<system.ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="3e217-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="3e217-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="3e217-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="3e217-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="3e217-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="3e217-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="3e217-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="3e217-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowInstanceQueries >** ](workflowinstancequeries.md)</span><span class="sxs-lookup"><span data-stu-id="3e217-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)</span></span>\
<span data-ttu-id="3e217-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowInstanceQuery >** ](workflowinstancequery.md)</span><span class="sxs-lookup"><span data-stu-id="3e217-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)</span></span>\
<span data-ttu-id="3e217-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<状態 >**</span><span class="sxs-lookup"><span data-stu-id="3e217-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e217-112">構文</span><span class="sxs-lookup"><span data-stu-id="3e217-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e217-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3e217-113">Attributes and Elements</span></span>  
 <span data-ttu-id="3e217-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e217-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e217-115">属性</span><span class="sxs-lookup"><span data-stu-id="3e217-115">Attributes</span></span>  
 <span data-ttu-id="3e217-116">なし。</span><span class="sxs-lookup"><span data-stu-id="3e217-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3e217-117">子要素</span><span class="sxs-lookup"><span data-stu-id="3e217-117">Child Elements</span></span>  
  
|<span data-ttu-id="3e217-118">要素</span><span class="sxs-lookup"><span data-stu-id="3e217-118">Element</span></span>|<span data-ttu-id="3e217-119">説明</span><span class="sxs-lookup"><span data-stu-id="3e217-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3e217-120">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="3e217-120">\<state></span></span>](states.md)|<span data-ttu-id="3e217-121">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態。</span><span class="sxs-lookup"><span data-stu-id="3e217-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3e217-122">親要素</span><span class="sxs-lookup"><span data-stu-id="3e217-122">Parent Elements</span></span>  
  
|<span data-ttu-id="3e217-123">要素</span><span class="sxs-lookup"><span data-stu-id="3e217-123">Element</span></span>|<span data-ttu-id="3e217-124">説明</span><span class="sxs-lookup"><span data-stu-id="3e217-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3e217-125">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="3e217-125">\<workflowInstanceQuery></span></span>](workflowinstancequery.md)|<span data-ttu-id="3e217-126">開始したイベントや完了したイベントなど、ワークフロー インスタンスのライフサイクルの変化を追跡するクエリ。</span><span class="sxs-lookup"><span data-stu-id="3e217-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e217-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="3e217-127">Remarks</span></span>  
 <span data-ttu-id="3e217-128">返されたレコードは、このコレクションの状態でフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="3e217-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="3e217-129">次の表に、有効な状態の値を示します。</span><span class="sxs-lookup"><span data-stu-id="3e217-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="3e217-130">状態</span><span class="sxs-lookup"><span data-stu-id="3e217-130">State</span></span>|<span data-ttu-id="3e217-131">説明</span><span class="sxs-lookup"><span data-stu-id="3e217-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3e217-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="3e217-132">Aborted</span></span>|<span data-ttu-id="3e217-133">ワークフロー インスタンスは中止されました。</span><span class="sxs-lookup"><span data-stu-id="3e217-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="3e217-134">完了</span><span class="sxs-lookup"><span data-stu-id="3e217-134">Completed</span></span>|<span data-ttu-id="3e217-135">ワークフロー インスタンスは完了しました。</span><span class="sxs-lookup"><span data-stu-id="3e217-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="3e217-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="3e217-136">Deleted</span></span>|<span data-ttu-id="3e217-137">ワークフロー インスタンスは削除されました。</span><span class="sxs-lookup"><span data-stu-id="3e217-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="3e217-138">アイドル</span><span class="sxs-lookup"><span data-stu-id="3e217-138">Idle</span></span>|<span data-ttu-id="3e217-139">ワークフロー インスタンスはアイドル状態です。</span><span class="sxs-lookup"><span data-stu-id="3e217-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="3e217-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="3e217-140">Persisted</span></span>|<span data-ttu-id="3e217-141">ワークフロー インスタンスは永続化されました。</span><span class="sxs-lookup"><span data-stu-id="3e217-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="3e217-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="3e217-142">Resumed</span></span>|<span data-ttu-id="3e217-143">ワークフロー インスタンスが再開されました。</span><span class="sxs-lookup"><span data-stu-id="3e217-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="3e217-144">Started</span><span class="sxs-lookup"><span data-stu-id="3e217-144">Started</span></span>|<span data-ttu-id="3e217-145">ワークフロー インスタンスが開始されました。</span><span class="sxs-lookup"><span data-stu-id="3e217-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="3e217-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="3e217-146">UnhandledException</span></span>|<span data-ttu-id="3e217-147">ワークフロー インスタンスで未処理の例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="3e217-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="3e217-148">アンロードされました</span><span class="sxs-lookup"><span data-stu-id="3e217-148">Unloaded</span></span>|<span data-ttu-id="3e217-149">ワークフロー インスタンスはアンロードされました。</span><span class="sxs-lookup"><span data-stu-id="3e217-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="3e217-150">Canceled</span><span class="sxs-lookup"><span data-stu-id="3e217-150">Canceled</span></span>|<span data-ttu-id="3e217-151">ワークフロー インスタンスは取り消されました。</span><span class="sxs-lookup"><span data-stu-id="3e217-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="3e217-152">中断</span><span class="sxs-lookup"><span data-stu-id="3e217-152">Suspended</span></span>|<span data-ttu-id="3e217-153">ワークフロー インスタンスが中断されています。</span><span class="sxs-lookup"><span data-stu-id="3e217-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="3e217-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="3e217-154">Terminated</span></span>|<span data-ttu-id="3e217-155">ワークフロー インスタンスは終了しました。</span><span class="sxs-lookup"><span data-stu-id="3e217-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="3e217-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="3e217-156">Unsuspended</span></span>|<span data-ttu-id="3e217-157">ワークフロー インスタンスの中断が解除されました。</span><span class="sxs-lookup"><span data-stu-id="3e217-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3e217-158">例</span><span class="sxs-lookup"><span data-stu-id="3e217-158">Example</span></span>  
 <span data-ttu-id="3e217-159">次の構成は、このクエリを使用して、`Started` インスタンス状態のワークフロー インスタンス レベルの追跡レコードを定期受信します。</span><span class="sxs-lookup"><span data-stu-id="3e217-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e217-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e217-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3e217-161">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="3e217-161">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3e217-162">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="3e217-162">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
