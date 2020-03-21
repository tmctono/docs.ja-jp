---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 3e6840ce647625c36356cccd4651f17de32777e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152288"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="0cd7c-101">\<キャンセル要求されたクエリ></span><span class="sxs-lookup"><span data-stu-id="0cd7c-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="0cd7c-102">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用するクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="0cd7c-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="0cd7c-103">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="0cd7c-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="0cd7c-104">プロファイル クエリの追跡の詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cd7c-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="0cd7c-105">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0cd7c-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0cd7c-106">&nbsp;&nbsp;[**\<システム。サービスモデル>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="0cd7c-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="0cd7c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<追跡>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="0cd7c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="0cd7c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<追跡プロファイル>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="0cd7c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="0cd7c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ワークフロー>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="0cd7c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="0cd7c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>要求されたクエリをキャンセルします。**](cancelrequestedqueries.md)</span><span class="sxs-lookup"><span data-stu-id="0cd7c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)</span></span>\
<span data-ttu-id="0cd7c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<キャンセル要求されたクエリ>**</span><span class="sxs-lookup"><span data-stu-id="0cd7c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cd7c-112">構文</span><span class="sxs-lookup"><span data-stu-id="0cd7c-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0cd7c-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0cd7c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0cd7c-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0cd7c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0cd7c-115">属性</span><span class="sxs-lookup"><span data-stu-id="0cd7c-115">Attributes</span></span>  
  
|<span data-ttu-id="0cd7c-116">属性</span><span class="sxs-lookup"><span data-stu-id="0cd7c-116">Attribute</span></span>|<span data-ttu-id="0cd7c-117">説明</span><span class="sxs-lookup"><span data-stu-id="0cd7c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0cd7c-118">activityName</span><span class="sxs-lookup"><span data-stu-id="0cd7c-118">activityName</span></span>|<span data-ttu-id="0cd7c-119">キャンセルを要求しているアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="0cd7c-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="0cd7c-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="0cd7c-120">childActivityName</span></span>|<span data-ttu-id="0cd7c-121">キャンセルが要求された子アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="0cd7c-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0cd7c-122">子要素</span><span class="sxs-lookup"><span data-stu-id="0cd7c-122">Child Elements</span></span>  
 <span data-ttu-id="0cd7c-123">[なし] :</span><span class="sxs-lookup"><span data-stu-id="0cd7c-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0cd7c-124">親要素</span><span class="sxs-lookup"><span data-stu-id="0cd7c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="0cd7c-125">要素</span><span class="sxs-lookup"><span data-stu-id="0cd7c-125">Element</span></span>|<span data-ttu-id="0cd7c-126">説明</span><span class="sxs-lookup"><span data-stu-id="0cd7c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0cd7c-127">\<フォルト伝播クエリ></span><span class="sxs-lookup"><span data-stu-id="0cd7c-127">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="0cd7c-128">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する構成要素の一覧を表します。</span><span class="sxs-lookup"><span data-stu-id="0cd7c-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="0cd7c-129">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="0cd7c-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0cd7c-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="0cd7c-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0cd7c-131">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="0cd7c-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0cd7c-132">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="0cd7c-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
