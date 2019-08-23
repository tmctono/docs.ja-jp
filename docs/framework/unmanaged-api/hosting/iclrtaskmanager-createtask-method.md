---
title: ICLRTaskManager::CreateTask メソッド
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::CreateTask
helpviewer_keywords:
- ICLRTaskManager::CreateTask method [.NET Framework hosting]
- CreateTask method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: eea570d9-2e53-4320-9ea0-eb777bf9dcf3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a89ea76d78431ae8833602588379d5150e473710
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938306"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="6fb33-102">ICLRTaskManager::CreateTask メソッド</span><span class="sxs-lookup"><span data-stu-id="6fb33-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="6fb33-103">共通言語ランタイム (CLR) によって新しいタスクが作成されることを明示的に要求します。</span><span class="sxs-lookup"><span data-stu-id="6fb33-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fb33-104">構文</span><span class="sxs-lookup"><span data-stu-id="6fb33-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fb33-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6fb33-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="6fb33-106">入出力新しく作成された[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)のアドレスへのポインター、またはタスクを作成できなかった場合は null。</span><span class="sxs-lookup"><span data-stu-id="6fb33-106">[out] A pointer to the address of a newly created [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6fb33-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="6fb33-107">Return Value</span></span>  
  
|<span data-ttu-id="6fb33-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6fb33-108">HRESULT</span></span>|<span data-ttu-id="6fb33-109">説明</span><span class="sxs-lookup"><span data-stu-id="6fb33-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6fb33-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6fb33-110">S_OK</span></span>|<span data-ttu-id="6fb33-111">メソッドが正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="6fb33-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="6fb33-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6fb33-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6fb33-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="6fb33-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6fb33-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6fb33-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6fb33-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="6fb33-115">The call timed out.</span></span>|  
|<span data-ttu-id="6fb33-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6fb33-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6fb33-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="6fb33-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6fb33-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6fb33-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6fb33-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="6fb33-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6fb33-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6fb33-120">E_FAIL</span></span>|<span data-ttu-id="6fb33-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6fb33-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6fb33-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="6fb33-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6fb33-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="6fb33-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6fb33-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6fb33-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="6fb33-125">要求されたリソースを割り当てるのに十分なメモリがありません。</span><span class="sxs-lookup"><span data-stu-id="6fb33-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6fb33-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="6fb33-126">Remarks</span></span>  
 <span data-ttu-id="6fb33-127">CLR は、初期化時、ユーザーコードが<xref:System.Threading>名前空間の型を使用してスレッドを作成するとき、またはスレッドプールのサイズが増加したときに、新しいタスクを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="6fb33-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="6fb33-128">また、アンマネージコードがマネージ関数を呼び出す場合にも、タスクが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6fb33-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="6fb33-129">`CreateTask`CLR によって新しいタスクが作成されることをホストが明示的に要求できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6fb33-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="6fb33-130">たとえば、ホストはこのメソッドを呼び出して、データ構造を事前に初期化できます。</span><span class="sxs-lookup"><span data-stu-id="6fb33-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6fb33-131">新しいタスクは中断状態で返され、ホストが明示的に[IHostTask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)を呼び出すまで中断されたままになります。</span><span class="sxs-lookup"><span data-stu-id="6fb33-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fb33-132">必要条件</span><span class="sxs-lookup"><span data-stu-id="6fb33-132">Requirements</span></span>  
 <span data-ttu-id="6fb33-133">**・**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fb33-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fb33-134">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6fb33-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6fb33-135">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="6fb33-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6fb33-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fb33-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fb33-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fb33-137">See also</span></span>

- [<span data-ttu-id="6fb33-138">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fb33-138">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="6fb33-139">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fb33-139">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="6fb33-140">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fb33-140">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="6fb33-141">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fb33-141">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
