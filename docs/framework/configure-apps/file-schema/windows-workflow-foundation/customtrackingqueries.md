---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 429940b2ed69d8be497626f634a21adca540b529
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945828"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="8d304-101">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="8d304-101">\<customTrackingQueries></span></span>
<span data-ttu-id="8d304-102">コード アクティビティで定義するイベントを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="8d304-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="8d304-103">追跡参加要素がカスタム追跡レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="8d304-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="8d304-104">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d304-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="8d304-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8d304-105">\<system.serviceModel></span></span>  
<span data-ttu-id="8d304-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="8d304-106">\<tracking></span></span>  
<span data-ttu-id="8d304-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="8d304-107">\<trackingProfile></span></span>  
<span data-ttu-id="8d304-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="8d304-108">\<workflow></span></span>  
<span data-ttu-id="8d304-109">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="8d304-109">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d304-110">構文</span><span class="sxs-lookup"><span data-stu-id="8d304-110">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d304-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8d304-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8d304-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d304-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d304-113">属性</span><span class="sxs-lookup"><span data-stu-id="8d304-113">Attributes</span></span>  
 <span data-ttu-id="8d304-114">なし。</span><span class="sxs-lookup"><span data-stu-id="8d304-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8d304-115">子要素</span><span class="sxs-lookup"><span data-stu-id="8d304-115">Child Elements</span></span>  
  
|<span data-ttu-id="8d304-116">要素</span><span class="sxs-lookup"><span data-stu-id="8d304-116">Element</span></span>|<span data-ttu-id="8d304-117">説明</span><span class="sxs-lookup"><span data-stu-id="8d304-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d304-118">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="8d304-118">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="8d304-119">コード アクティビティで定義するイベントを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="8d304-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8d304-120">親要素</span><span class="sxs-lookup"><span data-stu-id="8d304-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8d304-121">要素</span><span class="sxs-lookup"><span data-stu-id="8d304-121">Element</span></span>|<span data-ttu-id="8d304-122">説明</span><span class="sxs-lookup"><span data-stu-id="8d304-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d304-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="8d304-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="8d304-124">**ActivityDefinitionId**プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="8d304-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8d304-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d304-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8d304-126">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="8d304-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8d304-127">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="8d304-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
