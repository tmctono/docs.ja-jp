---
title: IHostIoCompletionManager::SetMinThreads メソッド
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: dea34b81-8d2b-4cc3-8696-0ad4291d8a92
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fd37546c63ef5e5f25686e105247555dfeb132a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222784"
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="d697a-102">IHostIoCompletionManager::SetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="d697a-102">IHostIoCompletionManager::SetMinThreads Method</span></span>
<span data-ttu-id="d697a-103">I/O 完了するには、ホストを割り当てるスレッドの最小数を設定します。</span><span class="sxs-lookup"><span data-stu-id="d697a-103">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d697a-104">構文</span><span class="sxs-lookup"><span data-stu-id="d697a-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d697a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d697a-105">Parameters</span></span>  
 `dwMinIoCompletionThreads`  
 <span data-ttu-id="d697a-106">[in]ホストを作成する必要があります I/O 完了スレッドの最小数。</span><span class="sxs-lookup"><span data-stu-id="d697a-106">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d697a-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="d697a-107">Return Value</span></span>  
  
|<span data-ttu-id="d697a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d697a-108">HRESULT</span></span>|<span data-ttu-id="d697a-109">説明</span><span class="sxs-lookup"><span data-stu-id="d697a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d697a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d697a-110">S_OK</span></span>|<span data-ttu-id="d697a-111">`SetMinThreads` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="d697a-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="d697a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d697a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d697a-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="d697a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d697a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d697a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d697a-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="d697a-115">The call timed out.</span></span>|  
|<span data-ttu-id="d697a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d697a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d697a-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="d697a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d697a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d697a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d697a-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="d697a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d697a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d697a-120">E_FAIL</span></span>|<span data-ttu-id="d697a-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d697a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d697a-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d697a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d697a-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="d697a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d697a-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="d697a-124">E_NOTIMPL</span></span>|<span data-ttu-id="d697a-125">ホストがの実装を提供しない`SetMinThreads`します。</span><span class="sxs-lookup"><span data-stu-id="d697a-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d697a-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="d697a-126">Remarks</span></span>  
 <span data-ttu-id="d697a-127">ホストは、実装、パフォーマンス、スケーラビリティなどのための I/O 要求の処理に割り当てることができるスレッドの数を排他的に制御を必要があります。</span><span class="sxs-lookup"><span data-stu-id="d697a-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="d697a-128">このため、ホストする必要はありません実装`SetMinThreads`します。</span><span class="sxs-lookup"><span data-stu-id="d697a-128">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="d697a-129">この場合、ホストは、このメソッドから E_NOTIMPL を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d697a-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d697a-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="d697a-130">Requirements</span></span>  
 <span data-ttu-id="d697a-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d697a-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d697a-132">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d697a-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d697a-133">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d697a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d697a-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d697a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d697a-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="d697a-135">See also</span></span>

- [<span data-ttu-id="d697a-136">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d697a-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="d697a-137">SetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="d697a-137">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)
- [<span data-ttu-id="d697a-138">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d697a-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
