---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: 186990577ec4eedc7cae3710c455816c3162fc94
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790287"
---
# <a name="bookmarkresumptionqueries"></a><span data-ttu-id="3d682-101">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="3d682-101">\<bookmarkResumptionQueries></span></span>
<span data-ttu-id="3d682-102">ワークフロー インスタンス内のブックマークの再開を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="3d682-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="3d682-103">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="3d682-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="3d682-104">追跡プロファイルのクエリの詳細については、次を参照してください[追跡プロファイル。](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="3d682-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="3d682-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3d682-105">\<system.serviceModel></span></span>  
<span data-ttu-id="3d682-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="3d682-106">\<tracking></span></span>  
<span data-ttu-id="3d682-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="3d682-107">\<trackingProfile></span></span>  
<span data-ttu-id="3d682-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="3d682-108">\<workflow></span></span>  
<span data-ttu-id="3d682-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="3d682-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="3d682-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="3d682-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d682-111">構文</span><span class="sxs-lookup"><span data-stu-id="3d682-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d682-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3d682-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3d682-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d682-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d682-114">属性</span><span class="sxs-lookup"><span data-stu-id="3d682-114">Attributes</span></span>  
 <span data-ttu-id="3d682-115">なし。</span><span class="sxs-lookup"><span data-stu-id="3d682-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3d682-116">子要素</span><span class="sxs-lookup"><span data-stu-id="3d682-116">Child Elements</span></span>  
  
|<span data-ttu-id="3d682-117">要素</span><span class="sxs-lookup"><span data-stu-id="3d682-117">Element</span></span>|<span data-ttu-id="3d682-118">説明</span><span class="sxs-lookup"><span data-stu-id="3d682-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d682-119">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="3d682-119">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="3d682-120">ワークフロー インスタンス内のブックマークの再開を追跡するために使用されるクエリ。</span><span class="sxs-lookup"><span data-stu-id="3d682-120">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="3d682-121">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="3d682-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3d682-122">親要素</span><span class="sxs-lookup"><span data-stu-id="3d682-122">Parent Elements</span></span>  
  
|<span data-ttu-id="3d682-123">要素</span><span class="sxs-lookup"><span data-stu-id="3d682-123">Element</span></span>|<span data-ttu-id="3d682-124">説明</span><span class="sxs-lookup"><span data-stu-id="3d682-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d682-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="3d682-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="3d682-126">識別される特定のワークフローのすべてのクエリを格納する構成要素、 **activityDefinitionId**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3d682-126">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d682-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d682-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3d682-128">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="3d682-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3d682-129">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="3d682-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
