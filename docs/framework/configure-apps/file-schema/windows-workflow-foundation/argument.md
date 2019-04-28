---
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: a920d60d703fe262bee96d75c420c526d54f88ab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790326"
---
# <a name="argument"></a><span data-ttu-id="ddba9-101">\<argument></span><span class="sxs-lookup"><span data-stu-id="ddba9-101">\<argument></span></span>
<span data-ttu-id="ddba9-102">アクティビティ状態クエリに関連付けられている引数を表す構成要素。</span><span class="sxs-lookup"><span data-stu-id="ddba9-102">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="ddba9-103">追跡プロファイルのクエリの詳細については、次を参照してください。[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)します。</span><span class="sxs-lookup"><span data-stu-id="ddba9-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="ddba9-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ddba9-104">\<system.serviceModel></span></span>  
<span data-ttu-id="ddba9-105">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="ddba9-105">\<tracking></span></span>  
<span data-ttu-id="ddba9-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ddba9-106">\<trackingProfile></span></span>  
<span data-ttu-id="ddba9-107">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="ddba9-107">\<workflow></span></span>  
<span data-ttu-id="ddba9-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="ddba9-108">\<activityStateQueries></span></span>  
<span data-ttu-id="ddba9-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="ddba9-109">\<activityStateQuery></span></span>  
<span data-ttu-id="ddba9-110">\<arguments></span><span class="sxs-lookup"><span data-stu-id="ddba9-110">\<arguments></span></span>  
<span data-ttu-id="ddba9-111">\<argument></span><span class="sxs-lookup"><span data-stu-id="ddba9-111">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddba9-112">構文</span><span class="sxs-lookup"><span data-stu-id="ddba9-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ddba9-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ddba9-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ddba9-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ddba9-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ddba9-115">属性</span><span class="sxs-lookup"><span data-stu-id="ddba9-115">Attributes</span></span>  
  
|<span data-ttu-id="ddba9-116">属性</span><span class="sxs-lookup"><span data-stu-id="ddba9-116">Attribute</span></span>|<span data-ttu-id="ddba9-117">説明</span><span class="sxs-lookup"><span data-stu-id="ddba9-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ddba9-118">name</span><span class="sxs-lookup"><span data-stu-id="ddba9-118">name</span></span>|<span data-ttu-id="ddba9-119">この引数の名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="ddba9-119">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ddba9-120">子要素</span><span class="sxs-lookup"><span data-stu-id="ddba9-120">Child Elements</span></span>  
 <span data-ttu-id="ddba9-121">なし。</span><span class="sxs-lookup"><span data-stu-id="ddba9-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ddba9-122">親要素</span><span class="sxs-lookup"><span data-stu-id="ddba9-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ddba9-123">要素</span><span class="sxs-lookup"><span data-stu-id="ddba9-123">Element</span></span>|<span data-ttu-id="ddba9-124">説明</span><span class="sxs-lookup"><span data-stu-id="ddba9-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ddba9-125">\<arguments></span><span class="sxs-lookup"><span data-stu-id="ddba9-125">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="ddba9-126">このアクティビティ クエリに関連付けられている引数のコレクション。</span><span class="sxs-lookup"><span data-stu-id="ddba9-126">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddba9-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="ddba9-127">Remarks</span></span>  
 <span data-ttu-id="ddba9-128">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="ddba9-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="ddba9-129">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="ddba9-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="ddba9-130">使用することができます、 [\<引数 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)、 [\<状態 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)と[\<状態 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)任意の変数または引数を抽出する要素ワークフロー内の任意のアクティビティから</span><span class="sxs-lookup"><span data-stu-id="ddba9-130">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="ddba9-131">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="ddba9-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="ddba9-132">ActivityStateRecord でのみ抽出できるし、追跡のため購読中の変数と引数を使用してプロファイル[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)します。</span><span class="sxs-lookup"><span data-stu-id="ddba9-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ddba9-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="ddba9-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ddba9-134">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="ddba9-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ddba9-135">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="ddba9-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
