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
ms.openlocfilehash: 02066d3923714e66bf287f1435b7854280c97cb7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195827"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="bb879-102">IHostSyncManager::CreateSemaphore メソッド</span><span class="sxs-lookup"><span data-stu-id="bb879-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="bb879-103">待機イベントのセマフォとして使用する共通言語ランタイム (CLR) の[IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="bb879-103">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb879-104">構文</span><span class="sxs-lookup"><span data-stu-id="bb879-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb879-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bb879-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="bb879-106">から`ppSemaphore`の初期カウント。</span><span class="sxs-lookup"><span data-stu-id="bb879-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="bb879-107">から`ppSemaphore`の最大数。</span><span class="sxs-lookup"><span data-stu-id="bb879-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="bb879-108">入出力`IHostSemaphore` インスタンスのアドレスへのポインター。セマフォを作成できなかった場合は null。</span><span class="sxs-lookup"><span data-stu-id="bb879-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb879-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="bb879-109">Return Value</span></span>  
  
|<span data-ttu-id="bb879-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bb879-110">HRESULT</span></span>|<span data-ttu-id="bb879-111">説明</span><span class="sxs-lookup"><span data-stu-id="bb879-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bb879-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="bb879-112">S_OK</span></span>|<span data-ttu-id="bb879-113">`CreateSemaphore` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="bb879-113">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="bb879-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bb879-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bb879-115">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="bb879-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bb879-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bb879-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bb879-117">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="bb879-117">The call timed out.</span></span>|  
|<span data-ttu-id="bb879-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bb879-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bb879-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="bb879-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bb879-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bb879-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bb879-121">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="bb879-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bb879-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bb879-122">E_FAIL</span></span>|<span data-ttu-id="bb879-123">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="bb879-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bb879-124">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="bb879-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bb879-125">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="bb879-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bb879-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="bb879-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="bb879-127">要求されたイベントオブジェクトを作成するのに十分なメモリがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="bb879-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb879-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="bb879-128">Remarks</span></span>  
 <span data-ttu-id="bb879-129">`CreateSemaphore` は、同じ名前を持つ Win32 関数をミラー化します。</span><span class="sxs-lookup"><span data-stu-id="bb879-129">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="bb879-130">`dwInitial` パラメーターと `dwMax` パラメーターは、それぞれ、Win32 `lInitialCount` および `lMaximumCount` パラメーターと同じセマンティクスを使用します。</span><span class="sxs-lookup"><span data-stu-id="bb879-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="bb879-131">`dwInitial` は0から `dwMax`までの範囲で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb879-131">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="bb879-132">`dwMax` には0より大きい値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb879-132">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb879-133">［要件］</span><span class="sxs-lookup"><span data-stu-id="bb879-133">Requirements</span></span>  
 <span data-ttu-id="bb879-134">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb879-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb879-135">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bb879-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bb879-136">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="bb879-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bb879-137">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb879-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb879-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb879-138">See also</span></span>

- [<span data-ttu-id="bb879-139">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bb879-139">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="bb879-140">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bb879-140">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="bb879-141">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bb879-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
