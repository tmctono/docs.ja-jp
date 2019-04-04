---
title: <faultPropagationQueries> WCF の
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: bc016827c5bb243bc83dbb53c1eda7eec1bfd8c4
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55280398"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="ae7e4-102">\<faultPropagationQueries > の WCF</span><span class="sxs-lookup"><span data-stu-id="ae7e4-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="ae7e4-103">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="ae7e4-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="ae7e4-104">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="ae7e4-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="ae7e4-105">1 つのアクティビティ内で発生したエラーの処理は、このようなクエリを使用して追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae7e4-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="ae7e4-106">追跡参加要素がエラー伝達レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="ae7e4-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="ae7e4-107">追跡プロファイルのクエリの詳細については、[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae7e4-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="ae7e4-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ae7e4-108">\<system.serviceModel></span></span>  
<span data-ttu-id="ae7e4-109">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="ae7e4-109">\<tracking></span></span>  
<span data-ttu-id="ae7e4-110">\<プロファイル ></span><span class="sxs-lookup"><span data-stu-id="ae7e4-110">\<profiles></span></span>  
<span data-ttu-id="ae7e4-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ae7e4-111">\<trackingProfile></span></span>  
<span data-ttu-id="ae7e4-112">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="ae7e4-112">\<workflow></span></span>  
<span data-ttu-id="ae7e4-113">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="ae7e4-113">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae7e4-114">構文</span><span class="sxs-lookup"><span data-stu-id="ae7e4-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String"/>
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae7e4-115">属性と要素</span><span class="sxs-lookup"><span data-stu-id="ae7e4-115">Attributes and elements</span></span>

<span data-ttu-id="ae7e4-116">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae7e4-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="ae7e4-117">属性</span><span class="sxs-lookup"><span data-stu-id="ae7e4-117">Attributes</span></span>

<span data-ttu-id="ae7e4-118">なし。</span><span class="sxs-lookup"><span data-stu-id="ae7e4-118">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="ae7e4-119">子要素</span><span class="sxs-lookup"><span data-stu-id="ae7e4-119">Child elements</span></span>

|<span data-ttu-id="ae7e4-120">要素</span><span class="sxs-lookup"><span data-stu-id="ae7e4-120">Element</span></span>|<span data-ttu-id="ae7e4-121">説明</span><span class="sxs-lookup"><span data-stu-id="ae7e4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae7e4-122">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="ae7e4-122">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="ae7e4-123">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="ae7e4-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="ae7e4-124">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="ae7e4-124">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ae7e4-125">親要素</span><span class="sxs-lookup"><span data-stu-id="ae7e4-125">Parent elements</span></span>  
  
|<span data-ttu-id="ae7e4-126">要素</span><span class="sxs-lookup"><span data-stu-id="ae7e4-126">Element</span></span>|<span data-ttu-id="ae7e4-127">説明</span><span class="sxs-lookup"><span data-stu-id="ae7e4-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae7e4-128">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ae7e4-128">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="ae7e4-129">`activityDefinitionId` プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="ae7e4-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae7e4-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae7e4-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ae7e4-131">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="ae7e4-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ae7e4-132">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="ae7e4-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
