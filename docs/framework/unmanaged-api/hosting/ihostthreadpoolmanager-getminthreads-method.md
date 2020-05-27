---
title: IHostThreadPoolManager::GetMinThreads メソッド
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMinThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMinThreads method [.NET Framework hosting]
- GetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: dc07232b-b2e4-4dab-87e2-3c955974ab48
topic_type:
- apiref
ms.openlocfilehash: a05cfb43b5b4a328d22c4df04049a7fa156ca080
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841933"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="44b96-102">IHostThreadPoolManager::GetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="44b96-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="44b96-103">要求を処理するために、ホストがスレッドプールで保持するアイドル状態のスレッドの最小数を取得します。</span><span class="sxs-lookup"><span data-stu-id="44b96-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44b96-104">構文</span><span class="sxs-lookup"><span data-stu-id="44b96-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44b96-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="44b96-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="44b96-106">入出力ホストが現在保持しているアイドル状態のワーカースレッドの最小数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="44b96-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44b96-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="44b96-107">Return Value</span></span>  
  
|<span data-ttu-id="44b96-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="44b96-108">HRESULT</span></span>|<span data-ttu-id="44b96-109">説明</span><span class="sxs-lookup"><span data-stu-id="44b96-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="44b96-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="44b96-110">S_OK</span></span>|<span data-ttu-id="44b96-111">`GetMinThreads`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="44b96-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="44b96-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="44b96-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="44b96-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="44b96-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="44b96-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="44b96-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="44b96-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="44b96-115">The call timed out.</span></span>|  
|<span data-ttu-id="44b96-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="44b96-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="44b96-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="44b96-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="44b96-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="44b96-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="44b96-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="44b96-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="44b96-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="44b96-120">E_FAIL</span></span>|<span data-ttu-id="44b96-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="44b96-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="44b96-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="44b96-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="44b96-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="44b96-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="44b96-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="44b96-124">E_NOTIMPL</span></span>|<span data-ttu-id="44b96-125">ホストはの実装を提供していません `GetMinThreads` 。</span><span class="sxs-lookup"><span data-stu-id="44b96-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44b96-126">コメント</span><span class="sxs-lookup"><span data-stu-id="44b96-126">Remarks</span></span>  
 <span data-ttu-id="44b96-127">ホストは、の実装を提供する必要はありません `GetMinThreads` 。</span><span class="sxs-lookup"><span data-stu-id="44b96-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="44b96-128">この場合、E_NOTIMPL の HRESULT 値が返されます。</span><span class="sxs-lookup"><span data-stu-id="44b96-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44b96-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="44b96-129">Requirements</span></span>  
 <span data-ttu-id="44b96-130">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44b96-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44b96-131">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="44b96-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="44b96-132">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="44b96-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="44b96-133">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44b96-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44b96-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="44b96-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="44b96-135">GetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="44b96-135">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="44b96-136">SetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="44b96-136">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="44b96-137">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="44b96-137">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
