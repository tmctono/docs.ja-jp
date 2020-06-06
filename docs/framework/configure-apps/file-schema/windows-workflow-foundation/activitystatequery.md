---
title: <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: 5d3c35589330ab5bed5f89c0dafac006b9e3af55
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398938"
---
# \<activityStateQuery>
<span data-ttu-id="3d0da-101">ワークフロー インスタンスを構成するアクティビティのライフサイクルの変化を追跡するために使用されるクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="3d0da-101">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="3d0da-102">たとえば、ワークフローインスタンス内で "電子メールの送信" アクティビティが完了するたびに追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="3d0da-102">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="3d0da-103">追跡参加要素がアクティビティ状態レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="3d0da-103">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="3d0da-104">定期受信可能な状態は ActivityStates で指定します。</span><span class="sxs-lookup"><span data-stu-id="3d0da-104">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="3d0da-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d0da-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="3d0da-106">構文</span><span class="sxs-lookup"><span data-stu-id="3d0da-106">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
        <states>
          <state name="String"/>
        </states>
        <variables>
          <variable name="String"/>
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d0da-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3d0da-107">Attributes and Elements</span></span>  
 <span data-ttu-id="3d0da-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d0da-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d0da-109">属性</span><span class="sxs-lookup"><span data-stu-id="3d0da-109">Attributes</span></span>  
  
|<span data-ttu-id="3d0da-110">属性</span><span class="sxs-lookup"><span data-stu-id="3d0da-110">Attribute</span></span>|<span data-ttu-id="3d0da-111">説明</span><span class="sxs-lookup"><span data-stu-id="3d0da-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3d0da-112">activityName</span><span class="sxs-lookup"><span data-stu-id="3d0da-112">activityName</span></span>|<span data-ttu-id="3d0da-113"><xref:System.Activities.Tracking.ActivityStateRecord> インスタンスをフィルターするために、アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="3d0da-113">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3d0da-114">子要素</span><span class="sxs-lookup"><span data-stu-id="3d0da-114">Child Elements</span></span>  
  
|<span data-ttu-id="3d0da-115">要素</span><span class="sxs-lookup"><span data-stu-id="3d0da-115">Element</span></span>|<span data-ttu-id="3d0da-116">Description</span><span class="sxs-lookup"><span data-stu-id="3d0da-116">Description</span></span>|  
|-------------|-----------------|  
|[\<arguments>](arguments.md)|<span data-ttu-id="3d0da-117">このアクティビティ クエリに関連付けられている引数のコレクション。</span><span class="sxs-lookup"><span data-stu-id="3d0da-117">A collection of arguments associated with this activity query.</span></span>|  
|[\<states>](states.md)|<span data-ttu-id="3d0da-118">追跡レコードを生成する必要がある定期受信済みアクティビティの状態を含む構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="3d0da-118">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[\<states>](states.md)|<span data-ttu-id="3d0da-119">このアクティビティ クエリに関連付けられている変数のコレクション。</span><span class="sxs-lookup"><span data-stu-id="3d0da-119">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3d0da-120">親要素</span><span class="sxs-lookup"><span data-stu-id="3d0da-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3d0da-121">要素</span><span class="sxs-lookup"><span data-stu-id="3d0da-121">Element</span></span>|<span data-ttu-id="3d0da-122">Description</span><span class="sxs-lookup"><span data-stu-id="3d0da-122">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="3d0da-123">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する構成要素の一覧を表します。</span><span class="sxs-lookup"><span data-stu-id="3d0da-123">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="3d0da-124">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="3d0da-124">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d0da-125">解説</span><span class="sxs-lookup"><span data-stu-id="3d0da-125">Remarks</span></span>  
 <span data-ttu-id="3d0da-126">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="3d0da-126">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="3d0da-127">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="3d0da-127">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="3d0da-128">、、およびの各要素を使用して、 [\<arguments>](arguments.md) [\<states>](states.md) [\<states>](states.md) ワークフロー内の任意のアクティビティから任意の変数または引数を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="3d0da-128">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="3d0da-129">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="3d0da-129">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="3d0da-130">変数と引数は、ActivityStateRecord でのみ抽出できるため、を使用して追跡プロファイル内でサブスクライブされ [\<activityStateQuery>](activitystatequery.md) ます。</span><span class="sxs-lookup"><span data-stu-id="3d0da-130">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3d0da-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d0da-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3d0da-132">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="3d0da-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3d0da-133">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="3d0da-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
