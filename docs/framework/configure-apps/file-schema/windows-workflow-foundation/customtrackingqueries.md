---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 663dda571990a86dc71ea927c4e97241e0ed3fc1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120082"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="3d468-101">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="3d468-101">\<customTrackingQueries></span></span>
<span data-ttu-id="3d468-102">コード アクティビティで定義するイベントを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="3d468-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="3d468-103">追跡参加要素がカスタム追跡レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="3d468-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="3d468-104">追跡プロファイルのクエリの詳細については、次を参照してください[追跡プロファイル。](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="3d468-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="3d468-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3d468-105">\<system.serviceModel></span></span>  
<span data-ttu-id="3d468-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="3d468-106">\<tracking></span></span>  
<span data-ttu-id="3d468-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="3d468-107">\<trackingProfile></span></span>  
<span data-ttu-id="3d468-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="3d468-108">\<workflow></span></span>  
<span data-ttu-id="3d468-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="3d468-109">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d468-110">構文</span><span class="sxs-lookup"><span data-stu-id="3d468-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d468-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3d468-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3d468-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d468-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d468-113">属性</span><span class="sxs-lookup"><span data-stu-id="3d468-113">Attributes</span></span>  
 <span data-ttu-id="3d468-114">なし。</span><span class="sxs-lookup"><span data-stu-id="3d468-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3d468-115">子要素</span><span class="sxs-lookup"><span data-stu-id="3d468-115">Child Elements</span></span>  
  
|<span data-ttu-id="3d468-116">要素</span><span class="sxs-lookup"><span data-stu-id="3d468-116">Element</span></span>|<span data-ttu-id="3d468-117">説明</span><span class="sxs-lookup"><span data-stu-id="3d468-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d468-118">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="3d468-118">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="3d468-119">コード アクティビティで定義するイベントを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="3d468-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3d468-120">親要素</span><span class="sxs-lookup"><span data-stu-id="3d468-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3d468-121">要素</span><span class="sxs-lookup"><span data-stu-id="3d468-121">Element</span></span>|<span data-ttu-id="3d468-122">説明</span><span class="sxs-lookup"><span data-stu-id="3d468-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d468-123">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="3d468-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="3d468-124">識別される特定のワークフローのすべてのクエリを格納する構成要素、 **activityDefinitionId**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3d468-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d468-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d468-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3d468-126">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="3d468-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3d468-127">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="3d468-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
