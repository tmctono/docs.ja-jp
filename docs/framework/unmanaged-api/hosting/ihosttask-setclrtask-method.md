---
title: IHostTask::SetCLRTask メソッド
ms.date: 03/30/2017
api_name:
- IHostTask.SetCLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetCLRTask
helpviewer_keywords:
- SetCLRTask method [.NET Framework hosting]
- IHostTask::SetCLRTask method [.NET Framework hosting]
ms.assetid: e9d39c80-41a1-49e7-bb5e-ea3433bfb5d7
topic_type:
- apiref
ms.openlocfilehash: bbb563a304e3ff7cdba3dfe7e394da9cf138ff10
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121371"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="7557c-102">IHostTask::SetCLRTask メソッド</span><span class="sxs-lookup"><span data-stu-id="7557c-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="7557c-103">`ICLRTask` インスタンスを現在の[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)インスタンスに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="7557c-103">Associates an `ICLRTask` instance with the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7557c-104">構文</span><span class="sxs-lookup"><span data-stu-id="7557c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7557c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7557c-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="7557c-106">から現在の `IHostTask` インスタンスに関連付けられる `ICLRTask` インスタンスへのインターフェイスポインター。</span><span class="sxs-lookup"><span data-stu-id="7557c-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7557c-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="7557c-107">Return Value</span></span>  
  
|<span data-ttu-id="7557c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7557c-108">HRESULT</span></span>|<span data-ttu-id="7557c-109">説明</span><span class="sxs-lookup"><span data-stu-id="7557c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7557c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7557c-110">S_OK</span></span>|<span data-ttu-id="7557c-111">`SetCLRTask` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="7557c-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="7557c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7557c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7557c-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="7557c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7557c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7557c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7557c-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="7557c-115">The call timed out.</span></span>|  
|<span data-ttu-id="7557c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7557c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7557c-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="7557c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7557c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7557c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7557c-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="7557c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7557c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7557c-120">E_FAIL</span></span>|<span data-ttu-id="7557c-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7557c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7557c-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="7557c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7557c-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="7557c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7557c-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="7557c-124">Remarks</span></span>  
 <span data-ttu-id="7557c-125">CLR は `SetCLRTask` を呼び出して、`ICLRTask` インスタンスを現在の `IHostTask` インスタンスに関連付けます。これは、 [IHostTaskManager:: CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)の呼び出しによって作成されたものです。</span><span class="sxs-lookup"><span data-stu-id="7557c-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7557c-126">［要件］</span><span class="sxs-lookup"><span data-stu-id="7557c-126">Requirements</span></span>  
 <span data-ttu-id="7557c-127">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7557c-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7557c-128">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7557c-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7557c-129">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="7557c-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7557c-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7557c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7557c-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="7557c-131">See also</span></span>

- [<span data-ttu-id="7557c-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7557c-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="7557c-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7557c-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="7557c-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7557c-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="7557c-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7557c-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
