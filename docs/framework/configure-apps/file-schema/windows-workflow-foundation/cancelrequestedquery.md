---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 5f2e46d5e4cdd64c37219476790b9ff92c606b6b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215314"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="c9867-101">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="c9867-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="c9867-102">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用するクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="c9867-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="c9867-103">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="c9867-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="c9867-104">追跡プロファイルのクエリの詳細については、次を参照してください。[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)します。</span><span class="sxs-lookup"><span data-stu-id="c9867-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="c9867-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c9867-105">\<system.serviceModel></span></span>  
<span data-ttu-id="c9867-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="c9867-106">\<tracking></span></span>  
<span data-ttu-id="c9867-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="c9867-107">\<trackingProfile></span></span>  
<span data-ttu-id="c9867-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="c9867-108">\<workflow></span></span>  
<span data-ttu-id="c9867-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="c9867-109">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="c9867-110">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="c9867-110">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9867-111">構文</span><span class="sxs-lookup"><span data-stu-id="c9867-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9867-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c9867-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c9867-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9867-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9867-114">属性</span><span class="sxs-lookup"><span data-stu-id="c9867-114">Attributes</span></span>  
  
|<span data-ttu-id="c9867-115">属性</span><span class="sxs-lookup"><span data-stu-id="c9867-115">Attribute</span></span>|<span data-ttu-id="c9867-116">説明</span><span class="sxs-lookup"><span data-stu-id="c9867-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c9867-117">activityName</span><span class="sxs-lookup"><span data-stu-id="c9867-117">activityName</span></span>|<span data-ttu-id="c9867-118">キャンセルを要求しているアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="c9867-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="c9867-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="c9867-119">childActivityName</span></span>|<span data-ttu-id="c9867-120">キャンセルが要求された子アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="c9867-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c9867-121">子要素</span><span class="sxs-lookup"><span data-stu-id="c9867-121">Child Elements</span></span>  
 <span data-ttu-id="c9867-122">なし。</span><span class="sxs-lookup"><span data-stu-id="c9867-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c9867-123">親要素</span><span class="sxs-lookup"><span data-stu-id="c9867-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c9867-124">要素</span><span class="sxs-lookup"><span data-stu-id="c9867-124">Element</span></span>|<span data-ttu-id="c9867-125">説明</span><span class="sxs-lookup"><span data-stu-id="c9867-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9867-126">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="c9867-126">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="c9867-127">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する構成要素の一覧を表します。</span><span class="sxs-lookup"><span data-stu-id="c9867-127">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="c9867-128">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="c9867-128">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c9867-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9867-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c9867-130">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="c9867-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c9867-131">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="c9867-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
