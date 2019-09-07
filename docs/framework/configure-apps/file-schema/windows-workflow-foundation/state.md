---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 7af75182cf38a6acb8a31b71e8b7b42103f8046b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398648"
---
# <a name="state"></a><span data-ttu-id="5d27b-101">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="5d27b-101">\<state></span></span>
<span data-ttu-id="5d27b-102">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="5d27b-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="5d27b-103">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d27b-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="5d27b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5d27b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5d27b-105">&nbsp;&nbsp;[ **\<system.ServiceModel >** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5d27b-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="5d27b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="5d27b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="5d27b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="5d27b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="5d27b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5d27b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="5d27b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowInstanceQueries >** ](workflowinstancequeries.md)</span><span class="sxs-lookup"><span data-stu-id="5d27b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)</span></span>\
<span data-ttu-id="5d27b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowInstanceQuery >** ](workflowinstancequery.md)</span><span class="sxs-lookup"><span data-stu-id="5d27b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)</span></span>\
<span data-ttu-id="5d27b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<状態 >** ](states.md)</span><span class="sxs-lookup"><span data-stu-id="5d27b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states.md)</span></span>\
<span data-ttu-id="5d27b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<状態 >**</span><span class="sxs-lookup"><span data-stu-id="5d27b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d27b-113">構文</span><span class="sxs-lookup"><span data-stu-id="5d27b-113">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name" />
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d27b-114">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5d27b-114">Attributes and Elements</span></span>  
 <span data-ttu-id="5d27b-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d27b-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d27b-116">属性</span><span class="sxs-lookup"><span data-stu-id="5d27b-116">Attributes</span></span>  
  
|<span data-ttu-id="5d27b-117">属性</span><span class="sxs-lookup"><span data-stu-id="5d27b-117">Attribute</span></span>|<span data-ttu-id="5d27b-118">説明</span><span class="sxs-lookup"><span data-stu-id="5d27b-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5d27b-119">name</span><span class="sxs-lookup"><span data-stu-id="5d27b-119">name</span></span>|<span data-ttu-id="5d27b-120">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="5d27b-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d27b-121">子要素</span><span class="sxs-lookup"><span data-stu-id="5d27b-121">Child Elements</span></span>  
 <span data-ttu-id="5d27b-122">なし。</span><span class="sxs-lookup"><span data-stu-id="5d27b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5d27b-123">親要素</span><span class="sxs-lookup"><span data-stu-id="5d27b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5d27b-124">要素</span><span class="sxs-lookup"><span data-stu-id="5d27b-124">Element</span></span>|<span data-ttu-id="5d27b-125">説明</span><span class="sxs-lookup"><span data-stu-id="5d27b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d27b-126">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="5d27b-126">\<states></span></span>](states.md)|<span data-ttu-id="5d27b-127">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態のコレクション。</span><span class="sxs-lookup"><span data-stu-id="5d27b-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d27b-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="5d27b-128">Remarks</span></span>  
 <span data-ttu-id="5d27b-129">返されたレコードは、このコレクションの状態でフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="5d27b-129">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="5d27b-130">次の表に、有効な状態の値を示します。</span><span class="sxs-lookup"><span data-stu-id="5d27b-130">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="5d27b-131">状態</span><span class="sxs-lookup"><span data-stu-id="5d27b-131">State</span></span>|<span data-ttu-id="5d27b-132">説明</span><span class="sxs-lookup"><span data-stu-id="5d27b-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5d27b-133">Aborted</span><span class="sxs-lookup"><span data-stu-id="5d27b-133">Aborted</span></span>|<span data-ttu-id="5d27b-134">ワークフロー インスタンスは中止されました。</span><span class="sxs-lookup"><span data-stu-id="5d27b-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="5d27b-135">完了</span><span class="sxs-lookup"><span data-stu-id="5d27b-135">Completed</span></span>|<span data-ttu-id="5d27b-136">ワークフロー インスタンスは完了しました。</span><span class="sxs-lookup"><span data-stu-id="5d27b-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="5d27b-137">Deleted</span><span class="sxs-lookup"><span data-stu-id="5d27b-137">Deleted</span></span>|<span data-ttu-id="5d27b-138">ワークフロー インスタンスは削除されました。</span><span class="sxs-lookup"><span data-stu-id="5d27b-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="5d27b-139">アイドル</span><span class="sxs-lookup"><span data-stu-id="5d27b-139">Idle</span></span>|<span data-ttu-id="5d27b-140">ワークフロー インスタンスはアイドル状態です。</span><span class="sxs-lookup"><span data-stu-id="5d27b-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="5d27b-141">Persisted</span><span class="sxs-lookup"><span data-stu-id="5d27b-141">Persisted</span></span>|<span data-ttu-id="5d27b-142">ワークフロー インスタンスは永続化されました。</span><span class="sxs-lookup"><span data-stu-id="5d27b-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="5d27b-143">Resumed</span><span class="sxs-lookup"><span data-stu-id="5d27b-143">Resumed</span></span>|<span data-ttu-id="5d27b-144">ワークフロー インスタンスが再開されました。</span><span class="sxs-lookup"><span data-stu-id="5d27b-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="5d27b-145">Started</span><span class="sxs-lookup"><span data-stu-id="5d27b-145">Started</span></span>|<span data-ttu-id="5d27b-146">ワークフロー インスタンスが開始されました。</span><span class="sxs-lookup"><span data-stu-id="5d27b-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="5d27b-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="5d27b-147">UnhandledException</span></span>|<span data-ttu-id="5d27b-148">ワークフロー インスタンスで未処理の例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="5d27b-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="5d27b-149">アンロードされました</span><span class="sxs-lookup"><span data-stu-id="5d27b-149">Unloaded</span></span>|<span data-ttu-id="5d27b-150">ワークフロー インスタンスはアンロードされました。</span><span class="sxs-lookup"><span data-stu-id="5d27b-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="5d27b-151">Canceled</span><span class="sxs-lookup"><span data-stu-id="5d27b-151">Canceled</span></span>|<span data-ttu-id="5d27b-152">ワークフロー インスタンスは取り消されました。</span><span class="sxs-lookup"><span data-stu-id="5d27b-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="5d27b-153">中断</span><span class="sxs-lookup"><span data-stu-id="5d27b-153">Suspended</span></span>|<span data-ttu-id="5d27b-154">ワークフロー インスタンスが中断されています。</span><span class="sxs-lookup"><span data-stu-id="5d27b-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="5d27b-155">Terminated</span><span class="sxs-lookup"><span data-stu-id="5d27b-155">Terminated</span></span>|<span data-ttu-id="5d27b-156">ワークフロー インスタンスは終了しました。</span><span class="sxs-lookup"><span data-stu-id="5d27b-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="5d27b-157">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="5d27b-157">Unsuspended</span></span>|<span data-ttu-id="5d27b-158">ワークフロー インスタンスの中断が解除されました。</span><span class="sxs-lookup"><span data-stu-id="5d27b-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5d27b-159">例</span><span class="sxs-lookup"><span data-stu-id="5d27b-159">Example</span></span>  
 <span data-ttu-id="5d27b-160">次の構成は、このクエリを使用して、`Started` インスタンス状態のワークフロー インスタンス レベルの追跡レコードを定期受信します。</span><span class="sxs-lookup"><span data-stu-id="5d27b-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5d27b-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d27b-161">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5d27b-162">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="5d27b-162">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5d27b-163">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="5d27b-163">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
