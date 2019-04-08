---
title: IHostSemaphore::ReleaseSemaphore メソッド
ms.date: 03/30/2017
api_name:
- IHostSemaphore.ReleaseSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::ReleaseSemaphore
helpviewer_keywords:
- ReleaseSemaphore method [.NET Framework hosting]
- IHostSemaphore::ReleaseSemaphore method [.NET Framework hosting]
ms.assetid: a343d197-979a-4ac6-ab8c-cb8a05f3120e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24ec56345a5b48540d2451769f739a236a85e47b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100614"
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="bd92b-102">IHostSemaphore::ReleaseSemaphore メソッド</span><span class="sxs-lookup"><span data-stu-id="bd92b-102">IHostSemaphore::ReleaseSemaphore Method</span></span>
<span data-ttu-id="bd92b-103">現在のカウントを増やします[IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)インスタンスを指定の量。</span><span class="sxs-lookup"><span data-stu-id="bd92b-103">Increases the count of the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd92b-104">構文</span><span class="sxs-lookup"><span data-stu-id="bd92b-104">Syntax</span></span>  
  
```  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd92b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bd92b-105">Parameters</span></span>  
 `lReleaseCount`  
 <span data-ttu-id="bd92b-106">[in]現在の数を増やす量`IHostSemaphore`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="bd92b-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="bd92b-107">この量は、0 より大きくなければなりません。</span><span class="sxs-lookup"><span data-stu-id="bd92b-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="bd92b-108">[out]前のカウント、または呼び出し元は、前のカウントを必要としない場合は null へのポインター。</span><span class="sxs-lookup"><span data-stu-id="bd92b-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd92b-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="bd92b-109">Return Value</span></span>  
  
|<span data-ttu-id="bd92b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bd92b-110">HRESULT</span></span>|<span data-ttu-id="bd92b-111">説明</span><span class="sxs-lookup"><span data-stu-id="bd92b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bd92b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="bd92b-112">S_OK</span></span>|`ReleaseSemaphore` <span data-ttu-id="bd92b-113">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="bd92b-113">returned successfully.</span></span>|  
|<span data-ttu-id="bd92b-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bd92b-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bd92b-115">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="bd92b-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bd92b-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bd92b-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bd92b-117">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="bd92b-117">The call timed out.</span></span>|  
|<span data-ttu-id="bd92b-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bd92b-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bd92b-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="bd92b-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bd92b-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bd92b-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bd92b-121">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="bd92b-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bd92b-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bd92b-122">E_FAIL</span></span>|<span data-ttu-id="bd92b-123">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="bd92b-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bd92b-124">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="bd92b-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bd92b-125">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="bd92b-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd92b-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="bd92b-126">Remarks</span></span>  
 <span data-ttu-id="bd92b-127">CLR は通常、呼び出し`ReleaseSemaphore`にホストの 1 の値を渡すこと、リソースを使用して完了したことを通知する、`lReleaseCount`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="bd92b-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd92b-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="bd92b-128">Requirements</span></span>  
 <span data-ttu-id="bd92b-129">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd92b-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd92b-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bd92b-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bd92b-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="bd92b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="bd92b-132">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="bd92b-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bd92b-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd92b-133">See also</span></span>

- [<span data-ttu-id="bd92b-134">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bd92b-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="bd92b-135">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bd92b-135">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="bd92b-136">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bd92b-136">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="bd92b-137">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bd92b-137">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="bd92b-138">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bd92b-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
