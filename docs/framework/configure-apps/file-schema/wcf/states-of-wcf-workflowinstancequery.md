---
title: <states>WCF の<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: 5b779cf1074687dbd648b23d04f7cf3a354a2014
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855029"
---
# <a name="states-of-wcf-workflowinstancequery"></a><span data-ttu-id="e8f6f-102">\<WCF、 \<workflowinstancequery > の > 状態</span><span class="sxs-lookup"><span data-stu-id="e8f6f-102">\<states> of WCF, \<workflowInstanceQuery></span></span>

<span data-ttu-id="e8f6f-103">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
<span data-ttu-id="e8f6f-104">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="e8f6f-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e8f6f-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e8f6f-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e8f6f-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e8f6f-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="e8f6f-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="e8f6f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<プロファイル >** </span><span class="sxs-lookup"><span data-stu-id="e8f6f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="e8f6f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="e8f6f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="e8f6f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="e8f6f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="e8f6f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowInstanceQueries >** ](workflowinstancequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="e8f6f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)</span></span>\
<span data-ttu-id="e8f6f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowInstanceQuery >** ](workflowinstancequery-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="e8f6f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)</span></span>\
<span data-ttu-id="e8f6f-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<状態 >**</span><span class="sxs-lookup"><span data-stu-id="e8f6f-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8f6f-114">構文</span><span class="sxs-lookup"><span data-stu-id="e8f6f-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <workflowInstanceQueries>
          <workflowInstanceQuery>
            <states>
              <state name="Name" />
            </states>
          </workflowInstanceQuery>
        </workflowInstanceQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8f6f-115">属性と要素</span><span class="sxs-lookup"><span data-stu-id="e8f6f-115">Attributes and elements</span></span>

<span data-ttu-id="e8f6f-116">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8f6f-117">属性</span><span class="sxs-lookup"><span data-stu-id="e8f6f-117">Attributes</span></span>  

<span data-ttu-id="e8f6f-118">なし。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-118">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e8f6f-119">子要素</span><span class="sxs-lookup"><span data-stu-id="e8f6f-119">Child elements</span></span>
  
|<span data-ttu-id="e8f6f-120">要素</span><span class="sxs-lookup"><span data-stu-id="e8f6f-120">Element</span></span>|<span data-ttu-id="e8f6f-121">説明</span><span class="sxs-lookup"><span data-stu-id="e8f6f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8f6f-122">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="e8f6f-122">\<states></span></span>](state-of-wcf-workflowinstancequery.md)|<span data-ttu-id="e8f6f-123">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-123">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e8f6f-124">親要素</span><span class="sxs-lookup"><span data-stu-id="e8f6f-124">Parent elements</span></span>  
  
|<span data-ttu-id="e8f6f-125">要素</span><span class="sxs-lookup"><span data-stu-id="e8f6f-125">Element</span></span>|<span data-ttu-id="e8f6f-126">説明</span><span class="sxs-lookup"><span data-stu-id="e8f6f-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8f6f-127">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="e8f6f-127">\<workflowInstanceQuery></span></span>](../windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="e8f6f-128">開始したイベントや完了したイベントなど、ワークフロー インスタンスのライフサイクルの変化を追跡するクエリ。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-128">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8f6f-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="e8f6f-129">Remarks</span></span>

<span data-ttu-id="e8f6f-130">返されたレコードは、このコレクションの状態でフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-130">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="e8f6f-131">次の表に、有効な状態の値を示します。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-131">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="e8f6f-132">状態</span><span class="sxs-lookup"><span data-stu-id="e8f6f-132">State</span></span>|<span data-ttu-id="e8f6f-133">説明</span><span class="sxs-lookup"><span data-stu-id="e8f6f-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e8f6f-134">Aborted</span><span class="sxs-lookup"><span data-stu-id="e8f6f-134">Aborted</span></span>|<span data-ttu-id="e8f6f-135">ワークフロー インスタンスは中止されました。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-135">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="e8f6f-136">完了</span><span class="sxs-lookup"><span data-stu-id="e8f6f-136">Completed</span></span>|<span data-ttu-id="e8f6f-137">ワークフロー インスタンスは完了しました。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-137">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="e8f6f-138">Deleted</span><span class="sxs-lookup"><span data-stu-id="e8f6f-138">Deleted</span></span>|<span data-ttu-id="e8f6f-139">ワークフロー インスタンスは削除されました。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-139">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="e8f6f-140">アイドル</span><span class="sxs-lookup"><span data-stu-id="e8f6f-140">Idle</span></span>|<span data-ttu-id="e8f6f-141">ワークフロー インスタンスはアイドル状態です。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-141">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="e8f6f-142">Persisted</span><span class="sxs-lookup"><span data-stu-id="e8f6f-142">Persisted</span></span>|<span data-ttu-id="e8f6f-143">ワークフロー インスタンスは永続化されました。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-143">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="e8f6f-144">Resumed</span><span class="sxs-lookup"><span data-stu-id="e8f6f-144">Resumed</span></span>|<span data-ttu-id="e8f6f-145">ワークフロー インスタンスが再開されました。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-145">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="e8f6f-146">Started</span><span class="sxs-lookup"><span data-stu-id="e8f6f-146">Started</span></span>|<span data-ttu-id="e8f6f-147">ワークフロー インスタンスが開始されました。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-147">The workflow instance is started.</span></span>|  
|<span data-ttu-id="e8f6f-148">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="e8f6f-148">UnhandledException</span></span>|<span data-ttu-id="e8f6f-149">ワークフロー インスタンスで未処理の例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-149">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="e8f6f-150">アンロードされました</span><span class="sxs-lookup"><span data-stu-id="e8f6f-150">Unloaded</span></span>|<span data-ttu-id="e8f6f-151">ワークフロー インスタンスはアンロードされました。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-151">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="e8f6f-152">Canceled</span><span class="sxs-lookup"><span data-stu-id="e8f6f-152">Canceled</span></span>|<span data-ttu-id="e8f6f-153">ワークフロー インスタンスは取り消されました。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-153">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="e8f6f-154">中断</span><span class="sxs-lookup"><span data-stu-id="e8f6f-154">Suspended</span></span>|<span data-ttu-id="e8f6f-155">ワークフロー インスタンスが中断されています。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-155">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="e8f6f-156">Terminated</span><span class="sxs-lookup"><span data-stu-id="e8f6f-156">Terminated</span></span>|<span data-ttu-id="e8f6f-157">ワークフロー インスタンスは終了しました。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-157">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="e8f6f-158">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="e8f6f-158">Unsuspended</span></span>|<span data-ttu-id="e8f6f-159">ワークフロー インスタンスの中断が解除されました。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-159">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e8f6f-160">例</span><span class="sxs-lookup"><span data-stu-id="e8f6f-160">Example</span></span>

<span data-ttu-id="e8f6f-161">次の構成は、このクエリを使用して、`Started` インスタンス状態のワークフロー インスタンス レベルの追跡レコードを定期受信します。</span><span class="sxs-lookup"><span data-stu-id="e8f6f-161">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="e8f6f-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8f6f-162">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e8f6f-163">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="e8f6f-163">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e8f6f-164">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="e8f6f-164">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
