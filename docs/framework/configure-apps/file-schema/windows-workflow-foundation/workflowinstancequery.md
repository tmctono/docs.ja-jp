---
title: <workflowInstanceQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
ms.openlocfilehash: f0a3c3a27b40000432b40b7008f81251fe771ca2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913140"
---
# <a name="workflowinstancequery"></a><span data-ttu-id="37cc6-101">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="37cc6-101">\<workflowInstanceQuery></span></span>
<span data-ttu-id="37cc6-102">開始したイベントや完了したイベントなど、ワークフロー インスタンスのライフサイクルの変化を追跡するクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="37cc6-102">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="37cc6-103">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37cc6-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="37cc6-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="37cc6-104">\<system.serviceModel></span></span>  
<span data-ttu-id="37cc6-105">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="37cc6-105">\<tracking></span></span>  
<span data-ttu-id="37cc6-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="37cc6-106">\<trackingProfile></span></span>  
<span data-ttu-id="37cc6-107">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="37cc6-107">\<workflow></span></span>  
<span data-ttu-id="37cc6-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="37cc6-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="37cc6-109">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="37cc6-109">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37cc6-110">構文</span><span class="sxs-lookup"><span data-stu-id="37cc6-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37cc6-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="37cc6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="37cc6-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="37cc6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37cc6-113">属性</span><span class="sxs-lookup"><span data-stu-id="37cc6-113">Attributes</span></span>  
 <span data-ttu-id="37cc6-114">なし。</span><span class="sxs-lookup"><span data-stu-id="37cc6-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="37cc6-115">子要素</span><span class="sxs-lookup"><span data-stu-id="37cc6-115">Child Elements</span></span>  
  
|<span data-ttu-id="37cc6-116">要素</span><span class="sxs-lookup"><span data-stu-id="37cc6-116">Element</span></span>|<span data-ttu-id="37cc6-117">説明</span><span class="sxs-lookup"><span data-stu-id="37cc6-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37cc6-118">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="37cc6-118">\<states></span></span>](states.md)|<span data-ttu-id="37cc6-119">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態のコレクション。</span><span class="sxs-lookup"><span data-stu-id="37cc6-119">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="37cc6-120">親要素</span><span class="sxs-lookup"><span data-stu-id="37cc6-120">Parent Elements</span></span>  
  
|<span data-ttu-id="37cc6-121">要素</span><span class="sxs-lookup"><span data-stu-id="37cc6-121">Element</span></span>|<span data-ttu-id="37cc6-122">説明</span><span class="sxs-lookup"><span data-stu-id="37cc6-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37cc6-123">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="37cc6-123">\<workflowInstanceQueries></span></span>](workflowinstancequeries.md)|<span data-ttu-id="37cc6-124">開始したイベントや完了したイベントなど、ワークフロー インスタンスのライフサイクルの変化を追跡する構成要素のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="37cc6-124">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37cc6-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="37cc6-125">Remarks</span></span>  
 <span data-ttu-id="37cc6-126"><xref:System.Activities.Tracking.WorkflowInstanceQuery> は、次の <xref:System.Activities.Tracking.TrackingRecord> オブジェクトの定期受信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="37cc6-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="37cc6-127">例</span><span class="sxs-lookup"><span data-stu-id="37cc6-127">Example</span></span>  
 <span data-ttu-id="37cc6-128">次の構成は、このクエリを使用して、`Started` インスタンス状態のワークフロー インスタンス レベルの追跡レコードを定期受信します。</span><span class="sxs-lookup"><span data-stu-id="37cc6-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="37cc6-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="37cc6-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="37cc6-130">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="37cc6-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="37cc6-131">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="37cc6-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
