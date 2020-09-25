---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: 047d13bc8477214fa1e3c9ffdbed6785b29da637
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189580"
---
# \<bookmarkResumptionQueries>

<span data-ttu-id="99a19-101">ワークフロー インスタンス内のブックマークの再開を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="99a19-101">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="99a19-102">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="99a19-102">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="99a19-103">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99a19-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**  

## <a name="syntax"></a><span data-ttu-id="99a19-104">構文</span><span class="sxs-lookup"><span data-stu-id="99a19-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <bookmarkResumptionQueries>
        <bookmarkResumptionQuery name="String" />
      </bookmarkResumptionQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99a19-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="99a19-105">Attributes and Elements</span></span>  

 <span data-ttu-id="99a19-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="99a19-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99a19-107">属性</span><span class="sxs-lookup"><span data-stu-id="99a19-107">Attributes</span></span>  

 <span data-ttu-id="99a19-108">なし。</span><span class="sxs-lookup"><span data-stu-id="99a19-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="99a19-109">子要素</span><span class="sxs-lookup"><span data-stu-id="99a19-109">Child Elements</span></span>  
  
|<span data-ttu-id="99a19-110">要素</span><span class="sxs-lookup"><span data-stu-id="99a19-110">Element</span></span>|<span data-ttu-id="99a19-111">説明</span><span class="sxs-lookup"><span data-stu-id="99a19-111">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQuery>](bookmarkresumptionquery.md)|<span data-ttu-id="99a19-112">ワークフロー インスタンス内のブックマークの再開を追跡するために使用されるクエリ。</span><span class="sxs-lookup"><span data-stu-id="99a19-112">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="99a19-113">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="99a19-113">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="99a19-114">親要素</span><span class="sxs-lookup"><span data-stu-id="99a19-114">Parent Elements</span></span>  
  
|<span data-ttu-id="99a19-115">要素</span><span class="sxs-lookup"><span data-stu-id="99a19-115">Element</span></span>|<span data-ttu-id="99a19-116">説明</span><span class="sxs-lookup"><span data-stu-id="99a19-116">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="99a19-117">**ActivityDefinitionId**プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="99a19-117">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99a19-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="99a19-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="99a19-119">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="99a19-119">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="99a19-120">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="99a19-120">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
