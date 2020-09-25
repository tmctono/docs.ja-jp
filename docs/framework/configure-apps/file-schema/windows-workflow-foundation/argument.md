---
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: 72a2d6f8439e720bb7bf236bd942552224e85501
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189728"
---
# \<argument>

<span data-ttu-id="bba4d-101">アクティビティ状態クエリに関連付けられている引数を表す構成要素。</span><span class="sxs-lookup"><span data-stu-id="bba4d-101">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="bba4d-102">追跡プロファイルのクエリの詳細については、「 [追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bba4d-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<arguments>**](arguments.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<argument>**  
  
## <a name="syntax"></a><span data-ttu-id="bba4d-103">構文</span><span class="sxs-lookup"><span data-stu-id="bba4d-103">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bba4d-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bba4d-104">Attributes and Elements</span></span>  

 <span data-ttu-id="bba4d-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bba4d-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bba4d-106">属性</span><span class="sxs-lookup"><span data-stu-id="bba4d-106">Attributes</span></span>  
  
|<span data-ttu-id="bba4d-107">属性</span><span class="sxs-lookup"><span data-stu-id="bba4d-107">Attribute</span></span>|<span data-ttu-id="bba4d-108">説明</span><span class="sxs-lookup"><span data-stu-id="bba4d-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bba4d-109">name</span><span class="sxs-lookup"><span data-stu-id="bba4d-109">name</span></span>|<span data-ttu-id="bba4d-110">この引数の名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="bba4d-110">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bba4d-111">子要素</span><span class="sxs-lookup"><span data-stu-id="bba4d-111">Child Elements</span></span>  

 <span data-ttu-id="bba4d-112">なし。</span><span class="sxs-lookup"><span data-stu-id="bba4d-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bba4d-113">親要素</span><span class="sxs-lookup"><span data-stu-id="bba4d-113">Parent Elements</span></span>  
  
|<span data-ttu-id="bba4d-114">要素</span><span class="sxs-lookup"><span data-stu-id="bba4d-114">Element</span></span>|<span data-ttu-id="bba4d-115">説明</span><span class="sxs-lookup"><span data-stu-id="bba4d-115">Description</span></span>|  
|-------------|-----------------|  
|[\<arguments>](arguments.md)|<span data-ttu-id="bba4d-116">このアクティビティ クエリに関連付けられている引数のコレクション。</span><span class="sxs-lookup"><span data-stu-id="bba4d-116">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bba4d-117">解説</span><span class="sxs-lookup"><span data-stu-id="bba4d-117">Remarks</span></span>  

 <span data-ttu-id="bba4d-118">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="bba4d-118">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="bba4d-119">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="bba4d-119">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="bba4d-120">、、およびの各要素を使用して、 [\<arguments>](arguments.md) [\<states>](states.md) [\<states>](states.md) ワークフロー内の任意のアクティビティから任意の変数または引数を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="bba4d-120">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="bba4d-121">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="bba4d-121">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="bba4d-122">変数と引数は、ActivityStateRecord でのみ抽出できるため、を使用して追跡プロファイル内でサブスクライブされ [\<activityStateQuery>](activitystatequery.md) ます。</span><span class="sxs-lookup"><span data-stu-id="bba4d-122">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bba4d-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="bba4d-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="bba4d-124">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="bba4d-124">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="bba4d-125">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="bba4d-125">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
