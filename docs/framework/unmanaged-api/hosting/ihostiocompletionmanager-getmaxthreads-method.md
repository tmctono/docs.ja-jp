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
ms.openlocfilehash: 8875fb24512ddfea57d5f9249e58de3c12b8c507
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796853"
---
# <a name="ihostiocompletionmanagergetmaxthreads-method"></a><span data-ttu-id="154a0-102">IHostIoCompletionManager::GetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="154a0-102">IHostIoCompletionManager::GetMaxThreads Method</span></span>
<span data-ttu-id="154a0-103">I/O 要求を処理するには、ホストに割り当てることができますのスレッドの最大数を取得します。</span><span class="sxs-lookup"><span data-stu-id="154a0-103">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="154a0-104">構文</span><span class="sxs-lookup"><span data-stu-id="154a0-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="154a0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="154a0-105">Parameters</span></span>  
 `pdwMaxIoCompletionThreads`  
 <span data-ttu-id="154a0-106">[out]ホストが I/O 要求を処理するために割り当てるスレッド プール内のスレッドの最大数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="154a0-106">[out] A pointer to the maximum number of threads in the thread pool that the host can allot to service I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="154a0-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="154a0-107">Return Value</span></span>  
  
|<span data-ttu-id="154a0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="154a0-108">HRESULT</span></span>|<span data-ttu-id="154a0-109">説明</span><span class="sxs-lookup"><span data-stu-id="154a0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="154a0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="154a0-110">S_OK</span></span>|<span data-ttu-id="154a0-111">`GetMaxThreads` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="154a0-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="154a0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="154a0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="154a0-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="154a0-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="154a0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="154a0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="154a0-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="154a0-115">The call timed out.</span></span>|  
|<span data-ttu-id="154a0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="154a0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="154a0-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="154a0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="154a0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="154a0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="154a0-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="154a0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="154a0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="154a0-120">E_FAIL</span></span>|<span data-ttu-id="154a0-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="154a0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="154a0-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="154a0-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="154a0-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="154a0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="154a0-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="154a0-124">E_NOTIMPL</span></span>|<span data-ttu-id="154a0-125">ホストがの実装を提供しない`GetMaxThreads`します。</span><span class="sxs-lookup"><span data-stu-id="154a0-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="154a0-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="154a0-126">Remarks</span></span>  
 <span data-ttu-id="154a0-127">ホストは、実装、パフォーマンス、スケーラビリティなどのための I/O 要求の処理に割り当てることができるスレッドの数を排他的に制御を必要があります。</span><span class="sxs-lookup"><span data-stu-id="154a0-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="154a0-128">このため、ホストする必要はありません実装`GetMaxThreads`します。</span><span class="sxs-lookup"><span data-stu-id="154a0-128">For this reason, the host is not required to implement `GetMaxThreads`.</span></span> <span data-ttu-id="154a0-129">この場合、ホストは、このメソッドから E_NOTIMPL を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="154a0-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="154a0-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="154a0-130">Requirements</span></span>  
 <span data-ttu-id="154a0-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="154a0-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="154a0-132">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="154a0-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="154a0-133">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="154a0-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="154a0-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="154a0-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="154a0-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="154a0-135">See also</span></span>

- [<span data-ttu-id="154a0-136">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="154a0-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="154a0-137">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="154a0-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
