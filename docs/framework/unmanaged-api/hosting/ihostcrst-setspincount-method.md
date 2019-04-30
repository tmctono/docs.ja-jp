---
title: IHostCrst::SetSpinCount メソッド
ms.date: 03/30/2017
api_name:
- IHostCrst.SetSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::SetSpinCount
helpviewer_keywords:
- IHostCrst::SetSpinCount method [.NET Framework hosting]
- SetSpinCount method [.NET Framework hosting]
ms.assetid: 863fc8ce-9b8a-477e-8dd8-75c8544bb43a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ca17a6814b56c0fe781cfb28a35a576f02f1943
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967675"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="4a38d-102">IHostCrst::SetSpinCount メソッド</span><span class="sxs-lookup"><span data-stu-id="4a38d-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="4a38d-103">現在のスピン カウントを設定[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="4a38d-103">Sets the spin count for the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a38d-104">構文</span><span class="sxs-lookup"><span data-stu-id="4a38d-104">Syntax</span></span>  
  
```  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a38d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a38d-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="4a38d-106">[in]現在の新しいスピン カウント`IHostCrst`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="4a38d-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a38d-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="4a38d-107">Return Value</span></span>  
  
|<span data-ttu-id="4a38d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4a38d-108">HRESULT</span></span>|<span data-ttu-id="4a38d-109">説明</span><span class="sxs-lookup"><span data-stu-id="4a38d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4a38d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4a38d-110">S_OK</span></span>|<span data-ttu-id="4a38d-111">`SetSpinCount` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="4a38d-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="4a38d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4a38d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4a38d-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="4a38d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4a38d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4a38d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4a38d-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="4a38d-115">The call timed out.</span></span>|  
|<span data-ttu-id="4a38d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a38d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4a38d-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="4a38d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4a38d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4a38d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4a38d-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="4a38d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4a38d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4a38d-120">E_FAIL</span></span>|<span data-ttu-id="4a38d-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="4a38d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4a38d-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="4a38d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4a38d-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="4a38d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a38d-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="4a38d-124">Remarks</span></span>  
 <span data-ttu-id="4a38d-125">マルチプロセッサ システムでは、現在、クリティカル セクションを表す場合`IHostCrst`インスタンスが利用できない、呼び出し元のスレッドをスピン`dwSpinCount`回呼び出す前に[ihostsemaphore::wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)関連付けられているセマフォで重要なセクションです。</span><span class="sxs-lookup"><span data-stu-id="4a38d-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="4a38d-126">クリティカル セクションは、スピン操作中に無料になると、呼び出し元のスレッドは待機操作を回避できます。</span><span class="sxs-lookup"><span data-stu-id="4a38d-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="4a38d-127">使用状況`dwSpinCount`、Win32 では、同じ名前のパラメーターの使用量と同じ`InitializeCriticalSectionAndSpinCount`関数。</span><span class="sxs-lookup"><span data-stu-id="4a38d-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a38d-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="4a38d-128">Requirements</span></span>  
 <span data-ttu-id="4a38d-129">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a38d-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a38d-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4a38d-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a38d-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="4a38d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a38d-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a38d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a38d-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a38d-133">See also</span></span>

- [<span data-ttu-id="4a38d-134">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4a38d-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="4a38d-135">IHostCrst インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4a38d-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="4a38d-136">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4a38d-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
