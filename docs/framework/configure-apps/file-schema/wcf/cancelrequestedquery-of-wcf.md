---
title: <cancelRequestedQuery>WCF の
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 0ac8b87afc44927ab6653dd6fcdc09cd61436a9b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850054"
---
# <a name="cancelrequestedquery-of-wcf"></a><span data-ttu-id="c8e00-102">\<WCF の cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="c8e00-102">\<cancelRequestedQuery> of WCF</span></span>

<span data-ttu-id="c8e00-103">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用するクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="c8e00-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="c8e00-104">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="c8e00-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="c8e00-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8e00-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="c8e00-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c8e00-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c8e00-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c8e00-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c8e00-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="c8e00-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="c8e00-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<プロファイル >** </span><span class="sxs-lookup"><span data-stu-id="c8e00-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="c8e00-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="c8e00-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="c8e00-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="c8e00-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="c8e00-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cancelRequestedQueries >** ](cancelrequestedqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="c8e00-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries-of-wcf.md)</span></span>\
<span data-ttu-id="c8e00-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<cancelRequestedQuery >**</span><span class="sxs-lookup"><span data-stu-id="c8e00-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="c8e00-114">構文</span><span class="sxs-lookup"><span data-stu-id="c8e00-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestedQueries>
          <cancelRequestedQuery activityName="String"
                                childActivityName="String" />
        </cancelRequestedQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8e00-115">属性と要素</span><span class="sxs-lookup"><span data-stu-id="c8e00-115">Attributes and elements</span></span>

<span data-ttu-id="c8e00-116">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8e00-116">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c8e00-117">属性</span><span class="sxs-lookup"><span data-stu-id="c8e00-117">Attributes</span></span>  
  
|<span data-ttu-id="c8e00-118">属性</span><span class="sxs-lookup"><span data-stu-id="c8e00-118">Attribute</span></span>|<span data-ttu-id="c8e00-119">説明</span><span class="sxs-lookup"><span data-stu-id="c8e00-119">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="c8e00-120">キャンセルを要求しているアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="c8e00-120">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="c8e00-121">キャンセルが要求された子アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="c8e00-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8e00-122">子要素</span><span class="sxs-lookup"><span data-stu-id="c8e00-122">Child elements</span></span>

<span data-ttu-id="c8e00-123">なし。</span><span class="sxs-lookup"><span data-stu-id="c8e00-123">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="c8e00-124">親要素</span><span class="sxs-lookup"><span data-stu-id="c8e00-124">Parent elements</span></span>
  
|<span data-ttu-id="c8e00-125">要素</span><span class="sxs-lookup"><span data-stu-id="c8e00-125">Element</span></span>|<span data-ttu-id="c8e00-126">説明</span><span class="sxs-lookup"><span data-stu-id="c8e00-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8e00-127">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="c8e00-127">\<cancelRequestedQueries></span></span>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="c8e00-128">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="c8e00-128">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c8e00-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8e00-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c8e00-130">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="c8e00-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c8e00-131">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="c8e00-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
