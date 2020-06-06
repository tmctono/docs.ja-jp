---
title: <bookmarkResumptionQueries>WCF の
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 94ff9f44f295b45c03e1bd8f52a85d6b7b0c6e3b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850127"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="fceb2-102">\<bookmarkResumptionQueries>WCF の</span><span class="sxs-lookup"><span data-stu-id="fceb2-102">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="fceb2-103">ワークフロー インスタンス内のブックマークの再開を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="fceb2-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="fceb2-104">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="fceb2-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="fceb2-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fceb2-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**  

## <a name="syntax"></a><span data-ttu-id="fceb2-106">構文</span><span class="sxs-lookup"><span data-stu-id="fceb2-106">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <bookmarkResumptionQueries>
          <bookmarkResumptionQuery name="String" />
        </bookmarkResumptionQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fceb2-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="fceb2-107">Attributes and elements</span></span>  
  
<span data-ttu-id="fceb2-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="fceb2-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fceb2-109">属性</span><span class="sxs-lookup"><span data-stu-id="fceb2-109">Attributes</span></span>  
  
<span data-ttu-id="fceb2-110">なし。</span><span class="sxs-lookup"><span data-stu-id="fceb2-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fceb2-111">子要素</span><span class="sxs-lookup"><span data-stu-id="fceb2-111">Child elements</span></span>  
  
|<span data-ttu-id="fceb2-112">要素</span><span class="sxs-lookup"><span data-stu-id="fceb2-112">Element</span></span>|<span data-ttu-id="fceb2-113">説明</span><span class="sxs-lookup"><span data-stu-id="fceb2-113">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQuery>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="fceb2-114">ワークフロー インスタンス内のブックマークの再開を追跡するために使用されるクエリ。</span><span class="sxs-lookup"><span data-stu-id="fceb2-114">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="fceb2-115">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="fceb2-115">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fceb2-116">親要素</span><span class="sxs-lookup"><span data-stu-id="fceb2-116">Parent elements</span></span>  
  
|<span data-ttu-id="fceb2-117">要素</span><span class="sxs-lookup"><span data-stu-id="fceb2-117">Element</span></span>|<span data-ttu-id="fceb2-118">説明</span><span class="sxs-lookup"><span data-stu-id="fceb2-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="fceb2-119">`activityDefinitionId` プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="fceb2-119">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fceb2-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="fceb2-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="fceb2-121">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="fceb2-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="fceb2-122">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="fceb2-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
