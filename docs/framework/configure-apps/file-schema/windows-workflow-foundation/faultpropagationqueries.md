---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: bc0cc5fd027da45994269b149b72496fa03becef
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398729"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="9ecf3-101">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="9ecf3-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="9ecf3-102">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="9ecf3-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="9ecf3-103">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="9ecf3-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="9ecf3-104">1 つのアクティビティ内で発生したエラーの処理は、このようなクエリを使用して追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ecf3-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="9ecf3-105">追跡参加要素がエラー伝達レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="9ecf3-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="9ecf3-106">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ecf3-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="9ecf3-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9ecf3-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9ecf3-108">&nbsp;&nbsp;[ **\<system.ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9ecf3-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="9ecf3-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="9ecf3-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="9ecf3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="9ecf3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="9ecf3-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9ecf3-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="9ecf3-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<faultPropagationQueries >**</span><span class="sxs-lookup"><span data-stu-id="9ecf3-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="9ecf3-113">構文</span><span class="sxs-lookup"><span data-stu-id="9ecf3-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ecf3-114">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9ecf3-114">Attributes and Elements</span></span>  
 <span data-ttu-id="9ecf3-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ecf3-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ecf3-116">属性</span><span class="sxs-lookup"><span data-stu-id="9ecf3-116">Attributes</span></span>  
 <span data-ttu-id="9ecf3-117">なし。</span><span class="sxs-lookup"><span data-stu-id="9ecf3-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9ecf3-118">子要素</span><span class="sxs-lookup"><span data-stu-id="9ecf3-118">Child Elements</span></span>  
  
|<span data-ttu-id="9ecf3-119">要素</span><span class="sxs-lookup"><span data-stu-id="9ecf3-119">Element</span></span>|<span data-ttu-id="9ecf3-120">説明</span><span class="sxs-lookup"><span data-stu-id="9ecf3-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ecf3-121">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="9ecf3-121">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="9ecf3-122">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="9ecf3-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="9ecf3-123">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="9ecf3-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9ecf3-124">親要素</span><span class="sxs-lookup"><span data-stu-id="9ecf3-124">Parent Elements</span></span>  
  
|<span data-ttu-id="9ecf3-125">要素</span><span class="sxs-lookup"><span data-stu-id="9ecf3-125">Element</span></span>|<span data-ttu-id="9ecf3-126">説明</span><span class="sxs-lookup"><span data-stu-id="9ecf3-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ecf3-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="9ecf3-127">\<workflow></span></span>](workflow.md)|<span data-ttu-id="9ecf3-128">**ActivityDefinitionId**プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="9ecf3-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ecf3-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ecf3-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9ecf3-130">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="9ecf3-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9ecf3-131">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="9ecf3-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
