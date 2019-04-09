---
title: <workflowInstanceQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: e54f98c980f60d02377e38d53d9d0eb48581eec0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132484"
---
# <a name="workflowinstancequeries"></a><span data-ttu-id="49541-101">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="49541-101">\<workflowInstanceQueries></span></span>
<span data-ttu-id="49541-102">開始したイベントや完了したイベントなど、ワークフロー インスタンスのライフサイクルの変化を追跡する構成要素のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="49541-102">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="49541-103">追跡プロファイルのクエリの詳細については、次を参照してください[追跡プロファイル。](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="49541-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="49541-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="49541-104">\<system.serviceModel></span></span>  
<span data-ttu-id="49541-105">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="49541-105">\<tracking></span></span>  
<span data-ttu-id="49541-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="49541-106">\<trackingProfile></span></span>  
<span data-ttu-id="49541-107">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="49541-107">\<workflow></span></span>  
<span data-ttu-id="49541-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="49541-108">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49541-109">構文</span><span class="sxs-lookup"><span data-stu-id="49541-109">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49541-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="49541-110">Attributes and Elements</span></span>  
 <span data-ttu-id="49541-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="49541-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49541-112">属性</span><span class="sxs-lookup"><span data-stu-id="49541-112">Attributes</span></span>  
 <span data-ttu-id="49541-113">なし。</span><span class="sxs-lookup"><span data-stu-id="49541-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="49541-114">子要素</span><span class="sxs-lookup"><span data-stu-id="49541-114">Child Elements</span></span>  
  
|<span data-ttu-id="49541-115">要素</span><span class="sxs-lookup"><span data-stu-id="49541-115">Element</span></span>|<span data-ttu-id="49541-116">説明</span><span class="sxs-lookup"><span data-stu-id="49541-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49541-117">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="49541-117">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="49541-118">ワークフロー インスタンスのライフサイクルの変化を追跡するために使用されるクエリ。</span><span class="sxs-lookup"><span data-stu-id="49541-118">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="49541-119">親要素</span><span class="sxs-lookup"><span data-stu-id="49541-119">Parent Elements</span></span>  
  
|<span data-ttu-id="49541-120">要素</span><span class="sxs-lookup"><span data-stu-id="49541-120">Element</span></span>|<span data-ttu-id="49541-121">説明</span><span class="sxs-lookup"><span data-stu-id="49541-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49541-122">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="49541-122">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="49541-123">識別される特定のワークフローのすべてのクエリを格納する構成要素、 **activityDefinitionId**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="49541-123">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49541-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="49541-124">Remarks</span></span>  
 <span data-ttu-id="49541-125"><xref:System.Activities.Tracking.WorkflowInstanceQuery> は、次の <xref:System.Activities.Tracking.TrackingRecord> オブジェクトの定期受信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="49541-125">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="49541-126">例</span><span class="sxs-lookup"><span data-stu-id="49541-126">Example</span></span>  
 <span data-ttu-id="49541-127">次の構成は、このクエリを使用して、`Started` インスタンス状態のワークフロー インスタンス レベルの追跡レコードを定期受信します。</span><span class="sxs-lookup"><span data-stu-id="49541-127">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="49541-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="49541-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="49541-129">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="49541-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="49541-130">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="49541-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
