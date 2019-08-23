---
title: IHostSyncManager::CreateCrst メソッド
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrst
helpviewer_keywords:
- CreateCrst method [.NET Framework hosting]
- IHostSyncManager::CreateCrst method [.NET Framework hosting]
ms.assetid: ac278cc8-2540-4a6c-b5c6-b90c3970b4f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 622b6c523adfb7bae2fc38826152ef69709568cc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931073"
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="16a62-102">IHostSyncManager::CreateCrst メソッド</span><span class="sxs-lookup"><span data-stu-id="16a62-102">IHostSyncManager::CreateCrst Method</span></span>
<span data-ttu-id="16a62-103">同期のための重要なセクションオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="16a62-103">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16a62-104">構文</span><span class="sxs-lookup"><span data-stu-id="16a62-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16a62-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="16a62-105">Parameters</span></span>  
 `ppCrst`  
 <span data-ttu-id="16a62-106">入出力ホストによって実装されている[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)インスタンスのアドレスへのポインター。クリティカルセクションを作成できなかった場合は null。</span><span class="sxs-lookup"><span data-stu-id="16a62-106">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16a62-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="16a62-107">Return Value</span></span>  
  
|<span data-ttu-id="16a62-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="16a62-108">HRESULT</span></span>|<span data-ttu-id="16a62-109">説明</span><span class="sxs-lookup"><span data-stu-id="16a62-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="16a62-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="16a62-110">S_OK</span></span>|<span data-ttu-id="16a62-111">`CreateCrst`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="16a62-111">`CreateCrst` returned successfully.</span></span>|  
|<span data-ttu-id="16a62-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="16a62-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="16a62-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="16a62-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="16a62-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="16a62-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="16a62-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="16a62-115">The call timed out.</span></span>|  
|<span data-ttu-id="16a62-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="16a62-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="16a62-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="16a62-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="16a62-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="16a62-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="16a62-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="16a62-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="16a62-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="16a62-120">E_FAIL</span></span>|<span data-ttu-id="16a62-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="16a62-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="16a62-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="16a62-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="16a62-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="16a62-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="16a62-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="16a62-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="16a62-125">要求されたクリティカルセクションを作成するのに十分なメモリがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="16a62-125">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16a62-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="16a62-126">Remarks</span></span>  
 <span data-ttu-id="16a62-127">クリティカルセクションオブジェクトは、1つのプロセスのスレッドのみが使用できるクリティカルセクションを除き、ミューテックスオブジェクトで提供されるものと同様の同期を提供します。</span><span class="sxs-lookup"><span data-stu-id="16a62-127">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> <span data-ttu-id="16a62-128">`CreateCrst`Win32 `InitializeCriticalSection`関数をミラー化します。</span><span class="sxs-lookup"><span data-stu-id="16a62-128">`CreateCrst` mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16a62-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="16a62-129">Requirements</span></span>  
 <span data-ttu-id="16a62-130">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="16a62-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16a62-131">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="16a62-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="16a62-132">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="16a62-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16a62-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16a62-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16a62-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="16a62-134">See also</span></span>

- [<span data-ttu-id="16a62-135">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16a62-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="16a62-136">IHostCrst インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16a62-136">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="16a62-137">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16a62-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="16a62-138">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16a62-138">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="16a62-139">ミューテックス</span><span class="sxs-lookup"><span data-stu-id="16a62-139">Mutexes</span></span>](../../../standard/threading/mutexes.md)
- [<span data-ttu-id="16a62-140">Semaphore と SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="16a62-140">Semaphore and SemaphoreSlim</span></span>](../../../standard/threading/semaphore-and-semaphoreslim.md)
