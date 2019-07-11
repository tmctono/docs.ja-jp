---
title: IHostIoCompletionManager::GetMaxThreads メソッド
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: e7a6cadc-2433-4472-a701-58891abcde45
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fcd66914448fa63c892f7285b8cd364d4cacc5f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779207"
---
# <a name="ihostiocompletionmanagergetmaxthreads-method"></a><span data-ttu-id="e9cd8-102">IHostIoCompletionManager::GetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="e9cd8-102">IHostIoCompletionManager::GetMaxThreads Method</span></span>
<span data-ttu-id="e9cd8-103">I/O 要求を処理するには、ホストに割り当てることができますのスレッドの最大数を取得します。</span><span class="sxs-lookup"><span data-stu-id="e9cd8-103">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9cd8-104">構文</span><span class="sxs-lookup"><span data-stu-id="e9cd8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9cd8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e9cd8-105">Parameters</span></span>  
 `pdwMaxIoCompletionThreads`  
 <span data-ttu-id="e9cd8-106">[out]ホストが I/O 要求を処理するために割り当てるスレッド プール内のスレッドの最大数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e9cd8-106">[out] A pointer to the maximum number of threads in the thread pool that the host can allot to service I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9cd8-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="e9cd8-107">Return Value</span></span>  
  
|<span data-ttu-id="e9cd8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e9cd8-108">HRESULT</span></span>|<span data-ttu-id="e9cd8-109">説明</span><span class="sxs-lookup"><span data-stu-id="e9cd8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e9cd8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e9cd8-110">S_OK</span></span>|<span data-ttu-id="e9cd8-111">`GetMaxThreads` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="e9cd8-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="e9cd8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e9cd8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e9cd8-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="e9cd8-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e9cd8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e9cd8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e9cd8-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="e9cd8-115">The call timed out.</span></span>|  
|<span data-ttu-id="e9cd8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e9cd8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e9cd8-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="e9cd8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e9cd8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e9cd8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e9cd8-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="e9cd8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e9cd8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e9cd8-120">E_FAIL</span></span>|<span data-ttu-id="e9cd8-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e9cd8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e9cd8-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e9cd8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e9cd8-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="e9cd8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e9cd8-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="e9cd8-124">E_NOTIMPL</span></span>|<span data-ttu-id="e9cd8-125">ホストがの実装を提供しない`GetMaxThreads`します。</span><span class="sxs-lookup"><span data-stu-id="e9cd8-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9cd8-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="e9cd8-126">Remarks</span></span>  
 <span data-ttu-id="e9cd8-127">ホストは、実装、パフォーマンス、スケーラビリティなどのための I/O 要求の処理に割り当てることができるスレッドの数を排他的に制御を必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9cd8-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="e9cd8-128">このため、ホストする必要はありません実装`GetMaxThreads`します。</span><span class="sxs-lookup"><span data-stu-id="e9cd8-128">For this reason, the host is not required to implement `GetMaxThreads`.</span></span> <span data-ttu-id="e9cd8-129">この場合、ホストは、このメソッドから E_NOTIMPL を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9cd8-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9cd8-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="e9cd8-130">Requirements</span></span>  
 <span data-ttu-id="e9cd8-131">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9cd8-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9cd8-132">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e9cd8-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9cd8-133">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="e9cd8-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9cd8-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9cd8-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9cd8-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9cd8-135">See also</span></span>

- [<span data-ttu-id="e9cd8-136">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e9cd8-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="e9cd8-137">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e9cd8-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
