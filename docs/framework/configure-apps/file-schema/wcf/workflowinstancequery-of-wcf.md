---
title: <workflowInstanceQuery>WCF の
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: eaf0cd204265aac7c1421e3de0c33963e6bbb7a1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854729"
---
# <a name="workflowinstancequery-of-wcf"></a><span data-ttu-id="3d937-102">\<workflowInstanceQuery>WCF の</span><span class="sxs-lookup"><span data-stu-id="3d937-102">\<workflowInstanceQuery> of WCF</span></span>

<span data-ttu-id="3d937-103">開始したイベントや完了したイベントなど、ワークフロー インスタンスのライフサイクルの変化を追跡するクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="3d937-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="3d937-104">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d937-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="3d937-105">構文</span><span class="sxs-lookup"><span data-stu-id="3d937-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d937-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="3d937-106">Attributes and elements</span></span>  

<span data-ttu-id="3d937-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d937-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d937-108">属性</span><span class="sxs-lookup"><span data-stu-id="3d937-108">Attributes</span></span>  

<span data-ttu-id="3d937-109">なし。</span><span class="sxs-lookup"><span data-stu-id="3d937-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3d937-110">子要素</span><span class="sxs-lookup"><span data-stu-id="3d937-110">Child elements</span></span>  
  
|<span data-ttu-id="3d937-111">要素</span><span class="sxs-lookup"><span data-stu-id="3d937-111">Element</span></span>|<span data-ttu-id="3d937-112">説明</span><span class="sxs-lookup"><span data-stu-id="3d937-112">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="3d937-113">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態のコレクション。</span><span class="sxs-lookup"><span data-stu-id="3d937-113">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3d937-114">親要素</span><span class="sxs-lookup"><span data-stu-id="3d937-114">Parent elements</span></span>  
  
|<span data-ttu-id="3d937-115">要素</span><span class="sxs-lookup"><span data-stu-id="3d937-115">Element</span></span>|<span data-ttu-id="3d937-116">説明</span><span class="sxs-lookup"><span data-stu-id="3d937-116">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQueries>](workflowinstancequeries-of-wcf.md)|<span data-ttu-id="3d937-117">開始したイベントや完了したイベントなど、ワークフロー インスタンスのライフサイクルの変化を追跡する構成要素のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="3d937-117">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d937-118">解説</span><span class="sxs-lookup"><span data-stu-id="3d937-118">Remarks</span></span>  

<span data-ttu-id="3d937-119"><xref:System.Activities.Tracking.WorkflowInstanceQuery> は、次の <xref:System.Activities.Tracking.TrackingRecord> オブジェクトの定期受信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3d937-119">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="3d937-120">例</span><span class="sxs-lookup"><span data-stu-id="3d937-120">Example</span></span>  

<span data-ttu-id="3d937-121">次の構成は、このクエリを使用して、`Started` インスタンス状態のワークフロー インスタンス レベルの追跡レコードを定期受信します。</span><span class="sxs-lookup"><span data-stu-id="3d937-121">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="3d937-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d937-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3d937-123">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="3d937-123">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3d937-124">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="3d937-124">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
