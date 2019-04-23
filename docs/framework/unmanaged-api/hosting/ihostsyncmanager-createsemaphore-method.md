---
title: IHostSyncManager::CreateSemaphore メソッド
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateSemaphore
helpviewer_keywords:
- CreateSemaphore method [.NET Framework hosting]
- IHostSyncManager::CreateSemaphore method [.NET Framework hosting]
ms.assetid: 37679e94-5ff9-4173-8fa5-457febeb89bf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ef9a5896c2ecc54b7fd48670f751d193ac74554
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59138620"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="6d4d6-102">IHostSyncManager::CreateSemaphore メソッド</span><span class="sxs-lookup"><span data-stu-id="6d4d6-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="6d4d6-103">作成、 [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)待機イベントのセマフォとして使用する共通言語ランタイム (CLR) オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6d4d6-103">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d4d6-104">構文</span><span class="sxs-lookup"><span data-stu-id="6d4d6-104">Syntax</span></span>  
  
```  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d4d6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6d4d6-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="6d4d6-106">[in]最初の数の`ppSemaphore`します。</span><span class="sxs-lookup"><span data-stu-id="6d4d6-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="6d4d6-107">[in]最大数は、`ppSemaphore`します。</span><span class="sxs-lookup"><span data-stu-id="6d4d6-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="6d4d6-108">[out]アドレスへのポインター、`IHostSemaphore`インスタンス、またはセマフォを作成できなかった場合は null です。</span><span class="sxs-lookup"><span data-stu-id="6d4d6-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d4d6-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="6d4d6-109">Return Value</span></span>  
  
|<span data-ttu-id="6d4d6-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6d4d6-110">HRESULT</span></span>|<span data-ttu-id="6d4d6-111">説明</span><span class="sxs-lookup"><span data-stu-id="6d4d6-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6d4d6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6d4d6-112">S_OK</span></span>|<span data-ttu-id="6d4d6-113">`CreateSemaphore` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="6d4d6-113">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="6d4d6-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6d4d6-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6d4d6-115">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="6d4d6-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6d4d6-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6d4d6-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6d4d6-117">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="6d4d6-117">The call timed out.</span></span>|  
|<span data-ttu-id="6d4d6-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6d4d6-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6d4d6-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="6d4d6-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6d4d6-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6d4d6-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6d4d6-121">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="6d4d6-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6d4d6-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6d4d6-122">E_FAIL</span></span>|<span data-ttu-id="6d4d6-123">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6d4d6-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6d4d6-124">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="6d4d6-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6d4d6-125">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="6d4d6-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6d4d6-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6d4d6-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="6d4d6-127">メモリ不足は、要求されたイベント オブジェクトを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="6d4d6-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d4d6-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="6d4d6-128">Remarks</span></span>  
 <span data-ttu-id="6d4d6-129">`CreateSemaphore` 同じ名前を持つ Win32 関数をミラー化します。</span><span class="sxs-lookup"><span data-stu-id="6d4d6-129">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="6d4d6-130">`dwInitial`と`dwMax`パラメーターとして、Win32 セマフォのカウントのと同じセマンティクスを使用して`lInitialCount`と`lMaximumCount`パラメーター、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="6d4d6-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="6d4d6-131">`dwInitial` 0 の間である必要がありますと`dwMax`までの値。</span><span class="sxs-lookup"><span data-stu-id="6d4d6-131">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="6d4d6-132">`dwMax` 0 より大きくなければなりません。</span><span class="sxs-lookup"><span data-stu-id="6d4d6-132">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d4d6-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="6d4d6-133">Requirements</span></span>  
 <span data-ttu-id="6d4d6-134">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d4d6-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d4d6-135">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6d4d6-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6d4d6-136">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="6d4d6-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d4d6-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d4d6-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d4d6-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d4d6-138">See also</span></span>

- [<span data-ttu-id="6d4d6-139">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6d4d6-139">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="6d4d6-140">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6d4d6-140">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="6d4d6-141">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6d4d6-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
