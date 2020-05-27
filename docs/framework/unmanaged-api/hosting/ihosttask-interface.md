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
ms.openlocfilehash: f8f476f681764a46700dd5ec83c8f9b2739f18f6
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842492"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="318db-102">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="318db-102">IHostTask Interface</span></span>
<span data-ttu-id="318db-103">共通言語ランタイム (CLR) がホストと通信してタスクを管理できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="318db-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="318db-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="318db-104">Methods</span></span>  
  
|<span data-ttu-id="318db-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="318db-105">Method</span></span>|<span data-ttu-id="318db-106">説明</span><span class="sxs-lookup"><span data-stu-id="318db-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="318db-107">Alert メソッド</span><span class="sxs-lookup"><span data-stu-id="318db-107">Alert Method</span></span>](ihosttask-alert-method.md)|<span data-ttu-id="318db-108">現在のインスタンスによって表されるタスクをホストがスリープ解除する `IHostTask` ように要求します。これにより、タスクを中止できます。</span><span class="sxs-lookup"><span data-stu-id="318db-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="318db-109">GetPriority メソッド</span><span class="sxs-lookup"><span data-stu-id="318db-109">GetPriority Method</span></span>](ihosttask-getpriority-method.md)|<span data-ttu-id="318db-110">現在のインスタンスによって表されるタスクのスレッド優先度レベルを取得し `IHostTask` ます。</span><span class="sxs-lookup"><span data-stu-id="318db-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="318db-111">Join メソッド</span><span class="sxs-lookup"><span data-stu-id="318db-111">Join Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|<span data-ttu-id="318db-112">現在のインスタンスによって表されるタスクが `IHostTask` 完了するか、指定された時間が経過するか、または[IHostTask:: Alert](ihosttask-alert-method.md)が呼び出されるまで、呼び出し元のタスクをブロックします。</span><span class="sxs-lookup"><span data-stu-id="318db-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="318db-113">SetCLRTask メソッド</span><span class="sxs-lookup"><span data-stu-id="318db-113">SetCLRTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|<span data-ttu-id="318db-114">[ICLRTask インターフェイス](iclrtask-interface.md)インスタンスを現在のインスタンスに関連付け `IHostTask` ます。</span><span class="sxs-lookup"><span data-stu-id="318db-114">Associates an [ICLRTask Interface](iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="318db-115">SetPriority メソッド</span><span class="sxs-lookup"><span data-stu-id="318db-115">SetPriority Method</span></span>](ihosttask-setpriority-method.md)|<span data-ttu-id="318db-116">現在のインスタンスによって表されるタスクのスレッドの優先度レベルをホストが調整するように要求 `IHostTask` します。</span><span class="sxs-lookup"><span data-stu-id="318db-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="318db-117">Start メソッド</span><span class="sxs-lookup"><span data-stu-id="318db-117">Start Method</span></span>](ihosttask-start-method.md)|<span data-ttu-id="318db-118">現在のインスタンスによって表されるタスクを中断状態からライブ状態に移行するようホストに要求し `IHostTask` ます。このとき、コードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="318db-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="318db-119">コメント</span><span class="sxs-lookup"><span data-stu-id="318db-119">Remarks</span></span>  
 <span data-ttu-id="318db-120">CLR は、によって定義されたメソッドを呼び出して、 `IHostTask` タスクを開始したり、スレッドの優先度レベルを設定したりします。</span><span class="sxs-lookup"><span data-stu-id="318db-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="318db-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="318db-121">Requirements</span></span>  
 <span data-ttu-id="318db-122">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="318db-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="318db-123">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="318db-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="318db-124">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="318db-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="318db-125">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="318db-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="318db-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="318db-126">See also</span></span>

- [<span data-ttu-id="318db-127">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="318db-127">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="318db-128">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="318db-128">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="318db-129">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="318db-129">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="318db-130">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="318db-130">Hosting Interfaces</span></span>](hosting-interfaces.md)
