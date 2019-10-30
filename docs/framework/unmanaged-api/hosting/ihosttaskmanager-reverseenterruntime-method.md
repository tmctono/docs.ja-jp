---
title: IHostTaskManager::ReverseEnterRuntime メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseEnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseEnterRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseEnterRuntime method [.NET Framework hosting]
- ReverseEnterRuntime method [.NET Framework hosting]
ms.assetid: b1e26bff-d3ea-436e-9867-29720df999f4
topic_type:
- apiref
ms.openlocfilehash: 390a29760c0f3680ca082561607ab678e8bd1e8b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133011"
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a><span data-ttu-id="69122-102">IHostTaskManager::ReverseEnterRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="69122-102">IHostTaskManager::ReverseEnterRuntime Method</span></span>
<span data-ttu-id="69122-103">アンマネージコードから共通言語ランタイム (CLR) への呼び出しが行われていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="69122-103">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69122-104">構文</span><span class="sxs-lookup"><span data-stu-id="69122-104">Syntax</span></span>  
  
```cpp  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="69122-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="69122-105">Return Value</span></span>  
  
|<span data-ttu-id="69122-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="69122-106">HRESULT</span></span>|<span data-ttu-id="69122-107">説明</span><span class="sxs-lookup"><span data-stu-id="69122-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="69122-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="69122-108">S_OK</span></span>|<span data-ttu-id="69122-109">`ReverseEnterRuntime` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="69122-109">`ReverseEnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="69122-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="69122-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="69122-111">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="69122-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="69122-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="69122-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="69122-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="69122-113">The call timed out.</span></span>|  
|<span data-ttu-id="69122-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="69122-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="69122-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="69122-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="69122-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="69122-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="69122-117">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="69122-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="69122-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="69122-118">E_FAIL</span></span>|<span data-ttu-id="69122-119">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="69122-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="69122-120">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="69122-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="69122-121">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="69122-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="69122-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="69122-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="69122-123">要求されたリソース割り当てを完了するために必要なメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="69122-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69122-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="69122-124">Remarks</span></span>  
 <span data-ttu-id="69122-125">マネージコードで発生したシーケンスから CLR への呼び出しが行われた場合、`ReverseEnterRuntime` を呼び出すたびに、 [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)への呼び出しに対応します。</span><span class="sxs-lookup"><span data-stu-id="69122-125">If the call into the CLR is made from a sequence that originated in managed code, each call to `ReverseEnterRuntime` corresponds to a call to [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69122-126">呼び出しは、入れ子になっていなくてもアンマネージコードから発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="69122-126">Calls can originate from unmanaged code without being nested.</span></span> <span data-ttu-id="69122-127">この場合、 [Enterruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)、all [veruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)、または `ReverseLeaveRuntime`は呼び出されません。また、`ReverseEnterRuntime` への呼び出しの回数は `ReverseLeaveRuntime`への呼び出しの数と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="69122-127">In this case, there is no call to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), or `ReverseLeaveRuntime`, and the number of calls to `ReverseEnterRuntime` does not equal the number of calls to `ReverseLeaveRuntime`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69122-128">［要件］</span><span class="sxs-lookup"><span data-stu-id="69122-128">Requirements</span></span>  
 <span data-ttu-id="69122-129">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69122-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69122-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="69122-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="69122-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="69122-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69122-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69122-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69122-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="69122-133">See also</span></span>

- [<span data-ttu-id="69122-134">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="69122-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="69122-135">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="69122-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="69122-136">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="69122-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="69122-137">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="69122-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
