---
title: <faultPropagationQueries>WCF の
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: aeb964fc8c96c8cb9aeb316bb95f9565fc4a7f18
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918943"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="5750e-102">\<WCF の faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="5750e-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="5750e-103">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="5750e-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="5750e-104">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="5750e-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="5750e-105">1 つのアクティビティ内で発生したエラーの処理は、このようなクエリを使用して追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5750e-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="5750e-106">追跡参加要素がエラー伝達レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="5750e-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="5750e-107">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5750e-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="5750e-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5750e-108">\<system.serviceModel></span></span>  
<span data-ttu-id="5750e-109">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="5750e-109">\<tracking></span></span>  
<span data-ttu-id="5750e-110">\<プロファイル ></span><span class="sxs-lookup"><span data-stu-id="5750e-110">\<profiles></span></span>  
<span data-ttu-id="5750e-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="5750e-111">\<trackingProfile></span></span>  
<span data-ttu-id="5750e-112">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="5750e-112">\<workflow></span></span>  
<span data-ttu-id="5750e-113">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="5750e-113">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5750e-114">構文</span><span class="sxs-lookup"><span data-stu-id="5750e-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5750e-115">属性と要素</span><span class="sxs-lookup"><span data-stu-id="5750e-115">Attributes and elements</span></span>

<span data-ttu-id="5750e-116">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5750e-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="5750e-117">属性</span><span class="sxs-lookup"><span data-stu-id="5750e-117">Attributes</span></span>

<span data-ttu-id="5750e-118">なし。</span><span class="sxs-lookup"><span data-stu-id="5750e-118">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="5750e-119">子要素</span><span class="sxs-lookup"><span data-stu-id="5750e-119">Child elements</span></span>

|<span data-ttu-id="5750e-120">要素</span><span class="sxs-lookup"><span data-stu-id="5750e-120">Element</span></span>|<span data-ttu-id="5750e-121">説明</span><span class="sxs-lookup"><span data-stu-id="5750e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5750e-122">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="5750e-122">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="5750e-123">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="5750e-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="5750e-124">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="5750e-124">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5750e-125">親要素</span><span class="sxs-lookup"><span data-stu-id="5750e-125">Parent elements</span></span>  
  
|<span data-ttu-id="5750e-126">要素</span><span class="sxs-lookup"><span data-stu-id="5750e-126">Element</span></span>|<span data-ttu-id="5750e-127">説明</span><span class="sxs-lookup"><span data-stu-id="5750e-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5750e-128">\<workflow></span><span class="sxs-lookup"><span data-stu-id="5750e-128">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="5750e-129">`activityDefinitionId` プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="5750e-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5750e-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="5750e-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5750e-131">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="5750e-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5750e-132">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="5750e-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
