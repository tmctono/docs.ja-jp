---
title: IHostTaskManager::BeginDelayAbort メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginDelayAbort
helpviewer_keywords:
- BeginDelayAbort method [.NET Framework hosting]
- IHostTaskManager::BeginDelayAbort method [.NET Framework hosting]
ms.assetid: 75f42a8b-ed68-4718-a030-a179cfba7d72
topic_type:
- apiref
ms.openlocfilehash: b765d5449cebbdec5f106a8e4743fee2f0ee5521
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133133"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="714c3-102">IHostTaskManager::BeginDelayAbort メソッド</span><span class="sxs-lookup"><span data-stu-id="714c3-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="714c3-103">マネージコードが、現在のタスクを中止できない期間を入力していることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="714c3-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="714c3-104">構文</span><span class="sxs-lookup"><span data-stu-id="714c3-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="714c3-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="714c3-105">Return Value</span></span>  
  
|<span data-ttu-id="714c3-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="714c3-106">HRESULT</span></span>|<span data-ttu-id="714c3-107">説明</span><span class="sxs-lookup"><span data-stu-id="714c3-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="714c3-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="714c3-108">S_OK</span></span>|<span data-ttu-id="714c3-109">`BeginDelayAbort` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="714c3-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="714c3-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="714c3-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="714c3-111">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="714c3-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="714c3-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="714c3-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="714c3-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="714c3-113">The call timed out.</span></span>|  
|<span data-ttu-id="714c3-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="714c3-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="714c3-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="714c3-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="714c3-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="714c3-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="714c3-117">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="714c3-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="714c3-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="714c3-118">E_FAIL</span></span>|<span data-ttu-id="714c3-119">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="714c3-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="714c3-120">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="714c3-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="714c3-121">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="714c3-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="714c3-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="714c3-122">E_UNEXPECTED</span></span>|<span data-ttu-id="714c3-123">`BeginDelayAbort` は既に呼び出されていますが、 [Enddelayabort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)への対応する呼び出しはまだ受信されていません。</span><span class="sxs-lookup"><span data-stu-id="714c3-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="714c3-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="714c3-124">Remarks</span></span>  
 <span data-ttu-id="714c3-125">ホストは `EndDelayAbort` が呼び出されるまで、現在のタスクを中止することはできません。</span><span class="sxs-lookup"><span data-stu-id="714c3-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="714c3-126">`EndDelayAbort`の呼び出しが介在せずに `BeginDelayAbort` の別の呼び出しが行われた場合、ホストは `BeginDelayAbort`から E_UNEXPECTED を返し、アクションを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="714c3-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="714c3-127">［要件］</span><span class="sxs-lookup"><span data-stu-id="714c3-127">Requirements</span></span>  
 <span data-ttu-id="714c3-128">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="714c3-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="714c3-129">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="714c3-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="714c3-130">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="714c3-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="714c3-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="714c3-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="714c3-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="714c3-132">See also</span></span>

- [<span data-ttu-id="714c3-133">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="714c3-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="714c3-134">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="714c3-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="714c3-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="714c3-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
