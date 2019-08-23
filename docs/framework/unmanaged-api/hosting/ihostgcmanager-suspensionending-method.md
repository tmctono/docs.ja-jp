---
title: IHostGCManager::SuspensionEnding メソッド
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionEnding
helpviewer_keywords:
- SuspensionEnding method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionEnding method [.NET Framework hosting]
ms.assetid: 8849a1db-17f0-44b7-880a-bd36d431eb91
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f65f924b872195000f73bf29b267d1fc30b74f1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937730"
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="20d61-102">IHostGCManager::SuspensionEnding メソッド</span><span class="sxs-lookup"><span data-stu-id="20d61-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="20d61-103">共通言語ランタイム (CLR) がガベージコレクションのために中断されたスレッドでタスクの実行を再開していることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="20d61-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20d61-104">構文</span><span class="sxs-lookup"><span data-stu-id="20d61-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20d61-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="20d61-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="20d61-106">からスレッドが再開される直前に終了するガベージコレクション生成。</span><span class="sxs-lookup"><span data-stu-id="20d61-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20d61-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="20d61-107">Return Value</span></span>  
  
|<span data-ttu-id="20d61-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="20d61-108">HRESULT</span></span>|<span data-ttu-id="20d61-109">説明</span><span class="sxs-lookup"><span data-stu-id="20d61-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="20d61-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="20d61-110">S_OK</span></span>|<span data-ttu-id="20d61-111">`SuspensionEnding`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="20d61-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="20d61-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="20d61-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="20d61-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="20d61-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="20d61-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="20d61-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="20d61-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="20d61-115">The call timed out.</span></span>|  
|<span data-ttu-id="20d61-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="20d61-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="20d61-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="20d61-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="20d61-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="20d61-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="20d61-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="20d61-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="20d61-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="20d61-120">E_FAIL</span></span>|<span data-ttu-id="20d61-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="20d61-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="20d61-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="20d61-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="20d61-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="20d61-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20d61-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="20d61-124">Remarks</span></span>  
 <span data-ttu-id="20d61-125">CLR は、 `SuspensionEnding`ガベージコレクションを実行した後にを呼び出して、スレッドが実行を再開していることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="20d61-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="20d61-126">メソッドの呼び出しが行われたスレッドを再スケジュールしないでください。</span><span class="sxs-lookup"><span data-stu-id="20d61-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20d61-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="20d61-127">Requirements</span></span>  
 <span data-ttu-id="20d61-128">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="20d61-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20d61-129">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="20d61-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="20d61-130">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="20d61-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="20d61-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20d61-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20d61-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="20d61-132">See also</span></span>

- [<span data-ttu-id="20d61-133">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="20d61-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="20d61-134">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="20d61-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="20d61-135">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="20d61-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="20d61-136">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="20d61-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="20d61-137">IHostGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="20d61-137">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
