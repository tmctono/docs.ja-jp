---
title: <activityScheduledQueries>WCF の
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: c2281a9027aabfc5255ef7b09176f60d1725b522
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850498"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="91377-102">\<WCF の activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="91377-102">\<activityScheduledQueries> of WCF</span></span>
<span data-ttu-id="91377-103">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="91377-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="91377-104">アクティビティがスケジュールされたレコードを追跡参加要素が定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="91377-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="91377-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91377-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="91377-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="91377-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="91377-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="91377-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="91377-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="91377-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="91377-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<プロファイル >** </span><span class="sxs-lookup"><span data-stu-id="91377-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="91377-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="91377-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="91377-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="91377-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="91377-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<activityScheduledQueries >**</span><span class="sxs-lookup"><span data-stu-id="91377-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91377-113">構文</span><span class="sxs-lookup"><span data-stu-id="91377-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91377-114">属性と要素</span><span class="sxs-lookup"><span data-stu-id="91377-114">Attributes and elements</span></span>  

<span data-ttu-id="91377-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="91377-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91377-116">属性</span><span class="sxs-lookup"><span data-stu-id="91377-116">Attributes</span></span>  

<span data-ttu-id="91377-117">なし。</span><span class="sxs-lookup"><span data-stu-id="91377-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="91377-118">子要素</span><span class="sxs-lookup"><span data-stu-id="91377-118">Child elements</span></span>  
  
|<span data-ttu-id="91377-119">要素</span><span class="sxs-lookup"><span data-stu-id="91377-119">Element</span></span>|<span data-ttu-id="91377-120">説明</span><span class="sxs-lookup"><span data-stu-id="91377-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91377-121">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="91377-121">\<activityScheduledQuery></span></span>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="91377-122">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="91377-122">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="91377-123">親要素</span><span class="sxs-lookup"><span data-stu-id="91377-123">Parent elements</span></span>  
  
|<span data-ttu-id="91377-124">要素</span><span class="sxs-lookup"><span data-stu-id="91377-124">Element</span></span>|<span data-ttu-id="91377-125">説明</span><span class="sxs-lookup"><span data-stu-id="91377-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91377-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="91377-126">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="91377-127">`activityDefinitionId` プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="91377-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91377-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="91377-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="91377-129">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="91377-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="91377-130">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="91377-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
