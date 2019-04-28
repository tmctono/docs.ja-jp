---
title: <activityStateQuery> WCF の
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: 97fce512415ad6ae165b29c7e8eff3394d5e675a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704532"
---
# <a name="activitystatequery-of-wcf"></a><span data-ttu-id="2dd25-102">\<activityStateQuery > の WCF</span><span class="sxs-lookup"><span data-stu-id="2dd25-102">\<activityStateQuery> of WCF</span></span>

<span data-ttu-id="2dd25-103">ワークフロー インスタンスを構成するアクティビティのライフサイクルの変化を追跡するために使用されるクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="2dd25-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="2dd25-104">たとえば、ワークフロー インスタンス内で、「電子メールの送信」アクティビティが完了するたびの追跡する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2dd25-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="2dd25-105">追跡参加要素がアクティビティ状態レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="2dd25-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="2dd25-106">定期受信可能な状態は ActivityStates で指定します。</span><span class="sxs-lookup"><span data-stu-id="2dd25-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="2dd25-107">追跡プロファイルのクエリの詳細については、次を参照してください。[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)します。</span><span class="sxs-lookup"><span data-stu-id="2dd25-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="2dd25-108">\<system.serviceModel> \<tracking></span><span class="sxs-lookup"><span data-stu-id="2dd25-108">\<system.serviceModel> \<tracking></span></span>  
<span data-ttu-id="2dd25-109">\<プロファイル > \<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="2dd25-109">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="2dd25-110">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="2dd25-110">\<workflow></span></span>  
<span data-ttu-id="2dd25-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="2dd25-111">\<activityStateQueries></span></span>  
<span data-ttu-id="2dd25-112">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="2dd25-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dd25-113">構文</span><span class="sxs-lookup"><span data-stu-id="2dd25-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2dd25-114">属性と要素</span><span class="sxs-lookup"><span data-stu-id="2dd25-114">Attributes and elements</span></span>  

<span data-ttu-id="2dd25-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2dd25-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2dd25-116">属性</span><span class="sxs-lookup"><span data-stu-id="2dd25-116">Attributes</span></span>  
  
|<span data-ttu-id="2dd25-117">属性</span><span class="sxs-lookup"><span data-stu-id="2dd25-117">Attribute</span></span>|<span data-ttu-id="2dd25-118">説明</span><span class="sxs-lookup"><span data-stu-id="2dd25-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2dd25-119">activityName</span><span class="sxs-lookup"><span data-stu-id="2dd25-119">activityName</span></span>|<span data-ttu-id="2dd25-120"><xref:System.Activities.Tracking.ActivityStateRecord> インスタンスをフィルターするために、アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="2dd25-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2dd25-121">子要素</span><span class="sxs-lookup"><span data-stu-id="2dd25-121">Child elements</span></span>  
  
|<span data-ttu-id="2dd25-122">要素</span><span class="sxs-lookup"><span data-stu-id="2dd25-122">Element</span></span>|<span data-ttu-id="2dd25-123">説明</span><span class="sxs-lookup"><span data-stu-id="2dd25-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2dd25-124">\<arguments></span><span class="sxs-lookup"><span data-stu-id="2dd25-124">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="2dd25-125">このアクティビティ クエリに関連付けられている引数のコレクション。</span><span class="sxs-lookup"><span data-stu-id="2dd25-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="2dd25-126">\<states></span><span class="sxs-lookup"><span data-stu-id="2dd25-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="2dd25-127">追跡レコードを生成する必要がある定期受信済みアクティビティの状態を含む構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="2dd25-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="2dd25-128">\<states></span><span class="sxs-lookup"><span data-stu-id="2dd25-128">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="2dd25-129">このアクティビティ クエリに関連付けられている変数のコレクション。</span><span class="sxs-lookup"><span data-stu-id="2dd25-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2dd25-130">親要素</span><span class="sxs-lookup"><span data-stu-id="2dd25-130">Parent elements</span></span>  
  
|<span data-ttu-id="2dd25-131">要素</span><span class="sxs-lookup"><span data-stu-id="2dd25-131">Element</span></span>|<span data-ttu-id="2dd25-132">説明</span><span class="sxs-lookup"><span data-stu-id="2dd25-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2dd25-133">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="2dd25-133">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="2dd25-134">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する構成要素の一覧を表します。</span><span class="sxs-lookup"><span data-stu-id="2dd25-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="2dd25-135">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="2dd25-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2dd25-136">Remarks</span><span class="sxs-lookup"><span data-stu-id="2dd25-136">Remarks</span></span>

<span data-ttu-id="2dd25-137">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="2dd25-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="2dd25-138">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="2dd25-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="2dd25-139">使用することができます、 [\<引数 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)、 [\<状態 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)と[\<状態 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)任意の変数または引数を抽出する要素ワークフロー内の任意のアクティビティから次の例では、アクティビティ状態クエリ変数と引数を抽出するときに、アクティビティの`Closed`追跡レコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="2dd25-139">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="2dd25-140">ActivityStateRecord でのみ抽出できるし、追跡のため購読中の変数と引数を使用してプロファイル[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)します。</span><span class="sxs-lookup"><span data-stu-id="2dd25-140">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2dd25-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="2dd25-141">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="2dd25-142">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="2dd25-142">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2dd25-143">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="2dd25-143">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
