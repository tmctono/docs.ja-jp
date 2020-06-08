---
title: IHostTaskManager::CallNeedsHostHook メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CallNeedsHostHook
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type:
- apiref
ms.openlocfilehash: 8cbac3b4ad25ba7dc01413f0c1b44541c43b3999
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503875"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="c42f9-102">IHostTaskManager::CallNeedsHostHook メソッド</span><span class="sxs-lookup"><span data-stu-id="c42f9-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="c42f9-103">共通言語ランタイム (CLR) が、指定された呼び出しをアンマネージ関数にインライン化できるかどうかをホストが指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c42f9-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c42f9-104">構文</span><span class="sxs-lookup"><span data-stu-id="c42f9-104">Syntax</span></span>  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c42f9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c42f9-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="c42f9-106">から呼び出されるアンマネージ関数の、マップされたポータブル実行可能 (PE) ファイル内のアドレス。</span><span class="sxs-lookup"><span data-stu-id="c42f9-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="c42f9-107">入出力ホストがフックの呼び出しを必要とするかどうかを示すブール値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c42f9-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c42f9-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="c42f9-108">Return Value</span></span>  
  
|<span data-ttu-id="c42f9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c42f9-109">HRESULT</span></span>|<span data-ttu-id="c42f9-110">説明</span><span class="sxs-lookup"><span data-stu-id="c42f9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c42f9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c42f9-111">S_OK</span></span>|<span data-ttu-id="c42f9-112">`CallNeedsHostHook`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="c42f9-112">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="c42f9-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c42f9-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c42f9-114">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="c42f9-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c42f9-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c42f9-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c42f9-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="c42f9-116">The call timed out.</span></span>|  
|<span data-ttu-id="c42f9-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c42f9-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c42f9-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="c42f9-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c42f9-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c42f9-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c42f9-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="c42f9-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c42f9-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c42f9-121">E_FAIL</span></span>|<span data-ttu-id="c42f9-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c42f9-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="c42f9-123">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="c42f9-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c42f9-124">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="c42f9-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c42f9-125">解説</span><span class="sxs-lookup"><span data-stu-id="c42f9-125">Remarks</span></span>  
 <span data-ttu-id="c42f9-126">コードの実行を最適化するために、CLR はコンパイル中に各プラットフォーム呼び出しの分析を実行し、呼び出しをインライン化できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="c42f9-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="c42f9-127">`CallNeedsHostHook`アンマネージ関数の呼び出しをフックするように要求することによって、ホストがその決定をオーバーライドできるようにします。</span><span class="sxs-lookup"><span data-stu-id="c42f9-127">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="c42f9-128">ホストにフックが必要な場合、ランタイムは呼び出しをインライン化しません。</span><span class="sxs-lookup"><span data-stu-id="c42f9-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="c42f9-129">通常、このホストでは、浮動小数点の状態を調整する必要があるフックが必要になります。または、呼び出しによって実行されるメモリまたはロックのランタイム要求を追跡できない状態になるという通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="c42f9-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="c42f9-130">ホストが呼び出しをフックする必要がある場合、ランタイムは、 [Enterruntime](ihosttaskmanager-enterruntime-method.md)、all [veruntime](ihosttaskmanager-leaveruntime-method.md)、 [ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md)、および[ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md)の呼び出しを使用して、マネージコードとの間の遷移をホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="c42f9-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c42f9-131">要件</span><span class="sxs-lookup"><span data-stu-id="c42f9-131">Requirements</span></span>  
 <span data-ttu-id="c42f9-132">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c42f9-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c42f9-133">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c42f9-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c42f9-134">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="c42f9-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c42f9-135">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c42f9-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c42f9-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="c42f9-136">See also</span></span>

- [<span data-ttu-id="c42f9-137">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c42f9-137">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="c42f9-138">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c42f9-138">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="c42f9-139">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c42f9-139">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="c42f9-140">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c42f9-140">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
