---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: d9c3f91edb41bd034bcd978b075d62f74b6e308d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945882"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="1ecd2-101">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="1ecd2-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="1ecd2-102">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用するクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="1ecd2-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="1ecd2-103">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="1ecd2-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="1ecd2-104">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ecd2-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="1ecd2-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1ecd2-105">\<system.serviceModel></span></span>  
<span data-ttu-id="1ecd2-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="1ecd2-106">\<tracking></span></span>  
<span data-ttu-id="1ecd2-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="1ecd2-107">\<trackingProfile></span></span>  
<span data-ttu-id="1ecd2-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="1ecd2-108">\<workflow></span></span>  
<span data-ttu-id="1ecd2-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="1ecd2-109">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="1ecd2-110">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="1ecd2-110">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ecd2-111">構文</span><span class="sxs-lookup"><span data-stu-id="1ecd2-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ecd2-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1ecd2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1ecd2-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ecd2-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ecd2-114">属性</span><span class="sxs-lookup"><span data-stu-id="1ecd2-114">Attributes</span></span>  
  
|<span data-ttu-id="1ecd2-115">属性</span><span class="sxs-lookup"><span data-stu-id="1ecd2-115">Attribute</span></span>|<span data-ttu-id="1ecd2-116">説明</span><span class="sxs-lookup"><span data-stu-id="1ecd2-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1ecd2-117">activityName</span><span class="sxs-lookup"><span data-stu-id="1ecd2-117">activityName</span></span>|<span data-ttu-id="1ecd2-118">キャンセルを要求しているアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="1ecd2-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="1ecd2-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="1ecd2-119">childActivityName</span></span>|<span data-ttu-id="1ecd2-120">キャンセルが要求された子アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="1ecd2-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ecd2-121">子要素</span><span class="sxs-lookup"><span data-stu-id="1ecd2-121">Child Elements</span></span>  
 <span data-ttu-id="1ecd2-122">なし。</span><span class="sxs-lookup"><span data-stu-id="1ecd2-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1ecd2-123">親要素</span><span class="sxs-lookup"><span data-stu-id="1ecd2-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1ecd2-124">要素</span><span class="sxs-lookup"><span data-stu-id="1ecd2-124">Element</span></span>|<span data-ttu-id="1ecd2-125">説明</span><span class="sxs-lookup"><span data-stu-id="1ecd2-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ecd2-126">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="1ecd2-126">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="1ecd2-127">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する構成要素の一覧を表します。</span><span class="sxs-lookup"><span data-stu-id="1ecd2-127">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="1ecd2-128">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="1ecd2-128">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1ecd2-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ecd2-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1ecd2-130">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="1ecd2-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1ecd2-131">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="1ecd2-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
