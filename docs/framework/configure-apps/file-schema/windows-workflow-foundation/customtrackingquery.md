---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: a02d71811709b2c285ab7081b89ee3082ec5b43d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152210"
---
# \<customTrackingQuery>
<span data-ttu-id="3c6f6-101">コード アクティビティで定義するイベントを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="3c6f6-101">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="3c6f6-102">追跡参加要素がカスタム追跡レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="3c6f6-102">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="3c6f6-103">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c6f6-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="3c6f6-104">構文</span><span class="sxs-lookup"><span data-stu-id="3c6f6-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c6f6-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3c6f6-105">Attributes and Elements</span></span>  
 <span data-ttu-id="3c6f6-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c6f6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c6f6-107">属性</span><span class="sxs-lookup"><span data-stu-id="3c6f6-107">Attributes</span></span>  
  
|<span data-ttu-id="3c6f6-108">属性</span><span class="sxs-lookup"><span data-stu-id="3c6f6-108">Attribute</span></span>|<span data-ttu-id="3c6f6-109">説明</span><span class="sxs-lookup"><span data-stu-id="3c6f6-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3c6f6-110">activityName</span><span class="sxs-lookup"><span data-stu-id="3c6f6-110">activityName</span></span>|<span data-ttu-id="3c6f6-111">追跡レコードを生成したアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="3c6f6-111">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="3c6f6-112">name</span><span class="sxs-lookup"><span data-stu-id="3c6f6-112">name</span></span>|<span data-ttu-id="3c6f6-113">生成されたカスタム追跡レコードの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="3c6f6-113">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3c6f6-114">子要素</span><span class="sxs-lookup"><span data-stu-id="3c6f6-114">Child Elements</span></span>  
 <span data-ttu-id="3c6f6-115">なし。</span><span class="sxs-lookup"><span data-stu-id="3c6f6-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3c6f6-116">親要素</span><span class="sxs-lookup"><span data-stu-id="3c6f6-116">Parent Elements</span></span>  
  
|<span data-ttu-id="3c6f6-117">要素</span><span class="sxs-lookup"><span data-stu-id="3c6f6-117">Element</span></span>|<span data-ttu-id="3c6f6-118">Description</span><span class="sxs-lookup"><span data-stu-id="3c6f6-118">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery.md)|<span data-ttu-id="3c6f6-119">コード アクティビティで定義するイベントを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="3c6f6-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3c6f6-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c6f6-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3c6f6-121">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="3c6f6-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3c6f6-122">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="3c6f6-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
