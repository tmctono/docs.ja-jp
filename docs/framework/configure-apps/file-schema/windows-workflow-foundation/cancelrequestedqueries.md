---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 89297b3a7d64f4300a735d8512230d441836c634
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152308"
---
# \<cancelRequestedQueries>
<span data-ttu-id="abe99-101">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="abe99-101">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="abe99-102">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="abe99-102">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="abe99-103">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abe99-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="abe99-104">構文</span><span class="sxs-lookup"><span data-stu-id="abe99-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String"
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="abe99-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="abe99-105">Attributes and Elements</span></span>  
 <span data-ttu-id="abe99-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="abe99-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="abe99-107">属性</span><span class="sxs-lookup"><span data-stu-id="abe99-107">Attributes</span></span>  
 <span data-ttu-id="abe99-108">なし。</span><span class="sxs-lookup"><span data-stu-id="abe99-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="abe99-109">子要素</span><span class="sxs-lookup"><span data-stu-id="abe99-109">Child Elements</span></span>  
  
|<span data-ttu-id="abe99-110">要素</span><span class="sxs-lookup"><span data-stu-id="abe99-110">Element</span></span>|<span data-ttu-id="abe99-111">説明</span><span class="sxs-lookup"><span data-stu-id="abe99-111">Description</span></span>|  
|-------------|-----------------|  
|[\<cancelRequestedQuery>](cancelrequestedquery.md)|<span data-ttu-id="abe99-112">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="abe99-112">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="abe99-113">親要素</span><span class="sxs-lookup"><span data-stu-id="abe99-113">Parent Elements</span></span>  
  
|<span data-ttu-id="abe99-114">要素</span><span class="sxs-lookup"><span data-stu-id="abe99-114">Element</span></span>|<span data-ttu-id="abe99-115">説明</span><span class="sxs-lookup"><span data-stu-id="abe99-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="abe99-116">**ActivityDefinitionId**プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="abe99-116">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="abe99-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="abe99-117">See also</span></span>

- [<span data-ttu-id="abe99-118">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="abe99-118">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="abe99-119">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="abe99-119">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
