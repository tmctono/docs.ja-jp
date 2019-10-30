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
ms.openlocfilehash: dda68041dbf4efa82a35c48702d83aa231462fef
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121381"
---
# <a name="ihosttaskjoin-method"></a><span data-ttu-id="58f04-102">IHostTask::Join メソッド</span><span class="sxs-lookup"><span data-stu-id="58f04-102">IHostTask::Join Method</span></span>
<span data-ttu-id="58f04-103">現在の[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)インスタンスによって表されるタスクが完了するまで、または指定された時間が経過するか、または[IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)が呼び出されるまで、呼び出し元のタスクをブロックします。</span><span class="sxs-lookup"><span data-stu-id="58f04-103">Blocks the calling task until the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58f04-104">構文</span><span class="sxs-lookup"><span data-stu-id="58f04-104">Syntax</span></span>  
  
```cpp  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58f04-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="58f04-105">Parameters</span></span>  
 `milliseconds`  
 <span data-ttu-id="58f04-106">からタスクの終了を待機する時間間隔 (ミリ秒単位)。</span><span class="sxs-lookup"><span data-stu-id="58f04-106">[in] The time interval, in milliseconds, to wait for the task to terminate.</span></span> <span data-ttu-id="58f04-107">タスクが終了する前にこの間隔が経過すると、呼び出し元のタスクがブロック解除されます。</span><span class="sxs-lookup"><span data-stu-id="58f04-107">If this interval elapses before the task terminates, the calling task unblocks.</span></span>  
  
 `option`  
 <span data-ttu-id="58f04-108">から[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)値の1つ。</span><span class="sxs-lookup"><span data-stu-id="58f04-108">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values.</span></span> <span data-ttu-id="58f04-109">値 WAIT_ALERTABLE は、`milliseconds` が経過する前に `Alert` が呼び出された場合に、タスクをスリープ解除するようにホストに指示します。</span><span class="sxs-lookup"><span data-stu-id="58f04-109">A value of WAIT_ALERTABLE instructs the host to wake the task if `Alert` is called before `milliseconds` elapses.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58f04-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="58f04-110">Return Value</span></span>  
  
|<span data-ttu-id="58f04-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="58f04-111">HRESULT</span></span>|<span data-ttu-id="58f04-112">説明</span><span class="sxs-lookup"><span data-stu-id="58f04-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="58f04-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="58f04-113">S_OK</span></span>|<span data-ttu-id="58f04-114">`Join` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="58f04-114">`Join` returned successfully.</span></span>|  
|<span data-ttu-id="58f04-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="58f04-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="58f04-116">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="58f04-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="58f04-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="58f04-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="58f04-118">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="58f04-118">The call timed out.</span></span>|  
|<span data-ttu-id="58f04-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="58f04-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="58f04-120">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="58f04-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="58f04-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="58f04-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="58f04-122">ブロックされたスレッドまたはファイバーが待機中であるか、または現在の `IHostTask` インスタンスがタスクに関連付けられていないときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="58f04-122">An event was canceled while a blocked thread or fiber was waiting on it, or the current `IHostTask` instance is not associated with a task.</span></span>|  
|<span data-ttu-id="58f04-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="58f04-123">E_FAIL</span></span>|<span data-ttu-id="58f04-124">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="58f04-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="58f04-125">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="58f04-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="58f04-126">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="58f04-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="58f04-127">［要件］</span><span class="sxs-lookup"><span data-stu-id="58f04-127">Requirements</span></span>  
 <span data-ttu-id="58f04-128">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58f04-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58f04-129">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="58f04-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="58f04-130">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="58f04-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58f04-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58f04-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58f04-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="58f04-132">See also</span></span>

- [<span data-ttu-id="58f04-133">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="58f04-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="58f04-134">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="58f04-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="58f04-135">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="58f04-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="58f04-136">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="58f04-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="58f04-137">WAIT_OPTION 列挙型</span><span class="sxs-lookup"><span data-stu-id="58f04-137">WAIT_OPTION Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)
