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
ms.openlocfilehash: aa67aabbe8a7a47a9b3036f508e2f8bb6082c3e0
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803553"
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="466e9-102">IHostSemaphore::ReleaseSemaphore メソッド</span><span class="sxs-lookup"><span data-stu-id="466e9-102">IHostSemaphore::ReleaseSemaphore Method</span></span>
<span data-ttu-id="466e9-103">現在の[IHostSemaphore](ihostsemaphore-interface.md)インスタンスの数を指定された量だけ増やします。</span><span class="sxs-lookup"><span data-stu-id="466e9-103">Increases the count of the current [IHostSemaphore](ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="466e9-104">構文</span><span class="sxs-lookup"><span data-stu-id="466e9-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="466e9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="466e9-105">Parameters</span></span>  
 `lReleaseCount`  
 <span data-ttu-id="466e9-106">から現在のインスタンスの数を増やす量 `IHostSemaphore` 。</span><span class="sxs-lookup"><span data-stu-id="466e9-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="466e9-107">この値は0より大きくなければなりません。</span><span class="sxs-lookup"><span data-stu-id="466e9-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="466e9-108">入出力前のカウントへのポインター。呼び出し元が前のカウントを必要としない場合は null。</span><span class="sxs-lookup"><span data-stu-id="466e9-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="466e9-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="466e9-109">Return Value</span></span>  
  
|<span data-ttu-id="466e9-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="466e9-110">HRESULT</span></span>|<span data-ttu-id="466e9-111">説明</span><span class="sxs-lookup"><span data-stu-id="466e9-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="466e9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="466e9-112">S_OK</span></span>|<span data-ttu-id="466e9-113">`ReleaseSemaphore`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="466e9-113">`ReleaseSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="466e9-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="466e9-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="466e9-115">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="466e9-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="466e9-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="466e9-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="466e9-117">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="466e9-117">The call timed out.</span></span>|  
|<span data-ttu-id="466e9-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="466e9-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="466e9-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="466e9-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="466e9-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="466e9-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="466e9-121">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="466e9-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="466e9-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="466e9-122">E_FAIL</span></span>|<span data-ttu-id="466e9-123">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="466e9-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="466e9-124">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="466e9-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="466e9-125">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="466e9-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="466e9-126">解説</span><span class="sxs-lookup"><span data-stu-id="466e9-126">Remarks</span></span>  
 <span data-ttu-id="466e9-127">CLR は、通常、を呼び出して、 `ReleaseSemaphore` リソースを使用して終了したことをホストに通知し、パラメーターに値1を渡し `lReleaseCount` ます。</span><span class="sxs-lookup"><span data-stu-id="466e9-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="466e9-128">要件</span><span class="sxs-lookup"><span data-stu-id="466e9-128">Requirements</span></span>  
 <span data-ttu-id="466e9-129">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="466e9-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="466e9-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="466e9-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="466e9-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="466e9-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="466e9-132">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="466e9-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="466e9-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="466e9-133">See also</span></span>

- [<span data-ttu-id="466e9-134">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="466e9-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="466e9-135">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="466e9-135">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="466e9-136">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="466e9-136">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="466e9-137">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="466e9-137">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="466e9-138">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="466e9-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
