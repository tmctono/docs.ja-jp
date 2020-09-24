---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: e759f86e7746eaf3fdd72ed923612b24ef9b0c23
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150818"
---
# \<states>

<span data-ttu-id="eb446-101">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="eb446-101">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="eb446-102">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb446-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**  
  
## <a name="syntax"></a><span data-ttu-id="eb446-103">構文</span><span class="sxs-lookup"><span data-stu-id="eb446-103">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb446-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="eb446-104">Attributes and Elements</span></span>  

 <span data-ttu-id="eb446-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="eb446-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb446-106">属性</span><span class="sxs-lookup"><span data-stu-id="eb446-106">Attributes</span></span>  

 <span data-ttu-id="eb446-107">なし。</span><span class="sxs-lookup"><span data-stu-id="eb446-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eb446-108">子要素</span><span class="sxs-lookup"><span data-stu-id="eb446-108">Child Elements</span></span>  
  
|<span data-ttu-id="eb446-109">要素</span><span class="sxs-lookup"><span data-stu-id="eb446-109">Element</span></span>|<span data-ttu-id="eb446-110">説明</span><span class="sxs-lookup"><span data-stu-id="eb446-110">Description</span></span>|  
|-------------|-----------------|  
|[\<state>](states.md)|<span data-ttu-id="eb446-111">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態。</span><span class="sxs-lookup"><span data-stu-id="eb446-111">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eb446-112">親要素</span><span class="sxs-lookup"><span data-stu-id="eb446-112">Parent Elements</span></span>  
  
|<span data-ttu-id="eb446-113">要素</span><span class="sxs-lookup"><span data-stu-id="eb446-113">Element</span></span>|<span data-ttu-id="eb446-114">説明</span><span class="sxs-lookup"><span data-stu-id="eb446-114">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](workflowinstancequery.md)|<span data-ttu-id="eb446-115">開始したイベントや完了したイベントなど、ワークフロー インスタンスのライフサイクルの変化を追跡するクエリ。</span><span class="sxs-lookup"><span data-stu-id="eb446-115">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb446-116">解説</span><span class="sxs-lookup"><span data-stu-id="eb446-116">Remarks</span></span>  

 <span data-ttu-id="eb446-117">返されたレコードは、このコレクションの状態でフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="eb446-117">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="eb446-118">次の表に、有効な状態の値を示します。</span><span class="sxs-lookup"><span data-stu-id="eb446-118">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="eb446-119">状態</span><span class="sxs-lookup"><span data-stu-id="eb446-119">State</span></span>|<span data-ttu-id="eb446-120">説明</span><span class="sxs-lookup"><span data-stu-id="eb446-120">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eb446-121">Aborted</span><span class="sxs-lookup"><span data-stu-id="eb446-121">Aborted</span></span>|<span data-ttu-id="eb446-122">ワークフロー インスタンスは中止されました。</span><span class="sxs-lookup"><span data-stu-id="eb446-122">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="eb446-123">完了</span><span class="sxs-lookup"><span data-stu-id="eb446-123">Completed</span></span>|<span data-ttu-id="eb446-124">ワークフロー インスタンスは完了しました。</span><span class="sxs-lookup"><span data-stu-id="eb446-124">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="eb446-125">Deleted</span><span class="sxs-lookup"><span data-stu-id="eb446-125">Deleted</span></span>|<span data-ttu-id="eb446-126">ワークフロー インスタンスは削除されました。</span><span class="sxs-lookup"><span data-stu-id="eb446-126">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="eb446-127">アイドル</span><span class="sxs-lookup"><span data-stu-id="eb446-127">Idle</span></span>|<span data-ttu-id="eb446-128">ワークフロー インスタンスはアイドル状態です。</span><span class="sxs-lookup"><span data-stu-id="eb446-128">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="eb446-129">Persisted</span><span class="sxs-lookup"><span data-stu-id="eb446-129">Persisted</span></span>|<span data-ttu-id="eb446-130">ワークフロー インスタンスは永続化されました。</span><span class="sxs-lookup"><span data-stu-id="eb446-130">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="eb446-131">Resumed</span><span class="sxs-lookup"><span data-stu-id="eb446-131">Resumed</span></span>|<span data-ttu-id="eb446-132">ワークフロー インスタンスが再開されました。</span><span class="sxs-lookup"><span data-stu-id="eb446-132">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="eb446-133">Started</span><span class="sxs-lookup"><span data-stu-id="eb446-133">Started</span></span>|<span data-ttu-id="eb446-134">ワークフロー インスタンスが開始されました。</span><span class="sxs-lookup"><span data-stu-id="eb446-134">The workflow instance is started.</span></span>|  
|<span data-ttu-id="eb446-135">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="eb446-135">UnhandledException</span></span>|<span data-ttu-id="eb446-136">ワークフロー インスタンスで未処理の例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="eb446-136">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="eb446-137">アンロードされました</span><span class="sxs-lookup"><span data-stu-id="eb446-137">Unloaded</span></span>|<span data-ttu-id="eb446-138">ワークフロー インスタンスはアンロードされました。</span><span class="sxs-lookup"><span data-stu-id="eb446-138">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="eb446-139">Canceled</span><span class="sxs-lookup"><span data-stu-id="eb446-139">Canceled</span></span>|<span data-ttu-id="eb446-140">ワークフロー インスタンスは取り消されました。</span><span class="sxs-lookup"><span data-stu-id="eb446-140">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="eb446-141">Suspended</span><span class="sxs-lookup"><span data-stu-id="eb446-141">Suspended</span></span>|<span data-ttu-id="eb446-142">ワークフロー インスタンスが中断されています。</span><span class="sxs-lookup"><span data-stu-id="eb446-142">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="eb446-143">終了</span><span class="sxs-lookup"><span data-stu-id="eb446-143">Terminated</span></span>|<span data-ttu-id="eb446-144">ワークフロー インスタンスは終了しました。</span><span class="sxs-lookup"><span data-stu-id="eb446-144">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="eb446-145">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="eb446-145">Unsuspended</span></span>|<span data-ttu-id="eb446-146">ワークフロー インスタンスの中断が解除されました。</span><span class="sxs-lookup"><span data-stu-id="eb446-146">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="eb446-147">例</span><span class="sxs-lookup"><span data-stu-id="eb446-147">Example</span></span>  

 <span data-ttu-id="eb446-148">次の構成は、このクエリを使用して、`Started` インスタンス状態のワークフロー インスタンス レベルの追跡レコードを定期受信します。</span><span class="sxs-lookup"><span data-stu-id="eb446-148">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="eb446-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb446-149">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="eb446-150">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="eb446-150">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="eb446-151">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="eb446-151">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
