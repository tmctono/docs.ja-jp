---
title: <workflowInstanceQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
ms.openlocfilehash: 68e44584858e55c136bc3c3dc5f1fb333485fa17
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397511"
---
# <a name="workflowinstancequery"></a><span data-ttu-id="57ef8-101">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="57ef8-101">\<workflowInstanceQuery></span></span>
<span data-ttu-id="57ef8-102">開始したイベントや完了したイベントなど、ワークフロー インスタンスのライフサイクルの変化を追跡するクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="57ef8-102">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="57ef8-103">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57ef8-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="57ef8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="57ef8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="57ef8-105">&nbsp;&nbsp;[ **\<system.ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="57ef8-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="57ef8-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="57ef8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="57ef8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="57ef8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="57ef8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="57ef8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="57ef8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowInstanceQueries >** ](workflowinstancequeries.md)</span><span class="sxs-lookup"><span data-stu-id="57ef8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)</span></span>\
<span data-ttu-id="57ef8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<workflowInstanceQuery >**</span><span class="sxs-lookup"><span data-stu-id="57ef8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57ef8-111">構文</span><span class="sxs-lookup"><span data-stu-id="57ef8-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57ef8-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="57ef8-112">Attributes and Elements</span></span>  
 <span data-ttu-id="57ef8-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="57ef8-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57ef8-114">属性</span><span class="sxs-lookup"><span data-stu-id="57ef8-114">Attributes</span></span>  
 <span data-ttu-id="57ef8-115">なし。</span><span class="sxs-lookup"><span data-stu-id="57ef8-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="57ef8-116">子要素</span><span class="sxs-lookup"><span data-stu-id="57ef8-116">Child Elements</span></span>  
  
|<span data-ttu-id="57ef8-117">要素</span><span class="sxs-lookup"><span data-stu-id="57ef8-117">Element</span></span>|<span data-ttu-id="57ef8-118">説明</span><span class="sxs-lookup"><span data-stu-id="57ef8-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="57ef8-119">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="57ef8-119">\<states></span></span>](states.md)|<span data-ttu-id="57ef8-120">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態のコレクション。</span><span class="sxs-lookup"><span data-stu-id="57ef8-120">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="57ef8-121">親要素</span><span class="sxs-lookup"><span data-stu-id="57ef8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="57ef8-122">要素</span><span class="sxs-lookup"><span data-stu-id="57ef8-122">Element</span></span>|<span data-ttu-id="57ef8-123">説明</span><span class="sxs-lookup"><span data-stu-id="57ef8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="57ef8-124">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="57ef8-124">\<workflowInstanceQueries></span></span>](workflowinstancequeries.md)|<span data-ttu-id="57ef8-125">開始したイベントや完了したイベントなど、ワークフロー インスタンスのライフサイクルの変化を追跡する構成要素のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="57ef8-125">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57ef8-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="57ef8-126">Remarks</span></span>  
 <span data-ttu-id="57ef8-127"><xref:System.Activities.Tracking.WorkflowInstanceQuery> は、次の <xref:System.Activities.Tracking.TrackingRecord> オブジェクトの定期受信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="57ef8-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="57ef8-128">例</span><span class="sxs-lookup"><span data-stu-id="57ef8-128">Example</span></span>  
 <span data-ttu-id="57ef8-129">次の構成は、このクエリを使用して、`Started` インスタンス状態のワークフロー インスタンス レベルの追跡レコードを定期受信します。</span><span class="sxs-lookup"><span data-stu-id="57ef8-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="57ef8-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="57ef8-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="57ef8-131">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="57ef8-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="57ef8-132">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="57ef8-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
