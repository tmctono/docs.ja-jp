---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 32a37fb3cc2b93046bea133f351185638b0d7545
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59163164"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="1a404-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="1a404-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="1a404-102">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="1a404-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="1a404-103">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="1a404-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="1a404-104">追跡プロファイルのクエリの詳細については、次を参照してください[追跡プロファイル。](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="1a404-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1a404-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1a404-105">\<system.serviceModel></span></span>  
<span data-ttu-id="1a404-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="1a404-106">\<tracking></span></span>  
<span data-ttu-id="1a404-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="1a404-107">\<trackingProfile></span></span>  
<span data-ttu-id="1a404-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="1a404-108">\<workflow></span></span>  
<span data-ttu-id="1a404-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="1a404-109">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a404-110">構文</span><span class="sxs-lookup"><span data-stu-id="1a404-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a404-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1a404-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1a404-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a404-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a404-113">属性</span><span class="sxs-lookup"><span data-stu-id="1a404-113">Attributes</span></span>  
 <span data-ttu-id="1a404-114">なし。</span><span class="sxs-lookup"><span data-stu-id="1a404-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1a404-115">子要素</span><span class="sxs-lookup"><span data-stu-id="1a404-115">Child Elements</span></span>  
  
|<span data-ttu-id="1a404-116">要素</span><span class="sxs-lookup"><span data-stu-id="1a404-116">Element</span></span>|<span data-ttu-id="1a404-117">説明</span><span class="sxs-lookup"><span data-stu-id="1a404-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a404-118">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="1a404-118">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="1a404-119">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="1a404-119">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1a404-120">親要素</span><span class="sxs-lookup"><span data-stu-id="1a404-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1a404-121">要素</span><span class="sxs-lookup"><span data-stu-id="1a404-121">Element</span></span>|<span data-ttu-id="1a404-122">説明</span><span class="sxs-lookup"><span data-stu-id="1a404-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a404-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="1a404-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="1a404-124">識別される特定のワークフローのすべてのクエリを格納する構成要素、 **activityDefinitionId**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="1a404-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a404-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a404-125">See also</span></span>

- [<span data-ttu-id="1a404-126">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="1a404-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1a404-127">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="1a404-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
