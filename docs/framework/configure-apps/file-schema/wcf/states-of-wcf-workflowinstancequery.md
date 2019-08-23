---
title: <states>WCF の<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: ef4ce4b6fa6e60ead10b196b10a7c1489e15ac25
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938977"
---
# <a name="states-of-wcf-workflowinstancequery"></a><span data-ttu-id="2f155-102">\<WCF、 \<workflowinstancequery > の > 状態</span><span class="sxs-lookup"><span data-stu-id="2f155-102">\<states> of WCF, \<workflowInstanceQuery></span></span>

<span data-ttu-id="2f155-103">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="2f155-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
<span data-ttu-id="2f155-104">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f155-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="2f155-105">\<system.serviceModel> \<tracking></span><span class="sxs-lookup"><span data-stu-id="2f155-105">\<system.serviceModel> \<tracking></span></span>  
<span data-ttu-id="2f155-106">\<プロファイル ></span><span class="sxs-lookup"><span data-stu-id="2f155-106">\<profiles></span></span>  
<span data-ttu-id="2f155-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2f155-107">\<trackingProfile></span></span>  
<span data-ttu-id="2f155-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="2f155-108">\<workflow></span></span>  
<span data-ttu-id="2f155-109">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="2f155-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="2f155-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="2f155-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="2f155-111">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="2f155-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f155-112">構文</span><span class="sxs-lookup"><span data-stu-id="2f155-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f155-113">属性と要素</span><span class="sxs-lookup"><span data-stu-id="2f155-113">Attributes and elements</span></span>

<span data-ttu-id="2f155-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f155-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f155-115">属性</span><span class="sxs-lookup"><span data-stu-id="2f155-115">Attributes</span></span>  

<span data-ttu-id="2f155-116">なし。</span><span class="sxs-lookup"><span data-stu-id="2f155-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2f155-117">子要素</span><span class="sxs-lookup"><span data-stu-id="2f155-117">Child elements</span></span>
  
|<span data-ttu-id="2f155-118">要素</span><span class="sxs-lookup"><span data-stu-id="2f155-118">Element</span></span>|<span data-ttu-id="2f155-119">説明</span><span class="sxs-lookup"><span data-stu-id="2f155-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f155-120">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="2f155-120">\<states></span></span>](state-of-wcf-workflowinstancequery.md)|<span data-ttu-id="2f155-121">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態。</span><span class="sxs-lookup"><span data-stu-id="2f155-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2f155-122">親要素</span><span class="sxs-lookup"><span data-stu-id="2f155-122">Parent elements</span></span>  
  
|<span data-ttu-id="2f155-123">要素</span><span class="sxs-lookup"><span data-stu-id="2f155-123">Element</span></span>|<span data-ttu-id="2f155-124">説明</span><span class="sxs-lookup"><span data-stu-id="2f155-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f155-125">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="2f155-125">\<workflowInstanceQuery></span></span>](../windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="2f155-126">開始したイベントや完了したイベントなど、ワークフロー インスタンスのライフサイクルの変化を追跡するクエリ。</span><span class="sxs-lookup"><span data-stu-id="2f155-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f155-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="2f155-127">Remarks</span></span>

<span data-ttu-id="2f155-128">返されたレコードは、このコレクションの状態でフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="2f155-128">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="2f155-129">次の表に、有効な状態の値を示します。</span><span class="sxs-lookup"><span data-stu-id="2f155-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="2f155-130">状態</span><span class="sxs-lookup"><span data-stu-id="2f155-130">State</span></span>|<span data-ttu-id="2f155-131">説明</span><span class="sxs-lookup"><span data-stu-id="2f155-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2f155-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="2f155-132">Aborted</span></span>|<span data-ttu-id="2f155-133">ワークフロー インスタンスは中止されました。</span><span class="sxs-lookup"><span data-stu-id="2f155-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="2f155-134">完了</span><span class="sxs-lookup"><span data-stu-id="2f155-134">Completed</span></span>|<span data-ttu-id="2f155-135">ワークフロー インスタンスは完了しました。</span><span class="sxs-lookup"><span data-stu-id="2f155-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="2f155-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="2f155-136">Deleted</span></span>|<span data-ttu-id="2f155-137">ワークフロー インスタンスは削除されました。</span><span class="sxs-lookup"><span data-stu-id="2f155-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="2f155-138">アイドル</span><span class="sxs-lookup"><span data-stu-id="2f155-138">Idle</span></span>|<span data-ttu-id="2f155-139">ワークフロー インスタンスはアイドル状態です。</span><span class="sxs-lookup"><span data-stu-id="2f155-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="2f155-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="2f155-140">Persisted</span></span>|<span data-ttu-id="2f155-141">ワークフロー インスタンスは永続化されました。</span><span class="sxs-lookup"><span data-stu-id="2f155-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="2f155-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="2f155-142">Resumed</span></span>|<span data-ttu-id="2f155-143">ワークフロー インスタンスが再開されました。</span><span class="sxs-lookup"><span data-stu-id="2f155-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="2f155-144">Started</span><span class="sxs-lookup"><span data-stu-id="2f155-144">Started</span></span>|<span data-ttu-id="2f155-145">ワークフロー インスタンスが開始されました。</span><span class="sxs-lookup"><span data-stu-id="2f155-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="2f155-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="2f155-146">UnhandledException</span></span>|<span data-ttu-id="2f155-147">ワークフロー インスタンスで未処理の例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="2f155-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="2f155-148">アンロードされました</span><span class="sxs-lookup"><span data-stu-id="2f155-148">Unloaded</span></span>|<span data-ttu-id="2f155-149">ワークフロー インスタンスはアンロードされました。</span><span class="sxs-lookup"><span data-stu-id="2f155-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="2f155-150">Canceled</span><span class="sxs-lookup"><span data-stu-id="2f155-150">Canceled</span></span>|<span data-ttu-id="2f155-151">ワークフロー インスタンスは取り消されました。</span><span class="sxs-lookup"><span data-stu-id="2f155-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="2f155-152">中断</span><span class="sxs-lookup"><span data-stu-id="2f155-152">Suspended</span></span>|<span data-ttu-id="2f155-153">ワークフロー インスタンスが中断されています。</span><span class="sxs-lookup"><span data-stu-id="2f155-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="2f155-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="2f155-154">Terminated</span></span>|<span data-ttu-id="2f155-155">ワークフロー インスタンスは終了しました。</span><span class="sxs-lookup"><span data-stu-id="2f155-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="2f155-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="2f155-156">Unsuspended</span></span>|<span data-ttu-id="2f155-157">ワークフロー インスタンスの中断が解除されました。</span><span class="sxs-lookup"><span data-stu-id="2f155-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2f155-158">例</span><span class="sxs-lookup"><span data-stu-id="2f155-158">Example</span></span>

<span data-ttu-id="2f155-159">次の構成は、このクエリを使用して、`Started` インスタンス状態のワークフロー インスタンス レベルの追跡レコードを定期受信します。</span><span class="sxs-lookup"><span data-stu-id="2f155-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="2f155-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f155-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2f155-161">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="2f155-161">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2f155-162">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="2f155-162">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
