---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 936267f7d61dfd09af45ddb96b4406c92c30b3b2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148777"
---
# \<activityScheduledQueries>

<span data-ttu-id="a632d-101">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="a632d-101">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="a632d-102">アクティビティがスケジュールされたレコードを追跡参加要素が定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="a632d-102">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="a632d-103">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a632d-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="a632d-104">構文</span><span class="sxs-lookup"><span data-stu-id="a632d-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a632d-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a632d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a632d-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a632d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a632d-107">属性</span><span class="sxs-lookup"><span data-stu-id="a632d-107">Attributes</span></span>  

 <span data-ttu-id="a632d-108">なし。</span><span class="sxs-lookup"><span data-stu-id="a632d-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a632d-109">子要素</span><span class="sxs-lookup"><span data-stu-id="a632d-109">Child Elements</span></span>  
  
|<span data-ttu-id="a632d-110">要素</span><span class="sxs-lookup"><span data-stu-id="a632d-110">Element</span></span>|<span data-ttu-id="a632d-111">説明</span><span class="sxs-lookup"><span data-stu-id="a632d-111">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery.md)|<span data-ttu-id="a632d-112">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="a632d-112">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a632d-113">親要素</span><span class="sxs-lookup"><span data-stu-id="a632d-113">Parent Elements</span></span>  
  
|<span data-ttu-id="a632d-114">要素</span><span class="sxs-lookup"><span data-stu-id="a632d-114">Element</span></span>|<span data-ttu-id="a632d-115">説明</span><span class="sxs-lookup"><span data-stu-id="a632d-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="a632d-116">**ActivityDefinitionId**プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="a632d-116">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a632d-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a632d-117">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a632d-118">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="a632d-118">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a632d-119">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="a632d-119">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
