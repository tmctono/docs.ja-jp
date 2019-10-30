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
ms.openlocfilehash: 33a92365e7765befe669439eabefac607232ff15
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139469"
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="2f3d1-102">IHostSemaphore::ReleaseSemaphore メソッド</span><span class="sxs-lookup"><span data-stu-id="2f3d1-102">IHostSemaphore::ReleaseSemaphore Method</span></span>
<span data-ttu-id="2f3d1-103">現在の[IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)インスタンスの数を指定された量だけ増やします。</span><span class="sxs-lookup"><span data-stu-id="2f3d1-103">Increases the count of the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f3d1-104">構文</span><span class="sxs-lookup"><span data-stu-id="2f3d1-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f3d1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2f3d1-105">Parameters</span></span>  
 `lReleaseCount`  
 <span data-ttu-id="2f3d1-106">から現在の `IHostSemaphore` インスタンスの数を増やす量。</span><span class="sxs-lookup"><span data-stu-id="2f3d1-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="2f3d1-107">この値は0より大きくなければなりません。</span><span class="sxs-lookup"><span data-stu-id="2f3d1-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="2f3d1-108">入出力前のカウントへのポインター。呼び出し元が前のカウントを必要としない場合は null。</span><span class="sxs-lookup"><span data-stu-id="2f3d1-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f3d1-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="2f3d1-109">Return Value</span></span>  
  
|<span data-ttu-id="2f3d1-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2f3d1-110">HRESULT</span></span>|<span data-ttu-id="2f3d1-111">説明</span><span class="sxs-lookup"><span data-stu-id="2f3d1-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2f3d1-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2f3d1-112">S_OK</span></span>|<span data-ttu-id="2f3d1-113">`ReleaseSemaphore` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="2f3d1-113">`ReleaseSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="2f3d1-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2f3d1-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2f3d1-115">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="2f3d1-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2f3d1-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2f3d1-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2f3d1-117">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="2f3d1-117">The call timed out.</span></span>|  
|<span data-ttu-id="2f3d1-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2f3d1-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2f3d1-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="2f3d1-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2f3d1-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2f3d1-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2f3d1-121">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="2f3d1-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2f3d1-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2f3d1-122">E_FAIL</span></span>|<span data-ttu-id="2f3d1-123">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="2f3d1-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2f3d1-124">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2f3d1-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2f3d1-125">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="2f3d1-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f3d1-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="2f3d1-126">Remarks</span></span>  
 <span data-ttu-id="2f3d1-127">CLR は通常、`ReleaseSemaphore` を呼び出して、リソースを使用して終了したことをホストに通知し、`lReleaseCount` パラメーターに値1を渡します。</span><span class="sxs-lookup"><span data-stu-id="2f3d1-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f3d1-128">［要件］</span><span class="sxs-lookup"><span data-stu-id="2f3d1-128">Requirements</span></span>  
 <span data-ttu-id="2f3d1-129">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f3d1-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f3d1-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2f3d1-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2f3d1-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="2f3d1-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2f3d1-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f3d1-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f3d1-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f3d1-133">See also</span></span>

- [<span data-ttu-id="2f3d1-134">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2f3d1-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="2f3d1-135">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2f3d1-135">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="2f3d1-136">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2f3d1-136">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="2f3d1-137">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2f3d1-137">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="2f3d1-138">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2f3d1-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
