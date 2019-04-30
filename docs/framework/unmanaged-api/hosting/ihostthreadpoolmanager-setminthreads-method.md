---
title: IHostThreadPoolManager::SetMinThreads メソッド
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: 10409db9-9fd2-4e4d-b8cd-cf6fec0afaa2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e290f20feacc59944bb1cafded327f4316ab88d9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62046216"
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="7c069-102">IHostThreadPoolManager::SetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="7c069-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="7c069-103">要求に応じるため、ホストを管理する必要があるアイドル状態のスレッドの最小数を設定します。</span><span class="sxs-lookup"><span data-stu-id="7c069-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c069-104">構文</span><span class="sxs-lookup"><span data-stu-id="7c069-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c069-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7c069-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="7c069-106">[in]ホストを管理する必要があるスレッドの新しいの最小数。</span><span class="sxs-lookup"><span data-stu-id="7c069-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c069-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="7c069-107">Return Value</span></span>  
  
|<span data-ttu-id="7c069-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c069-108">HRESULT</span></span>|<span data-ttu-id="7c069-109">説明</span><span class="sxs-lookup"><span data-stu-id="7c069-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c069-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c069-110">S_OK</span></span>|<span data-ttu-id="7c069-111">`SetMinThreads` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="7c069-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="7c069-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7c069-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c069-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="7c069-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7c069-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7c069-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7c069-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="7c069-115">The call timed out.</span></span>|  
|<span data-ttu-id="7c069-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7c069-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7c069-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="7c069-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7c069-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7c069-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7c069-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="7c069-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7c069-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c069-120">E_FAIL</span></span>|<span data-ttu-id="7c069-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7c069-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7c069-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="7c069-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7c069-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="7c069-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7c069-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="7c069-124">E_NOTIMPL</span></span>|<span data-ttu-id="7c069-125">ホストがの実装を提供しない`SetMinThreads`します。</span><span class="sxs-lookup"><span data-stu-id="7c069-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c069-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="7c069-126">Remarks</span></span>  
 <span data-ttu-id="7c069-127">ホストは、の実装を提供する必要はありません`SetMinThreads`します。</span><span class="sxs-lookup"><span data-stu-id="7c069-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="7c069-128">この場合、E_NOTIMPL の HRESULT 値を返す必要がありますに。</span><span class="sxs-lookup"><span data-stu-id="7c069-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c069-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="7c069-129">Requirements</span></span>  
 <span data-ttu-id="7c069-130">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c069-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c069-131">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7c069-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c069-132">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="7c069-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c069-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c069-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c069-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c069-134">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="7c069-135">GetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="7c069-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="7c069-136">SetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="7c069-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="7c069-137">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c069-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
