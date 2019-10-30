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
ms.openlocfilehash: 632b8d43ed459d489825dc796d39864e2ed15ec3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139417"
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="9e52a-102">IHostSyncManager::CreateCrstWithSpinCount メソッド</span><span class="sxs-lookup"><span data-stu-id="9e52a-102">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>
<span data-ttu-id="9e52a-103">同期のためにスピンカウントを持つクリティカルセクションオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="9e52a-103">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e52a-104">構文</span><span class="sxs-lookup"><span data-stu-id="9e52a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e52a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9e52a-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="9e52a-106">からクリティカルセクションオブジェクトのスピンカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e52a-106">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="9e52a-107">入出力[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)インスタンスのアドレスへのポインター。クリティカルセクションを作成できなかった場合は null。</span><span class="sxs-lookup"><span data-stu-id="9e52a-107">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e52a-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="9e52a-108">Return Value</span></span>  
  
|<span data-ttu-id="9e52a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9e52a-109">HRESULT</span></span>|<span data-ttu-id="9e52a-110">説明</span><span class="sxs-lookup"><span data-stu-id="9e52a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9e52a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9e52a-111">S_OK</span></span>|<span data-ttu-id="9e52a-112">`CreateCrstWithSpinCount` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="9e52a-112">`CreateCrstWithSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="9e52a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9e52a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9e52a-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="9e52a-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9e52a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9e52a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9e52a-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="9e52a-116">The call timed out.</span></span>|  
|<span data-ttu-id="9e52a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9e52a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9e52a-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="9e52a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9e52a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9e52a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9e52a-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="9e52a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9e52a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9e52a-121">E_FAIL</span></span>|<span data-ttu-id="9e52a-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="9e52a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9e52a-123">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="9e52a-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9e52a-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="9e52a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9e52a-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9e52a-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="9e52a-126">要求されたクリティカルセクションを作成するのに十分なメモリがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="9e52a-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e52a-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e52a-127">Remarks</span></span>  
 <span data-ttu-id="9e52a-128">スピンカウントは、マルチプロセッサシステムでのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="9e52a-128">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="9e52a-129">スピンカウントは、使用できないクリティカルセクションに関連付けられているセマフォで待機操作を実行する前に、呼び出し元のスレッドがスピンする必要がある回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9e52a-129">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="9e52a-130">スピン操作中にクリティカルセクションが解放されると、呼び出し元のスレッドは待機操作を回避します。</span><span class="sxs-lookup"><span data-stu-id="9e52a-130">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> <span data-ttu-id="9e52a-131">`CreateCrstWithSpinCount` Win32 `InitializeCriticalSectionAndSpinCount` 関数をミラー化します。</span><span class="sxs-lookup"><span data-stu-id="9e52a-131">`CreateCrstWithSpinCount` mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e52a-132">［要件］</span><span class="sxs-lookup"><span data-stu-id="9e52a-132">Requirements</span></span>  
 <span data-ttu-id="9e52a-133">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e52a-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e52a-134">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9e52a-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9e52a-135">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="9e52a-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e52a-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e52a-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e52a-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e52a-137">See also</span></span>

- [<span data-ttu-id="9e52a-138">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e52a-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="9e52a-139">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e52a-139">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="9e52a-140">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e52a-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
