---
title: ICLRTask::SwitchOut メソッド
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchOut
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type:
- apiref
ms.openlocfilehash: 75517ae55ebae07242f19c19c5473780ce4b0809
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762917"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="f951b-102">ICLRTask::SwitchOut メソッド</span><span class="sxs-lookup"><span data-stu-id="f951b-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="f951b-103">現在の[ICLRTask](iclrtask-interface.md)インスタンスによって表されるタスクが操作可能な状態ではなくなったことを、共通言語ランタイム (CLR) に通知します。</span><span class="sxs-lookup"><span data-stu-id="f951b-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f951b-104">構文</span><span class="sxs-lookup"><span data-stu-id="f951b-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f951b-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="f951b-105">Return Value</span></span>  
  
|<span data-ttu-id="f951b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f951b-106">HRESULT</span></span>|<span data-ttu-id="f951b-107">説明</span><span class="sxs-lookup"><span data-stu-id="f951b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f951b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f951b-108">S_OK</span></span>|<span data-ttu-id="f951b-109">`SwitchOut`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="f951b-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="f951b-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f951b-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f951b-111">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="f951b-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f951b-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f951b-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f951b-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="f951b-113">The call timed out.</span></span>|  
|<span data-ttu-id="f951b-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f951b-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f951b-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="f951b-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f951b-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f951b-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f951b-117">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="f951b-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f951b-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f951b-118">E_FAIL</span></span>|<span data-ttu-id="f951b-119">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="f951b-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f951b-120">メソッドが E_FAIL を返すと、そのプロセス内で CLR が使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f951b-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f951b-121">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="f951b-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f951b-122">解説</span><span class="sxs-lookup"><span data-stu-id="f951b-122">Remarks</span></span>  
 <span data-ttu-id="f951b-123">ホストは、 `SwitchOut` 現在のインスタンスが表すタスクの実行を一時的に停止したことを CLR に通知し、タスクを再 `ICLRTask` スケジュールします。</span><span class="sxs-lookup"><span data-stu-id="f951b-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f951b-124">要件</span><span class="sxs-lookup"><span data-stu-id="f951b-124">Requirements</span></span>  
 <span data-ttu-id="f951b-125">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f951b-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f951b-126">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f951b-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f951b-127">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="f951b-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f951b-128">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f951b-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f951b-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="f951b-129">See also</span></span>

- [<span data-ttu-id="f951b-130">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f951b-130">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="f951b-131">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f951b-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="f951b-132">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f951b-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="f951b-133">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f951b-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
