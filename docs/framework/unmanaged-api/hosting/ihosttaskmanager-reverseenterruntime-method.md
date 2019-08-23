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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6e5beabb5ac1b5a4b2a34ae8e18b7fad7c86504
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959052"
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a><span data-ttu-id="b2dea-102">IHostTaskManager::ReverseEnterRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="b2dea-102">IHostTaskManager::ReverseEnterRuntime Method</span></span>
<span data-ttu-id="b2dea-103">アンマネージコードから共通言語ランタイム (CLR) への呼び出しが行われていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="b2dea-103">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2dea-104">構文</span><span class="sxs-lookup"><span data-stu-id="b2dea-104">Syntax</span></span>  
  
```cpp  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b2dea-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="b2dea-105">Return Value</span></span>  
  
|<span data-ttu-id="b2dea-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b2dea-106">HRESULT</span></span>|<span data-ttu-id="b2dea-107">説明</span><span class="sxs-lookup"><span data-stu-id="b2dea-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b2dea-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2dea-108">S_OK</span></span>|<span data-ttu-id="b2dea-109">`ReverseEnterRuntime`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="b2dea-109">`ReverseEnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="b2dea-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b2dea-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b2dea-111">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="b2dea-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b2dea-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b2dea-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b2dea-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="b2dea-113">The call timed out.</span></span>|  
|<span data-ttu-id="b2dea-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b2dea-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b2dea-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="b2dea-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b2dea-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b2dea-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b2dea-117">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="b2dea-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b2dea-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b2dea-118">E_FAIL</span></span>|<span data-ttu-id="b2dea-119">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b2dea-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b2dea-120">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b2dea-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b2dea-121">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="b2dea-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b2dea-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b2dea-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="b2dea-123">要求されたリソース割り当てを完了するために必要なメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="b2dea-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2dea-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="b2dea-124">Remarks</span></span>  
 <span data-ttu-id="b2dea-125">マネージコードで開始されたシーケンスから CLR への呼び出しが行われる場合、へ`ReverseEnterRuntime`の各呼び出しは、 [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)の呼び出しに対応します。</span><span class="sxs-lookup"><span data-stu-id="b2dea-125">If the call into the CLR is made from a sequence that originated in managed code, each call to `ReverseEnterRuntime` corresponds to a call to [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2dea-126">呼び出しは、入れ子になっていなくてもアンマネージコードから発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="b2dea-126">Calls can originate from unmanaged code without being nested.</span></span> <span data-ttu-id="b2dea-127">この場合、 [enterruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)、all [veruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)、または`ReverseLeaveRuntime`が呼び出されておらず、へ`ReverseEnterRuntime`の呼び出しの回数がの呼び出し`ReverseLeaveRuntime`の数と等しくありません。</span><span class="sxs-lookup"><span data-stu-id="b2dea-127">In this case, there is no call to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), or `ReverseLeaveRuntime`, and the number of calls to `ReverseEnterRuntime` does not equal the number of calls to `ReverseLeaveRuntime`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2dea-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="b2dea-128">Requirements</span></span>  
 <span data-ttu-id="b2dea-129">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2dea-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2dea-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b2dea-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b2dea-131">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b2dea-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2dea-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2dea-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2dea-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2dea-133">See also</span></span>

- [<span data-ttu-id="b2dea-134">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b2dea-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="b2dea-135">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b2dea-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="b2dea-136">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b2dea-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="b2dea-137">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b2dea-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
