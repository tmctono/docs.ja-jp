---
title: <activityStateQuery>WCF の
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: 49c507424e813067e1dad9b08167d9661acef36f
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991215"
---
# <a name="activitystatequery-of-wcf"></a><span data-ttu-id="80bb0-102">\<WCF の activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="80bb0-102">\<activityStateQuery> of WCF</span></span>

<span data-ttu-id="80bb0-103">ワークフロー インスタンスを構成するアクティビティのライフサイクルの変化を追跡するために使用されるクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="80bb0-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="80bb0-104">たとえば、ワークフローインスタンス内で "電子メールの送信" アクティビティが完了するたびに追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="80bb0-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="80bb0-105">追跡参加要素がアクティビティ状態レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="80bb0-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="80bb0-106">定期受信可能な状態は ActivityStates で指定します。</span><span class="sxs-lookup"><span data-stu-id="80bb0-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="80bb0-107">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80bb0-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="80bb0-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="80bb0-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="80bb0-109">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="80bb0-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="80bb0-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="80bb0-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="80bb0-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<プロファイル >** </span><span class="sxs-lookup"><span data-stu-id="80bb0-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="80bb0-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="80bb0-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="80bb0-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="80bb0-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="80bb0-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityStateQueries >** ](activitystatequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="80bb0-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries-of-wcf.md)</span></span>\
<span data-ttu-id="80bb0-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<activityStateQuery >**</span><span class="sxs-lookup"><span data-stu-id="80bb0-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80bb0-116">構文</span><span class="sxs-lookup"><span data-stu-id="80bb0-116">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80bb0-117">属性と要素</span><span class="sxs-lookup"><span data-stu-id="80bb0-117">Attributes and elements</span></span>  

<span data-ttu-id="80bb0-118">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="80bb0-118">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80bb0-119">属性</span><span class="sxs-lookup"><span data-stu-id="80bb0-119">Attributes</span></span>  
  
|<span data-ttu-id="80bb0-120">属性</span><span class="sxs-lookup"><span data-stu-id="80bb0-120">Attribute</span></span>|<span data-ttu-id="80bb0-121">説明</span><span class="sxs-lookup"><span data-stu-id="80bb0-121">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="80bb0-122">activityName</span><span class="sxs-lookup"><span data-stu-id="80bb0-122">activityName</span></span>|<span data-ttu-id="80bb0-123"><xref:System.Activities.Tracking.ActivityStateRecord> インスタンスをフィルターするために、アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="80bb0-123">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80bb0-124">子要素</span><span class="sxs-lookup"><span data-stu-id="80bb0-124">Child elements</span></span>  
  
|<span data-ttu-id="80bb0-125">要素</span><span class="sxs-lookup"><span data-stu-id="80bb0-125">Element</span></span>|<span data-ttu-id="80bb0-126">説明</span><span class="sxs-lookup"><span data-stu-id="80bb0-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80bb0-127">\<引数 ></span><span class="sxs-lookup"><span data-stu-id="80bb0-127">\<arguments></span></span>](../windows-workflow-foundation/arguments.md)|<span data-ttu-id="80bb0-128">このアクティビティ クエリに関連付けられている引数のコレクション。</span><span class="sxs-lookup"><span data-stu-id="80bb0-128">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="80bb0-129">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="80bb0-129">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="80bb0-130">追跡レコードを生成する必要がある定期受信済みアクティビティの状態を含む構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="80bb0-130">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="80bb0-131">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="80bb0-131">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="80bb0-132">このアクティビティ クエリに関連付けられている変数のコレクション。</span><span class="sxs-lookup"><span data-stu-id="80bb0-132">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="80bb0-133">親要素</span><span class="sxs-lookup"><span data-stu-id="80bb0-133">Parent elements</span></span>  
  
|<span data-ttu-id="80bb0-134">要素</span><span class="sxs-lookup"><span data-stu-id="80bb0-134">Element</span></span>|<span data-ttu-id="80bb0-135">説明</span><span class="sxs-lookup"><span data-stu-id="80bb0-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80bb0-136">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="80bb0-136">\<faultPropagationQuery></span></span>](../windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="80bb0-137">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する構成要素の一覧を表します。</span><span class="sxs-lookup"><span data-stu-id="80bb0-137">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="80bb0-138">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="80bb0-138">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80bb0-139">Remarks</span><span class="sxs-lookup"><span data-stu-id="80bb0-139">Remarks</span></span>

<span data-ttu-id="80bb0-140">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="80bb0-140">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="80bb0-141">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="80bb0-141">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="80bb0-142">引数 >、 [ \<](../windows-workflow-foundation/arguments.md) [ states\<>](../windows-workflow-foundation/states.md)および[ states>要素を使用して、ワークフロー内の任意の\<](../windows-workflow-foundation/states.md)アクティビティから任意の変数または引数を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="80bb0-142">You can use the [\<arguments>](../windows-workflow-foundation/arguments.md), [\<states>](../windows-workflow-foundation/states.md) and [\<states>](../windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="80bb0-143">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="80bb0-143">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="80bb0-144">変数と引数は activitystaterecord でのみ抽出できるため、 [ \<activitystatequery >](../windows-workflow-foundation/activitystatequery.md)を使用して追跡プロファイル内でサブスクライブされます。</span><span class="sxs-lookup"><span data-stu-id="80bb0-144">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="80bb0-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="80bb0-145">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="80bb0-146">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="80bb0-146">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="80bb0-147">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="80bb0-147">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
