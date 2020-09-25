---
title: <arguments>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: cb1f96cb6ba2643e28552c354bdd5caf4d43285c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189644"
---
# \<arguments>

<span data-ttu-id="e35f9-101">アクティビティ状態クエリに関連付けられている引数のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="e35f9-101">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="e35f9-102">追跡プロファイルのクエリの詳細については、「 [追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e35f9-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<arguments>**  
  
## <a name="syntax"></a><span data-ttu-id="e35f9-103">構文</span><span class="sxs-lookup"><span data-stu-id="e35f9-103">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e35f9-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e35f9-104">Attributes and Elements</span></span>  

 <span data-ttu-id="e35f9-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e35f9-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e35f9-106">属性</span><span class="sxs-lookup"><span data-stu-id="e35f9-106">Attributes</span></span>  

 <span data-ttu-id="e35f9-107">なし。</span><span class="sxs-lookup"><span data-stu-id="e35f9-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e35f9-108">子要素</span><span class="sxs-lookup"><span data-stu-id="e35f9-108">Child Elements</span></span>  
  
|<span data-ttu-id="e35f9-109">要素</span><span class="sxs-lookup"><span data-stu-id="e35f9-109">Element</span></span>|<span data-ttu-id="e35f9-110">説明</span><span class="sxs-lookup"><span data-stu-id="e35f9-110">Description</span></span>|  
|-------------|-----------------|  
|[\<argument>](argument.md)|<span data-ttu-id="e35f9-111">アクティビティ状態クエリに関連付けられている引数。</span><span class="sxs-lookup"><span data-stu-id="e35f9-111">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e35f9-112">親要素</span><span class="sxs-lookup"><span data-stu-id="e35f9-112">Parent Elements</span></span>  
  
|<span data-ttu-id="e35f9-113">要素</span><span class="sxs-lookup"><span data-stu-id="e35f9-113">Element</span></span>|<span data-ttu-id="e35f9-114">説明</span><span class="sxs-lookup"><span data-stu-id="e35f9-114">Description</span></span>|  
|-------------|-----------------|  
|[\<activityStateQuery>](activitystatequery.md)|<span data-ttu-id="e35f9-115">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="e35f9-115">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="e35f9-116">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="e35f9-116">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e35f9-117">解説</span><span class="sxs-lookup"><span data-stu-id="e35f9-117">Remarks</span></span>  

 <span data-ttu-id="e35f9-118">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="e35f9-118">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="e35f9-119">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="e35f9-119">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="e35f9-120">、、およびの各要素を使用して、 [\<arguments>](arguments.md) [\<states>](states.md) [\<states>](states.md) ワークフロー内の任意のアクティビティから任意の変数または引数を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="e35f9-120">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="e35f9-121">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="e35f9-121">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="e35f9-122">変数と引数は、ActivityStateRecord でのみ抽出できるため、を使用して追跡プロファイル内でサブスクライブされ [\<activityStateQuery>](activitystatequery.md) ます。</span><span class="sxs-lookup"><span data-stu-id="e35f9-122">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e35f9-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="e35f9-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e35f9-124">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="e35f9-124">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e35f9-125">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="e35f9-125">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
