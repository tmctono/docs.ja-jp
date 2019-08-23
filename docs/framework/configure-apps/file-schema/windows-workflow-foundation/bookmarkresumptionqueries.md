---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: f048612673a9b6b69c3cdded6526c76359c444e9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945989"
---
# <a name="bookmarkresumptionqueries"></a><span data-ttu-id="ed83f-101">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="ed83f-101">\<bookmarkResumptionQueries></span></span>
<span data-ttu-id="ed83f-102">ワークフロー インスタンス内のブックマークの再開を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="ed83f-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="ed83f-103">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="ed83f-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="ed83f-104">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed83f-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="ed83f-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ed83f-105">\<system.serviceModel></span></span>  
<span data-ttu-id="ed83f-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="ed83f-106">\<tracking></span></span>  
<span data-ttu-id="ed83f-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ed83f-107">\<trackingProfile></span></span>  
<span data-ttu-id="ed83f-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="ed83f-108">\<workflow></span></span>  
<span data-ttu-id="ed83f-109">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="ed83f-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="ed83f-110">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="ed83f-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed83f-111">構文</span><span class="sxs-lookup"><span data-stu-id="ed83f-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <bookmarkResumptionQueries>
        <bookmarkResumptionQuery name="String" />
      </bookmarkResumptionQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed83f-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ed83f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ed83f-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ed83f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed83f-114">属性</span><span class="sxs-lookup"><span data-stu-id="ed83f-114">Attributes</span></span>  
 <span data-ttu-id="ed83f-115">なし。</span><span class="sxs-lookup"><span data-stu-id="ed83f-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ed83f-116">子要素</span><span class="sxs-lookup"><span data-stu-id="ed83f-116">Child Elements</span></span>  
  
|<span data-ttu-id="ed83f-117">要素</span><span class="sxs-lookup"><span data-stu-id="ed83f-117">Element</span></span>|<span data-ttu-id="ed83f-118">説明</span><span class="sxs-lookup"><span data-stu-id="ed83f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed83f-119">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="ed83f-119">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery.md)|<span data-ttu-id="ed83f-120">ワークフロー インスタンス内のブックマークの再開を追跡するために使用されるクエリ。</span><span class="sxs-lookup"><span data-stu-id="ed83f-120">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="ed83f-121">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="ed83f-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ed83f-122">親要素</span><span class="sxs-lookup"><span data-stu-id="ed83f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ed83f-123">要素</span><span class="sxs-lookup"><span data-stu-id="ed83f-123">Element</span></span>|<span data-ttu-id="ed83f-124">説明</span><span class="sxs-lookup"><span data-stu-id="ed83f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed83f-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ed83f-125">\<workflow></span></span>](workflow.md)|<span data-ttu-id="ed83f-126">**ActivityDefinitionId**プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="ed83f-126">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ed83f-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed83f-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ed83f-128">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="ed83f-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ed83f-129">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="ed83f-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
