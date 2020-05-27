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
ms.openlocfilehash: 3566907544c72da2735e155d9088fe09fea4a728
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803478"
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="da611-102">IHostSyncManager::CreateCrst メソッド</span><span class="sxs-lookup"><span data-stu-id="da611-102">IHostSyncManager::CreateCrst Method</span></span>
<span data-ttu-id="da611-103">同期のための重要なセクションオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="da611-103">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da611-104">構文</span><span class="sxs-lookup"><span data-stu-id="da611-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da611-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="da611-105">Parameters</span></span>  
 `ppCrst`  
 <span data-ttu-id="da611-106">入出力ホストによって実装されている[IHostCrst](ihostcrst-interface.md)インスタンスのアドレスへのポインター。クリティカルセクションを作成できなかった場合は null。</span><span class="sxs-lookup"><span data-stu-id="da611-106">[out] A pointer to the address of an [IHostCrst](ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da611-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="da611-107">Return Value</span></span>  
  
|<span data-ttu-id="da611-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="da611-108">HRESULT</span></span>|<span data-ttu-id="da611-109">説明</span><span class="sxs-lookup"><span data-stu-id="da611-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="da611-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="da611-110">S_OK</span></span>|<span data-ttu-id="da611-111">`CreateCrst`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="da611-111">`CreateCrst` returned successfully.</span></span>|  
|<span data-ttu-id="da611-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="da611-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="da611-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="da611-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="da611-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="da611-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="da611-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="da611-115">The call timed out.</span></span>|  
|<span data-ttu-id="da611-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="da611-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="da611-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="da611-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="da611-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="da611-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="da611-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="da611-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="da611-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="da611-120">E_FAIL</span></span>|<span data-ttu-id="da611-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="da611-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="da611-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="da611-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="da611-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="da611-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="da611-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="da611-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="da611-125">要求されたクリティカルセクションを作成するのに十分なメモリがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="da611-125">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da611-126">解説</span><span class="sxs-lookup"><span data-stu-id="da611-126">Remarks</span></span>  
 <span data-ttu-id="da611-127">クリティカルセクションオブジェクトは、1つのプロセスのスレッドのみが使用できるクリティカルセクションを除き、ミューテックスオブジェクトで提供されるものと同様の同期を提供します。</span><span class="sxs-lookup"><span data-stu-id="da611-127">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> <span data-ttu-id="da611-128">`CreateCrst`Win32 関数をミラー化 `InitializeCriticalSection` します。</span><span class="sxs-lookup"><span data-stu-id="da611-128">`CreateCrst` mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da611-129">要件</span><span class="sxs-lookup"><span data-stu-id="da611-129">Requirements</span></span>  
 <span data-ttu-id="da611-130">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da611-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da611-131">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="da611-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="da611-132">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="da611-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da611-133">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da611-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da611-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="da611-134">See also</span></span>

- [<span data-ttu-id="da611-135">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da611-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="da611-136">IHostCrst インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da611-136">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="da611-137">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da611-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="da611-138">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="da611-138">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="da611-139">ミューテックス</span><span class="sxs-lookup"><span data-stu-id="da611-139">Mutexes</span></span>](../../../standard/threading/mutexes.md)
- [<span data-ttu-id="da611-140">Semaphore と SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="da611-140">Semaphore and SemaphoreSlim</span></span>](../../../standard/threading/semaphore-and-semaphoreslim.md)
