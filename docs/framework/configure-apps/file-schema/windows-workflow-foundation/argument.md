---
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: f2aeb61e2e72f5bd6a696c031279f2c57907166b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946148"
---
# <a name="argument"></a><span data-ttu-id="7930f-101">\<引数 ></span><span class="sxs-lookup"><span data-stu-id="7930f-101">\<argument></span></span>
<span data-ttu-id="7930f-102">アクティビティ状態クエリに関連付けられている引数を表す構成要素。</span><span class="sxs-lookup"><span data-stu-id="7930f-102">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="7930f-103">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7930f-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="7930f-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7930f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="7930f-105">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="7930f-105">\<tracking></span></span>  
<span data-ttu-id="7930f-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="7930f-106">\<trackingProfile></span></span>  
<span data-ttu-id="7930f-107">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="7930f-107">\<workflow></span></span>  
<span data-ttu-id="7930f-108">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="7930f-108">\<activityStateQueries></span></span>  
<span data-ttu-id="7930f-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="7930f-109">\<activityStateQuery></span></span>  
<span data-ttu-id="7930f-110">\<引数 ></span><span class="sxs-lookup"><span data-stu-id="7930f-110">\<arguments></span></span>  
<span data-ttu-id="7930f-111">\<引数 ></span><span class="sxs-lookup"><span data-stu-id="7930f-111">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7930f-112">構文</span><span class="sxs-lookup"><span data-stu-id="7930f-112">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7930f-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7930f-113">Attributes and Elements</span></span>  
 <span data-ttu-id="7930f-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7930f-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7930f-115">属性</span><span class="sxs-lookup"><span data-stu-id="7930f-115">Attributes</span></span>  
  
|<span data-ttu-id="7930f-116">属性</span><span class="sxs-lookup"><span data-stu-id="7930f-116">Attribute</span></span>|<span data-ttu-id="7930f-117">説明</span><span class="sxs-lookup"><span data-stu-id="7930f-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7930f-118">name</span><span class="sxs-lookup"><span data-stu-id="7930f-118">name</span></span>|<span data-ttu-id="7930f-119">この引数の名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="7930f-119">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7930f-120">子要素</span><span class="sxs-lookup"><span data-stu-id="7930f-120">Child Elements</span></span>  
 <span data-ttu-id="7930f-121">なし。</span><span class="sxs-lookup"><span data-stu-id="7930f-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7930f-122">親要素</span><span class="sxs-lookup"><span data-stu-id="7930f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7930f-123">要素</span><span class="sxs-lookup"><span data-stu-id="7930f-123">Element</span></span>|<span data-ttu-id="7930f-124">説明</span><span class="sxs-lookup"><span data-stu-id="7930f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7930f-125">\<引数 ></span><span class="sxs-lookup"><span data-stu-id="7930f-125">\<arguments></span></span>](arguments.md)|<span data-ttu-id="7930f-126">このアクティビティ クエリに関連付けられている引数のコレクション。</span><span class="sxs-lookup"><span data-stu-id="7930f-126">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7930f-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="7930f-127">Remarks</span></span>  
 <span data-ttu-id="7930f-128">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="7930f-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="7930f-129">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="7930f-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="7930f-130">引数 >、 [ \<](arguments.md) [ states\<>](states.md)および[ states>要素を使用して、ワークフロー内の任意の\<](states.md)アクティビティから任意の変数または引数を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="7930f-130">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="7930f-131">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="7930f-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="7930f-132">変数と引数は activitystaterecord でのみ抽出できるため、 [ \<activitystatequery >](activitystatequery.md)を使用して追跡プロファイル内でサブスクライブされます。</span><span class="sxs-lookup"><span data-stu-id="7930f-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7930f-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="7930f-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="7930f-134">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="7930f-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7930f-135">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="7930f-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
