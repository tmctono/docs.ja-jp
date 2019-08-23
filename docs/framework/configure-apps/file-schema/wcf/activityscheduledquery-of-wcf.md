---
title: <activityScheduledQuery>WCF の
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: 7787ada68210ff832ff3fd1ec93c9d346e4d2eaa
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926925"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="b5d5a-102">\<WCF の activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="b5d5a-102">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="b5d5a-103">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="b5d5a-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="b5d5a-104">アクティビティがスケジュールされたレコードを追跡参加要素が定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="b5d5a-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="b5d5a-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5d5a-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b5d5a-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b5d5a-106">\<system.serviceModel></span></span>  
<span data-ttu-id="b5d5a-107">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="b5d5a-107">\<tracking></span></span>  
<span data-ttu-id="b5d5a-108">\<プロファイル ></span><span class="sxs-lookup"><span data-stu-id="b5d5a-108">\<profiles></span></span>  
<span data-ttu-id="b5d5a-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b5d5a-109">\<trackingProfile></span></span>  
<span data-ttu-id="b5d5a-110">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="b5d5a-110">\<workflow></span></span>  
<span data-ttu-id="b5d5a-111">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="b5d5a-111">\<activityScheduledQueries></span></span>  
<span data-ttu-id="b5d5a-112">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="b5d5a-112">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5d5a-113">構文</span><span class="sxs-lookup"><span data-stu-id="b5d5a-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5d5a-114">属性と要素</span><span class="sxs-lookup"><span data-stu-id="b5d5a-114">Attributes and elements</span></span>  

<span data-ttu-id="b5d5a-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b5d5a-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5d5a-116">属性</span><span class="sxs-lookup"><span data-stu-id="b5d5a-116">Attributes</span></span>  
  
|<span data-ttu-id="b5d5a-117">属性</span><span class="sxs-lookup"><span data-stu-id="b5d5a-117">Attribute</span></span>|<span data-ttu-id="b5d5a-118">説明</span><span class="sxs-lookup"><span data-stu-id="b5d5a-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="b5d5a-119">キャンセルを要求しているアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="b5d5a-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="b5d5a-120">キャンセルが要求された子アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="b5d5a-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b5d5a-121">子要素</span><span class="sxs-lookup"><span data-stu-id="b5d5a-121">Child elements</span></span>

<span data-ttu-id="b5d5a-122">なし。</span><span class="sxs-lookup"><span data-stu-id="b5d5a-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="b5d5a-123">親要素</span><span class="sxs-lookup"><span data-stu-id="b5d5a-123">Parent elements</span></span>  
  
|<span data-ttu-id="b5d5a-124">要素</span><span class="sxs-lookup"><span data-stu-id="b5d5a-124">Element</span></span>|<span data-ttu-id="b5d5a-125">説明</span><span class="sxs-lookup"><span data-stu-id="b5d5a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5d5a-126">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="b5d5a-126">\<activityScheduledQueries></span></span>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="b5d5a-127">親アクティビティによって実行されるようにスケジュールされたアクティビティを追跡するために使用されるクエリのコレクション。</span><span class="sxs-lookup"><span data-stu-id="b5d5a-127">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b5d5a-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5d5a-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="b5d5a-129">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="b5d5a-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b5d5a-130">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="b5d5a-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
