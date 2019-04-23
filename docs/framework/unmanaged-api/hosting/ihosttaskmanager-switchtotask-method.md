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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a50c9f7fc5921d3e5c21dd3566de81ac2249f3dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110561"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="62126-102">IHostTaskManager::SwitchToTask メソッド</span><span class="sxs-lookup"><span data-stu-id="62126-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="62126-103">現在のタスクを切り離すことをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="62126-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62126-104">構文</span><span class="sxs-lookup"><span data-stu-id="62126-104">Syntax</span></span>  
  
```  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62126-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="62126-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="62126-106">[in]1 つ、 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)場合に、ホストが実行するアクションを示す、列挙値、要求された操作がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="62126-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62126-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="62126-107">Return Value</span></span>  
  
|<span data-ttu-id="62126-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="62126-108">HRESULT</span></span>|<span data-ttu-id="62126-109">説明</span><span class="sxs-lookup"><span data-stu-id="62126-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="62126-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="62126-110">S_OK</span></span>|<span data-ttu-id="62126-111">`SwitchToTask` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="62126-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="62126-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="62126-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="62126-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="62126-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="62126-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="62126-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="62126-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="62126-115">The call timed out.</span></span>|  
|<span data-ttu-id="62126-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="62126-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="62126-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="62126-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="62126-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="62126-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="62126-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="62126-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="62126-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="62126-120">E_FAIL</span></span>|<span data-ttu-id="62126-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="62126-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="62126-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="62126-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="62126-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="62126-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62126-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="62126-124">Remarks</span></span>  
 <span data-ttu-id="62126-125">ホストは、必要に応じて、別のタスクに切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="62126-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62126-126">`SwitchToTask` ホストが切り替えるタスクで指定されていません。切り替える必要がありますが、タスクのみを指定します。</span><span class="sxs-lookup"><span data-stu-id="62126-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62126-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="62126-127">Requirements</span></span>  
 <span data-ttu-id="62126-128">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="62126-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62126-129">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="62126-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62126-130">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="62126-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62126-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62126-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62126-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="62126-132">See also</span></span>

- [<span data-ttu-id="62126-133">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="62126-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="62126-134">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="62126-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="62126-135">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="62126-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="62126-136">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="62126-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
