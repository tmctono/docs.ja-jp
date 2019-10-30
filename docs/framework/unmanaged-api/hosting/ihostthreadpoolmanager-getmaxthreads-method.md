---
title: IHostThreadPoolManager::GetMaxThreads メソッド
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type:
- apiref
ms.openlocfilehash: e53265556de026e84af7ca345a5f82be3c5ff812
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122053"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="bfd00-102">IHostThreadPoolManager::GetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="bfd00-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>
<span data-ttu-id="bfd00-103">ホストがスレッドプール内で同時に保持するスレッドの最大数を取得します。</span><span class="sxs-lookup"><span data-stu-id="bfd00-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfd00-104">構文</span><span class="sxs-lookup"><span data-stu-id="bfd00-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfd00-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bfd00-105">Parameters</span></span>  
 `pdwMaxWorkerThreads`  
 <span data-ttu-id="bfd00-106">入出力ホストがスレッドプールで保持するスレッドの最大数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="bfd00-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bfd00-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="bfd00-107">Return Value</span></span>  
  
|<span data-ttu-id="bfd00-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bfd00-108">HRESULT</span></span>|<span data-ttu-id="bfd00-109">説明</span><span class="sxs-lookup"><span data-stu-id="bfd00-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bfd00-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="bfd00-110">S_OK</span></span>|<span data-ttu-id="bfd00-111">`GetMaxThreads` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="bfd00-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="bfd00-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bfd00-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bfd00-113">共通言語ランタイム (CLR (プロセスに読み込まれていない)、または CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="bfd00-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bfd00-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bfd00-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bfd00-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="bfd00-115">The call timed out.</span></span>|  
|<span data-ttu-id="bfd00-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bfd00-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bfd00-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="bfd00-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bfd00-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bfd00-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bfd00-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="bfd00-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bfd00-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bfd00-120">E_FAIL</span></span>|<span data-ttu-id="bfd00-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="bfd00-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bfd00-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="bfd00-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bfd00-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="bfd00-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bfd00-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="bfd00-124">E_NOTIMPL</span></span>|<span data-ttu-id="bfd00-125">ホストに `GetMaxThreads`の実装が用意されていません。</span><span class="sxs-lookup"><span data-stu-id="bfd00-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfd00-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="bfd00-126">Remarks</span></span>  
 <span data-ttu-id="bfd00-127">CLR は `GetMaxThreads` を呼び出して、スレッドプール内のスレッドの合計数を確認します。</span><span class="sxs-lookup"><span data-stu-id="bfd00-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="bfd00-128">[Get利用スレッド](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)メソッドは、現在作業項目を処理していないスレッドの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="bfd00-128">The [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="bfd00-129">`pdwMaxWorkerThreads` パラメーターの戻り値を超えるすべての要求は、スレッドが使用可能になるまでキューに置かれたままになります。</span><span class="sxs-lookup"><span data-stu-id="bfd00-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="bfd00-130">ホストに `GetMaxThreads`の実装が提供されていない場合は、HRESULT 値として E_NOTIMPL が返されます。</span><span class="sxs-lookup"><span data-stu-id="bfd00-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfd00-131">［要件］</span><span class="sxs-lookup"><span data-stu-id="bfd00-131">Requirements</span></span>  
 <span data-ttu-id="bfd00-132">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfd00-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfd00-133">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bfd00-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bfd00-134">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="bfd00-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bfd00-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfd00-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfd00-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfd00-136">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="bfd00-137">GetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="bfd00-137">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="bfd00-138">SetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="bfd00-138">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="bfd00-139">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bfd00-139">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
