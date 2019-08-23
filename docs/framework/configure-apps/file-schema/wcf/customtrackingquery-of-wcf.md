---
title: <customTrackingQuery>WCF の
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: b034727dc89b58794ec2834cb0ff39cd7e5f1dca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919360"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="2ba4d-102">\<WCF の customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="2ba4d-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="2ba4d-103">コードアクティビティで定義するイベントを追跡するために使用されるクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="2ba4d-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="2ba4d-104">追跡参加要素がカスタム追跡レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="2ba4d-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="2ba4d-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ba4d-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="2ba4d-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2ba4d-106">\<system.serviceModel></span></span>  
<span data-ttu-id="2ba4d-107">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="2ba4d-107">\<tracking></span></span>  
<span data-ttu-id="2ba4d-108">\<プロファイル ></span><span class="sxs-lookup"><span data-stu-id="2ba4d-108">\<profiles></span></span>  
<span data-ttu-id="2ba4d-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2ba4d-109">\<trackingProfile></span></span>  
<span data-ttu-id="2ba4d-110">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="2ba4d-110">\<workflow></span></span>  
<span data-ttu-id="2ba4d-111">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="2ba4d-111">\<customTrackingQueries></span></span>  
<span data-ttu-id="2ba4d-112">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="2ba4d-112">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ba4d-113">構文</span><span class="sxs-lookup"><span data-stu-id="2ba4d-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ba4d-114">属性と要素</span><span class="sxs-lookup"><span data-stu-id="2ba4d-114">Attributes and elements</span></span>  

<span data-ttu-id="2ba4d-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ba4d-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ba4d-116">属性</span><span class="sxs-lookup"><span data-stu-id="2ba4d-116">Attributes</span></span>  
  
|<span data-ttu-id="2ba4d-117">属性</span><span class="sxs-lookup"><span data-stu-id="2ba4d-117">Attribute</span></span>|<span data-ttu-id="2ba4d-118">説明</span><span class="sxs-lookup"><span data-stu-id="2ba4d-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="2ba4d-119">追跡レコードを生成したアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="2ba4d-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="2ba4d-120">生成されたカスタム追跡レコードの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="2ba4d-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ba4d-121">子要素</span><span class="sxs-lookup"><span data-stu-id="2ba4d-121">Child elements</span></span>

<span data-ttu-id="2ba4d-122">なし。</span><span class="sxs-lookup"><span data-stu-id="2ba4d-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2ba4d-123">親要素</span><span class="sxs-lookup"><span data-stu-id="2ba4d-123">Parent elements</span></span>

|<span data-ttu-id="2ba4d-124">要素</span><span class="sxs-lookup"><span data-stu-id="2ba4d-124">Element</span></span>|<span data-ttu-id="2ba4d-125">説明</span><span class="sxs-lookup"><span data-stu-id="2ba4d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ba4d-126">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="2ba4d-126">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="2ba4d-127">コード アクティビティで定義するイベントを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="2ba4d-127">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="2ba4d-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ba4d-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2ba4d-129">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="2ba4d-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2ba4d-130">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="2ba4d-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
