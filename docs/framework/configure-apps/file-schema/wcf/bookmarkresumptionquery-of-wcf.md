---
title: <bookmarkResumptionQuery>WCF の
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 8cb254599a9742305ec958fd77174f4c4b8a57c2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "71834004"
---
# <a name="bookmarkresumptionquery-of-wcf"></a><span data-ttu-id="e8bd3-102">\<bookmarkResumptionQuery>WCF の</span><span class="sxs-lookup"><span data-stu-id="e8bd3-102">\<bookmarkResumptionQuery> of WCF</span></span>

<span data-ttu-id="e8bd3-103">ワークフロー インスタンス内のブックマークの再開を追跡するために使用されるクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="e8bd3-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="e8bd3-104">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="e8bd3-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="e8bd3-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8bd3-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="e8bd3-106">構文</span><span class="sxs-lookup"><span data-stu-id="e8bd3-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8bd3-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="e8bd3-107">Attributes and elements</span></span>

<span data-ttu-id="e8bd3-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8bd3-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8bd3-109">属性</span><span class="sxs-lookup"><span data-stu-id="e8bd3-109">Attributes</span></span>  
  
|<span data-ttu-id="e8bd3-110">属性</span><span class="sxs-lookup"><span data-stu-id="e8bd3-110">Attribute</span></span>|<span data-ttu-id="e8bd3-111">説明</span><span class="sxs-lookup"><span data-stu-id="e8bd3-111">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="e8bd3-112">定期受信するブックマーク レコードの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="e8bd3-112">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8bd3-113">子要素</span><span class="sxs-lookup"><span data-stu-id="e8bd3-113">Child elements</span></span>

<span data-ttu-id="e8bd3-114">なし。</span><span class="sxs-lookup"><span data-stu-id="e8bd3-114">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="e8bd3-115">親要素</span><span class="sxs-lookup"><span data-stu-id="e8bd3-115">Parent elements</span></span>  
  
|<span data-ttu-id="e8bd3-116">要素</span><span class="sxs-lookup"><span data-stu-id="e8bd3-116">Element</span></span>|<span data-ttu-id="e8bd3-117">Description</span><span class="sxs-lookup"><span data-stu-id="e8bd3-117">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQueries>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="e8bd3-118">ワークフロー インスタンス内のブックマークの再開を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="e8bd3-118">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8bd3-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8bd3-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e8bd3-120">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="e8bd3-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e8bd3-121">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="e8bd3-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
