---
title: ICLRDebugManager::SetConnectionTasks メソッド
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetConnectionTasks
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetConnectionTasks
helpviewer_keywords:
- SetConnectionTasks method [.NET Framework hosting]
- ICLRDebugManager::SetConnectionTasks method [.NET Framework hosting]
ms.assetid: b38bbc9a-872c-41a9-b8c3-ca011d25456a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aeb66e6c5b8ce6312ec9fad65d79e32a4fbe0576
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773094"
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a><span data-ttu-id="02e39-102">ICLRDebugManager::SetConnectionTasks メソッド</span><span class="sxs-lookup"><span data-stu-id="02e39-102">ICLRDebugManager::SetConnectionTasks Method</span></span>
<span data-ttu-id="02e39-103">リストを関連付けます[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)識別子とフレンドリ名を持つインスタンス。</span><span class="sxs-lookup"><span data-stu-id="02e39-103">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02e39-104">構文</span><span class="sxs-lookup"><span data-stu-id="02e39-104">Syntax</span></span>  
  
```cpp  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02e39-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="02e39-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="02e39-106">[in]関連付ける接続のホスト固有の識別子、`ppCLRTask`配列。</span><span class="sxs-lookup"><span data-stu-id="02e39-106">[in] The host-specific identifier for the connection with which to associate the `ppCLRTask` array.</span></span>  
  
 `dwCount`  
 <span data-ttu-id="02e39-107">[in]メンバー数`ppCLRTask`します。</span><span class="sxs-lookup"><span data-stu-id="02e39-107">[in] The number of members of `ppCLRTask`.</span></span> <span data-ttu-id="02e39-108">この番号は 0 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="02e39-108">This number must be greater than zero.</span></span>  
  
 `ppCLRTask`  
 <span data-ttu-id="02e39-109">[in]配列の`ICLRTask`ポインターで識別される、接続に関連付ける`id`します。</span><span class="sxs-lookup"><span data-stu-id="02e39-109">[in] An array of `ICLRTask` pointers to associate with the connection identified by `id`.</span></span> <span data-ttu-id="02e39-110">この配列は、少なくとも 1 つのメンバーを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="02e39-110">This array must contain at least one member.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02e39-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="02e39-111">Return Value</span></span>  
  
|<span data-ttu-id="02e39-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="02e39-112">HRESULT</span></span>|<span data-ttu-id="02e39-113">説明</span><span class="sxs-lookup"><span data-stu-id="02e39-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02e39-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="02e39-114">S_OK</span></span>|<span data-ttu-id="02e39-115">`SetConnectionTasks` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="02e39-115">`SetConnectionTasks` returned successfully.</span></span>|  
|<span data-ttu-id="02e39-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="02e39-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="02e39-117">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="02e39-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="02e39-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="02e39-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="02e39-119">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="02e39-119">The call timed out.</span></span>|  
|<span data-ttu-id="02e39-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="02e39-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="02e39-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="02e39-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="02e39-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="02e39-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="02e39-123">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="02e39-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="02e39-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="02e39-124">E_FAIL</span></span>|<span data-ttu-id="02e39-125">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="02e39-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="02e39-126">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="02e39-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="02e39-127">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="02e39-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="02e39-128">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="02e39-128">E_INVALIDARG</span></span>|<span data-ttu-id="02e39-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)が呼び出されていないのは、この値を使用して`id`、または`dwCount`または`id`はゼロ、または 1 つの要素の`ppCLRTask`が null です。</span><span class="sxs-lookup"><span data-stu-id="02e39-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) has not been called using this value of `id`, or `dwCount` or `id` is zero, or one of the elements of `ppCLRTask` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02e39-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="02e39-130">Remarks</span></span>  
 <span data-ttu-id="02e39-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) 3 つのメソッドを提供します`BeginConnection`、 `SetConnectionTasks`、および[EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)識別子とフレンドリ名をタスク一覧に関連付けるためです。</span><span class="sxs-lookup"><span data-stu-id="02e39-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, `SetConnectionTasks`, and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="02e39-132">タスクのセットごとに特定の順序では、これら 3 つのメソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="02e39-132">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="02e39-133">`BeginConnection` 新しい接続を確立するためが最初に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="02e39-133">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="02e39-134">`SetConnectionTasks` その接続に関連するタスクのセットを提供するが次に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="02e39-134">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="02e39-135">`EndConnection` タスク一覧と、識別子とフレンドリ名の間の関連付けを削除する最後に呼び出されます。ただし、異なる接続への呼び出しは入れ子にできます。</span><span class="sxs-lookup"><span data-stu-id="02e39-135">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02e39-136">必要条件</span><span class="sxs-lookup"><span data-stu-id="02e39-136">Requirements</span></span>  
 <span data-ttu-id="02e39-137">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02e39-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02e39-138">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="02e39-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="02e39-139">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="02e39-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02e39-140">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02e39-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02e39-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="02e39-141">See also</span></span>

- [<span data-ttu-id="02e39-142">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="02e39-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="02e39-143">ICLRDebugManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="02e39-143">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="02e39-144">BeginConnection メソッド</span><span class="sxs-lookup"><span data-stu-id="02e39-144">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="02e39-145">EndConnection メソッド</span><span class="sxs-lookup"><span data-stu-id="02e39-145">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="02e39-146">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="02e39-146">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
