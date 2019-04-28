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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 19ef7cb78791496de76e5741f8254ee88563c776
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763374"
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="27599-102">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27599-102">ICLRTaskManager Interface</span></span>
<span data-ttu-id="27599-103">共通言語ランタイム (CLR) にホストを明示的に要求を許可するメソッドが新しいタスクを作成し、現在実行中のタスクを取得および地理的な言語とタスクのカルチャ設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="27599-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="27599-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="27599-104">Methods</span></span>  
  
|<span data-ttu-id="27599-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="27599-105">Method</span></span>|<span data-ttu-id="27599-106">説明</span><span class="sxs-lookup"><span data-stu-id="27599-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="27599-107">CreateTask メソッド</span><span class="sxs-lookup"><span data-stu-id="27599-107">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|<span data-ttu-id="27599-108">CLR を新規に作成を明示的に要求[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="27599-108">Requests explicitly that the CLR create a new [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="27599-109">GetCurrentTask メソッド</span><span class="sxs-lookup"><span data-stu-id="27599-109">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="27599-110">取得、`ICLRTask`現在実行しているタスクを表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="27599-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="27599-111">GetCurrentTaskType メソッド</span><span class="sxs-lookup"><span data-stu-id="27599-111">GetCurrentTaskType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="27599-112">現在実行しているタスクの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="27599-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="27599-113">SetLocale メソッド</span><span class="sxs-lookup"><span data-stu-id="27599-113">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="27599-114">ホストが現在実行中のタスクのロケール識別子を変更したことを CLR に通知します。</span><span class="sxs-lookup"><span data-stu-id="27599-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="27599-115">SetUILocale メソッド</span><span class="sxs-lookup"><span data-stu-id="27599-115">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="27599-116">ホストが現在実行中のタスクのユーザー インターフェイスのロケール識別子を変更したことを共通言語ランタイムに通知します。</span><span class="sxs-lookup"><span data-stu-id="27599-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27599-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="27599-117">Remarks</span></span>  
 <span data-ttu-id="27599-118">ホスト環境で実行されている各タスクは、ホスト側の両方の表現を持つ (インスタンスの[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) と CLR 側 (インスタンスの[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md))。</span><span class="sxs-lookup"><span data-stu-id="27599-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span></span> <span data-ttu-id="27599-119">ホストまたは CLR には、タスクの作成を開始できますが、ホスト側の表現は、ホストとタスクに関する CLR の間の通信を成功させるのに対応する CLR 側表現を関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="27599-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="27599-120">2 つのオブジェクトは作成され、オペレーティング システム スレッドで実行するマネージ コードにインスタンス化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27599-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27599-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="27599-121">Requirements</span></span>  
 <span data-ttu-id="27599-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="27599-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27599-123">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="27599-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="27599-124">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="27599-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27599-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27599-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27599-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="27599-126">See also</span></span>

- [<span data-ttu-id="27599-127">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27599-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="27599-128">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27599-128">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="27599-129">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27599-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="27599-130">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27599-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
