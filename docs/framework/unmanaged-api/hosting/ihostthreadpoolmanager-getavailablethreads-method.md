---
title: IHostThreadPoolManager::GetAvailableThreads メソッド
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: 61d26dfd-7f24-4e7d-a63e-b30a463f08e1
topic_type:
- apiref
ms.openlocfilehash: 21449d9365e6260267d3c79f384f6136ce894821
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122099"
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="32259-102">IHostThreadPoolManager::GetAvailableThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="32259-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="32259-103">現在作業項目を処理していないスレッドプール内のスレッドの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="32259-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32259-104">構文</span><span class="sxs-lookup"><span data-stu-id="32259-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32259-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="32259-105">Parameters</span></span>  
 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="32259-106">入出力現在作業項目を処理していないスレッドプール内のスレッドの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="32259-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32259-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="32259-107">Return Value</span></span>  
  
|<span data-ttu-id="32259-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="32259-108">HRESULT</span></span>|<span data-ttu-id="32259-109">説明</span><span class="sxs-lookup"><span data-stu-id="32259-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="32259-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="32259-110">S_OK</span></span>|<span data-ttu-id="32259-111">`GetAvailableThreads` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="32259-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="32259-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="32259-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="32259-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="32259-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="32259-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="32259-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="32259-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="32259-115">The call timed out.</span></span>|  
|<span data-ttu-id="32259-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="32259-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="32259-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="32259-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="32259-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="32259-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="32259-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="32259-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="32259-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="32259-120">E_FAIL</span></span>|<span data-ttu-id="32259-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="32259-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="32259-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="32259-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="32259-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="32259-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="32259-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="32259-124">E_NOTIMPL</span></span>|<span data-ttu-id="32259-125">ホストに `GetAvailableThreads`の実装が用意されていません。</span><span class="sxs-lookup"><span data-stu-id="32259-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32259-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="32259-126">Remarks</span></span>  
 <span data-ttu-id="32259-127">ホストに `GetAvailableThreads`の実装が提供されていない場合は、HRESULT 値として E_NOTIMPL が返されます。</span><span class="sxs-lookup"><span data-stu-id="32259-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32259-128">［要件］</span><span class="sxs-lookup"><span data-stu-id="32259-128">Requirements</span></span>  
 <span data-ttu-id="32259-129">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32259-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32259-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="32259-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32259-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="32259-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32259-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32259-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32259-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="32259-133">See also</span></span>

- <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="32259-134">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="32259-134">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
