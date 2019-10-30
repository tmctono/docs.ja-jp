---
title: ICLRTask::NeedsPriorityScheduling メソッド
ms.date: 03/30/2017
api_name:
- ICLRTask.NeedsPriorityScheduling
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::NeedsPriorityScheduling
helpviewer_keywords:
- ICLRTask::NeedsPriorityScheduling method [.NET Framework hosting]
- NeedsPriorityScheduling method [.NET Framework hosting]
ms.assetid: 9c9db3f3-26bf-4317-88de-5eb926a22a1d
topic_type:
- apiref
ms.openlocfilehash: 91c1ea51969447861ff6d0956c5714baa0054450
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124666"
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="3b469-102">ICLRTask::NeedsPriorityScheduling メソッド</span><span class="sxs-lookup"><span data-stu-id="3b469-102">ICLRTask::NeedsPriorityScheduling Method</span></span>
<span data-ttu-id="3b469-103">現在のタスクが、切り替え先としてマークされている必要があるかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="3b469-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b469-104">構文</span><span class="sxs-lookup"><span data-stu-id="3b469-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b469-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3b469-105">Parameters</span></span>  
 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="3b469-106">[out] ホストが現在のタスクインスタンスの再スケジュールをできるだけ早く試行する必要がある場合は `true`。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="3b469-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b469-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="3b469-107">Return Value</span></span>  
  
|<span data-ttu-id="3b469-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3b469-108">HRESULT</span></span>|<span data-ttu-id="3b469-109">説明</span><span class="sxs-lookup"><span data-stu-id="3b469-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3b469-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3b469-110">S_OK</span></span>|<span data-ttu-id="3b469-111">`NeedsPriorityRescheduling` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="3b469-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="3b469-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3b469-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3b469-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="3b469-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3b469-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3b469-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3b469-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="3b469-115">The call timed out.</span></span>|  
|<span data-ttu-id="3b469-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3b469-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3b469-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="3b469-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3b469-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3b469-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3b469-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="3b469-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3b469-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3b469-120">E_FAIL</span></span>|<span data-ttu-id="3b469-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3b469-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3b469-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="3b469-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3b469-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="3b469-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b469-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="3b469-124">Remarks</span></span>  
 <span data-ttu-id="3b469-125">ガベージコレクターによってタスクが収集されるのが近い場合は、CLR によって `pbNeedsPriorityScheduling` の値が `true`に設定され、優先度の高い再スケジュールが示されます。</span><span class="sxs-lookup"><span data-stu-id="3b469-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="3b469-126">これにより、ホストはタスクを迅速に再スケジュールすることができます。これにより、ガベージコレクションの遅延の可能性が最小限に抑えられ、ホストとランタイムがメモリリソースを節約できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3b469-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b469-127">［要件］</span><span class="sxs-lookup"><span data-stu-id="3b469-127">Requirements</span></span>  
 <span data-ttu-id="3b469-128">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b469-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b469-129">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3b469-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3b469-130">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="3b469-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b469-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b469-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b469-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b469-132">See also</span></span>

- [<span data-ttu-id="3b469-133">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b469-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="3b469-134">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b469-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="3b469-135">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b469-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="3b469-136">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b469-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
