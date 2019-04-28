---
title: <activityScheduledQuery> WCF の
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: 5087d56092296f8c68b719ec0945993adeb3de0a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704720"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="d3595-102">\<activityScheduledQuery > の WCF</span><span class="sxs-lookup"><span data-stu-id="d3595-102">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="d3595-103">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="d3595-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="d3595-104">アクティビティがスケジュールされたレコードを追跡参加要素が定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="d3595-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="d3595-105">追跡プロファイルのクエリの詳細については、次を参照してください[追跡プロファイル。](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d3595-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="d3595-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d3595-106">\<system.serviceModel></span></span>  
<span data-ttu-id="d3595-107">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="d3595-107">\<tracking></span></span>  
<span data-ttu-id="d3595-108">\<プロファイル ></span><span class="sxs-lookup"><span data-stu-id="d3595-108">\<profiles></span></span>  
<span data-ttu-id="d3595-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d3595-109">\<trackingProfile></span></span>  
<span data-ttu-id="d3595-110">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="d3595-110">\<workflow></span></span>  
<span data-ttu-id="d3595-111">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="d3595-111">\<activityScheduledQueries></span></span>  
<span data-ttu-id="d3595-112">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="d3595-112">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3595-113">構文</span><span class="sxs-lookup"><span data-stu-id="d3595-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3595-114">属性と要素</span><span class="sxs-lookup"><span data-stu-id="d3595-114">Attributes and elements</span></span>  

<span data-ttu-id="d3595-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d3595-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3595-116">属性</span><span class="sxs-lookup"><span data-stu-id="d3595-116">Attributes</span></span>  
  
|<span data-ttu-id="d3595-117">属性</span><span class="sxs-lookup"><span data-stu-id="d3595-117">Attribute</span></span>|<span data-ttu-id="d3595-118">説明</span><span class="sxs-lookup"><span data-stu-id="d3595-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="d3595-119">キャンセルを要求しているアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="d3595-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="d3595-120">キャンセルが要求された子アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="d3595-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3595-121">子要素</span><span class="sxs-lookup"><span data-stu-id="d3595-121">Child elements</span></span>

<span data-ttu-id="d3595-122">なし。</span><span class="sxs-lookup"><span data-stu-id="d3595-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="d3595-123">親要素</span><span class="sxs-lookup"><span data-stu-id="d3595-123">Parent elements</span></span>  
  
|<span data-ttu-id="d3595-124">要素</span><span class="sxs-lookup"><span data-stu-id="d3595-124">Element</span></span>|<span data-ttu-id="d3595-125">説明</span><span class="sxs-lookup"><span data-stu-id="d3595-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d3595-126">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="d3595-126">\<activityScheduledQueries></span></span>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="d3595-127">親アクティビティによる実行のスケジュールされたアクティビティを追跡するために使用されるクエリのコレクション。</span><span class="sxs-lookup"><span data-stu-id="d3595-127">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d3595-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3595-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="d3595-129">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="d3595-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d3595-130">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="d3595-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
