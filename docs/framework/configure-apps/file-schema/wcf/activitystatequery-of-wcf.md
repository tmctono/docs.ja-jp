---
title: <activityStateQuery>WCF の
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: ce7505896b9c5bb605bb0f67d735cb324f4fd493
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926897"
---
# <a name="activitystatequery-of-wcf"></a><span data-ttu-id="21c76-102">\<WCF の activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="21c76-102">\<activityStateQuery> of WCF</span></span>

<span data-ttu-id="21c76-103">ワークフロー インスタンスを構成するアクティビティのライフサイクルの変化を追跡するために使用されるクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="21c76-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="21c76-104">たとえば、ワークフローインスタンス内で "電子メールの送信" アクティビティが完了するたびに追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="21c76-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="21c76-105">追跡参加要素がアクティビティ状態レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="21c76-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="21c76-106">定期受信可能な状態は ActivityStates で指定します。</span><span class="sxs-lookup"><span data-stu-id="21c76-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="21c76-107">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21c76-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="21c76-108">\<system.serviceModel> \<tracking></span><span class="sxs-lookup"><span data-stu-id="21c76-108">\<system.serviceModel> \<tracking></span></span>  
<span data-ttu-id="21c76-109">\<プロファイル > \<trackingprofile ></span><span class="sxs-lookup"><span data-stu-id="21c76-109">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="21c76-110">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="21c76-110">\<workflow></span></span>  
<span data-ttu-id="21c76-111">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="21c76-111">\<activityStateQueries></span></span>  
<span data-ttu-id="21c76-112">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="21c76-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21c76-113">構文</span><span class="sxs-lookup"><span data-stu-id="21c76-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String" />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21c76-114">属性と要素</span><span class="sxs-lookup"><span data-stu-id="21c76-114">Attributes and elements</span></span>  

<span data-ttu-id="21c76-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="21c76-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21c76-116">属性</span><span class="sxs-lookup"><span data-stu-id="21c76-116">Attributes</span></span>  
  
|<span data-ttu-id="21c76-117">属性</span><span class="sxs-lookup"><span data-stu-id="21c76-117">Attribute</span></span>|<span data-ttu-id="21c76-118">説明</span><span class="sxs-lookup"><span data-stu-id="21c76-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="21c76-119">activityName</span><span class="sxs-lookup"><span data-stu-id="21c76-119">activityName</span></span>|<span data-ttu-id="21c76-120"><xref:System.Activities.Tracking.ActivityStateRecord> インスタンスをフィルターするために、アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="21c76-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21c76-121">子要素</span><span class="sxs-lookup"><span data-stu-id="21c76-121">Child elements</span></span>  
  
|<span data-ttu-id="21c76-122">要素</span><span class="sxs-lookup"><span data-stu-id="21c76-122">Element</span></span>|<span data-ttu-id="21c76-123">説明</span><span class="sxs-lookup"><span data-stu-id="21c76-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21c76-124">\<引数 ></span><span class="sxs-lookup"><span data-stu-id="21c76-124">\<arguments></span></span>](../windows-workflow-foundation/arguments.md)|<span data-ttu-id="21c76-125">このアクティビティ クエリに関連付けられている引数のコレクション。</span><span class="sxs-lookup"><span data-stu-id="21c76-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="21c76-126">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="21c76-126">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="21c76-127">追跡レコードを生成する必要がある定期受信済みアクティビティの状態を含む構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="21c76-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="21c76-128">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="21c76-128">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="21c76-129">このアクティビティ クエリに関連付けられている変数のコレクション。</span><span class="sxs-lookup"><span data-stu-id="21c76-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="21c76-130">親要素</span><span class="sxs-lookup"><span data-stu-id="21c76-130">Parent elements</span></span>  
  
|<span data-ttu-id="21c76-131">要素</span><span class="sxs-lookup"><span data-stu-id="21c76-131">Element</span></span>|<span data-ttu-id="21c76-132">説明</span><span class="sxs-lookup"><span data-stu-id="21c76-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21c76-133">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="21c76-133">\<faultPropagationQuery></span></span>](../windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="21c76-134">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する構成要素の一覧を表します。</span><span class="sxs-lookup"><span data-stu-id="21c76-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="21c76-135">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="21c76-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21c76-136">Remarks</span><span class="sxs-lookup"><span data-stu-id="21c76-136">Remarks</span></span>

<span data-ttu-id="21c76-137">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="21c76-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="21c76-138">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="21c76-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="21c76-139">引数 >、 [ \<](../windows-workflow-foundation/arguments.md) [ states\<>](../windows-workflow-foundation/states.md)および[ states>要素を使用して、ワークフロー内の任意の\<](../windows-workflow-foundation/states.md)アクティビティから任意の変数または引数を抽出できます。次の例は、アクティビティの`Closed`追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="21c76-139">You can use the [\<arguments>](../windows-workflow-foundation/arguments.md), [\<states>](../windows-workflow-foundation/states.md) and [\<states>](../windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="21c76-140">変数と引数は activitystaterecord でのみ抽出できるため、 [ \<activitystatequery >](../windows-workflow-foundation/activitystatequery.md)を使用して追跡プロファイル内でサブスクライブされます。</span><span class="sxs-lookup"><span data-stu-id="21c76-140">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">
  <states>
    <state name="Closed" />
  </states>
  <variables>
    <variable name="FromAddress" />
  </variables>
  <arguments>
    <argument name="Result" />
  </arguments>
</activityStateQuery>
```  
  
## <a name="see-also"></a><span data-ttu-id="21c76-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="21c76-141">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="21c76-142">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="21c76-142">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="21c76-143">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="21c76-143">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
