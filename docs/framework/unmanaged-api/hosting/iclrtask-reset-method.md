---
title: ICLRTask::Reset メソッド
ms.date: 03/30/2017
api_name:
- ICLRTask.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Reset
helpviewer_keywords:
- ICLRTask::Reset method [.NET Framework hosting]
- Reset method, ICLRTask interface [.NET Framework hosting]
ms.assetid: 1bfb5d3a-0ffd-4bb4-9bf6-aec00cb675b7
topic_type:
- apiref
ms.openlocfilehash: 17fca3e5a2d763277d3a5f9f72e2d35be6fc350c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124639"
---
# <a name="iclrtaskreset-method"></a><span data-ttu-id="e7ebf-102">ICLRTask::Reset メソッド</span><span class="sxs-lookup"><span data-stu-id="e7ebf-102">ICLRTask::Reset Method</span></span>
<span data-ttu-id="e7ebf-103">ホストがタスクを完了したことを共通言語ランタイム (CLR) に通知し、CLR が現在の[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンスを再利用して別のタスクを表すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-103">Informs the common language runtime (CLR) that the host has completed a task, and enables the CLR to reuse the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance to represent another task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7ebf-104">構文</span><span class="sxs-lookup"><span data-stu-id="e7ebf-104">Syntax</span></span>  
  
```cpp  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7ebf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e7ebf-105">Parameters</span></span>  
 `fFull`  
 <span data-ttu-id="e7ebf-106">[in] `true`、現在の `ICLRTask` インスタンスに関連するセキュリティおよびロケール情報に加えて、ランタイムがスレッド関連のすべての静的な値をリセットする必要がある場合はです。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-106">[in] `true`, if the runtime should reset all thread-related static values in addition to the security and locale information related to the current `ICLRTask` instance; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="e7ebf-107">値が `true`場合、ランタイムは <xref:System.Threading.Thread.AllocateDataSlot%2A> または <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>を使用して格納されたデータをリセットします。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-107">If the value is `true`, the runtime resets data that was stored using <xref:System.Threading.Thread.AllocateDataSlot%2A> or <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7ebf-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="e7ebf-108">Return Value</span></span>  
  
|<span data-ttu-id="e7ebf-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e7ebf-109">HRESULT</span></span>|<span data-ttu-id="e7ebf-110">説明</span><span class="sxs-lookup"><span data-stu-id="e7ebf-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e7ebf-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e7ebf-111">S_OK</span></span>|<span data-ttu-id="e7ebf-112">`Reset` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-112">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="e7ebf-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e7ebf-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e7ebf-114">CLR がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しを処理できません。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="e7ebf-115">なく</span><span class="sxs-lookup"><span data-stu-id="e7ebf-115">successfully</span></span>|  
|<span data-ttu-id="e7ebf-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e7ebf-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e7ebf-117">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-117">The call timed out.</span></span>|  
|<span data-ttu-id="e7ebf-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e7ebf-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e7ebf-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e7ebf-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e7ebf-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e7ebf-121">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e7ebf-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e7ebf-122">E_FAIL</span></span>|<span data-ttu-id="e7ebf-123">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e7ebf-124">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e7ebf-125">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7ebf-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="e7ebf-126">Remarks</span></span>  
 <span data-ttu-id="e7ebf-127">CLR は、新しく作成された `ICLRTask` インスタンスをリサイクルして、新しいタスクが必要になるたびに新しいインスタンスを繰り返し作成するオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-127">The CLR can recycle previously created `ICLRTask` instances to avoid the overhead of repeatedly creating new instances every time it needs a fresh task.</span></span> <span data-ttu-id="e7ebf-128">ホストは、タスクを完了したときに、 [ICLRTask:: ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)ではなく `ICLRTask::Reset` を呼び出すことによって、この機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-128">The host enables this feature by calling `ICLRTask::Reset` instead of [ICLRTask::ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) when it has completed a task.</span></span> <span data-ttu-id="e7ebf-129">次の一覧は、`ICLRTask` インスタンスの通常のライフサイクルをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-129">The following list summarizes the normal life cycle of an `ICLRTask` instance:</span></span>  
  
1. <span data-ttu-id="e7ebf-130">ランタイムは、新しい `ICLRTask` インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-130">The runtime creates a new `ICLRTask` instance.</span></span>  
  
2. <span data-ttu-id="e7ebf-131">ランタイムは、 [IHostTaskManager:: GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)を呼び出して、現在のホストタスクへの参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-131">The runtime calls [IHostTaskManager::GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) to get a reference to the current host task.</span></span>  
  
3. <span data-ttu-id="e7ebf-132">ランタイムは、新しいインスタンスをホストタスクに関連付けるために、 [IHostTask:: SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-132">The runtime calls [IHostTask::SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) to associate the new instance with the host task.</span></span>  
  
4. <span data-ttu-id="e7ebf-133">タスクが実行され、完了します。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-133">The task executes and completes.</span></span>  
  
5. <span data-ttu-id="e7ebf-134">ホストは `ICLRTask::ExitTask`を呼び出すことによってタスクを破棄します。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-134">The host destroys the task by calling `ICLRTask::ExitTask`.</span></span>  
  
 <span data-ttu-id="e7ebf-135">`Reset` は、このシナリオを次の2つの方法で変更します。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-135">`Reset` alters this scenario in two ways.</span></span> <span data-ttu-id="e7ebf-136">上記の手順5では、ホストは `Reset` を呼び出して、タスクをクリーンな状態にリセットしてから、関連付けられている[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)インスタンスから `ICLRTask` インスタンスを切り離します。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-136">In step 5 above, the host calls `Reset` to reset the task to a clean state, and then decouples the `ICLRTask` instance from its associated [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span> <span data-ttu-id="e7ebf-137">必要に応じて、ホストは `IHostTask` インスタンスをキャッシュして再利用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-137">If desired, the host can also cache the `IHostTask` instance for reuse.</span></span> <span data-ttu-id="e7ebf-138">上記の手順 1. では、ランタイムは、新しいインスタンスを作成する代わりに、リサイクルされた `ICLRTask` をキャッシュから取得します。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-138">In step 1 above, the runtime pulls a recycled `ICLRTask` from the cache instead of creating a new instance.</span></span>  
  
 <span data-ttu-id="e7ebf-139">この方法は、ホストに再利用可能なワーカータスクのプールがある場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-139">This approach works well when the host also has a pool of reusable worker tasks.</span></span> <span data-ttu-id="e7ebf-140">ホストが `IHostTask` インスタンスのいずれかを破棄すると、`ExitTask`を呼び出すことによって、対応する `ICLRTask` が破棄されます。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-140">When the host destroys one of its `IHostTask` instances, it destroys the corresponding `ICLRTask` by calling `ExitTask`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7ebf-141">［要件］</span><span class="sxs-lookup"><span data-stu-id="e7ebf-141">Requirements</span></span>  
 <span data-ttu-id="e7ebf-142">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7ebf-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7ebf-143">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e7ebf-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e7ebf-144">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="e7ebf-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7ebf-145">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7ebf-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7ebf-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7ebf-146">See also</span></span>

- [<span data-ttu-id="e7ebf-147">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e7ebf-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e7ebf-148">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e7ebf-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e7ebf-149">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e7ebf-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="e7ebf-150">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e7ebf-150">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
