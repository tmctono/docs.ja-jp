---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 58e3752be81609e32eee631e46d10c0a7d704248
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398956"
---
# <a name="activitystatequeries"></a><span data-ttu-id="fb8ad-101">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="fb8ad-101">\<activityStateQueries></span></span>
<span data-ttu-id="fb8ad-102">ワークフロー インスタンスを構成するアクティビティのライフサイクルの変化を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="fb8ad-102">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="fb8ad-103">たとえば、ワークフローインスタンス内で "電子メールの送信" アクティビティが完了するたびに追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="fb8ad-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="fb8ad-104">追跡参加要素がアクティビティ状態レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="fb8ad-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="fb8ad-105">定期受信可能な状態は ActivityStates で指定します。</span><span class="sxs-lookup"><span data-stu-id="fb8ad-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="fb8ad-106">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb8ad-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="fb8ad-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fb8ad-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fb8ad-108">&nbsp;&nbsp;[ **\<system.ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="fb8ad-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="fb8ad-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="fb8ad-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="fb8ad-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="fb8ad-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="fb8ad-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="fb8ad-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="fb8ad-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<activityStateQueries >**</span><span class="sxs-lookup"><span data-stu-id="fb8ad-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb8ad-113">構文</span><span class="sxs-lookup"><span data-stu-id="fb8ad-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb8ad-114">属性および要素</span><span class="sxs-lookup"><span data-stu-id="fb8ad-114">Attributes and Elements</span></span>  
 <span data-ttu-id="fb8ad-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb8ad-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb8ad-116">属性</span><span class="sxs-lookup"><span data-stu-id="fb8ad-116">Attributes</span></span>  
 <span data-ttu-id="fb8ad-117">なし。</span><span class="sxs-lookup"><span data-stu-id="fb8ad-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fb8ad-118">子要素</span><span class="sxs-lookup"><span data-stu-id="fb8ad-118">Child Elements</span></span>  
  
|<span data-ttu-id="fb8ad-119">要素</span><span class="sxs-lookup"><span data-stu-id="fb8ad-119">Element</span></span>|<span data-ttu-id="fb8ad-120">説明</span><span class="sxs-lookup"><span data-stu-id="fb8ad-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb8ad-121">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="fb8ad-121">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="fb8ad-122">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="fb8ad-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="fb8ad-123">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="fb8ad-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fb8ad-124">親要素</span><span class="sxs-lookup"><span data-stu-id="fb8ad-124">Parent Elements</span></span>  
  
|<span data-ttu-id="fb8ad-125">要素</span><span class="sxs-lookup"><span data-stu-id="fb8ad-125">Element</span></span>|<span data-ttu-id="fb8ad-126">説明</span><span class="sxs-lookup"><span data-stu-id="fb8ad-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb8ad-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="fb8ad-127">\<workflow></span></span>](workflow.md)|<span data-ttu-id="fb8ad-128">**ActivityDefinitionId**プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="fb8ad-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb8ad-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb8ad-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="fb8ad-130">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="fb8ad-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="fb8ad-131">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="fb8ad-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
