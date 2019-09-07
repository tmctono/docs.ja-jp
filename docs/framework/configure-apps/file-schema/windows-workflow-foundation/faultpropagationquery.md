---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: 6b43a570b4d4534adce1ef5ab394849651e3ac0e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398714"
---
# <a name="faultpropagationquery"></a><span data-ttu-id="f9221-101">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="f9221-101">\<faultPropagationQuery></span></span>

<span data-ttu-id="f9221-102">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用するクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="f9221-102">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f9221-103">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="f9221-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="f9221-104">1 つのアクティビティ内で発生したエラーの処理は、このようなクエリを使用して追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9221-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="f9221-105">追跡参加要素がエラー伝達レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="f9221-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="f9221-106">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9221-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="f9221-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f9221-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f9221-108">&nbsp;&nbsp;[ **\<system.ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="f9221-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="f9221-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="f9221-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="f9221-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="f9221-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="f9221-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="f9221-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="f9221-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<faultPropagationQueries >** ](faultpropagationqueries.md)</span><span class="sxs-lookup"><span data-stu-id="f9221-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries.md)</span></span>\
<span data-ttu-id="f9221-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<faultPropagationQuery >**</span><span class="sxs-lookup"><span data-stu-id="f9221-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f9221-114">構文</span><span class="sxs-lookup"><span data-stu-id="f9221-114">Syntax</span></span>

```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String"
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f9221-115">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f9221-115">Attributes and Elements</span></span>

<span data-ttu-id="f9221-116">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9221-116">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f9221-117">属性</span><span class="sxs-lookup"><span data-stu-id="f9221-117">Attributes</span></span>

|<span data-ttu-id="f9221-118">属性</span><span class="sxs-lookup"><span data-stu-id="f9221-118">Attribute</span></span>|<span data-ttu-id="f9221-119">説明</span><span class="sxs-lookup"><span data-stu-id="f9221-119">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="f9221-120">activityName</span><span class="sxs-lookup"><span data-stu-id="f9221-120">activityName</span></span>|<span data-ttu-id="f9221-121">エラーを伝達したエラーハンドラーアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="f9221-121">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="f9221-122">既定値は \* で、すべてのアクティビティについてエラー伝達レコードが返されることを示します。</span><span class="sxs-lookup"><span data-stu-id="f9221-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="f9221-123">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="f9221-123">faultHandlerActivityName</span></span>|<span data-ttu-id="f9221-124">エラーの原因となったアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="f9221-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f9221-125">子要素</span><span class="sxs-lookup"><span data-stu-id="f9221-125">Child Elements</span></span>

<span data-ttu-id="f9221-126">なし。</span><span class="sxs-lookup"><span data-stu-id="f9221-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f9221-127">親要素</span><span class="sxs-lookup"><span data-stu-id="f9221-127">Parent Elements</span></span>

|<span data-ttu-id="f9221-128">要素</span><span class="sxs-lookup"><span data-stu-id="f9221-128">Element</span></span>|<span data-ttu-id="f9221-129">説明</span><span class="sxs-lookup"><span data-stu-id="f9221-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f9221-130">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="f9221-130">\<faultPropagationQueries></span></span>](faultpropagationqueries.md)|<span data-ttu-id="f9221-131">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用する、構成要素の一覧を表します。</span><span class="sxs-lookup"><span data-stu-id="f9221-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f9221-132">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="f9221-132">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="f9221-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9221-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f9221-134">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="f9221-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f9221-135">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="f9221-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
