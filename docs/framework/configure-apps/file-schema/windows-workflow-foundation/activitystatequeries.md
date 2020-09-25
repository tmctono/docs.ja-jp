---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 4663ccedcafb6b151de75568afd3743c83c75224
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189826"
---
# \<activityStateQueries>

<span data-ttu-id="0056a-101">ワークフロー インスタンスを構成するアクティビティのライフサイクルの変化を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="0056a-101">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="0056a-102">たとえば、ワークフローインスタンス内で "電子メールの送信" アクティビティが完了するたびに追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="0056a-102">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="0056a-103">追跡参加要素がアクティビティ状態レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="0056a-103">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="0056a-104">定期受信可能な状態は ActivityStates で指定します。</span><span class="sxs-lookup"><span data-stu-id="0056a-104">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="0056a-105">追跡プロファイルのクエリの詳細については、「 [追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0056a-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="0056a-106">構文</span><span class="sxs-lookup"><span data-stu-id="0056a-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0056a-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0056a-107">Attributes and Elements</span></span>  

 <span data-ttu-id="0056a-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0056a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0056a-109">属性</span><span class="sxs-lookup"><span data-stu-id="0056a-109">Attributes</span></span>  

 <span data-ttu-id="0056a-110">なし。</span><span class="sxs-lookup"><span data-stu-id="0056a-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0056a-111">子要素</span><span class="sxs-lookup"><span data-stu-id="0056a-111">Child Elements</span></span>  
  
|<span data-ttu-id="0056a-112">要素</span><span class="sxs-lookup"><span data-stu-id="0056a-112">Element</span></span>|<span data-ttu-id="0056a-113">説明</span><span class="sxs-lookup"><span data-stu-id="0056a-113">Description</span></span>|  
|-------------|-----------------|  
|[\<activityStateQuery>](activitystatequery.md)|<span data-ttu-id="0056a-114">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="0056a-114">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="0056a-115">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="0056a-115">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0056a-116">親要素</span><span class="sxs-lookup"><span data-stu-id="0056a-116">Parent Elements</span></span>  
  
|<span data-ttu-id="0056a-117">要素</span><span class="sxs-lookup"><span data-stu-id="0056a-117">Element</span></span>|<span data-ttu-id="0056a-118">説明</span><span class="sxs-lookup"><span data-stu-id="0056a-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="0056a-119">**ActivityDefinitionId**プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="0056a-119">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0056a-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="0056a-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0056a-121">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="0056a-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0056a-122">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="0056a-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
