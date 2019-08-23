---
title: ICLRSyncManager::GetRWLockOwnerNext メソッド
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetRWLockOwnerNext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetRWLockOwnerNext
helpviewer_keywords:
- ICLRSyncManager::GetRWLockOwnerNext method [.NET Framework hosting]
- GetRWLockOwnerNext method [.NET Framework hosting]
ms.assetid: 0e025b6a-280e-40a2-a2d0-b15f58777b81
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dbc38d9cf88f2449bbf689e4cf1b4101f47a0577
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943258"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="4f71a-102">ICLRSyncManager::GetRWLockOwnerNext メソッド</span><span class="sxs-lookup"><span data-stu-id="4f71a-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="4f71a-103">現在のリーダーライターロックでブロックされている次の[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="4f71a-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f71a-104">構文</span><span class="sxs-lookup"><span data-stu-id="4f71a-104">Syntax</span></span>  
  
```  
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f71a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4f71a-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="4f71a-106">から[Createrwlockowneriterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)の呼び出しを使用して作成された反復子。</span><span class="sxs-lookup"><span data-stu-id="4f71a-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="4f71a-107">入出力ロックを待機して`IHostTask`いる次のへのポインター。タスクが待機していない場合は null。</span><span class="sxs-lookup"><span data-stu-id="4f71a-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f71a-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="4f71a-108">Return Value</span></span>  
  
|<span data-ttu-id="4f71a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4f71a-109">HRESULT</span></span>|<span data-ttu-id="4f71a-110">説明</span><span class="sxs-lookup"><span data-stu-id="4f71a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4f71a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4f71a-111">S_OK</span></span>|<span data-ttu-id="4f71a-112">`GetRWLockOwnerNext`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="4f71a-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="4f71a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4f71a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4f71a-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="4f71a-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4f71a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4f71a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4f71a-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="4f71a-116">The call timed out.</span></span>|  
|<span data-ttu-id="4f71a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4f71a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4f71a-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="4f71a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4f71a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4f71a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4f71a-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="4f71a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4f71a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4f71a-121">E_FAIL</span></span>|<span data-ttu-id="4f71a-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="4f71a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4f71a-123">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="4f71a-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4f71a-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="4f71a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f71a-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="4f71a-125">Remarks</span></span>  
 <span data-ttu-id="4f71a-126">が`ppOwnerHostTask` null に設定されている場合、イテレーションは終了し、ホストは[DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md)メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f71a-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f71a-127">CLR は、 `AddRef`ホストが`IHostTask`ポインターを`ppOwnerHostTask`保持している間に、このタスクが終了しないようにするを指すに対してを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4f71a-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="4f71a-128">ホストは、終了`Release`時に参照カウントをデクリメントするためにを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f71a-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f71a-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="4f71a-129">Requirements</span></span>  
 <span data-ttu-id="4f71a-130">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f71a-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f71a-131">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4f71a-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4f71a-132">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="4f71a-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f71a-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f71a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f71a-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f71a-134">See also</span></span>

- [<span data-ttu-id="4f71a-135">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f71a-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="4f71a-136">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f71a-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
