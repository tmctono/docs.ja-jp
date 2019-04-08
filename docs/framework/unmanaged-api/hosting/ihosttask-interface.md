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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb15da31d91565d49df83099045f742866eebcaa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081503"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="8a64a-102">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a64a-102">IHostTask Interface</span></span>
<span data-ttu-id="8a64a-103">共通言語ランタイム (CLR) にタスクを管理するホストと通信できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="8a64a-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a64a-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="8a64a-104">Methods</span></span>  
  
|<span data-ttu-id="8a64a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="8a64a-105">Method</span></span>|<span data-ttu-id="8a64a-106">説明</span><span class="sxs-lookup"><span data-stu-id="8a64a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a64a-107">Alert メソッド</span><span class="sxs-lookup"><span data-stu-id="8a64a-107">Alert Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|<span data-ttu-id="8a64a-108">要求のホストが現在によって表されるタスクを wake`IHostTask`のインスタンスのため、タスクが中止されることができます。</span><span class="sxs-lookup"><span data-stu-id="8a64a-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="8a64a-109">GetPriority メソッド</span><span class="sxs-lookup"><span data-stu-id="8a64a-109">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|<span data-ttu-id="8a64a-110">現在のタスクのスレッド優先度レベルを取得`IHostTask`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="8a64a-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="8a64a-111">Join メソッド</span><span class="sxs-lookup"><span data-stu-id="8a64a-111">Join Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|<span data-ttu-id="8a64a-112">現在によって表されるタスクまで呼び出し元のタスクをブロック`IHostTask`インスタンスが完了すると、指定した時間間隔が経過すると、または[ihosttask::alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8a64a-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="8a64a-113">SetCLRTask メソッド</span><span class="sxs-lookup"><span data-stu-id="8a64a-113">SetCLRTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|<span data-ttu-id="8a64a-114">関連付けます、 [ICLRTask インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)を現在`IHostTask`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="8a64a-114">Associates an [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="8a64a-115">SetPriority メソッド</span><span class="sxs-lookup"><span data-stu-id="8a64a-115">SetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|<span data-ttu-id="8a64a-116">現在によって表されるタスクのスレッドの優先順位を変更するホストの要求レベル`IHostTask`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="8a64a-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="8a64a-117">Start メソッド</span><span class="sxs-lookup"><span data-stu-id="8a64a-117">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|<span data-ttu-id="8a64a-118">ホストが現在によって表されるタスクを移動要求`IHostTask`インスタンス、中断状態からコードを実行できる、ライブ状態にします。</span><span class="sxs-lookup"><span data-stu-id="8a64a-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a64a-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="8a64a-119">Remarks</span></span>  
 <span data-ttu-id="8a64a-120">CLR によって定義されたメソッドを呼び出し、`IHostTask`タスクを開始するにはそのスレッドの優先度をレベルの設定。</span><span class="sxs-lookup"><span data-stu-id="8a64a-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a64a-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="8a64a-121">Requirements</span></span>  
 <span data-ttu-id="8a64a-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a64a-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a64a-123">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8a64a-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a64a-124">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="8a64a-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="8a64a-125">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="8a64a-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8a64a-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a64a-126">See also</span></span>

- [<span data-ttu-id="8a64a-127">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a64a-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="8a64a-128">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a64a-128">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8a64a-129">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a64a-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="8a64a-130">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a64a-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
