---
title: <activityScheduledQueries>WCF の
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: c2281a9027aabfc5255ef7b09176f60d1725b522
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850498"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="8ea87-102">\<activityScheduledQueries>WCF の</span><span class="sxs-lookup"><span data-stu-id="8ea87-102">\<activityScheduledQueries> of WCF</span></span>
<span data-ttu-id="8ea87-103">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="8ea87-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="8ea87-104">アクティビティがスケジュールされたレコードを追跡参加要素が定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="8ea87-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="8ea87-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea87-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="8ea87-106">構文</span><span class="sxs-lookup"><span data-stu-id="8ea87-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ea87-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="8ea87-107">Attributes and elements</span></span>  

<span data-ttu-id="8ea87-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ea87-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ea87-109">属性</span><span class="sxs-lookup"><span data-stu-id="8ea87-109">Attributes</span></span>  

<span data-ttu-id="8ea87-110">なし。</span><span class="sxs-lookup"><span data-stu-id="8ea87-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8ea87-111">子要素</span><span class="sxs-lookup"><span data-stu-id="8ea87-111">Child elements</span></span>  
  
|<span data-ttu-id="8ea87-112">要素</span><span class="sxs-lookup"><span data-stu-id="8ea87-112">Element</span></span>|<span data-ttu-id="8ea87-113">説明</span><span class="sxs-lookup"><span data-stu-id="8ea87-113">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="8ea87-114">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="8ea87-114">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8ea87-115">親要素</span><span class="sxs-lookup"><span data-stu-id="8ea87-115">Parent elements</span></span>  
  
|<span data-ttu-id="8ea87-116">要素</span><span class="sxs-lookup"><span data-stu-id="8ea87-116">Element</span></span>|<span data-ttu-id="8ea87-117">説明</span><span class="sxs-lookup"><span data-stu-id="8ea87-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="8ea87-118">`activityDefinitionId` プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="8ea87-118">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ea87-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ea87-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="8ea87-120">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="8ea87-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8ea87-121">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="8ea87-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
