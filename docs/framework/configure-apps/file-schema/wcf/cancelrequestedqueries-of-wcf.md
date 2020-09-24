---
title: <cancelRequestedQueries> WCF の
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 205399330c1aa69b332c2149ee32d9b6098ccdbe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151169"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="d5d89-102">\<cancelRequestedQueries> WCF の</span><span class="sxs-lookup"><span data-stu-id="d5d89-102">\<cancelRequestedQueries> of WCF</span></span>

<span data-ttu-id="d5d89-103">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="d5d89-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="d5d89-104">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="d5d89-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="d5d89-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5d89-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="d5d89-106">構文</span><span class="sxs-lookup"><span data-stu-id="d5d89-106">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String" />
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5d89-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="d5d89-107">Attributes and elements</span></span>  

<span data-ttu-id="d5d89-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d5d89-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5d89-109">属性</span><span class="sxs-lookup"><span data-stu-id="d5d89-109">Attributes</span></span>

<span data-ttu-id="d5d89-110">なし。</span><span class="sxs-lookup"><span data-stu-id="d5d89-110">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="d5d89-111">子要素</span><span class="sxs-lookup"><span data-stu-id="d5d89-111">Child elements</span></span>
  
|<span data-ttu-id="d5d89-112">要素</span><span class="sxs-lookup"><span data-stu-id="d5d89-112">Element</span></span>|<span data-ttu-id="d5d89-113">説明</span><span class="sxs-lookup"><span data-stu-id="d5d89-113">Description</span></span>|  
|-------------|-----------------|  
|[\<cancelRequestedQuery>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="d5d89-114">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="d5d89-114">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d5d89-115">親要素</span><span class="sxs-lookup"><span data-stu-id="d5d89-115">Parent elements</span></span>  
  
|<span data-ttu-id="d5d89-116">要素</span><span class="sxs-lookup"><span data-stu-id="d5d89-116">Element</span></span>|<span data-ttu-id="d5d89-117">説明</span><span class="sxs-lookup"><span data-stu-id="d5d89-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="d5d89-118"><xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="d5d89-118">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5d89-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5d89-119">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="d5d89-120">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="d5d89-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d5d89-121">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="d5d89-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
