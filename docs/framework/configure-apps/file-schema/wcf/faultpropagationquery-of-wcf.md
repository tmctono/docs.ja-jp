---
title: <faultPropagationQuery> WCF の
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: e5793852d49a052d05f6cb2f4efbe166d67afc62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701048"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="7d81c-102">\<faultPropagationQuery > の WCF</span><span class="sxs-lookup"><span data-stu-id="7d81c-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="7d81c-103">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用するクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="7d81c-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="7d81c-104">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="7d81c-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="7d81c-105">1 つのアクティビティ内で発生したエラーの処理は、このようなクエリを使用して追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d81c-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="7d81c-106">追跡参加要素がエラー伝達レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="7d81c-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="7d81c-107">追跡プロファイルのクエリの詳細については、次を参照してください。[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)します。</span><span class="sxs-lookup"><span data-stu-id="7d81c-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="7d81c-108">\<system.serviceModel>\\</span><span class="sxs-lookup"><span data-stu-id="7d81c-108">\<system.serviceModel>\\</span></span>
<span data-ttu-id="7d81c-109">\<追跡 > \\</span><span class="sxs-lookup"><span data-stu-id="7d81c-109">\<tracking>\\</span></span>
<span data-ttu-id="7d81c-110">\<profiles>\\</span><span class="sxs-lookup"><span data-stu-id="7d81c-110">\<profiles>\\</span></span>
<span data-ttu-id="7d81c-111">\<trackingProfile>\\</span><span class="sxs-lookup"><span data-stu-id="7d81c-111">\<trackingProfile>\\</span></span>
<span data-ttu-id="7d81c-112">\<workflow>\\</span><span class="sxs-lookup"><span data-stu-id="7d81c-112">\<workflow>\\</span></span>
<span data-ttu-id="7d81c-113">\<faultPropagationQueries>\\</span><span class="sxs-lookup"><span data-stu-id="7d81c-113">\<faultPropagationQueries>\\</span></span>
<span data-ttu-id="7d81c-114">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="7d81c-114">\<faultPropagationQuery></span></span>

## <a name="syntax"></a><span data-ttu-id="7d81c-115">構文</span><span class="sxs-lookup"><span data-stu-id="7d81c-115">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="7d81c-116">属性と要素</span><span class="sxs-lookup"><span data-stu-id="7d81c-116">Attributes and elements</span></span>

<span data-ttu-id="7d81c-117">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d81c-117">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7d81c-118">属性</span><span class="sxs-lookup"><span data-stu-id="7d81c-118">Attributes</span></span>

|<span data-ttu-id="7d81c-119">属性</span><span class="sxs-lookup"><span data-stu-id="7d81c-119">Attribute</span></span>|<span data-ttu-id="7d81c-120">説明</span><span class="sxs-lookup"><span data-stu-id="7d81c-120">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="7d81c-121">エラーを伝達したエラー ハンドラー アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="7d81c-121">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="7d81c-122">既定値は\*、すべてのアクティビティについてエラー伝達レコードが返されることを示します。</span><span class="sxs-lookup"><span data-stu-id="7d81c-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="7d81c-123">エラーの原因となったアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="7d81c-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="7d81c-124">子要素</span><span class="sxs-lookup"><span data-stu-id="7d81c-124">Child elements</span></span>

<span data-ttu-id="7d81c-125">なし。</span><span class="sxs-lookup"><span data-stu-id="7d81c-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7d81c-126">親要素</span><span class="sxs-lookup"><span data-stu-id="7d81c-126">Parent elements</span></span>

|<span data-ttu-id="7d81c-127">要素</span><span class="sxs-lookup"><span data-stu-id="7d81c-127">Element</span></span>|<span data-ttu-id="7d81c-128">説明</span><span class="sxs-lookup"><span data-stu-id="7d81c-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7d81c-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="7d81c-129">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="7d81c-130">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用する、構成要素の一覧を表します。</span><span class="sxs-lookup"><span data-stu-id="7d81c-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="7d81c-131">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="7d81c-131">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="7d81c-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d81c-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="7d81c-133">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="7d81c-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7d81c-134">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="7d81c-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
