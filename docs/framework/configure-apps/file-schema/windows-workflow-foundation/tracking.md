---
title: <tracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
ms.openlocfilehash: 28d73bb74c4a49052589040adc26194b1300668c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397604"
---
# <a name="tracking"></a><span data-ttu-id="689af-101">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="689af-101">\<tracking></span></span>
<span data-ttu-id="689af-102">ワークフロー サービスの追跡設定を定義する構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="689af-102">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="689af-103">ワークフロー追跡とその構成の詳細については、「ワークフローの[追跡とトレース](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)」と「ワークフロー[の追跡の構成](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="689af-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
<span data-ttu-id="689af-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="689af-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="689af-105">&nbsp;&nbsp;[ **\<system.ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="689af-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="689af-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<追跡 >**</span><span class="sxs-lookup"><span data-stu-id="689af-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="689af-107">構文</span><span class="sxs-lookup"><span data-stu-id="689af-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="689af-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="689af-108">Attributes and Elements</span></span>  
 <span data-ttu-id="689af-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="689af-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="689af-110">属性</span><span class="sxs-lookup"><span data-stu-id="689af-110">Attributes</span></span>  
 <span data-ttu-id="689af-111">なし。</span><span class="sxs-lookup"><span data-stu-id="689af-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="689af-112">子要素</span><span class="sxs-lookup"><span data-stu-id="689af-112">Child Elements</span></span>  
  
|<span data-ttu-id="689af-113">要素</span><span class="sxs-lookup"><span data-stu-id="689af-113">Element</span></span>|<span data-ttu-id="689af-114">説明</span><span class="sxs-lookup"><span data-stu-id="689af-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="689af-115">\<participants></span><span class="sxs-lookup"><span data-stu-id="689af-115">\<participants></span></span>](participants.md)|<span data-ttu-id="689af-116">追跡レコードをサブスクライブする参加者を定義する構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="689af-116">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="689af-117">追跡参加要素には、追跡レコードからペイロードを処理するロジックが含まれています (たとえば、ファイルへの書き込みを選択できるなど)。</span><span class="sxs-lookup"><span data-stu-id="689af-117">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="689af-118">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="689af-118">\<trackingProfile></span></span>](trackingprofile.md)|<span data-ttu-id="689af-119">ワークフロー インスタンスで発生した追跡レコードをフィルター処理するための追跡プロファイル。</span><span class="sxs-lookup"><span data-stu-id="689af-119">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="689af-120">親要素</span><span class="sxs-lookup"><span data-stu-id="689af-120">Parent Elements</span></span>  
  
|<span data-ttu-id="689af-121">要素</span><span class="sxs-lookup"><span data-stu-id="689af-121">Element</span></span>|<span data-ttu-id="689af-122">説明</span><span class="sxs-lookup"><span data-stu-id="689af-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="689af-123">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="689af-123">system.ServiceModel</span></span>|<span data-ttu-id="689af-124">すべてのワークフロー構成要素のルート要素。</span><span class="sxs-lookup"><span data-stu-id="689af-124">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="689af-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="689af-125">Remarks</span></span>  
 <span data-ttu-id="689af-126">追跡には、ワークフローの実行を検証する機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="689af-126">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="689af-127">ワークフロー追跡インフラストラクチャはワークフローをインストルメント化し、実行中の主要イベントを反映してレコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="689af-127">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="689af-128">たとえば、ワークフロー インスタンスが開始または完了すると、追跡レコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="689af-128">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="689af-129">また、追跡によって、ワークフロー変数に関連付けられたビジネス関連データを抽出することもできます。</span><span class="sxs-lookup"><span data-stu-id="689af-129">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="689af-130">たとえば、ワークフローが注文処理システムを表している場合は、注文 ID と共に追跡レコードを抽出できます。</span><span class="sxs-lookup"><span data-stu-id="689af-130">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="689af-131">一般的に、WF 追跡機能を有効にすると、ワークフロー実行の診断またはビジネス分析が容易になります。</span><span class="sxs-lookup"><span data-stu-id="689af-131">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="689af-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="689af-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="689af-133">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="689af-133">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
