---
title: IHostManualEvent::Wait メソッド
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Wait
helpviewer_keywords:
- IHostManualEvent::Wait method [.NET Framework hosting]
- Wait method, IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 1fbb7d8b-8a23-4c2b-8376-1a70cd2d6030
topic_type:
- apiref
ms.openlocfilehash: f39a5af706ef49e3f6e4bd040d752e5698063b29
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136743"
---
# <a name="ihostmanualeventwait-method"></a><span data-ttu-id="1b5a0-102">IHostManualEvent::Wait メソッド</span><span class="sxs-lookup"><span data-stu-id="1b5a0-102">IHostManualEvent::Wait Method</span></span>
<span data-ttu-id="1b5a0-103">現在の[IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)インスタンスが所有されるか、指定された時間が経過するまで待機するようにします。</span><span class="sxs-lookup"><span data-stu-id="1b5a0-103">Causes the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to wait until it is owned, or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b5a0-104">構文</span><span class="sxs-lookup"><span data-stu-id="1b5a0-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b5a0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1b5a0-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="1b5a0-106">から現在の `IHostManualEvent` インスタンスが所有されていない場合に、を返す前に待機するミリ秒数。</span><span class="sxs-lookup"><span data-stu-id="1b5a0-106">[in] The number of milliseconds to wait before returning, if the current `IHostManualEvent` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="1b5a0-107">から[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)値の1つ。この操作がブロックされた場合にホストが実行するアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="1b5a0-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b5a0-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="1b5a0-108">Return Value</span></span>  
  
|<span data-ttu-id="1b5a0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1b5a0-109">HRESULT</span></span>|<span data-ttu-id="1b5a0-110">説明</span><span class="sxs-lookup"><span data-stu-id="1b5a0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1b5a0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1b5a0-111">S_OK</span></span>|<span data-ttu-id="1b5a0-112">`Wait` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="1b5a0-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="1b5a0-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1b5a0-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1b5a0-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="1b5a0-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1b5a0-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1b5a0-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1b5a0-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="1b5a0-116">The call timed out.</span></span>|  
|<span data-ttu-id="1b5a0-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1b5a0-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1b5a0-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="1b5a0-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1b5a0-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1b5a0-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1b5a0-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="1b5a0-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1b5a0-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1b5a0-121">E_FAIL</span></span>|<span data-ttu-id="1b5a0-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="1b5a0-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1b5a0-123">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="1b5a0-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1b5a0-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="1b5a0-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1b5a0-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="1b5a0-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="1b5a0-126">ホストは待機間隔中にデッドロックを検出し、現在の `IHostManualEvent` インスタンスをデッドロックの対象として選択しました。</span><span class="sxs-lookup"><span data-stu-id="1b5a0-126">The host detected a deadlock during the wait interval, and chose the current `IHostManualEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1b5a0-127">［要件］</span><span class="sxs-lookup"><span data-stu-id="1b5a0-127">Requirements</span></span>  
 <span data-ttu-id="1b5a0-128">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b5a0-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b5a0-129">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1b5a0-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1b5a0-130">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="1b5a0-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b5a0-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b5a0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b5a0-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b5a0-132">See also</span></span>

- [<span data-ttu-id="1b5a0-133">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1b5a0-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="1b5a0-134">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1b5a0-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="1b5a0-135">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1b5a0-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="1b5a0-136">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1b5a0-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="1b5a0-137">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1b5a0-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
