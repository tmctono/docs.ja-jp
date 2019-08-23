---
title: <cancelRequestedQueries>WCF の
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 0f04fc928358c96ca3112422f1a6ccd039269e47
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926246"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="7bbc7-102">\<WCF の cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="7bbc7-102">\<cancelRequestedQueries> of WCF</span></span>
<span data-ttu-id="7bbc7-103">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="7bbc7-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="7bbc7-104">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="7bbc7-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="7bbc7-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bbc7-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="7bbc7-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7bbc7-106">\<system.serviceModel></span></span>  
<span data-ttu-id="7bbc7-107">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="7bbc7-107">\<tracking></span></span>  
<span data-ttu-id="7bbc7-108">\<プロファイル > \<trackingprofile ></span><span class="sxs-lookup"><span data-stu-id="7bbc7-108">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="7bbc7-109">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="7bbc7-109">\<workflow></span></span>  
<span data-ttu-id="7bbc7-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="7bbc7-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bbc7-111">構文</span><span class="sxs-lookup"><span data-stu-id="7bbc7-111">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String" />
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7bbc7-112">属性と要素</span><span class="sxs-lookup"><span data-stu-id="7bbc7-112">Attributes and elements</span></span>  

<span data-ttu-id="7bbc7-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7bbc7-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7bbc7-114">属性</span><span class="sxs-lookup"><span data-stu-id="7bbc7-114">Attributes</span></span>

<span data-ttu-id="7bbc7-115">なし。</span><span class="sxs-lookup"><span data-stu-id="7bbc7-115">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="7bbc7-116">子要素</span><span class="sxs-lookup"><span data-stu-id="7bbc7-116">Child elements</span></span>
  
|<span data-ttu-id="7bbc7-117">要素</span><span class="sxs-lookup"><span data-stu-id="7bbc7-117">Element</span></span>|<span data-ttu-id="7bbc7-118">説明</span><span class="sxs-lookup"><span data-stu-id="7bbc7-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7bbc7-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="7bbc7-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="7bbc7-120">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="7bbc7-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7bbc7-121">親要素</span><span class="sxs-lookup"><span data-stu-id="7bbc7-121">Parent elements</span></span>  
  
|<span data-ttu-id="7bbc7-122">要素</span><span class="sxs-lookup"><span data-stu-id="7bbc7-122">Element</span></span>|<span data-ttu-id="7bbc7-123">説明</span><span class="sxs-lookup"><span data-stu-id="7bbc7-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7bbc7-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="7bbc7-124">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="7bbc7-125"><xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="7bbc7-125">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7bbc7-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="7bbc7-126">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="7bbc7-127">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="7bbc7-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7bbc7-128">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="7bbc7-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
