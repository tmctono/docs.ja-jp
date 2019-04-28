---
title: <activityStateQueries> WCF の
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: c9c78b6929b4550204a22fe2e2786891b516a818
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701087"
---
# <a name="activitystatequeries-of-wcf"></a><span data-ttu-id="5f258-102">\<activityStateQueries > の WCF</span><span class="sxs-lookup"><span data-stu-id="5f258-102">\<activityStateQueries> of WCF</span></span>

<span data-ttu-id="5f258-103">ワークフロー インスタンスを構成するアクティビティのライフサイクルの変化を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="5f258-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="5f258-104">たとえば、ワークフロー インスタンス内で、「電子メールの送信」アクティビティが完了するたびの追跡する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5f258-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="5f258-105">追跡参加要素がアクティビティ状態レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="5f258-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="5f258-106">定期受信可能な状態は ActivityStates で指定します。</span><span class="sxs-lookup"><span data-stu-id="5f258-106">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="5f258-107">追跡プロファイルのクエリの詳細については、次を参照してください。[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)します。</span><span class="sxs-lookup"><span data-stu-id="5f258-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="5f258-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5f258-108">\<system.serviceModel></span></span>  
<span data-ttu-id="5f258-109">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="5f258-109">\<tracking></span></span>  
<span data-ttu-id="5f258-110">\<プロファイル ></span><span class="sxs-lookup"><span data-stu-id="5f258-110">\<profiles></span></span>  
<span data-ttu-id="5f258-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="5f258-111">\<trackingProfile></span></span>  
<span data-ttu-id="5f258-112">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="5f258-112">\<workflow></span></span>  
<span data-ttu-id="5f258-113">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="5f258-113">\<activityStateQueries></span></span>  

## <a name="syntax"></a><span data-ttu-id="5f258-114">構文</span><span class="sxs-lookup"><span data-stu-id="5f258-114">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="5f258-115">属性と要素</span><span class="sxs-lookup"><span data-stu-id="5f258-115">Attributes and elements</span></span>

<span data-ttu-id="5f258-116">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5f258-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="5f258-117">属性</span><span class="sxs-lookup"><span data-stu-id="5f258-117">Attributes</span></span>  

<span data-ttu-id="5f258-118">なし。</span><span class="sxs-lookup"><span data-stu-id="5f258-118">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="5f258-119">子要素</span><span class="sxs-lookup"><span data-stu-id="5f258-119">Child elements</span></span>

|<span data-ttu-id="5f258-120">要素</span><span class="sxs-lookup"><span data-stu-id="5f258-120">Element</span></span>|<span data-ttu-id="5f258-121">説明</span><span class="sxs-lookup"><span data-stu-id="5f258-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5f258-122">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="5f258-122">\<activityStateQuery></span></span>](activitystatequery-of-wcf.md)|<span data-ttu-id="5f258-123">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="5f258-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="5f258-124">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="5f258-124">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5f258-125">親要素</span><span class="sxs-lookup"><span data-stu-id="5f258-125">Parent elements</span></span>

|<span data-ttu-id="5f258-126">要素</span><span class="sxs-lookup"><span data-stu-id="5f258-126">Element</span></span>|<span data-ttu-id="5f258-127">説明</span><span class="sxs-lookup"><span data-stu-id="5f258-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5f258-128">\<workflow></span><span class="sxs-lookup"><span data-stu-id="5f258-128">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="5f258-129">`activityDefinitionId` プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="5f258-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="5f258-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f258-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="5f258-131">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="5f258-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5f258-132">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="5f258-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
