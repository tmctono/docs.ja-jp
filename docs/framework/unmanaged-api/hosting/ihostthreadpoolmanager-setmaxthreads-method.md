---
title: IHostThreadPoolManager::SetMaxThreads メソッド
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: 77cfd347-95c2-4425-b807-4ecc2a8d4578
topic_type:
- apiref
ms.openlocfilehash: 53d42afda6668acc6462c419fcefd6bc1435a34c
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842453"
---
# <a name="ihostthreadpoolmanagersetmaxthreads-method"></a><span data-ttu-id="16e13-102">IHostThreadPoolManager::SetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="16e13-102">IHostThreadPoolManager::SetMaxThreads Method</span></span>
<span data-ttu-id="16e13-103">ホストがスレッドプールで保持できるスレッドの最大数を設定します。</span><span class="sxs-lookup"><span data-stu-id="16e13-103">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16e13-104">構文</span><span class="sxs-lookup"><span data-stu-id="16e13-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMaxThreads (  
    [in] DWORD MaxThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16e13-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="16e13-105">Parameters</span></span>  
 `MaxThreads`  
 <span data-ttu-id="16e13-106">スレッド プール内のワーカー スレッドの最大数。</span><span class="sxs-lookup"><span data-stu-id="16e13-106">The maximum number of worker threads in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16e13-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="16e13-107">Return Value</span></span>  
  
|<span data-ttu-id="16e13-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="16e13-108">HRESULT</span></span>|<span data-ttu-id="16e13-109">説明</span><span class="sxs-lookup"><span data-stu-id="16e13-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="16e13-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="16e13-110">S_OK</span></span>|<span data-ttu-id="16e13-111">`SetMaxThreads`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="16e13-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="16e13-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="16e13-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="16e13-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="16e13-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="16e13-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="16e13-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="16e13-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="16e13-115">The call timed out.</span></span>|  
|<span data-ttu-id="16e13-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="16e13-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="16e13-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="16e13-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="16e13-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="16e13-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="16e13-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="16e13-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="16e13-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="16e13-120">E_FAIL</span></span>|<span data-ttu-id="16e13-121">不明な重大なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="16e13-121">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="16e13-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="16e13-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="16e13-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="16e13-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="16e13-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="16e13-124">E_NOTIMPL</span></span>|<span data-ttu-id="16e13-125">ホストはの実装を提供していません `SetMaxThreads` 。</span><span class="sxs-lookup"><span data-stu-id="16e13-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16e13-126">コメント</span><span class="sxs-lookup"><span data-stu-id="16e13-126">Remarks</span></span>  
 <span data-ttu-id="16e13-127">CLR がスレッドプールのサイズを構成できるようにするために、ホストは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="16e13-127">A host is not required to allow the CLR to configure the size of the thread pool.</span></span> <span data-ttu-id="16e13-128">ホストによっては、実装、パフォーマンス、スケーラビリティなどの理由から、スレッドプールを排他的に制御することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="16e13-128">Some hosts might want exclusive control over the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="16e13-129">この場合、ホストは E_NOTIMPL の HRESULT 値を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="16e13-129">In this case, a host should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16e13-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="16e13-130">Requirements</span></span>  
 <span data-ttu-id="16e13-131">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16e13-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16e13-132">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="16e13-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="16e13-133">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="16e13-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16e13-134">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16e13-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16e13-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="16e13-135">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="16e13-136">GetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="16e13-136">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="16e13-137">SetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="16e13-137">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="16e13-138">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16e13-138">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
