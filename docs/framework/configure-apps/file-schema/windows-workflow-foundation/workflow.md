---
title: <workflow>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560aa9b6-9cf3-460e-b798-f87d14b1d2de
ms.openlocfilehash: d6c23bb0b819b5f22367a93db0dec64787449664
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61613483"
---
# <a name="workflow"></a><span data-ttu-id="7b144-101">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="7b144-101">\<workflow></span></span>
<span data-ttu-id="7b144-102"><xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="7b144-102">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="7b144-103">ワークフロー追跡とその構成の詳細については、次を参照してください。[ワークフロー追跡とトレース](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)と[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)します。</span><span class="sxs-lookup"><span data-stu-id="7b144-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="7b144-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7b144-104">\<system.serviceModel></span></span>  
<span data-ttu-id="7b144-105">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="7b144-105">\<tracking></span></span>  
<span data-ttu-id="7b144-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="7b144-106">\<trackingProfile></span></span>  
<span data-ttu-id="7b144-107">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="7b144-107">\<workflow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b144-108">構文</span><span class="sxs-lookup"><span data-stu-id="7b144-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <participants>
        <add name="String" 
             profileName="String" 
             type="String" />
      </participants>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String" 
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String"  />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQueries>
          <bookmarkResumptionQueries>
            <bookmarkResumptionQuery name="String" />
          </bookmarkResumptionQueries>
          <cancelRequestQueries>
            <cancelRequestQuery activityName="String" 
                                childActivityName="String"/>
          </cancelRequestQueries>
          <customTrackingQueries>
            <customTrackingQuery activityName="String" 
                                 name="String"/>
          </customTrackingQueries>
          <faultPropagationQueries>
            <faultPropagationQuery activityName="String" 
                                   faultHandlerActivityName="String" />
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String" />
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b144-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7b144-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7b144-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7b144-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b144-111">属性</span><span class="sxs-lookup"><span data-stu-id="7b144-111">Attributes</span></span>  
  
|<span data-ttu-id="7b144-112">属性</span><span class="sxs-lookup"><span data-stu-id="7b144-112">Attribute</span></span>|<span data-ttu-id="7b144-113">説明</span><span class="sxs-lookup"><span data-stu-id="7b144-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7b144-114">activityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="7b144-114">activityDefinitionId</span></span>|<span data-ttu-id="7b144-115">追跡対象のワークフローのアクティビティ定義 ID を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="7b144-115">A string that specifies the activity definition ID of the workflow being tracked.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b144-116">子要素</span><span class="sxs-lookup"><span data-stu-id="7b144-116">Child Elements</span></span>  
  
|<span data-ttu-id="7b144-117">要素</span><span class="sxs-lookup"><span data-stu-id="7b144-117">Element</span></span>|<span data-ttu-id="7b144-118">説明</span><span class="sxs-lookup"><span data-stu-id="7b144-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b144-119">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="7b144-119">\<activityScheduledQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledqueries.md)|<span data-ttu-id="7b144-120">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="7b144-120">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="7b144-121">アクティビティがスケジュールされたレコードを追跡参加要素が定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="7b144-121">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>|  
|[<span data-ttu-id="7b144-122">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="7b144-122">\<activityStateQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequeries.md)|<span data-ttu-id="7b144-123">ワークフロー インスタンスを構成するアクティビティのライフサイクルの変化を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="7b144-123">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="7b144-124">たとえば、ワークフロー インスタンス内で、「電子メールの送信」アクティビティが完了するたびの追跡する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7b144-124">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="7b144-125">追跡参加要素がアクティビティ状態レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="7b144-125">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="7b144-126">定期受信可能な状態は ActivityStates で指定します。</span><span class="sxs-lookup"><span data-stu-id="7b144-126">The available states to subscribe to are specified in ActivityStates.</span></span>|  
|[<span data-ttu-id="7b144-127">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="7b144-127">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="7b144-128">ワークフロー インスタンス内のブックマークの再開を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="7b144-128">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="7b144-129">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="7b144-129">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
|[<span data-ttu-id="7b144-130">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="7b144-130">\<cancelRequestedQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedqueries.md)|<span data-ttu-id="7b144-131">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="7b144-131">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="7b144-132">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="7b144-132">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
|[<span data-ttu-id="7b144-133">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="7b144-133">\<customTrackingQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingqueries.md)|<span data-ttu-id="7b144-134">コード アクティビティで定義するイベントを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="7b144-134">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="7b144-135">追跡参加要素がカスタム追跡レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="7b144-135">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>|  
|[<span data-ttu-id="7b144-136">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="7b144-136">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="7b144-137">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="7b144-137">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="7b144-138">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="7b144-138">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="7b144-139">1 つのアクティビティ内で発生したエラーの処理は、このようなクエリを使用して追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b144-139">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="7b144-140">追跡参加要素がエラー伝達レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="7b144-140">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>|  
|[<span data-ttu-id="7b144-141">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="7b144-141">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="7b144-142">開始したイベントや完了したイベントなど、ワークフロー インスタンスのライフサイクルの変化を追跡する構成要素のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="7b144-142">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7b144-143">親要素</span><span class="sxs-lookup"><span data-stu-id="7b144-143">Parent Elements</span></span>  
  
|<span data-ttu-id="7b144-144">要素</span><span class="sxs-lookup"><span data-stu-id="7b144-144">Element</span></span>|<span data-ttu-id="7b144-145">説明</span><span class="sxs-lookup"><span data-stu-id="7b144-145">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b144-146">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="7b144-146">\<trackingProfile></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="7b144-147">ワークフロー追跡参加要素内のレコードを追跡するサブスクリプションを作成するための構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="7b144-147">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="7b144-148">追跡プロファイルには、実行時にワークフロー インスタンスの状態が変化したときに生成されるワークフロー イベントを追跡参加要素が定期受信できるようにする、追跡クエリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7b144-148">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="7b144-149">追跡プロファイル セクション内で定義されたクエリでは、サブスクリプションによって返されるイベントの種類が定義されます。</span><span class="sxs-lookup"><span data-stu-id="7b144-149">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b144-150">Remarks</span><span class="sxs-lookup"><span data-stu-id="7b144-150">Remarks</span></span>  
 <span data-ttu-id="7b144-151">追跡プロファイルには、実行時に特定のワークフロー インスタンスの状態が変化したときに生成されるワークフロー イベントを追跡参加要素が定期受信できるようにする、追跡クエリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7b144-151">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a particular workflow instance changes at runtime.</span></span> <span data-ttu-id="7b144-152">この構成要素を使用して、追跡対象のワークフロー インスタンスが識別されます。</span><span class="sxs-lookup"><span data-stu-id="7b144-152">The workflow instance being tracked is identified by this configuration element.</span></span>  
  
 <span data-ttu-id="7b144-153">監視の要件に応じて、ワークフローの主な状態変化の少数のセットを定期受信する、大まかなプロファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7b144-153">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="7b144-154">それとは反対に、結果として得られるイベントが、後で詳細な実行フローを十分に再構築できるほど豊富な、詳細なプロファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="7b144-154">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="7b144-155">追跡プロファイルは、特定の追跡レコードを対象としてワークフロー ランタイムを照会できる、追跡レコード用の宣言型のサブスクリプションとして構築されます。</span><span class="sxs-lookup"><span data-stu-id="7b144-155">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="7b144-156">これには、いくつかの追跡レコードのさまざまなクラスを定期受信できるクエリの種類があります。</span><span class="sxs-lookup"><span data-stu-id="7b144-156">There are a handful of query types that allow you subscribe to different classes of tracking records.</span></span> <span data-ttu-id="7b144-157">クエリの完全な一覧は、このトピックの子要素の一覧を参照してくださいと[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)します。</span><span class="sxs-lookup"><span data-stu-id="7b144-157">For a complete list of queries, see the child element list of this topic and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="7b144-158">次の例は、追跡参加要素をサブスクライブできるようにする構成ファイルで追跡プロファイルを示します、`Started`と`Completed`ワークフロー イベント。</span><span class="sxs-lookup"><span data-stu-id="7b144-158">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
```xml  
<system.serviceModel>  
  <tracking>    
    <trackingProfile name="Sample Tracking Profile">  
      <workflow activityDefinitionId="*">  
         <workflowInstanceQueries>  
            <workflowInstanceQuery>  
            <states>  
              <state name="Started"/>  
              <state name="Completed"/>  
            </states>  
          </workflowInstanceQuery>  
        </workflowInstanceQueries>  
      </workflow>  
    </trackingProfile>          
   </profiles>  
  </tracking>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7b144-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b144-159">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="7b144-160">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="7b144-160">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7b144-161">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="7b144-161">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
