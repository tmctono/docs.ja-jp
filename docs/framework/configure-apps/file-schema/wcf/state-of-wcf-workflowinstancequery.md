---
title: <state>WCF の<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 80f7532f3c51680a2e34713b526dc43822db61b9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854954"
---
# <a name="state-of-wcf-workflowinstancequery"></a><span data-ttu-id="1ab7c-102">\<WCF、 \<workflowinstancequery > の状態 ></span><span class="sxs-lookup"><span data-stu-id="1ab7c-102">\<state> of WCF, \<workflowInstanceQuery></span></span>
<span data-ttu-id="1ab7c-103">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="1ab7c-104">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1ab7c-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1ab7c-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1ab7c-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1ab7c-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1ab7c-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<追跡 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="1ab7c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="1ab7c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<プロファイル >** </span><span class="sxs-lookup"><span data-stu-id="1ab7c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="1ab7c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<trackingProfile >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="1ab7c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="1ab7c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ワークフロー >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="1ab7c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="1ab7c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowInstanceQueries >** ](workflowinstancequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="1ab7c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)</span></span>\
<span data-ttu-id="1ab7c-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowInstanceQuery >** ](workflowinstancequery-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="1ab7c-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)</span></span>\
<span data-ttu-id="1ab7c-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<状態 >** ](states-of-wcf-workflowinstancequery.md)</span><span class="sxs-lookup"><span data-stu-id="1ab7c-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states-of-wcf-workflowinstancequery.md)</span></span>\
<span data-ttu-id="1ab7c-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<状態 >**</span><span class="sxs-lookup"><span data-stu-id="1ab7c-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ab7c-115">構文</span><span class="sxs-lookup"><span data-stu-id="1ab7c-115">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
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
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ab7c-116">属性と要素</span><span class="sxs-lookup"><span data-stu-id="1ab7c-116">Attributes and elements</span></span>

<span data-ttu-id="1ab7c-117">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-117">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="1ab7c-118">属性</span><span class="sxs-lookup"><span data-stu-id="1ab7c-118">Attributes</span></span>

|<span data-ttu-id="1ab7c-119">属性</span><span class="sxs-lookup"><span data-stu-id="1ab7c-119">Attribute</span></span>|<span data-ttu-id="1ab7c-120">説明</span><span class="sxs-lookup"><span data-stu-id="1ab7c-120">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="1ab7c-121">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-121">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ab7c-122">子要素</span><span class="sxs-lookup"><span data-stu-id="1ab7c-122">Child elements</span></span>

<span data-ttu-id="1ab7c-123">なし。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1ab7c-124">親要素</span><span class="sxs-lookup"><span data-stu-id="1ab7c-124">Parent elements</span></span>

|<span data-ttu-id="1ab7c-125">要素</span><span class="sxs-lookup"><span data-stu-id="1ab7c-125">Element</span></span>|<span data-ttu-id="1ab7c-126">説明</span><span class="sxs-lookup"><span data-stu-id="1ab7c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ab7c-127">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="1ab7c-127">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="1ab7c-128">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態のコレクション。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-128">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ab7c-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="1ab7c-129">Remarks</span></span>  

<span data-ttu-id="1ab7c-130">返されたレコードは、このコレクションの状態でフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-130">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="1ab7c-131">次の表で、使用可能な状態の値について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-131">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="1ab7c-132">状態</span><span class="sxs-lookup"><span data-stu-id="1ab7c-132">State</span></span>|<span data-ttu-id="1ab7c-133">説明</span><span class="sxs-lookup"><span data-stu-id="1ab7c-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1ab7c-134">Aborted</span><span class="sxs-lookup"><span data-stu-id="1ab7c-134">Aborted</span></span>|<span data-ttu-id="1ab7c-135">ワークフロー インスタンスは中止されました。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-135">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="1ab7c-136">完了</span><span class="sxs-lookup"><span data-stu-id="1ab7c-136">Completed</span></span>|<span data-ttu-id="1ab7c-137">ワークフロー インスタンスは完了しました。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-137">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="1ab7c-138">Deleted</span><span class="sxs-lookup"><span data-stu-id="1ab7c-138">Deleted</span></span>|<span data-ttu-id="1ab7c-139">ワークフロー インスタンスは削除されました。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-139">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="1ab7c-140">アイドル</span><span class="sxs-lookup"><span data-stu-id="1ab7c-140">Idle</span></span>|<span data-ttu-id="1ab7c-141">ワークフロー インスタンスはアイドル状態です。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-141">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="1ab7c-142">Persisted</span><span class="sxs-lookup"><span data-stu-id="1ab7c-142">Persisted</span></span>|<span data-ttu-id="1ab7c-143">ワークフロー インスタンスは永続化されました。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-143">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="1ab7c-144">Resumed</span><span class="sxs-lookup"><span data-stu-id="1ab7c-144">Resumed</span></span>|<span data-ttu-id="1ab7c-145">ワークフロー インスタンスが再開されました。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-145">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="1ab7c-146">Started</span><span class="sxs-lookup"><span data-stu-id="1ab7c-146">Started</span></span>|<span data-ttu-id="1ab7c-147">ワークフロー インスタンスが開始されました。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-147">The workflow instance is started.</span></span>|  
|<span data-ttu-id="1ab7c-148">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="1ab7c-148">UnhandledException</span></span>|<span data-ttu-id="1ab7c-149">ワークフロー インスタンスで未処理の例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-149">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="1ab7c-150">アンロードされました</span><span class="sxs-lookup"><span data-stu-id="1ab7c-150">Unloaded</span></span>|<span data-ttu-id="1ab7c-151">ワークフロー インスタンスはアンロードされました。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-151">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="1ab7c-152">Canceled</span><span class="sxs-lookup"><span data-stu-id="1ab7c-152">Canceled</span></span>|<span data-ttu-id="1ab7c-153">ワークフロー インスタンスは取り消されました。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-153">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="1ab7c-154">中断</span><span class="sxs-lookup"><span data-stu-id="1ab7c-154">Suspended</span></span>|<span data-ttu-id="1ab7c-155">ワークフロー インスタンスが中断されています。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-155">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="1ab7c-156">Terminated</span><span class="sxs-lookup"><span data-stu-id="1ab7c-156">Terminated</span></span>|<span data-ttu-id="1ab7c-157">ワークフロー インスタンスは終了しました。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-157">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="1ab7c-158">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="1ab7c-158">Unsuspended</span></span>|<span data-ttu-id="1ab7c-159">ワークフロー インスタンスの中断が解除されました。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-159">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1ab7c-160">例</span><span class="sxs-lookup"><span data-stu-id="1ab7c-160">Example</span></span>

<span data-ttu-id="1ab7c-161">次の構成は、このクエリを使用して、`Started` インスタンス状態のワークフロー インスタンス レベルの追跡レコードを定期受信します。</span><span class="sxs-lookup"><span data-stu-id="1ab7c-161">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="1ab7c-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ab7c-162">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1ab7c-163">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="1ab7c-163">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1ab7c-164">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="1ab7c-164">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
