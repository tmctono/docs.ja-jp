---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: 563e0cbd3f50887e1c9e3d47a3c9502acc13b2c9
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398869"
---
# <a name="bookmarkresumptionqueries"></a><span data-ttu-id="2b4b0-101">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="2b4b0-101">\<bookmarkResumptionQueries></span></span>
<span data-ttu-id="2b4b0-102">ワークフロー インスタンス内のブックマークの再開を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="2b4b0-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="2b4b0-103">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="2b4b0-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="2b4b0-104">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b4b0-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="2b4b0-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2b4b0-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2b4b0-106">&nbsp;&nbsp;[ **\<system.ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="2b4b0-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="2b4b0-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="2b4b0-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="2b4b0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="2b4b0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="2b4b0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="2b4b0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="2b4b0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<bookmarkResumptionQueries >**</span><span class="sxs-lookup"><span data-stu-id="2b4b0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="2b4b0-111">構文</span><span class="sxs-lookup"><span data-stu-id="2b4b0-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b4b0-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2b4b0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2b4b0-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2b4b0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b4b0-114">属性</span><span class="sxs-lookup"><span data-stu-id="2b4b0-114">Attributes</span></span>  
 <span data-ttu-id="2b4b0-115">なし。</span><span class="sxs-lookup"><span data-stu-id="2b4b0-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2b4b0-116">子要素</span><span class="sxs-lookup"><span data-stu-id="2b4b0-116">Child Elements</span></span>  
  
|<span data-ttu-id="2b4b0-117">要素</span><span class="sxs-lookup"><span data-stu-id="2b4b0-117">Element</span></span>|<span data-ttu-id="2b4b0-118">説明</span><span class="sxs-lookup"><span data-stu-id="2b4b0-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b4b0-119">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="2b4b0-119">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery.md)|<span data-ttu-id="2b4b0-120">ワークフロー インスタンス内のブックマークの再開を追跡するために使用されるクエリ。</span><span class="sxs-lookup"><span data-stu-id="2b4b0-120">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="2b4b0-121">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="2b4b0-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2b4b0-122">親要素</span><span class="sxs-lookup"><span data-stu-id="2b4b0-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2b4b0-123">要素</span><span class="sxs-lookup"><span data-stu-id="2b4b0-123">Element</span></span>|<span data-ttu-id="2b4b0-124">説明</span><span class="sxs-lookup"><span data-stu-id="2b4b0-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b4b0-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="2b4b0-125">\<workflow></span></span>](workflow.md)|<span data-ttu-id="2b4b0-126">**ActivityDefinitionId**プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="2b4b0-126">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2b4b0-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b4b0-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2b4b0-128">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="2b4b0-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2b4b0-129">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="2b4b0-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
