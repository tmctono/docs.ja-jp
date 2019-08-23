---
title: <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: 560df771b44fc8ba8d192657677bf0496283b539
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945426"
---
# <a name="activitystatequery"></a><span data-ttu-id="ca163-101">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="ca163-101">\<activityStateQuery></span></span>
<span data-ttu-id="ca163-102">ワークフロー インスタンスを構成するアクティビティのライフサイクルの変化を追跡するために使用されるクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="ca163-102">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="ca163-103">たとえば、ワークフローインスタンス内で "電子メールの送信" アクティビティが完了するたびに追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="ca163-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="ca163-104">追跡参加要素がアクティビティ状態レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="ca163-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="ca163-105">定期受信可能な状態は ActivityStates で指定します。</span><span class="sxs-lookup"><span data-stu-id="ca163-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="ca163-106">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca163-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="ca163-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ca163-107">\<system.serviceModel></span></span>  
<span data-ttu-id="ca163-108">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="ca163-108">\<tracking></span></span>  
<span data-ttu-id="ca163-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ca163-109">\<trackingProfile></span></span>  
<span data-ttu-id="ca163-110">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="ca163-110">\<workflow></span></span>  
<span data-ttu-id="ca163-111">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="ca163-111">\<activityStateQueries></span></span>  
<span data-ttu-id="ca163-112">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="ca163-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca163-113">構文</span><span class="sxs-lookup"><span data-stu-id="ca163-113">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
        <states>
          <state name="String"/>
        </states>
        <variables>
          <variable name="String"/>
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca163-114">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ca163-114">Attributes and Elements</span></span>  
 <span data-ttu-id="ca163-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca163-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca163-116">属性</span><span class="sxs-lookup"><span data-stu-id="ca163-116">Attributes</span></span>  
  
|<span data-ttu-id="ca163-117">属性</span><span class="sxs-lookup"><span data-stu-id="ca163-117">Attribute</span></span>|<span data-ttu-id="ca163-118">説明</span><span class="sxs-lookup"><span data-stu-id="ca163-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca163-119">activityName</span><span class="sxs-lookup"><span data-stu-id="ca163-119">activityName</span></span>|<span data-ttu-id="ca163-120"><xref:System.Activities.Tracking.ActivityStateRecord> インスタンスをフィルターするために、アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="ca163-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca163-121">子要素</span><span class="sxs-lookup"><span data-stu-id="ca163-121">Child Elements</span></span>  
  
|<span data-ttu-id="ca163-122">要素</span><span class="sxs-lookup"><span data-stu-id="ca163-122">Element</span></span>|<span data-ttu-id="ca163-123">説明</span><span class="sxs-lookup"><span data-stu-id="ca163-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca163-124">\<引数 ></span><span class="sxs-lookup"><span data-stu-id="ca163-124">\<arguments></span></span>](arguments.md)|<span data-ttu-id="ca163-125">このアクティビティ クエリに関連付けられている引数のコレクション。</span><span class="sxs-lookup"><span data-stu-id="ca163-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="ca163-126">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="ca163-126">\<states></span></span>](states.md)|<span data-ttu-id="ca163-127">追跡レコードを生成する必要がある定期受信済みアクティビティの状態を含む構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="ca163-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="ca163-128">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="ca163-128">\<states></span></span>](states.md)|<span data-ttu-id="ca163-129">このアクティビティ クエリに関連付けられている変数のコレクション。</span><span class="sxs-lookup"><span data-stu-id="ca163-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ca163-130">親要素</span><span class="sxs-lookup"><span data-stu-id="ca163-130">Parent Elements</span></span>  
  
|<span data-ttu-id="ca163-131">要素</span><span class="sxs-lookup"><span data-stu-id="ca163-131">Element</span></span>|<span data-ttu-id="ca163-132">説明</span><span class="sxs-lookup"><span data-stu-id="ca163-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca163-133">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="ca163-133">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="ca163-134">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する構成要素の一覧を表します。</span><span class="sxs-lookup"><span data-stu-id="ca163-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ca163-135">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="ca163-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca163-136">Remarks</span><span class="sxs-lookup"><span data-stu-id="ca163-136">Remarks</span></span>  
 <span data-ttu-id="ca163-137">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="ca163-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="ca163-138">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="ca163-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="ca163-139">引数 >、 [ \<](arguments.md) [ states\<>](states.md)および[ states>要素を使用して、ワークフロー内の任意の\<](states.md)アクティビティから任意の変数または引数を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="ca163-139">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="ca163-140">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="ca163-140">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="ca163-141">変数と引数は activitystaterecord でのみ抽出できるため、 [ \<activitystatequery >](activitystatequery.md)を使用して追跡プロファイル内でサブスクライブされます。</span><span class="sxs-lookup"><span data-stu-id="ca163-141">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ca163-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca163-142">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ca163-143">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="ca163-143">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ca163-144">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="ca163-144">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
