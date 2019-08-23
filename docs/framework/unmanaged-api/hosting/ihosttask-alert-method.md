---
title: IHostTask::Alert メソッド
ms.date: 03/30/2017
api_name:
- IHostTask.Alert
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Alert
helpviewer_keywords:
- IHostTask::Alert method [.NET Framework hosting]
- Alert method, IHostTask interface [.NET Framework hosting]
ms.assetid: 5245d4b5-b6c3-48df-9cb9-8caf059f43fb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75b3fc0b1dde35e743e699d22c5766cab4cf0faf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964717"
---
# <a name="ihosttaskalert-method"></a><span data-ttu-id="84396-102">IHostTask::Alert メソッド</span><span class="sxs-lookup"><span data-stu-id="84396-102">IHostTask::Alert Method</span></span>
<span data-ttu-id="84396-103">現在の[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)インスタンスによって表されるタスクをホストがスリープ解除するように要求します。これにより、タスクを中止できます。</span><span class="sxs-lookup"><span data-stu-id="84396-103">Requests that the host wake the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance, so the task can be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84396-104">構文</span><span class="sxs-lookup"><span data-stu-id="84396-104">Syntax</span></span>  
  
```cpp  
HRESULT Alert ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="84396-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="84396-105">Return Value</span></span>  
  
|<span data-ttu-id="84396-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="84396-106">HRESULT</span></span>|<span data-ttu-id="84396-107">説明</span><span class="sxs-lookup"><span data-stu-id="84396-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="84396-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="84396-108">S_OK</span></span>|<span data-ttu-id="84396-109">メソッドが正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="84396-109">The method returned successfully.</span></span>|  
|<span data-ttu-id="84396-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="84396-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="84396-111">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="84396-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="84396-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="84396-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="84396-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="84396-113">The call timed out.</span></span>|  
|<span data-ttu-id="84396-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="84396-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="84396-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="84396-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="84396-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="84396-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="84396-117">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="84396-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="84396-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="84396-118">E_FAIL</span></span>|<span data-ttu-id="84396-119">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="84396-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="84396-120">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="84396-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="84396-121">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="84396-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84396-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="84396-122">Remarks</span></span>  
 <span data-ttu-id="84396-123">`Alert`がユーザー <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> コードから呼び出され<xref:System.Threading.Thread>た場合、または現在のに関連付けられているがシャットダウンした場合、CLRはメソッドを呼び出します。<xref:System.AppDomain></span><span class="sxs-lookup"><span data-stu-id="84396-123">The CLR calls the `Alert` method when <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is called from user code, or when the <xref:System.AppDomain> associated with the current <xref:System.Threading.Thread> shuts down.</span></span> <span data-ttu-id="84396-124">呼び出しは非同期的に行われるため、ホストはすぐに制御を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="84396-124">The host must return immediately, because the call is made asynchronously.</span></span> <span data-ttu-id="84396-125">ホストがすぐにタスクを警告できない場合は、次にアラートが通知される状態になったときに起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84396-125">If the host cannot alert the task immediately, it must wake up the next time it enters a state in which it can be alerted.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="84396-126">`Alert`は、ランタイムが WAIT_ALERTABLE の[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)値を[Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)などのメソッドに渡すタスクにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="84396-126">`Alert` affects only those tasks to which the runtime has passed a [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) value of WAIT_ALERTABLE to methods such as [Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84396-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="84396-127">Requirements</span></span>  
 <span data-ttu-id="84396-128">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="84396-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84396-129">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="84396-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84396-130">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="84396-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84396-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84396-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84396-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="84396-132">See also</span></span>

- [<span data-ttu-id="84396-133">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="84396-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="84396-134">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="84396-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="84396-135">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="84396-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="84396-136">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="84396-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
