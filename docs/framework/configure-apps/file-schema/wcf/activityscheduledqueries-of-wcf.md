---
title: <activityScheduledQueries> WCF の
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 1c9c292080016d7a2d0014ed07be371c0e247621
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701126"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="39004-102">\<activityScheduledQueries > の WCF</span><span class="sxs-lookup"><span data-stu-id="39004-102">\<activityScheduledQueries> of WCF</span></span>
<span data-ttu-id="39004-103">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="39004-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="39004-104">アクティビティがスケジュールされたレコードを追跡参加要素が定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="39004-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="39004-105">追跡プロファイルのクエリの詳細については、次を参照してください[追跡プロファイル。](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="39004-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="39004-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="39004-106">\<system.serviceModel></span></span>  
<span data-ttu-id="39004-107">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="39004-107">\<tracking></span></span>  
<span data-ttu-id="39004-108">\<プロファイル ></span><span class="sxs-lookup"><span data-stu-id="39004-108">\<profiles></span></span>  
<span data-ttu-id="39004-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="39004-109">\<trackingProfile></span></span>  
<span data-ttu-id="39004-110">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="39004-110">\<workflow></span></span>  
<span data-ttu-id="39004-111">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="39004-111">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39004-112">構文</span><span class="sxs-lookup"><span data-stu-id="39004-112">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"
                                  childActivityName="String" />
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39004-113">属性と要素</span><span class="sxs-lookup"><span data-stu-id="39004-113">Attributes and elements</span></span>  

<span data-ttu-id="39004-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="39004-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39004-115">属性</span><span class="sxs-lookup"><span data-stu-id="39004-115">Attributes</span></span>  

<span data-ttu-id="39004-116">なし。</span><span class="sxs-lookup"><span data-stu-id="39004-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="39004-117">子要素</span><span class="sxs-lookup"><span data-stu-id="39004-117">Child elements</span></span>  
  
|<span data-ttu-id="39004-118">要素</span><span class="sxs-lookup"><span data-stu-id="39004-118">Element</span></span>|<span data-ttu-id="39004-119">説明</span><span class="sxs-lookup"><span data-stu-id="39004-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39004-120">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="39004-120">\<activityScheduledQuery></span></span>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="39004-121">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="39004-121">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="39004-122">親要素</span><span class="sxs-lookup"><span data-stu-id="39004-122">Parent elements</span></span>  
  
|<span data-ttu-id="39004-123">要素</span><span class="sxs-lookup"><span data-stu-id="39004-123">Element</span></span>|<span data-ttu-id="39004-124">説明</span><span class="sxs-lookup"><span data-stu-id="39004-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39004-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="39004-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="39004-126">`activityDefinitionId` プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="39004-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39004-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="39004-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="39004-128">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="39004-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="39004-129">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="39004-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
