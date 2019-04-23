---
title: IHostGCManager::SuspensionStarting メソッド
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionStarting
helpviewer_keywords:
- SuspensionStarting method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionStarting method [.NET Framework hosting]
ms.assetid: c381f524-94cf-4fa2-9298-50f847a03431
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47ef5bb2539820d5a7bcd4ca6b4de86564290709
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213091"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="e5237-102">IHostGCManager::SuspensionStarting メソッド</span><span class="sxs-lookup"><span data-stu-id="e5237-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="e5237-103">共通言語ランタイム (CLR) がガベージ コレクションを実行するタスクの実行を中断していることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="e5237-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5237-104">構文</span><span class="sxs-lookup"><span data-stu-id="e5237-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e5237-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="e5237-105">Return Value</span></span>  
  
|<span data-ttu-id="e5237-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e5237-106">HRESULT</span></span>|<span data-ttu-id="e5237-107">説明</span><span class="sxs-lookup"><span data-stu-id="e5237-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e5237-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e5237-108">S_OK</span></span>|<span data-ttu-id="e5237-109">`SuspensionStarting` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="e5237-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="e5237-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e5237-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e5237-111">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="e5237-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e5237-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e5237-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e5237-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="e5237-113">The call timed out.</span></span>|  
|<span data-ttu-id="e5237-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e5237-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e5237-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="e5237-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e5237-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e5237-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e5237-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="e5237-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e5237-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e5237-118">E_FAIL</span></span>|<span data-ttu-id="e5237-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e5237-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e5237-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e5237-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e5237-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="e5237-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5237-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="e5237-122">Remarks</span></span>  
 <span data-ttu-id="e5237-123">CLR 呼び出し`SuspensionStarting`ガベージ コレクションが発生しているホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="e5237-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e5237-124">このタスクのスケジュールを変更できません。</span><span class="sxs-lookup"><span data-stu-id="e5237-124">Do not reschedule this task.</span></span> <span data-ttu-id="e5237-125">タスクのスケジュールを変更する必要があります、ホストと[ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e5237-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5237-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="e5237-126">Requirements</span></span>  
 <span data-ttu-id="e5237-127">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5237-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5237-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e5237-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e5237-129">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="e5237-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5237-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5237-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5237-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5237-131">See also</span></span>

- [<span data-ttu-id="e5237-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5237-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e5237-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5237-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e5237-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5237-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="e5237-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5237-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="e5237-136">IHostGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5237-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
