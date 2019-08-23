---
title: <workflow>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560aa9b6-9cf3-460e-b798-f87d14b1d2de
ms.openlocfilehash: 89f9d0e7c57f6e66b9fdffd148d9dcae5a189fba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947233"
---
# <a name="workflow"></a><span data-ttu-id="78974-101">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="78974-101">\<workflow></span></span>
<span data-ttu-id="78974-102"><xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="78974-102">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="78974-103">ワークフロー追跡とその構成の詳細については、「[ワークフローの追跡とトレース](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)」と「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78974-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="78974-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="78974-104">\<system.serviceModel></span></span>  
<span data-ttu-id="78974-105">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="78974-105">\<tracking></span></span>  
<span data-ttu-id="78974-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="78974-106">\<trackingProfile></span></span>  
<span data-ttu-id="78974-107">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="78974-107">\<workflow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78974-108">構文</span><span class="sxs-lookup"><span data-stu-id="78974-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78974-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="78974-109">Attributes and Elements</span></span>  
 <span data-ttu-id="78974-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="78974-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78974-111">属性</span><span class="sxs-lookup"><span data-stu-id="78974-111">Attributes</span></span>  
  
|<span data-ttu-id="78974-112">属性</span><span class="sxs-lookup"><span data-stu-id="78974-112">Attribute</span></span>|<span data-ttu-id="78974-113">説明</span><span class="sxs-lookup"><span data-stu-id="78974-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78974-114">activityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="78974-114">activityDefinitionId</span></span>|<span data-ttu-id="78974-115">追跡対象のワークフローのアクティビティ定義 ID を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="78974-115">A string that specifies the activity definition ID of the workflow being tracked.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78974-116">子要素</span><span class="sxs-lookup"><span data-stu-id="78974-116">Child Elements</span></span>  
  
|<span data-ttu-id="78974-117">要素</span><span class="sxs-lookup"><span data-stu-id="78974-117">Element</span></span>|<span data-ttu-id="78974-118">説明</span><span class="sxs-lookup"><span data-stu-id="78974-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78974-119">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="78974-119">\<activityScheduledQueries></span></span>](activityscheduledqueries.md)|<span data-ttu-id="78974-120">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="78974-120">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="78974-121">アクティビティがスケジュールされたレコードを追跡参加要素が定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="78974-121">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>|  
|[<span data-ttu-id="78974-122">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="78974-122">\<activityStateQueries></span></span>](activitystatequeries.md)|<span data-ttu-id="78974-123">ワークフロー インスタンスを構成するアクティビティのライフサイクルの変化を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="78974-123">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="78974-124">たとえば、ワークフローインスタンス内で "電子メールの送信" アクティビティが完了するたびに追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="78974-124">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="78974-125">追跡参加要素がアクティビティ状態レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="78974-125">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="78974-126">定期受信可能な状態は ActivityStates で指定します。</span><span class="sxs-lookup"><span data-stu-id="78974-126">The available states to subscribe to are specified in ActivityStates.</span></span>|  
|[<span data-ttu-id="78974-127">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="78974-127">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries.md)|<span data-ttu-id="78974-128">ワークフロー インスタンス内のブックマークの再開を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="78974-128">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="78974-129">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="78974-129">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
|[<span data-ttu-id="78974-130">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="78974-130">\<cancelRequestedQueries></span></span>](cancelrequestedqueries.md)|<span data-ttu-id="78974-131">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="78974-131">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="78974-132">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="78974-132">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
|[<span data-ttu-id="78974-133">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="78974-133">\<customTrackingQueries></span></span>](customtrackingqueries.md)|<span data-ttu-id="78974-134">コード アクティビティで定義するイベントを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="78974-134">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="78974-135">追跡参加要素がカスタム追跡レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="78974-135">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>|  
|[<span data-ttu-id="78974-136">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="78974-136">\<faultPropagationQueries></span></span>](faultpropagationqueries.md)|<span data-ttu-id="78974-137">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="78974-137">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="78974-138">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="78974-138">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="78974-139">1 つのアクティビティ内で発生したエラーの処理は、このようなクエリを使用して追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78974-139">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="78974-140">追跡参加要素がエラー伝達レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="78974-140">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>|  
|[<span data-ttu-id="78974-141">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="78974-141">\<workflowInstanceQueries></span></span>](workflowinstancequeries.md)|<span data-ttu-id="78974-142">開始したイベントや完了したイベントなど、ワークフロー インスタンスのライフサイクルの変化を追跡する構成要素のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="78974-142">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="78974-143">親要素</span><span class="sxs-lookup"><span data-stu-id="78974-143">Parent Elements</span></span>  
  
|<span data-ttu-id="78974-144">要素</span><span class="sxs-lookup"><span data-stu-id="78974-144">Element</span></span>|<span data-ttu-id="78974-145">説明</span><span class="sxs-lookup"><span data-stu-id="78974-145">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78974-146">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="78974-146">\<trackingProfile></span></span>](trackingprofile.md)|<span data-ttu-id="78974-147">追跡参加要素のワークフロー追跡レコードに対するサブスクリプションを作成するための構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="78974-147">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="78974-148">追跡プロファイルには、実行時にワークフロー インスタンスの状態が変化したときに生成されるワークフロー イベントを追跡参加要素が定期受信できるようにする、追跡クエリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="78974-148">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="78974-149">追跡プロファイル セクション内で定義されたクエリでは、サブスクリプションによって返されるイベントの種類が定義されます。</span><span class="sxs-lookup"><span data-stu-id="78974-149">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78974-150">Remarks</span><span class="sxs-lookup"><span data-stu-id="78974-150">Remarks</span></span>  
 <span data-ttu-id="78974-151">追跡プロファイルには、実行時に特定のワークフロー インスタンスの状態が変化したときに生成されるワークフロー イベントを追跡参加要素が定期受信できるようにする、追跡クエリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="78974-151">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a particular workflow instance changes at runtime.</span></span> <span data-ttu-id="78974-152">この構成要素を使用して、追跡対象のワークフロー インスタンスが識別されます。</span><span class="sxs-lookup"><span data-stu-id="78974-152">The workflow instance being tracked is identified by this configuration element.</span></span>  
  
 <span data-ttu-id="78974-153">監視の要件に応じて、ワークフローの主な状態変化の少数のセットを定期受信する、大まかなプロファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="78974-153">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="78974-154">それとは反対に、結果として得られるイベントが、後で詳細な実行フローを十分に再構築できるほど豊富な、詳細なプロファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="78974-154">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="78974-155">追跡プロファイルは、特定の追跡レコードを対象としてワークフロー ランタイムを照会できる、追跡レコード用の宣言型のサブスクリプションとして構築されます。</span><span class="sxs-lookup"><span data-stu-id="78974-155">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="78974-156">さまざまな種類のクエリを使用して、さまざまなクラスの追跡レコードをサブスクライブすることができます。</span><span class="sxs-lookup"><span data-stu-id="78974-156">There are a handful of query types that allow you subscribe to different classes of tracking records.</span></span> <span data-ttu-id="78974-157">クエリの完全な一覧については、このトピックの子要素の一覧と[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78974-157">For a complete list of queries, see the child element list of this topic and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="78974-158">次の例は、追跡参加要素がワークフローイベント`Started`と`Completed`ワークフローイベントをサブスクライブできるようにする、構成ファイル内の追跡プロファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="78974-158">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="78974-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="78974-159">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="78974-160">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="78974-160">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="78974-161">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="78974-161">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
