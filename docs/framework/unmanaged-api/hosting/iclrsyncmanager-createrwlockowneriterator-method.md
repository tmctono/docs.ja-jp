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
ms.openlocfilehash: fcf034d93ceb7ececd5f6c71708d442f62a00f65
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092253"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a><span data-ttu-id="0cab7-102">ICLRSyncManager::CreateRWLockOwnerIterator メソッド</span><span class="sxs-lookup"><span data-stu-id="0cab7-102">ICLRSyncManager::CreateRWLockOwnerIterator Method</span></span>
<span data-ttu-id="0cab7-103">リーダーライターロックを待機しているタスクのセットを決定するために使用するホストの反復子を共通言語ランタイム (CLR) が作成することを要求します。</span><span class="sxs-lookup"><span data-stu-id="0cab7-103">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cab7-104">構文</span><span class="sxs-lookup"><span data-stu-id="0cab7-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0cab7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0cab7-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="0cab7-106">から目的のリーダーライターロックに関連付けられているクッキー。</span><span class="sxs-lookup"><span data-stu-id="0cab7-106">[in] The cookie associated with the desired reader-writer lock.</span></span>  
  
 `pIterator`  
 <span data-ttu-id="0cab7-107">入出力[GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md)メソッドおよび[DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md)メソッドに渡すことができる反復子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="0cab7-107">[out] A pointer to an iterator that can be passed to the [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) and [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0cab7-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="0cab7-108">Return Value</span></span>  
  
|<span data-ttu-id="0cab7-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0cab7-109">HRESULT</span></span>|<span data-ttu-id="0cab7-110">説明</span><span class="sxs-lookup"><span data-stu-id="0cab7-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0cab7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0cab7-111">S_OK</span></span>|<span data-ttu-id="0cab7-112">`CreateRWLockOwnerIterator` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="0cab7-112">`CreateRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="0cab7-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0cab7-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0cab7-114">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="0cab7-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0cab7-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0cab7-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0cab7-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="0cab7-116">The call timed out.</span></span>|  
|<span data-ttu-id="0cab7-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0cab7-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0cab7-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="0cab7-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0cab7-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0cab7-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0cab7-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="0cab7-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0cab7-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0cab7-121">E_FAIL</span></span>|<span data-ttu-id="0cab7-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="0cab7-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0cab7-123">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="0cab7-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0cab7-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="0cab7-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0cab7-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="0cab7-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="0cab7-126">`CreateRWLockOwnerIterator` は、現在マネージコードを実行しているスレッドで呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="0cab7-126">`CreateRWLockOwnerIterator` was called on a thread that is currently running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0cab7-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="0cab7-127">Remarks</span></span>  
 <span data-ttu-id="0cab7-128">通常、ホストは、デッドロックの検出時に `CreateRWLockOwnerIterator`、`DeleteRWLockOwnerIterator`、および `GetRWLockOwnerNext` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0cab7-128">Hosts typically call the `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, and `GetRWLockOwnerNext` methods during deadlock detection.</span></span> <span data-ttu-id="0cab7-129">ホストは、リーダーライターロックが有効であることを CLR が防ぐため、リーダーライターロックが引き続き有効であることを保証する役割を担います。</span><span class="sxs-lookup"><span data-stu-id="0cab7-129">The host is responsible for ensuring that the reader-writer lock is still valid, because the CLR makes no attempt to keep the reader-writer lock alive.</span></span> <span data-ttu-id="0cab7-130">ホストでは、次のようないくつかの方法でロックの有効性を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0cab7-130">Several strategies are available for the host to ensure the validity of the lock:</span></span>  
  
- <span data-ttu-id="0cab7-131">ホストは、このブロックでデッドロックが発生しないようにするために、リーダーライターロック (たとえば、 [IHostSemaphore:: ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) でのリリース呼び出しをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="0cab7-131">The host can block release calls on the reader-writer lock (for example, [IHostSemaphore::ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) while ensuring that this block does not cause deadlock.</span></span>  
  
- <span data-ttu-id="0cab7-132">ホストは、リーダーライターロックに関連付けられているイベントオブジェクトでの終了の待機をブロックできます。このブロックによってデッドロックが発生しないようにします。</span><span class="sxs-lookup"><span data-stu-id="0cab7-132">The host can block the exit from waiting on the event object associated with the reader-writer lock, again ensuring that this block does not cause deadlock.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0cab7-133">`CreateRWLockOwnerIterator` は、現在アンマネージコードを実行しているスレッドでのみ呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cab7-133">`CreateRWLockOwnerIterator` must be called only on threads that are currently executing unmanaged code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cab7-134">［要件］</span><span class="sxs-lookup"><span data-stu-id="0cab7-134">Requirements</span></span>  
 <span data-ttu-id="0cab7-135">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cab7-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cab7-136">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0cab7-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0cab7-137">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="0cab7-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0cab7-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cab7-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cab7-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="0cab7-139">See also</span></span>

- [<span data-ttu-id="0cab7-140">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0cab7-140">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="0cab7-141">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0cab7-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
