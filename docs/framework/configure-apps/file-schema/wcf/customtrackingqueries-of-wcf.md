---
title: <customTrackingQueries>WCF の
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: abc0c7dfb426338ec6bca61b0a4b87754bb63588
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925939"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="8a665-102">\<WCF の customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="8a665-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="8a665-103">コード アクティビティで定義するイベントを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="8a665-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="8a665-104">追跡参加要素がカスタム追跡レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="8a665-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="8a665-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a665-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="8a665-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8a665-106">\<system.serviceModel></span></span>  
<span data-ttu-id="8a665-107">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="8a665-107">\<tracking></span></span>  
<span data-ttu-id="8a665-108">\<プロファイル ></span><span class="sxs-lookup"><span data-stu-id="8a665-108">\<profiles></span></span>  
<span data-ttu-id="8a665-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="8a665-109">\<trackingProfile></span></span>  
<span data-ttu-id="8a665-110">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="8a665-110">\<workflow></span></span>  
<span data-ttu-id="8a665-111">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="8a665-111">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a665-112">構文</span><span class="sxs-lookup"><span data-stu-id="8a665-112">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a665-113">属性と要素</span><span class="sxs-lookup"><span data-stu-id="8a665-113">Attributes and elements</span></span>

<span data-ttu-id="8a665-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8a665-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a665-115">属性</span><span class="sxs-lookup"><span data-stu-id="8a665-115">Attributes</span></span>

<span data-ttu-id="8a665-116">なし。</span><span class="sxs-lookup"><span data-stu-id="8a665-116">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="8a665-117">子要素</span><span class="sxs-lookup"><span data-stu-id="8a665-117">Child elements</span></span>
  
|<span data-ttu-id="8a665-118">要素</span><span class="sxs-lookup"><span data-stu-id="8a665-118">Element</span></span>|<span data-ttu-id="8a665-119">説明</span><span class="sxs-lookup"><span data-stu-id="8a665-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a665-120">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="8a665-120">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="8a665-121">コード アクティビティで定義するイベントを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="8a665-121">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8a665-122">親要素</span><span class="sxs-lookup"><span data-stu-id="8a665-122">Parent elements</span></span>  
  
|<span data-ttu-id="8a665-123">要素</span><span class="sxs-lookup"><span data-stu-id="8a665-123">Element</span></span>|<span data-ttu-id="8a665-124">説明</span><span class="sxs-lookup"><span data-stu-id="8a665-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a665-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="8a665-125">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="8a665-126">`activityDefinitionId` プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="8a665-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a665-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a665-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8a665-128">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="8a665-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8a665-129">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="8a665-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
