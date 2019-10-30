---
title: ICLRTask::RudeAbort メソッド
ms.date: 03/30/2017
api_name:
- ICLRTask.RudeAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::RudeAbort
helpviewer_keywords:
- RudeAbort method, ICLRTask interface [.NET Framework hosting]
- ICLRTask::RudeAbort method [.NET Framework hosting]
ms.assetid: b5785468-fcd7-4cc3-8a5d-8796337b53fc
topic_type:
- apiref
ms.openlocfilehash: 69e3ecfc82985d52bd5b14e9faf2566e395b622b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124653"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="3cc0a-102">ICLRTask::RudeAbort メソッド</span><span class="sxs-lookup"><span data-stu-id="3cc0a-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="3cc0a-103">現在の[ICLRTask インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンスによって表されるタスクをすぐに無条件で中止するように、共通言語ランタイム (CLR) に指示します。</span><span class="sxs-lookup"><span data-stu-id="3cc0a-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cc0a-104">構文</span><span class="sxs-lookup"><span data-stu-id="3cc0a-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="3cc0a-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="3cc0a-105">Return Value</span></span>  
  
|<span data-ttu-id="3cc0a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3cc0a-106">HRESULT</span></span>|<span data-ttu-id="3cc0a-107">説明</span><span class="sxs-lookup"><span data-stu-id="3cc0a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3cc0a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3cc0a-108">S_OK</span></span>|<span data-ttu-id="3cc0a-109">`RudeAbort` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="3cc0a-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="3cc0a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3cc0a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3cc0a-111">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="3cc0a-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3cc0a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3cc0a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3cc0a-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="3cc0a-113">The call timed out.</span></span>|  
|<span data-ttu-id="3cc0a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3cc0a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3cc0a-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="3cc0a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3cc0a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3cc0a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3cc0a-117">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="3cc0a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3cc0a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3cc0a-118">E_FAIL</span></span>|<span data-ttu-id="3cc0a-119">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="3cc0a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3cc0a-120">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="3cc0a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3cc0a-121">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="3cc0a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cc0a-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="3cc0a-122">Remarks</span></span>  
 <span data-ttu-id="3cc0a-123">ホストは `RudeAbort` を呼び出して、タスクをすぐに中止します。</span><span class="sxs-lookup"><span data-stu-id="3cc0a-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="3cc0a-124">ファイナライザーと例外処理ルーチンは、必ずしも実行されるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="3cc0a-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cc0a-125">［要件］</span><span class="sxs-lookup"><span data-stu-id="3cc0a-125">Requirements</span></span>  
 <span data-ttu-id="3cc0a-126">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cc0a-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cc0a-127">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3cc0a-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3cc0a-128">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="3cc0a-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3cc0a-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cc0a-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cc0a-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="3cc0a-130">See also</span></span>

- [<span data-ttu-id="3cc0a-131">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3cc0a-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="3cc0a-132">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3cc0a-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="3cc0a-133">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3cc0a-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="3cc0a-134">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3cc0a-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
