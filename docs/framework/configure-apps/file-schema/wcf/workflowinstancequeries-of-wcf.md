---
title: <workflowInstanceQueries> WCF の
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: 89e122b87743a81a80ce63b382ae235c1c4863bc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790521"
---
# <a name="workflowinstancequeries-of-wcf"></a><span data-ttu-id="d865d-102">\<workflowInstanceQueries > の WCF</span><span class="sxs-lookup"><span data-stu-id="d865d-102">\<workflowInstanceQueries> of WCF</span></span>

<span data-ttu-id="d865d-103">開始したイベントや完了したイベントなど、ワークフロー インスタンスのライフサイクルの変化を追跡する構成要素のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="d865d-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="d865d-104">追跡プロファイルのクエリの詳細については、次を参照してください[追跡プロファイル。](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d865d-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="d865d-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d865d-105">\<system.serviceModel></span></span>  
<span data-ttu-id="d865d-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="d865d-106">\<tracking></span></span>  
<span data-ttu-id="d865d-107">\<プロファイル ></span><span class="sxs-lookup"><span data-stu-id="d865d-107">\<profiles></span></span>  
<span data-ttu-id="d865d-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d865d-108">\<trackingProfile></span></span>  
<span data-ttu-id="d865d-109">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="d865d-109">\<workflow></span></span>  
<span data-ttu-id="d865d-110">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="d865d-110">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d865d-111">構文</span><span class="sxs-lookup"><span data-stu-id="d865d-111">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
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
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d865d-112">属性と要素</span><span class="sxs-lookup"><span data-stu-id="d865d-112">Attributes and elements</span></span>

<span data-ttu-id="d865d-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d865d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d865d-114">属性</span><span class="sxs-lookup"><span data-stu-id="d865d-114">Attributes</span></span>  

<span data-ttu-id="d865d-115">なし。</span><span class="sxs-lookup"><span data-stu-id="d865d-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d865d-116">子要素</span><span class="sxs-lookup"><span data-stu-id="d865d-116">Child elements</span></span>  
  
|<span data-ttu-id="d865d-117">要素</span><span class="sxs-lookup"><span data-stu-id="d865d-117">Element</span></span>|<span data-ttu-id="d865d-118">説明</span><span class="sxs-lookup"><span data-stu-id="d865d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d865d-119">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="d865d-119">\<workflowInstanceQuery></span></span>](workflowinstancequery-of-wcf.md)|<span data-ttu-id="d865d-120">ワークフロー インスタンスのライフサイクルの変化を追跡するために使用されるクエリ。</span><span class="sxs-lookup"><span data-stu-id="d865d-120">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d865d-121">親要素</span><span class="sxs-lookup"><span data-stu-id="d865d-121">Parent elements</span></span>  
  
|<span data-ttu-id="d865d-122">要素</span><span class="sxs-lookup"><span data-stu-id="d865d-122">Element</span></span>|<span data-ttu-id="d865d-123">説明</span><span class="sxs-lookup"><span data-stu-id="d865d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d865d-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="d865d-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="d865d-125">識別される特定のワークフローのすべてのクエリを格納する構成要素、 [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId)プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d865d-125">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d865d-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="d865d-126">Remarks</span></span>

<span data-ttu-id="d865d-127"><xref:System.Activities.Tracking.WorkflowInstanceQuery> は、次の <xref:System.Activities.Tracking.TrackingRecord> オブジェクトの定期受信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d865d-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="d865d-128">例</span><span class="sxs-lookup"><span data-stu-id="d865d-128">Example</span></span>  

<span data-ttu-id="d865d-129">次の構成は、このクエリを使用して、`Started` インスタンス状態のワークフロー インスタンス レベルの追跡レコードを定期受信します。</span><span class="sxs-lookup"><span data-stu-id="d865d-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="d865d-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="d865d-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d865d-131">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="d865d-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d865d-132">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="d865d-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
