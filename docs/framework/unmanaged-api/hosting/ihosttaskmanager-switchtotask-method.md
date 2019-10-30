---
title: IHostTaskManager::SwitchToTask メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SwitchToTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SwitchToTask
helpviewer_keywords:
- IHostTaskManager::SwitchToTask method [.NET Framework hosting]
- SwitchToTask method [.NET Framework hosting]
ms.assetid: 35d0c27e-4b14-49ce-810d-7ab2120177e8
topic_type:
- apiref
ms.openlocfilehash: a55b43f3629cebb0ba1d3a7ac1802126874418d8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122113"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="f023d-102">IHostTaskManager::SwitchToTask メソッド</span><span class="sxs-lookup"><span data-stu-id="f023d-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="f023d-103">現在のタスクを切り替える必要があることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="f023d-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f023d-104">構文</span><span class="sxs-lookup"><span data-stu-id="f023d-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f023d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f023d-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="f023d-106">から[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)列挙値の1つ。要求された操作がブロックされた場合にホストが実行するアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="f023d-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f023d-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="f023d-107">Return Value</span></span>  
  
|<span data-ttu-id="f023d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f023d-108">HRESULT</span></span>|<span data-ttu-id="f023d-109">説明</span><span class="sxs-lookup"><span data-stu-id="f023d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f023d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f023d-110">S_OK</span></span>|<span data-ttu-id="f023d-111">`SwitchToTask` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="f023d-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="f023d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f023d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f023d-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="f023d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f023d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f023d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f023d-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="f023d-115">The call timed out.</span></span>|  
|<span data-ttu-id="f023d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f023d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f023d-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="f023d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f023d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f023d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f023d-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="f023d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f023d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f023d-120">E_FAIL</span></span>|<span data-ttu-id="f023d-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="f023d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f023d-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f023d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f023d-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="f023d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f023d-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="f023d-124">Remarks</span></span>  
 <span data-ttu-id="f023d-125">ホストは、必要に応じて別のタスクに切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="f023d-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f023d-126">`SwitchToTask` では、ホストが切り替える必要があるタスクが指定されていません。これは、切り替え元のタスクだけを指定します。</span><span class="sxs-lookup"><span data-stu-id="f023d-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f023d-127">［要件］</span><span class="sxs-lookup"><span data-stu-id="f023d-127">Requirements</span></span>  
 <span data-ttu-id="f023d-128">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f023d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f023d-129">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f023d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f023d-130">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="f023d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f023d-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f023d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f023d-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="f023d-132">See also</span></span>

- [<span data-ttu-id="f023d-133">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f023d-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f023d-134">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f023d-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f023d-135">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f023d-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f023d-136">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f023d-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
