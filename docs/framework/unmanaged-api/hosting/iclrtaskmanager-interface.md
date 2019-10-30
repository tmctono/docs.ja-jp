---
title: ICLRTaskManager インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager
helpviewer_keywords:
- ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type:
- apiref
ms.openlocfilehash: e25a6a03a836b8b4964b8260c974c8e8d8d9998d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092188"
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="377e1-102">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="377e1-102">ICLRTaskManager Interface</span></span>
<span data-ttu-id="377e1-103">ホストが、共通言語ランタイム (CLR) が新しいタスクを作成し、現在実行中のタスクを取得し、タスクの地理的言語とカルチャを設定することを明示的に要求するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="377e1-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="377e1-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="377e1-104">Methods</span></span>  
  
|<span data-ttu-id="377e1-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="377e1-105">Method</span></span>|<span data-ttu-id="377e1-106">説明</span><span class="sxs-lookup"><span data-stu-id="377e1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="377e1-107">CreateTask メソッド</span><span class="sxs-lookup"><span data-stu-id="377e1-107">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|<span data-ttu-id="377e1-108">CLR が新しい[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンスを作成することを明示的に要求します。</span><span class="sxs-lookup"><span data-stu-id="377e1-108">Requests explicitly that the CLR create a new [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="377e1-109">GetCurrentTask メソッド</span><span class="sxs-lookup"><span data-stu-id="377e1-109">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="377e1-110">現在実行中のタスクを表す `ICLRTask` インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="377e1-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="377e1-111">GetCurrentTaskType メソッド</span><span class="sxs-lookup"><span data-stu-id="377e1-111">GetCurrentTaskType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="377e1-112">現在実行中のタスクの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="377e1-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="377e1-113">SetLocale メソッド</span><span class="sxs-lookup"><span data-stu-id="377e1-113">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="377e1-114">現在実行中のタスクのロケール識別子がホストによって変更されたことを CLR に通知します。</span><span class="sxs-lookup"><span data-stu-id="377e1-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="377e1-115">SetUILocale メソッド</span><span class="sxs-lookup"><span data-stu-id="377e1-115">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="377e1-116">現在実行中のタスクのユーザーインターフェイスのロケール識別子がホストによって変更されたことを、共通言語ランタイムに通知します。</span><span class="sxs-lookup"><span data-stu-id="377e1-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="377e1-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="377e1-117">Remarks</span></span>  
 <span data-ttu-id="377e1-118">ホスト環境で実行されている各タスクは、ホスト側 ( [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)のインスタンス) と CLR 側 ( [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)のインスタンス) の両方で表現されます。</span><span class="sxs-lookup"><span data-stu-id="377e1-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span></span> <span data-ttu-id="377e1-119">ホストまたは CLR がタスクの作成を開始することはできますが、ホストと CLR の間でタスクに関して正常に通信できるように、ホスト側表現を対応する CLR 側表現に関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="377e1-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="377e1-120">マネージコードをオペレーティングシステムのスレッドで実行するには、2つのオブジェクトを作成してインスタンス化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="377e1-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="377e1-121">［要件］</span><span class="sxs-lookup"><span data-stu-id="377e1-121">Requirements</span></span>  
 <span data-ttu-id="377e1-122">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="377e1-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="377e1-123">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="377e1-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="377e1-124">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="377e1-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="377e1-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="377e1-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="377e1-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="377e1-126">See also</span></span>

- [<span data-ttu-id="377e1-127">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="377e1-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="377e1-128">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="377e1-128">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="377e1-129">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="377e1-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="377e1-130">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="377e1-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
