---
title: <tracking>WCF の
ms.date: 03/30/2017
ms.assetid: 70cfaf24-a91c-4e56-ac47-d2ed87a963b3
ms.openlocfilehash: e8f74d635299a965b754536234e6be28e4e7a104
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399418"
---
# <a name="tracking-of-wcf"></a><span data-ttu-id="f8dd0-102">\<WCF の > の追跡</span><span class="sxs-lookup"><span data-stu-id="f8dd0-102">\<tracking> of WCF</span></span>
<span data-ttu-id="f8dd0-103">ワークフロー サービスの追跡設定を定義する構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="f8dd0-103">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="f8dd0-104">ワークフロー追跡とその構成の詳細については、「ワークフローの[追跡とトレース](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)」と「ワークフロー[の追跡の構成](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8dd0-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
<span data-ttu-id="f8dd0-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f8dd0-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f8dd0-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f8dd0-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f8dd0-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<追跡 >**</span><span class="sxs-lookup"><span data-stu-id="f8dd0-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8dd0-108">構文</span><span class="sxs-lookup"><span data-stu-id="f8dd0-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <participants>
      <add name="String"
           profileName="String"
           type="String" />
    </participants>
    <profiles>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String"
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String"/>
            </arguments>
            <states>
              <state name="String"/>
            </states>
            <variables>
              <variable name="String"/>
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
                                   faultHandlerActivityName="String"/>
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String"/>
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8dd0-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f8dd0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f8dd0-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f8dd0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8dd0-111">属性</span><span class="sxs-lookup"><span data-stu-id="f8dd0-111">Attributes</span></span>  
 <span data-ttu-id="f8dd0-112">なし。</span><span class="sxs-lookup"><span data-stu-id="f8dd0-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f8dd0-113">子要素</span><span class="sxs-lookup"><span data-stu-id="f8dd0-113">Child Elements</span></span>  
  
|<span data-ttu-id="f8dd0-114">要素</span><span class="sxs-lookup"><span data-stu-id="f8dd0-114">Element</span></span>|<span data-ttu-id="f8dd0-115">説明</span><span class="sxs-lookup"><span data-stu-id="f8dd0-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8dd0-116">\<participants></span><span class="sxs-lookup"><span data-stu-id="f8dd0-116">\<participants></span></span>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="f8dd0-117">追跡レコードをサブスクライブする参加者を定義する構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="f8dd0-117">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="f8dd0-118">追跡参加要素には、追跡レコードからペイロードを処理するロジックが含まれています (たとえば、ファイルへの書き込みを選択できるなど)。</span><span class="sxs-lookup"><span data-stu-id="f8dd0-118">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="f8dd0-119">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="f8dd0-119">\<trackingProfile></span></span>](../windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="f8dd0-120">ワークフロー インスタンスで発生した追跡レコードをフィルター処理するための追跡プロファイル。</span><span class="sxs-lookup"><span data-stu-id="f8dd0-120">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f8dd0-121">親要素</span><span class="sxs-lookup"><span data-stu-id="f8dd0-121">Parent Elements</span></span>  
  
|<span data-ttu-id="f8dd0-122">要素</span><span class="sxs-lookup"><span data-stu-id="f8dd0-122">Element</span></span>|<span data-ttu-id="f8dd0-123">説明</span><span class="sxs-lookup"><span data-stu-id="f8dd0-123">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f8dd0-124">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f8dd0-124">system.ServiceModel</span></span>|<span data-ttu-id="f8dd0-125">すべてのワークフロー構成要素のルート要素。</span><span class="sxs-lookup"><span data-stu-id="f8dd0-125">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8dd0-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="f8dd0-126">Remarks</span></span>  
 <span data-ttu-id="f8dd0-127">追跡には、ワークフローの実行を検証する機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="f8dd0-127">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="f8dd0-128">ワークフロー追跡インフラストラクチャはワークフローをインストルメント化し、実行中の主要イベントを反映してレコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="f8dd0-128">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="f8dd0-129">たとえば、ワークフロー インスタンスが開始または完了すると、追跡レコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f8dd0-129">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="f8dd0-130">また、追跡によって、ワークフロー変数に関連付けられたビジネス関連データを抽出することもできます。</span><span class="sxs-lookup"><span data-stu-id="f8dd0-130">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="f8dd0-131">たとえば、ワークフローが注文処理システムを表している場合は、注文 ID と共に追跡レコードを抽出できます。</span><span class="sxs-lookup"><span data-stu-id="f8dd0-131">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="f8dd0-132">一般的に、WF 追跡機能を有効にすると、ワークフロー実行の診断またはビジネス分析が容易になります。</span><span class="sxs-lookup"><span data-stu-id="f8dd0-132">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8dd0-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8dd0-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="f8dd0-134">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="f8dd0-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
