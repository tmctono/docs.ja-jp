---
title: ICLRTaskManager::GetCurrentTask メソッド
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: c0b82a9f-edc6-4878-9c81-48de53c02142
topic_type:
- apiref
ms.openlocfilehash: a57610d1b41d80d54a245b9744aafd78a1e88177
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195904"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="b3607-102">ICLRTaskManager::GetCurrentTask メソッド</span><span class="sxs-lookup"><span data-stu-id="b3607-102">ICLRTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="b3607-103">メソッドの呼び出し元のオペレーティングシステムスレッドで現在実行されている[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b3607-103">Gets the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3607-104">構文</span><span class="sxs-lookup"><span data-stu-id="b3607-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3607-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b3607-105">Parameters</span></span>  
 `ppTask`  
 <span data-ttu-id="b3607-106">入出力呼び出し元のオペレーティングシステムスレッドで現在実行されている `ICLRTask` インスタンスのアドレスへのポインター。このスレッドでタスクが現在実行されていない場合は null。</span><span class="sxs-lookup"><span data-stu-id="b3607-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3607-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="b3607-107">Return Value</span></span>  
  
|<span data-ttu-id="b3607-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b3607-108">HRESULT</span></span>|<span data-ttu-id="b3607-109">説明</span><span class="sxs-lookup"><span data-stu-id="b3607-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b3607-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b3607-110">S_OK</span></span>|<span data-ttu-id="b3607-111">メソッドが正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="b3607-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="b3607-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b3607-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b3607-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="b3607-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b3607-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b3607-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b3607-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="b3607-115">The call timed out.</span></span>|  
|<span data-ttu-id="b3607-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b3607-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b3607-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="b3607-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b3607-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b3607-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b3607-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="b3607-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b3607-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b3607-120">E_FAIL</span></span>|<span data-ttu-id="b3607-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b3607-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b3607-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b3607-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b3607-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="b3607-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3607-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="b3607-124">Remarks</span></span>  
 <span data-ttu-id="b3607-125">`ppTask` パラメーターが指す `ICLRTask` インスタンスは、CLR に対して現在実行中のタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="b3607-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="b3607-126">`ICLRTask` インスタンスは、ホストのタスクを表す、対応する[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)インスタンスに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="b3607-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3607-127">［要件］</span><span class="sxs-lookup"><span data-stu-id="b3607-127">Requirements</span></span>  
 <span data-ttu-id="b3607-128">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3607-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3607-129">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b3607-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b3607-130">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b3607-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b3607-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3607-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3607-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3607-132">See also</span></span>

- [<span data-ttu-id="b3607-133">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b3607-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="b3607-134">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b3607-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="b3607-135">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b3607-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="b3607-136">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b3607-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
