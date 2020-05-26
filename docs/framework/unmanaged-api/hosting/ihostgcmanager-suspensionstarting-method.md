---
title: IHostGCManager::SuspensionStarting メソッド
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionStarting
helpviewer_keywords:
- SuspensionStarting method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionStarting method [.NET Framework hosting]
ms.assetid: c381f524-94cf-4fa2-9298-50f847a03431
topic_type:
- apiref
ms.openlocfilehash: f2b4028c78daf266e4ffecd86e6b0b30b9607d5b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804813"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="0e4b9-102">IHostGCManager::SuspensionStarting メソッド</span><span class="sxs-lookup"><span data-stu-id="0e4b9-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="0e4b9-103">ガベージコレクションを実行するために、共通言語ランタイム (CLR) がタスクの実行を中断していることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="0e4b9-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e4b9-104">構文</span><span class="sxs-lookup"><span data-stu-id="0e4b9-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0e4b9-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="0e4b9-105">Return Value</span></span>  
  
|<span data-ttu-id="0e4b9-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0e4b9-106">HRESULT</span></span>|<span data-ttu-id="0e4b9-107">説明</span><span class="sxs-lookup"><span data-stu-id="0e4b9-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0e4b9-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="0e4b9-108">S_OK</span></span>|<span data-ttu-id="0e4b9-109">`SuspensionStarting`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="0e4b9-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="0e4b9-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0e4b9-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0e4b9-111">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="0e4b9-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0e4b9-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0e4b9-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0e4b9-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="0e4b9-113">The call timed out.</span></span>|  
|<span data-ttu-id="0e4b9-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0e4b9-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0e4b9-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="0e4b9-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0e4b9-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0e4b9-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0e4b9-117">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="0e4b9-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0e4b9-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0e4b9-118">E_FAIL</span></span>|<span data-ttu-id="0e4b9-119">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="0e4b9-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0e4b9-120">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="0e4b9-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0e4b9-121">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="0e4b9-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e4b9-122">解説</span><span class="sxs-lookup"><span data-stu-id="0e4b9-122">Remarks</span></span>  
 <span data-ttu-id="0e4b9-123">CLR はを呼び出して `SuspensionStarting` 、ガベージコレクションが発生していることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="0e4b9-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0e4b9-124">このタスクを再スケジュールしないでください。</span><span class="sxs-lookup"><span data-stu-id="0e4b9-124">Do not reschedule this task.</span></span> <span data-ttu-id="0e4b9-125">[ThreadIsBlockingForSuspension](ihostgcmanager-threadisblockingforsuspension-method.md)が呼び出されたときに、ホストはタスクを再スケジュールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e4b9-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e4b9-126">要件</span><span class="sxs-lookup"><span data-stu-id="0e4b9-126">Requirements</span></span>  
 <span data-ttu-id="0e4b9-127">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e4b9-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e4b9-128">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0e4b9-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0e4b9-129">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="0e4b9-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0e4b9-130">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e4b9-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e4b9-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e4b9-131">See also</span></span>

- [<span data-ttu-id="0e4b9-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0e4b9-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="0e4b9-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0e4b9-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="0e4b9-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0e4b9-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="0e4b9-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0e4b9-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="0e4b9-136">IHostGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0e4b9-136">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)
