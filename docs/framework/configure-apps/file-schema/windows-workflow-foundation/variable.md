---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: 5878720f51f4b5cfe3163abf316a867ccda31342
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397776"
---
# \<variable>
<span data-ttu-id="60a20-101">このアクティビティ クエリに関連付けられている変数のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="60a20-101">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="60a20-102">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60a20-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<variables>**](variables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<variable>**  
  
## <a name="syntax"></a><span data-ttu-id="60a20-103">構文</span><span class="sxs-lookup"><span data-stu-id="60a20-103">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <variables>
          <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60a20-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="60a20-104">Attributes and Elements</span></span>  
 <span data-ttu-id="60a20-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="60a20-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60a20-106">属性</span><span class="sxs-lookup"><span data-stu-id="60a20-106">Attributes</span></span>  
  
|<span data-ttu-id="60a20-107">属性</span><span class="sxs-lookup"><span data-stu-id="60a20-107">Attribute</span></span>|<span data-ttu-id="60a20-108">説明</span><span class="sxs-lookup"><span data-stu-id="60a20-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="60a20-109">name</span><span class="sxs-lookup"><span data-stu-id="60a20-109">name</span></span>|<span data-ttu-id="60a20-110">変数の名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="60a20-110">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60a20-111">子要素</span><span class="sxs-lookup"><span data-stu-id="60a20-111">Child Elements</span></span>  
 <span data-ttu-id="60a20-112">なし。</span><span class="sxs-lookup"><span data-stu-id="60a20-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60a20-113">親要素</span><span class="sxs-lookup"><span data-stu-id="60a20-113">Parent Elements</span></span>  
  
|<span data-ttu-id="60a20-114">要素</span><span class="sxs-lookup"><span data-stu-id="60a20-114">Element</span></span>|<span data-ttu-id="60a20-115">Description</span><span class="sxs-lookup"><span data-stu-id="60a20-115">Description</span></span>|  
|-------------|-----------------|  
|[\<variable>](variable.md)|<span data-ttu-id="60a20-116">アクティビティ状態クエリに関連付けられている変数。</span><span class="sxs-lookup"><span data-stu-id="60a20-116">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60a20-117">解説</span><span class="sxs-lookup"><span data-stu-id="60a20-117">Remarks</span></span>  
 <span data-ttu-id="60a20-118">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="60a20-118">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="60a20-119">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="60a20-119">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="60a20-120">、、およびの各要素を使用して、 [\<arguments>](arguments.md) [\<states>](states.md) [\<states>](states.md) ワークフロー内の任意のアクティビティから任意の変数または引数を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="60a20-120">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="60a20-121">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="60a20-121">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="60a20-122">変数と引数は、ActivityStateRecord でのみ抽出できるため、を使用して追跡プロファイル内でサブスクライブされ [\<activityStateQuery>](activitystatequery.md) ます。</span><span class="sxs-lookup"><span data-stu-id="60a20-122">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="60a20-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="60a20-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="60a20-124">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="60a20-124">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="60a20-125">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="60a20-125">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
