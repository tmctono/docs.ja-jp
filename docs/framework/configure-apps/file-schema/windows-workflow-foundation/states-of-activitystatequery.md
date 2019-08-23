---
title: <states> の <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7cc2018-2b79-44f1-825a-bb7ca08690a3
ms.openlocfilehash: 50827577374859133e6c673e8850e145b4ccab73
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947426"
---
# <a name="states-of-activitystatequery"></a><span data-ttu-id="d9327-102">\<activitystatequery \<> の状態 ></span><span class="sxs-lookup"><span data-stu-id="d9327-102">\<states> of \<activityStateQuery></span></span>
<span data-ttu-id="d9327-103">追跡レコードを生成する必要がある定期受信済みアクティビティの状態を含む構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="d9327-103">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="d9327-104">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9327-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="d9327-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d9327-105">\<system.serviceModel></span></span>  
<span data-ttu-id="d9327-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="d9327-106">\<tracking></span></span>  
<span data-ttu-id="d9327-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d9327-107">\<trackingProfile></span></span>  
<span data-ttu-id="d9327-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="d9327-108">\<workflow></span></span>  
<span data-ttu-id="d9327-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="d9327-109">\<activityStateQueries></span></span>  
<span data-ttu-id="d9327-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="d9327-110">\<activityStateQuery></span></span>  
<span data-ttu-id="d9327-111">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="d9327-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9327-112">構文</span><span class="sxs-lookup"><span data-stu-id="d9327-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <states>
          <state name="String" />
        </states>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9327-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d9327-113">Attributes and Elements</span></span>  
 <span data-ttu-id="d9327-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d9327-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9327-115">属性</span><span class="sxs-lookup"><span data-stu-id="d9327-115">Attributes</span></span>  
 <span data-ttu-id="d9327-116">なし。</span><span class="sxs-lookup"><span data-stu-id="d9327-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d9327-117">子要素</span><span class="sxs-lookup"><span data-stu-id="d9327-117">Child Elements</span></span>  
  
|<span data-ttu-id="d9327-118">要素</span><span class="sxs-lookup"><span data-stu-id="d9327-118">Element</span></span>|<span data-ttu-id="d9327-119">説明</span><span class="sxs-lookup"><span data-stu-id="d9327-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9327-120">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="d9327-120">\<state></span></span>](state-of-states.md)|<span data-ttu-id="d9327-121">追跡レコードを生成する必要がある定期受信済みアクティビティの状態を含む構成要素。</span><span class="sxs-lookup"><span data-stu-id="d9327-121">A configuration element that contains the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d9327-122">親要素</span><span class="sxs-lookup"><span data-stu-id="d9327-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d9327-123">要素</span><span class="sxs-lookup"><span data-stu-id="d9327-123">Element</span></span>|<span data-ttu-id="d9327-124">説明</span><span class="sxs-lookup"><span data-stu-id="d9327-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9327-125">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="d9327-125">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="d9327-126">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="d9327-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="d9327-127">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="d9327-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9327-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="d9327-128">Remarks</span></span>  
 <span data-ttu-id="d9327-129">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="d9327-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="d9327-130">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="d9327-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="d9327-131">引数 >、 [ \<](arguments.md) [ states\<>](states.md)および[ states>要素を使用して、ワークフロー内の任意の\<](states.md)アクティビティから任意の変数または引数を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="d9327-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="d9327-132">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="d9327-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="d9327-133">変数と引数は activitystaterecord でのみ抽出できるため、 [ \<activitystatequery >](activitystatequery.md)を使用して追跡プロファイル内でサブスクライブされます。</span><span class="sxs-lookup"><span data-stu-id="d9327-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d9327-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9327-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d9327-135">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="d9327-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d9327-136">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="d9327-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
