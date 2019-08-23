---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: dc04405204be7c5484d47b4a3767f846b11abf9f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945500"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="d8164-101">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="d8164-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="d8164-102">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="d8164-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="d8164-103">アクティビティがスケジュールされたレコードを追跡参加要素が定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="d8164-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="d8164-104">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8164-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="d8164-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d8164-105">\<system.serviceModel></span></span>  
<span data-ttu-id="d8164-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="d8164-106">\<tracking></span></span>  
<span data-ttu-id="d8164-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d8164-107">\<trackingProfile></span></span>  
<span data-ttu-id="d8164-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="d8164-108">\<workflow></span></span>  
<span data-ttu-id="d8164-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="d8164-109">\<activityScheduledQueries></span></span>  
<span data-ttu-id="d8164-110">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="d8164-110">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8164-111">構文</span><span class="sxs-lookup"><span data-stu-id="d8164-111">Syntax</span></span>  
  
```xml 
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String"/>
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8164-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d8164-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d8164-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d8164-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8164-114">属性</span><span class="sxs-lookup"><span data-stu-id="d8164-114">Attributes</span></span>  
  
|<span data-ttu-id="d8164-115">属性</span><span class="sxs-lookup"><span data-stu-id="d8164-115">Attribute</span></span>|<span data-ttu-id="d8164-116">説明</span><span class="sxs-lookup"><span data-stu-id="d8164-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d8164-117">activityName</span><span class="sxs-lookup"><span data-stu-id="d8164-117">activityName</span></span>|<span data-ttu-id="d8164-118">キャンセルを要求しているアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="d8164-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="d8164-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="d8164-119">childActivityName</span></span>|<span data-ttu-id="d8164-120">キャンセルが要求された子アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="d8164-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d8164-121">子要素</span><span class="sxs-lookup"><span data-stu-id="d8164-121">Child Elements</span></span>  
 <span data-ttu-id="d8164-122">なし。</span><span class="sxs-lookup"><span data-stu-id="d8164-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d8164-123">親要素</span><span class="sxs-lookup"><span data-stu-id="d8164-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d8164-124">要素</span><span class="sxs-lookup"><span data-stu-id="d8164-124">Element</span></span>|<span data-ttu-id="d8164-125">説明</span><span class="sxs-lookup"><span data-stu-id="d8164-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8164-126">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="d8164-126">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="d8164-127">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="d8164-127">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8164-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8164-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d8164-129">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="d8164-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d8164-130">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="d8164-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
