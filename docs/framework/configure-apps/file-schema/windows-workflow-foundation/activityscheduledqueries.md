---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: a43242e2f22c48a57c11f6f03657d7d3de27ff48
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398974"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="36e81-101">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="36e81-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="36e81-102">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="36e81-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="36e81-103">アクティビティがスケジュールされたレコードを追跡参加要素が定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="36e81-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="36e81-104">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36e81-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="36e81-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="36e81-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="36e81-106">&nbsp;&nbsp;[ **\<system.ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="36e81-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="36e81-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="36e81-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="36e81-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="36e81-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="36e81-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="36e81-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="36e81-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<activityScheduledQueries >**</span><span class="sxs-lookup"><span data-stu-id="36e81-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36e81-111">構文</span><span class="sxs-lookup"><span data-stu-id="36e81-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36e81-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="36e81-112">Attributes and Elements</span></span>  
 <span data-ttu-id="36e81-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="36e81-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36e81-114">属性</span><span class="sxs-lookup"><span data-stu-id="36e81-114">Attributes</span></span>  
 <span data-ttu-id="36e81-115">なし。</span><span class="sxs-lookup"><span data-stu-id="36e81-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="36e81-116">子要素</span><span class="sxs-lookup"><span data-stu-id="36e81-116">Child Elements</span></span>  
  
|<span data-ttu-id="36e81-117">要素</span><span class="sxs-lookup"><span data-stu-id="36e81-117">Element</span></span>|<span data-ttu-id="36e81-118">説明</span><span class="sxs-lookup"><span data-stu-id="36e81-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36e81-119">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="36e81-119">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="36e81-120">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="36e81-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="36e81-121">親要素</span><span class="sxs-lookup"><span data-stu-id="36e81-121">Parent Elements</span></span>  
  
|<span data-ttu-id="36e81-122">要素</span><span class="sxs-lookup"><span data-stu-id="36e81-122">Element</span></span>|<span data-ttu-id="36e81-123">説明</span><span class="sxs-lookup"><span data-stu-id="36e81-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36e81-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="36e81-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="36e81-125">**ActivityDefinitionId**プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="36e81-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36e81-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="36e81-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="36e81-127">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="36e81-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="36e81-128">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="36e81-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
