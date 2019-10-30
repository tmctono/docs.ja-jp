---
title: IHostThreadPoolManager::SetMinThreads メソッド
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: 10409db9-9fd2-4e4d-b8cd-cf6fec0afaa2
topic_type:
- apiref
ms.openlocfilehash: f2d2665382559596563d9b155d2afa4d99c91ee7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141260"
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="5afb2-102">IHostThreadPoolManager::SetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="5afb2-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="5afb2-103">ホストが要求を見越して保持する必要があるアイドル状態のスレッドの最小数を設定します。</span><span class="sxs-lookup"><span data-stu-id="5afb2-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5afb2-104">構文</span><span class="sxs-lookup"><span data-stu-id="5afb2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5afb2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5afb2-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="5afb2-106">からホストが保持する必要があるスレッドの新しい最小数。</span><span class="sxs-lookup"><span data-stu-id="5afb2-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5afb2-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="5afb2-107">Return Value</span></span>  
  
|<span data-ttu-id="5afb2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5afb2-108">HRESULT</span></span>|<span data-ttu-id="5afb2-109">説明</span><span class="sxs-lookup"><span data-stu-id="5afb2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5afb2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5afb2-110">S_OK</span></span>|<span data-ttu-id="5afb2-111">`SetMinThreads` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="5afb2-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="5afb2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5afb2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5afb2-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="5afb2-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5afb2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5afb2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5afb2-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="5afb2-115">The call timed out.</span></span>|  
|<span data-ttu-id="5afb2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5afb2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5afb2-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="5afb2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5afb2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5afb2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5afb2-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="5afb2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5afb2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5afb2-120">E_FAIL</span></span>|<span data-ttu-id="5afb2-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5afb2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5afb2-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5afb2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5afb2-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="5afb2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5afb2-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="5afb2-124">E_NOTIMPL</span></span>|<span data-ttu-id="5afb2-125">ホストに `SetMinThreads`の実装が用意されていません。</span><span class="sxs-lookup"><span data-stu-id="5afb2-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5afb2-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="5afb2-126">Remarks</span></span>  
 <span data-ttu-id="5afb2-127">ホストは、`SetMinThreads`の実装を提供する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5afb2-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="5afb2-128">この場合は、値 E_NOTIMPL の HRESULT 値を返します。</span><span class="sxs-lookup"><span data-stu-id="5afb2-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5afb2-129">［要件］</span><span class="sxs-lookup"><span data-stu-id="5afb2-129">Requirements</span></span>  
 <span data-ttu-id="5afb2-130">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5afb2-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5afb2-131">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5afb2-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5afb2-132">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="5afb2-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5afb2-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5afb2-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5afb2-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="5afb2-134">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="5afb2-135">GetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="5afb2-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="5afb2-136">SetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="5afb2-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="5afb2-137">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5afb2-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
