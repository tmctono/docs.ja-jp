---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 6901244009956a499458858bf73f8fd83ec52e13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152262"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="8c3a7-101">\<カスタム追跡クエリ></span><span class="sxs-lookup"><span data-stu-id="8c3a7-101">\<customTrackingQueries></span></span>
<span data-ttu-id="8c3a7-102">コード アクティビティで定義するイベントを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="8c3a7-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="8c3a7-103">追跡参加要素がカスタム追跡レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="8c3a7-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="8c3a7-104">プロファイル クエリの追跡の詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c3a7-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="8c3a7-105">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8c3a7-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8c3a7-106">&nbsp;&nbsp;[**\<システム。サービスモデル>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="8c3a7-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="8c3a7-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<追跡>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="8c3a7-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="8c3a7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<追跡プロファイル>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="8c3a7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="8c3a7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ワークフロー>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="8c3a7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="8c3a7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>を照会する**</span><span class="sxs-lookup"><span data-stu-id="8c3a7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c3a7-111">構文</span><span class="sxs-lookup"><span data-stu-id="8c3a7-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c3a7-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8c3a7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8c3a7-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8c3a7-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c3a7-114">属性</span><span class="sxs-lookup"><span data-stu-id="8c3a7-114">Attributes</span></span>  
 <span data-ttu-id="8c3a7-115">[なし] :</span><span class="sxs-lookup"><span data-stu-id="8c3a7-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8c3a7-116">子要素</span><span class="sxs-lookup"><span data-stu-id="8c3a7-116">Child Elements</span></span>  
  
|<span data-ttu-id="8c3a7-117">要素</span><span class="sxs-lookup"><span data-stu-id="8c3a7-117">Element</span></span>|<span data-ttu-id="8c3a7-118">説明</span><span class="sxs-lookup"><span data-stu-id="8c3a7-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c3a7-119">\<カスタム追跡クエリ></span><span class="sxs-lookup"><span data-stu-id="8c3a7-119">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="8c3a7-120">コード アクティビティで定義するイベントを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="8c3a7-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c3a7-121">親要素</span><span class="sxs-lookup"><span data-stu-id="8c3a7-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8c3a7-122">要素</span><span class="sxs-lookup"><span data-stu-id="8c3a7-122">Element</span></span>|<span data-ttu-id="8c3a7-123">説明</span><span class="sxs-lookup"><span data-stu-id="8c3a7-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c3a7-124">\<ワークフロー></span><span class="sxs-lookup"><span data-stu-id="8c3a7-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="8c3a7-125">**activityDefinitionId**プロパティによって識別される特定のワークフローのすべてのクエリを含む構成要素。</span><span class="sxs-lookup"><span data-stu-id="8c3a7-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8c3a7-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c3a7-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8c3a7-127">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="8c3a7-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8c3a7-128">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="8c3a7-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
