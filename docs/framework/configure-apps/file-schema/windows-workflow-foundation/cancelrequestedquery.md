---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: a50e9965a595fce64c383313091334e883dcfbfa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189488"
---
# \<cancelRequestedQuery>

<span data-ttu-id="3a016-101">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用するクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="3a016-101">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="3a016-102">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="3a016-102">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="3a016-103">追跡プロファイルのクエリの詳細については、「 [追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a016-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="3a016-104">構文</span><span class="sxs-lookup"><span data-stu-id="3a016-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String"
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a016-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3a016-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3a016-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3a016-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a016-107">属性</span><span class="sxs-lookup"><span data-stu-id="3a016-107">Attributes</span></span>  
  
|<span data-ttu-id="3a016-108">属性</span><span class="sxs-lookup"><span data-stu-id="3a016-108">Attribute</span></span>|<span data-ttu-id="3a016-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="3a016-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3a016-110">activityName</span><span class="sxs-lookup"><span data-stu-id="3a016-110">activityName</span></span>|<span data-ttu-id="3a016-111">キャンセルを要求しているアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="3a016-111">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="3a016-112">childActivityName</span><span class="sxs-lookup"><span data-stu-id="3a016-112">childActivityName</span></span>|<span data-ttu-id="3a016-113">キャンセルが要求された子アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="3a016-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a016-114">子要素</span><span class="sxs-lookup"><span data-stu-id="3a016-114">Child Elements</span></span>  

 <span data-ttu-id="3a016-115">なし。</span><span class="sxs-lookup"><span data-stu-id="3a016-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a016-116">親要素</span><span class="sxs-lookup"><span data-stu-id="3a016-116">Parent Elements</span></span>  
  
|<span data-ttu-id="3a016-117">要素</span><span class="sxs-lookup"><span data-stu-id="3a016-117">Element</span></span>|<span data-ttu-id="3a016-118">説明</span><span class="sxs-lookup"><span data-stu-id="3a016-118">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="3a016-119">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する構成要素の一覧を表します。</span><span class="sxs-lookup"><span data-stu-id="3a016-119">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="3a016-120">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="3a016-120">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a016-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a016-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3a016-122">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="3a016-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3a016-123">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="3a016-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
