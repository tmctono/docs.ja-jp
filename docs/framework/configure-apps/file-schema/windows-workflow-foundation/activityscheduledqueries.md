---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 763754b95a7f39c7f35e05df28589b69352168e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152425"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="aecc4-101">\<アクティビティスケジュールされたクエリ></span><span class="sxs-lookup"><span data-stu-id="aecc4-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="aecc4-102">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="aecc4-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="aecc4-103">アクティビティがスケジュールされたレコードを追跡参加要素が定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="aecc4-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="aecc4-104">プロファイル クエリの追跡の詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aecc4-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="aecc4-105">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aecc4-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="aecc4-106">&nbsp;&nbsp;[**\<システム。サービスモデル>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="aecc4-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="aecc4-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<追跡>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="aecc4-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="aecc4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<追跡プロファイル>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="aecc4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="aecc4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ワークフロー>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="aecc4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="aecc4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<アクティビティスケジュールされたクエリ>**</span><span class="sxs-lookup"><span data-stu-id="aecc4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aecc4-111">構文</span><span class="sxs-lookup"><span data-stu-id="aecc4-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aecc4-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="aecc4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="aecc4-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="aecc4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aecc4-114">属性</span><span class="sxs-lookup"><span data-stu-id="aecc4-114">Attributes</span></span>  
 <span data-ttu-id="aecc4-115">[なし] :</span><span class="sxs-lookup"><span data-stu-id="aecc4-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aecc4-116">子要素</span><span class="sxs-lookup"><span data-stu-id="aecc4-116">Child Elements</span></span>  
  
|<span data-ttu-id="aecc4-117">要素</span><span class="sxs-lookup"><span data-stu-id="aecc4-117">Element</span></span>|<span data-ttu-id="aecc4-118">説明</span><span class="sxs-lookup"><span data-stu-id="aecc4-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aecc4-119">\<アクティビティスケジュールクエリ></span><span class="sxs-lookup"><span data-stu-id="aecc4-119">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="aecc4-120">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="aecc4-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aecc4-121">親要素</span><span class="sxs-lookup"><span data-stu-id="aecc4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="aecc4-122">要素</span><span class="sxs-lookup"><span data-stu-id="aecc4-122">Element</span></span>|<span data-ttu-id="aecc4-123">説明</span><span class="sxs-lookup"><span data-stu-id="aecc4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aecc4-124">\<ワークフロー></span><span class="sxs-lookup"><span data-stu-id="aecc4-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="aecc4-125">**activityDefinitionId**プロパティによって識別される特定のワークフローのすべてのクエリを含む構成要素。</span><span class="sxs-lookup"><span data-stu-id="aecc4-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aecc4-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="aecc4-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="aecc4-127">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="aecc4-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="aecc4-128">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="aecc4-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
