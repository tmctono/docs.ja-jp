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
ms.openlocfilehash: 86bc320c28a5fbf122d234a4a1f15b674628c0b5
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803395"
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="ea1c6-102">IHostSyncManager::CreateCrstWithSpinCount メソッド</span><span class="sxs-lookup"><span data-stu-id="ea1c6-102">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>
<span data-ttu-id="ea1c6-103">同期のためにスピンカウントを持つクリティカルセクションオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ea1c6-103">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea1c6-104">構文</span><span class="sxs-lookup"><span data-stu-id="ea1c6-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea1c6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea1c6-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="ea1c6-106">からクリティカルセクションオブジェクトのスピンカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea1c6-106">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="ea1c6-107">入出力[IHostCrst](ihostcrst-interface.md)インスタンスのアドレスへのポインター。クリティカルセクションを作成できなかった場合は null。</span><span class="sxs-lookup"><span data-stu-id="ea1c6-107">[out] A pointer to the address of an [IHostCrst](ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ea1c6-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="ea1c6-108">Return Value</span></span>  
  
|<span data-ttu-id="ea1c6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ea1c6-109">HRESULT</span></span>|<span data-ttu-id="ea1c6-110">説明</span><span class="sxs-lookup"><span data-stu-id="ea1c6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ea1c6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ea1c6-111">S_OK</span></span>|<span data-ttu-id="ea1c6-112">`CreateCrstWithSpinCount`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="ea1c6-112">`CreateCrstWithSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="ea1c6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ea1c6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ea1c6-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="ea1c6-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ea1c6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ea1c6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ea1c6-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="ea1c6-116">The call timed out.</span></span>|  
|<span data-ttu-id="ea1c6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ea1c6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ea1c6-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="ea1c6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ea1c6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ea1c6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ea1c6-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="ea1c6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ea1c6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ea1c6-121">E_FAIL</span></span>|<span data-ttu-id="ea1c6-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="ea1c6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ea1c6-123">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ea1c6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ea1c6-124">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="ea1c6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ea1c6-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ea1c6-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ea1c6-126">要求されたクリティカルセクションを作成するのに十分なメモリがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="ea1c6-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea1c6-127">解説</span><span class="sxs-lookup"><span data-stu-id="ea1c6-127">Remarks</span></span>  
 <span data-ttu-id="ea1c6-128">スピンカウントは、マルチプロセッサシステムでのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="ea1c6-128">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="ea1c6-129">スピンカウントは、使用できないクリティカルセクションに関連付けられているセマフォで待機操作を実行する前に、呼び出し元のスレッドがスピンする必要がある回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea1c6-129">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="ea1c6-130">スピン操作中にクリティカルセクションが解放されると、呼び出し元のスレッドは待機操作を回避します。</span><span class="sxs-lookup"><span data-stu-id="ea1c6-130">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> <span data-ttu-id="ea1c6-131">`CreateCrstWithSpinCount`Win32 関数をミラー化 `InitializeCriticalSectionAndSpinCount` します。</span><span class="sxs-lookup"><span data-stu-id="ea1c6-131">`CreateCrstWithSpinCount` mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea1c6-132">要件</span><span class="sxs-lookup"><span data-stu-id="ea1c6-132">Requirements</span></span>  
 <span data-ttu-id="ea1c6-133">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea1c6-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea1c6-134">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ea1c6-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ea1c6-135">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="ea1c6-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ea1c6-136">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea1c6-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea1c6-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea1c6-137">See also</span></span>

- [<span data-ttu-id="ea1c6-138">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea1c6-138">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="ea1c6-139">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea1c6-139">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="ea1c6-140">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea1c6-140">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
