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
ms.openlocfilehash: e748a731f2c6934f58a1cd838cc40ce4fd0e4652
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804719"
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a><span data-ttu-id="3f2b5-102">IHostIoCompletionManager::GetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="3f2b5-102">IHostIoCompletionManager::GetMinThreads Method</span></span>
<span data-ttu-id="3f2b5-103">ホストが i/o 要求を処理するために提供するスレッドの最小数を取得します。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-103">Gets the minimum number of threads that the host provides for processing I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f2b5-104">構文</span><span class="sxs-lookup"><span data-stu-id="3f2b5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f2b5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3f2b5-105">Parameters</span></span>  
 `pdwMinIOCompletionThreads`  
 <span data-ttu-id="3f2b5-106">入出力I/o 要求を処理するためにホストが提供するスレッドの最小数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-106">[out] A pointer to the minimum number of threads that the host provides to process I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f2b5-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="3f2b5-107">Return Value</span></span>  
  
|<span data-ttu-id="3f2b5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3f2b5-108">HRESULT</span></span>|<span data-ttu-id="3f2b5-109">説明</span><span class="sxs-lookup"><span data-stu-id="3f2b5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3f2b5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3f2b5-110">S_OK</span></span>|<span data-ttu-id="3f2b5-111">`GetMinThreads`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="3f2b5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3f2b5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3f2b5-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3f2b5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3f2b5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3f2b5-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-115">The call timed out.</span></span>|  
|<span data-ttu-id="3f2b5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3f2b5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3f2b5-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3f2b5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3f2b5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3f2b5-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3f2b5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3f2b5-120">E_FAIL</span></span>|<span data-ttu-id="3f2b5-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3f2b5-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3f2b5-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3f2b5-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="3f2b5-124">E_NOTIMPL</span></span>|<span data-ttu-id="3f2b5-125">ホストはの実装を提供していません `GetMinThreads` 。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f2b5-126">解説</span><span class="sxs-lookup"><span data-stu-id="3f2b5-126">Remarks</span></span>  
 <span data-ttu-id="3f2b5-127">ホストは、実装、パフォーマンス、スケーラビリティなどの理由から、サービス i/o 要求に割り当てられたスレッド数を排他的に制御することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-127">A host might want exclusive control over the number of threads allotted to service I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="3f2b5-128">このため、ホストでを実装する必要はありません `GetMinThreads` 。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-128">For this reason, the host is not required to implement `GetMinThreads`.</span></span> <span data-ttu-id="3f2b5-129">この場合、ホストはこのメソッドから E_NOTIMPL を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f2b5-130">要件</span><span class="sxs-lookup"><span data-stu-id="3f2b5-130">Requirements</span></span>  
 <span data-ttu-id="3f2b5-131">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f2b5-132">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3f2b5-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3f2b5-133">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="3f2b5-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3f2b5-134">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f2b5-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f2b5-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f2b5-135">See also</span></span>

- [<span data-ttu-id="3f2b5-136">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f2b5-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="3f2b5-137">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3f2b5-137">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
