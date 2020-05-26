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
ms.openlocfilehash: 22d570711c293dd8c0cc6fefd198dd46d6489bea
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803534"
---
# <a name="ihostsemaphorewait-method"></a><span data-ttu-id="9ef28-102">IHostSemaphore::Wait メソッド</span><span class="sxs-lookup"><span data-stu-id="9ef28-102">IHostSemaphore::Wait Method</span></span>
<span data-ttu-id="9ef28-103">現在の[IHostSemaphore](ihostsemaphore-interface.md)インスタンスが所有されるか、指定された時間が経過するまで待機するようにします。</span><span class="sxs-lookup"><span data-stu-id="9ef28-103">Causes the current [IHostSemaphore](ihostsemaphore-interface.md) instance to wait until it is owned or the specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ef28-104">構文</span><span class="sxs-lookup"><span data-stu-id="9ef28-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ef28-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9ef28-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="9ef28-106">から現在のインスタンスが所有されていない場合に、を返す前に待機するミリ秒数 `IHostSemaphore` 。</span><span class="sxs-lookup"><span data-stu-id="9ef28-106">[in] The number of milliseconds to wait before returning, if the current `IHostSemaphore` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="9ef28-107">から[WAIT_OPTION](wait-option-enumeration.md)値の1つ。この操作がブロックされた場合にホストが実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ef28-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, specifying what action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ef28-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="9ef28-108">Return Value</span></span>  
  
|<span data-ttu-id="9ef28-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9ef28-109">HRESULT</span></span>|<span data-ttu-id="9ef28-110">説明</span><span class="sxs-lookup"><span data-stu-id="9ef28-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9ef28-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9ef28-111">S_OK</span></span>|<span data-ttu-id="9ef28-112">`Wait`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="9ef28-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="9ef28-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9ef28-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9ef28-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="9ef28-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9ef28-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9ef28-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9ef28-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="9ef28-116">The call timed out.</span></span>|  
|<span data-ttu-id="9ef28-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9ef28-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9ef28-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="9ef28-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9ef28-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9ef28-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9ef28-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="9ef28-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9ef28-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9ef28-121">E_FAIL</span></span>|<span data-ttu-id="9ef28-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="9ef28-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9ef28-123">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="9ef28-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9ef28-124">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="9ef28-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9ef28-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="9ef28-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="9ef28-126">待機間隔中にホストがデッドロックを検出し、現在の `IHostSemaphore` インスタンスをデッドロックの対象として選択しました。</span><span class="sxs-lookup"><span data-stu-id="9ef28-126">The host detected a deadlock during the wait interval, and chose the current `IHostSemaphore` instance as a deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9ef28-127">要件</span><span class="sxs-lookup"><span data-stu-id="9ef28-127">Requirements</span></span>  
 <span data-ttu-id="9ef28-128">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ef28-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ef28-129">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9ef28-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ef28-130">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="9ef28-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ef28-131">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ef28-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ef28-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ef28-132">See also</span></span>

- [<span data-ttu-id="9ef28-133">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ef28-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="9ef28-134">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ef28-134">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="9ef28-135">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ef28-135">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="9ef28-136">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ef28-136">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="9ef28-137">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9ef28-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
