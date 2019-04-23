---
title: ICLRTask::GetMemStats メソッド
ms.date: 03/30/2017
api_name:
- ICLRTask.GetMemStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::GetMemStats
helpviewer_keywords:
- ICLRTask::GetMemStats method [.NET Framework hosting]
- GetMemStats method [.NET Framework hosting]
ms.assetid: c9e07657-1682-4c30-a336-f8658ff1a125
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 668e570c315f5473f222905a061f05ac94afa81a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183405"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="976eb-102">ICLRTask::GetMemStats メソッド</span><span class="sxs-lookup"><span data-stu-id="976eb-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="976eb-103">タスクに関連する統計のメモリ使用量の情報を取得する現在[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンスが表す。</span><span class="sxs-lookup"><span data-stu-id="976eb-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="976eb-104">構文</span><span class="sxs-lookup"><span data-stu-id="976eb-104">Syntax</span></span>  
  
```  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="976eb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="976eb-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="976eb-106">[out]ポインターを[COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md)割り当てられたバイト数など、タスクのメモリ使用量に関する詳細を含むインスタンス。</span><span class="sxs-lookup"><span data-stu-id="976eb-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="976eb-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="976eb-107">Return Value</span></span>  
  
|<span data-ttu-id="976eb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="976eb-108">HRESULT</span></span>|<span data-ttu-id="976eb-109">説明</span><span class="sxs-lookup"><span data-stu-id="976eb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="976eb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="976eb-110">S_OK</span></span>|<span data-ttu-id="976eb-111">`GetMemStats` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="976eb-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="976eb-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="976eb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="976eb-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="976eb-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="976eb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="976eb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="976eb-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="976eb-115">The call timed out.</span></span>|  
|<span data-ttu-id="976eb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="976eb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="976eb-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="976eb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="976eb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="976eb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="976eb-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="976eb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="976eb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="976eb-120">E_FAIL</span></span>|<span data-ttu-id="976eb-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="976eb-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="976eb-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="976eb-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="976eb-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="976eb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="976eb-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="976eb-124">Requirements</span></span>  
 <span data-ttu-id="976eb-125">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="976eb-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="976eb-126">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="976eb-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="976eb-127">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="976eb-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="976eb-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="976eb-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="976eb-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="976eb-129">See also</span></span>

- [<span data-ttu-id="976eb-130">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="976eb-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="976eb-131">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="976eb-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="976eb-132">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="976eb-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="976eb-133">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="976eb-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
