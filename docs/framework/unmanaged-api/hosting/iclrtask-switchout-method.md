---
title: ICLRTask::SwitchOut メソッド
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchOut
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type:
- apiref
ms.openlocfilehash: f9c2e77013ff9e31a0a2ef3b4ca511b76ae345e1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124601"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="ecbb5-102">ICLRTask::SwitchOut メソッド</span><span class="sxs-lookup"><span data-stu-id="ecbb5-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="ecbb5-103">現在の[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンスによって表されるタスクが操作可能な状態ではなくなったことを、共通言語ランタイム (CLR) に通知します。</span><span class="sxs-lookup"><span data-stu-id="ecbb5-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecbb5-104">構文</span><span class="sxs-lookup"><span data-stu-id="ecbb5-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ecbb5-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="ecbb5-105">Return Value</span></span>  
  
|<span data-ttu-id="ecbb5-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ecbb5-106">HRESULT</span></span>|<span data-ttu-id="ecbb5-107">説明</span><span class="sxs-lookup"><span data-stu-id="ecbb5-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ecbb5-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ecbb5-108">S_OK</span></span>|<span data-ttu-id="ecbb5-109">`SwitchOut` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="ecbb5-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="ecbb5-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ecbb5-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ecbb5-111">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="ecbb5-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ecbb5-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ecbb5-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ecbb5-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="ecbb5-113">The call timed out.</span></span>|  
|<span data-ttu-id="ecbb5-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ecbb5-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ecbb5-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="ecbb5-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ecbb5-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ecbb5-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ecbb5-117">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="ecbb5-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ecbb5-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ecbb5-118">E_FAIL</span></span>|<span data-ttu-id="ecbb5-119">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="ecbb5-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ecbb5-120">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ecbb5-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ecbb5-121">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="ecbb5-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ecbb5-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="ecbb5-122">Remarks</span></span>  
 <span data-ttu-id="ecbb5-123">ホストは `SwitchOut` を呼び出して、現在の `ICLRTask` インスタンスが表すタスクの実行を一時的に停止したことを CLR に通知し、タスクの再スケジュールを行います。</span><span class="sxs-lookup"><span data-stu-id="ecbb5-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecbb5-124">［要件］</span><span class="sxs-lookup"><span data-stu-id="ecbb5-124">Requirements</span></span>  
 <span data-ttu-id="ecbb5-125">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecbb5-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecbb5-126">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ecbb5-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ecbb5-127">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="ecbb5-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ecbb5-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecbb5-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecbb5-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="ecbb5-129">See also</span></span>

- [<span data-ttu-id="ecbb5-130">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ecbb5-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="ecbb5-131">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ecbb5-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="ecbb5-132">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ecbb5-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="ecbb5-133">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ecbb5-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
