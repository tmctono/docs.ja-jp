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
ms.openlocfilehash: 2e08af840d1c4a654fa9b9ff8b2064f5265afaf9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943236"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a><span data-ttu-id="527a1-102">ICLRSyncManager::GetMonitorOwner メソッド</span><span class="sxs-lookup"><span data-stu-id="527a1-102">ICLRSyncManager::GetMonitorOwner Method</span></span>
<span data-ttu-id="527a1-103">指定したクッキーによって識別されるモニターを所有する[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="527a1-103">Gets the [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that owns the monitor identified by the specified cookie.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="527a1-104">構文</span><span class="sxs-lookup"><span data-stu-id="527a1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="527a1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="527a1-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="527a1-106">からモニターに関連付けられているクッキー。</span><span class="sxs-lookup"><span data-stu-id="527a1-106">[in] The cookie associated with the monitor.</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="527a1-107">入出力現在モニターを所有`IHostTask`しているへのポインター。タスクに所有権がない場合は null。</span><span class="sxs-lookup"><span data-stu-id="527a1-107">[out] A pointer to the `IHostTask` that currently owns the monitor, or null if no task has ownership.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="527a1-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="527a1-108">Return Value</span></span>  
  
|<span data-ttu-id="527a1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="527a1-109">HRESULT</span></span>|<span data-ttu-id="527a1-110">説明</span><span class="sxs-lookup"><span data-stu-id="527a1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="527a1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="527a1-111">S_OK</span></span>|<span data-ttu-id="527a1-112">`GetMonitorOwner`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="527a1-112">`GetMonitorOwner` returned successfully.</span></span>|  
|<span data-ttu-id="527a1-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="527a1-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="527a1-114">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="527a1-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="527a1-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="527a1-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="527a1-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="527a1-116">The call timed out.</span></span>|  
|<span data-ttu-id="527a1-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="527a1-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="527a1-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="527a1-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="527a1-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="527a1-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="527a1-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="527a1-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="527a1-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="527a1-121">E_FAIL</span></span>|<span data-ttu-id="527a1-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="527a1-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="527a1-123">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="527a1-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="527a1-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="527a1-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="527a1-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="527a1-125">Remarks</span></span>  
 <span data-ttu-id="527a1-126">ホストは通常、 `GetMonitorOwner`デッドロック検出メカニズムの一部としてを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="527a1-126">The host typically calls `GetMonitorOwner` as part of a deadlock-detection mechanism.</span></span> <span data-ttu-id="527a1-127">クッキーは、 [IHostSyncManager:: CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)の呼び出しを使用して作成されるときに、モニターに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="527a1-127">The cookie is associated with a monitor when it is created by using a call to [IHostSyncManager::CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="527a1-128">モニターの基になるイベントを解放する呼び出しはブロックされる可能性がありますが、このメソッドの呼び出しが、そのモニターに関連付けられているクッキーで現在有効である場合、デッドロックは発生しません。</span><span class="sxs-lookup"><span data-stu-id="527a1-128">A call to release the event underlying the monitor might block—but will not deadlock—if a call to this method is currently in effect on the cookie associated with that monitor.</span></span> <span data-ttu-id="527a1-129">他のタスクも、このモニタを取得しようとするとブロックされることがあります。</span><span class="sxs-lookup"><span data-stu-id="527a1-129">Other tasks might also block if they attempt to acquire this monitor.</span></span>  
  
 <span data-ttu-id="527a1-130">`GetMonitorOwner`は常にを直ちに返します。を`CreateMonitorEvent`呼び出した後、いつでも呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="527a1-130">`GetMonitorOwner` always returns immediately and can be called any time after a call to `CreateMonitorEvent`.</span></span> <span data-ttu-id="527a1-131">ホストは、タスクがイベントを待機するまで待機する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="527a1-131">The host does not need to wait until a task is waiting on the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="527a1-132">必要条件</span><span class="sxs-lookup"><span data-stu-id="527a1-132">Requirements</span></span>  
 <span data-ttu-id="527a1-133">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="527a1-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="527a1-134">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="527a1-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="527a1-135">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="527a1-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="527a1-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="527a1-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="527a1-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="527a1-137">See also</span></span>

- [<span data-ttu-id="527a1-138">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="527a1-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="527a1-139">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="527a1-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
