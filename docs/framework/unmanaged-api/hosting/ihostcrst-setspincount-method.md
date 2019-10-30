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
ms.openlocfilehash: a8642235cda359b849c49a35ab565397402c37d2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130515"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="01c4e-102">IHostCrst::SetSpinCount メソッド</span><span class="sxs-lookup"><span data-stu-id="01c4e-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="01c4e-103">現在の[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)インスタンスのスピンカウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="01c4e-103">Sets the spin count for the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01c4e-104">構文</span><span class="sxs-lookup"><span data-stu-id="01c4e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01c4e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="01c4e-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="01c4e-106">から現在の `IHostCrst` インスタンスの新しいスピンカウント。</span><span class="sxs-lookup"><span data-stu-id="01c4e-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01c4e-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="01c4e-107">Return Value</span></span>  
  
|<span data-ttu-id="01c4e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="01c4e-108">HRESULT</span></span>|<span data-ttu-id="01c4e-109">説明</span><span class="sxs-lookup"><span data-stu-id="01c4e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="01c4e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="01c4e-110">S_OK</span></span>|<span data-ttu-id="01c4e-111">`SetSpinCount` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="01c4e-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="01c4e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="01c4e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="01c4e-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="01c4e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="01c4e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="01c4e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="01c4e-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="01c4e-115">The call timed out.</span></span>|  
|<span data-ttu-id="01c4e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="01c4e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="01c4e-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="01c4e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="01c4e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="01c4e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="01c4e-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="01c4e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="01c4e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01c4e-120">E_FAIL</span></span>|<span data-ttu-id="01c4e-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="01c4e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="01c4e-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="01c4e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="01c4e-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="01c4e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01c4e-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="01c4e-124">Remarks</span></span>  
 <span data-ttu-id="01c4e-125">マルチプロセッサシステムでは、現在の `IHostCrst` インスタンスによって表されるクリティカルセクションが使用できない場合、呼び出し元のスレッドは、クリティカルセクションに関連付けられているセマフォで[IHostSemaphore:: Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)を呼び出す前に、`dwSpinCount` の時刻をスピンします。</span><span class="sxs-lookup"><span data-stu-id="01c4e-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="01c4e-126">スピン操作中にクリティカルセクションが解放されると、呼び出し元のスレッドは待機操作を回避します。</span><span class="sxs-lookup"><span data-stu-id="01c4e-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="01c4e-127">`dwSpinCount` の使用方法は、Win32 `InitializeCriticalSectionAndSpinCount` 関数で同じ名前のパラメーターを使用する場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="01c4e-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01c4e-128">［要件］</span><span class="sxs-lookup"><span data-stu-id="01c4e-128">Requirements</span></span>  
 <span data-ttu-id="01c4e-129">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01c4e-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01c4e-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="01c4e-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01c4e-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="01c4e-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01c4e-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01c4e-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01c4e-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="01c4e-133">See also</span></span>

- [<span data-ttu-id="01c4e-134">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="01c4e-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="01c4e-135">IHostCrst インターフェイス</span><span class="sxs-lookup"><span data-stu-id="01c4e-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="01c4e-136">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="01c4e-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
