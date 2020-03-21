---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: a02d71811709b2c285ab7081b89ee3082ec5b43d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152210"
---
# <a name="customtrackingquery"></a><span data-ttu-id="b9966-101">\<カスタム追跡クエリ></span><span class="sxs-lookup"><span data-stu-id="b9966-101">\<customTrackingQuery></span></span>
<span data-ttu-id="b9966-102">コード アクティビティで定義するイベントを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="b9966-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="b9966-103">追跡参加要素がカスタム追跡レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="b9966-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="b9966-104">プロファイル クエリの追跡の詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9966-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b9966-105">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b9966-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b9966-106">&nbsp;&nbsp;[**\<システム。サービスモデル>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b9966-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="b9966-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<追跡>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="b9966-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="b9966-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<追跡プロファイル>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="b9966-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="b9966-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ワークフロー>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b9966-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="b9966-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>を照会する**](customtrackingqueries.md)</span><span class="sxs-lookup"><span data-stu-id="b9966-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)</span></span>\
<span data-ttu-id="b9966-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<カスタム追跡クエリ>**</span><span class="sxs-lookup"><span data-stu-id="b9966-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9966-112">構文</span><span class="sxs-lookup"><span data-stu-id="b9966-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9966-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b9966-113">Attributes and Elements</span></span>  
 <span data-ttu-id="b9966-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9966-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9966-115">属性</span><span class="sxs-lookup"><span data-stu-id="b9966-115">Attributes</span></span>  
  
|<span data-ttu-id="b9966-116">属性</span><span class="sxs-lookup"><span data-stu-id="b9966-116">Attribute</span></span>|<span data-ttu-id="b9966-117">説明</span><span class="sxs-lookup"><span data-stu-id="b9966-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b9966-118">activityName</span><span class="sxs-lookup"><span data-stu-id="b9966-118">activityName</span></span>|<span data-ttu-id="b9966-119">追跡レコードを生成したアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="b9966-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="b9966-120">name</span><span class="sxs-lookup"><span data-stu-id="b9966-120">name</span></span>|<span data-ttu-id="b9966-121">生成されたカスタム追跡レコードの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="b9966-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b9966-122">子要素</span><span class="sxs-lookup"><span data-stu-id="b9966-122">Child Elements</span></span>  
 <span data-ttu-id="b9966-123">[なし] :</span><span class="sxs-lookup"><span data-stu-id="b9966-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b9966-124">親要素</span><span class="sxs-lookup"><span data-stu-id="b9966-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b9966-125">要素</span><span class="sxs-lookup"><span data-stu-id="b9966-125">Element</span></span>|<span data-ttu-id="b9966-126">説明</span><span class="sxs-lookup"><span data-stu-id="b9966-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b9966-127">\<カスタム追跡クエリ></span><span class="sxs-lookup"><span data-stu-id="b9966-127">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="b9966-128">コード アクティビティで定義するイベントを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="b9966-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b9966-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9966-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b9966-130">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="b9966-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b9966-131">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="b9966-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
