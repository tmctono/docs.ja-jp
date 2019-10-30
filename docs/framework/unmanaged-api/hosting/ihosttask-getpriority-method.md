---
title: IHostTask::GetPriority メソッド
ms.date: 03/30/2017
api_name:
- IHostTask.GetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::GetPriority
helpviewer_keywords:
- GetPriority method [.NET Framework hosting]
- IHostTask::GetPriority method [.NET Framework hosting]
ms.assetid: 4b463cd6-77c1-4f9a-8518-346ad8fc4b70
topic_type:
- apiref
ms.openlocfilehash: 6c33fa6d2e6cb09f013c5334461e61235db549f7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121416"
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="1cc18-102">IHostTask::GetPriority メソッド</span><span class="sxs-lookup"><span data-stu-id="1cc18-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="1cc18-103">現在の[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)インスタンスによって表されるタスクのスレッド優先度レベルを取得します。</span><span class="sxs-lookup"><span data-stu-id="1cc18-103">Gets the thread priority level of the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cc18-104">構文</span><span class="sxs-lookup"><span data-stu-id="1cc18-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1cc18-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1cc18-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="1cc18-106">入出力現在の `IHostTask` インスタンスによって表されるタスクのスレッド優先度レベルを示す整数を指すポインターです。</span><span class="sxs-lookup"><span data-stu-id="1cc18-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1cc18-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="1cc18-107">Return Value</span></span>  
  
|<span data-ttu-id="1cc18-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1cc18-108">HRESULT</span></span>|<span data-ttu-id="1cc18-109">説明</span><span class="sxs-lookup"><span data-stu-id="1cc18-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1cc18-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1cc18-110">S_OK</span></span>|<span data-ttu-id="1cc18-111">`GetPriority` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="1cc18-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="1cc18-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1cc18-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1cc18-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="1cc18-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1cc18-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1cc18-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1cc18-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="1cc18-115">The call timed out.</span></span>|  
|<span data-ttu-id="1cc18-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1cc18-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1cc18-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="1cc18-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1cc18-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1cc18-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1cc18-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="1cc18-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1cc18-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1cc18-120">E_FAIL</span></span>|<span data-ttu-id="1cc18-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="1cc18-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1cc18-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="1cc18-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1cc18-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="1cc18-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1cc18-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="1cc18-124">Remarks</span></span>  
 <span data-ttu-id="1cc18-125">スレッドの優先度レベルの値は、Win32 `SetThreadPriority` 関数によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="1cc18-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cc18-126">［要件］</span><span class="sxs-lookup"><span data-stu-id="1cc18-126">Requirements</span></span>  
 <span data-ttu-id="1cc18-127">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cc18-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cc18-128">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1cc18-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1cc18-129">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="1cc18-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1cc18-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cc18-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cc18-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="1cc18-131">See also</span></span>

- [<span data-ttu-id="1cc18-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1cc18-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="1cc18-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1cc18-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="1cc18-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1cc18-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="1cc18-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1cc18-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
