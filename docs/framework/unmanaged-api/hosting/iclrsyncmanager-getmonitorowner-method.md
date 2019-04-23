---
title: ICLRSyncManager::GetMonitorOwner メソッド
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetMonitorOwner
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetMonitorOwner
helpviewer_keywords:
- ICLRSyncManager::GetMonitorOwner method [.NET Framework hosting]
- GetMonitorOwner method [.NET Framework hosting]
ms.assetid: 840983a4-396d-47b4-86a0-d35f9b437cdb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b14421bbe71b68ca677cf712512a7f10aa30583
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208203"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a><span data-ttu-id="0ebbf-102">ICLRSyncManager::GetMonitorOwner メソッド</span><span class="sxs-lookup"><span data-stu-id="0ebbf-102">ICLRSyncManager::GetMonitorOwner Method</span></span>
<span data-ttu-id="0ebbf-103">取得、 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)指定したクッキーで識別されるモニターを所有するインスタンス。</span><span class="sxs-lookup"><span data-stu-id="0ebbf-103">Gets the [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that owns the monitor identified by the specified cookie.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ebbf-104">構文</span><span class="sxs-lookup"><span data-stu-id="0ebbf-104">Syntax</span></span>  
  
```  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ebbf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0ebbf-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="0ebbf-106">[in]モニターに関連付けられているクッキー。</span><span class="sxs-lookup"><span data-stu-id="0ebbf-106">[in] The cookie associated with the monitor.</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="0ebbf-107">[out]ポインター、`IHostTask`現在所有しているモニター、または null タスクには、所有権があるない場合。</span><span class="sxs-lookup"><span data-stu-id="0ebbf-107">[out] A pointer to the `IHostTask` that currently owns the monitor, or null if no task has ownership.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ebbf-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="0ebbf-108">Return Value</span></span>  
  
|<span data-ttu-id="0ebbf-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0ebbf-109">HRESULT</span></span>|<span data-ttu-id="0ebbf-110">説明</span><span class="sxs-lookup"><span data-stu-id="0ebbf-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0ebbf-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0ebbf-111">S_OK</span></span>|<span data-ttu-id="0ebbf-112">`GetMonitorOwner` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="0ebbf-112">`GetMonitorOwner` returned successfully.</span></span>|  
|<span data-ttu-id="0ebbf-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0ebbf-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0ebbf-114">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="0ebbf-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0ebbf-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0ebbf-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0ebbf-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="0ebbf-116">The call timed out.</span></span>|  
|<span data-ttu-id="0ebbf-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0ebbf-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0ebbf-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="0ebbf-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0ebbf-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0ebbf-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0ebbf-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="0ebbf-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0ebbf-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0ebbf-121">E_FAIL</span></span>|<span data-ttu-id="0ebbf-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="0ebbf-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0ebbf-123">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0ebbf-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0ebbf-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="0ebbf-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ebbf-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="0ebbf-125">Remarks</span></span>  
 <span data-ttu-id="0ebbf-126">ホストは`GetMonitorOwner`デッドロック検出メカニズムの一部として。</span><span class="sxs-lookup"><span data-stu-id="0ebbf-126">The host typically calls `GetMonitorOwner` as part of a deadlock-detection mechanism.</span></span> <span data-ttu-id="0ebbf-127">呼び出しを使用して作成する場合は、cookie がモニターを使用して関連付けられている[ihostsyncmanager::createmonitorevent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="0ebbf-127">The cookie is associated with a monitor when it is created by using a call to [IHostSyncManager::CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ebbf-128">モニターを基になるイベントを解放する呼び出しがブロックされる可能性、デッドロックは発生しませんが、-このメソッドの呼び出しがそのモニターに関連付けられている cookie で現在有効である場合。</span><span class="sxs-lookup"><span data-stu-id="0ebbf-128">A call to release the event underlying the monitor might block—but will not deadlock—if a call to this method is currently in effect on the cookie associated with that monitor.</span></span> <span data-ttu-id="0ebbf-129">このモニターの取得を試みる場合、その他のタスクがブロックもあります。</span><span class="sxs-lookup"><span data-stu-id="0ebbf-129">Other tasks might also block if they attempt to acquire this monitor.</span></span>  
  
 <span data-ttu-id="0ebbf-130">`GetMonitorOwner` 常にすぐを返し、呼び出しの後にいつでも呼び出すことができます`CreateMonitorEvent`します。</span><span class="sxs-lookup"><span data-stu-id="0ebbf-130">`GetMonitorOwner` always returns immediately and can be called any time after a call to `CreateMonitorEvent`.</span></span> <span data-ttu-id="0ebbf-131">ホストは、タスクがイベントで待機するまで待機する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0ebbf-131">The host does not need to wait until a task is waiting on the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ebbf-132">必要条件</span><span class="sxs-lookup"><span data-stu-id="0ebbf-132">Requirements</span></span>  
 <span data-ttu-id="0ebbf-133">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ebbf-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ebbf-134">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0ebbf-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ebbf-135">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="0ebbf-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ebbf-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ebbf-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ebbf-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ebbf-137">See also</span></span>

- [<span data-ttu-id="0ebbf-138">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0ebbf-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="0ebbf-139">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0ebbf-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
