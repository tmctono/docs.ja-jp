---
title: IHostThreadPoolManager::SetMaxThreads メソッド
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: 77cfd347-95c2-4425-b807-4ecc2a8d4578
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0df8d11bba870dfec880401064ec3f78f5f04e1f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081477"
---
# <a name="ihostthreadpoolmanagersetmaxthreads-method"></a><span data-ttu-id="acc3f-102">IHostThreadPoolManager::SetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="acc3f-102">IHostThreadPoolManager::SetMaxThreads Method</span></span>
<span data-ttu-id="acc3f-103">ホストは、スレッド プールで保持できるスレッドの最大数を設定します。</span><span class="sxs-lookup"><span data-stu-id="acc3f-103">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acc3f-104">構文</span><span class="sxs-lookup"><span data-stu-id="acc3f-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD MaxThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acc3f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="acc3f-105">Parameters</span></span>  
 `MaxThreads`  
 <span data-ttu-id="acc3f-106">スレッド プール内のワーカー スレッドの最大数。</span><span class="sxs-lookup"><span data-stu-id="acc3f-106">The maximum number of worker threads in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="acc3f-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="acc3f-107">Return Value</span></span>  
  
|<span data-ttu-id="acc3f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="acc3f-108">HRESULT</span></span>|<span data-ttu-id="acc3f-109">説明</span><span class="sxs-lookup"><span data-stu-id="acc3f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="acc3f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="acc3f-110">S_OK</span></span>|`SetMaxThreads` <span data-ttu-id="acc3f-111">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="acc3f-111">returned successfully.</span></span>|  
|<span data-ttu-id="acc3f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="acc3f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="acc3f-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="acc3f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="acc3f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="acc3f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="acc3f-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="acc3f-115">The call timed out.</span></span>|  
|<span data-ttu-id="acc3f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="acc3f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="acc3f-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="acc3f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="acc3f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="acc3f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="acc3f-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="acc3f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="acc3f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="acc3f-120">E_FAIL</span></span>|<span data-ttu-id="acc3f-121">未知の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="acc3f-121">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="acc3f-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="acc3f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="acc3f-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="acc3f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="acc3f-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="acc3f-124">E_NOTIMPL</span></span>|<span data-ttu-id="acc3f-125">ホストがの実装を提供しない`SetMaxThreads`します。</span><span class="sxs-lookup"><span data-stu-id="acc3f-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acc3f-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="acc3f-126">Remarks</span></span>  
 <span data-ttu-id="acc3f-127">ホストは、CLR スレッド プールのサイズの構成を許可する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="acc3f-127">A host is not required to allow the CLR to configure the size of the thread pool.</span></span> <span data-ttu-id="acc3f-128">一部のホストは、実装、パフォーマンス、スケーラビリティなどの理由で、スレッド プールを排他的に制御を必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="acc3f-128">Some hosts might want exclusive control over the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="acc3f-129">ここでは、ホストは HRESULT 値 E_NOTIMPL を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="acc3f-129">In this case, a host should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acc3f-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="acc3f-130">Requirements</span></span>  
 <span data-ttu-id="acc3f-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="acc3f-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acc3f-132">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="acc3f-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="acc3f-133">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="acc3f-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="acc3f-134">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="acc3f-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="acc3f-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="acc3f-135">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="acc3f-136">GetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="acc3f-136">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="acc3f-137">SetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="acc3f-137">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="acc3f-138">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="acc3f-138">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
