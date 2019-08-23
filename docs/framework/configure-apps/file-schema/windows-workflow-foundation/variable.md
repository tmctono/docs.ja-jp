---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: a8f66f950db1edf8cd6ec21400785fb7e01b878e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947278"
---
# <a name="variable"></a><span data-ttu-id="c4378-101">\<変数 ></span><span class="sxs-lookup"><span data-stu-id="c4378-101">\<variable></span></span>
<span data-ttu-id="c4378-102">このアクティビティ クエリに関連付けられている変数のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="c4378-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="c4378-103">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4378-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="c4378-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c4378-104">\<system.serviceModel></span></span>  
<span data-ttu-id="c4378-105">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="c4378-105">\<tracking></span></span>  
<span data-ttu-id="c4378-106">\<プロファイル ></span><span class="sxs-lookup"><span data-stu-id="c4378-106">\<profiles></span></span>  
<span data-ttu-id="c4378-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="c4378-107">\<trackingProfile></span></span>  
<span data-ttu-id="c4378-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="c4378-108">\<workflow></span></span>  
<span data-ttu-id="c4378-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="c4378-109">\<activityStateQueries></span></span>  
<span data-ttu-id="c4378-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="c4378-110">\<activityStateQuery></span></span>  
<span data-ttu-id="c4378-111">\<変数 ></span><span class="sxs-lookup"><span data-stu-id="c4378-111">\<variables></span></span>  
<span data-ttu-id="c4378-112">\<変数 ></span><span class="sxs-lookup"><span data-stu-id="c4378-112">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4378-113">構文</span><span class="sxs-lookup"><span data-stu-id="c4378-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4378-114">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c4378-114">Attributes and Elements</span></span>  
 <span data-ttu-id="c4378-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4378-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4378-116">属性</span><span class="sxs-lookup"><span data-stu-id="c4378-116">Attributes</span></span>  
  
|<span data-ttu-id="c4378-117">属性</span><span class="sxs-lookup"><span data-stu-id="c4378-117">Attribute</span></span>|<span data-ttu-id="c4378-118">説明</span><span class="sxs-lookup"><span data-stu-id="c4378-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c4378-119">name</span><span class="sxs-lookup"><span data-stu-id="c4378-119">name</span></span>|<span data-ttu-id="c4378-120">変数の名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="c4378-120">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4378-121">子要素</span><span class="sxs-lookup"><span data-stu-id="c4378-121">Child Elements</span></span>  
 <span data-ttu-id="c4378-122">なし。</span><span class="sxs-lookup"><span data-stu-id="c4378-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c4378-123">親要素</span><span class="sxs-lookup"><span data-stu-id="c4378-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c4378-124">要素</span><span class="sxs-lookup"><span data-stu-id="c4378-124">Element</span></span>|<span data-ttu-id="c4378-125">説明</span><span class="sxs-lookup"><span data-stu-id="c4378-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c4378-126">\<変数 ></span><span class="sxs-lookup"><span data-stu-id="c4378-126">\<variable></span></span>](variable.md)|<span data-ttu-id="c4378-127">アクティビティ状態クエリに関連付けられている変数。</span><span class="sxs-lookup"><span data-stu-id="c4378-127">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4378-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="c4378-128">Remarks</span></span>  
 <span data-ttu-id="c4378-129">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="c4378-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="c4378-130">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="c4378-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="c4378-131">引数 >、 [ \<](arguments.md) [ states\<>](states.md)および[ states>要素を使用して、ワークフロー内の任意の\<](states.md)アクティビティから任意の変数または引数を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="c4378-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="c4378-132">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="c4378-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="c4378-133">変数と引数は activitystaterecord でのみ抽出できるため、 [ \<activitystatequery >](activitystatequery.md)を使用して追跡プロファイル内でサブスクライブされます。</span><span class="sxs-lookup"><span data-stu-id="c4378-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c4378-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4378-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c4378-135">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="c4378-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c4378-136">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="c4378-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
