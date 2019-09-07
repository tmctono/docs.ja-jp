---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 5de459717fdc0dbf946f12dceda18dce79ca4b06
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398813"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="1e0e0-101">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="1e0e0-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="1e0e0-102">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用するクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="1e0e0-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="1e0e0-103">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="1e0e0-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="1e0e0-104">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e0e0-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="1e0e0-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1e0e0-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1e0e0-106">&nbsp;&nbsp;[ **\<system.ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1e0e0-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="1e0e0-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="1e0e0-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="1e0e0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="1e0e0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="1e0e0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1e0e0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="1e0e0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cancelRequestedQueries >** ](cancelrequestedqueries.md)</span><span class="sxs-lookup"><span data-stu-id="1e0e0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)</span></span>\
<span data-ttu-id="1e0e0-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<cancelRequestedQuery >**</span><span class="sxs-lookup"><span data-stu-id="1e0e0-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e0e0-112">構文</span><span class="sxs-lookup"><span data-stu-id="1e0e0-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e0e0-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1e0e0-113">Attributes and Elements</span></span>  
 <span data-ttu-id="1e0e0-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1e0e0-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e0e0-115">属性</span><span class="sxs-lookup"><span data-stu-id="1e0e0-115">Attributes</span></span>  
  
|<span data-ttu-id="1e0e0-116">属性</span><span class="sxs-lookup"><span data-stu-id="1e0e0-116">Attribute</span></span>|<span data-ttu-id="1e0e0-117">説明</span><span class="sxs-lookup"><span data-stu-id="1e0e0-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1e0e0-118">activityName</span><span class="sxs-lookup"><span data-stu-id="1e0e0-118">activityName</span></span>|<span data-ttu-id="1e0e0-119">キャンセルを要求しているアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="1e0e0-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="1e0e0-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="1e0e0-120">childActivityName</span></span>|<span data-ttu-id="1e0e0-121">キャンセルが要求された子アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="1e0e0-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e0e0-122">子要素</span><span class="sxs-lookup"><span data-stu-id="1e0e0-122">Child Elements</span></span>  
 <span data-ttu-id="1e0e0-123">なし。</span><span class="sxs-lookup"><span data-stu-id="1e0e0-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1e0e0-124">親要素</span><span class="sxs-lookup"><span data-stu-id="1e0e0-124">Parent Elements</span></span>  
  
|<span data-ttu-id="1e0e0-125">要素</span><span class="sxs-lookup"><span data-stu-id="1e0e0-125">Element</span></span>|<span data-ttu-id="1e0e0-126">説明</span><span class="sxs-lookup"><span data-stu-id="1e0e0-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e0e0-127">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="1e0e0-127">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="1e0e0-128">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する構成要素の一覧を表します。</span><span class="sxs-lookup"><span data-stu-id="1e0e0-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="1e0e0-129">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="1e0e0-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1e0e0-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e0e0-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1e0e0-131">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="1e0e0-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1e0e0-132">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="1e0e0-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
