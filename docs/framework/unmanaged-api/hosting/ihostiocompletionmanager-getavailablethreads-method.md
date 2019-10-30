---
title: IHostIoCompletionManager::GetAvailableThreads メソッド
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: bab363d1-b859-47a4-9884-5661c611cce7
topic_type:
- apiref
ms.openlocfilehash: 2fa429979faa04518397cf58aaa62d3e45230a76
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133841"
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="7a47d-102">IHostIoCompletionManager::GetAvailableThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="7a47d-102">IHostIoCompletionManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="7a47d-103">ホストによって管理されているスレッドの合計数に対する i/o 完了スレッドの数を取得します。これは現在、要求を処理していません。</span><span class="sxs-lookup"><span data-stu-id="7a47d-103">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a47d-104">構文</span><span class="sxs-lookup"><span data-stu-id="7a47d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a47d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7a47d-105">Parameters</span></span>  
 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="7a47d-106">入出力現在サービス要求で使用できるホストによって管理されている i/o 完了スレッドの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="7a47d-106">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a47d-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="7a47d-107">Return Value</span></span>  
  
|<span data-ttu-id="7a47d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7a47d-108">HRESULT</span></span>|<span data-ttu-id="7a47d-109">説明</span><span class="sxs-lookup"><span data-stu-id="7a47d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7a47d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7a47d-110">S_OK</span></span>|<span data-ttu-id="7a47d-111">`GetAvailableThreads` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="7a47d-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="7a47d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7a47d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7a47d-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="7a47d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7a47d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7a47d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7a47d-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="7a47d-115">The call timed out.</span></span>|  
|<span data-ttu-id="7a47d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7a47d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7a47d-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="7a47d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7a47d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7a47d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7a47d-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="7a47d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7a47d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7a47d-120">E_FAIL</span></span>|<span data-ttu-id="7a47d-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7a47d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7a47d-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="7a47d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7a47d-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="7a47d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7a47d-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="7a47d-124">E_NOTIMPL</span></span>|<span data-ttu-id="7a47d-125">ホストに `GetAvailableThreads`の実装が用意されていません。</span><span class="sxs-lookup"><span data-stu-id="7a47d-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a47d-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="7a47d-126">Remarks</span></span>  
 <span data-ttu-id="7a47d-127">ホストは、実装、パフォーマンス、スケーラビリティなどの理由から、i/o 完了スレッドプールのサイズを排他的に制御することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="7a47d-127">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="7a47d-128">そのため、ホストは `GetAvailableThreads`を実装する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7a47d-128">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="7a47d-129">この場合、ホストはこのメソッドから E_NOTIMPL を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a47d-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a47d-130">［要件］</span><span class="sxs-lookup"><span data-stu-id="7a47d-130">Requirements</span></span>  
 <span data-ttu-id="7a47d-131">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a47d-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a47d-132">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7a47d-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7a47d-133">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="7a47d-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7a47d-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a47d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a47d-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a47d-135">See also</span></span>

- [<span data-ttu-id="7a47d-136">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7a47d-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="7a47d-137">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7a47d-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
