---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: 30cb2efa4c00c8b292a8ace6a03306d6ac76a7f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073123"
---
# <a name="states"></a><span data-ttu-id="c5807-101">\<states></span><span class="sxs-lookup"><span data-stu-id="c5807-101">\<states></span></span>
<span data-ttu-id="c5807-102">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="c5807-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="c5807-103">追跡プロファイルのクエリの詳細については、次を参照してください[追跡プロファイル。](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="c5807-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="c5807-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c5807-104">\<system.serviceModel></span></span>  
<span data-ttu-id="c5807-105">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="c5807-105">\<tracking></span></span>  
<span data-ttu-id="c5807-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="c5807-106">\<trackingProfile></span></span>  
<span data-ttu-id="c5807-107">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="c5807-107">\<workflow></span></span>  
<span data-ttu-id="c5807-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="c5807-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="c5807-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="c5807-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="c5807-110">\<states></span><span class="sxs-lookup"><span data-stu-id="c5807-110">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5807-111">構文</span><span class="sxs-lookup"><span data-stu-id="c5807-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5807-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c5807-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c5807-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5807-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5807-114">属性</span><span class="sxs-lookup"><span data-stu-id="c5807-114">Attributes</span></span>  
 <span data-ttu-id="c5807-115">なし。</span><span class="sxs-lookup"><span data-stu-id="c5807-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c5807-116">子要素</span><span class="sxs-lookup"><span data-stu-id="c5807-116">Child Elements</span></span>  
  
|<span data-ttu-id="c5807-117">要素</span><span class="sxs-lookup"><span data-stu-id="c5807-117">Element</span></span>|<span data-ttu-id="c5807-118">説明</span><span class="sxs-lookup"><span data-stu-id="c5807-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5807-119">\<state></span><span class="sxs-lookup"><span data-stu-id="c5807-119">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="c5807-120">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態。</span><span class="sxs-lookup"><span data-stu-id="c5807-120">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c5807-121">親要素</span><span class="sxs-lookup"><span data-stu-id="c5807-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c5807-122">要素</span><span class="sxs-lookup"><span data-stu-id="c5807-122">Element</span></span>|<span data-ttu-id="c5807-123">説明</span><span class="sxs-lookup"><span data-stu-id="c5807-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5807-124">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="c5807-124">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="c5807-125">開始したイベントや完了したイベントなど、ワークフロー インスタンスのライフサイクルの変化を追跡するクエリ。</span><span class="sxs-lookup"><span data-stu-id="c5807-125">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5807-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="c5807-126">Remarks</span></span>  
 <span data-ttu-id="c5807-127">返されたレコードは、このコレクションの状態でフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="c5807-127">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="c5807-128">次の表に、有効な状態の値を示します。</span><span class="sxs-lookup"><span data-stu-id="c5807-128">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="c5807-129">状態</span><span class="sxs-lookup"><span data-stu-id="c5807-129">State</span></span>|<span data-ttu-id="c5807-130">説明</span><span class="sxs-lookup"><span data-stu-id="c5807-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c5807-131">Aborted</span><span class="sxs-lookup"><span data-stu-id="c5807-131">Aborted</span></span>|<span data-ttu-id="c5807-132">ワークフロー インスタンスは中止されました。</span><span class="sxs-lookup"><span data-stu-id="c5807-132">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="c5807-133">完了</span><span class="sxs-lookup"><span data-stu-id="c5807-133">Completed</span></span>|<span data-ttu-id="c5807-134">ワークフロー インスタンスは完了しました。</span><span class="sxs-lookup"><span data-stu-id="c5807-134">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="c5807-135">Deleted</span><span class="sxs-lookup"><span data-stu-id="c5807-135">Deleted</span></span>|<span data-ttu-id="c5807-136">ワークフロー インスタンスは削除されました。</span><span class="sxs-lookup"><span data-stu-id="c5807-136">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="c5807-137">Idle</span><span class="sxs-lookup"><span data-stu-id="c5807-137">Idle</span></span>|<span data-ttu-id="c5807-138">ワークフロー インスタンスはアイドル状態です。</span><span class="sxs-lookup"><span data-stu-id="c5807-138">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="c5807-139">Persisted</span><span class="sxs-lookup"><span data-stu-id="c5807-139">Persisted</span></span>|<span data-ttu-id="c5807-140">ワークフロー インスタンスは永続化されました。</span><span class="sxs-lookup"><span data-stu-id="c5807-140">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="c5807-141">Resumed</span><span class="sxs-lookup"><span data-stu-id="c5807-141">Resumed</span></span>|<span data-ttu-id="c5807-142">ワークフロー インスタンスが再開されました。</span><span class="sxs-lookup"><span data-stu-id="c5807-142">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="c5807-143">開始</span><span class="sxs-lookup"><span data-stu-id="c5807-143">Started</span></span>|<span data-ttu-id="c5807-144">ワークフロー インスタンスが開始されました。</span><span class="sxs-lookup"><span data-stu-id="c5807-144">The workflow instance is started.</span></span>|  
|<span data-ttu-id="c5807-145">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="c5807-145">UnhandledException</span></span>|<span data-ttu-id="c5807-146">ワークフロー インスタンスで未処理の例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="c5807-146">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="c5807-147">アンロードされました</span><span class="sxs-lookup"><span data-stu-id="c5807-147">Unloaded</span></span>|<span data-ttu-id="c5807-148">ワークフロー インスタンスはアンロードされました。</span><span class="sxs-lookup"><span data-stu-id="c5807-148">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="c5807-149">Canceled</span><span class="sxs-lookup"><span data-stu-id="c5807-149">Canceled</span></span>|<span data-ttu-id="c5807-150">ワークフロー インスタンスは取り消されました。</span><span class="sxs-lookup"><span data-stu-id="c5807-150">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="c5807-151">Suspended</span><span class="sxs-lookup"><span data-stu-id="c5807-151">Suspended</span></span>|<span data-ttu-id="c5807-152">ワークフロー インスタンスが中断されています。</span><span class="sxs-lookup"><span data-stu-id="c5807-152">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="c5807-153">Terminated</span><span class="sxs-lookup"><span data-stu-id="c5807-153">Terminated</span></span>|<span data-ttu-id="c5807-154">ワークフロー インスタンスは終了しました。</span><span class="sxs-lookup"><span data-stu-id="c5807-154">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="c5807-155">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="c5807-155">Unsuspended</span></span>|<span data-ttu-id="c5807-156">ワークフロー インスタンスの中断が解除されました。</span><span class="sxs-lookup"><span data-stu-id="c5807-156">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c5807-157">例</span><span class="sxs-lookup"><span data-stu-id="c5807-157">Example</span></span>  
 <span data-ttu-id="c5807-158">次の構成は、このクエリを使用して、`Started` インスタンス状態のワークフロー インスタンス レベルの追跡レコードを定期受信します。</span><span class="sxs-lookup"><span data-stu-id="c5807-158">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5807-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5807-159">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c5807-160">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="c5807-160">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c5807-161">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="c5807-161">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
