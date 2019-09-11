---
title: <faultPropagationQuery>WCF の
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: a6ef4e198caec4a1f21cedf2ff46d390aeaa2d3b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855332"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="f885a-102">\<WCF の faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="f885a-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="f885a-103">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用するクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="f885a-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f885a-104">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="f885a-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="f885a-105">1 つのアクティビティ内で発生したエラーの処理は、このようなクエリを使用して追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f885a-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="f885a-106">追跡参加要素がエラー伝達レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="f885a-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="f885a-107">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f885a-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="f885a-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f885a-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f885a-109">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f885a-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f885a-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f885a-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="f885a-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<プロファイル >** </span><span class="sxs-lookup"><span data-stu-id="f885a-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="f885a-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f885a-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="f885a-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f885a-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="f885a-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<faultPropagationQueries >** ](faultpropagationqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f885a-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries-of-wcf.md)</span></span>\
<span data-ttu-id="f885a-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<faultPropagationQuery >**</span><span class="sxs-lookup"><span data-stu-id="f885a-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="f885a-116">構文</span><span class="sxs-lookup"><span data-stu-id="f885a-116">Syntax</span></span>

```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String" />
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f885a-117">属性と要素</span><span class="sxs-lookup"><span data-stu-id="f885a-117">Attributes and elements</span></span>

<span data-ttu-id="f885a-118">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f885a-118">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f885a-119">属性</span><span class="sxs-lookup"><span data-stu-id="f885a-119">Attributes</span></span>

|<span data-ttu-id="f885a-120">属性</span><span class="sxs-lookup"><span data-stu-id="f885a-120">Attribute</span></span>|<span data-ttu-id="f885a-121">説明</span><span class="sxs-lookup"><span data-stu-id="f885a-121">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="f885a-122">エラーを伝達したエラーハンドラーアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="f885a-122">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="f885a-123">既定値は\*で、すべてのアクティビティについてエラー伝達レコードが返されることを示します。</span><span class="sxs-lookup"><span data-stu-id="f885a-123">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="f885a-124">エラーの原因となったアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="f885a-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f885a-125">子要素</span><span class="sxs-lookup"><span data-stu-id="f885a-125">Child elements</span></span>

<span data-ttu-id="f885a-126">なし。</span><span class="sxs-lookup"><span data-stu-id="f885a-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f885a-127">親要素</span><span class="sxs-lookup"><span data-stu-id="f885a-127">Parent elements</span></span>

|<span data-ttu-id="f885a-128">要素</span><span class="sxs-lookup"><span data-stu-id="f885a-128">Element</span></span>|<span data-ttu-id="f885a-129">説明</span><span class="sxs-lookup"><span data-stu-id="f885a-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f885a-130">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="f885a-130">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="f885a-131">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用する、構成要素の一覧を表します。</span><span class="sxs-lookup"><span data-stu-id="f885a-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f885a-132">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="f885a-132">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="f885a-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="f885a-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f885a-134">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="f885a-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f885a-135">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="f885a-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
