---
title: ICLRTask::SwitchIn メソッド
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchIn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchIn
helpviewer_keywords:
- ICLRTask::SwitchIn method [.NET Framework hosting]
- SwitchIn method [.NET Framework hosting]
ms.assetid: 3d37ce20-aa65-4043-8f13-7c728b5d8a52
topic_type:
- apiref
ms.openlocfilehash: d8f57af459d1bb3f338cfbfcbb29f69f533ea927
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762930"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="0de53-102">ICLRTask::SwitchIn メソッド</span><span class="sxs-lookup"><span data-stu-id="0de53-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="0de53-103">現在の[ICLRTask](iclrtask-interface.md)インスタンスが表すタスクが操作可能な状態であることを、共通言語ランタイム (CLR) に通知します。</span><span class="sxs-lookup"><span data-stu-id="0de53-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0de53-104">構文</span><span class="sxs-lookup"><span data-stu-id="0de53-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0de53-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0de53-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="0de53-106">から現在のインスタンスによって表されるタスクが実行されている物理スレッドへのハンドル `ICLRTask` 。</span><span class="sxs-lookup"><span data-stu-id="0de53-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0de53-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="0de53-107">Return Value</span></span>  
  
|<span data-ttu-id="0de53-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0de53-108">HRESULT</span></span>|<span data-ttu-id="0de53-109">説明</span><span class="sxs-lookup"><span data-stu-id="0de53-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0de53-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0de53-110">S_OK</span></span>|<span data-ttu-id="0de53-111">`SwitchIn`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="0de53-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="0de53-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0de53-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0de53-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="0de53-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0de53-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0de53-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0de53-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="0de53-115">The call timed out.</span></span>|  
|<span data-ttu-id="0de53-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0de53-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0de53-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="0de53-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0de53-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0de53-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0de53-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="0de53-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0de53-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0de53-120">E_FAIL</span></span>|<span data-ttu-id="0de53-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="0de53-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0de53-122">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="0de53-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0de53-123">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="0de53-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0de53-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="0de53-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="0de53-125">`SwitchIn`は、以前の[Switchout メソッド](iclrtask-switchout-method.md)の呼び出しなしで呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="0de53-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0de53-126">解説</span><span class="sxs-lookup"><span data-stu-id="0de53-126">Remarks</span></span>  
 <span data-ttu-id="0de53-127">パラメーターは、 `threadHandle` 現在のインスタンスによって表されるタスク `ICLRTask` がスケジュールされているオペレーティングシステムスレッドへのハンドルを表します。</span><span class="sxs-lookup"><span data-stu-id="0de53-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="0de53-128">このスレッドで偽装が発生した場合は、タスクを切り替える前に[IHostSecurityManager:: RevertToSelf](ihostsecuritymanager-reverttoself-method.md)を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="0de53-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0de53-129">を呼び出していないを呼び出すと、が `SwitchIn` `SwitchOut` HRESULT 値 HOST_E_INVALIDOPERATION で失敗します。</span><span class="sxs-lookup"><span data-stu-id="0de53-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0de53-130">要件</span><span class="sxs-lookup"><span data-stu-id="0de53-130">Requirements</span></span>  
 <span data-ttu-id="0de53-131">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0de53-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0de53-132">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0de53-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0de53-133">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="0de53-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0de53-134">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0de53-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0de53-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="0de53-135">See also</span></span>

- [<span data-ttu-id="0de53-136">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0de53-136">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="0de53-137">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0de53-137">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="0de53-138">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0de53-138">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="0de53-139">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0de53-139">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
