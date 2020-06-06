---
title: <customTrackingQuery>WCF の
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 204bbb6cf5ebcb30bf92b697885ecbbbd94385e0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855426"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="10534-102">\<customTrackingQuery>WCF の</span><span class="sxs-lookup"><span data-stu-id="10534-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="10534-103">コードアクティビティで定義するイベントを追跡するために使用されるクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="10534-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="10534-104">追跡参加要素がカスタム追跡レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="10534-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="10534-105">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10534-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="10534-106">構文</span><span class="sxs-lookup"><span data-stu-id="10534-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10534-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="10534-107">Attributes and elements</span></span>  

<span data-ttu-id="10534-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="10534-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10534-109">属性</span><span class="sxs-lookup"><span data-stu-id="10534-109">Attributes</span></span>  
  
|<span data-ttu-id="10534-110">属性</span><span class="sxs-lookup"><span data-stu-id="10534-110">Attribute</span></span>|<span data-ttu-id="10534-111">説明</span><span class="sxs-lookup"><span data-stu-id="10534-111">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="10534-112">追跡レコードを生成したアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="10534-112">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="10534-113">生成されたカスタム追跡レコードの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="10534-113">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10534-114">子要素</span><span class="sxs-lookup"><span data-stu-id="10534-114">Child elements</span></span>

<span data-ttu-id="10534-115">なし。</span><span class="sxs-lookup"><span data-stu-id="10534-115">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="10534-116">親要素</span><span class="sxs-lookup"><span data-stu-id="10534-116">Parent elements</span></span>

|<span data-ttu-id="10534-117">要素</span><span class="sxs-lookup"><span data-stu-id="10534-117">Element</span></span>|<span data-ttu-id="10534-118">Description</span><span class="sxs-lookup"><span data-stu-id="10534-118">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQueries>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="10534-119">コード アクティビティで定義するイベントを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="10534-119">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="10534-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="10534-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="10534-121">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="10534-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="10534-122">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="10534-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
