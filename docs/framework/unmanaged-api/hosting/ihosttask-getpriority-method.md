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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b722963290ec9713d4dc991cc4135473da96b42e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764524"
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="62d4f-102">IHostTask::GetPriority メソッド</span><span class="sxs-lookup"><span data-stu-id="62d4f-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="62d4f-103">現在のタスクのスレッド優先度レベルを取得[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="62d4f-103">Gets the thread priority level of the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62d4f-104">構文</span><span class="sxs-lookup"><span data-stu-id="62d4f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62d4f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="62d4f-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="62d4f-106">[out]現在のタスクのスレッドの優先順位を示す整数を指すポインター`IHostTask`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="62d4f-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62d4f-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="62d4f-107">Return Value</span></span>  
  
|<span data-ttu-id="62d4f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="62d4f-108">HRESULT</span></span>|<span data-ttu-id="62d4f-109">説明</span><span class="sxs-lookup"><span data-stu-id="62d4f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="62d4f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="62d4f-110">S_OK</span></span>|<span data-ttu-id="62d4f-111">`GetPriority` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="62d4f-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="62d4f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="62d4f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="62d4f-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="62d4f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="62d4f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="62d4f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="62d4f-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="62d4f-115">The call timed out.</span></span>|  
|<span data-ttu-id="62d4f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="62d4f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="62d4f-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="62d4f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="62d4f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="62d4f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="62d4f-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="62d4f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="62d4f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="62d4f-120">E_FAIL</span></span>|<span data-ttu-id="62d4f-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="62d4f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="62d4f-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="62d4f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="62d4f-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="62d4f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62d4f-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="62d4f-124">Remarks</span></span>  
 <span data-ttu-id="62d4f-125">によって Win32 スレッド優先度レベルの値が定義されている`SetThreadPriority`関数。</span><span class="sxs-lookup"><span data-stu-id="62d4f-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62d4f-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="62d4f-126">Requirements</span></span>  
 <span data-ttu-id="62d4f-127">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="62d4f-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62d4f-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="62d4f-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62d4f-129">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="62d4f-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62d4f-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62d4f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62d4f-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="62d4f-131">See also</span></span>

- [<span data-ttu-id="62d4f-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="62d4f-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="62d4f-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="62d4f-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="62d4f-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="62d4f-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="62d4f-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="62d4f-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
