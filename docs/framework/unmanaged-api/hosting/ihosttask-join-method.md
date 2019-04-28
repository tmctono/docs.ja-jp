---
title: IHostTask::Join メソッド
ms.date: 03/30/2017
api_name:
- IHostTask.Join
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Join
helpviewer_keywords:
- IHostTask::Join method [.NET Framework hosting]
- Join method, IHostTask interface [.NET Framework hosting]
ms.assetid: 2cffcc52-19e0-4ced-a440-fc7375078ac9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4373fc4e8a4c414c40e8d3c5547b5998b9300348
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789525"
---
# <a name="ihosttaskjoin-method"></a><span data-ttu-id="16b16-102">IHostTask::Join メソッド</span><span class="sxs-lookup"><span data-stu-id="16b16-102">IHostTask::Join Method</span></span>
<span data-ttu-id="16b16-103">現在によって表されるタスクまで呼び出し元のタスクをブロック[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)インスタンスが完了すると、指定した時間間隔が経過すると、または[ihosttask::alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="16b16-103">Blocks the calling task until the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16b16-104">構文</span><span class="sxs-lookup"><span data-stu-id="16b16-104">Syntax</span></span>  
  
```  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16b16-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="16b16-105">Parameters</span></span>  
 `milliseconds`  
 <span data-ttu-id="16b16-106">[in]タスクが終了するまで待機するミリ秒単位の時間間隔。</span><span class="sxs-lookup"><span data-stu-id="16b16-106">[in] The time interval, in milliseconds, to wait for the task to terminate.</span></span> <span data-ttu-id="16b16-107">この間隔が経過するは、タスクを終了する前に、呼び出し元のタスクがブロック解除します。</span><span class="sxs-lookup"><span data-stu-id="16b16-107">If this interval elapses before the task terminates, the calling task unblocks.</span></span>  
  
 `option`  
 <span data-ttu-id="16b16-108">[in]1 つ、 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)値。</span><span class="sxs-lookup"><span data-stu-id="16b16-108">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values.</span></span> <span data-ttu-id="16b16-109">WAIT_ALERTABLE の値が場合、タスクのスリープを解除するホストを指示`Alert`前に呼び出されます`milliseconds`が経過するとします。</span><span class="sxs-lookup"><span data-stu-id="16b16-109">A value of WAIT_ALERTABLE instructs the host to wake the task if `Alert` is called before `milliseconds` elapses.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16b16-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="16b16-110">Return Value</span></span>  
  
|<span data-ttu-id="16b16-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="16b16-111">HRESULT</span></span>|<span data-ttu-id="16b16-112">説明</span><span class="sxs-lookup"><span data-stu-id="16b16-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="16b16-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="16b16-113">S_OK</span></span>|<span data-ttu-id="16b16-114">`Join` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="16b16-114">`Join` returned successfully.</span></span>|  
|<span data-ttu-id="16b16-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="16b16-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="16b16-116">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="16b16-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="16b16-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="16b16-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="16b16-118">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="16b16-118">The call timed out.</span></span>|  
|<span data-ttu-id="16b16-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="16b16-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="16b16-120">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="16b16-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="16b16-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="16b16-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="16b16-122">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しているか、現在`IHostTask`インスタンスは、タスクに関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="16b16-122">An event was canceled while a blocked thread or fiber was waiting on it, or the current `IHostTask` instance is not associated with a task.</span></span>|  
|<span data-ttu-id="16b16-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="16b16-123">E_FAIL</span></span>|<span data-ttu-id="16b16-124">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="16b16-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="16b16-125">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="16b16-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="16b16-126">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="16b16-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="16b16-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="16b16-127">Requirements</span></span>  
 <span data-ttu-id="16b16-128">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="16b16-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16b16-129">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="16b16-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="16b16-130">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="16b16-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16b16-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16b16-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16b16-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="16b16-132">See also</span></span>

- [<span data-ttu-id="16b16-133">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16b16-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="16b16-134">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16b16-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="16b16-135">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16b16-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="16b16-136">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="16b16-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="16b16-137">WAIT_OPTION 列挙型</span><span class="sxs-lookup"><span data-stu-id="16b16-137">WAIT_OPTION Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)
