---
title: <customTrackingQueries> WCF の
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 8b317cc289853902592e145e34b6e7bf5f84763b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55282374"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="20c32-102">\<customTrackingQueries > の WCF</span><span class="sxs-lookup"><span data-stu-id="20c32-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="20c32-103">コード アクティビティで定義するイベントを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="20c32-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="20c32-104">追跡参加要素がカスタム追跡レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="20c32-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="20c32-105">追跡プロファイルのクエリの詳細については、[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c32-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="20c32-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="20c32-106">\<system.serviceModel></span></span>  
<span data-ttu-id="20c32-107">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="20c32-107">\<tracking></span></span>  
<span data-ttu-id="20c32-108">\<プロファイル ></span><span class="sxs-lookup"><span data-stu-id="20c32-108">\<profiles></span></span>  
<span data-ttu-id="20c32-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="20c32-109">\<trackingProfile></span></span>  
<span data-ttu-id="20c32-110">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="20c32-110">\<workflow></span></span>  
<span data-ttu-id="20c32-111">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="20c32-111">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20c32-112">構文</span><span class="sxs-lookup"><span data-stu-id="20c32-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20c32-113">属性と要素</span><span class="sxs-lookup"><span data-stu-id="20c32-113">Attributes and elements</span></span>

<span data-ttu-id="20c32-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="20c32-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20c32-115">属性</span><span class="sxs-lookup"><span data-stu-id="20c32-115">Attributes</span></span>

<span data-ttu-id="20c32-116">なし。</span><span class="sxs-lookup"><span data-stu-id="20c32-116">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="20c32-117">子要素</span><span class="sxs-lookup"><span data-stu-id="20c32-117">Child elements</span></span>
  
|<span data-ttu-id="20c32-118">要素</span><span class="sxs-lookup"><span data-stu-id="20c32-118">Element</span></span>|<span data-ttu-id="20c32-119">説明</span><span class="sxs-lookup"><span data-stu-id="20c32-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20c32-120">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="20c32-120">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="20c32-121">コード アクティビティで定義するイベントを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="20c32-121">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="20c32-122">親要素</span><span class="sxs-lookup"><span data-stu-id="20c32-122">Parent elements</span></span>  
  
|<span data-ttu-id="20c32-123">要素</span><span class="sxs-lookup"><span data-stu-id="20c32-123">Element</span></span>|<span data-ttu-id="20c32-124">説明</span><span class="sxs-lookup"><span data-stu-id="20c32-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20c32-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="20c32-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="20c32-126">`activityDefinitionId` プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="20c32-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="20c32-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="20c32-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="20c32-128">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="20c32-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="20c32-129">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="20c32-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
