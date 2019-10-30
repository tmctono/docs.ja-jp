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
ms.openlocfilehash: 0bf8b6f393806e590be8f97dbfe2d01d5746c339
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139696"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="8f46d-102">ICLRTask::GetMemStats メソッド</span><span class="sxs-lookup"><span data-stu-id="8f46d-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="8f46d-103">現在の[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンスが表すタスクに関連する統計的メモリ使用量情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="8f46d-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f46d-104">構文</span><span class="sxs-lookup"><span data-stu-id="8f46d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f46d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8f46d-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="8f46d-106">入出力割り当てられたバイト数を含む、タスクのメモリ使用量に関する詳細を含む[COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md)インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8f46d-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f46d-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="8f46d-107">Return Value</span></span>  
  
|<span data-ttu-id="8f46d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8f46d-108">HRESULT</span></span>|<span data-ttu-id="8f46d-109">説明</span><span class="sxs-lookup"><span data-stu-id="8f46d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8f46d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8f46d-110">S_OK</span></span>|<span data-ttu-id="8f46d-111">`GetMemStats` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="8f46d-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="8f46d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8f46d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8f46d-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="8f46d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8f46d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8f46d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8f46d-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="8f46d-115">The call timed out.</span></span>|  
|<span data-ttu-id="8f46d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8f46d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8f46d-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="8f46d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8f46d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8f46d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8f46d-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="8f46d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8f46d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8f46d-120">E_FAIL</span></span>|<span data-ttu-id="8f46d-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="8f46d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8f46d-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="8f46d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8f46d-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="8f46d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8f46d-124">［要件］</span><span class="sxs-lookup"><span data-stu-id="8f46d-124">Requirements</span></span>  
 <span data-ttu-id="8f46d-125">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f46d-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f46d-126">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8f46d-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f46d-127">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="8f46d-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f46d-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f46d-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f46d-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f46d-129">See also</span></span>

- [<span data-ttu-id="8f46d-130">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f46d-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="8f46d-131">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f46d-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8f46d-132">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f46d-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="8f46d-133">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f46d-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
