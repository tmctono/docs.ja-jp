---
title: <trackingProfile>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 154830ff-ddd3-4397-a3b5-5b334907777f
ms.openlocfilehash: 747660df58604dd9384abefccb51ea665f97e2e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61614974"
---
# <a name="trackingprofile"></a><span data-ttu-id="31123-101">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="31123-101">\<trackingProfile></span></span>
<span data-ttu-id="31123-102">ワークフロー追跡参加要素内のレコードを追跡するサブスクリプションを作成するための構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="31123-102">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="31123-103">追跡プロファイルには、実行時にワークフロー インスタンスの状態が変化したときに生成されるワークフロー イベントを追跡参加要素が定期受信できるようにする、追跡クエリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="31123-103">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="31123-104">追跡プロファイル セクション内で定義されたクエリでは、サブスクリプションによって返されるイベントの種類が定義されます。</span><span class="sxs-lookup"><span data-stu-id="31123-104">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="31123-105">ワークフロー追跡とその構成の詳細については、次を参照してください。[ワークフロー追跡とトレース](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)と[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)します。</span><span class="sxs-lookup"><span data-stu-id="31123-105">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="31123-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="31123-106">\<system.serviceModel></span></span>  
<span data-ttu-id="31123-107">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="31123-107">\<tracking></span></span>  
<span data-ttu-id="31123-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="31123-108">\<trackingProfile></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31123-109">構文</span><span class="sxs-lookup"><span data-stu-id="31123-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31123-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="31123-110">Attributes and Elements</span></span>  
 <span data-ttu-id="31123-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="31123-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31123-112">属性</span><span class="sxs-lookup"><span data-stu-id="31123-112">Attributes</span></span>  
  
|<span data-ttu-id="31123-113">属性</span><span class="sxs-lookup"><span data-stu-id="31123-113">Attribute</span></span>|<span data-ttu-id="31123-114">説明</span><span class="sxs-lookup"><span data-stu-id="31123-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="31123-115">name</span><span class="sxs-lookup"><span data-stu-id="31123-115">name</span></span>|<span data-ttu-id="31123-116">追跡プロファイルの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="31123-116">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="31123-117">子要素</span><span class="sxs-lookup"><span data-stu-id="31123-117">Child Elements</span></span>  
  
|<span data-ttu-id="31123-118">要素</span><span class="sxs-lookup"><span data-stu-id="31123-118">Element</span></span>|<span data-ttu-id="31123-119">説明</span><span class="sxs-lookup"><span data-stu-id="31123-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31123-120">\<participants></span><span class="sxs-lookup"><span data-stu-id="31123-120">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="31123-121"><xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType> プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="31123-121">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="31123-122">親要素</span><span class="sxs-lookup"><span data-stu-id="31123-122">Parent Elements</span></span>  
  
|<span data-ttu-id="31123-123">要素</span><span class="sxs-lookup"><span data-stu-id="31123-123">Element</span></span>|<span data-ttu-id="31123-124">説明</span><span class="sxs-lookup"><span data-stu-id="31123-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31123-125">\<tracking></span><span class="sxs-lookup"><span data-stu-id="31123-125">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="31123-126">ワークフロー サービスの追跡設定を定義する構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="31123-126">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31123-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="31123-127">Remarks</span></span>  
 <span data-ttu-id="31123-128">追跡プロファイルには、実行時にワークフロー インスタンスの状態が変化したときに生成されるワークフロー イベントを追跡参加要素が定期受信できるようにする、追跡クエリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="31123-128">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="31123-129">監視の要件に応じて、ワークフローの主な状態変化の少数のセットを定期受信する、大まかなプロファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="31123-129">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="31123-130">それとは反対に、結果として得られるイベントが、後で詳細な実行フローを十分に再構築できるほど豊富な、詳細なプロファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="31123-130">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="31123-131">追跡プロファイルは、特定の追跡レコードを対象としてワークフロー ランタイムを照会できる、追跡レコード用の宣言型のサブスクリプションとして構築されます。</span><span class="sxs-lookup"><span data-stu-id="31123-131">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="31123-132">いくつかのクエリの種類のさまざまなクラスを定期受信できる<xref:System.Activities.Tracking.TrackingRecord>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="31123-132">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="31123-133">クエリの完全な一覧を参照してください[\<参加者 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)と[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="31123-133">For a complete list of queries, see [\<participants>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)..</span></span>  
  
 <span data-ttu-id="31123-134">次の例は、追跡参加要素をサブスクライブできるようにする構成ファイルで追跡プロファイルを示します、`Started`と`Completed`ワークフロー イベント。</span><span class="sxs-lookup"><span data-stu-id="31123-134">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="31123-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="31123-135">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="31123-136">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="31123-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="31123-137">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="31123-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
