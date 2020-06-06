---
title: <tracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
ms.openlocfilehash: 968cfa8e5402458afd6f13545ed999a472adf2e0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79151911"
---
# \<tracking>
<span data-ttu-id="539e0-101">ワークフロー サービスの追跡設定を定義する構成セクションを表します。</span><span class="sxs-lookup"><span data-stu-id="539e0-101">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="539e0-102">ワークフロー追跡とその構成の詳細については、「ワークフローの[追跡とトレース](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)」と「ワークフロー[の追跡の構成](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="539e0-102">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**  
  
## <a name="syntax"></a><span data-ttu-id="539e0-103">構文</span><span class="sxs-lookup"><span data-stu-id="539e0-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="539e0-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="539e0-104">Attributes and Elements</span></span>  
 <span data-ttu-id="539e0-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="539e0-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="539e0-106">属性</span><span class="sxs-lookup"><span data-stu-id="539e0-106">Attributes</span></span>  
 <span data-ttu-id="539e0-107">なし。</span><span class="sxs-lookup"><span data-stu-id="539e0-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="539e0-108">子要素</span><span class="sxs-lookup"><span data-stu-id="539e0-108">Child Elements</span></span>  
  
|<span data-ttu-id="539e0-109">要素</span><span class="sxs-lookup"><span data-stu-id="539e0-109">Element</span></span>|<span data-ttu-id="539e0-110">説明</span><span class="sxs-lookup"><span data-stu-id="539e0-110">Description</span></span>|  
|-------------|-----------------|  
|[\<participants>](participants.md)|<span data-ttu-id="539e0-111">追跡レコードを定期受信する参加要素を定義する、構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="539e0-111">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="539e0-112">追跡参加要素には、追跡レコードからペイロードを処理するロジックが含まれています (たとえば、ファイルへの書き込みを選択できるなど)。</span><span class="sxs-lookup"><span data-stu-id="539e0-112">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[\<trackingProfile>](trackingprofile.md)|<span data-ttu-id="539e0-113">ワークフロー インスタンスで発生した追跡レコードをフィルター処理するための追跡プロファイル。</span><span class="sxs-lookup"><span data-stu-id="539e0-113">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="539e0-114">親要素</span><span class="sxs-lookup"><span data-stu-id="539e0-114">Parent Elements</span></span>  
  
|<span data-ttu-id="539e0-115">要素</span><span class="sxs-lookup"><span data-stu-id="539e0-115">Element</span></span>|<span data-ttu-id="539e0-116">説明</span><span class="sxs-lookup"><span data-stu-id="539e0-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="539e0-117">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="539e0-117">system.ServiceModel</span></span>|<span data-ttu-id="539e0-118">すべてのワークフロー構成要素のルート要素。</span><span class="sxs-lookup"><span data-stu-id="539e0-118">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="539e0-119">解説</span><span class="sxs-lookup"><span data-stu-id="539e0-119">Remarks</span></span>  
 <span data-ttu-id="539e0-120">追跡には、ワークフローの実行を検証する機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="539e0-120">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="539e0-121">ワークフロー追跡インフラストラクチャはワークフローをインストルメント化し、実行中の主要イベントを反映してレコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="539e0-121">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="539e0-122">たとえば、ワークフロー インスタンスが開始または完了すると、追跡レコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="539e0-122">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="539e0-123">また、追跡によって、ワークフロー変数に関連付けられたビジネス関連データを抽出することもできます。</span><span class="sxs-lookup"><span data-stu-id="539e0-123">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="539e0-124">たとえば、ワークフローが注文処理システムを表している場合は、注文 ID と共に追跡レコードを抽出できます。</span><span class="sxs-lookup"><span data-stu-id="539e0-124">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="539e0-125">一般的に、WF 追跡機能を有効にすると、ワークフロー実行の診断またはビジネス分析が容易になります。</span><span class="sxs-lookup"><span data-stu-id="539e0-125">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="539e0-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="539e0-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="539e0-127">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="539e0-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
