---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 763754b95a7f39c7f35e05df28589b69352168e6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152425"
---
# \<activityScheduledQueries>
<span data-ttu-id="2c007-101">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="2c007-101">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="2c007-102">アクティビティがスケジュールされたレコードを追跡参加要素が定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="2c007-102">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="2c007-103">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c007-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="2c007-104">構文</span><span class="sxs-lookup"><span data-stu-id="2c007-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c007-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2c007-105">Attributes and Elements</span></span>  
 <span data-ttu-id="2c007-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c007-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c007-107">属性</span><span class="sxs-lookup"><span data-stu-id="2c007-107">Attributes</span></span>  
 <span data-ttu-id="2c007-108">なし。</span><span class="sxs-lookup"><span data-stu-id="2c007-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2c007-109">子要素</span><span class="sxs-lookup"><span data-stu-id="2c007-109">Child Elements</span></span>  
  
|<span data-ttu-id="2c007-110">要素</span><span class="sxs-lookup"><span data-stu-id="2c007-110">Element</span></span>|<span data-ttu-id="2c007-111">説明</span><span class="sxs-lookup"><span data-stu-id="2c007-111">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery.md)|<span data-ttu-id="2c007-112">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="2c007-112">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2c007-113">親要素</span><span class="sxs-lookup"><span data-stu-id="2c007-113">Parent Elements</span></span>  
  
|<span data-ttu-id="2c007-114">要素</span><span class="sxs-lookup"><span data-stu-id="2c007-114">Element</span></span>|<span data-ttu-id="2c007-115">説明</span><span class="sxs-lookup"><span data-stu-id="2c007-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="2c007-116">**ActivityDefinitionId**プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="2c007-116">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c007-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c007-117">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2c007-118">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="2c007-118">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2c007-119">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="2c007-119">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
