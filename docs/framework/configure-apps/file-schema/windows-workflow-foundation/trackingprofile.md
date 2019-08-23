---
title: <trackingProfile>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 154830ff-ddd3-4397-a3b5-5b334907777f
ms.openlocfilehash: 8b8cfe95a646563642e7425fdb4b5257cafa466f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947297"
---
# <a name="trackingprofile"></a><span data-ttu-id="66be6-101">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="66be6-101">\<trackingProfile></span></span>
<span data-ttu-id="66be6-102">追跡参加要素のワークフロー追跡レコードに対するサブスクリプションを作成するための構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="66be6-102">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="66be6-103">追跡プロファイルには、実行時にワークフロー インスタンスの状態が変化したときに生成されるワークフロー イベントを追跡参加要素が定期受信できるようにする、追跡クエリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="66be6-103">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="66be6-104">追跡プロファイル セクション内で定義されたクエリでは、サブスクリプションによって返されるイベントの種類が定義されます。</span><span class="sxs-lookup"><span data-stu-id="66be6-104">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="66be6-105">ワークフロー追跡とその構成の詳細については、「[ワークフローの追跡とトレース](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)」と「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66be6-105">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="66be6-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="66be6-106">\<system.serviceModel></span></span>  
<span data-ttu-id="66be6-107">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="66be6-107">\<tracking></span></span>  
<span data-ttu-id="66be6-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="66be6-108">\<trackingProfile></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66be6-109">構文</span><span class="sxs-lookup"><span data-stu-id="66be6-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66be6-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="66be6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="66be6-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="66be6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66be6-112">属性</span><span class="sxs-lookup"><span data-stu-id="66be6-112">Attributes</span></span>  
  
|<span data-ttu-id="66be6-113">属性</span><span class="sxs-lookup"><span data-stu-id="66be6-113">Attribute</span></span>|<span data-ttu-id="66be6-114">説明</span><span class="sxs-lookup"><span data-stu-id="66be6-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="66be6-115">name</span><span class="sxs-lookup"><span data-stu-id="66be6-115">name</span></span>|<span data-ttu-id="66be6-116">追跡プロファイルの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="66be6-116">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="66be6-117">子要素</span><span class="sxs-lookup"><span data-stu-id="66be6-117">Child Elements</span></span>  
  
|<span data-ttu-id="66be6-118">要素</span><span class="sxs-lookup"><span data-stu-id="66be6-118">Element</span></span>|<span data-ttu-id="66be6-119">説明</span><span class="sxs-lookup"><span data-stu-id="66be6-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66be6-120">\<participants></span><span class="sxs-lookup"><span data-stu-id="66be6-120">\<participants></span></span>](participants.md)|<span data-ttu-id="66be6-121"><xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType> プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="66be6-121">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="66be6-122">親要素</span><span class="sxs-lookup"><span data-stu-id="66be6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="66be6-123">要素</span><span class="sxs-lookup"><span data-stu-id="66be6-123">Element</span></span>|<span data-ttu-id="66be6-124">説明</span><span class="sxs-lookup"><span data-stu-id="66be6-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66be6-125">\<tracking></span><span class="sxs-lookup"><span data-stu-id="66be6-125">\<tracking></span></span>](tracking.md)|<span data-ttu-id="66be6-126">ワークフロー サービスの追跡設定を定義する構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="66be6-126">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66be6-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="66be6-127">Remarks</span></span>  
 <span data-ttu-id="66be6-128">追跡プロファイルには、実行時にワークフロー インスタンスの状態が変化したときに生成されるワークフロー イベントを追跡参加要素が定期受信できるようにする、追跡クエリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="66be6-128">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="66be6-129">監視の要件に応じて、ワークフローの主な状態変化の少数のセットを定期受信する、大まかなプロファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="66be6-129">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="66be6-130">それとは反対に、結果として得られるイベントが、後で詳細な実行フローを十分に再構築できるほど豊富な、詳細なプロファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="66be6-130">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="66be6-131">追跡プロファイルは、特定の追跡レコードを対象としてワークフロー ランタイムを照会できる、追跡レコード用の宣言型のサブスクリプションとして構築されます。</span><span class="sxs-lookup"><span data-stu-id="66be6-131">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="66be6-132">オブジェクトの<xref:System.Activities.Tracking.TrackingRecord>さまざまなクラスをサブスクライブできるクエリの種類がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="66be6-132">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="66be6-133">クエリの完全な一覧を参照してください[\<参加者 >](participants.md)と[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="66be6-133">For a complete list of queries, see [\<participants>](participants.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)..</span></span>  
  
 <span data-ttu-id="66be6-134">次の例は、追跡参加要素がワークフローイベント`Started`と`Completed`ワークフローイベントをサブスクライブできるようにする、構成ファイル内の追跡プロファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="66be6-134">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="66be6-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="66be6-135">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="66be6-136">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="66be6-136">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="66be6-137">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="66be6-137">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
