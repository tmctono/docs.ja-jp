---
title: IHostSyncManager::CreateCrstWithSpinCount メソッド
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrstWithSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrstWithSpinCount
helpviewer_keywords:
- CreateCrstWithSpinCount method [.NET Framework hosting]
- IHostSyncManager::CreateCrstWithSpinCount method [.NET Framework hosting]
ms.assetid: 7280fa8c-3639-4abf-91cb-bc343da742d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c4dd73efbad5ffac47c8585facd1717d77147fa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501586"
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="9a27c-102">IHostSyncManager::CreateCrstWithSpinCount メソッド</span><span class="sxs-lookup"><span data-stu-id="9a27c-102">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>
<span data-ttu-id="9a27c-103">同期のためのスピン カウントとクリティカル セクション オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="9a27c-103">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a27c-104">構文</span><span class="sxs-lookup"><span data-stu-id="9a27c-104">Syntax</span></span>  
  
```  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a27c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9a27c-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="9a27c-106">[in]クリティカル セクション オブジェクトのスピン カウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="9a27c-106">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="9a27c-107">[out]アドレスへのポインター、 [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)インスタンス、または、クリティカル セクションを作成できなかった場合は null です。</span><span class="sxs-lookup"><span data-stu-id="9a27c-107">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a27c-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="9a27c-108">Return Value</span></span>  
  
|<span data-ttu-id="9a27c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9a27c-109">HRESULT</span></span>|<span data-ttu-id="9a27c-110">説明</span><span class="sxs-lookup"><span data-stu-id="9a27c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9a27c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a27c-111">S_OK</span></span>|<span data-ttu-id="9a27c-112">`CreateCrstWithSpinCount` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="9a27c-112">`CreateCrstWithSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="9a27c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9a27c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9a27c-114">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="9a27c-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9a27c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9a27c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9a27c-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="9a27c-116">The call timed out.</span></span>|  
|<span data-ttu-id="9a27c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9a27c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9a27c-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="9a27c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9a27c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9a27c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9a27c-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="9a27c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9a27c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9a27c-121">E_FAIL</span></span>|<span data-ttu-id="9a27c-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="9a27c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9a27c-123">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="9a27c-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9a27c-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="9a27c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9a27c-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9a27c-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="9a27c-126">メモリ不足は、要求のクリティカル セクションを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="9a27c-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a27c-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="9a27c-127">Remarks</span></span>  
 <span data-ttu-id="9a27c-128">スピン カウントは、マルチプロセッサ システムでのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="9a27c-128">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="9a27c-129">スピン カウントには、呼び出し元のスレッドが利用不可のクリティカル セクションに関連付けられているセマフォの待機操作を実行する前に回転する必要があります回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9a27c-129">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="9a27c-130">クリティカル セクションは、スピン操作中に無料になると、呼び出し元のスレッドは待機操作を回避できます。</span><span class="sxs-lookup"><span data-stu-id="9a27c-130">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> <span data-ttu-id="9a27c-131">`CreateCrstWithSpinCount` Win32 をミラー化`InitializeCriticalSectionAndSpinCount`関数。</span><span class="sxs-lookup"><span data-stu-id="9a27c-131">`CreateCrstWithSpinCount` mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a27c-132">必要条件</span><span class="sxs-lookup"><span data-stu-id="9a27c-132">Requirements</span></span>  
 <span data-ttu-id="9a27c-133">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a27c-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a27c-134">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9a27c-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9a27c-135">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="9a27c-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a27c-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a27c-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a27c-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a27c-137">See also</span></span>
- [<span data-ttu-id="9a27c-138">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a27c-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="9a27c-139">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a27c-139">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="9a27c-140">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a27c-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
