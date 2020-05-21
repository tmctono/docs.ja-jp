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
ms.openlocfilehash: 9829f57da911b43626516284e4858adc4139a3ca
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762878"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="c75b8-102">ICLRTaskManager::CreateTask メソッド</span><span class="sxs-lookup"><span data-stu-id="c75b8-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="c75b8-103">共通言語ランタイム (CLR) によって新しいタスクが作成されることを明示的に要求します。</span><span class="sxs-lookup"><span data-stu-id="c75b8-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c75b8-104">構文</span><span class="sxs-lookup"><span data-stu-id="c75b8-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c75b8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c75b8-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="c75b8-106">入出力新しく作成された[ICLRTask](iclrtask-interface.md)のアドレスへのポインター、またはタスクを作成できなかった場合は null。</span><span class="sxs-lookup"><span data-stu-id="c75b8-106">[out] A pointer to the address of a newly created [ICLRTask](iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c75b8-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="c75b8-107">Return Value</span></span>  
  
|<span data-ttu-id="c75b8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c75b8-108">HRESULT</span></span>|<span data-ttu-id="c75b8-109">説明</span><span class="sxs-lookup"><span data-stu-id="c75b8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c75b8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c75b8-110">S_OK</span></span>|<span data-ttu-id="c75b8-111">メソッドから正常に値が返されました。</span><span class="sxs-lookup"><span data-stu-id="c75b8-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="c75b8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c75b8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c75b8-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="c75b8-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c75b8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c75b8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c75b8-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="c75b8-115">The call timed out.</span></span>|  
|<span data-ttu-id="c75b8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c75b8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c75b8-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="c75b8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c75b8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c75b8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c75b8-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="c75b8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c75b8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c75b8-120">E_FAIL</span></span>|<span data-ttu-id="c75b8-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c75b8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c75b8-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="c75b8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c75b8-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="c75b8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c75b8-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c75b8-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c75b8-125">要求されたリソースを割り当てるのに十分なメモリがありません。</span><span class="sxs-lookup"><span data-stu-id="c75b8-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c75b8-126">解説</span><span class="sxs-lookup"><span data-stu-id="c75b8-126">Remarks</span></span>  
 <span data-ttu-id="c75b8-127">CLR は、初期化時、ユーザーコードが名前空間の型を使用してスレッドを作成するとき、 <xref:System.Threading> またはスレッドプールのサイズが増加したときに、新しいタスクを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="c75b8-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="c75b8-128">また、アンマネージコードがマネージ関数を呼び出す場合にも、タスクが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c75b8-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="c75b8-129">`CreateTask`CLR によって新しいタスクが作成されることをホストが明示的に要求できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c75b8-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="c75b8-130">たとえば、ホストはこのメソッドを呼び出して、データ構造を事前に初期化できます。</span><span class="sxs-lookup"><span data-stu-id="c75b8-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c75b8-131">新しいタスクは中断状態で返され、ホストが明示的に[IHostTask:: Start](ihosttask-start-method.md)を呼び出すまで中断されたままになります。</span><span class="sxs-lookup"><span data-stu-id="c75b8-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c75b8-132">要件</span><span class="sxs-lookup"><span data-stu-id="c75b8-132">Requirements</span></span>  
 <span data-ttu-id="c75b8-133">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c75b8-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c75b8-134">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c75b8-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c75b8-135">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="c75b8-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c75b8-136">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c75b8-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c75b8-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="c75b8-137">See also</span></span>

- [<span data-ttu-id="c75b8-138">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c75b8-138">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="c75b8-139">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c75b8-139">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="c75b8-140">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c75b8-140">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="c75b8-141">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c75b8-141">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
