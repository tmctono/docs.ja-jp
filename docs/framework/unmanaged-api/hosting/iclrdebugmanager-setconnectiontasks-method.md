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
ms.openlocfilehash: 85db4247ebe4a488f7907e195bb0f25f72d87e9b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951353"
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a><span data-ttu-id="6be5a-102">ICLRDebugManager::SetConnectionTasks メソッド</span><span class="sxs-lookup"><span data-stu-id="6be5a-102">ICLRDebugManager::SetConnectionTasks Method</span></span>
<span data-ttu-id="6be5a-103">[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンスのリストを識別子とフレンドリ名に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="6be5a-103">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6be5a-104">構文</span><span class="sxs-lookup"><span data-stu-id="6be5a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6be5a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6be5a-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="6be5a-106">から`ppCLRTask`配列を関連付ける接続のホスト固有の識別子。</span><span class="sxs-lookup"><span data-stu-id="6be5a-106">[in] The host-specific identifier for the connection with which to associate the `ppCLRTask` array.</span></span>  
  
 `dwCount`  
 <span data-ttu-id="6be5a-107">からの`ppCLRTask`メンバーの数。</span><span class="sxs-lookup"><span data-stu-id="6be5a-107">[in] The number of members of `ppCLRTask`.</span></span> <span data-ttu-id="6be5a-108">この値は0より大きくなければなりません。</span><span class="sxs-lookup"><span data-stu-id="6be5a-108">This number must be greater than zero.</span></span>  
  
 `ppCLRTask`  
 <span data-ttu-id="6be5a-109">からによって`ICLRTask` `id`識別される接続に関連付けるポインターの配列。</span><span class="sxs-lookup"><span data-stu-id="6be5a-109">[in] An array of `ICLRTask` pointers to associate with the connection identified by `id`.</span></span> <span data-ttu-id="6be5a-110">この配列には、少なくとも1つのメンバーが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6be5a-110">This array must contain at least one member.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6be5a-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="6be5a-111">Return Value</span></span>  
  
|<span data-ttu-id="6be5a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6be5a-112">HRESULT</span></span>|<span data-ttu-id="6be5a-113">説明</span><span class="sxs-lookup"><span data-stu-id="6be5a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6be5a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="6be5a-114">S_OK</span></span>|<span data-ttu-id="6be5a-115">`SetConnectionTasks`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="6be5a-115">`SetConnectionTasks` returned successfully.</span></span>|  
|<span data-ttu-id="6be5a-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6be5a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6be5a-117">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="6be5a-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6be5a-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6be5a-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6be5a-119">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="6be5a-119">The call timed out.</span></span>|  
|<span data-ttu-id="6be5a-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6be5a-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6be5a-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="6be5a-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6be5a-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6be5a-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6be5a-123">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="6be5a-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6be5a-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6be5a-124">E_FAIL</span></span>|<span data-ttu-id="6be5a-125">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6be5a-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6be5a-126">メソッドから E_FAIL が返された後は、そのプロセス内で CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="6be5a-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6be5a-127">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="6be5a-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6be5a-128">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="6be5a-128">E_INVALIDARG</span></span>|<span data-ttu-id="6be5a-129">[Beginconnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)が`id`この値`dwCount`を使用して呼び出されてい`id`ないか、またはが0である`ppCLRTask`か、またはの要素の1つが null です。</span><span class="sxs-lookup"><span data-stu-id="6be5a-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) has not been called using this value of `id`, or `dwCount` or `id` is zero, or one of the elements of `ppCLRTask` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6be5a-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="6be5a-130">Remarks</span></span>  
 <span data-ttu-id="6be5a-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)では、、 `BeginConnection`、 `SetConnectionTasks`および[endconnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)という3つのメソッドを使用して、タスクリストを識別子とフレンドリ名に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="6be5a-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, `SetConnectionTasks`, and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6be5a-132">これら3つのメソッドは、一連のタスクごとに特定の順序で呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6be5a-132">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="6be5a-133">`BeginConnection`は、新しい接続を確立するために最初に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6be5a-133">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="6be5a-134">`SetConnectionTasks`は、その接続に関連する一連のタスクを提供するために、次に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6be5a-134">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="6be5a-135">`EndConnection`は、タスク一覧と識別子とフレンドリ名の間の関連付けを削除するために最後に呼び出されます。ただし、異なる接続の呼び出しは入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6be5a-135">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6be5a-136">必要条件</span><span class="sxs-lookup"><span data-stu-id="6be5a-136">Requirements</span></span>  
 <span data-ttu-id="6be5a-137">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6be5a-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6be5a-138">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6be5a-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6be5a-139">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="6be5a-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6be5a-140">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6be5a-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6be5a-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="6be5a-141">See also</span></span>

- [<span data-ttu-id="6be5a-142">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6be5a-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="6be5a-143">ICLRDebugManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6be5a-143">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="6be5a-144">BeginConnection メソッド</span><span class="sxs-lookup"><span data-stu-id="6be5a-144">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="6be5a-145">EndConnection メソッド</span><span class="sxs-lookup"><span data-stu-id="6be5a-145">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="6be5a-146">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6be5a-146">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
