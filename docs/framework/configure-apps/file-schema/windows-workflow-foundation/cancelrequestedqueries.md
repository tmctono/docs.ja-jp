---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 628dbf801cae5f61dc7d518c27df3380dd2d3d23
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945945"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="49c2d-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="49c2d-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="49c2d-102">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="49c2d-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="49c2d-103">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="49c2d-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="49c2d-104">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49c2d-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="49c2d-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="49c2d-105">\<system.serviceModel></span></span>  
<span data-ttu-id="49c2d-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="49c2d-106">\<tracking></span></span>  
<span data-ttu-id="49c2d-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="49c2d-107">\<trackingProfile></span></span>  
<span data-ttu-id="49c2d-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="49c2d-108">\<workflow></span></span>  
<span data-ttu-id="49c2d-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="49c2d-109">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49c2d-110">構文</span><span class="sxs-lookup"><span data-stu-id="49c2d-110">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String" 
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49c2d-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="49c2d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="49c2d-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="49c2d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49c2d-113">属性</span><span class="sxs-lookup"><span data-stu-id="49c2d-113">Attributes</span></span>  
 <span data-ttu-id="49c2d-114">なし。</span><span class="sxs-lookup"><span data-stu-id="49c2d-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="49c2d-115">子要素</span><span class="sxs-lookup"><span data-stu-id="49c2d-115">Child Elements</span></span>  
  
|<span data-ttu-id="49c2d-116">要素</span><span class="sxs-lookup"><span data-stu-id="49c2d-116">Element</span></span>|<span data-ttu-id="49c2d-117">説明</span><span class="sxs-lookup"><span data-stu-id="49c2d-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49c2d-118">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="49c2d-118">\<cancelRequestedQuery></span></span>](cancelrequestedquery.md)|<span data-ttu-id="49c2d-119">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="49c2d-119">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="49c2d-120">親要素</span><span class="sxs-lookup"><span data-stu-id="49c2d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="49c2d-121">要素</span><span class="sxs-lookup"><span data-stu-id="49c2d-121">Element</span></span>|<span data-ttu-id="49c2d-122">説明</span><span class="sxs-lookup"><span data-stu-id="49c2d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49c2d-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="49c2d-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="49c2d-124">**ActivityDefinitionId**プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="49c2d-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="49c2d-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="49c2d-125">See also</span></span>

- [<span data-ttu-id="49c2d-126">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="49c2d-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="49c2d-127">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="49c2d-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
