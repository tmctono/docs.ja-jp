---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: d49c6d933a09dce5d657746358f1a5f716ab639b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143365"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="0ede6-101">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="0ede6-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="0ede6-102">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="0ede6-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="0ede6-103">アクティビティがスケジュールされたレコードを追跡参加要素が定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="0ede6-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="0ede6-104">追跡プロファイルのクエリの詳細については、次を参照してください[追跡プロファイル。](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="0ede6-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="0ede6-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0ede6-105">\<system.serviceModel></span></span>  
<span data-ttu-id="0ede6-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="0ede6-106">\<tracking></span></span>  
<span data-ttu-id="0ede6-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="0ede6-107">\<trackingProfile></span></span>  
<span data-ttu-id="0ede6-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="0ede6-108">\<workflow></span></span>  
<span data-ttu-id="0ede6-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="0ede6-109">\<activityScheduledQueries></span></span>  
<span data-ttu-id="0ede6-110">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="0ede6-110">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ede6-111">構文</span><span class="sxs-lookup"><span data-stu-id="0ede6-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ede6-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0ede6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0ede6-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0ede6-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ede6-114">属性</span><span class="sxs-lookup"><span data-stu-id="0ede6-114">Attributes</span></span>  
  
|<span data-ttu-id="0ede6-115">属性</span><span class="sxs-lookup"><span data-stu-id="0ede6-115">Attribute</span></span>|<span data-ttu-id="0ede6-116">説明</span><span class="sxs-lookup"><span data-stu-id="0ede6-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0ede6-117">activityName</span><span class="sxs-lookup"><span data-stu-id="0ede6-117">activityName</span></span>|<span data-ttu-id="0ede6-118">キャンセルを要求しているアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="0ede6-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="0ede6-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="0ede6-119">childActivityName</span></span>|<span data-ttu-id="0ede6-120">キャンセルが要求された子アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="0ede6-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0ede6-121">子要素</span><span class="sxs-lookup"><span data-stu-id="0ede6-121">Child Elements</span></span>  
 <span data-ttu-id="0ede6-122">なし。</span><span class="sxs-lookup"><span data-stu-id="0ede6-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0ede6-123">親要素</span><span class="sxs-lookup"><span data-stu-id="0ede6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="0ede6-124">要素</span><span class="sxs-lookup"><span data-stu-id="0ede6-124">Element</span></span>|<span data-ttu-id="0ede6-125">説明</span><span class="sxs-lookup"><span data-stu-id="0ede6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0ede6-126">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="0ede6-126">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="0ede6-127">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="0ede6-127">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0ede6-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ede6-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0ede6-129">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="0ede6-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0ede6-130">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="0ede6-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
