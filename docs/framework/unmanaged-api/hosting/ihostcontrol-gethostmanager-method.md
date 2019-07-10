---
title: IHostControl::GetHostManager メソッド
ms.date: 03/30/2017
api_name:
- IHostControl.GetHostManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::GetHostManager
helpviewer_keywords:
- GetHostManager method [.NET Framework hosting]
- IHostControl::GetHostManager method [.NET Framework hosting]
ms.assetid: 0fa34bca-ed18-4626-9e78-d33684d18edb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6187da564a62b8c30abdc6a150f0df45d565615
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763870"
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="39b21-102">IHostControl::GetHostManager メソッド</span><span class="sxs-lookup"><span data-stu-id="39b21-102">IHostControl::GetHostManager Method</span></span>
<span data-ttu-id="39b21-103">指定したホストのインターフェイスの実装にインターフェイス ポインターを取得します。`IID`します。</span><span class="sxs-lookup"><span data-stu-id="39b21-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39b21-104">構文</span><span class="sxs-lookup"><span data-stu-id="39b21-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39b21-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="39b21-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="39b21-106">[in]`IID`インターフェイスの共通言語ランタイム (CLR) を照会しているのです。</span><span class="sxs-lookup"><span data-stu-id="39b21-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="39b21-107">[out]ホスト実装のインターフェイスの場合、または、ホストがこのインターフェイスをサポートしていない場合は null へのポインター。</span><span class="sxs-lookup"><span data-stu-id="39b21-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39b21-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="39b21-108">Return Value</span></span>  
  
|<span data-ttu-id="39b21-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="39b21-109">HRESULT</span></span>|<span data-ttu-id="39b21-110">説明</span><span class="sxs-lookup"><span data-stu-id="39b21-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="39b21-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="39b21-111">S_OK</span></span>|<span data-ttu-id="39b21-112">`GetHostManager` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="39b21-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="39b21-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="39b21-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="39b21-114">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="39b21-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="39b21-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="39b21-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="39b21-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="39b21-116">The call timed out.</span></span>|  
|<span data-ttu-id="39b21-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="39b21-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="39b21-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="39b21-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="39b21-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="39b21-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="39b21-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="39b21-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="39b21-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="39b21-121">E_FAIL</span></span>|<span data-ttu-id="39b21-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="39b21-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="39b21-123">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="39b21-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="39b21-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="39b21-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="39b21-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="39b21-125">E_INVALIDARG</span></span>|<span data-ttu-id="39b21-126">要求された`IID`が無効です。</span><span class="sxs-lookup"><span data-stu-id="39b21-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="39b21-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="39b21-127">E_NOINTERFACE</span></span>|<span data-ttu-id="39b21-128">要求されたインターフェイスがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="39b21-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39b21-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="39b21-129">Remarks</span></span>  
 <span data-ttu-id="39b21-130">CLR では、次のインターフェイスの 1 つ以上をサポートすることかどうかを確認するホストを照会します。</span><span class="sxs-lookup"><span data-stu-id="39b21-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
- [<span data-ttu-id="39b21-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="39b21-131">IHostMemoryManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
  
- [<span data-ttu-id="39b21-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="39b21-132">IHostTaskManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
  
- [<span data-ttu-id="39b21-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="39b21-133">IHostThreadPoolManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
  
- [<span data-ttu-id="39b21-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="39b21-134">IHostIoCompletionManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
  
- [<span data-ttu-id="39b21-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="39b21-135">IHostSyncManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
  
- [<span data-ttu-id="39b21-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="39b21-136">IHostAssemblyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
  
- [<span data-ttu-id="39b21-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="39b21-137">IHostGCManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
  
- [<span data-ttu-id="39b21-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="39b21-138">IHostPolicyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
  
- [<span data-ttu-id="39b21-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="39b21-139">IHostSecurityManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="39b21-140">ホストは、指定したインターフェイスをサポートする場合は設定`ppObject`そのインターフェイスの実装にします。</span><span class="sxs-lookup"><span data-stu-id="39b21-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="39b21-141">それ以外の場合、設定`ppObject`を null にします。</span><span class="sxs-lookup"><span data-stu-id="39b21-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="39b21-142">CLR は呼び出しません`Release`シャット ダウンした場合でも、ホスト マネージャー。</span><span class="sxs-lookup"><span data-stu-id="39b21-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39b21-143">必要条件</span><span class="sxs-lookup"><span data-stu-id="39b21-143">Requirements</span></span>  
 <span data-ttu-id="39b21-144">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="39b21-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39b21-145">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="39b21-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="39b21-146">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="39b21-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39b21-147">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39b21-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39b21-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="39b21-148">See also</span></span>

- [<span data-ttu-id="39b21-149">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39b21-149">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
