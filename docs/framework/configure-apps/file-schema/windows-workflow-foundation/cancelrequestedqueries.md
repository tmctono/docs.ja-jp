---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 89297b3a7d64f4300a735d8512230d441836c634
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152308"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="c15a2-101">\<キャンセル要求されたクエリ></span><span class="sxs-lookup"><span data-stu-id="c15a2-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="c15a2-102">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="c15a2-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="c15a2-103">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="c15a2-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="c15a2-104">プロファイル クエリの追跡の詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c15a2-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="c15a2-105">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c15a2-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c15a2-106">&nbsp;&nbsp;[**\<システム。サービスモデル>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="c15a2-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="c15a2-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<追跡>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="c15a2-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="c15a2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<追跡プロファイル>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="c15a2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="c15a2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ワークフロー>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="c15a2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="c15a2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>要求されたクエリをキャンセルします。**</span><span class="sxs-lookup"><span data-stu-id="c15a2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c15a2-111">構文</span><span class="sxs-lookup"><span data-stu-id="c15a2-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c15a2-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c15a2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c15a2-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c15a2-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c15a2-114">属性</span><span class="sxs-lookup"><span data-stu-id="c15a2-114">Attributes</span></span>  
 <span data-ttu-id="c15a2-115">[なし] :</span><span class="sxs-lookup"><span data-stu-id="c15a2-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c15a2-116">子要素</span><span class="sxs-lookup"><span data-stu-id="c15a2-116">Child Elements</span></span>  
  
|<span data-ttu-id="c15a2-117">要素</span><span class="sxs-lookup"><span data-stu-id="c15a2-117">Element</span></span>|<span data-ttu-id="c15a2-118">説明</span><span class="sxs-lookup"><span data-stu-id="c15a2-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c15a2-119">\<キャンセル要求されたクエリ></span><span class="sxs-lookup"><span data-stu-id="c15a2-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery.md)|<span data-ttu-id="c15a2-120">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="c15a2-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c15a2-121">親要素</span><span class="sxs-lookup"><span data-stu-id="c15a2-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c15a2-122">要素</span><span class="sxs-lookup"><span data-stu-id="c15a2-122">Element</span></span>|<span data-ttu-id="c15a2-123">説明</span><span class="sxs-lookup"><span data-stu-id="c15a2-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c15a2-124">\<ワークフロー></span><span class="sxs-lookup"><span data-stu-id="c15a2-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="c15a2-125">**activityDefinitionId**プロパティによって識別される特定のワークフローのすべてのクエリを含む構成要素。</span><span class="sxs-lookup"><span data-stu-id="c15a2-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c15a2-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="c15a2-126">See also</span></span>

- [<span data-ttu-id="c15a2-127">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="c15a2-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c15a2-128">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="c15a2-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
