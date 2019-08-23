---
title: IHostTask::SetPriority メソッド
ms.date: 03/30/2017
api_name:
- IHostTask.SetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetPriority
helpviewer_keywords:
- IHostTask::SetPriority method [.NET Framework hosting]
- SetPriority method [.NET Framework hosting]
ms.assetid: cd8c379b-c7a0-434f-8e23-899bd26be75d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 533e3d715b46b4ef6d473795a010fa3ad297ded2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913752"
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="8ac13-102">IHostTask::SetPriority メソッド</span><span class="sxs-lookup"><span data-stu-id="8ac13-102">IHostTask::SetPriority Method</span></span>
<span data-ttu-id="8ac13-103">現在の[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)インスタンスによって表されるタスクのスレッドの優先度レベルをホストが調整するように要求します。</span><span class="sxs-lookup"><span data-stu-id="8ac13-103">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ac13-104">構文</span><span class="sxs-lookup"><span data-stu-id="8ac13-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ac13-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8ac13-105">Parameters</span></span>  
 `newPriority`  
 <span data-ttu-id="8ac13-106">から現在`IHostTask`のインスタンスによって表されるタスクについて、要求されたスレッドの優先順位値を表す整数。</span><span class="sxs-lookup"><span data-stu-id="8ac13-106">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ac13-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="8ac13-107">Return Value</span></span>  
  
|<span data-ttu-id="8ac13-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8ac13-108">HRESULT</span></span>|<span data-ttu-id="8ac13-109">説明</span><span class="sxs-lookup"><span data-stu-id="8ac13-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8ac13-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8ac13-110">S_OK</span></span>|<span data-ttu-id="8ac13-111">`SetPriority`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="8ac13-111">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="8ac13-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8ac13-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8ac13-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="8ac13-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8ac13-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8ac13-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8ac13-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="8ac13-115">The call timed out.</span></span>|  
|<span data-ttu-id="8ac13-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8ac13-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8ac13-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="8ac13-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8ac13-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8ac13-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8ac13-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="8ac13-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8ac13-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8ac13-120">E_FAIL</span></span>|<span data-ttu-id="8ac13-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="8ac13-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8ac13-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="8ac13-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8ac13-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="8ac13-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ac13-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="8ac13-124">Remarks</span></span>  
 <span data-ttu-id="8ac13-125">スレッドには、スレッドの優先度レベルに基づいたラウンドロビンシステムを使用した処理時間が与えられます。</span><span class="sxs-lookup"><span data-stu-id="8ac13-125">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="8ac13-126">`SetPriority`CLR が現在のタスクに対して、そのスレッドの優先度レベルを設定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8ac13-126">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="8ac13-127">次`newPriority`の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8ac13-127">The following `newPriority` values are supported.</span></span>  
  
- <span data-ttu-id="8ac13-128">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="8ac13-128">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
- <span data-ttu-id="8ac13-129">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="8ac13-129">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
- <span data-ttu-id="8ac13-130">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="8ac13-130">THREAD_PRIORITY_HIGHEST</span></span>  
  
- <span data-ttu-id="8ac13-131">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="8ac13-131">THREAD_PRIORITY_IDLE</span></span>  
  
- <span data-ttu-id="8ac13-132">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="8ac13-132">THREAD_PRIORITY_LOWEST</span></span>  
  
- <span data-ttu-id="8ac13-133">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="8ac13-133">THREAD_PRIORITY_NORMAL</span></span>  
  
- <span data-ttu-id="8ac13-134">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="8ac13-134">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="8ac13-135">CLR は、 `SetPriority` <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType>の値がユーザーコードによって変更されたときにを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8ac13-135">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="8ac13-136">ホストは、スレッドの優先度割り当てに対して独自のアルゴリズムを定義でき、この要求を無視することができます。</span><span class="sxs-lookup"><span data-stu-id="8ac13-136">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8ac13-137">`SetPriority`では、スレッドの優先度レベルが変更されたかどうかは報告されません。</span><span class="sxs-lookup"><span data-stu-id="8ac13-137">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="8ac13-138">[IHostTask:: GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)を呼び出して、タスクのスレッド優先度レベルの値を決定します。</span><span class="sxs-lookup"><span data-stu-id="8ac13-138">Call [IHostTask::GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="8ac13-139">スレッドの優先度レベルの値は、 `SetThreadPriority` Win32 関数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="8ac13-139">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="8ac13-140">スレッドの優先順位の詳細については、Windows プラットフォームのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ac13-140">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ac13-141">必要条件</span><span class="sxs-lookup"><span data-stu-id="8ac13-141">Requirements</span></span>  
 <span data-ttu-id="8ac13-142">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ac13-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ac13-143">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8ac13-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ac13-144">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="8ac13-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ac13-145">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ac13-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ac13-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ac13-146">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="8ac13-147">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8ac13-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="8ac13-148">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8ac13-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8ac13-149">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8ac13-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="8ac13-150">GetPriority メソッド</span><span class="sxs-lookup"><span data-stu-id="8ac13-150">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)
- [<span data-ttu-id="8ac13-151">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8ac13-151">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
