---
title: ICLRDebugManager::EndConnection メソッド
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.EndConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::EndConnection
helpviewer_keywords:
- ICLRDebugManager::EndConnection method [.NET Framework hosting]
- EndConnection method [.NET Framework hosting]
ms.assetid: 89dc7363-2f29-4eb2-8f23-fccdda6a76a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d2af6970907eb9895750ca58065b2e0cb735cea8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969402"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="e2658-102">ICLRDebugManager::EndConnection メソッド</span><span class="sxs-lookup"><span data-stu-id="e2658-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="e2658-103">タスクのリストと id とフレンドリ名の間の関連付けを削除します。</span><span class="sxs-lookup"><span data-stu-id="e2658-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2658-104">構文</span><span class="sxs-lookup"><span data-stu-id="e2658-104">Syntax</span></span>  
  
```cpp  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2658-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e2658-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="e2658-106">から接続のホスト固有の識別子と、関連付けられている共通言語ランタイム (CLR) タスクのリスト。</span><span class="sxs-lookup"><span data-stu-id="e2658-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2658-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="e2658-107">Return Value</span></span>  
  
|<span data-ttu-id="e2658-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e2658-108">HRESULT</span></span>|<span data-ttu-id="e2658-109">説明</span><span class="sxs-lookup"><span data-stu-id="e2658-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e2658-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e2658-110">S_OK</span></span>|<span data-ttu-id="e2658-111">`EndConnection`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="e2658-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="e2658-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e2658-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e2658-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="e2658-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e2658-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e2658-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e2658-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="e2658-115">The call timed out.</span></span>|  
|<span data-ttu-id="e2658-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e2658-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e2658-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="e2658-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e2658-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e2658-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e2658-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="e2658-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e2658-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e2658-120">E_FAIL</span></span>|<span data-ttu-id="e2658-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e2658-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e2658-122">メソッドから E_FAIL が返された後は、そのプロセス内で CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="e2658-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e2658-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="e2658-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e2658-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="e2658-124">E_INVALIDARG</span></span>|<span data-ttu-id="e2658-125">[Beginconnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)がを使用し`dwConnectionId`て呼び出さ`dwConnectionId`れていないか、またはが0でした。</span><span class="sxs-lookup"><span data-stu-id="e2658-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2658-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="e2658-126">Remarks</span></span>  
 <span data-ttu-id="e2658-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)には`BeginConnection`、、 [setconnectiontasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)、および`EndConnection`の3つのメソッドが用意されており、タスクリストを識別子と表示名に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e2658-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e2658-128">これら3つのメソッドは、一連のタスクごとに特定の順序で呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2658-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="e2658-129">`BeginConnection`は、新しい接続を確立するために最初に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e2658-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="e2658-130">`SetConnectionTasks`は、その接続に関連する一連のタスクを提供するために、次に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e2658-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="e2658-131">`EndConnection`は、タスク一覧と識別子とフレンドリ名の間の関連付けを削除するために最後に呼び出されます。ただし、異なる接続の呼び出しは入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e2658-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2658-132">必要条件</span><span class="sxs-lookup"><span data-stu-id="e2658-132">Requirements</span></span>  
 <span data-ttu-id="e2658-133">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2658-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2658-134">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e2658-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e2658-135">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="e2658-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2658-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2658-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2658-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2658-137">See also</span></span>

- [<span data-ttu-id="e2658-138">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e2658-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="e2658-139">ICLRDebugManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e2658-139">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="e2658-140">BeginConnection メソッド</span><span class="sxs-lookup"><span data-stu-id="e2658-140">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="e2658-141">SetConnectionTasks メソッド</span><span class="sxs-lookup"><span data-stu-id="e2658-141">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="e2658-142">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e2658-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
