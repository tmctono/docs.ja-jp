---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: efd1e4e54223ff9f5d60b4087fbe5b6bebf1af2f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189591"
---
# \<bookmarkResumptionQuery>

<span data-ttu-id="838cc-101">ワークフロー インスタンス内のブックマークの再開を追跡するために使用されるクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="838cc-101">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="838cc-102">追跡参加要素がブックマーク再開レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="838cc-102">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="838cc-103">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="838cc-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="838cc-104">構文</span><span class="sxs-lookup"><span data-stu-id="838cc-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="838cc-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="838cc-105">Attributes and Elements</span></span>  

 <span data-ttu-id="838cc-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="838cc-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="838cc-107">属性</span><span class="sxs-lookup"><span data-stu-id="838cc-107">Attributes</span></span>  
  
|<span data-ttu-id="838cc-108">属性</span><span class="sxs-lookup"><span data-stu-id="838cc-108">Attribute</span></span>|<span data-ttu-id="838cc-109">説明</span><span class="sxs-lookup"><span data-stu-id="838cc-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="838cc-110">name</span><span class="sxs-lookup"><span data-stu-id="838cc-110">name</span></span>|<span data-ttu-id="838cc-111">定期受信するブックマーク レコードの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="838cc-111">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="838cc-112">子要素</span><span class="sxs-lookup"><span data-stu-id="838cc-112">Child Elements</span></span>  

 <span data-ttu-id="838cc-113">なし。</span><span class="sxs-lookup"><span data-stu-id="838cc-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="838cc-114">親要素</span><span class="sxs-lookup"><span data-stu-id="838cc-114">Parent Elements</span></span>  
  
|<span data-ttu-id="838cc-115">要素</span><span class="sxs-lookup"><span data-stu-id="838cc-115">Element</span></span>|<span data-ttu-id="838cc-116">説明</span><span class="sxs-lookup"><span data-stu-id="838cc-116">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQueries>](bookmarkresumptionqueries.md)|<span data-ttu-id="838cc-117">ワークフロー インスタンス内のブックマークの再開を追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="838cc-117">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="838cc-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="838cc-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="838cc-119">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="838cc-119">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="838cc-120">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="838cc-120">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
