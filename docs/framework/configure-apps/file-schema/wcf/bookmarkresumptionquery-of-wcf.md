---
title: <bookmarkResumptionQuery> WCF の
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 38c87cefc49821b03d119299ef60e3fbbad21d7e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704389"
---
# <a name="bookmarkresumptionquery-of-wcf"></a><span data-ttu-id="b2e44-102">\<bookmarkResumptionQuery > の WCF</span><span class="sxs-lookup"><span data-stu-id="b2e44-102">\<bookmarkResumptionQuery> of WCF</span></span>

<span data-ttu-id="b2e44-103">ワークフロー インスタンス内のブックマークの再開を追跡するために使用されるクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="b2e44-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="b2e44-104">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="b2e44-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="b2e44-105">追跡プロファイルのクエリの詳細については、次を参照してください[追跡プロファイル。](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b2e44-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>
  
<span data-ttu-id="b2e44-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b2e44-106">\<system.serviceModel></span></span>  
<span data-ttu-id="b2e44-107">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="b2e44-107">\<tracking></span></span>  
<span data-ttu-id="b2e44-108">\<プロファイル ></span><span class="sxs-lookup"><span data-stu-id="b2e44-108">\<profiles></span></span>  
<span data-ttu-id="b2e44-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b2e44-109">\<trackingProfile></span></span>  
<span data-ttu-id="b2e44-110">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="b2e44-110">\<workflow></span></span>  
<span data-ttu-id="b2e44-111">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="b2e44-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="b2e44-112">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="b2e44-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2e44-113">構文</span><span class="sxs-lookup"><span data-stu-id="b2e44-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <bookmarkResumptionQueries>
          <bookmarkResumptionQuery name="String" />
        </bookmarkResumptionQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2e44-114">属性と要素</span><span class="sxs-lookup"><span data-stu-id="b2e44-114">Attributes and elements</span></span>

<span data-ttu-id="b2e44-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b2e44-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2e44-116">属性</span><span class="sxs-lookup"><span data-stu-id="b2e44-116">Attributes</span></span>  
  
|<span data-ttu-id="b2e44-117">属性</span><span class="sxs-lookup"><span data-stu-id="b2e44-117">Attribute</span></span>|<span data-ttu-id="b2e44-118">説明</span><span class="sxs-lookup"><span data-stu-id="b2e44-118">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="b2e44-119">定期受信するブックマーク レコードの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="b2e44-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2e44-120">子要素</span><span class="sxs-lookup"><span data-stu-id="b2e44-120">Child elements</span></span>

<span data-ttu-id="b2e44-121">なし。</span><span class="sxs-lookup"><span data-stu-id="b2e44-121">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="b2e44-122">親要素</span><span class="sxs-lookup"><span data-stu-id="b2e44-122">Parent elements</span></span>  
  
|<span data-ttu-id="b2e44-123">要素</span><span class="sxs-lookup"><span data-stu-id="b2e44-123">Element</span></span>|<span data-ttu-id="b2e44-124">説明</span><span class="sxs-lookup"><span data-stu-id="b2e44-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2e44-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="b2e44-125">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="b2e44-126">ワークフロー インスタンス内のブックマークの再開を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="b2e44-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b2e44-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2e44-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b2e44-128">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="b2e44-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b2e44-129">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="b2e44-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
