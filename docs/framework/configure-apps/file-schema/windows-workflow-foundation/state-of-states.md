---
title: <state> の <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
ms.openlocfilehash: 391e552bce34d637a324c78702cb0e7121f2c999
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398650"
---
# <a name="state-of-states"></a><span data-ttu-id="07c22-102">\<state> の \<states></span><span class="sxs-lookup"><span data-stu-id="07c22-102">\<state> of \<states></span></span>
<span data-ttu-id="07c22-103">追跡レコードを生成する必要がある定期受信済みアクティビティの状態を含む構成要素。</span><span class="sxs-lookup"><span data-stu-id="07c22-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="07c22-104">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07c22-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states-of-activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**  
  
## <a name="syntax"></a><span data-ttu-id="07c22-105">構文</span><span class="sxs-lookup"><span data-stu-id="07c22-105">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <states>
          <state name="String" />
        </states>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07c22-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="07c22-106">Attributes and Elements</span></span>  
 <span data-ttu-id="07c22-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="07c22-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07c22-108">属性</span><span class="sxs-lookup"><span data-stu-id="07c22-108">Attributes</span></span>  
  
|<span data-ttu-id="07c22-109">属性</span><span class="sxs-lookup"><span data-stu-id="07c22-109">Attribute</span></span>|<span data-ttu-id="07c22-110">説明</span><span class="sxs-lookup"><span data-stu-id="07c22-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="07c22-111">name</span><span class="sxs-lookup"><span data-stu-id="07c22-111">name</span></span>|<span data-ttu-id="07c22-112">追跡レコードを生成する必要がある定期受信済みアクティビティの状態を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="07c22-112">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="07c22-113">子要素</span><span class="sxs-lookup"><span data-stu-id="07c22-113">Child Elements</span></span>  
 <span data-ttu-id="07c22-114">なし。</span><span class="sxs-lookup"><span data-stu-id="07c22-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="07c22-115">親要素</span><span class="sxs-lookup"><span data-stu-id="07c22-115">Parent Elements</span></span>  
  
|<span data-ttu-id="07c22-116">要素</span><span class="sxs-lookup"><span data-stu-id="07c22-116">Element</span></span>|<span data-ttu-id="07c22-117">Description</span><span class="sxs-lookup"><span data-stu-id="07c22-117">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](states-of-activitystatequery.md)|<span data-ttu-id="07c22-118">追跡レコードを生成する必要がある定期受信済みアクティビティの状態を含む構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="07c22-118">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07c22-119">解説</span><span class="sxs-lookup"><span data-stu-id="07c22-119">Remarks</span></span>  
 <span data-ttu-id="07c22-120">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="07c22-120">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="07c22-121">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="07c22-121">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="07c22-122">、、およびの各要素を使用して、 [\<arguments>](arguments.md) [\<states>](states.md) [\<states>](states.md) ワークフロー内の任意のアクティビティから任意の変数または引数を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="07c22-122">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="07c22-123">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="07c22-123">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="07c22-124">変数と引数は、ActivityStateRecord でのみ抽出できるため、を使用して追跡プロファイル内でサブスクライブされ [\<activityStateQuery>](activitystatequery.md) ます。</span><span class="sxs-lookup"><span data-stu-id="07c22-124">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="07c22-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="07c22-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="07c22-126">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="07c22-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="07c22-127">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="07c22-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
