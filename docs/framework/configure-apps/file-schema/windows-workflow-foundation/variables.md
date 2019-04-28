---
title: <variables>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
ms.openlocfilehash: 61a786efc67f4e9afa585864e1f62b966b5cdff8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61613430"
---
# <a name="variables"></a><span data-ttu-id="5fdd1-101">\<variables></span><span class="sxs-lookup"><span data-stu-id="5fdd1-101">\<variables></span></span>
<span data-ttu-id="5fdd1-102">このアクティビティ クエリに関連付けられている変数のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="5fdd1-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="5fdd1-103">追跡プロファイルのクエリの詳細については、次を参照してください。[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)します。</span><span class="sxs-lookup"><span data-stu-id="5fdd1-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="5fdd1-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5fdd1-104">\<system.serviceModel></span></span>  
<span data-ttu-id="5fdd1-105">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="5fdd1-105">\<tracking></span></span>  
<span data-ttu-id="5fdd1-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="5fdd1-106">\<trackingProfile></span></span>  
<span data-ttu-id="5fdd1-107">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="5fdd1-107">\<workflow></span></span>  
<span data-ttu-id="5fdd1-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="5fdd1-108">\<activityStateQueries></span></span>  
<span data-ttu-id="5fdd1-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="5fdd1-109">\<activityStateQuery></span></span>  
<span data-ttu-id="5fdd1-110">\<variables></span><span class="sxs-lookup"><span data-stu-id="5fdd1-110">\<variables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fdd1-111">構文</span><span class="sxs-lookup"><span data-stu-id="5fdd1-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <variables>
          <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5fdd1-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5fdd1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5fdd1-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5fdd1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5fdd1-114">属性</span><span class="sxs-lookup"><span data-stu-id="5fdd1-114">Attributes</span></span>  
 <span data-ttu-id="5fdd1-115">なし。</span><span class="sxs-lookup"><span data-stu-id="5fdd1-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5fdd1-116">子要素</span><span class="sxs-lookup"><span data-stu-id="5fdd1-116">Child Elements</span></span>  
  
|<span data-ttu-id="5fdd1-117">要素</span><span class="sxs-lookup"><span data-stu-id="5fdd1-117">Element</span></span>|<span data-ttu-id="5fdd1-118">説明</span><span class="sxs-lookup"><span data-stu-id="5fdd1-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5fdd1-119">\<variable></span><span class="sxs-lookup"><span data-stu-id="5fdd1-119">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="5fdd1-120">アクティビティ状態クエリに関連付けられている変数。</span><span class="sxs-lookup"><span data-stu-id="5fdd1-120">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5fdd1-121">親要素</span><span class="sxs-lookup"><span data-stu-id="5fdd1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5fdd1-122">要素</span><span class="sxs-lookup"><span data-stu-id="5fdd1-122">Element</span></span>|<span data-ttu-id="5fdd1-123">説明</span><span class="sxs-lookup"><span data-stu-id="5fdd1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5fdd1-124">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="5fdd1-124">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="5fdd1-125">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="5fdd1-125">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="5fdd1-126">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="5fdd1-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5fdd1-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="5fdd1-127">Remarks</span></span>  
 <span data-ttu-id="5fdd1-128">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="5fdd1-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="5fdd1-129">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="5fdd1-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="5fdd1-130">使用することができます、 [\<引数 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)、 [\<状態 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)と[\<状態 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)任意の変数または引数を抽出する要素ワークフロー内の任意のアクティビティから</span><span class="sxs-lookup"><span data-stu-id="5fdd1-130">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="5fdd1-131">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="5fdd1-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="5fdd1-132">ActivityStateRecord でのみ抽出できるし、追跡のため購読中の変数と引数を使用してプロファイル[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)します。</span><span class="sxs-lookup"><span data-stu-id="5fdd1-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5fdd1-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="5fdd1-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5fdd1-134">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="5fdd1-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5fdd1-135">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="5fdd1-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
