---
title: <customTrackingQuery>WCF の
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 204bbb6cf5ebcb30bf92b697885ecbbbd94385e0
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855426"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="1e37b-102">\<WCF の customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="1e37b-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="1e37b-103">コードアクティビティで定義するイベントを追跡するために使用されるクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="1e37b-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="1e37b-104">追跡参加要素がカスタム追跡レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="1e37b-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="1e37b-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e37b-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1e37b-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1e37b-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1e37b-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1e37b-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1e37b-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="1e37b-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="1e37b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<プロファイル >** </span><span class="sxs-lookup"><span data-stu-id="1e37b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="1e37b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="1e37b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="1e37b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="1e37b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="1e37b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customTrackingQueries >** ](customtrackingqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="1e37b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries-of-wcf.md)</span></span>\
<span data-ttu-id="1e37b-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<customTrackingQuery >**</span><span class="sxs-lookup"><span data-stu-id="1e37b-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e37b-114">構文</span><span class="sxs-lookup"><span data-stu-id="1e37b-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e37b-115">属性と要素</span><span class="sxs-lookup"><span data-stu-id="1e37b-115">Attributes and elements</span></span>  

<span data-ttu-id="1e37b-116">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1e37b-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e37b-117">属性</span><span class="sxs-lookup"><span data-stu-id="1e37b-117">Attributes</span></span>  
  
|<span data-ttu-id="1e37b-118">属性</span><span class="sxs-lookup"><span data-stu-id="1e37b-118">Attribute</span></span>|<span data-ttu-id="1e37b-119">説明</span><span class="sxs-lookup"><span data-stu-id="1e37b-119">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="1e37b-120">追跡レコードを生成したアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="1e37b-120">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="1e37b-121">生成されたカスタム追跡レコードの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="1e37b-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e37b-122">子要素</span><span class="sxs-lookup"><span data-stu-id="1e37b-122">Child elements</span></span>

<span data-ttu-id="1e37b-123">なし。</span><span class="sxs-lookup"><span data-stu-id="1e37b-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1e37b-124">親要素</span><span class="sxs-lookup"><span data-stu-id="1e37b-124">Parent elements</span></span>

|<span data-ttu-id="1e37b-125">要素</span><span class="sxs-lookup"><span data-stu-id="1e37b-125">Element</span></span>|<span data-ttu-id="1e37b-126">説明</span><span class="sxs-lookup"><span data-stu-id="1e37b-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e37b-127">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="1e37b-127">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="1e37b-128">コード アクティビティで定義するイベントを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="1e37b-128">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="1e37b-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e37b-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1e37b-130">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="1e37b-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1e37b-131">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="1e37b-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
