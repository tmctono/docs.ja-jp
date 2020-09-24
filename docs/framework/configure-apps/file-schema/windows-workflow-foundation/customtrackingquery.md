---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 59a76ea772dc8d06c390e3bca9d531df5f11e5f0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148725"
---
# \<customTrackingQuery>

<span data-ttu-id="e5799-101">コード アクティビティで定義するイベントを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="e5799-101">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="e5799-102">追跡参加要素がカスタム追跡レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="e5799-102">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="e5799-103">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5799-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="e5799-104">構文</span><span class="sxs-lookup"><span data-stu-id="e5799-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5799-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e5799-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e5799-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5799-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5799-107">属性</span><span class="sxs-lookup"><span data-stu-id="e5799-107">Attributes</span></span>  
  
|<span data-ttu-id="e5799-108">属性</span><span class="sxs-lookup"><span data-stu-id="e5799-108">Attribute</span></span>|<span data-ttu-id="e5799-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="e5799-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5799-110">activityName</span><span class="sxs-lookup"><span data-stu-id="e5799-110">activityName</span></span>|<span data-ttu-id="e5799-111">追跡レコードを生成したアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="e5799-111">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="e5799-112">name</span><span class="sxs-lookup"><span data-stu-id="e5799-112">name</span></span>|<span data-ttu-id="e5799-113">生成されたカスタム追跡レコードの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="e5799-113">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5799-114">子要素</span><span class="sxs-lookup"><span data-stu-id="e5799-114">Child Elements</span></span>  

 <span data-ttu-id="e5799-115">なし。</span><span class="sxs-lookup"><span data-stu-id="e5799-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5799-116">親要素</span><span class="sxs-lookup"><span data-stu-id="e5799-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e5799-117">要素</span><span class="sxs-lookup"><span data-stu-id="e5799-117">Element</span></span>|<span data-ttu-id="e5799-118">説明</span><span class="sxs-lookup"><span data-stu-id="e5799-118">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery.md)|<span data-ttu-id="e5799-119">コード アクティビティで定義するイベントを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="e5799-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5799-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5799-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e5799-121">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="e5799-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e5799-122">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="e5799-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
