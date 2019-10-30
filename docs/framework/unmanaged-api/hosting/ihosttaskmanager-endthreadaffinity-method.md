---
title: IHostTaskManager::EndThreadAffinity メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndThreadAffinity
helpviewer_keywords:
- EndThreadAffinity method [.NET Framework hosting]
- IHostTaskManager::EndThreadAffinity method [.NET Framework hosting]
ms.assetid: 7738a904-0cd7-4fde-a3eb-2323a5533157
topic_type:
- apiref
ms.openlocfilehash: c40febb78c1bc78a5a724f559eb95869e90bdad0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133087"
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="09715-102">IHostTaskManager::EndThreadAffinity メソッド</span><span class="sxs-lookup"><span data-stu-id="09715-102">IHostTaskManager::EndThreadAffinity Method</span></span>
<span data-ttu-id="09715-103">以前に[IHostTaskManager:: BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)を呼び出した後に、マネージコードが、現在のタスクを別のオペレーティングシステムのスレッドに移動できない期間を終了していることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="09715-103">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09715-104">構文</span><span class="sxs-lookup"><span data-stu-id="09715-104">Syntax</span></span>  
  
```cpp  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="09715-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="09715-105">Return Value</span></span>  
  
|<span data-ttu-id="09715-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09715-106">HRESULT</span></span>|<span data-ttu-id="09715-107">説明</span><span class="sxs-lookup"><span data-stu-id="09715-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09715-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="09715-108">S_OK</span></span>|<span data-ttu-id="09715-109">`EndThreadAffinity` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="09715-109">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="09715-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="09715-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="09715-111">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="09715-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="09715-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="09715-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="09715-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="09715-113">The call timed out.</span></span>|  
|<span data-ttu-id="09715-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="09715-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="09715-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="09715-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="09715-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="09715-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="09715-117">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="09715-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="09715-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="09715-118">E_FAIL</span></span>|<span data-ttu-id="09715-119">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="09715-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="09715-120">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="09715-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="09715-121">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="09715-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="09715-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="09715-122">E_UNEXPECTED</span></span>|<span data-ttu-id="09715-123">以前に対応する `BeginThreadAffinity`の呼び出しなしで `EndThreadAffinity` が呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="09715-123">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09715-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="09715-124">Remarks</span></span>  
 <span data-ttu-id="09715-125">CLR は、`EndThreadAffinity`を呼び出す前に、現在のタスクの `BeginThreadAffinity` への対応する呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="09715-125">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="09715-126">このような対応する呼び出しがない場合、ホストの[IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)の実装は E_UNEXPECTED を返す必要があり、アクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="09715-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09715-127">［要件］</span><span class="sxs-lookup"><span data-stu-id="09715-127">Requirements</span></span>  
 <span data-ttu-id="09715-128">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09715-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09715-129">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="09715-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="09715-130">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="09715-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09715-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09715-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09715-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="09715-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="09715-133">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="09715-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="09715-134">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="09715-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="09715-135">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="09715-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="09715-136">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="09715-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
