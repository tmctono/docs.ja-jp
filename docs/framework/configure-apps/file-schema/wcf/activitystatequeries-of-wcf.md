---
title: <activityStateQueries>WCF の
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 249ac3d91f6251a943dd856e4122b8b54f691702
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850574"
---
# <a name="activitystatequeries-of-wcf"></a><span data-ttu-id="cf2e8-102">\<activityStateQueries>WCF の</span><span class="sxs-lookup"><span data-stu-id="cf2e8-102">\<activityStateQueries> of WCF</span></span>

<span data-ttu-id="cf2e8-103">ワークフロー インスタンスを構成するアクティビティのライフサイクルの変化を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="cf2e8-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="cf2e8-104">たとえば、ワークフローインスタンス内で "電子メールの送信" アクティビティが完了するたびに追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="cf2e8-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="cf2e8-105">追跡参加要素がアクティビティ状態レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="cf2e8-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="cf2e8-106">定期受信可能な状態は ActivityStates で指定します。</span><span class="sxs-lookup"><span data-stu-id="cf2e8-106">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="cf2e8-107">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf2e8-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="cf2e8-108">構文</span><span class="sxs-lookup"><span data-stu-id="cf2e8-108">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="cf2e8-109">属性と要素</span><span class="sxs-lookup"><span data-stu-id="cf2e8-109">Attributes and elements</span></span>

<span data-ttu-id="cf2e8-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cf2e8-110">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="cf2e8-111">属性</span><span class="sxs-lookup"><span data-stu-id="cf2e8-111">Attributes</span></span>  

<span data-ttu-id="cf2e8-112">なし。</span><span class="sxs-lookup"><span data-stu-id="cf2e8-112">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="cf2e8-113">子要素</span><span class="sxs-lookup"><span data-stu-id="cf2e8-113">Child elements</span></span>

|<span data-ttu-id="cf2e8-114">要素</span><span class="sxs-lookup"><span data-stu-id="cf2e8-114">Element</span></span>|<span data-ttu-id="cf2e8-115">説明</span><span class="sxs-lookup"><span data-stu-id="cf2e8-115">Description</span></span>|
|-------------|-----------------|
|[\<activityStateQuery>](activitystatequery-of-wcf.md)|<span data-ttu-id="cf2e8-116">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="cf2e8-116">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="cf2e8-117">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="cf2e8-117">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cf2e8-118">親要素</span><span class="sxs-lookup"><span data-stu-id="cf2e8-118">Parent elements</span></span>

|<span data-ttu-id="cf2e8-119">要素</span><span class="sxs-lookup"><span data-stu-id="cf2e8-119">Element</span></span>|<span data-ttu-id="cf2e8-120">説明</span><span class="sxs-lookup"><span data-stu-id="cf2e8-120">Description</span></span>|
|-------------|-----------------|
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="cf2e8-121">`activityDefinitionId` プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="cf2e8-121">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="cf2e8-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf2e8-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="cf2e8-123">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="cf2e8-123">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="cf2e8-124">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="cf2e8-124">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
