---
title: IHostThreadPoolManager::GetMinThreads メソッド
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMinThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMinThreads method [.NET Framework hosting]
- GetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: dc07232b-b2e4-4dab-87e2-3c955974ab48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec323daf7c0d612d84c86c950c0c7235c7f9ebe7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485253"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="77e5a-102">IHostThreadPoolManager::GetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="77e5a-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="77e5a-103">要求に応じるため、スレッド プール内のホストで管理されるアイドル状態のスレッドの最小数を取得します。</span><span class="sxs-lookup"><span data-stu-id="77e5a-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77e5a-104">構文</span><span class="sxs-lookup"><span data-stu-id="77e5a-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77e5a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="77e5a-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="77e5a-106">[out]ホストが現在保持するアイドル状態のワーカー スレッドの最小数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="77e5a-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77e5a-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="77e5a-107">Return Value</span></span>  
  
|<span data-ttu-id="77e5a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="77e5a-108">HRESULT</span></span>|<span data-ttu-id="77e5a-109">説明</span><span class="sxs-lookup"><span data-stu-id="77e5a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="77e5a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="77e5a-110">S_OK</span></span>|<span data-ttu-id="77e5a-111">`GetMinThreads` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="77e5a-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="77e5a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="77e5a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="77e5a-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="77e5a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="77e5a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="77e5a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="77e5a-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="77e5a-115">The call timed out.</span></span>|  
|<span data-ttu-id="77e5a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="77e5a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="77e5a-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="77e5a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="77e5a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="77e5a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="77e5a-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="77e5a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="77e5a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="77e5a-120">E_FAIL</span></span>|<span data-ttu-id="77e5a-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="77e5a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="77e5a-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="77e5a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="77e5a-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="77e5a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="77e5a-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="77e5a-124">E_NOTIMPL</span></span>|<span data-ttu-id="77e5a-125">ホストがの実装を提供しない`GetMinThreads`します。</span><span class="sxs-lookup"><span data-stu-id="77e5a-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77e5a-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="77e5a-126">Remarks</span></span>  
 <span data-ttu-id="77e5a-127">ホストは、の実装を提供する必要はありません`GetMinThreads`します。</span><span class="sxs-lookup"><span data-stu-id="77e5a-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="77e5a-128">この場合、E_NOTIMPL の HRESULT 値を返す必要がありますに。</span><span class="sxs-lookup"><span data-stu-id="77e5a-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77e5a-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="77e5a-129">Requirements</span></span>  
 <span data-ttu-id="77e5a-130">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77e5a-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77e5a-131">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="77e5a-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="77e5a-132">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="77e5a-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77e5a-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77e5a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77e5a-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="77e5a-134">See also</span></span>
- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="77e5a-135">GetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="77e5a-135">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="77e5a-136">SetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="77e5a-136">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="77e5a-137">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="77e5a-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
