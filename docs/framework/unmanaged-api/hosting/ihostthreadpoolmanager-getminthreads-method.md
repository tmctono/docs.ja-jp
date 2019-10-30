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
ms.openlocfilehash: ce1abb75c5135a9bb23f1ad2d2acbd40d9111b14
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122067"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="4c765-102">IHostThreadPoolManager::GetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="4c765-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="4c765-103">要求を処理するために、ホストがスレッドプールで保持するアイドル状態のスレッドの最小数を取得します。</span><span class="sxs-lookup"><span data-stu-id="4c765-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c765-104">構文</span><span class="sxs-lookup"><span data-stu-id="4c765-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c765-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4c765-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="4c765-106">入出力ホストが現在保持しているアイドル状態のワーカースレッドの最小数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="4c765-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c765-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="4c765-107">Return Value</span></span>  
  
|<span data-ttu-id="4c765-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4c765-108">HRESULT</span></span>|<span data-ttu-id="4c765-109">説明</span><span class="sxs-lookup"><span data-stu-id="4c765-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4c765-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4c765-110">S_OK</span></span>|<span data-ttu-id="4c765-111">`GetMinThreads` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="4c765-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="4c765-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4c765-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4c765-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="4c765-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4c765-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4c765-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4c765-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="4c765-115">The call timed out.</span></span>|  
|<span data-ttu-id="4c765-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4c765-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4c765-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="4c765-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4c765-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4c765-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4c765-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="4c765-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4c765-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4c765-120">E_FAIL</span></span>|<span data-ttu-id="4c765-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="4c765-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4c765-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="4c765-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4c765-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="4c765-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4c765-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="4c765-124">E_NOTIMPL</span></span>|<span data-ttu-id="4c765-125">ホストに `GetMinThreads`の実装が用意されていません。</span><span class="sxs-lookup"><span data-stu-id="4c765-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c765-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="4c765-126">Remarks</span></span>  
 <span data-ttu-id="4c765-127">ホストは、`GetMinThreads`の実装を提供する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4c765-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="4c765-128">この場合は、値 E_NOTIMPL の HRESULT 値を返します。</span><span class="sxs-lookup"><span data-stu-id="4c765-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c765-129">［要件］</span><span class="sxs-lookup"><span data-stu-id="4c765-129">Requirements</span></span>  
 <span data-ttu-id="4c765-130">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c765-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c765-131">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4c765-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4c765-132">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="4c765-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4c765-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c765-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c765-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c765-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="4c765-135">GetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="4c765-135">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="4c765-136">SetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="4c765-136">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="4c765-137">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4c765-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
