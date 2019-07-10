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
ms.openlocfilehash: 21e77b781c382cbcab79a93a0c58edd4f07690b2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770402"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="3e9a8-102">ICLRTask::SwitchOut メソッド</span><span class="sxs-lookup"><span data-stu-id="3e9a8-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="3e9a8-103">タスクが現在によって表される共通言語ランタイム (CLR) に通知[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンスは操作可能な状態ではありません。</span><span class="sxs-lookup"><span data-stu-id="3e9a8-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e9a8-104">構文</span><span class="sxs-lookup"><span data-stu-id="3e9a8-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3e9a8-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="3e9a8-105">Return Value</span></span>  
  
|<span data-ttu-id="3e9a8-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3e9a8-106">HRESULT</span></span>|<span data-ttu-id="3e9a8-107">説明</span><span class="sxs-lookup"><span data-stu-id="3e9a8-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3e9a8-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3e9a8-108">S_OK</span></span>|<span data-ttu-id="3e9a8-109">`SwitchOut` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="3e9a8-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="3e9a8-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3e9a8-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3e9a8-111">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="3e9a8-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3e9a8-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3e9a8-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3e9a8-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="3e9a8-113">The call timed out.</span></span>|  
|<span data-ttu-id="3e9a8-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3e9a8-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3e9a8-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="3e9a8-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3e9a8-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3e9a8-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3e9a8-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="3e9a8-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3e9a8-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3e9a8-118">E_FAIL</span></span>|<span data-ttu-id="3e9a8-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3e9a8-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3e9a8-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="3e9a8-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3e9a8-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="3e9a8-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e9a8-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="3e9a8-122">Remarks</span></span>  
 <span data-ttu-id="3e9a8-123">ホストは`SwitchOut`CLR に通知するタスクを実行するが一時的に停止しましたが、現在`ICLRTask`インスタンスが表す、およびタスクのスケジュールを変更します。</span><span class="sxs-lookup"><span data-stu-id="3e9a8-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e9a8-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="3e9a8-124">Requirements</span></span>  
 <span data-ttu-id="3e9a8-125">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e9a8-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e9a8-126">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3e9a8-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3e9a8-127">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="3e9a8-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e9a8-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e9a8-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e9a8-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e9a8-129">See also</span></span>

- [<span data-ttu-id="3e9a8-130">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e9a8-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="3e9a8-131">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e9a8-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="3e9a8-132">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e9a8-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="3e9a8-133">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e9a8-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
