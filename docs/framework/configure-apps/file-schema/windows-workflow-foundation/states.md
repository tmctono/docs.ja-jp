---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: fd0b57d7d08cf77ba7792e079b7abd2ff8f2839e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947408"
---
# <a name="states"></a><span data-ttu-id="e580b-101">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="e580b-101">\<states></span></span>
<span data-ttu-id="e580b-102">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="e580b-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="e580b-103">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e580b-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="e580b-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e580b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="e580b-105">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="e580b-105">\<tracking></span></span>  
<span data-ttu-id="e580b-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="e580b-106">\<trackingProfile></span></span>  
<span data-ttu-id="e580b-107">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="e580b-107">\<workflow></span></span>  
<span data-ttu-id="e580b-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="e580b-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="e580b-109">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="e580b-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="e580b-110">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="e580b-110">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e580b-111">構文</span><span class="sxs-lookup"><span data-stu-id="e580b-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e580b-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e580b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e580b-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e580b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e580b-114">属性</span><span class="sxs-lookup"><span data-stu-id="e580b-114">Attributes</span></span>  
 <span data-ttu-id="e580b-115">なし。</span><span class="sxs-lookup"><span data-stu-id="e580b-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e580b-116">子要素</span><span class="sxs-lookup"><span data-stu-id="e580b-116">Child Elements</span></span>  
  
|<span data-ttu-id="e580b-117">要素</span><span class="sxs-lookup"><span data-stu-id="e580b-117">Element</span></span>|<span data-ttu-id="e580b-118">説明</span><span class="sxs-lookup"><span data-stu-id="e580b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e580b-119">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="e580b-119">\<state></span></span>](states.md)|<span data-ttu-id="e580b-120">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態。</span><span class="sxs-lookup"><span data-stu-id="e580b-120">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e580b-121">親要素</span><span class="sxs-lookup"><span data-stu-id="e580b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e580b-122">要素</span><span class="sxs-lookup"><span data-stu-id="e580b-122">Element</span></span>|<span data-ttu-id="e580b-123">説明</span><span class="sxs-lookup"><span data-stu-id="e580b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e580b-124">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="e580b-124">\<workflowInstanceQuery></span></span>](workflowinstancequery.md)|<span data-ttu-id="e580b-125">開始したイベントや完了したイベントなど、ワークフロー インスタンスのライフサイクルの変化を追跡するクエリ。</span><span class="sxs-lookup"><span data-stu-id="e580b-125">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e580b-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="e580b-126">Remarks</span></span>  
 <span data-ttu-id="e580b-127">返されたレコードは、このコレクションの状態でフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="e580b-127">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="e580b-128">次の表に、有効な状態の値を示します。</span><span class="sxs-lookup"><span data-stu-id="e580b-128">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="e580b-129">状態</span><span class="sxs-lookup"><span data-stu-id="e580b-129">State</span></span>|<span data-ttu-id="e580b-130">説明</span><span class="sxs-lookup"><span data-stu-id="e580b-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e580b-131">Aborted</span><span class="sxs-lookup"><span data-stu-id="e580b-131">Aborted</span></span>|<span data-ttu-id="e580b-132">ワークフロー インスタンスは中止されました。</span><span class="sxs-lookup"><span data-stu-id="e580b-132">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="e580b-133">完了</span><span class="sxs-lookup"><span data-stu-id="e580b-133">Completed</span></span>|<span data-ttu-id="e580b-134">ワークフロー インスタンスは完了しました。</span><span class="sxs-lookup"><span data-stu-id="e580b-134">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="e580b-135">Deleted</span><span class="sxs-lookup"><span data-stu-id="e580b-135">Deleted</span></span>|<span data-ttu-id="e580b-136">ワークフロー インスタンスは削除されました。</span><span class="sxs-lookup"><span data-stu-id="e580b-136">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="e580b-137">アイドル</span><span class="sxs-lookup"><span data-stu-id="e580b-137">Idle</span></span>|<span data-ttu-id="e580b-138">ワークフロー インスタンスはアイドル状態です。</span><span class="sxs-lookup"><span data-stu-id="e580b-138">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="e580b-139">Persisted</span><span class="sxs-lookup"><span data-stu-id="e580b-139">Persisted</span></span>|<span data-ttu-id="e580b-140">ワークフロー インスタンスは永続化されました。</span><span class="sxs-lookup"><span data-stu-id="e580b-140">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="e580b-141">Resumed</span><span class="sxs-lookup"><span data-stu-id="e580b-141">Resumed</span></span>|<span data-ttu-id="e580b-142">ワークフロー インスタンスが再開されました。</span><span class="sxs-lookup"><span data-stu-id="e580b-142">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="e580b-143">Started</span><span class="sxs-lookup"><span data-stu-id="e580b-143">Started</span></span>|<span data-ttu-id="e580b-144">ワークフロー インスタンスが開始されました。</span><span class="sxs-lookup"><span data-stu-id="e580b-144">The workflow instance is started.</span></span>|  
|<span data-ttu-id="e580b-145">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="e580b-145">UnhandledException</span></span>|<span data-ttu-id="e580b-146">ワークフロー インスタンスで未処理の例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="e580b-146">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="e580b-147">アンロードされました</span><span class="sxs-lookup"><span data-stu-id="e580b-147">Unloaded</span></span>|<span data-ttu-id="e580b-148">ワークフロー インスタンスはアンロードされました。</span><span class="sxs-lookup"><span data-stu-id="e580b-148">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="e580b-149">Canceled</span><span class="sxs-lookup"><span data-stu-id="e580b-149">Canceled</span></span>|<span data-ttu-id="e580b-150">ワークフロー インスタンスは取り消されました。</span><span class="sxs-lookup"><span data-stu-id="e580b-150">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="e580b-151">中断</span><span class="sxs-lookup"><span data-stu-id="e580b-151">Suspended</span></span>|<span data-ttu-id="e580b-152">ワークフロー インスタンスが中断されています。</span><span class="sxs-lookup"><span data-stu-id="e580b-152">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="e580b-153">Terminated</span><span class="sxs-lookup"><span data-stu-id="e580b-153">Terminated</span></span>|<span data-ttu-id="e580b-154">ワークフロー インスタンスは終了しました。</span><span class="sxs-lookup"><span data-stu-id="e580b-154">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="e580b-155">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="e580b-155">Unsuspended</span></span>|<span data-ttu-id="e580b-156">ワークフロー インスタンスの中断が解除されました。</span><span class="sxs-lookup"><span data-stu-id="e580b-156">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e580b-157">例</span><span class="sxs-lookup"><span data-stu-id="e580b-157">Example</span></span>  
 <span data-ttu-id="e580b-158">次の構成は、このクエリを使用して、`Started` インスタンス状態のワークフロー インスタンス レベルの追跡レコードを定期受信します。</span><span class="sxs-lookup"><span data-stu-id="e580b-158">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e580b-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="e580b-159">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e580b-160">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="e580b-160">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e580b-161">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="e580b-161">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
