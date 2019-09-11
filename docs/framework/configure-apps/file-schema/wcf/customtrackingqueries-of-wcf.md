---
title: <customTrackingQueries>WCF の
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 2c4bd74ae346c536e8bc0ae454e638b7c76a40fc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855439"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="00662-102">\<WCF の customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="00662-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="00662-103">コード アクティビティで定義するイベントを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="00662-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="00662-104">追跡参加要素がカスタム追跡レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="00662-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
<span data-ttu-id="00662-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00662-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="00662-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="00662-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="00662-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="00662-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="00662-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="00662-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="00662-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<プロファイル >** </span><span class="sxs-lookup"><span data-stu-id="00662-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="00662-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="00662-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="00662-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="00662-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="00662-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<customTrackingQueries >**</span><span class="sxs-lookup"><span data-stu-id="00662-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="00662-113">構文</span><span class="sxs-lookup"><span data-stu-id="00662-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00662-114">属性と要素</span><span class="sxs-lookup"><span data-stu-id="00662-114">Attributes and elements</span></span>

<span data-ttu-id="00662-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="00662-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00662-116">属性</span><span class="sxs-lookup"><span data-stu-id="00662-116">Attributes</span></span>

<span data-ttu-id="00662-117">なし。</span><span class="sxs-lookup"><span data-stu-id="00662-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="00662-118">子要素</span><span class="sxs-lookup"><span data-stu-id="00662-118">Child elements</span></span>
  
|<span data-ttu-id="00662-119">要素</span><span class="sxs-lookup"><span data-stu-id="00662-119">Element</span></span>|<span data-ttu-id="00662-120">説明</span><span class="sxs-lookup"><span data-stu-id="00662-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00662-121">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="00662-121">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="00662-122">コード アクティビティで定義するイベントを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="00662-122">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="00662-123">親要素</span><span class="sxs-lookup"><span data-stu-id="00662-123">Parent elements</span></span>  
  
|<span data-ttu-id="00662-124">要素</span><span class="sxs-lookup"><span data-stu-id="00662-124">Element</span></span>|<span data-ttu-id="00662-125">説明</span><span class="sxs-lookup"><span data-stu-id="00662-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00662-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="00662-126">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="00662-127">`activityDefinitionId` プロパティによって識別される特定のワークフローのすべてのクエリを格納する構成要素。</span><span class="sxs-lookup"><span data-stu-id="00662-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="00662-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="00662-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="00662-129">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="00662-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="00662-130">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="00662-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
