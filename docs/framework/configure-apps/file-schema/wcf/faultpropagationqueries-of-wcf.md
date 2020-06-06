---
title: <faultPropagationQueries>WCF の
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 709c2c6907b4d0d28118f9de12edb047aa16d741
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855262"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="d0ec6-102">\<faultPropagationQueries>WCF の</span><span class="sxs-lookup"><span data-stu-id="d0ec6-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="d0ec6-103">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="d0ec6-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="d0ec6-104">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="d0ec6-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="d0ec6-105">1 つのアクティビティ内で発生したエラーの処理は、このようなクエリを使用して追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0ec6-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="d0ec6-106">追跡参加要素がエラー伝達レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="d0ec6-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="d0ec6-107">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0ec6-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="d0ec6-108">構文</span><span class="sxs-lookup"><span data-stu-id="d0ec6-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0ec6-109">属性と要素</span><span class="sxs-lookup"><span data-stu-id="d0ec6-109">Attributes and elements</span></span>

<span data-ttu-id="d0ec6-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d0ec6-110">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="d0ec6-111">属性</span><span class="sxs-lookup"><span data-stu-id="d0ec6-111">Attributes</span></span>

<span data-ttu-id="d0ec6-112">なし。</span><span class="sxs-lookup"><span data-stu-id="d0ec6-112">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="d0ec6-113">子要素</span><span class="sxs-lookup"><span data-stu-id="d0ec6-113">Child elements</span></span>

|<span data-ttu-id="d0ec6-114">要素</span><span class="sxs-lookup"><span data-stu-id="d0ec6-114">Element</span></span>|<span data-ttu-id="d0ec6-115">説明</span><span class="sxs-lookup"><span data-stu-id="d0ec6-115">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="d0ec6-116">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="d0ec6-116">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="d0ec6-117">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="d0ec6-117">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d0ec6-118">親要素</span><span class="sxs-lookup"><span data-stu-id="d0ec6-118">Parent elements</span></span>  
  
|<span data-ttu-id="d0ec6-119">要素</span><span class="sxs-lookup"><span data-stu-id="d0ec6-119">Element</span></span>|<span data-ttu-id="d0ec6-120">説明</span><span class="sxs-lookup"><span data-stu-id="d0ec6-120">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="d0ec6-121">`activityDefinitionId` プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="d0ec6-121">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d0ec6-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0ec6-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d0ec6-123">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="d0ec6-123">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d0ec6-124">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="d0ec6-124">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
