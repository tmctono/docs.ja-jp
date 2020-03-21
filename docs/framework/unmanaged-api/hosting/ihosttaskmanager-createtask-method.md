---
title: IHostTaskManager::CreateTask メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CreateTask
helpviewer_keywords:
- CreateTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::CreateTask method [.NET Framework hosting]
ms.assetid: a6f8ad36-61e1-42b0-9db2-add575646d18
topic_type:
- apiref
ms.openlocfilehash: fef2f56fd000a8610a40661a30aa306ae5a7884e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177997"
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="34481-102">IHostTaskManager::CreateTask メソッド</span><span class="sxs-lookup"><span data-stu-id="34481-102">IHostTaskManager::CreateTask Method</span></span>
<span data-ttu-id="34481-103">ホストに新しいタスクの作成を要求します。</span><span class="sxs-lookup"><span data-stu-id="34481-103">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34481-104">構文</span><span class="sxs-lookup"><span data-stu-id="34481-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [in]  DWORD stacksize,
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34481-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="34481-105">Parameters</span></span>  
 `stacksize`  
 <span data-ttu-id="34481-106">[in]要求されたスタックの要求されたサイズ (バイト単位) またはデフォルト サイズの 0 (ゼロ)。</span><span class="sxs-lookup"><span data-stu-id="34481-106">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="34481-107">[in]タスクが実行する関数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="34481-107">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="34481-108">[in]関数に渡されるユーザー データへのポインター。</span><span class="sxs-lookup"><span data-stu-id="34481-108">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="34481-109">[アウト]ホストによって作成された[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)インスタンスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="34481-109">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="34481-110">タスクは[、IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)の呼び出しによって明示的に開始されるまで中断状態のままになります。</span><span class="sxs-lookup"><span data-stu-id="34481-110">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34481-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="34481-111">Return Value</span></span>  
  
|<span data-ttu-id="34481-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="34481-112">HRESULT</span></span>|<span data-ttu-id="34481-113">説明</span><span class="sxs-lookup"><span data-stu-id="34481-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="34481-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="34481-114">S_OK</span></span>|<span data-ttu-id="34481-115">`CreateTask`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="34481-115">`CreateTask` returned successfully.</span></span>|  
|<span data-ttu-id="34481-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="34481-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="34481-117">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージ コードを実行できない状態または呼び出しを正常に処理できない状態にあります。</span><span class="sxs-lookup"><span data-stu-id="34481-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="34481-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="34481-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="34481-119">通話がタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="34481-119">The call timed out.</span></span>|  
|<span data-ttu-id="34481-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="34481-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="34481-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="34481-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="34481-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="34481-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="34481-123">ブロックされたスレッドまたはファイバが待機しているときにイベントがキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="34481-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="34481-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="34481-124">E_FAIL</span></span>|<span data-ttu-id="34481-125">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="34481-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="34481-126">メソッドがE_FAILを返すと、CLR はプロセス内で使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="34481-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="34481-127">ホスト メソッドへの後続の呼び出しは、HOST_E_CLRNOTAVAILABLEを返します。</span><span class="sxs-lookup"><span data-stu-id="34481-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="34481-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="34481-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="34481-129">メモリ不足で、要求されたタスクを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="34481-129">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34481-130">解説</span><span class="sxs-lookup"><span data-stu-id="34481-130">Remarks</span></span>  
 <span data-ttu-id="34481-131">ホストが新`CreateTask`しいタスクを作成することを要求する CLR 呼び出し。</span><span class="sxs-lookup"><span data-stu-id="34481-131">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="34481-132">ホストは、インスタンスへのインターフェイス ポインター`IHostTask`を返します。</span><span class="sxs-lookup"><span data-stu-id="34481-132">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="34481-133">返されたタスクは、 への呼び出しによって明示的に開始されるまで`IHostTask::Start`中断されたままにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="34481-133">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34481-134">必要条件</span><span class="sxs-lookup"><span data-stu-id="34481-134">Requirements</span></span>  
 <span data-ttu-id="34481-135">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34481-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34481-136">**ヘッダー:** msCorEE.h</span><span class="sxs-lookup"><span data-stu-id="34481-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="34481-137">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="34481-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="34481-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34481-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34481-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="34481-139">See also</span></span>

- [<span data-ttu-id="34481-140">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34481-140">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="34481-141">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34481-141">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="34481-142">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34481-142">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="34481-143">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34481-143">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
