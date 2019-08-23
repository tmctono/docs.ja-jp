---
title: <bookmarkResumptionQueries>WCF の
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 5ec9827e9862866096265da576c91b10573012d1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919734"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="2fcbb-102">\<WCF の bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="2fcbb-102">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="2fcbb-103">ワークフロー インスタンス内のブックマークの再開を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="2fcbb-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="2fcbb-104">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="2fcbb-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="2fcbb-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fcbb-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="2fcbb-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2fcbb-106">\<system.serviceModel></span></span>  
<span data-ttu-id="2fcbb-107">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="2fcbb-107">\<tracking></span></span>  
<span data-ttu-id="2fcbb-108">\<プロファイル ></span><span class="sxs-lookup"><span data-stu-id="2fcbb-108">\<profiles></span></span>  
<span data-ttu-id="2fcbb-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2fcbb-109">\<trackingProfile></span></span>  
<span data-ttu-id="2fcbb-110">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="2fcbb-110">\<workflow></span></span>  
<span data-ttu-id="2fcbb-111">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="2fcbb-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="2fcbb-112">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="2fcbb-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fcbb-113">構文</span><span class="sxs-lookup"><span data-stu-id="2fcbb-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <bookmarkResumptionQueries>
          <bookmarkResumptionQuery name="String" />
        </bookmarkResumptionQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2fcbb-114">属性と要素</span><span class="sxs-lookup"><span data-stu-id="2fcbb-114">Attributes and elements</span></span>  
  
<span data-ttu-id="2fcbb-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2fcbb-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2fcbb-116">属性</span><span class="sxs-lookup"><span data-stu-id="2fcbb-116">Attributes</span></span>  
  
<span data-ttu-id="2fcbb-117">なし。</span><span class="sxs-lookup"><span data-stu-id="2fcbb-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2fcbb-118">子要素</span><span class="sxs-lookup"><span data-stu-id="2fcbb-118">Child elements</span></span>  
  
|<span data-ttu-id="2fcbb-119">要素</span><span class="sxs-lookup"><span data-stu-id="2fcbb-119">Element</span></span>|<span data-ttu-id="2fcbb-120">説明</span><span class="sxs-lookup"><span data-stu-id="2fcbb-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2fcbb-121">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="2fcbb-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="2fcbb-122">ワークフロー インスタンス内のブックマークの再開を追跡するために使用されるクエリ。</span><span class="sxs-lookup"><span data-stu-id="2fcbb-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="2fcbb-123">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="2fcbb-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2fcbb-124">親要素</span><span class="sxs-lookup"><span data-stu-id="2fcbb-124">Parent elements</span></span>  
  
|<span data-ttu-id="2fcbb-125">要素</span><span class="sxs-lookup"><span data-stu-id="2fcbb-125">Element</span></span>|<span data-ttu-id="2fcbb-126">説明</span><span class="sxs-lookup"><span data-stu-id="2fcbb-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2fcbb-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="2fcbb-127">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="2fcbb-128">`activityDefinitionId` プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="2fcbb-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2fcbb-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="2fcbb-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2fcbb-130">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="2fcbb-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2fcbb-131">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="2fcbb-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
