---
title: <states> の <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7cc2018-2b79-44f1-825a-bb7ca08690a3
ms.openlocfilehash: fa3736fc13f6f40f52d15b8257b7a79f4179d738
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189600"
---
# <a name="states-of-activitystatequery"></a><span data-ttu-id="e1133-102">\<状態 > の\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="e1133-102">\<states> of \<activityStateQuery></span></span>
<span data-ttu-id="e1133-103">追跡レコードを生成する必要がある定期受信済みアクティビティの状態を含む構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="e1133-103">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="e1133-104">追跡プロファイルのクエリの詳細については、次を参照してください。[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)します。</span><span class="sxs-lookup"><span data-stu-id="e1133-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="e1133-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e1133-105">\<system.serviceModel></span></span>  
<span data-ttu-id="e1133-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="e1133-106">\<tracking></span></span>  
<span data-ttu-id="e1133-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="e1133-107">\<trackingProfile></span></span>  
<span data-ttu-id="e1133-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="e1133-108">\<workflow></span></span>  
<span data-ttu-id="e1133-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="e1133-109">\<activityStateQueries></span></span>  
<span data-ttu-id="e1133-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="e1133-110">\<activityStateQuery></span></span>  
<span data-ttu-id="e1133-111">\<states></span><span class="sxs-lookup"><span data-stu-id="e1133-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1133-112">構文</span><span class="sxs-lookup"><span data-stu-id="e1133-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1133-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e1133-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e1133-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e1133-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1133-115">属性</span><span class="sxs-lookup"><span data-stu-id="e1133-115">Attributes</span></span>  
 <span data-ttu-id="e1133-116">なし。</span><span class="sxs-lookup"><span data-stu-id="e1133-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e1133-117">子要素</span><span class="sxs-lookup"><span data-stu-id="e1133-117">Child Elements</span></span>  
  
|<span data-ttu-id="e1133-118">要素</span><span class="sxs-lookup"><span data-stu-id="e1133-118">Element</span></span>|<span data-ttu-id="e1133-119">説明</span><span class="sxs-lookup"><span data-stu-id="e1133-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1133-120">\<state></span><span class="sxs-lookup"><span data-stu-id="e1133-120">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/state-of-states.md)|<span data-ttu-id="e1133-121">追跡レコードを生成する必要がある定期受信済みアクティビティの状態を含む構成要素。</span><span class="sxs-lookup"><span data-stu-id="e1133-121">A configuration element that contains the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e1133-122">親要素</span><span class="sxs-lookup"><span data-stu-id="e1133-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e1133-123">要素</span><span class="sxs-lookup"><span data-stu-id="e1133-123">Element</span></span>|<span data-ttu-id="e1133-124">説明</span><span class="sxs-lookup"><span data-stu-id="e1133-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1133-125">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="e1133-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="e1133-126">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="e1133-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="e1133-127">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="e1133-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1133-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="e1133-128">Remarks</span></span>  
 <span data-ttu-id="e1133-129">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="e1133-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="e1133-130">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="e1133-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="e1133-131">使用することができます、 [\<引数 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)、 [\<状態 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)と[\<状態 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)任意の変数または引数を抽出する要素ワークフロー内の任意のアクティビティから</span><span class="sxs-lookup"><span data-stu-id="e1133-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="e1133-132">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="e1133-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="e1133-133">ActivityStateRecord でのみ抽出できるし、追跡のため購読中の変数と引数を使用してプロファイル[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)します。</span><span class="sxs-lookup"><span data-stu-id="e1133-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e1133-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1133-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e1133-135">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="e1133-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e1133-136">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="e1133-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
