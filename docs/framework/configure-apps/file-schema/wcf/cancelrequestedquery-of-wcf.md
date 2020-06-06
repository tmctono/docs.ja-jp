---
title: <cancelRequestedQuery>WCF の
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 0ac8b87afc44927ab6653dd6fcdc09cd61436a9b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850054"
---
# <a name="cancelrequestedquery-of-wcf"></a><span data-ttu-id="e79fb-102">\<cancelRequestedQuery>WCF の</span><span class="sxs-lookup"><span data-stu-id="e79fb-102">\<cancelRequestedQuery> of WCF</span></span>

<span data-ttu-id="e79fb-103">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用するクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="e79fb-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="e79fb-104">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="e79fb-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="e79fb-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e79fb-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**  

## <a name="syntax"></a><span data-ttu-id="e79fb-106">構文</span><span class="sxs-lookup"><span data-stu-id="e79fb-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e79fb-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="e79fb-107">Attributes and elements</span></span>

<span data-ttu-id="e79fb-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e79fb-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e79fb-109">属性</span><span class="sxs-lookup"><span data-stu-id="e79fb-109">Attributes</span></span>  
  
|<span data-ttu-id="e79fb-110">属性</span><span class="sxs-lookup"><span data-stu-id="e79fb-110">Attribute</span></span>|<span data-ttu-id="e79fb-111">説明</span><span class="sxs-lookup"><span data-stu-id="e79fb-111">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="e79fb-112">キャンセルを要求しているアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="e79fb-112">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="e79fb-113">キャンセルが要求された子アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="e79fb-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e79fb-114">子要素</span><span class="sxs-lookup"><span data-stu-id="e79fb-114">Child elements</span></span>

<span data-ttu-id="e79fb-115">なし。</span><span class="sxs-lookup"><span data-stu-id="e79fb-115">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="e79fb-116">親要素</span><span class="sxs-lookup"><span data-stu-id="e79fb-116">Parent elements</span></span>
  
|<span data-ttu-id="e79fb-117">要素</span><span class="sxs-lookup"><span data-stu-id="e79fb-117">Element</span></span>|<span data-ttu-id="e79fb-118">Description</span><span class="sxs-lookup"><span data-stu-id="e79fb-118">Description</span></span>|  
|-------------|-----------------|  
|[\<cancelRequestedQueries>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="e79fb-119">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="e79fb-119">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e79fb-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="e79fb-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e79fb-121">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="e79fb-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e79fb-122">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="e79fb-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
