---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 7217fb886cc96e1ad19f96e2c6542277cfc7979e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175761"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="9126b-101">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="9126b-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="9126b-102">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="9126b-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="9126b-103">アクティビティがスケジュールされたレコードを追跡参加要素が定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="9126b-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="9126b-104">追跡プロファイルのクエリの詳細については、次を参照してください[追跡プロファイル。](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="9126b-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="9126b-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9126b-105">\<system.serviceModel></span></span>  
<span data-ttu-id="9126b-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="9126b-106">\<tracking></span></span>  
<span data-ttu-id="9126b-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="9126b-107">\<trackingProfile></span></span>  
<span data-ttu-id="9126b-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="9126b-108">\<workflow></span></span>  
<span data-ttu-id="9126b-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="9126b-109">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9126b-110">構文</span><span class="sxs-lookup"><span data-stu-id="9126b-110">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String" />
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9126b-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9126b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9126b-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9126b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9126b-113">属性</span><span class="sxs-lookup"><span data-stu-id="9126b-113">Attributes</span></span>  
 <span data-ttu-id="9126b-114">なし。</span><span class="sxs-lookup"><span data-stu-id="9126b-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9126b-115">子要素</span><span class="sxs-lookup"><span data-stu-id="9126b-115">Child Elements</span></span>  
  
|<span data-ttu-id="9126b-116">要素</span><span class="sxs-lookup"><span data-stu-id="9126b-116">Element</span></span>|<span data-ttu-id="9126b-117">説明</span><span class="sxs-lookup"><span data-stu-id="9126b-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9126b-118">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="9126b-118">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="9126b-119">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="9126b-119">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9126b-120">親要素</span><span class="sxs-lookup"><span data-stu-id="9126b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9126b-121">要素</span><span class="sxs-lookup"><span data-stu-id="9126b-121">Element</span></span>|<span data-ttu-id="9126b-122">説明</span><span class="sxs-lookup"><span data-stu-id="9126b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9126b-123">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="9126b-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="9126b-124">識別される特定のワークフローのすべてのクエリを格納する構成要素、 **activityDefinitionId**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="9126b-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9126b-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="9126b-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9126b-126">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="9126b-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9126b-127">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="9126b-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
