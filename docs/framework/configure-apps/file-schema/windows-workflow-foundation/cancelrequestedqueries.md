---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 0d08612ce5d74f4f7f505c538187ddecea610132
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398823"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="89510-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="89510-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="89510-102">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="89510-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="89510-103">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="89510-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="89510-104">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89510-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="89510-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="89510-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="89510-106">&nbsp;&nbsp;[ **\<system.ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="89510-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="89510-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="89510-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="89510-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="89510-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="89510-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="89510-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="89510-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<cancelRequestedQueries >**</span><span class="sxs-lookup"><span data-stu-id="89510-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89510-111">構文</span><span class="sxs-lookup"><span data-stu-id="89510-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89510-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="89510-112">Attributes and Elements</span></span>  
 <span data-ttu-id="89510-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="89510-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89510-114">属性</span><span class="sxs-lookup"><span data-stu-id="89510-114">Attributes</span></span>  
 <span data-ttu-id="89510-115">なし。</span><span class="sxs-lookup"><span data-stu-id="89510-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="89510-116">子要素</span><span class="sxs-lookup"><span data-stu-id="89510-116">Child Elements</span></span>  
  
|<span data-ttu-id="89510-117">要素</span><span class="sxs-lookup"><span data-stu-id="89510-117">Element</span></span>|<span data-ttu-id="89510-118">説明</span><span class="sxs-lookup"><span data-stu-id="89510-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89510-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="89510-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery.md)|<span data-ttu-id="89510-120">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="89510-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="89510-121">親要素</span><span class="sxs-lookup"><span data-stu-id="89510-121">Parent Elements</span></span>  
  
|<span data-ttu-id="89510-122">要素</span><span class="sxs-lookup"><span data-stu-id="89510-122">Element</span></span>|<span data-ttu-id="89510-123">説明</span><span class="sxs-lookup"><span data-stu-id="89510-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89510-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="89510-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="89510-125">**ActivityDefinitionId**プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="89510-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="89510-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="89510-126">See also</span></span>

- [<span data-ttu-id="89510-127">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="89510-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="89510-128">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="89510-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
