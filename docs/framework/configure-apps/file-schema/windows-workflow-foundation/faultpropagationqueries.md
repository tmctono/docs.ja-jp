---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 24e9136729df1352ebb1e665d1ebaf0ce9dc28a5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175838"
---
# \<faultPropagationQueries>

<span data-ttu-id="76754-101">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="76754-101">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="76754-102">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="76754-102">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="76754-103">1 つのアクティビティ内で発生したエラーの処理は、このようなクエリを使用して追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76754-103">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="76754-104">追跡参加要素がエラー伝達レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="76754-104">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="76754-105">追跡プロファイルのクエリの詳細については、「 [追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76754-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**
  
## <a name="syntax"></a><span data-ttu-id="76754-106">構文</span><span class="sxs-lookup"><span data-stu-id="76754-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76754-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="76754-107">Attributes and Elements</span></span>  

 <span data-ttu-id="76754-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="76754-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76754-109">属性</span><span class="sxs-lookup"><span data-stu-id="76754-109">Attributes</span></span>  

 <span data-ttu-id="76754-110">なし。</span><span class="sxs-lookup"><span data-stu-id="76754-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="76754-111">子要素</span><span class="sxs-lookup"><span data-stu-id="76754-111">Child Elements</span></span>  
  
|<span data-ttu-id="76754-112">要素</span><span class="sxs-lookup"><span data-stu-id="76754-112">Element</span></span>|<span data-ttu-id="76754-113">説明</span><span class="sxs-lookup"><span data-stu-id="76754-113">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="76754-114">1 つのアクティビティ内で発生するエラーの処理を追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="76754-114">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="76754-115">このイベントは、FaultHandler がエラーを処理するたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="76754-115">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="76754-116">親要素</span><span class="sxs-lookup"><span data-stu-id="76754-116">Parent Elements</span></span>  
  
|<span data-ttu-id="76754-117">要素</span><span class="sxs-lookup"><span data-stu-id="76754-117">Element</span></span>|<span data-ttu-id="76754-118">説明</span><span class="sxs-lookup"><span data-stu-id="76754-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="76754-119">**ActivityDefinitionId**プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="76754-119">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="76754-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="76754-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="76754-121">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="76754-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="76754-122">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="76754-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
