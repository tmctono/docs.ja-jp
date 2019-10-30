---
title: IHostTaskManager::GetCurrentTask メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: f17bca49-90bd-4dee-a5e1-b9a57ea46f85
topic_type:
- apiref
ms.openlocfilehash: d1d6ddfe7834a1c6f22b9195042d32363d6ea6cc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133043"
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="4d85e-102">IHostTaskManager::GetCurrentTask メソッド</span><span class="sxs-lookup"><span data-stu-id="4d85e-102">IHostTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="4d85e-103">この呼び出しが行われたオペレーティングシステムスレッドで現在実行されているタスクへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="4d85e-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d85e-104">構文</span><span class="sxs-lookup"><span data-stu-id="4d85e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d85e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4d85e-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="4d85e-106">入出力現在実行中のタスクを表す[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)インスタンスのアドレスへのポインター、またはタスクが現在実行されていない場合は null。</span><span class="sxs-lookup"><span data-stu-id="4d85e-106">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d85e-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="4d85e-107">Return Value</span></span>  
  
|<span data-ttu-id="4d85e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4d85e-108">HRESULT</span></span>|<span data-ttu-id="4d85e-109">説明</span><span class="sxs-lookup"><span data-stu-id="4d85e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4d85e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4d85e-110">S_OK</span></span>|<span data-ttu-id="4d85e-111">`GetCurrentTask` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="4d85e-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="4d85e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4d85e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4d85e-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="4d85e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4d85e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4d85e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4d85e-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="4d85e-115">The call timed out.</span></span>|  
|<span data-ttu-id="4d85e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4d85e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4d85e-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="4d85e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4d85e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4d85e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4d85e-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="4d85e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4d85e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4d85e-120">E_FAIL</span></span>|<span data-ttu-id="4d85e-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="4d85e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4d85e-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="4d85e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4d85e-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="4d85e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4d85e-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="4d85e-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="4d85e-125">ホストの制御外にあるオペレーティングシステムのスレッドで `GetCurrentTask` が呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="4d85e-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d85e-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="4d85e-126">Remarks</span></span>  
 <span data-ttu-id="4d85e-127">また、ホストは `pTask` パラメーターを null に設定して、開始されなかったタスクが CLR に入ってくるのを防ぐこともできます。</span><span class="sxs-lookup"><span data-stu-id="4d85e-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d85e-128">［要件］</span><span class="sxs-lookup"><span data-stu-id="4d85e-128">Requirements</span></span>  
 <span data-ttu-id="4d85e-129">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d85e-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d85e-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4d85e-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4d85e-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="4d85e-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4d85e-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d85e-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d85e-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d85e-133">See also</span></span>

- [<span data-ttu-id="4d85e-134">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4d85e-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="4d85e-135">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4d85e-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="4d85e-136">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4d85e-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="4d85e-137">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4d85e-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
