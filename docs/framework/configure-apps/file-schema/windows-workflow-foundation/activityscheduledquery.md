---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: 09cbc43ae4db82dc80e6985131f8d6cc0c24b2ac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152412"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="724b8-101">\<アクティビティスケジュールクエリ></span><span class="sxs-lookup"><span data-stu-id="724b8-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="724b8-102">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="724b8-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="724b8-103">アクティビティがスケジュールされたレコードを追跡参加要素が定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="724b8-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="724b8-104">プロファイル クエリの追跡の詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="724b8-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="724b8-105">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="724b8-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="724b8-106">&nbsp;&nbsp;[**\<システム。サービスモデル>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="724b8-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="724b8-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<追跡>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="724b8-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="724b8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<追跡プロファイル>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="724b8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="724b8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ワークフロー>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="724b8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="724b8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<アクティビティスケジュールされたクエリ>**](activityscheduledqueries.md)</span><span class="sxs-lookup"><span data-stu-id="724b8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries.md)</span></span>\
<span data-ttu-id="724b8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<アクティビティスケジュールクエリ>**</span><span class="sxs-lookup"><span data-stu-id="724b8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="724b8-112">構文</span><span class="sxs-lookup"><span data-stu-id="724b8-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="724b8-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="724b8-113">Attributes and Elements</span></span>  
 <span data-ttu-id="724b8-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="724b8-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="724b8-115">属性</span><span class="sxs-lookup"><span data-stu-id="724b8-115">Attributes</span></span>  
  
|<span data-ttu-id="724b8-116">属性</span><span class="sxs-lookup"><span data-stu-id="724b8-116">Attribute</span></span>|<span data-ttu-id="724b8-117">説明</span><span class="sxs-lookup"><span data-stu-id="724b8-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="724b8-118">activityName</span><span class="sxs-lookup"><span data-stu-id="724b8-118">activityName</span></span>|<span data-ttu-id="724b8-119">キャンセルを要求しているアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="724b8-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="724b8-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="724b8-120">childActivityName</span></span>|<span data-ttu-id="724b8-121">キャンセルが要求された子アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="724b8-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="724b8-122">子要素</span><span class="sxs-lookup"><span data-stu-id="724b8-122">Child Elements</span></span>  
 <span data-ttu-id="724b8-123">[なし] :</span><span class="sxs-lookup"><span data-stu-id="724b8-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="724b8-124">親要素</span><span class="sxs-lookup"><span data-stu-id="724b8-124">Parent Elements</span></span>  
  
|<span data-ttu-id="724b8-125">要素</span><span class="sxs-lookup"><span data-stu-id="724b8-125">Element</span></span>|<span data-ttu-id="724b8-126">説明</span><span class="sxs-lookup"><span data-stu-id="724b8-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="724b8-127">\<アクティビティスケジュールクエリ></span><span class="sxs-lookup"><span data-stu-id="724b8-127">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="724b8-128">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="724b8-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="724b8-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="724b8-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="724b8-130">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="724b8-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="724b8-131">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="724b8-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
