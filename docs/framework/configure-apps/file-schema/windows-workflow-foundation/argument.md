---
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: ed08f5533cd6b3839775d061452cb17110cc627e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398898"
---
# <a name="argument"></a><span data-ttu-id="da535-101">\<引数 ></span><span class="sxs-lookup"><span data-stu-id="da535-101">\<argument></span></span>
<span data-ttu-id="da535-102">アクティビティ状態クエリに関連付けられている引数を表す構成要素。</span><span class="sxs-lookup"><span data-stu-id="da535-102">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="da535-103">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da535-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="da535-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="da535-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="da535-105">&nbsp;&nbsp;[ **\<system.ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="da535-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="da535-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="da535-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="da535-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="da535-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="da535-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="da535-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="da535-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityStateQueries >** ](activitystatequeries.md)</span><span class="sxs-lookup"><span data-stu-id="da535-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)</span></span>\
<span data-ttu-id="da535-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityStateQuery >** ](activitystatequery.md)</span><span class="sxs-lookup"><span data-stu-id="da535-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)</span></span>\
<span data-ttu-id="da535-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<引数 >** ](arguments.md)</span><span class="sxs-lookup"><span data-stu-id="da535-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<arguments>**](arguments.md)</span></span>\
<span data-ttu-id="da535-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<引数 >**</span><span class="sxs-lookup"><span data-stu-id="da535-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<argument>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da535-113">構文</span><span class="sxs-lookup"><span data-stu-id="da535-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da535-114">属性および要素</span><span class="sxs-lookup"><span data-stu-id="da535-114">Attributes and Elements</span></span>  
 <span data-ttu-id="da535-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="da535-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da535-116">属性</span><span class="sxs-lookup"><span data-stu-id="da535-116">Attributes</span></span>  
  
|<span data-ttu-id="da535-117">属性</span><span class="sxs-lookup"><span data-stu-id="da535-117">Attribute</span></span>|<span data-ttu-id="da535-118">説明</span><span class="sxs-lookup"><span data-stu-id="da535-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="da535-119">name</span><span class="sxs-lookup"><span data-stu-id="da535-119">name</span></span>|<span data-ttu-id="da535-120">この引数の名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="da535-120">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da535-121">子要素</span><span class="sxs-lookup"><span data-stu-id="da535-121">Child Elements</span></span>  
 <span data-ttu-id="da535-122">なし。</span><span class="sxs-lookup"><span data-stu-id="da535-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da535-123">親要素</span><span class="sxs-lookup"><span data-stu-id="da535-123">Parent Elements</span></span>  
  
|<span data-ttu-id="da535-124">要素</span><span class="sxs-lookup"><span data-stu-id="da535-124">Element</span></span>|<span data-ttu-id="da535-125">説明</span><span class="sxs-lookup"><span data-stu-id="da535-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da535-126">\<引数 ></span><span class="sxs-lookup"><span data-stu-id="da535-126">\<arguments></span></span>](arguments.md)|<span data-ttu-id="da535-127">このアクティビティ クエリに関連付けられている引数のコレクション。</span><span class="sxs-lookup"><span data-stu-id="da535-127">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da535-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="da535-128">Remarks</span></span>  
 <span data-ttu-id="da535-129">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="da535-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="da535-130">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="da535-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="da535-131">引数 >、 [ \<](arguments.md) [ states\<>](states.md)および[ states>要素を使用して、ワークフロー内の任意の\<](states.md)アクティビティから任意の変数または引数を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="da535-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="da535-132">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="da535-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="da535-133">変数と引数は activitystaterecord でのみ抽出できるため、 [ \<activitystatequery >](activitystatequery.md)を使用して追跡プロファイル内でサブスクライブされます。</span><span class="sxs-lookup"><span data-stu-id="da535-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="da535-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="da535-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="da535-135">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="da535-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="da535-136">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="da535-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
