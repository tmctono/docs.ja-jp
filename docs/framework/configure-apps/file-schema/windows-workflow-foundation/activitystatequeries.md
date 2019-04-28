---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 90acda7277fd276f43a619a014fbce103261aa1e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790404"
---
# <a name="activitystatequeries"></a><span data-ttu-id="ef37a-101">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="ef37a-101">\<activityStateQueries></span></span>
<span data-ttu-id="ef37a-102">ワークフロー インスタンスを構成するアクティビティのライフサイクルの変化を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="ef37a-102">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="ef37a-103">たとえば、ワークフロー インスタンス内で、「電子メールの送信」アクティビティが完了するたびの追跡する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ef37a-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="ef37a-104">追跡参加要素がアクティビティ状態レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="ef37a-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="ef37a-105">定期受信可能な状態は ActivityStates で指定します。</span><span class="sxs-lookup"><span data-stu-id="ef37a-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="ef37a-106">追跡プロファイルのクエリの詳細については、次を参照してください。[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)します。</span><span class="sxs-lookup"><span data-stu-id="ef37a-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="ef37a-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ef37a-107">\<system.serviceModel></span></span>  
<span data-ttu-id="ef37a-108">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="ef37a-108">\<tracking></span></span>  
<span data-ttu-id="ef37a-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ef37a-109">\<trackingProfile></span></span>  
<span data-ttu-id="ef37a-110">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="ef37a-110">\<workflow></span></span>  
<span data-ttu-id="ef37a-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="ef37a-111">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef37a-112">構文</span><span class="sxs-lookup"><span data-stu-id="ef37a-112">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
        <states>
          <state name="String" />
        </states>
        <variables>
         <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef37a-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ef37a-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ef37a-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ef37a-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef37a-115">属性</span><span class="sxs-lookup"><span data-stu-id="ef37a-115">Attributes</span></span>  
 <span data-ttu-id="ef37a-116">なし。</span><span class="sxs-lookup"><span data-stu-id="ef37a-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ef37a-117">子要素</span><span class="sxs-lookup"><span data-stu-id="ef37a-117">Child Elements</span></span>  
  
|<span data-ttu-id="ef37a-118">要素</span><span class="sxs-lookup"><span data-stu-id="ef37a-118">Element</span></span>|<span data-ttu-id="ef37a-119">説明</span><span class="sxs-lookup"><span data-stu-id="ef37a-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef37a-120">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="ef37a-120">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="ef37a-121">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="ef37a-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="ef37a-122">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="ef37a-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ef37a-123">親要素</span><span class="sxs-lookup"><span data-stu-id="ef37a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ef37a-124">要素</span><span class="sxs-lookup"><span data-stu-id="ef37a-124">Element</span></span>|<span data-ttu-id="ef37a-125">説明</span><span class="sxs-lookup"><span data-stu-id="ef37a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef37a-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ef37a-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="ef37a-127">識別される特定のワークフローのすべてのクエリを格納する構成要素、 **activityDefinitionId**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ef37a-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef37a-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef37a-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ef37a-129">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="ef37a-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ef37a-130">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="ef37a-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
