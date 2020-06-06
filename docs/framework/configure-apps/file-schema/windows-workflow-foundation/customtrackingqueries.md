---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 6901244009956a499458858bf73f8fd83ec52e13
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152262"
---
# \<customTrackingQueries>
<span data-ttu-id="c3161-101">コード アクティビティで定義するイベントを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="c3161-101">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="c3161-102">追跡参加要素がカスタム追跡レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="c3161-102">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="c3161-103">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3161-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="c3161-104">構文</span><span class="sxs-lookup"><span data-stu-id="c3161-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String"
                             name="String" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3161-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c3161-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c3161-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c3161-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3161-107">属性</span><span class="sxs-lookup"><span data-stu-id="c3161-107">Attributes</span></span>  
 <span data-ttu-id="c3161-108">なし。</span><span class="sxs-lookup"><span data-stu-id="c3161-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c3161-109">子要素</span><span class="sxs-lookup"><span data-stu-id="c3161-109">Child Elements</span></span>  
  
|<span data-ttu-id="c3161-110">要素</span><span class="sxs-lookup"><span data-stu-id="c3161-110">Element</span></span>|<span data-ttu-id="c3161-111">説明</span><span class="sxs-lookup"><span data-stu-id="c3161-111">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery.md)|<span data-ttu-id="c3161-112">コード アクティビティで定義するイベントを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="c3161-112">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c3161-113">親要素</span><span class="sxs-lookup"><span data-stu-id="c3161-113">Parent Elements</span></span>  
  
|<span data-ttu-id="c3161-114">要素</span><span class="sxs-lookup"><span data-stu-id="c3161-114">Element</span></span>|<span data-ttu-id="c3161-115">説明</span><span class="sxs-lookup"><span data-stu-id="c3161-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="c3161-116">**ActivityDefinitionId**プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="c3161-116">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c3161-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3161-117">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c3161-118">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="c3161-118">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c3161-119">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="c3161-119">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
