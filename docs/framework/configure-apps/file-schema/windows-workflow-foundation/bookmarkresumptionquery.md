---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: b2a81a42a17474bdb0124bec6d3c3eeefa514411
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398846"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="b37ef-101">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="b37ef-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="b37ef-102">ワークフロー インスタンス内のブックマークの再開を追跡するために使用されるクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="b37ef-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="b37ef-103">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="b37ef-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="b37ef-104">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b37ef-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b37ef-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b37ef-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b37ef-106">&nbsp;&nbsp;[ **\<system.ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b37ef-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="b37ef-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="b37ef-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="b37ef-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="b37ef-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="b37ef-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b37ef-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="b37ef-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bookmarkResumptionQueries >** ](bookmarkresumptionqueries.md)</span><span class="sxs-lookup"><span data-stu-id="b37ef-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries.md)</span></span>\
<span data-ttu-id="b37ef-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<bookmarkResumptionQuery >**</span><span class="sxs-lookup"><span data-stu-id="b37ef-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b37ef-112">構文</span><span class="sxs-lookup"><span data-stu-id="b37ef-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b37ef-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b37ef-113">Attributes and Elements</span></span>  
 <span data-ttu-id="b37ef-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b37ef-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b37ef-115">属性</span><span class="sxs-lookup"><span data-stu-id="b37ef-115">Attributes</span></span>  
  
|<span data-ttu-id="b37ef-116">属性</span><span class="sxs-lookup"><span data-stu-id="b37ef-116">Attribute</span></span>|<span data-ttu-id="b37ef-117">説明</span><span class="sxs-lookup"><span data-stu-id="b37ef-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b37ef-118">name</span><span class="sxs-lookup"><span data-stu-id="b37ef-118">name</span></span>|<span data-ttu-id="b37ef-119">定期受信するブックマーク レコードの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="b37ef-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b37ef-120">子要素</span><span class="sxs-lookup"><span data-stu-id="b37ef-120">Child Elements</span></span>  
 <span data-ttu-id="b37ef-121">なし。</span><span class="sxs-lookup"><span data-stu-id="b37ef-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b37ef-122">親要素</span><span class="sxs-lookup"><span data-stu-id="b37ef-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b37ef-123">要素</span><span class="sxs-lookup"><span data-stu-id="b37ef-123">Element</span></span>|<span data-ttu-id="b37ef-124">説明</span><span class="sxs-lookup"><span data-stu-id="b37ef-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b37ef-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="b37ef-125">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries.md)|<span data-ttu-id="b37ef-126">ワークフロー インスタンス内のブックマークの再開を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="b37ef-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b37ef-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="b37ef-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b37ef-128">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="b37ef-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b37ef-129">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="b37ef-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
