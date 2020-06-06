---
title: <faultPropagationQuery>WCF の
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: a6ef4e198caec4a1f21cedf2ff46d390aeaa2d3b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855332"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="03124-102">\<faultPropagationQuery>WCF の</span><span class="sxs-lookup"><span data-stu-id="03124-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="03124-103">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用するクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="03124-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="03124-104">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="03124-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="03124-105">1 つのアクティビティ内で発生したエラーの処理は、このようなクエリを使用して追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03124-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="03124-106">追跡参加要素がエラー伝達レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="03124-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="03124-107">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03124-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**  

## <a name="syntax"></a><span data-ttu-id="03124-108">構文</span><span class="sxs-lookup"><span data-stu-id="03124-108">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="03124-109">属性と要素</span><span class="sxs-lookup"><span data-stu-id="03124-109">Attributes and elements</span></span>

<span data-ttu-id="03124-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="03124-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="03124-111">属性</span><span class="sxs-lookup"><span data-stu-id="03124-111">Attributes</span></span>

|<span data-ttu-id="03124-112">属性</span><span class="sxs-lookup"><span data-stu-id="03124-112">Attribute</span></span>|<span data-ttu-id="03124-113">説明</span><span class="sxs-lookup"><span data-stu-id="03124-113">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="03124-114">エラーを伝達したエラーハンドラーアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="03124-114">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="03124-115">既定値は \* で、すべてのアクティビティについてエラー伝達レコードが返されることを示します。</span><span class="sxs-lookup"><span data-stu-id="03124-115">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="03124-116">エラーの原因となったアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="03124-116">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="03124-117">子要素</span><span class="sxs-lookup"><span data-stu-id="03124-117">Child elements</span></span>

<span data-ttu-id="03124-118">なし。</span><span class="sxs-lookup"><span data-stu-id="03124-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="03124-119">親要素</span><span class="sxs-lookup"><span data-stu-id="03124-119">Parent elements</span></span>

|<span data-ttu-id="03124-120">要素</span><span class="sxs-lookup"><span data-stu-id="03124-120">Element</span></span>|<span data-ttu-id="03124-121">Description</span><span class="sxs-lookup"><span data-stu-id="03124-121">Description</span></span>|
|-------------|-----------------|
|[\<faultPropagationQueries>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="03124-122">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用する、構成要素の一覧を表します。</span><span class="sxs-lookup"><span data-stu-id="03124-122">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="03124-123">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="03124-123">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="03124-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="03124-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="03124-125">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="03124-125">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="03124-126">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="03124-126">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
