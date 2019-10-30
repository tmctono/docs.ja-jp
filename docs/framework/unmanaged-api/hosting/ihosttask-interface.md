---
title: IHostTask インターフェイス
ms.date: 03/30/2017
api_name:
- IHostTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask
helpviewer_keywords:
- IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type:
- apiref
ms.openlocfilehash: 18dfee606f3d41229aa58a5b4bb9380b87c4efa5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121395"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="3342d-102">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3342d-102">IHostTask Interface</span></span>
<span data-ttu-id="3342d-103">共通言語ランタイム (CLR) がホストと通信してタスクを管理できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="3342d-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3342d-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="3342d-104">Methods</span></span>  
  
|<span data-ttu-id="3342d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3342d-105">Method</span></span>|<span data-ttu-id="3342d-106">説明</span><span class="sxs-lookup"><span data-stu-id="3342d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3342d-107">Alert メソッド</span><span class="sxs-lookup"><span data-stu-id="3342d-107">Alert Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|<span data-ttu-id="3342d-108">現在の `IHostTask` インスタンスによって表されるタスクをホストがスリープ解除するように要求します。これにより、タスクを中止できます。</span><span class="sxs-lookup"><span data-stu-id="3342d-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="3342d-109">GetPriority メソッド</span><span class="sxs-lookup"><span data-stu-id="3342d-109">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|<span data-ttu-id="3342d-110">現在の `IHostTask` インスタンスによって表されるタスクのスレッド優先度レベルを取得します。</span><span class="sxs-lookup"><span data-stu-id="3342d-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="3342d-111">Join メソッド</span><span class="sxs-lookup"><span data-stu-id="3342d-111">Join Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|<span data-ttu-id="3342d-112">現在の `IHostTask` インスタンスによって表されるタスクが完了するまで、または指定された時間間隔が経過するか、または[IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)が呼び出されるまで、呼び出し元のタスクをブロックします。</span><span class="sxs-lookup"><span data-stu-id="3342d-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="3342d-113">SetCLRTask メソッド</span><span class="sxs-lookup"><span data-stu-id="3342d-113">SetCLRTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|<span data-ttu-id="3342d-114">[ICLRTask インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンスを現在の `IHostTask` インスタンスに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="3342d-114">Associates an [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="3342d-115">SetPriority メソッド</span><span class="sxs-lookup"><span data-stu-id="3342d-115">SetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|<span data-ttu-id="3342d-116">現在の `IHostTask` インスタンスによって表されるタスクのスレッドの優先度レベルをホストが調整するように要求します。</span><span class="sxs-lookup"><span data-stu-id="3342d-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="3342d-117">Start メソッド</span><span class="sxs-lookup"><span data-stu-id="3342d-117">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|<span data-ttu-id="3342d-118">現在の `IHostTask` インスタンスによって表されるタスクを中断状態からライブ状態に移行するようホストに要求します。このとき、コードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3342d-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3342d-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="3342d-119">Remarks</span></span>  
 <span data-ttu-id="3342d-120">CLR は、`IHostTask` によって定義されたメソッドを呼び出して、タスクを開始したり、スレッドの優先度レベルを設定したりします。</span><span class="sxs-lookup"><span data-stu-id="3342d-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3342d-121">［要件］</span><span class="sxs-lookup"><span data-stu-id="3342d-121">Requirements</span></span>  
 <span data-ttu-id="3342d-122">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3342d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3342d-123">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3342d-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3342d-124">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="3342d-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3342d-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3342d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3342d-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="3342d-126">See also</span></span>

- [<span data-ttu-id="3342d-127">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3342d-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="3342d-128">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3342d-128">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="3342d-129">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3342d-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="3342d-130">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3342d-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
