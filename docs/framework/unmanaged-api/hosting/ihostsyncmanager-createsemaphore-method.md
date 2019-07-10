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
ms.openlocfilehash: 43935829d11a925d4a3389149f5c316df15f06bb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764589"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="98881-102">IHostSyncManager::CreateSemaphore メソッド</span><span class="sxs-lookup"><span data-stu-id="98881-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="98881-103">作成、 [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)待機イベントのセマフォとして使用する共通言語ランタイム (CLR) オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="98881-103">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98881-104">構文</span><span class="sxs-lookup"><span data-stu-id="98881-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98881-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="98881-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="98881-106">[in]最初の数の`ppSemaphore`します。</span><span class="sxs-lookup"><span data-stu-id="98881-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="98881-107">[in]最大数は、`ppSemaphore`します。</span><span class="sxs-lookup"><span data-stu-id="98881-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="98881-108">[out]アドレスへのポインター、`IHostSemaphore`インスタンス、またはセマフォを作成できなかった場合は null です。</span><span class="sxs-lookup"><span data-stu-id="98881-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98881-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="98881-109">Return Value</span></span>  
  
|<span data-ttu-id="98881-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="98881-110">HRESULT</span></span>|<span data-ttu-id="98881-111">説明</span><span class="sxs-lookup"><span data-stu-id="98881-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="98881-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="98881-112">S_OK</span></span>|<span data-ttu-id="98881-113">`CreateSemaphore` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="98881-113">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="98881-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="98881-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="98881-115">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="98881-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="98881-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="98881-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="98881-117">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="98881-117">The call timed out.</span></span>|  
|<span data-ttu-id="98881-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="98881-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="98881-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="98881-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="98881-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="98881-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="98881-121">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="98881-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="98881-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="98881-122">E_FAIL</span></span>|<span data-ttu-id="98881-123">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="98881-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="98881-124">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="98881-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="98881-125">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="98881-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="98881-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="98881-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="98881-127">メモリ不足は、要求されたイベント オブジェクトを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="98881-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98881-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="98881-128">Remarks</span></span>  
 <span data-ttu-id="98881-129">`CreateSemaphore` 同じ名前を持つ Win32 関数をミラー化します。</span><span class="sxs-lookup"><span data-stu-id="98881-129">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="98881-130">`dwInitial`と`dwMax`パラメーターとして、Win32 セマフォのカウントのと同じセマンティクスを使用して`lInitialCount`と`lMaximumCount`パラメーター、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="98881-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="98881-131">`dwInitial` 0 の間である必要がありますと`dwMax`までの値。</span><span class="sxs-lookup"><span data-stu-id="98881-131">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="98881-132">`dwMax` 0 より大きくなければなりません。</span><span class="sxs-lookup"><span data-stu-id="98881-132">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98881-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="98881-133">Requirements</span></span>  
 <span data-ttu-id="98881-134">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="98881-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98881-135">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="98881-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="98881-136">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="98881-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98881-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98881-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98881-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="98881-138">See also</span></span>

- [<span data-ttu-id="98881-139">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="98881-139">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="98881-140">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="98881-140">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="98881-141">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="98881-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
