---
title: <state> の <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
ms.openlocfilehash: 7c7326b2fd5ae39ca4c0f39fac05444802fa3d49
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947496"
---
# <a name="state-of-states"></a><span data-ttu-id="eaa64-102">\<状態 > \<></span><span class="sxs-lookup"><span data-stu-id="eaa64-102">\<state> of \<states></span></span>
<span data-ttu-id="eaa64-103">追跡レコードを生成する必要がある定期受信済みアクティビティの状態を含む構成要素。</span><span class="sxs-lookup"><span data-stu-id="eaa64-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="eaa64-104">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaa64-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="eaa64-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="eaa64-105">\<system.serviceModel></span></span>  
<span data-ttu-id="eaa64-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="eaa64-106">\<tracking></span></span>  
<span data-ttu-id="eaa64-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="eaa64-107">\<trackingProfile></span></span>  
<span data-ttu-id="eaa64-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="eaa64-108">\<workflow></span></span>  
<span data-ttu-id="eaa64-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="eaa64-109">\<activityStateQueries></span></span>  
<span data-ttu-id="eaa64-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="eaa64-110">\<activityStateQuery></span></span>  
<span data-ttu-id="eaa64-111">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="eaa64-111">\<states></span></span>  
<span data-ttu-id="eaa64-112">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="eaa64-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaa64-113">構文</span><span class="sxs-lookup"><span data-stu-id="eaa64-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eaa64-114">属性および要素</span><span class="sxs-lookup"><span data-stu-id="eaa64-114">Attributes and Elements</span></span>  
 <span data-ttu-id="eaa64-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="eaa64-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eaa64-116">属性</span><span class="sxs-lookup"><span data-stu-id="eaa64-116">Attributes</span></span>  
  
|<span data-ttu-id="eaa64-117">属性</span><span class="sxs-lookup"><span data-stu-id="eaa64-117">Attribute</span></span>|<span data-ttu-id="eaa64-118">説明</span><span class="sxs-lookup"><span data-stu-id="eaa64-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eaa64-119">name</span><span class="sxs-lookup"><span data-stu-id="eaa64-119">name</span></span>|<span data-ttu-id="eaa64-120">追跡レコードを生成する必要がある定期受信済みアクティビティの状態を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="eaa64-120">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eaa64-121">子要素</span><span class="sxs-lookup"><span data-stu-id="eaa64-121">Child Elements</span></span>  
 <span data-ttu-id="eaa64-122">なし。</span><span class="sxs-lookup"><span data-stu-id="eaa64-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eaa64-123">親要素</span><span class="sxs-lookup"><span data-stu-id="eaa64-123">Parent Elements</span></span>  
  
|<span data-ttu-id="eaa64-124">要素</span><span class="sxs-lookup"><span data-stu-id="eaa64-124">Element</span></span>|<span data-ttu-id="eaa64-125">説明</span><span class="sxs-lookup"><span data-stu-id="eaa64-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eaa64-126">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="eaa64-126">\<states></span></span>](states-of-activitystatequery.md)|<span data-ttu-id="eaa64-127">追跡レコードを生成する必要がある定期受信済みアクティビティの状態を含む構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="eaa64-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eaa64-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="eaa64-128">Remarks</span></span>  
 <span data-ttu-id="eaa64-129">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="eaa64-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="eaa64-130">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="eaa64-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="eaa64-131">引数 >、 [ \<](arguments.md) [ states\<>](states.md)および[ states>要素を使用して、ワークフロー内の任意の\<](states.md)アクティビティから任意の変数または引数を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="eaa64-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="eaa64-132">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="eaa64-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="eaa64-133">変数と引数は activitystaterecord でのみ抽出できるため、 [ \<activitystatequery >](activitystatequery.md)を使用して追跡プロファイル内でサブスクライブされます。</span><span class="sxs-lookup"><span data-stu-id="eaa64-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eaa64-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="eaa64-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="eaa64-135">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="eaa64-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="eaa64-136">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="eaa64-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
