---
title: <cancelRequestedQueries>WCF の
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 63cfc835ac7ce88bde56fd9243a2cf6652cbce6e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850096"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="5db00-102">\<WCF の cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="5db00-102">\<cancelRequestedQueries> of WCF</span></span>
<span data-ttu-id="5db00-103">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="5db00-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="5db00-104">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="5db00-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="5db00-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5db00-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="5db00-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5db00-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5db00-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5db00-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5db00-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="5db00-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="5db00-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<プロファイル >** </span><span class="sxs-lookup"><span data-stu-id="5db00-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="5db00-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="5db00-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="5db00-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="5db00-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="5db00-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<cancelRequestedQueries >**</span><span class="sxs-lookup"><span data-stu-id="5db00-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5db00-113">構文</span><span class="sxs-lookup"><span data-stu-id="5db00-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String" />
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5db00-114">属性と要素</span><span class="sxs-lookup"><span data-stu-id="5db00-114">Attributes and elements</span></span>  

<span data-ttu-id="5db00-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5db00-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5db00-116">属性</span><span class="sxs-lookup"><span data-stu-id="5db00-116">Attributes</span></span>

<span data-ttu-id="5db00-117">なし。</span><span class="sxs-lookup"><span data-stu-id="5db00-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="5db00-118">子要素</span><span class="sxs-lookup"><span data-stu-id="5db00-118">Child elements</span></span>
  
|<span data-ttu-id="5db00-119">要素</span><span class="sxs-lookup"><span data-stu-id="5db00-119">Element</span></span>|<span data-ttu-id="5db00-120">説明</span><span class="sxs-lookup"><span data-stu-id="5db00-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5db00-121">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="5db00-121">\<cancelRequestedQuery></span></span>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="5db00-122">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="5db00-122">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5db00-123">親要素</span><span class="sxs-lookup"><span data-stu-id="5db00-123">Parent elements</span></span>  
  
|<span data-ttu-id="5db00-124">要素</span><span class="sxs-lookup"><span data-stu-id="5db00-124">Element</span></span>|<span data-ttu-id="5db00-125">説明</span><span class="sxs-lookup"><span data-stu-id="5db00-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5db00-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="5db00-126">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="5db00-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="5db00-127">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5db00-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="5db00-128">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="5db00-129">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="5db00-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5db00-130">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="5db00-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
