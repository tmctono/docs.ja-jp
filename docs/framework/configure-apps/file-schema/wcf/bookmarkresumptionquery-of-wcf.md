---
title: <bookmarkResumptionQuery>WCF の
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: ee8457645a0b54e21ef27c2891ebea97d6cc547b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926358"
---
# <a name="bookmarkresumptionquery-of-wcf"></a><span data-ttu-id="60e35-102">\<WCF の bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="60e35-102">\<bookmarkResumptionQuery> of WCF</span></span>

<span data-ttu-id="60e35-103">ワークフロー インスタンス内のブックマークの再開を追跡するために使用されるクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="60e35-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="60e35-104">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="60e35-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="60e35-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60e35-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>
  
<span data-ttu-id="60e35-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="60e35-106">\<system.serviceModel></span></span>  
<span data-ttu-id="60e35-107">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="60e35-107">\<tracking></span></span>  
<span data-ttu-id="60e35-108">\<プロファイル ></span><span class="sxs-lookup"><span data-stu-id="60e35-108">\<profiles></span></span>  
<span data-ttu-id="60e35-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="60e35-109">\<trackingProfile></span></span>  
<span data-ttu-id="60e35-110">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="60e35-110">\<workflow></span></span>  
<span data-ttu-id="60e35-111">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="60e35-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="60e35-112">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="60e35-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60e35-113">構文</span><span class="sxs-lookup"><span data-stu-id="60e35-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60e35-114">属性と要素</span><span class="sxs-lookup"><span data-stu-id="60e35-114">Attributes and elements</span></span>

<span data-ttu-id="60e35-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="60e35-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60e35-116">属性</span><span class="sxs-lookup"><span data-stu-id="60e35-116">Attributes</span></span>  
  
|<span data-ttu-id="60e35-117">属性</span><span class="sxs-lookup"><span data-stu-id="60e35-117">Attribute</span></span>|<span data-ttu-id="60e35-118">説明</span><span class="sxs-lookup"><span data-stu-id="60e35-118">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="60e35-119">定期受信するブックマーク レコードの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="60e35-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60e35-120">子要素</span><span class="sxs-lookup"><span data-stu-id="60e35-120">Child elements</span></span>

<span data-ttu-id="60e35-121">なし。</span><span class="sxs-lookup"><span data-stu-id="60e35-121">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="60e35-122">親要素</span><span class="sxs-lookup"><span data-stu-id="60e35-122">Parent elements</span></span>  
  
|<span data-ttu-id="60e35-123">要素</span><span class="sxs-lookup"><span data-stu-id="60e35-123">Element</span></span>|<span data-ttu-id="60e35-124">説明</span><span class="sxs-lookup"><span data-stu-id="60e35-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60e35-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="60e35-125">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="60e35-126">ワークフロー インスタンス内のブックマークの再開を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="60e35-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60e35-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="60e35-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="60e35-128">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="60e35-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="60e35-129">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="60e35-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
