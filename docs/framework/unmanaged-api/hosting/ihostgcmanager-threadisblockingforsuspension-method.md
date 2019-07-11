---
title: IHostGCManager::ThreadIsBlockingForSuspension メソッド
ms.date: 03/30/2017
api_name:
- IHostGCManager.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension
helpviewer_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: 2657d45d-26d2-4d0a-8473-32b652e3321d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0c59d9f5abb200b17d3c46915e73fd3b9e9c8fd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780578"
---
# <a name="ihostgcmanagerthreadisblockingforsuspension-method"></a><span data-ttu-id="84240-102">IHostGCManager::ThreadIsBlockingForSuspension メソッド</span><span class="sxs-lookup"><span data-stu-id="84240-102">IHostGCManager::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="84240-103">メソッドの呼び出し元のスレッドは、ホストに通知のガベージ コレクションをブロックします。</span><span class="sxs-lookup"><span data-stu-id="84240-103">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84240-104">構文</span><span class="sxs-lookup"><span data-stu-id="84240-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="84240-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="84240-105">Return Value</span></span>  
  
|<span data-ttu-id="84240-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="84240-106">HRESULT</span></span>|<span data-ttu-id="84240-107">説明</span><span class="sxs-lookup"><span data-stu-id="84240-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="84240-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="84240-108">S_OK</span></span>|<span data-ttu-id="84240-109">`ThreadIsBlockingForSuspension` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="84240-109">`ThreadIsBlockingForSuspension` returned successfully.</span></span>|  
|<span data-ttu-id="84240-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="84240-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="84240-111">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="84240-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="84240-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="84240-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="84240-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="84240-113">The call timed out.</span></span>|  
|<span data-ttu-id="84240-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="84240-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="84240-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="84240-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="84240-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="84240-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="84240-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="84240-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="84240-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="84240-118">E_FAIL</span></span>|<span data-ttu-id="84240-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="84240-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="84240-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="84240-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="84240-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="84240-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84240-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="84240-122">Remarks</span></span>  
 <span data-ttu-id="84240-123">CLR は通常、呼び出し、`ThreadIsBlockForSuspension`準備として、ホストの管理されていないタスクのスレッドを再スケジュールする機会を提供する、ガベージ コレクションのメソッド。</span><span class="sxs-lookup"><span data-stu-id="84240-123">The CLR typically calls the `ThreadIsBlockForSuspension` method in preparation for a garbage collection, to give the host an opportunity to reschedule the thread for unmanaged tasks.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="84240-124">ホストは、タスクを再スケジュールへの呼び出し後にのみ`ThreadIsBlockingForSuspension`します。</span><span class="sxs-lookup"><span data-stu-id="84240-124">The host can reschedule tasks only after a call to `ThreadIsBlockingForSuspension`.</span></span> <span data-ttu-id="84240-125">ランタイム呼び出し後[SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)ホストのタスクを再スケジュールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="84240-125">After the runtime calls [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md), the host must not reschedule a task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84240-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="84240-126">Requirements</span></span>  
 <span data-ttu-id="84240-127">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="84240-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84240-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="84240-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84240-129">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="84240-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84240-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84240-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84240-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="84240-131">See also</span></span>

- [<span data-ttu-id="84240-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="84240-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="84240-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="84240-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="84240-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="84240-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="84240-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="84240-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="84240-136">IHostGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="84240-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
