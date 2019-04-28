---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: e43ba66e2c3ccfbb723b1eea8ef6774ad3f9f2aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790274"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="85e49-101">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="85e49-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="85e49-102">ワークフロー インスタンス内のブックマークの再開を追跡するために使用されるクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="85e49-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="85e49-103">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="85e49-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="85e49-104">追跡プロファイルのクエリの詳細については、次を参照してください[追跡プロファイル。](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="85e49-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="85e49-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="85e49-105">\<system.serviceModel></span></span>  
<span data-ttu-id="85e49-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="85e49-106">\<tracking></span></span>  
<span data-ttu-id="85e49-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="85e49-107">\<trackingProfile></span></span>  
<span data-ttu-id="85e49-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="85e49-108">\<workflow></span></span>  
<span data-ttu-id="85e49-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="85e49-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="85e49-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="85e49-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85e49-111">構文</span><span class="sxs-lookup"><span data-stu-id="85e49-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85e49-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="85e49-112">Attributes and Elements</span></span>  
 <span data-ttu-id="85e49-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="85e49-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85e49-114">属性</span><span class="sxs-lookup"><span data-stu-id="85e49-114">Attributes</span></span>  
  
|<span data-ttu-id="85e49-115">属性</span><span class="sxs-lookup"><span data-stu-id="85e49-115">Attribute</span></span>|<span data-ttu-id="85e49-116">説明</span><span class="sxs-lookup"><span data-stu-id="85e49-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="85e49-117">name</span><span class="sxs-lookup"><span data-stu-id="85e49-117">name</span></span>|<span data-ttu-id="85e49-118">定期受信するブックマーク レコードの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="85e49-118">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85e49-119">子要素</span><span class="sxs-lookup"><span data-stu-id="85e49-119">Child Elements</span></span>  
 <span data-ttu-id="85e49-120">なし。</span><span class="sxs-lookup"><span data-stu-id="85e49-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85e49-121">親要素</span><span class="sxs-lookup"><span data-stu-id="85e49-121">Parent Elements</span></span>  
  
|<span data-ttu-id="85e49-122">要素</span><span class="sxs-lookup"><span data-stu-id="85e49-122">Element</span></span>|<span data-ttu-id="85e49-123">説明</span><span class="sxs-lookup"><span data-stu-id="85e49-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85e49-124">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="85e49-124">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="85e49-125">ワークフロー インスタンス内のブックマークの再開を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="85e49-125">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85e49-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="85e49-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="85e49-127">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="85e49-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="85e49-128">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="85e49-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
