---
title: <arguments>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: bb7ae702209df3c0297ec2cfac6b09ee47ad9558
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946128"
---
# <a name="arguments"></a><span data-ttu-id="42f4f-101">\<引数 ></span><span class="sxs-lookup"><span data-stu-id="42f4f-101">\<arguments></span></span>
<span data-ttu-id="42f4f-102">アクティビティ状態クエリに関連付けられている引数のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="42f4f-102">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="42f4f-103">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42f4f-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="42f4f-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="42f4f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="42f4f-105">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="42f4f-105">\<tracking></span></span>  
<span data-ttu-id="42f4f-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="42f4f-106">\<trackingProfile></span></span>  
<span data-ttu-id="42f4f-107">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="42f4f-107">\<workflow></span></span>  
<span data-ttu-id="42f4f-108">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="42f4f-108">\<activityStateQueries></span></span>  
<span data-ttu-id="42f4f-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="42f4f-109">\<activityStateQuery></span></span>  
<span data-ttu-id="42f4f-110">\<引数 ></span><span class="sxs-lookup"><span data-stu-id="42f4f-110">\<arguments></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42f4f-111">構文</span><span class="sxs-lookup"><span data-stu-id="42f4f-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42f4f-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="42f4f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="42f4f-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="42f4f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42f4f-114">属性</span><span class="sxs-lookup"><span data-stu-id="42f4f-114">Attributes</span></span>  
 <span data-ttu-id="42f4f-115">なし。</span><span class="sxs-lookup"><span data-stu-id="42f4f-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="42f4f-116">子要素</span><span class="sxs-lookup"><span data-stu-id="42f4f-116">Child Elements</span></span>  
  
|<span data-ttu-id="42f4f-117">要素</span><span class="sxs-lookup"><span data-stu-id="42f4f-117">Element</span></span>|<span data-ttu-id="42f4f-118">説明</span><span class="sxs-lookup"><span data-stu-id="42f4f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42f4f-119">\<引数 ></span><span class="sxs-lookup"><span data-stu-id="42f4f-119">\<argument></span></span>](argument.md)|<span data-ttu-id="42f4f-120">アクティビティ状態クエリに関連付けられている引数。</span><span class="sxs-lookup"><span data-stu-id="42f4f-120">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="42f4f-121">親要素</span><span class="sxs-lookup"><span data-stu-id="42f4f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="42f4f-122">要素</span><span class="sxs-lookup"><span data-stu-id="42f4f-122">Element</span></span>|<span data-ttu-id="42f4f-123">説明</span><span class="sxs-lookup"><span data-stu-id="42f4f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42f4f-124">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="42f4f-124">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="42f4f-125">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="42f4f-125">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="42f4f-126">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="42f4f-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42f4f-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="42f4f-127">Remarks</span></span>  
 <span data-ttu-id="42f4f-128">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="42f4f-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="42f4f-129">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="42f4f-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="42f4f-130">引数 >、 [ \<](arguments.md) [ states\<>](states.md)および[ states>要素を使用して、ワークフロー内の任意の\<](states.md)アクティビティから任意の変数または引数を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="42f4f-130">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="42f4f-131">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="42f4f-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="42f4f-132">変数と引数は activitystaterecord でのみ抽出できるため、 [ \<activitystatequery >](activitystatequery.md)を使用して追跡プロファイル内でサブスクライブされます。</span><span class="sxs-lookup"><span data-stu-id="42f4f-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="42f4f-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="42f4f-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="42f4f-134">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="42f4f-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="42f4f-135">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="42f4f-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
