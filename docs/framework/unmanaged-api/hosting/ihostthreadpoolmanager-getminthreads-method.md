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
ms.openlocfilehash: 9f4c2ea6deadeb0e9e1869a4ab064f2a948a74f4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749204"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="32d74-102">IHostThreadPoolManager::GetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="32d74-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="32d74-103">要求に応じるため、スレッド プール内のホストで管理されるアイドル状態のスレッドの最小数を取得します。</span><span class="sxs-lookup"><span data-stu-id="32d74-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32d74-104">構文</span><span class="sxs-lookup"><span data-stu-id="32d74-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32d74-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="32d74-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="32d74-106">[out]ホストが現在保持するアイドル状態のワーカー スレッドの最小数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="32d74-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32d74-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="32d74-107">Return Value</span></span>  
  
|<span data-ttu-id="32d74-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="32d74-108">HRESULT</span></span>|<span data-ttu-id="32d74-109">説明</span><span class="sxs-lookup"><span data-stu-id="32d74-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="32d74-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="32d74-110">S_OK</span></span>|<span data-ttu-id="32d74-111">`GetMinThreads` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="32d74-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="32d74-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="32d74-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="32d74-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="32d74-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="32d74-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="32d74-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="32d74-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="32d74-115">The call timed out.</span></span>|  
|<span data-ttu-id="32d74-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="32d74-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="32d74-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="32d74-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="32d74-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="32d74-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="32d74-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="32d74-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="32d74-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="32d74-120">E_FAIL</span></span>|<span data-ttu-id="32d74-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="32d74-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="32d74-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="32d74-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="32d74-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="32d74-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="32d74-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="32d74-124">E_NOTIMPL</span></span>|<span data-ttu-id="32d74-125">ホストがの実装を提供しない`GetMinThreads`します。</span><span class="sxs-lookup"><span data-stu-id="32d74-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32d74-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="32d74-126">Remarks</span></span>  
 <span data-ttu-id="32d74-127">ホストは、の実装を提供する必要はありません`GetMinThreads`します。</span><span class="sxs-lookup"><span data-stu-id="32d74-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="32d74-128">この場合、E_NOTIMPL の HRESULT 値を返す必要がありますに。</span><span class="sxs-lookup"><span data-stu-id="32d74-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32d74-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="32d74-129">Requirements</span></span>  
 <span data-ttu-id="32d74-130">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32d74-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32d74-131">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="32d74-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32d74-132">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="32d74-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32d74-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32d74-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32d74-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="32d74-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="32d74-135">GetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="32d74-135">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="32d74-136">SetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="32d74-136">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="32d74-137">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="32d74-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
