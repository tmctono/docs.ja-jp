---
title: <faultPropagationQueries>WCF の
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 709c2c6907b4d0d28118f9de12edb047aa16d741
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855262"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="a9552-102">\<WCF の faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="a9552-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="a9552-103">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="a9552-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="a9552-104">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="a9552-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="a9552-105">1 つのアクティビティ内で発生したエラーの処理は、このようなクエリを使用して追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9552-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="a9552-106">追跡参加要素がエラー伝達レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="a9552-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="a9552-107">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9552-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="a9552-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a9552-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a9552-109">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a9552-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a9552-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="a9552-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="a9552-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<プロファイル >** </span><span class="sxs-lookup"><span data-stu-id="a9552-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="a9552-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="a9552-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="a9552-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="a9552-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="a9552-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<faultPropagationQueries >**</span><span class="sxs-lookup"><span data-stu-id="a9552-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9552-115">構文</span><span class="sxs-lookup"><span data-stu-id="a9552-115">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9552-116">属性と要素</span><span class="sxs-lookup"><span data-stu-id="a9552-116">Attributes and elements</span></span>

<span data-ttu-id="a9552-117">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a9552-117">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="a9552-118">属性</span><span class="sxs-lookup"><span data-stu-id="a9552-118">Attributes</span></span>

<span data-ttu-id="a9552-119">なし。</span><span class="sxs-lookup"><span data-stu-id="a9552-119">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="a9552-120">子要素</span><span class="sxs-lookup"><span data-stu-id="a9552-120">Child elements</span></span>

|<span data-ttu-id="a9552-121">要素</span><span class="sxs-lookup"><span data-stu-id="a9552-121">Element</span></span>|<span data-ttu-id="a9552-122">説明</span><span class="sxs-lookup"><span data-stu-id="a9552-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9552-123">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="a9552-123">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="a9552-124">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="a9552-124">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="a9552-125">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="a9552-125">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a9552-126">親要素</span><span class="sxs-lookup"><span data-stu-id="a9552-126">Parent elements</span></span>  
  
|<span data-ttu-id="a9552-127">要素</span><span class="sxs-lookup"><span data-stu-id="a9552-127">Element</span></span>|<span data-ttu-id="a9552-128">説明</span><span class="sxs-lookup"><span data-stu-id="a9552-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9552-129">\<workflow></span><span class="sxs-lookup"><span data-stu-id="a9552-129">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="a9552-130">`activityDefinitionId` プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="a9552-130">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a9552-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9552-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a9552-132">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="a9552-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a9552-133">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="a9552-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
