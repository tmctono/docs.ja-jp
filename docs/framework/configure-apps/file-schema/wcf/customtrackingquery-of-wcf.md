---
title: <customTrackingQuery> WCF の
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 0a5e7c034ce1ef12a8d7d5b1753e2e441e48e293
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673174"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="42f4f-102">\<customTrackingQuery > の WCF</span><span class="sxs-lookup"><span data-stu-id="42f4f-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="42f4f-103">コード アクティビティで定義するイベントを追跡するために使用されるクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="42f4f-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="42f4f-104">追跡参加要素がカスタム追跡レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="42f4f-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="42f4f-105">追跡プロファイルのクエリの詳細については、次を参照してください[追跡プロファイル。](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="42f4f-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="42f4f-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="42f4f-106">\<system.serviceModel></span></span>  
<span data-ttu-id="42f4f-107">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="42f4f-107">\<tracking></span></span>  
<span data-ttu-id="42f4f-108">\<プロファイル ></span><span class="sxs-lookup"><span data-stu-id="42f4f-108">\<profiles></span></span>  
<span data-ttu-id="42f4f-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="42f4f-109">\<trackingProfile></span></span>  
<span data-ttu-id="42f4f-110">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="42f4f-110">\<workflow></span></span>  
<span data-ttu-id="42f4f-111">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="42f4f-111">\<customTrackingQueries></span></span>  
<span data-ttu-id="42f4f-112">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="42f4f-112">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42f4f-113">構文</span><span class="sxs-lookup"><span data-stu-id="42f4f-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42f4f-114">属性と要素</span><span class="sxs-lookup"><span data-stu-id="42f4f-114">Attributes and elements</span></span>  

<span data-ttu-id="42f4f-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="42f4f-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42f4f-116">属性</span><span class="sxs-lookup"><span data-stu-id="42f4f-116">Attributes</span></span>  
  
|<span data-ttu-id="42f4f-117">属性</span><span class="sxs-lookup"><span data-stu-id="42f4f-117">Attribute</span></span>|<span data-ttu-id="42f4f-118">説明</span><span class="sxs-lookup"><span data-stu-id="42f4f-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="42f4f-119">追跡レコードを生成したアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="42f4f-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="42f4f-120">生成されたカスタム追跡レコードの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="42f4f-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42f4f-121">子要素</span><span class="sxs-lookup"><span data-stu-id="42f4f-121">Child elements</span></span>

<span data-ttu-id="42f4f-122">なし。</span><span class="sxs-lookup"><span data-stu-id="42f4f-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="42f4f-123">親要素</span><span class="sxs-lookup"><span data-stu-id="42f4f-123">Parent elements</span></span>

|<span data-ttu-id="42f4f-124">要素</span><span class="sxs-lookup"><span data-stu-id="42f4f-124">Element</span></span>|<span data-ttu-id="42f4f-125">説明</span><span class="sxs-lookup"><span data-stu-id="42f4f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42f4f-126">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="42f4f-126">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="42f4f-127">コード アクティビティで定義するイベントを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="42f4f-127">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="42f4f-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="42f4f-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="42f4f-129">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="42f4f-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="42f4f-130">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="42f4f-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
