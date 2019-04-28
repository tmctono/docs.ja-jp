---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: c85f3c57739c48566c97c8b1debfb7f2c3912bdf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61613522"
---
# <a name="variable"></a><span data-ttu-id="178ac-101">\<変数 ></span><span class="sxs-lookup"><span data-stu-id="178ac-101">\<variable></span></span>
<span data-ttu-id="178ac-102">このアクティビティ クエリに関連付けられている変数のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="178ac-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="178ac-103">追跡プロファイルのクエリの詳細については、次を参照してください。[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)します。</span><span class="sxs-lookup"><span data-stu-id="178ac-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="178ac-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="178ac-104">\<system.serviceModel></span></span>  
<span data-ttu-id="178ac-105">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="178ac-105">\<tracking></span></span>  
<span data-ttu-id="178ac-106">\<プロファイル ></span><span class="sxs-lookup"><span data-stu-id="178ac-106">\<profiles></span></span>  
<span data-ttu-id="178ac-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="178ac-107">\<trackingProfile></span></span>  
<span data-ttu-id="178ac-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="178ac-108">\<workflow></span></span>  
<span data-ttu-id="178ac-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="178ac-109">\<activityStateQueries></span></span>  
<span data-ttu-id="178ac-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="178ac-110">\<activityStateQuery></span></span>  
<span data-ttu-id="178ac-111">\<variables></span><span class="sxs-lookup"><span data-stu-id="178ac-111">\<variables></span></span>  
<span data-ttu-id="178ac-112">\<変数 ></span><span class="sxs-lookup"><span data-stu-id="178ac-112">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="178ac-113">構文</span><span class="sxs-lookup"><span data-stu-id="178ac-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="178ac-114">属性および要素</span><span class="sxs-lookup"><span data-stu-id="178ac-114">Attributes and Elements</span></span>  
 <span data-ttu-id="178ac-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="178ac-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="178ac-116">属性</span><span class="sxs-lookup"><span data-stu-id="178ac-116">Attributes</span></span>  
  
|<span data-ttu-id="178ac-117">属性</span><span class="sxs-lookup"><span data-stu-id="178ac-117">Attribute</span></span>|<span data-ttu-id="178ac-118">説明</span><span class="sxs-lookup"><span data-stu-id="178ac-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="178ac-119">name</span><span class="sxs-lookup"><span data-stu-id="178ac-119">name</span></span>|<span data-ttu-id="178ac-120">変数の名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="178ac-120">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="178ac-121">子要素</span><span class="sxs-lookup"><span data-stu-id="178ac-121">Child Elements</span></span>  
 <span data-ttu-id="178ac-122">なし。</span><span class="sxs-lookup"><span data-stu-id="178ac-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="178ac-123">親要素</span><span class="sxs-lookup"><span data-stu-id="178ac-123">Parent Elements</span></span>  
  
|<span data-ttu-id="178ac-124">要素</span><span class="sxs-lookup"><span data-stu-id="178ac-124">Element</span></span>|<span data-ttu-id="178ac-125">説明</span><span class="sxs-lookup"><span data-stu-id="178ac-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="178ac-126">\<variable></span><span class="sxs-lookup"><span data-stu-id="178ac-126">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="178ac-127">アクティビティ状態クエリに関連付けられている変数。</span><span class="sxs-lookup"><span data-stu-id="178ac-127">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="178ac-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="178ac-128">Remarks</span></span>  
 <span data-ttu-id="178ac-129">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="178ac-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="178ac-130">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="178ac-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="178ac-131">使用することができます、 [\<引数 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)、 [\<状態 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)と[\<状態 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)任意の変数または引数を抽出する要素ワークフロー内の任意のアクティビティから</span><span class="sxs-lookup"><span data-stu-id="178ac-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="178ac-132">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="178ac-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="178ac-133">ActivityStateRecord でのみ抽出できるし、追跡のため購読中の変数と引数を使用してプロファイル[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)します。</span><span class="sxs-lookup"><span data-stu-id="178ac-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="178ac-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="178ac-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="178ac-135">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="178ac-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="178ac-136">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="178ac-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
