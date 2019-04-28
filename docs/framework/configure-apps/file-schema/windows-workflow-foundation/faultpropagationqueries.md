---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 402b938913575adfa9125b981dc2913680f07b73
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790157"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="7eb1a-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="7eb1a-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="7eb1a-102">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="7eb1a-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="7eb1a-103">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="7eb1a-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="7eb1a-104">1 つのアクティビティ内で発生したエラーの処理は、このようなクエリを使用して追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7eb1a-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="7eb1a-105">追跡参加要素がエラー伝達レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="7eb1a-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="7eb1a-106">追跡プロファイルのクエリの詳細については、次を参照してください。[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)します。</span><span class="sxs-lookup"><span data-stu-id="7eb1a-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="7eb1a-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7eb1a-107">\<system.serviceModel></span></span>  
<span data-ttu-id="7eb1a-108">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="7eb1a-108">\<tracking></span></span>  
<span data-ttu-id="7eb1a-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="7eb1a-109">\<trackingProfile></span></span>  
<span data-ttu-id="7eb1a-110">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="7eb1a-110">\<workflow></span></span>  
<span data-ttu-id="7eb1a-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="7eb1a-111">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eb1a-112">構文</span><span class="sxs-lookup"><span data-stu-id="7eb1a-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7eb1a-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7eb1a-113">Attributes and Elements</span></span>  
 <span data-ttu-id="7eb1a-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7eb1a-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7eb1a-115">属性</span><span class="sxs-lookup"><span data-stu-id="7eb1a-115">Attributes</span></span>  
 <span data-ttu-id="7eb1a-116">なし。</span><span class="sxs-lookup"><span data-stu-id="7eb1a-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7eb1a-117">子要素</span><span class="sxs-lookup"><span data-stu-id="7eb1a-117">Child Elements</span></span>  
  
|<span data-ttu-id="7eb1a-118">要素</span><span class="sxs-lookup"><span data-stu-id="7eb1a-118">Element</span></span>|<span data-ttu-id="7eb1a-119">説明</span><span class="sxs-lookup"><span data-stu-id="7eb1a-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7eb1a-120">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="7eb1a-120">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="7eb1a-121">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="7eb1a-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="7eb1a-122">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="7eb1a-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7eb1a-123">親要素</span><span class="sxs-lookup"><span data-stu-id="7eb1a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7eb1a-124">要素</span><span class="sxs-lookup"><span data-stu-id="7eb1a-124">Element</span></span>|<span data-ttu-id="7eb1a-125">説明</span><span class="sxs-lookup"><span data-stu-id="7eb1a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7eb1a-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="7eb1a-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="7eb1a-127">識別される特定のワークフローのすべてのクエリを格納する構成要素、 **activityDefinitionId**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="7eb1a-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7eb1a-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="7eb1a-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="7eb1a-129">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="7eb1a-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7eb1a-130">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="7eb1a-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
