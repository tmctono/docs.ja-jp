---
title: IHostTaskManager::GetCurrentTask メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: f17bca49-90bd-4dee-a5e1-b9a57ea46f85
topic_type:
- apiref
ms.openlocfilehash: 874951d6b5efed0dc08e6d0e166962767e295c3e
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842050"
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="80011-102">IHostTaskManager::GetCurrentTask メソッド</span><span class="sxs-lookup"><span data-stu-id="80011-102">IHostTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="80011-103">この呼び出しが行われたオペレーティングシステムスレッドで現在実行されているタスクへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="80011-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80011-104">構文</span><span class="sxs-lookup"><span data-stu-id="80011-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80011-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="80011-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="80011-106">入出力現在実行中のタスクを表す[IHostTask](ihosttask-interface.md)インスタンスのアドレスへのポインター、またはタスクが現在実行されていない場合は null。</span><span class="sxs-lookup"><span data-stu-id="80011-106">[out] A pointer to the address of an [IHostTask](ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80011-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="80011-107">Return Value</span></span>  
  
|<span data-ttu-id="80011-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="80011-108">HRESULT</span></span>|<span data-ttu-id="80011-109">説明</span><span class="sxs-lookup"><span data-stu-id="80011-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="80011-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="80011-110">S_OK</span></span>|<span data-ttu-id="80011-111">`GetCurrentTask`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="80011-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="80011-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="80011-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="80011-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="80011-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="80011-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="80011-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="80011-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="80011-115">The call timed out.</span></span>|  
|<span data-ttu-id="80011-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="80011-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="80011-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="80011-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="80011-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="80011-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="80011-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="80011-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="80011-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="80011-120">E_FAIL</span></span>|<span data-ttu-id="80011-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="80011-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="80011-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="80011-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="80011-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="80011-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="80011-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="80011-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="80011-125">`GetCurrentTask`は、ホストの制御外にあるオペレーティングシステムのスレッドで呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="80011-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80011-126">コメント</span><span class="sxs-lookup"><span data-stu-id="80011-126">Remarks</span></span>  
 <span data-ttu-id="80011-127">ホストは、パラメーターを null に設定して、開始しなかっ `pTask` たタスクが CLR に入ってくるのを防ぐこともできます。</span><span class="sxs-lookup"><span data-stu-id="80011-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80011-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="80011-128">Requirements</span></span>  
 <span data-ttu-id="80011-129">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80011-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80011-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="80011-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="80011-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="80011-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80011-132">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80011-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80011-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="80011-133">See also</span></span>

- [<span data-ttu-id="80011-134">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="80011-134">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="80011-135">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="80011-135">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="80011-136">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="80011-136">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="80011-137">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="80011-137">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
