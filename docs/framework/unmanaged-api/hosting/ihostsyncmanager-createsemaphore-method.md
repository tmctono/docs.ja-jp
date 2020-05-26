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
ms.openlocfilehash: 680280e959d523356b95a5a4d9390c80720c0330
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803135"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="6ca09-102">IHostSyncManager::CreateSemaphore メソッド</span><span class="sxs-lookup"><span data-stu-id="6ca09-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="6ca09-103">待機イベントのセマフォとして使用する共通言語ランタイム (CLR) の[IHostSemaphore](ihostsemaphore-interface.md)オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="6ca09-103">Creates an [IHostSemaphore](ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ca09-104">構文</span><span class="sxs-lookup"><span data-stu-id="6ca09-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ca09-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6ca09-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="6ca09-106">からの初期カウント `ppSemaphore` 。</span><span class="sxs-lookup"><span data-stu-id="6ca09-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="6ca09-107">からの最大数 `ppSemaphore` 。</span><span class="sxs-lookup"><span data-stu-id="6ca09-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="6ca09-108">入出力インスタンスのアドレスへのポインター。セマフォを作成できなかった `IHostSemaphore` 場合は null。</span><span class="sxs-lookup"><span data-stu-id="6ca09-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ca09-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="6ca09-109">Return Value</span></span>  
  
|<span data-ttu-id="6ca09-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6ca09-110">HRESULT</span></span>|<span data-ttu-id="6ca09-111">説明</span><span class="sxs-lookup"><span data-stu-id="6ca09-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6ca09-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6ca09-112">S_OK</span></span>|<span data-ttu-id="6ca09-113">`CreateSemaphore`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="6ca09-113">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="6ca09-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6ca09-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6ca09-115">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="6ca09-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6ca09-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6ca09-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6ca09-117">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="6ca09-117">The call timed out.</span></span>|  
|<span data-ttu-id="6ca09-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6ca09-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6ca09-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="6ca09-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6ca09-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6ca09-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6ca09-121">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="6ca09-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6ca09-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6ca09-122">E_FAIL</span></span>|<span data-ttu-id="6ca09-123">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6ca09-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6ca09-124">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="6ca09-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6ca09-125">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="6ca09-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6ca09-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6ca09-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="6ca09-127">要求されたイベントオブジェクトを作成するのに十分なメモリがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="6ca09-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ca09-128">解説</span><span class="sxs-lookup"><span data-stu-id="6ca09-128">Remarks</span></span>  
 <span data-ttu-id="6ca09-129">`CreateSemaphore`同じ名前を持つ Win32 関数をミラー化します。</span><span class="sxs-lookup"><span data-stu-id="6ca09-129">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="6ca09-130">`dwInitial`パラメーターと `dwMax` パラメーターは、それぞれ、Win32 およびパラメーターと同じセマンティクスを使用し `lInitialCount` `lMaximumCount` ます。</span><span class="sxs-lookup"><span data-stu-id="6ca09-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="6ca09-131">`dwInitial`0からまでの範囲で指定する必要があり `dwMax` ます。</span><span class="sxs-lookup"><span data-stu-id="6ca09-131">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="6ca09-132">`dwMax` は 0 よりも大きい値にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ca09-132">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ca09-133">要件</span><span class="sxs-lookup"><span data-stu-id="6ca09-133">Requirements</span></span>  
 <span data-ttu-id="6ca09-134">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ca09-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ca09-135">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6ca09-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6ca09-136">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="6ca09-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ca09-137">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ca09-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ca09-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ca09-138">See also</span></span>

- [<span data-ttu-id="6ca09-139">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6ca09-139">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="6ca09-140">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6ca09-140">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="6ca09-141">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6ca09-141">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
