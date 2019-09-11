---
title: <bookmarkResumptionQueries>WCF の
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 94ff9f44f295b45c03e1bd8f52a85d6b7b0c6e3b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850127"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="acb17-102">\<WCF の bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="acb17-102">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="acb17-103">ワークフロー インスタンス内のブックマークの再開を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="acb17-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="acb17-104">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="acb17-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="acb17-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acb17-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="acb17-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="acb17-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="acb17-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="acb17-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="acb17-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="acb17-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="acb17-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<プロファイル >** </span><span class="sxs-lookup"><span data-stu-id="acb17-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="acb17-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="acb17-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="acb17-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="acb17-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="acb17-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<bookmarkResumptionQueries >**</span><span class="sxs-lookup"><span data-stu-id="acb17-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="acb17-113">構文</span><span class="sxs-lookup"><span data-stu-id="acb17-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="acb17-114">属性と要素</span><span class="sxs-lookup"><span data-stu-id="acb17-114">Attributes and elements</span></span>  
  
<span data-ttu-id="acb17-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="acb17-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="acb17-116">属性</span><span class="sxs-lookup"><span data-stu-id="acb17-116">Attributes</span></span>  
  
<span data-ttu-id="acb17-117">なし。</span><span class="sxs-lookup"><span data-stu-id="acb17-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="acb17-118">子要素</span><span class="sxs-lookup"><span data-stu-id="acb17-118">Child elements</span></span>  
  
|<span data-ttu-id="acb17-119">要素</span><span class="sxs-lookup"><span data-stu-id="acb17-119">Element</span></span>|<span data-ttu-id="acb17-120">説明</span><span class="sxs-lookup"><span data-stu-id="acb17-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="acb17-121">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="acb17-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="acb17-122">ワークフロー インスタンス内のブックマークの再開を追跡するために使用されるクエリ。</span><span class="sxs-lookup"><span data-stu-id="acb17-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="acb17-123">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="acb17-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="acb17-124">親要素</span><span class="sxs-lookup"><span data-stu-id="acb17-124">Parent elements</span></span>  
  
|<span data-ttu-id="acb17-125">要素</span><span class="sxs-lookup"><span data-stu-id="acb17-125">Element</span></span>|<span data-ttu-id="acb17-126">説明</span><span class="sxs-lookup"><span data-stu-id="acb17-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="acb17-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="acb17-127">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="acb17-128">`activityDefinitionId` プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="acb17-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="acb17-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="acb17-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="acb17-130">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="acb17-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="acb17-131">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="acb17-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
