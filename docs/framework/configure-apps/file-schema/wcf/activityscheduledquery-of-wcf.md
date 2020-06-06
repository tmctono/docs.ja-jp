---
title: <activityScheduledQuery>WCF の
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: b173964cf5d691f4b9300bca69ca4a1fe1ea7e11
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850466"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="d6fac-102">\<activityScheduledQuery>WCF の</span><span class="sxs-lookup"><span data-stu-id="d6fac-102">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="d6fac-103">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="d6fac-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="d6fac-104">アクティビティがスケジュールされたレコードを追跡参加要素が定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="d6fac-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="d6fac-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6fac-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="d6fac-106">構文</span><span class="sxs-lookup"><span data-stu-id="d6fac-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6fac-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="d6fac-107">Attributes and elements</span></span>  

<span data-ttu-id="d6fac-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6fac-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6fac-109">属性</span><span class="sxs-lookup"><span data-stu-id="d6fac-109">Attributes</span></span>  
  
|<span data-ttu-id="d6fac-110">属性</span><span class="sxs-lookup"><span data-stu-id="d6fac-110">Attribute</span></span>|<span data-ttu-id="d6fac-111">説明</span><span class="sxs-lookup"><span data-stu-id="d6fac-111">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="d6fac-112">キャンセルを要求しているアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="d6fac-112">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="d6fac-113">キャンセルが要求された子アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="d6fac-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6fac-114">子要素</span><span class="sxs-lookup"><span data-stu-id="d6fac-114">Child elements</span></span>

<span data-ttu-id="d6fac-115">なし。</span><span class="sxs-lookup"><span data-stu-id="d6fac-115">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="d6fac-116">親要素</span><span class="sxs-lookup"><span data-stu-id="d6fac-116">Parent elements</span></span>  
  
|<span data-ttu-id="d6fac-117">要素</span><span class="sxs-lookup"><span data-stu-id="d6fac-117">Element</span></span>|<span data-ttu-id="d6fac-118">Description</span><span class="sxs-lookup"><span data-stu-id="d6fac-118">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQueries>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="d6fac-119">親アクティビティによって実行されるようにスケジュールされたアクティビティを追跡するために使用されるクエリのコレクション。</span><span class="sxs-lookup"><span data-stu-id="d6fac-119">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d6fac-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6fac-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="d6fac-121">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="d6fac-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d6fac-122">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="d6fac-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
