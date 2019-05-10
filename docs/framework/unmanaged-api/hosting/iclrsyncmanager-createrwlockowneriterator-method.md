---
title: ICLRSyncManager::CreateRWLockOwnerIterator メソッド
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.CreateRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator method [.NET Framework hosting]
- CreateRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: b5535b87-9439-424e-b9b3-7d6fafb9819e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 450530baed850a66327c4b1326c399529b3de67d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630591"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a><span data-ttu-id="efce8-102">ICLRSyncManager::CreateRWLockOwnerIterator メソッド</span><span class="sxs-lookup"><span data-stu-id="efce8-102">ICLRSyncManager::CreateRWLockOwnerIterator Method</span></span>
<span data-ttu-id="efce8-103">共通言語ランタイム (CLR) を使用して、リーダー/ライター ロックで待機しているタスクのセットを決定するホストの反復子を作成するように要求します。</span><span class="sxs-lookup"><span data-stu-id="efce8-103">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efce8-104">構文</span><span class="sxs-lookup"><span data-stu-id="efce8-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efce8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="efce8-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="efce8-106">[in]目的のリーダー/ライター ロックに関連付けられているクッキー。</span><span class="sxs-lookup"><span data-stu-id="efce8-106">[in] The cookie associated with the desired reader-writer lock.</span></span>  
  
 `pIterator`  
 <span data-ttu-id="efce8-107">[out]渡すことができる反復子へのポインター、 [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md)と[DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="efce8-107">[out] A pointer to an iterator that can be passed to the [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) and [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="efce8-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="efce8-108">Return Value</span></span>  
  
|<span data-ttu-id="efce8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="efce8-109">HRESULT</span></span>|<span data-ttu-id="efce8-110">説明</span><span class="sxs-lookup"><span data-stu-id="efce8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="efce8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="efce8-111">S_OK</span></span>|<span data-ttu-id="efce8-112">`CreateRWLockOwnerIterator` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="efce8-112">`CreateRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="efce8-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="efce8-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="efce8-114">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="efce8-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="efce8-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="efce8-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="efce8-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="efce8-116">The call timed out.</span></span>|  
|<span data-ttu-id="efce8-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="efce8-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="efce8-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="efce8-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="efce8-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="efce8-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="efce8-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="efce8-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="efce8-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="efce8-121">E_FAIL</span></span>|<span data-ttu-id="efce8-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="efce8-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="efce8-123">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="efce8-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="efce8-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="efce8-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="efce8-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="efce8-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="efce8-126">`CreateRWLockOwnerIterator` マネージ コードを実行している現在のスレッドで呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="efce8-126">`CreateRWLockOwnerIterator` was called on a thread that is currently running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="efce8-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="efce8-127">Remarks</span></span>  
 <span data-ttu-id="efce8-128">ホストの通常の呼び出し、 `CreateRWLockOwnerIterator`、 `DeleteRWLockOwnerIterator`、および`GetRWLockOwnerNext`デッドロックの検出中にメソッド。</span><span class="sxs-lookup"><span data-stu-id="efce8-128">Hosts typically call the `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, and `GetRWLockOwnerNext` methods during deadlock detection.</span></span> <span data-ttu-id="efce8-129">ホストは、CLR は、リーダー/ライター ロックを維持する操作を行わないため、リーダー/ライター ロックがまだ有効であることを保証します。</span><span class="sxs-lookup"><span data-stu-id="efce8-129">The host is responsible for ensuring that the reader-writer lock is still valid, because the CLR makes no attempt to keep the reader-writer lock alive.</span></span> <span data-ttu-id="efce8-130">いくつかの方法はホストがロックの有効性を確保するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="efce8-130">Several strategies are available for the host to ensure the validity of the lock:</span></span>  
  
- <span data-ttu-id="efce8-131">ホストは、リーダー/ライター ロックの解放呼び出しをブロックできます (たとえば、 [ihostsemaphore::releasesemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) ながら、このブロックには、デッドロックは発生しません。</span><span class="sxs-lookup"><span data-stu-id="efce8-131">The host can block release calls on the reader-writer lock (for example, [IHostSemaphore::ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) while ensuring that this block does not cause deadlock.</span></span>  
  
- <span data-ttu-id="efce8-132">ホストは、もう一度このブロックにデッドロックが発生しないことを確認、リーダー/ライター ロックに関連付けられているイベント オブジェクトを待機してから終了をブロックできます。</span><span class="sxs-lookup"><span data-stu-id="efce8-132">The host can block the exit from waiting on the event object associated with the reader-writer lock, again ensuring that this block does not cause deadlock.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="efce8-133">`CreateRWLockOwnerIterator` アンマネージ コードを現在実行中のスレッドでのみ呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="efce8-133">`CreateRWLockOwnerIterator` must be called only on threads that are currently executing unmanaged code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efce8-134">必要条件</span><span class="sxs-lookup"><span data-stu-id="efce8-134">Requirements</span></span>  
 <span data-ttu-id="efce8-135">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="efce8-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efce8-136">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="efce8-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="efce8-137">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="efce8-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="efce8-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efce8-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efce8-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="efce8-139">See also</span></span>

- [<span data-ttu-id="efce8-140">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="efce8-140">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="efce8-141">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="efce8-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
