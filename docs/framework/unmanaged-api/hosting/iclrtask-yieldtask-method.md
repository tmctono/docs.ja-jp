---
title: ICLRTask::YieldTask メソッド
ms.date: 03/30/2017
api_name:
- ICLRTask.YieldTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::YieldTask
helpviewer_keywords:
- ICLRTask::YieldTask method [.NET Framework hosting]
- YieldTask method [.NET Framework hosting]
ms.assetid: b8eb4095-3a8f-4be3-9446-63e9893dce7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6fde9586c1b3736b5db2c4814058dd23713dd34d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770333"
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="34bd7-102">ICLRTask::YieldTask メソッド</span><span class="sxs-lookup"><span data-stu-id="34bd7-102">ICLRTask::YieldTask Method</span></span>
<span data-ttu-id="34bd7-103">共通言語ランタイム (CLR) で確保、タスクを開始する要求を現在[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンスが表す、およびプロセッサ時間をその他のタスクを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="34bd7-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34bd7-104">構文</span><span class="sxs-lookup"><span data-stu-id="34bd7-104">Syntax</span></span>  
  
```cpp  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="34bd7-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="34bd7-105">Return Value</span></span>  
  
|<span data-ttu-id="34bd7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="34bd7-106">HRESULT</span></span>|<span data-ttu-id="34bd7-107">説明</span><span class="sxs-lookup"><span data-stu-id="34bd7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="34bd7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="34bd7-108">S_OK</span></span>|<span data-ttu-id="34bd7-109">`YieldTask` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="34bd7-109">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="34bd7-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="34bd7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="34bd7-111">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="34bd7-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="34bd7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="34bd7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="34bd7-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="34bd7-113">The call timed out.</span></span>|  
|<span data-ttu-id="34bd7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="34bd7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="34bd7-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="34bd7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="34bd7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="34bd7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="34bd7-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="34bd7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="34bd7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="34bd7-118">E_FAIL</span></span>|<span data-ttu-id="34bd7-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="34bd7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="34bd7-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="34bd7-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="34bd7-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="34bd7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34bd7-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="34bd7-122">Remarks</span></span>  
 <span data-ttu-id="34bd7-123">ホストは`YieldTask`他のタスクまたはプロセスのプロセッサ リソースを要求します。</span><span class="sxs-lookup"><span data-stu-id="34bd7-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="34bd7-124">このメソッドは、主に CPU 時間を断念する実行時間の長いコードを許可します。</span><span class="sxs-lookup"><span data-stu-id="34bd7-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="34bd7-125">ランタイムが、タスクを配置しようとしています。 を現在`ICLRTask`インスタンスが表す状態が、処理時間を生成することができますが、成功の保証はありません。</span><span class="sxs-lookup"><span data-stu-id="34bd7-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34bd7-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="34bd7-126">Requirements</span></span>  
 <span data-ttu-id="34bd7-127">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="34bd7-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34bd7-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="34bd7-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="34bd7-129">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="34bd7-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="34bd7-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34bd7-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34bd7-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="34bd7-131">See also</span></span>

- [<span data-ttu-id="34bd7-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34bd7-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="34bd7-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34bd7-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="34bd7-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34bd7-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="34bd7-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34bd7-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
