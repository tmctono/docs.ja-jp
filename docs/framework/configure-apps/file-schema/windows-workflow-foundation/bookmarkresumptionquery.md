---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: 9043deb66e1a4314df97f4da41103e74676a270c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945953"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="448de-101">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="448de-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="448de-102">ワークフロー インスタンス内のブックマークの再開を追跡するために使用されるクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="448de-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="448de-103">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="448de-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="448de-104">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="448de-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="448de-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="448de-105">\<system.serviceModel></span></span>  
<span data-ttu-id="448de-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="448de-106">\<tracking></span></span>  
<span data-ttu-id="448de-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="448de-107">\<trackingProfile></span></span>  
<span data-ttu-id="448de-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="448de-108">\<workflow></span></span>  
<span data-ttu-id="448de-109">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="448de-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="448de-110">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="448de-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="448de-111">構文</span><span class="sxs-lookup"><span data-stu-id="448de-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <bookmarkResumptionQueries>
        <bookmarkResumptionQuery name="String" />
      </bookmarkResumptionQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="448de-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="448de-112">Attributes and Elements</span></span>  
 <span data-ttu-id="448de-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="448de-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="448de-114">属性</span><span class="sxs-lookup"><span data-stu-id="448de-114">Attributes</span></span>  
  
|<span data-ttu-id="448de-115">属性</span><span class="sxs-lookup"><span data-stu-id="448de-115">Attribute</span></span>|<span data-ttu-id="448de-116">説明</span><span class="sxs-lookup"><span data-stu-id="448de-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="448de-117">name</span><span class="sxs-lookup"><span data-stu-id="448de-117">name</span></span>|<span data-ttu-id="448de-118">定期受信するブックマーク レコードの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="448de-118">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="448de-119">子要素</span><span class="sxs-lookup"><span data-stu-id="448de-119">Child Elements</span></span>  
 <span data-ttu-id="448de-120">なし。</span><span class="sxs-lookup"><span data-stu-id="448de-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="448de-121">親要素</span><span class="sxs-lookup"><span data-stu-id="448de-121">Parent Elements</span></span>  
  
|<span data-ttu-id="448de-122">要素</span><span class="sxs-lookup"><span data-stu-id="448de-122">Element</span></span>|<span data-ttu-id="448de-123">説明</span><span class="sxs-lookup"><span data-stu-id="448de-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="448de-124">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="448de-124">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries.md)|<span data-ttu-id="448de-125">ワークフロー インスタンス内のブックマークの再開を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="448de-125">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="448de-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="448de-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="448de-127">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="448de-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="448de-128">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="448de-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
