---
title: IHostSemaphore::Wait メソッド
ms.date: 03/30/2017
api_name:
- IHostSemaphore.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::Wait
helpviewer_keywords:
- IHostSemaphore::Wait method [.NET Framework hosting]
- Wait method, IHostSemaphore interface [.NET Framework hosting]
ms.assetid: 0da962a3-ce55-44dd-ab7a-14ad7105af4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1d578fa0f8e80ae2c8fbada9e383bcd849ff2f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753608"
---
# <a name="ihostsemaphorewait-method"></a><span data-ttu-id="ca6d4-102">IHostSemaphore::Wait メソッド</span><span class="sxs-lookup"><span data-stu-id="ca6d4-102">IHostSemaphore::Wait Method</span></span>
<span data-ttu-id="ca6d4-103">現在[IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)所有者になるまで待機するインスタンスまたは指定された時間が経過する量。</span><span class="sxs-lookup"><span data-stu-id="ca6d4-103">Causes the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance to wait until it is owned or the specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca6d4-104">構文</span><span class="sxs-lookup"><span data-stu-id="ca6d4-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca6d4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ca6d4-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="ca6d4-106">[in]場合は、戻る前に待機するミリ秒数、現在`IHostSemaphore`インスタンスは所有されていません。</span><span class="sxs-lookup"><span data-stu-id="ca6d4-106">[in] The number of milliseconds to wait before returning, if the current `IHostSemaphore` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="ca6d4-107">[in]1 つ、 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)ホストが実行する場合は、このアクションを指定する値は、操作がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="ca6d4-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying what action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca6d4-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="ca6d4-108">Return Value</span></span>  
  
|<span data-ttu-id="ca6d4-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ca6d4-109">HRESULT</span></span>|<span data-ttu-id="ca6d4-110">説明</span><span class="sxs-lookup"><span data-stu-id="ca6d4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ca6d4-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ca6d4-111">S_OK</span></span>|<span data-ttu-id="ca6d4-112">`Wait` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="ca6d4-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="ca6d4-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ca6d4-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ca6d4-114">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="ca6d4-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ca6d4-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ca6d4-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ca6d4-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="ca6d4-116">The call timed out.</span></span>|  
|<span data-ttu-id="ca6d4-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ca6d4-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ca6d4-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="ca6d4-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ca6d4-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ca6d4-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ca6d4-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="ca6d4-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ca6d4-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ca6d4-121">E_FAIL</span></span>|<span data-ttu-id="ca6d4-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="ca6d4-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ca6d4-123">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ca6d4-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ca6d4-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="ca6d4-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ca6d4-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="ca6d4-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="ca6d4-126">ホストが、待機中にデッドロックを検出し、現在`IHostSemaphore`デッドロックの対象としてインスタンス。</span><span class="sxs-lookup"><span data-stu-id="ca6d4-126">The host detected a deadlock during the wait interval, and chose the current `IHostSemaphore` instance as a deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ca6d4-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="ca6d4-127">Requirements</span></span>  
 <span data-ttu-id="ca6d4-128">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca6d4-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca6d4-129">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ca6d4-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca6d4-130">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="ca6d4-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca6d4-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca6d4-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca6d4-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca6d4-132">See also</span></span>

- [<span data-ttu-id="ca6d4-133">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ca6d4-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="ca6d4-134">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ca6d4-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="ca6d4-135">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ca6d4-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="ca6d4-136">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ca6d4-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="ca6d4-137">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ca6d4-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
