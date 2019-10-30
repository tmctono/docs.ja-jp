---
title: IHostIoCompletionManager::GetMinThreads メソッド
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMinThreads
helpviewer_keywords:
- GetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetMinThreads method [.NET Framework hosting]
ms.assetid: d7a7f733-677d-481c-b3d5-444fcc502b8e
topic_type:
- apiref
ms.openlocfilehash: 2506de5f04840f130fab28518f9db7b58eb6e9ff
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133831"
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a><span data-ttu-id="8dbbd-102">IHostIoCompletionManager::GetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="8dbbd-102">IHostIoCompletionManager::GetMinThreads Method</span></span>
<span data-ttu-id="8dbbd-103">ホストが i/o 要求を処理するために提供するスレッドの最小数を取得します。</span><span class="sxs-lookup"><span data-stu-id="8dbbd-103">Gets the minimum number of threads that the host provides for processing I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dbbd-104">構文</span><span class="sxs-lookup"><span data-stu-id="8dbbd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8dbbd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8dbbd-105">Parameters</span></span>  
 `pdwMinIOCompletionThreads`  
 <span data-ttu-id="8dbbd-106">入出力I/o 要求を処理するためにホストが提供するスレッドの最小数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8dbbd-106">[out] A pointer to the minimum number of threads that the host provides to process I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8dbbd-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="8dbbd-107">Return Value</span></span>  
  
|<span data-ttu-id="8dbbd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8dbbd-108">HRESULT</span></span>|<span data-ttu-id="8dbbd-109">説明</span><span class="sxs-lookup"><span data-stu-id="8dbbd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8dbbd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8dbbd-110">S_OK</span></span>|<span data-ttu-id="8dbbd-111">`GetMinThreads` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="8dbbd-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="8dbbd-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8dbbd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8dbbd-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="8dbbd-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8dbbd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8dbbd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8dbbd-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="8dbbd-115">The call timed out.</span></span>|  
|<span data-ttu-id="8dbbd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8dbbd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8dbbd-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="8dbbd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8dbbd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8dbbd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8dbbd-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="8dbbd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8dbbd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8dbbd-120">E_FAIL</span></span>|<span data-ttu-id="8dbbd-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="8dbbd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8dbbd-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="8dbbd-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8dbbd-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="8dbbd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8dbbd-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="8dbbd-124">E_NOTIMPL</span></span>|<span data-ttu-id="8dbbd-125">ホストに `GetMinThreads`の実装が用意されていません。</span><span class="sxs-lookup"><span data-stu-id="8dbbd-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8dbbd-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="8dbbd-126">Remarks</span></span>  
 <span data-ttu-id="8dbbd-127">ホストは、実装、パフォーマンス、スケーラビリティなどの理由から、サービス i/o 要求に割り当てられたスレッド数を排他的に制御することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="8dbbd-127">A host might want exclusive control over the number of threads allotted to service I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="8dbbd-128">このため、ホストは `GetMinThreads`を実装する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8dbbd-128">For this reason, the host is not required to implement `GetMinThreads`.</span></span> <span data-ttu-id="8dbbd-129">この場合、ホストはこのメソッドから E_NOTIMPL を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="8dbbd-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dbbd-130">［要件］</span><span class="sxs-lookup"><span data-stu-id="8dbbd-130">Requirements</span></span>  
 <span data-ttu-id="8dbbd-131">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8dbbd-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dbbd-132">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8dbbd-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8dbbd-133">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="8dbbd-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8dbbd-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dbbd-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dbbd-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="8dbbd-135">See also</span></span>

- [<span data-ttu-id="8dbbd-136">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8dbbd-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="8dbbd-137">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8dbbd-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
