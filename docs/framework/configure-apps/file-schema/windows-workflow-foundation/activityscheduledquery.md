---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: 207931f68303883c29161cc28a5fc1974d01b6b8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148738"
---
# \<activityScheduledQuery>

<span data-ttu-id="1f880-101">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="1f880-101">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="1f880-102">アクティビティがスケジュールされたレコードを追跡参加要素が定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="1f880-102">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="1f880-103">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f880-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="1f880-104">構文</span><span class="sxs-lookup"><span data-stu-id="1f880-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f880-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1f880-105">Attributes and Elements</span></span>  

 <span data-ttu-id="1f880-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1f880-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f880-107">属性</span><span class="sxs-lookup"><span data-stu-id="1f880-107">Attributes</span></span>  
  
|<span data-ttu-id="1f880-108">属性</span><span class="sxs-lookup"><span data-stu-id="1f880-108">Attribute</span></span>|<span data-ttu-id="1f880-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="1f880-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1f880-110">activityName</span><span class="sxs-lookup"><span data-stu-id="1f880-110">activityName</span></span>|<span data-ttu-id="1f880-111">キャンセルを要求しているアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="1f880-111">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="1f880-112">childActivityName</span><span class="sxs-lookup"><span data-stu-id="1f880-112">childActivityName</span></span>|<span data-ttu-id="1f880-113">キャンセルが要求された子アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="1f880-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1f880-114">子要素</span><span class="sxs-lookup"><span data-stu-id="1f880-114">Child Elements</span></span>  

 <span data-ttu-id="1f880-115">なし。</span><span class="sxs-lookup"><span data-stu-id="1f880-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1f880-116">親要素</span><span class="sxs-lookup"><span data-stu-id="1f880-116">Parent Elements</span></span>  
  
|<span data-ttu-id="1f880-117">要素</span><span class="sxs-lookup"><span data-stu-id="1f880-117">Element</span></span>|<span data-ttu-id="1f880-118">説明</span><span class="sxs-lookup"><span data-stu-id="1f880-118">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery.md)|<span data-ttu-id="1f880-119">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="1f880-119">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1f880-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f880-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1f880-121">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="1f880-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1f880-122">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="1f880-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
