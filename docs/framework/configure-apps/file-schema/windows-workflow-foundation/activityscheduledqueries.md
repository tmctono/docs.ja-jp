---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 89de9ef10449fbae78a8c5b558101a2cf6477b07
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945535"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="f96b6-101">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="f96b6-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="f96b6-102">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="f96b6-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="f96b6-103">アクティビティがスケジュールされたレコードを追跡参加要素が定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="f96b6-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="f96b6-104">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f96b6-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="f96b6-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f96b6-105">\<system.serviceModel></span></span>  
<span data-ttu-id="f96b6-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="f96b6-106">\<tracking></span></span>  
<span data-ttu-id="f96b6-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="f96b6-107">\<trackingProfile></span></span>  
<span data-ttu-id="f96b6-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="f96b6-108">\<workflow></span></span>  
<span data-ttu-id="f96b6-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="f96b6-109">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f96b6-110">構文</span><span class="sxs-lookup"><span data-stu-id="f96b6-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f96b6-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f96b6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f96b6-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f96b6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f96b6-113">属性</span><span class="sxs-lookup"><span data-stu-id="f96b6-113">Attributes</span></span>  
 <span data-ttu-id="f96b6-114">なし。</span><span class="sxs-lookup"><span data-stu-id="f96b6-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f96b6-115">子要素</span><span class="sxs-lookup"><span data-stu-id="f96b6-115">Child Elements</span></span>  
  
|<span data-ttu-id="f96b6-116">要素</span><span class="sxs-lookup"><span data-stu-id="f96b6-116">Element</span></span>|<span data-ttu-id="f96b6-117">説明</span><span class="sxs-lookup"><span data-stu-id="f96b6-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f96b6-118">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="f96b6-118">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="f96b6-119">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="f96b6-119">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f96b6-120">親要素</span><span class="sxs-lookup"><span data-stu-id="f96b6-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f96b6-121">要素</span><span class="sxs-lookup"><span data-stu-id="f96b6-121">Element</span></span>|<span data-ttu-id="f96b6-122">説明</span><span class="sxs-lookup"><span data-stu-id="f96b6-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f96b6-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="f96b6-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="f96b6-124">**ActivityDefinitionId**プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="f96b6-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f96b6-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="f96b6-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f96b6-126">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="f96b6-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f96b6-127">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="f96b6-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
