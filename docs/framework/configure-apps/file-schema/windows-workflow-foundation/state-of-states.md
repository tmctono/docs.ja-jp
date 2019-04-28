---
title: <state> の <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
ms.openlocfilehash: ff75895949c50cd369e4297ea77dc21106994067
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794410"
---
# <a name="state-of-states"></a><span data-ttu-id="86b91-102">\<状態 > の\<状態 ></span><span class="sxs-lookup"><span data-stu-id="86b91-102">\<state> of \<states></span></span>
<span data-ttu-id="86b91-103">追跡レコードを生成する必要がある定期受信済みアクティビティの状態を含む構成要素。</span><span class="sxs-lookup"><span data-stu-id="86b91-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="86b91-104">追跡プロファイルのクエリの詳細については、次を参照してください。[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)します。</span><span class="sxs-lookup"><span data-stu-id="86b91-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="86b91-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="86b91-105">\<system.serviceModel></span></span>  
<span data-ttu-id="86b91-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="86b91-106">\<tracking></span></span>  
<span data-ttu-id="86b91-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="86b91-107">\<trackingProfile></span></span>  
<span data-ttu-id="86b91-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="86b91-108">\<workflow></span></span>  
<span data-ttu-id="86b91-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="86b91-109">\<activityStateQueries></span></span>  
<span data-ttu-id="86b91-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="86b91-110">\<activityStateQuery></span></span>  
<span data-ttu-id="86b91-111">\<states></span><span class="sxs-lookup"><span data-stu-id="86b91-111">\<states></span></span>  
<span data-ttu-id="86b91-112">\<state></span><span class="sxs-lookup"><span data-stu-id="86b91-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86b91-113">構文</span><span class="sxs-lookup"><span data-stu-id="86b91-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86b91-114">属性および要素</span><span class="sxs-lookup"><span data-stu-id="86b91-114">Attributes and Elements</span></span>  
 <span data-ttu-id="86b91-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="86b91-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86b91-116">属性</span><span class="sxs-lookup"><span data-stu-id="86b91-116">Attributes</span></span>  
  
|<span data-ttu-id="86b91-117">属性</span><span class="sxs-lookup"><span data-stu-id="86b91-117">Attribute</span></span>|<span data-ttu-id="86b91-118">説明</span><span class="sxs-lookup"><span data-stu-id="86b91-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="86b91-119">name</span><span class="sxs-lookup"><span data-stu-id="86b91-119">name</span></span>|<span data-ttu-id="86b91-120">追跡レコードを生成する必要がある定期受信済みアクティビティの状態を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="86b91-120">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="86b91-121">子要素</span><span class="sxs-lookup"><span data-stu-id="86b91-121">Child Elements</span></span>  
 <span data-ttu-id="86b91-122">なし。</span><span class="sxs-lookup"><span data-stu-id="86b91-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="86b91-123">親要素</span><span class="sxs-lookup"><span data-stu-id="86b91-123">Parent Elements</span></span>  
  
|<span data-ttu-id="86b91-124">要素</span><span class="sxs-lookup"><span data-stu-id="86b91-124">Element</span></span>|<span data-ttu-id="86b91-125">説明</span><span class="sxs-lookup"><span data-stu-id="86b91-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86b91-126">\<states></span><span class="sxs-lookup"><span data-stu-id="86b91-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states-of-activitystatequery.md)|<span data-ttu-id="86b91-127">追跡レコードを生成する必要がある定期受信済みアクティビティの状態を含む構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="86b91-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86b91-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="86b91-128">Remarks</span></span>  
 <span data-ttu-id="86b91-129">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="86b91-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="86b91-130">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="86b91-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="86b91-131">使用することができます、 [\<引数 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)、 [\<状態 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)と[\<状態 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)任意の変数または引数を抽出する要素ワークフロー内の任意のアクティビティから</span><span class="sxs-lookup"><span data-stu-id="86b91-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="86b91-132">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="86b91-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="86b91-133">ActivityStateRecord でのみ抽出できるし、追跡のため購読中の変数と引数を使用してプロファイル[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)します。</span><span class="sxs-lookup"><span data-stu-id="86b91-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="86b91-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="86b91-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="86b91-135">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="86b91-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="86b91-136">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="86b91-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
