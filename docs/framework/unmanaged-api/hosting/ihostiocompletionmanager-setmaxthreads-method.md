---
title: IHostIoCompletionManager::SetMaxThreads メソッド
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: ebad4f40-d9f1-4dc6-9b27-a89c9eb3926f
topic_type:
- apiref
ms.openlocfilehash: 7a16c141d9d07af82bd984955e06199e66ce3bbf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133759"
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="7c596-102">IHostIoCompletionManager::SetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="7c596-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="7c596-103">ホストが大量の i/o 要求を処理するスレッドの最大数を設定します。</span><span class="sxs-lookup"><span data-stu-id="7c596-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c596-104">構文</span><span class="sxs-lookup"><span data-stu-id="7c596-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c596-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7c596-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="7c596-106">からI/o 要求に割り当てるスレッドの最大数。</span><span class="sxs-lookup"><span data-stu-id="7c596-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c596-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="7c596-107">Return Value</span></span>  
  
|<span data-ttu-id="7c596-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c596-108">HRESULT</span></span>|<span data-ttu-id="7c596-109">説明</span><span class="sxs-lookup"><span data-stu-id="7c596-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c596-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c596-110">S_OK</span></span>|<span data-ttu-id="7c596-111">`SetMaxThreads` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="7c596-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="7c596-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7c596-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c596-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="7c596-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7c596-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7c596-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7c596-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="7c596-115">The call timed out.</span></span>|  
|<span data-ttu-id="7c596-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7c596-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7c596-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="7c596-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7c596-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7c596-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7c596-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="7c596-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7c596-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c596-120">E_FAIL</span></span>|<span data-ttu-id="7c596-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7c596-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7c596-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="7c596-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7c596-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="7c596-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7c596-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="7c596-124">E_NOTIMPL</span></span>|<span data-ttu-id="7c596-125">ホストに `SetMaxThreads`の実装が用意されていません。</span><span class="sxs-lookup"><span data-stu-id="7c596-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c596-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="7c596-126">Remarks</span></span>  
 <span data-ttu-id="7c596-127">`SetMaxThreads` では、i/o ポートでのサービス要求に使用できるスレッドの最大数を設定する機会が CLR に提供されます。</span><span class="sxs-lookup"><span data-stu-id="7c596-127">`SetMaxThreads` provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="7c596-128">ホストには、実装、パフォーマンス、スケーラビリティなどの理由から、スレッドプールのサイズを排他的に制御する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="7c596-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="7c596-129">このため、ホストは `SetMaxThreads`を実装する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7c596-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="7c596-130">この場合、ホストはこのメソッドから E_NOTIMPL を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c596-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c596-131">［要件］</span><span class="sxs-lookup"><span data-stu-id="7c596-131">Requirements</span></span>  
 <span data-ttu-id="7c596-132">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c596-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c596-133">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7c596-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c596-134">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="7c596-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c596-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c596-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c596-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c596-136">See also</span></span>

- [<span data-ttu-id="7c596-137">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c596-137">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="7c596-138">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c596-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
