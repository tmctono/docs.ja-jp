---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 7af75182cf38a6acb8a31b71e8b7b42103f8046b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398648"
---
# \<state>
<span data-ttu-id="898ed-101">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="898ed-101">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="898ed-102">追跡プロファイルのクエリの詳細については、「[追跡プロファイル](../../../windows-workflow-foundation/tracking-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="898ed-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**  
  
## <a name="syntax"></a><span data-ttu-id="898ed-103">構文</span><span class="sxs-lookup"><span data-stu-id="898ed-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="898ed-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="898ed-104">Attributes and Elements</span></span>  
 <span data-ttu-id="898ed-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="898ed-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="898ed-106">属性</span><span class="sxs-lookup"><span data-stu-id="898ed-106">Attributes</span></span>  
  
|<span data-ttu-id="898ed-107">属性</span><span class="sxs-lookup"><span data-stu-id="898ed-107">Attribute</span></span>|<span data-ttu-id="898ed-108">説明</span><span class="sxs-lookup"><span data-stu-id="898ed-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="898ed-109">name</span><span class="sxs-lookup"><span data-stu-id="898ed-109">name</span></span>|<span data-ttu-id="898ed-110">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="898ed-110">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="898ed-111">子要素</span><span class="sxs-lookup"><span data-stu-id="898ed-111">Child Elements</span></span>  
 <span data-ttu-id="898ed-112">なし。</span><span class="sxs-lookup"><span data-stu-id="898ed-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="898ed-113">親要素</span><span class="sxs-lookup"><span data-stu-id="898ed-113">Parent Elements</span></span>  
  
|<span data-ttu-id="898ed-114">要素</span><span class="sxs-lookup"><span data-stu-id="898ed-114">Element</span></span>|<span data-ttu-id="898ed-115">Description</span><span class="sxs-lookup"><span data-stu-id="898ed-115">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](states.md)|<span data-ttu-id="898ed-116">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態のコレクション。</span><span class="sxs-lookup"><span data-stu-id="898ed-116">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="898ed-117">解説</span><span class="sxs-lookup"><span data-stu-id="898ed-117">Remarks</span></span>  
 <span data-ttu-id="898ed-118">返されたレコードは、このコレクションの状態でフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="898ed-118">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="898ed-119">次の表に、有効な状態の値を示します。</span><span class="sxs-lookup"><span data-stu-id="898ed-119">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="898ed-120">州</span><span class="sxs-lookup"><span data-stu-id="898ed-120">State</span></span>|<span data-ttu-id="898ed-121">Description</span><span class="sxs-lookup"><span data-stu-id="898ed-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="898ed-122">Aborted</span><span class="sxs-lookup"><span data-stu-id="898ed-122">Aborted</span></span>|<span data-ttu-id="898ed-123">ワークフロー インスタンスは中止されました。</span><span class="sxs-lookup"><span data-stu-id="898ed-123">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="898ed-124">完了</span><span class="sxs-lookup"><span data-stu-id="898ed-124">Completed</span></span>|<span data-ttu-id="898ed-125">ワークフロー インスタンスは完了しました。</span><span class="sxs-lookup"><span data-stu-id="898ed-125">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="898ed-126">削除済み</span><span class="sxs-lookup"><span data-stu-id="898ed-126">Deleted</span></span>|<span data-ttu-id="898ed-127">ワークフロー インスタンスは削除されました。</span><span class="sxs-lookup"><span data-stu-id="898ed-127">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="898ed-128">アイドル</span><span class="sxs-lookup"><span data-stu-id="898ed-128">Idle</span></span>|<span data-ttu-id="898ed-129">ワークフロー インスタンスはアイドル状態です。</span><span class="sxs-lookup"><span data-stu-id="898ed-129">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="898ed-130">Persisted</span><span class="sxs-lookup"><span data-stu-id="898ed-130">Persisted</span></span>|<span data-ttu-id="898ed-131">ワークフロー インスタンスは永続化されました。</span><span class="sxs-lookup"><span data-stu-id="898ed-131">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="898ed-132">Resumed</span><span class="sxs-lookup"><span data-stu-id="898ed-132">Resumed</span></span>|<span data-ttu-id="898ed-133">ワークフロー インスタンスが再開されました。</span><span class="sxs-lookup"><span data-stu-id="898ed-133">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="898ed-134">Started</span><span class="sxs-lookup"><span data-stu-id="898ed-134">Started</span></span>|<span data-ttu-id="898ed-135">ワークフロー インスタンスが開始されました。</span><span class="sxs-lookup"><span data-stu-id="898ed-135">The workflow instance is started.</span></span>|  
|<span data-ttu-id="898ed-136">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="898ed-136">UnhandledException</span></span>|<span data-ttu-id="898ed-137">ワークフロー インスタンスで未処理の例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="898ed-137">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="898ed-138">アンロードされました</span><span class="sxs-lookup"><span data-stu-id="898ed-138">Unloaded</span></span>|<span data-ttu-id="898ed-139">ワークフロー インスタンスはアンロードされました。</span><span class="sxs-lookup"><span data-stu-id="898ed-139">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="898ed-140">Canceled</span><span class="sxs-lookup"><span data-stu-id="898ed-140">Canceled</span></span>|<span data-ttu-id="898ed-141">ワークフロー インスタンスは取り消されました。</span><span class="sxs-lookup"><span data-stu-id="898ed-141">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="898ed-142">Suspended</span><span class="sxs-lookup"><span data-stu-id="898ed-142">Suspended</span></span>|<span data-ttu-id="898ed-143">ワークフロー インスタンスが中断されています。</span><span class="sxs-lookup"><span data-stu-id="898ed-143">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="898ed-144">Terminated</span><span class="sxs-lookup"><span data-stu-id="898ed-144">Terminated</span></span>|<span data-ttu-id="898ed-145">ワークフロー インスタンスは終了しました。</span><span class="sxs-lookup"><span data-stu-id="898ed-145">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="898ed-146">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="898ed-146">Unsuspended</span></span>|<span data-ttu-id="898ed-147">ワークフロー インスタンスの中断が解除されました。</span><span class="sxs-lookup"><span data-stu-id="898ed-147">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="898ed-148">例</span><span class="sxs-lookup"><span data-stu-id="898ed-148">Example</span></span>  
 <span data-ttu-id="898ed-149">次の構成は、このクエリを使用して、`Started` インスタンス状態のワークフロー インスタンス レベルの追跡レコードを定期受信します。</span><span class="sxs-lookup"><span data-stu-id="898ed-149">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="898ed-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="898ed-150">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="898ed-151">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="898ed-151">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="898ed-152">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="898ed-152">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
