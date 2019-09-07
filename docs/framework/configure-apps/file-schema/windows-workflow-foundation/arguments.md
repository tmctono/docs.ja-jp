---
title: <arguments>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: f06a2188ea3561437c1453d3a1cb23d42d767f53
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398910"
---
# <a name="arguments"></a><span data-ttu-id="4227f-101">\<引数 ></span><span class="sxs-lookup"><span data-stu-id="4227f-101">\<arguments></span></span>
<span data-ttu-id="4227f-102">アクティビティ状態クエリに関連付けられている引数のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="4227f-102">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="4227f-103">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4227f-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="4227f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4227f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4227f-105">&nbsp;&nbsp;[ **\<system.ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="4227f-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="4227f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="4227f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="4227f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="4227f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="4227f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="4227f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="4227f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityStateQueries >** ](activitystatequeries.md)</span><span class="sxs-lookup"><span data-stu-id="4227f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)</span></span>\
<span data-ttu-id="4227f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityStateQuery >** ](activitystatequery.md)</span><span class="sxs-lookup"><span data-stu-id="4227f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)</span></span>\
<span data-ttu-id="4227f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<引数 >**</span><span class="sxs-lookup"><span data-stu-id="4227f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<arguments>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4227f-112">構文</span><span class="sxs-lookup"><span data-stu-id="4227f-112">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4227f-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4227f-113">Attributes and Elements</span></span>  
 <span data-ttu-id="4227f-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4227f-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4227f-115">属性</span><span class="sxs-lookup"><span data-stu-id="4227f-115">Attributes</span></span>  
 <span data-ttu-id="4227f-116">なし。</span><span class="sxs-lookup"><span data-stu-id="4227f-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4227f-117">子要素</span><span class="sxs-lookup"><span data-stu-id="4227f-117">Child Elements</span></span>  
  
|<span data-ttu-id="4227f-118">要素</span><span class="sxs-lookup"><span data-stu-id="4227f-118">Element</span></span>|<span data-ttu-id="4227f-119">説明</span><span class="sxs-lookup"><span data-stu-id="4227f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4227f-120">\<引数 ></span><span class="sxs-lookup"><span data-stu-id="4227f-120">\<argument></span></span>](argument.md)|<span data-ttu-id="4227f-121">アクティビティ状態クエリに関連付けられている引数。</span><span class="sxs-lookup"><span data-stu-id="4227f-121">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4227f-122">親要素</span><span class="sxs-lookup"><span data-stu-id="4227f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4227f-123">要素</span><span class="sxs-lookup"><span data-stu-id="4227f-123">Element</span></span>|<span data-ttu-id="4227f-124">説明</span><span class="sxs-lookup"><span data-stu-id="4227f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4227f-125">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="4227f-125">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="4227f-126">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="4227f-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="4227f-127">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="4227f-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4227f-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="4227f-128">Remarks</span></span>  
 <span data-ttu-id="4227f-129">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="4227f-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="4227f-130">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="4227f-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="4227f-131">引数 >、 [ \<](arguments.md) [ states\<>](states.md)および[ states>要素を使用して、ワークフロー内の任意の\<](states.md)アクティビティから任意の変数または引数を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="4227f-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="4227f-132">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="4227f-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="4227f-133">変数と引数は activitystaterecord でのみ抽出できるため、 [ \<activitystatequery >](activitystatequery.md)を使用して追跡プロファイル内でサブスクライブされます。</span><span class="sxs-lookup"><span data-stu-id="4227f-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4227f-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="4227f-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4227f-135">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="4227f-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4227f-136">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="4227f-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
