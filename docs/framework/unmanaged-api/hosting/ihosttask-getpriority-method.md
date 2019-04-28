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
ms.openlocfilehash: 702992ab4edfea3f0b699efefedb195cd87586ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789572"
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="54a5e-102">IHostTask::GetPriority メソッド</span><span class="sxs-lookup"><span data-stu-id="54a5e-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="54a5e-103">現在のタスクのスレッド優先度レベルを取得[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="54a5e-103">Gets the thread priority level of the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54a5e-104">構文</span><span class="sxs-lookup"><span data-stu-id="54a5e-104">Syntax</span></span>  
  
```  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54a5e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="54a5e-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="54a5e-106">[out]現在のタスクのスレッドの優先順位を示す整数を指すポインター`IHostTask`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="54a5e-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54a5e-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="54a5e-107">Return Value</span></span>  
  
|<span data-ttu-id="54a5e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="54a5e-108">HRESULT</span></span>|<span data-ttu-id="54a5e-109">説明</span><span class="sxs-lookup"><span data-stu-id="54a5e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="54a5e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="54a5e-110">S_OK</span></span>|<span data-ttu-id="54a5e-111">`GetPriority` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="54a5e-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="54a5e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="54a5e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="54a5e-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="54a5e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="54a5e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="54a5e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="54a5e-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="54a5e-115">The call timed out.</span></span>|  
|<span data-ttu-id="54a5e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="54a5e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="54a5e-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="54a5e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="54a5e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="54a5e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="54a5e-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="54a5e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="54a5e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="54a5e-120">E_FAIL</span></span>|<span data-ttu-id="54a5e-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="54a5e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="54a5e-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="54a5e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="54a5e-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="54a5e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54a5e-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="54a5e-124">Remarks</span></span>  
 <span data-ttu-id="54a5e-125">によって Win32 スレッド優先度レベルの値が定義されている`SetThreadPriority`関数。</span><span class="sxs-lookup"><span data-stu-id="54a5e-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54a5e-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="54a5e-126">Requirements</span></span>  
 <span data-ttu-id="54a5e-127">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="54a5e-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54a5e-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="54a5e-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="54a5e-129">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="54a5e-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="54a5e-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54a5e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54a5e-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="54a5e-131">See also</span></span>

- [<span data-ttu-id="54a5e-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="54a5e-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="54a5e-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="54a5e-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="54a5e-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="54a5e-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="54a5e-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="54a5e-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
