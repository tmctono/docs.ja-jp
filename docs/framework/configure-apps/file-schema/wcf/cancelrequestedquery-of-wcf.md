---
title: <cancelRequestedQuery> WCF の
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: bd6157e63761efa954744ab08ea6c66535def514
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55281334"
---
# <a name="cancelrequestedquery-of-wcf"></a><span data-ttu-id="bd18c-102">\<cancelRequestedQuery > の WCF</span><span class="sxs-lookup"><span data-stu-id="bd18c-102">\<cancelRequestedQuery> of WCF</span></span>

<span data-ttu-id="bd18c-103">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用するクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="bd18c-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="bd18c-104">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="bd18c-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="bd18c-105">追跡プロファイルのクエリの詳細については、[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd18c-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="bd18c-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="bd18c-106">\<system.serviceModel></span></span>  
<span data-ttu-id="bd18c-107">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="bd18c-107">\<tracking></span></span>  
<span data-ttu-id="bd18c-108">\<プロファイル ></span><span class="sxs-lookup"><span data-stu-id="bd18c-108">\<profiles></span></span>  
<span data-ttu-id="bd18c-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="bd18c-109">\<trackingProfile></span></span>  
<span data-ttu-id="bd18c-110">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="bd18c-110">\<workflow></span></span>  
<span data-ttu-id="bd18c-111">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="bd18c-111">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="bd18c-112">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="bd18c-112">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd18c-113">構文</span><span class="sxs-lookup"><span data-stu-id="bd18c-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestedQueries>
          <cancelRequestedQuery activityName="String"
                                childActivityName="String" />
        </cancelRequestedQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd18c-114">属性と要素</span><span class="sxs-lookup"><span data-stu-id="bd18c-114">Attributes and elements</span></span>

<span data-ttu-id="bd18c-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bd18c-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="bd18c-116">属性</span><span class="sxs-lookup"><span data-stu-id="bd18c-116">Attributes</span></span>  
  
|<span data-ttu-id="bd18c-117">属性</span><span class="sxs-lookup"><span data-stu-id="bd18c-117">Attribute</span></span>|<span data-ttu-id="bd18c-118">説明</span><span class="sxs-lookup"><span data-stu-id="bd18c-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="bd18c-119">キャンセルを要求しているアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="bd18c-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="bd18c-120">キャンセルが要求された子アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="bd18c-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bd18c-121">子要素</span><span class="sxs-lookup"><span data-stu-id="bd18c-121">Child elements</span></span>

<span data-ttu-id="bd18c-122">なし。</span><span class="sxs-lookup"><span data-stu-id="bd18c-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="bd18c-123">親要素</span><span class="sxs-lookup"><span data-stu-id="bd18c-123">Parent elements</span></span>
  
|<span data-ttu-id="bd18c-124">要素</span><span class="sxs-lookup"><span data-stu-id="bd18c-124">Element</span></span>|<span data-ttu-id="bd18c-125">説明</span><span class="sxs-lookup"><span data-stu-id="bd18c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd18c-126">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="bd18c-126">\<cancelRequestedQueries></span></span>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="bd18c-127">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="bd18c-127">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd18c-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd18c-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="bd18c-129">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="bd18c-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="bd18c-130">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="bd18c-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
