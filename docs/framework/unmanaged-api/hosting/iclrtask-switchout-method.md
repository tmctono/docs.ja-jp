---
title: ICLRTask::SwitchOut メソッド
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchOut
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a215189461bd22011462842bf02ff6c0109119fa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763478"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="22732-102">ICLRTask::SwitchOut メソッド</span><span class="sxs-lookup"><span data-stu-id="22732-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="22732-103">タスクが現在によって表される共通言語ランタイム (CLR) に通知[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンスは操作可能な状態ではありません。</span><span class="sxs-lookup"><span data-stu-id="22732-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22732-104">構文</span><span class="sxs-lookup"><span data-stu-id="22732-104">Syntax</span></span>  
  
```  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="22732-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="22732-105">Return Value</span></span>  
  
|<span data-ttu-id="22732-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="22732-106">HRESULT</span></span>|<span data-ttu-id="22732-107">説明</span><span class="sxs-lookup"><span data-stu-id="22732-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="22732-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="22732-108">S_OK</span></span>|<span data-ttu-id="22732-109">`SwitchOut` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="22732-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="22732-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="22732-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="22732-111">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="22732-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="22732-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="22732-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="22732-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="22732-113">The call timed out.</span></span>|  
|<span data-ttu-id="22732-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="22732-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="22732-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="22732-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="22732-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="22732-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="22732-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="22732-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="22732-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="22732-118">E_FAIL</span></span>|<span data-ttu-id="22732-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="22732-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="22732-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="22732-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="22732-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="22732-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22732-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="22732-122">Remarks</span></span>  
 <span data-ttu-id="22732-123">ホストは`SwitchOut`CLR に通知するタスクを実行するが一時的に停止しましたが、現在`ICLRTask`インスタンスが表す、およびタスクのスケジュールを変更します。</span><span class="sxs-lookup"><span data-stu-id="22732-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22732-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="22732-124">Requirements</span></span>  
 <span data-ttu-id="22732-125">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="22732-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22732-126">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="22732-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22732-127">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="22732-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22732-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22732-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22732-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="22732-129">See also</span></span>

- [<span data-ttu-id="22732-130">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="22732-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="22732-131">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="22732-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="22732-132">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="22732-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="22732-133">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="22732-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
