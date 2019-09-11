---
title: <activityStateQueries>WCF の
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 249ac3d91f6251a943dd856e4122b8b54f691702
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850574"
---
# <a name="activitystatequeries-of-wcf"></a><span data-ttu-id="3a07b-102">\<WCF の activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="3a07b-102">\<activityStateQueries> of WCF</span></span>

<span data-ttu-id="3a07b-103">ワークフロー インスタンスを構成するアクティビティのライフサイクルの変化を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="3a07b-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="3a07b-104">たとえば、ワークフローインスタンス内で "電子メールの送信" アクティビティが完了するたびに追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="3a07b-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="3a07b-105">追跡参加要素がアクティビティ状態レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="3a07b-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="3a07b-106">定期受信可能な状態は ActivityStates で指定します。</span><span class="sxs-lookup"><span data-stu-id="3a07b-106">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="3a07b-107">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a07b-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="3a07b-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3a07b-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3a07b-109">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3a07b-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3a07b-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="3a07b-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="3a07b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<プロファイル >** </span><span class="sxs-lookup"><span data-stu-id="3a07b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="3a07b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="3a07b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="3a07b-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="3a07b-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="3a07b-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<activityStateQueries >**</span><span class="sxs-lookup"><span data-stu-id="3a07b-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a07b-115">構文</span><span class="sxs-lookup"><span data-stu-id="3a07b-115">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="3a07b-116">属性と要素</span><span class="sxs-lookup"><span data-stu-id="3a07b-116">Attributes and elements</span></span>

<span data-ttu-id="3a07b-117">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3a07b-117">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="3a07b-118">属性</span><span class="sxs-lookup"><span data-stu-id="3a07b-118">Attributes</span></span>  

<span data-ttu-id="3a07b-119">なし。</span><span class="sxs-lookup"><span data-stu-id="3a07b-119">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="3a07b-120">子要素</span><span class="sxs-lookup"><span data-stu-id="3a07b-120">Child elements</span></span>

|<span data-ttu-id="3a07b-121">要素</span><span class="sxs-lookup"><span data-stu-id="3a07b-121">Element</span></span>|<span data-ttu-id="3a07b-122">説明</span><span class="sxs-lookup"><span data-stu-id="3a07b-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3a07b-123">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="3a07b-123">\<activityStateQuery></span></span>](activitystatequery-of-wcf.md)|<span data-ttu-id="3a07b-124">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="3a07b-124">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="3a07b-125">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="3a07b-125">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3a07b-126">親要素</span><span class="sxs-lookup"><span data-stu-id="3a07b-126">Parent elements</span></span>

|<span data-ttu-id="3a07b-127">要素</span><span class="sxs-lookup"><span data-stu-id="3a07b-127">Element</span></span>|<span data-ttu-id="3a07b-128">説明</span><span class="sxs-lookup"><span data-stu-id="3a07b-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3a07b-129">\<workflow></span><span class="sxs-lookup"><span data-stu-id="3a07b-129">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="3a07b-130">`activityDefinitionId` プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="3a07b-130">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="3a07b-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a07b-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="3a07b-132">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="3a07b-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3a07b-133">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="3a07b-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
