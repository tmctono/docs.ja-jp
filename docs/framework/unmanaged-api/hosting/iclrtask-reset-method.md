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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13bf7342157de48e0183537afea2f2e53d1498dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763491"
---
# <a name="iclrtaskreset-method"></a><span data-ttu-id="dc6fa-102">ICLRTask::Reset メソッド</span><span class="sxs-lookup"><span data-stu-id="dc6fa-102">ICLRTask::Reset Method</span></span>
<span data-ttu-id="dc6fa-103">ホストは、タスクを完了し、現在を再利用する CLR を有効に、共通言語ランタイム (CLR) を通知[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)を別のタスクを表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-103">Informs the common language runtime (CLR) that the host has completed a task, and enables the CLR to reuse the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance to represent another task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc6fa-104">構文</span><span class="sxs-lookup"><span data-stu-id="dc6fa-104">Syntax</span></span>  
  
```  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc6fa-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dc6fa-105">Parameters</span></span>  
 `fFull`  
 <span data-ttu-id="dc6fa-106">[in]`true`場合は、ランタイムは、現在に関連するセキュリティとロケール情報だけでなく、スレッド関連の静的な値をリセットする必要があります、`ICLRTask`インスタンス。 それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-106">[in] `true`, if the runtime should reset all thread-related static values in addition to the security and locale information related to the current `ICLRTask` instance; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="dc6fa-107">値が場合`true`、ランタイムを使用して格納されたデータをリセットする<xref:System.Threading.Thread.AllocateDataSlot%2A>または<xref:System.Threading.Thread.AllocateNamedDataSlot%2A>します。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-107">If the value is `true`, the runtime resets data that was stored using <xref:System.Threading.Thread.AllocateDataSlot%2A> or <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc6fa-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="dc6fa-108">Return Value</span></span>  
  
|<span data-ttu-id="dc6fa-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dc6fa-109">HRESULT</span></span>|<span data-ttu-id="dc6fa-110">説明</span><span class="sxs-lookup"><span data-stu-id="dc6fa-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dc6fa-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="dc6fa-111">S_OK</span></span>|<span data-ttu-id="dc6fa-112">`Reset` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-112">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="dc6fa-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dc6fa-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dc6fa-114">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しの処理にことはできません。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="dc6fa-115">正常に</span><span class="sxs-lookup"><span data-stu-id="dc6fa-115">successfully</span></span>|  
|<span data-ttu-id="dc6fa-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dc6fa-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dc6fa-117">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-117">The call timed out.</span></span>|  
|<span data-ttu-id="dc6fa-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dc6fa-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dc6fa-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dc6fa-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dc6fa-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dc6fa-121">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dc6fa-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dc6fa-122">E_FAIL</span></span>|<span data-ttu-id="dc6fa-123">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dc6fa-124">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dc6fa-125">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc6fa-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="dc6fa-126">Remarks</span></span>  
 <span data-ttu-id="dc6fa-127">以前に作成した、CLR をリサイクルできます`ICLRTask`インスタンスに新しいタスクが必要があるたびに、新しいインスタンスを繰り返し作成のオーバーヘッドを回避します。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-127">The CLR can recycle previously created `ICLRTask` instances to avoid the overhead of repeatedly creating new instances every time it needs a fresh task.</span></span> <span data-ttu-id="dc6fa-128">ホストが呼び出すことによってこの機能を有効`ICLRTask::Reset`の代わりに[iclrtask::exittask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)タスクを完了したとき。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-128">The host enables this feature by calling `ICLRTask::Reset` instead of [ICLRTask::ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) when it has completed a task.</span></span> <span data-ttu-id="dc6fa-129">次の一覧は、通常のライフ サイクルをまとめたものです、`ICLRTask`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-129">The following list summarizes the normal life cycle of an `ICLRTask` instance:</span></span>  
  
1. <span data-ttu-id="dc6fa-130">新しいランタイムを作成`ICLRTask`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-130">The runtime creates a new `ICLRTask` instance.</span></span>  
  
2. <span data-ttu-id="dc6fa-131">ランタイム呼び出し[ihosttaskmanager::getcurrenttask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)ホストの現在のタスクへの参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-131">The runtime calls [IHostTaskManager::GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) to get a reference to the current host task.</span></span>  
  
3. <span data-ttu-id="dc6fa-132">ランタイム呼び出し[ihosttask::setclrtask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)に新しいインスタンスを関連付けるホスト タスク。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-132">The runtime calls [IHostTask::SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) to associate the new instance with the host task.</span></span>  
  
4. <span data-ttu-id="dc6fa-133">タスクを実行し、完了します。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-133">The task executes and completes.</span></span>  
  
5. <span data-ttu-id="dc6fa-134">ホストが呼び出すことによって、タスクを破棄`ICLRTask::ExitTask`します。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-134">The host destroys the task by calling `ICLRTask::ExitTask`.</span></span>  
  
 <span data-ttu-id="dc6fa-135">`Reset` このシナリオは 2 つの方法を変更します。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-135">`Reset` alters this scenario in two ways.</span></span> <span data-ttu-id="dc6fa-136">5 は、ホストの呼び出し前の手順で`Reset`タスクをクリーンな状態にリセットしてを分離し、`ICLRTask`から関連付けられたインスタンス[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-136">In step 5 above, the host calls `Reset` to reset the task to a clean state, and then decouples the `ICLRTask` instance from its associated [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span> <span data-ttu-id="dc6fa-137">ホストをキャッシュできますも、必要な場合は、`IHostTask`インスタンスを再利用します。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-137">If desired, the host can also cache the `IHostTask` instance for reuse.</span></span> <span data-ttu-id="dc6fa-138">1 つ目の手順で、ランタイムは、リサイクル`ICLRTask`新しいインスタンスを作成する代わりにキャッシュからします。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-138">In step 1 above, the runtime pulls a recycled `ICLRTask` from the cache instead of creating a new instance.</span></span>  
  
 <span data-ttu-id="dc6fa-139">このアプローチは、ホストにも再利用可能なワーカー タスクのプールがある場合に機能します。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-139">This approach works well when the host also has a pool of reusable worker tasks.</span></span> <span data-ttu-id="dc6fa-140">ホストがのいずれかを破棄するときにその`IHostTask`インスタンス、破棄、対応する`ICLRTask`呼び出すことによって`ExitTask`。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-140">When the host destroys one of its `IHostTask` instances, it destroys the corresponding `ICLRTask` by calling `ExitTask`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc6fa-141">必要条件</span><span class="sxs-lookup"><span data-stu-id="dc6fa-141">Requirements</span></span>  
 <span data-ttu-id="dc6fa-142">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc6fa-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc6fa-143">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dc6fa-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dc6fa-144">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="dc6fa-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc6fa-145">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc6fa-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc6fa-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc6fa-146">See also</span></span>

- [<span data-ttu-id="dc6fa-147">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dc6fa-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="dc6fa-148">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dc6fa-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="dc6fa-149">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dc6fa-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="dc6fa-150">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dc6fa-150">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
