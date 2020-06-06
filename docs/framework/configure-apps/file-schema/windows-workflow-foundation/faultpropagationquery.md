---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: 6b43a570b4d4534adce1ef5ab394849651e3ac0e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398714"
---
# \<faultPropagationQuery>

<span data-ttu-id="a7656-101">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用するクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="a7656-101">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="a7656-102">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="a7656-102">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="a7656-103">1 つのアクティビティ内で発生したエラーの処理は、このようなクエリを使用して追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7656-103">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="a7656-104">追跡参加要素がエラー伝達レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="a7656-104">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="a7656-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7656-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**

## <a name="syntax"></a><span data-ttu-id="a7656-106">構文</span><span class="sxs-lookup"><span data-stu-id="a7656-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="a7656-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a7656-107">Attributes and Elements</span></span>

<span data-ttu-id="a7656-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a7656-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a7656-109">属性</span><span class="sxs-lookup"><span data-stu-id="a7656-109">Attributes</span></span>

|<span data-ttu-id="a7656-110">属性</span><span class="sxs-lookup"><span data-stu-id="a7656-110">Attribute</span></span>|<span data-ttu-id="a7656-111">説明</span><span class="sxs-lookup"><span data-stu-id="a7656-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="a7656-112">activityName</span><span class="sxs-lookup"><span data-stu-id="a7656-112">activityName</span></span>|<span data-ttu-id="a7656-113">エラーを伝達したエラーハンドラーアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="a7656-113">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="a7656-114">既定値は \* で、すべてのアクティビティについてエラー伝達レコードが返されることを示します。</span><span class="sxs-lookup"><span data-stu-id="a7656-114">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="a7656-115">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="a7656-115">faultHandlerActivityName</span></span>|<span data-ttu-id="a7656-116">エラーの原因となったアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="a7656-116">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a7656-117">子要素</span><span class="sxs-lookup"><span data-stu-id="a7656-117">Child Elements</span></span>

<span data-ttu-id="a7656-118">なし。</span><span class="sxs-lookup"><span data-stu-id="a7656-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a7656-119">親要素</span><span class="sxs-lookup"><span data-stu-id="a7656-119">Parent Elements</span></span>

|<span data-ttu-id="a7656-120">要素</span><span class="sxs-lookup"><span data-stu-id="a7656-120">Element</span></span>|<span data-ttu-id="a7656-121">Description</span><span class="sxs-lookup"><span data-stu-id="a7656-121">Description</span></span>|
|-------------|-----------------|
|[\<faultPropagationQueries>](faultpropagationqueries.md)|<span data-ttu-id="a7656-122">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用する、構成要素の一覧を表します。</span><span class="sxs-lookup"><span data-stu-id="a7656-122">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="a7656-123">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="a7656-123">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="a7656-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7656-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a7656-125">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="a7656-125">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a7656-126">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="a7656-126">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
