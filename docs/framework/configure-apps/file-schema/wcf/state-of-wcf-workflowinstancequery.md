---
title: <state>WCF の<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 80f7532f3c51680a2e34713b526dc43822db61b9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854954"
---
# <a name="state-of-wcf-workflowinstancequery"></a><span data-ttu-id="d3f39-102">\<state>WCF の\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="d3f39-102">\<state> of WCF, \<workflowInstanceQuery></span></span>
<span data-ttu-id="d3f39-103">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="d3f39-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="d3f39-104">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3f39-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states-of-wcf-workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**  
  
## <a name="syntax"></a><span data-ttu-id="d3f39-105">構文</span><span class="sxs-lookup"><span data-stu-id="d3f39-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3f39-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="d3f39-106">Attributes and elements</span></span>

<span data-ttu-id="d3f39-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d3f39-107">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="d3f39-108">属性</span><span class="sxs-lookup"><span data-stu-id="d3f39-108">Attributes</span></span>

|<span data-ttu-id="d3f39-109">属性</span><span class="sxs-lookup"><span data-stu-id="d3f39-109">Attribute</span></span>|<span data-ttu-id="d3f39-110">[説明]</span><span class="sxs-lookup"><span data-stu-id="d3f39-110">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="d3f39-111">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="d3f39-111">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3f39-112">子要素</span><span class="sxs-lookup"><span data-stu-id="d3f39-112">Child elements</span></span>

<span data-ttu-id="d3f39-113">なし。</span><span class="sxs-lookup"><span data-stu-id="d3f39-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d3f39-114">親要素</span><span class="sxs-lookup"><span data-stu-id="d3f39-114">Parent elements</span></span>

|<span data-ttu-id="d3f39-115">要素</span><span class="sxs-lookup"><span data-stu-id="d3f39-115">Element</span></span>|<span data-ttu-id="d3f39-116">Description</span><span class="sxs-lookup"><span data-stu-id="d3f39-116">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="d3f39-117">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態のコレクション。</span><span class="sxs-lookup"><span data-stu-id="d3f39-117">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3f39-118">解説</span><span class="sxs-lookup"><span data-stu-id="d3f39-118">Remarks</span></span>  

<span data-ttu-id="d3f39-119">返されたレコードは、このコレクションの状態でフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="d3f39-119">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="d3f39-120">次の表で、使用可能な状態の値について説明します。</span><span class="sxs-lookup"><span data-stu-id="d3f39-120">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="d3f39-121">州</span><span class="sxs-lookup"><span data-stu-id="d3f39-121">State</span></span>|<span data-ttu-id="d3f39-122">Description</span><span class="sxs-lookup"><span data-stu-id="d3f39-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d3f39-123">Aborted</span><span class="sxs-lookup"><span data-stu-id="d3f39-123">Aborted</span></span>|<span data-ttu-id="d3f39-124">ワークフロー インスタンスは中止されました。</span><span class="sxs-lookup"><span data-stu-id="d3f39-124">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="d3f39-125">完了</span><span class="sxs-lookup"><span data-stu-id="d3f39-125">Completed</span></span>|<span data-ttu-id="d3f39-126">ワークフロー インスタンスは完了しました。</span><span class="sxs-lookup"><span data-stu-id="d3f39-126">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="d3f39-127">削除済み</span><span class="sxs-lookup"><span data-stu-id="d3f39-127">Deleted</span></span>|<span data-ttu-id="d3f39-128">ワークフロー インスタンスは削除されました。</span><span class="sxs-lookup"><span data-stu-id="d3f39-128">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="d3f39-129">アイドル</span><span class="sxs-lookup"><span data-stu-id="d3f39-129">Idle</span></span>|<span data-ttu-id="d3f39-130">ワークフロー インスタンスはアイドル状態です。</span><span class="sxs-lookup"><span data-stu-id="d3f39-130">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="d3f39-131">Persisted</span><span class="sxs-lookup"><span data-stu-id="d3f39-131">Persisted</span></span>|<span data-ttu-id="d3f39-132">ワークフロー インスタンスは永続化されました。</span><span class="sxs-lookup"><span data-stu-id="d3f39-132">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="d3f39-133">Resumed</span><span class="sxs-lookup"><span data-stu-id="d3f39-133">Resumed</span></span>|<span data-ttu-id="d3f39-134">ワークフロー インスタンスが再開されました。</span><span class="sxs-lookup"><span data-stu-id="d3f39-134">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="d3f39-135">Started</span><span class="sxs-lookup"><span data-stu-id="d3f39-135">Started</span></span>|<span data-ttu-id="d3f39-136">ワークフロー インスタンスが開始されました。</span><span class="sxs-lookup"><span data-stu-id="d3f39-136">The workflow instance is started.</span></span>|  
|<span data-ttu-id="d3f39-137">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="d3f39-137">UnhandledException</span></span>|<span data-ttu-id="d3f39-138">ワークフロー インスタンスで未処理の例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="d3f39-138">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="d3f39-139">アンロードされました</span><span class="sxs-lookup"><span data-stu-id="d3f39-139">Unloaded</span></span>|<span data-ttu-id="d3f39-140">ワークフロー インスタンスはアンロードされました。</span><span class="sxs-lookup"><span data-stu-id="d3f39-140">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="d3f39-141">Canceled</span><span class="sxs-lookup"><span data-stu-id="d3f39-141">Canceled</span></span>|<span data-ttu-id="d3f39-142">ワークフロー インスタンスは取り消されました。</span><span class="sxs-lookup"><span data-stu-id="d3f39-142">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="d3f39-143">Suspended</span><span class="sxs-lookup"><span data-stu-id="d3f39-143">Suspended</span></span>|<span data-ttu-id="d3f39-144">ワークフロー インスタンスが中断されています。</span><span class="sxs-lookup"><span data-stu-id="d3f39-144">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="d3f39-145">Terminated</span><span class="sxs-lookup"><span data-stu-id="d3f39-145">Terminated</span></span>|<span data-ttu-id="d3f39-146">ワークフロー インスタンスは終了しました。</span><span class="sxs-lookup"><span data-stu-id="d3f39-146">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="d3f39-147">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="d3f39-147">Unsuspended</span></span>|<span data-ttu-id="d3f39-148">ワークフロー インスタンスの中断が解除されました。</span><span class="sxs-lookup"><span data-stu-id="d3f39-148">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d3f39-149">例</span><span class="sxs-lookup"><span data-stu-id="d3f39-149">Example</span></span>

<span data-ttu-id="d3f39-150">次の構成は、このクエリを使用して、`Started` インスタンス状態のワークフロー インスタンス レベルの追跡レコードを定期受信します。</span><span class="sxs-lookup"><span data-stu-id="d3f39-150">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="d3f39-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3f39-151">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d3f39-152">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="d3f39-152">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d3f39-153">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="d3f39-153">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
