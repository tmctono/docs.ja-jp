---
title: <tracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
ms.openlocfilehash: fa96cb374204ffbdb4c0fcd353c70b6e27ef7481
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55263811"
---
# <a name="tracking"></a><span data-ttu-id="d2e14-101">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="d2e14-101">\<tracking></span></span>
<span data-ttu-id="d2e14-102">ワークフロー サービスの追跡設定を定義する構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="d2e14-102">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="d2e14-103">ワークフロー追跡とその構成の詳細については、[ワークフロー追跡とトレース](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)と[ワークフローの追跡を構成する](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2e14-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
<span data-ttu-id="d2e14-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d2e14-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d2e14-105">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="d2e14-105">\<tracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2e14-106">構文</span><span class="sxs-lookup"><span data-stu-id="d2e14-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2e14-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d2e14-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d2e14-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d2e14-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2e14-109">属性</span><span class="sxs-lookup"><span data-stu-id="d2e14-109">Attributes</span></span>  
 <span data-ttu-id="d2e14-110">なし。</span><span class="sxs-lookup"><span data-stu-id="d2e14-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d2e14-111">子要素</span><span class="sxs-lookup"><span data-stu-id="d2e14-111">Child Elements</span></span>  
  
|<span data-ttu-id="d2e14-112">要素</span><span class="sxs-lookup"><span data-stu-id="d2e14-112">Element</span></span>|<span data-ttu-id="d2e14-113">説明</span><span class="sxs-lookup"><span data-stu-id="d2e14-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2e14-114">\<participants></span><span class="sxs-lookup"><span data-stu-id="d2e14-114">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="d2e14-115">追跡レコードを定期受信の参加要素を定義する構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="d2e14-115">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="d2e14-116">追跡参加要素には、追跡レコードからペイロードを処理するロジックが含まれています (たとえば、ファイルへの書き込みを選択できるなど)。</span><span class="sxs-lookup"><span data-stu-id="d2e14-116">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="d2e14-117">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d2e14-117">\<trackingProfile></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="d2e14-118">ワークフロー インスタンスで発生した追跡レコードをフィルター処理するための追跡プロファイル。</span><span class="sxs-lookup"><span data-stu-id="d2e14-118">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d2e14-119">親要素</span><span class="sxs-lookup"><span data-stu-id="d2e14-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d2e14-120">要素</span><span class="sxs-lookup"><span data-stu-id="d2e14-120">Element</span></span>|<span data-ttu-id="d2e14-121">説明</span><span class="sxs-lookup"><span data-stu-id="d2e14-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d2e14-122">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d2e14-122">system.ServiceModel</span></span>|<span data-ttu-id="d2e14-123">すべてのワークフロー構成要素のルート要素。</span><span class="sxs-lookup"><span data-stu-id="d2e14-123">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2e14-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="d2e14-124">Remarks</span></span>  
 <span data-ttu-id="d2e14-125">追跡には、ワークフローの実行を検証する機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d2e14-125">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="d2e14-126">ワークフロー追跡インフラストラクチャはワークフローをインストルメント化し、実行中の主要イベントを反映してレコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="d2e14-126">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="d2e14-127">たとえば、ワークフロー インスタンスが開始または完了すると、追跡レコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d2e14-127">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="d2e14-128">また、追跡によって、ワークフロー変数に関連付けられたビジネス関連データを抽出することもできます。</span><span class="sxs-lookup"><span data-stu-id="d2e14-128">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="d2e14-129">たとえば、ワークフローが注文処理システムを表している場合は、注文 ID と共に追跡レコードを抽出できます。</span><span class="sxs-lookup"><span data-stu-id="d2e14-129">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="d2e14-130">一般的に、WF 追跡機能を有効にすると、ワークフロー実行の診断またはビジネス分析が容易になります。</span><span class="sxs-lookup"><span data-stu-id="d2e14-130">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2e14-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="d2e14-131">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="d2e14-132">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="d2e14-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
