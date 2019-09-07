---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: 5878720f51f4b5cfe3163abf316a867ccda31342
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397776"
---
# <a name="variable"></a><span data-ttu-id="1154f-101">\<変数 ></span><span class="sxs-lookup"><span data-stu-id="1154f-101">\<variable></span></span>
<span data-ttu-id="1154f-102">このアクティビティ クエリに関連付けられている変数のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="1154f-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="1154f-103">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1154f-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="1154f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1154f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1154f-105">&nbsp;&nbsp;[ **\<system.ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1154f-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="1154f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="1154f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="1154f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="1154f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="1154f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1154f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="1154f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityStateQueries >** ](activitystatequeries.md)</span><span class="sxs-lookup"><span data-stu-id="1154f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)</span></span>\
<span data-ttu-id="1154f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityStateQuery >** ](activitystatequery.md)</span><span class="sxs-lookup"><span data-stu-id="1154f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)</span></span>\
<span data-ttu-id="1154f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<変数 >** ](variables.md)</span><span class="sxs-lookup"><span data-stu-id="1154f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<variables>**](variables.md)</span></span>\
<span data-ttu-id="1154f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<変数 >**</span><span class="sxs-lookup"><span data-stu-id="1154f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<variable>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1154f-113">構文</span><span class="sxs-lookup"><span data-stu-id="1154f-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1154f-114">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1154f-114">Attributes and Elements</span></span>  
 <span data-ttu-id="1154f-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1154f-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1154f-116">属性</span><span class="sxs-lookup"><span data-stu-id="1154f-116">Attributes</span></span>  
  
|<span data-ttu-id="1154f-117">属性</span><span class="sxs-lookup"><span data-stu-id="1154f-117">Attribute</span></span>|<span data-ttu-id="1154f-118">説明</span><span class="sxs-lookup"><span data-stu-id="1154f-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1154f-119">name</span><span class="sxs-lookup"><span data-stu-id="1154f-119">name</span></span>|<span data-ttu-id="1154f-120">変数の名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="1154f-120">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1154f-121">子要素</span><span class="sxs-lookup"><span data-stu-id="1154f-121">Child Elements</span></span>  
 <span data-ttu-id="1154f-122">なし。</span><span class="sxs-lookup"><span data-stu-id="1154f-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1154f-123">親要素</span><span class="sxs-lookup"><span data-stu-id="1154f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1154f-124">要素</span><span class="sxs-lookup"><span data-stu-id="1154f-124">Element</span></span>|<span data-ttu-id="1154f-125">説明</span><span class="sxs-lookup"><span data-stu-id="1154f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1154f-126">\<変数 ></span><span class="sxs-lookup"><span data-stu-id="1154f-126">\<variable></span></span>](variable.md)|<span data-ttu-id="1154f-127">アクティビティ状態クエリに関連付けられている変数。</span><span class="sxs-lookup"><span data-stu-id="1154f-127">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1154f-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="1154f-128">Remarks</span></span>  
 <span data-ttu-id="1154f-129">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="1154f-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="1154f-130">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="1154f-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="1154f-131">引数 >、 [ \<](arguments.md) [ states\<>](states.md)および[ states>要素を使用して、ワークフロー内の任意の\<](states.md)アクティビティから任意の変数または引数を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="1154f-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="1154f-132">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="1154f-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="1154f-133">変数と引数は activitystaterecord でのみ抽出できるため、 [ \<activitystatequery >](activitystatequery.md)を使用して追跡プロファイル内でサブスクライブされます。</span><span class="sxs-lookup"><span data-stu-id="1154f-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1154f-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="1154f-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1154f-135">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="1154f-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1154f-136">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="1154f-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
