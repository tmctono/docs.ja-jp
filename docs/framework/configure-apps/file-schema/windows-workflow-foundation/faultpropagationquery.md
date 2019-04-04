---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: f3e281ff8a9de9be41dd6ad9d01ab52798d8e89e
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679360"
---
# <a name="faultpropagationquery"></a><span data-ttu-id="a9ace-101">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="a9ace-101">\<faultPropagationQuery></span></span>

<span data-ttu-id="a9ace-102">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用するクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="a9ace-102">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="a9ace-103">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="a9ace-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="a9ace-104">1 つのアクティビティ内で発生したエラーの処理は、このようなクエリを使用して追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9ace-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="a9ace-105">追跡参加要素がエラー伝達レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="a9ace-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="a9ace-106">追跡プロファイルのクエリの詳細については、[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9ace-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="a9ace-107">\<system.serviceModel>\\</span><span class="sxs-lookup"><span data-stu-id="a9ace-107">\<system.serviceModel>\\</span></span>
<span data-ttu-id="a9ace-108">\<追跡 > \\</span><span class="sxs-lookup"><span data-stu-id="a9ace-108">\<tracking>\\</span></span>
<span data-ttu-id="a9ace-109">\<trackingProfile>\\</span><span class="sxs-lookup"><span data-stu-id="a9ace-109">\<trackingProfile>\\</span></span>
<span data-ttu-id="a9ace-110">\<workflow>\\</span><span class="sxs-lookup"><span data-stu-id="a9ace-110">\<workflow>\\</span></span>
<span data-ttu-id="a9ace-111">\<faultPropagationQueries>\\</span><span class="sxs-lookup"><span data-stu-id="a9ace-111">\<faultPropagationQueries>\\</span></span>
<span data-ttu-id="a9ace-112">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="a9ace-112">\<faultPropagationQuery></span></span>

## <a name="syntax"></a><span data-ttu-id="a9ace-113">構文</span><span class="sxs-lookup"><span data-stu-id="a9ace-113">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="a9ace-114">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a9ace-114">Attributes and Elements</span></span>

<span data-ttu-id="a9ace-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a9ace-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a9ace-116">属性</span><span class="sxs-lookup"><span data-stu-id="a9ace-116">Attributes</span></span>

|<span data-ttu-id="a9ace-117">属性</span><span class="sxs-lookup"><span data-stu-id="a9ace-117">Attribute</span></span>|<span data-ttu-id="a9ace-118">説明</span><span class="sxs-lookup"><span data-stu-id="a9ace-118">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="a9ace-119">activityName</span><span class="sxs-lookup"><span data-stu-id="a9ace-119">activityName</span></span>|<span data-ttu-id="a9ace-120">エラーを伝達したエラー ハンドラー アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="a9ace-120">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="a9ace-121">既定値は \* で、すべてのアクティビティについてエラー伝達レコードが返されることを示します。</span><span class="sxs-lookup"><span data-stu-id="a9ace-121">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="a9ace-122">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="a9ace-122">faultHandlerActivityName</span></span>|<span data-ttu-id="a9ace-123">エラーの原因となったアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="a9ace-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a9ace-124">子要素</span><span class="sxs-lookup"><span data-stu-id="a9ace-124">Child Elements</span></span>

<span data-ttu-id="a9ace-125">なし。</span><span class="sxs-lookup"><span data-stu-id="a9ace-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a9ace-126">親要素</span><span class="sxs-lookup"><span data-stu-id="a9ace-126">Parent Elements</span></span>

|<span data-ttu-id="a9ace-127">要素</span><span class="sxs-lookup"><span data-stu-id="a9ace-127">Element</span></span>|<span data-ttu-id="a9ace-128">説明</span><span class="sxs-lookup"><span data-stu-id="a9ace-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a9ace-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="a9ace-129">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="a9ace-130">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用する、構成要素の一覧を表します。</span><span class="sxs-lookup"><span data-stu-id="a9ace-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="a9ace-131">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="a9ace-131">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="a9ace-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9ace-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a9ace-133">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="a9ace-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a9ace-134">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="a9ace-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
