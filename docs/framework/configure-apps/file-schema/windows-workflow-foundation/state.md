---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 6f1a9474f3f12005df364a6fb84dc63aa1b68e04
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796163"
---
# <a name="state"></a><span data-ttu-id="09352-101">\<state></span><span class="sxs-lookup"><span data-stu-id="09352-101">\<state></span></span>
<span data-ttu-id="09352-102">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="09352-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="09352-103">追跡プロファイルのクエリの詳細については、次を参照してください[追跡プロファイル。](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="09352-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="09352-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="09352-104">\<system.serviceModel></span></span>  
<span data-ttu-id="09352-105">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="09352-105">\<tracking></span></span>  
<span data-ttu-id="09352-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="09352-106">\<trackingProfile></span></span>  
<span data-ttu-id="09352-107">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="09352-107">\<workflow></span></span>  
<span data-ttu-id="09352-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="09352-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="09352-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="09352-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="09352-110">\<states></span><span class="sxs-lookup"><span data-stu-id="09352-110">\<states></span></span>  
<span data-ttu-id="09352-111">\<state></span><span class="sxs-lookup"><span data-stu-id="09352-111">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09352-112">構文</span><span class="sxs-lookup"><span data-stu-id="09352-112">Syntax</span></span>  
  
```xml  
<tracking>
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
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09352-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="09352-113">Attributes and Elements</span></span>  
 <span data-ttu-id="09352-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="09352-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09352-115">属性</span><span class="sxs-lookup"><span data-stu-id="09352-115">Attributes</span></span>  
  
|<span data-ttu-id="09352-116">属性</span><span class="sxs-lookup"><span data-stu-id="09352-116">Attribute</span></span>|<span data-ttu-id="09352-117">説明</span><span class="sxs-lookup"><span data-stu-id="09352-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="09352-118">name</span><span class="sxs-lookup"><span data-stu-id="09352-118">name</span></span>|<span data-ttu-id="09352-119">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="09352-119">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="09352-120">子要素</span><span class="sxs-lookup"><span data-stu-id="09352-120">Child Elements</span></span>  
 <span data-ttu-id="09352-121">なし。</span><span class="sxs-lookup"><span data-stu-id="09352-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="09352-122">親要素</span><span class="sxs-lookup"><span data-stu-id="09352-122">Parent Elements</span></span>  
  
|<span data-ttu-id="09352-123">要素</span><span class="sxs-lookup"><span data-stu-id="09352-123">Element</span></span>|<span data-ttu-id="09352-124">説明</span><span class="sxs-lookup"><span data-stu-id="09352-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09352-125">\<states></span><span class="sxs-lookup"><span data-stu-id="09352-125">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="09352-126">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態のコレクション。</span><span class="sxs-lookup"><span data-stu-id="09352-126">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09352-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="09352-127">Remarks</span></span>  
 <span data-ttu-id="09352-128">返されたレコードは、このコレクションの状態でフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="09352-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="09352-129">次の表に、有効な状態の値を示します。</span><span class="sxs-lookup"><span data-stu-id="09352-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="09352-130">状態</span><span class="sxs-lookup"><span data-stu-id="09352-130">State</span></span>|<span data-ttu-id="09352-131">説明</span><span class="sxs-lookup"><span data-stu-id="09352-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="09352-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="09352-132">Aborted</span></span>|<span data-ttu-id="09352-133">ワークフロー インスタンスは中止されました。</span><span class="sxs-lookup"><span data-stu-id="09352-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="09352-134">完了</span><span class="sxs-lookup"><span data-stu-id="09352-134">Completed</span></span>|<span data-ttu-id="09352-135">ワークフロー インスタンスは完了しました。</span><span class="sxs-lookup"><span data-stu-id="09352-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="09352-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="09352-136">Deleted</span></span>|<span data-ttu-id="09352-137">ワークフロー インスタンスは削除されました。</span><span class="sxs-lookup"><span data-stu-id="09352-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="09352-138">Idle</span><span class="sxs-lookup"><span data-stu-id="09352-138">Idle</span></span>|<span data-ttu-id="09352-139">ワークフロー インスタンスはアイドル状態です。</span><span class="sxs-lookup"><span data-stu-id="09352-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="09352-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="09352-140">Persisted</span></span>|<span data-ttu-id="09352-141">ワークフロー インスタンスは永続化されました。</span><span class="sxs-lookup"><span data-stu-id="09352-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="09352-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="09352-142">Resumed</span></span>|<span data-ttu-id="09352-143">ワークフロー インスタンスが再開されました。</span><span class="sxs-lookup"><span data-stu-id="09352-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="09352-144">開始</span><span class="sxs-lookup"><span data-stu-id="09352-144">Started</span></span>|<span data-ttu-id="09352-145">ワークフロー インスタンスが開始されました。</span><span class="sxs-lookup"><span data-stu-id="09352-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="09352-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="09352-146">UnhandledException</span></span>|<span data-ttu-id="09352-147">ワークフロー インスタンスで未処理の例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="09352-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="09352-148">アンロードされました</span><span class="sxs-lookup"><span data-stu-id="09352-148">Unloaded</span></span>|<span data-ttu-id="09352-149">ワークフロー インスタンスはアンロードされました。</span><span class="sxs-lookup"><span data-stu-id="09352-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="09352-150">Canceled</span><span class="sxs-lookup"><span data-stu-id="09352-150">Canceled</span></span>|<span data-ttu-id="09352-151">ワークフロー インスタンスは取り消されました。</span><span class="sxs-lookup"><span data-stu-id="09352-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="09352-152">Suspended</span><span class="sxs-lookup"><span data-stu-id="09352-152">Suspended</span></span>|<span data-ttu-id="09352-153">ワークフロー インスタンスが中断されています。</span><span class="sxs-lookup"><span data-stu-id="09352-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="09352-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="09352-154">Terminated</span></span>|<span data-ttu-id="09352-155">ワークフロー インスタンスは終了しました。</span><span class="sxs-lookup"><span data-stu-id="09352-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="09352-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="09352-156">Unsuspended</span></span>|<span data-ttu-id="09352-157">ワークフロー インスタンスの中断が解除されました。</span><span class="sxs-lookup"><span data-stu-id="09352-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="09352-158">例</span><span class="sxs-lookup"><span data-stu-id="09352-158">Example</span></span>  
 <span data-ttu-id="09352-159">次の構成は、このクエリを使用して、`Started` インスタンス状態のワークフロー インスタンス レベルの追跡レコードを定期受信します。</span><span class="sxs-lookup"><span data-stu-id="09352-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="09352-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="09352-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="09352-161">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="09352-161">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="09352-162">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="09352-162">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
