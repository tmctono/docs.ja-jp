---
title: ICLRTask::LocksHeld メソッド
ms.date: 03/30/2017
api_name:
- ICLRTask.LocksHeld
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::LocksHeld
helpviewer_keywords:
- LocksHeld method [.NET Framework hosting]
- ICLRTask::LocksHeld method [.NET Framework hosting]
ms.assetid: e88a4dc3-02cc-4703-a474-292b71c40657
topic_type:
- apiref
ms.openlocfilehash: 3a3c42e2877957e3bbf5031e6ba650e4c9e0364e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195943"
---
# <a name="iclrtasklocksheld-method"></a><span data-ttu-id="42272-102">ICLRTask::LocksHeld メソッド</span><span class="sxs-lookup"><span data-stu-id="42272-102">ICLRTask::LocksHeld Method</span></span>
<span data-ttu-id="42272-103">タスクに現在保持されているロックの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="42272-103">Gets the number of locks currently held on the task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42272-104">構文</span><span class="sxs-lookup"><span data-stu-id="42272-104">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeld (  
    [out] SIZE_T *pLockCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42272-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="42272-105">Parameters</span></span>  
 `pLockCount`  
 <span data-ttu-id="42272-106">入出力メソッドの呼び出し時にタスクに保持されていたロックの数。</span><span class="sxs-lookup"><span data-stu-id="42272-106">[out] The number of locks held on the task at the time of the method call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42272-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="42272-107">Return Value</span></span>  
  
|<span data-ttu-id="42272-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="42272-108">HRESULT</span></span>|<span data-ttu-id="42272-109">説明</span><span class="sxs-lookup"><span data-stu-id="42272-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="42272-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="42272-110">S_OK</span></span>|<span data-ttu-id="42272-111">`LocksHeld` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="42272-111">`LocksHeld` returned successfully.</span></span>|  
|<span data-ttu-id="42272-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="42272-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="42272-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="42272-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="42272-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="42272-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="42272-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="42272-115">The call timed out.</span></span>|  
|<span data-ttu-id="42272-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="42272-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="42272-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="42272-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="42272-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="42272-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="42272-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="42272-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="42272-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="42272-120">E_FAIL</span></span>|<span data-ttu-id="42272-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="42272-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="42272-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="42272-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="42272-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="42272-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="42272-124">［要件］</span><span class="sxs-lookup"><span data-stu-id="42272-124">Requirements</span></span>  
 <span data-ttu-id="42272-125">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42272-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42272-126">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="42272-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42272-127">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="42272-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42272-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42272-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42272-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="42272-129">See also</span></span>

- [<span data-ttu-id="42272-130">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42272-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="42272-131">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42272-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="42272-132">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42272-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="42272-133">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42272-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
