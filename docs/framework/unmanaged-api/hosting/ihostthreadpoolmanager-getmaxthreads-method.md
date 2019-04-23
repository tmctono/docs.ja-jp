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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4dce4efeb82f44e2c0d19e95551696b16e9f07ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157548"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="c2978-102">IHostThreadPoolManager::GetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="c2978-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>
<span data-ttu-id="c2978-103">スレッド プールに同時にホストで管理されるスレッドの最大数を取得します。</span><span class="sxs-lookup"><span data-stu-id="c2978-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2978-104">構文</span><span class="sxs-lookup"><span data-stu-id="c2978-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2978-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c2978-105">Parameters</span></span>  
 `pdwMaxWorkerThreads`  
 <span data-ttu-id="c2978-106">[out]スレッド プールでホストを保持するスレッドの最大数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c2978-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2978-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="c2978-107">Return Value</span></span>  
  
|<span data-ttu-id="c2978-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c2978-108">HRESULT</span></span>|<span data-ttu-id="c2978-109">説明</span><span class="sxs-lookup"><span data-stu-id="c2978-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c2978-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c2978-110">S_OK</span></span>|<span data-ttu-id="c2978-111">`GetMaxThreads` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="c2978-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="c2978-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c2978-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c2978-113">共通言語ランタイム (CLR (プロセスに読み込まれていないか、CLR は状態で実行できませんマネージ コードまたはプロセスの呼び出しが正常にします。</span><span class="sxs-lookup"><span data-stu-id="c2978-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c2978-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c2978-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c2978-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="c2978-115">The call timed out.</span></span>|  
|<span data-ttu-id="c2978-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c2978-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c2978-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="c2978-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c2978-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c2978-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c2978-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="c2978-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c2978-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c2978-120">E_FAIL</span></span>|<span data-ttu-id="c2978-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c2978-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c2978-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c2978-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c2978-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="c2978-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c2978-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="c2978-124">E_NOTIMPL</span></span>|<span data-ttu-id="c2978-125">ホストがの実装を提供しない`GetMaxThreads`します。</span><span class="sxs-lookup"><span data-stu-id="c2978-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2978-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="c2978-126">Remarks</span></span>  
 <span data-ttu-id="c2978-127">CLR 呼び出し`GetMaxThreads`スレッド プール内のスレッドの合計数を決定します。</span><span class="sxs-lookup"><span data-stu-id="c2978-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="c2978-128">[GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)メソッドは、現在の作業項目を処理していないスレッドの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="c2978-128">The [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="c2978-129">戻り値を超える要求はすべて、`pdwMaxWorkerThreads`パラメーターは、スレッドが使用可能になるまでキューに置かれます。</span><span class="sxs-lookup"><span data-stu-id="c2978-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="c2978-130">ホストでの実装が提供されていない場合`GetMaxThreads`E_NOTIMPL の HRESULT 値を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2978-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2978-131">必要条件</span><span class="sxs-lookup"><span data-stu-id="c2978-131">Requirements</span></span>  
 <span data-ttu-id="c2978-132">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2978-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2978-133">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c2978-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2978-134">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c2978-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2978-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2978-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2978-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2978-136">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="c2978-137">GetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="c2978-137">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="c2978-138">SetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="c2978-138">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="c2978-139">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c2978-139">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
