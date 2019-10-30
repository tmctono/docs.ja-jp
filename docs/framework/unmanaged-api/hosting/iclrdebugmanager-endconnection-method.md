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
ms.openlocfilehash: 425f40da7a53aa4af1bd14964a8136add2f59f0b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135217"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="22ec2-102">ICLRDebugManager::EndConnection メソッド</span><span class="sxs-lookup"><span data-stu-id="22ec2-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="22ec2-103">タスクのリストと id とフレンドリ名の間の関連付けを削除します。</span><span class="sxs-lookup"><span data-stu-id="22ec2-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22ec2-104">構文</span><span class="sxs-lookup"><span data-stu-id="22ec2-104">Syntax</span></span>  
  
```cpp  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22ec2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="22ec2-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="22ec2-106">から接続のホスト固有の識別子と、関連付けられている共通言語ランタイム (CLR) タスクのリスト。</span><span class="sxs-lookup"><span data-stu-id="22ec2-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22ec2-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="22ec2-107">Return Value</span></span>  
  
|<span data-ttu-id="22ec2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="22ec2-108">HRESULT</span></span>|<span data-ttu-id="22ec2-109">説明</span><span class="sxs-lookup"><span data-stu-id="22ec2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="22ec2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="22ec2-110">S_OK</span></span>|<span data-ttu-id="22ec2-111">`EndConnection` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="22ec2-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="22ec2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="22ec2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="22ec2-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="22ec2-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="22ec2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="22ec2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="22ec2-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="22ec2-115">The call timed out.</span></span>|  
|<span data-ttu-id="22ec2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="22ec2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="22ec2-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="22ec2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="22ec2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="22ec2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="22ec2-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="22ec2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="22ec2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="22ec2-120">E_FAIL</span></span>|<span data-ttu-id="22ec2-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="22ec2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="22ec2-122">メソッドから E_FAIL が返された後は、そのプロセス内で CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="22ec2-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="22ec2-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="22ec2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="22ec2-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="22ec2-124">E_INVALIDARG</span></span>|<span data-ttu-id="22ec2-125">[Beginconnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)が `dwConnectionId`を使用して呼び出されていないか、`dwConnectionId` が0でした。</span><span class="sxs-lookup"><span data-stu-id="22ec2-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22ec2-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="22ec2-126">Remarks</span></span>  
 <span data-ttu-id="22ec2-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)には、`BeginConnection`、 [setconnectiontasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)、`EndConnection`の3つのメソッドが用意されており、タスクリストを識別子と表示名に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="22ec2-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="22ec2-128">これら3つのメソッドは、一連のタスクごとに特定の順序で呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="22ec2-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="22ec2-129">`BeginConnection` は、新しい接続を確立するために最初に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="22ec2-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="22ec2-130">この接続に関連する一連のタスクを指定するために、次に `SetConnectionTasks` が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="22ec2-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="22ec2-131">`EndConnection` は、タスク一覧と id とフレンドリ名の間の関連付けを削除するために最後に呼び出されます。ただし、異なる接続の呼び出しは入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="22ec2-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22ec2-132">［要件］</span><span class="sxs-lookup"><span data-stu-id="22ec2-132">Requirements</span></span>  
 <span data-ttu-id="22ec2-133">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22ec2-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22ec2-134">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="22ec2-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22ec2-135">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="22ec2-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22ec2-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22ec2-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22ec2-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="22ec2-137">See also</span></span>

- [<span data-ttu-id="22ec2-138">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="22ec2-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="22ec2-139">ICLRDebugManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="22ec2-139">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="22ec2-140">BeginConnection メソッド</span><span class="sxs-lookup"><span data-stu-id="22ec2-140">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="22ec2-141">SetConnectionTasks メソッド</span><span class="sxs-lookup"><span data-stu-id="22ec2-141">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="22ec2-142">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="22ec2-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
