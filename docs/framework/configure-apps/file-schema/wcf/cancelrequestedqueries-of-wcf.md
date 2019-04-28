---
title: <cancelRequestedQueries> WCF の
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: a9364fc53c7eb62a240206f6c81bd434b25c3f40
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704376"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="c2b68-102">\<cancelRequestedQueries > の WCF</span><span class="sxs-lookup"><span data-stu-id="c2b68-102">\<cancelRequestedQueries> of WCF</span></span>
<span data-ttu-id="c2b68-103">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="c2b68-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="c2b68-104">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="c2b68-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="c2b68-105">追跡プロファイルのクエリの詳細については、次を参照してください[追跡プロファイル。](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="c2b68-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="c2b68-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c2b68-106">\<system.serviceModel></span></span>  
<span data-ttu-id="c2b68-107">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="c2b68-107">\<tracking></span></span>  
<span data-ttu-id="c2b68-108">\<プロファイル > \<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="c2b68-108">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="c2b68-109">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="c2b68-109">\<workflow></span></span>  
<span data-ttu-id="c2b68-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="c2b68-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2b68-111">構文</span><span class="sxs-lookup"><span data-stu-id="c2b68-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2b68-112">属性と要素</span><span class="sxs-lookup"><span data-stu-id="c2b68-112">Attributes and elements</span></span>  

<span data-ttu-id="c2b68-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2b68-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2b68-114">属性</span><span class="sxs-lookup"><span data-stu-id="c2b68-114">Attributes</span></span>

<span data-ttu-id="c2b68-115">なし。</span><span class="sxs-lookup"><span data-stu-id="c2b68-115">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="c2b68-116">子要素</span><span class="sxs-lookup"><span data-stu-id="c2b68-116">Child elements</span></span>
  
|<span data-ttu-id="c2b68-117">要素</span><span class="sxs-lookup"><span data-stu-id="c2b68-117">Element</span></span>|<span data-ttu-id="c2b68-118">説明</span><span class="sxs-lookup"><span data-stu-id="c2b68-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c2b68-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="c2b68-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="c2b68-120">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="c2b68-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c2b68-121">親要素</span><span class="sxs-lookup"><span data-stu-id="c2b68-121">Parent elements</span></span>  
  
|<span data-ttu-id="c2b68-122">要素</span><span class="sxs-lookup"><span data-stu-id="c2b68-122">Element</span></span>|<span data-ttu-id="c2b68-123">説明</span><span class="sxs-lookup"><span data-stu-id="c2b68-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c2b68-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="c2b68-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="c2b68-125"><xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="c2b68-125">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c2b68-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2b68-126">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="c2b68-127">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="c2b68-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c2b68-128">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="c2b68-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
