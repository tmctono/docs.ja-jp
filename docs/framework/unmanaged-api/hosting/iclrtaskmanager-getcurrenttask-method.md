---
title: ICLRTaskManager::GetCurrentTask メソッド
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: c0b82a9f-edc6-4878-9c81-48de53c02142
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9996b1a84a5f095cf12d74d0c6f594911e7a7788
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770198"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="77256-102">ICLRTaskManager::GetCurrentTask メソッド</span><span class="sxs-lookup"><span data-stu-id="77256-102">ICLRTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="77256-103">取得、 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)メソッドの呼び出しが元のオペレーティング システム スレッドで現在実行中のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="77256-103">Gets the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77256-104">構文</span><span class="sxs-lookup"><span data-stu-id="77256-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77256-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="77256-105">Parameters</span></span>  
 `ppTask`  
 <span data-ttu-id="77256-106">[out]アドレスへのポインター、`ICLRTask`呼び出しを起点となるオペレーティング システム スレッドで現在実行しているインスタンスまたはこのスレッドで現在実行しているタスクがなくなる場合は null です。</span><span class="sxs-lookup"><span data-stu-id="77256-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77256-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="77256-107">Return Value</span></span>  
  
|<span data-ttu-id="77256-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="77256-108">HRESULT</span></span>|<span data-ttu-id="77256-109">説明</span><span class="sxs-lookup"><span data-stu-id="77256-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="77256-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="77256-110">S_OK</span></span>|<span data-ttu-id="77256-111">メソッドが正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="77256-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="77256-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="77256-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="77256-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="77256-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="77256-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="77256-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="77256-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="77256-115">The call timed out.</span></span>|  
|<span data-ttu-id="77256-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="77256-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="77256-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="77256-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="77256-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="77256-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="77256-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="77256-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="77256-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="77256-120">E_FAIL</span></span>|<span data-ttu-id="77256-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="77256-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="77256-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="77256-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="77256-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="77256-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77256-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="77256-124">Remarks</span></span>  
 <span data-ttu-id="77256-125">`ICLRTask`インスタンスが、`ppTask`パラメーターが指すは、現在実行中のタスク、CLR の。</span><span class="sxs-lookup"><span data-stu-id="77256-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="77256-126">`ICLRTask`インスタンスは、対応する関連付け[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)ホストのタスクを表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="77256-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77256-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="77256-127">Requirements</span></span>  
 <span data-ttu-id="77256-128">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77256-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77256-129">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="77256-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="77256-130">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="77256-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77256-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77256-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77256-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="77256-132">See also</span></span>

- [<span data-ttu-id="77256-133">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="77256-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="77256-134">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="77256-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="77256-135">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="77256-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="77256-136">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="77256-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
