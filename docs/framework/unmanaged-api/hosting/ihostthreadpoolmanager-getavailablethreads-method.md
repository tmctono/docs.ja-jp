---
title: IHostThreadPoolManager::GetAvailableThreads メソッド
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: 61d26dfd-7f24-4e7d-a63e-b30a463f08e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21a727a5287f6eaad600fc37befc32790fc4cf26
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749298"
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="650fa-102">IHostThreadPoolManager::GetAvailableThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="650fa-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="650fa-103">作業項目を現在処理していないスレッド プールのスレッドの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="650fa-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="650fa-104">構文</span><span class="sxs-lookup"><span data-stu-id="650fa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="650fa-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="650fa-105">Parameters</span></span>  
 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="650fa-106">[out]作業項目を現在処理していないスレッド プール内のスレッドの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="650fa-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="650fa-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="650fa-107">Return Value</span></span>  
  
|<span data-ttu-id="650fa-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="650fa-108">HRESULT</span></span>|<span data-ttu-id="650fa-109">説明</span><span class="sxs-lookup"><span data-stu-id="650fa-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="650fa-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="650fa-110">S_OK</span></span>|<span data-ttu-id="650fa-111">`GetAvailableThreads` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="650fa-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="650fa-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="650fa-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="650fa-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="650fa-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="650fa-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="650fa-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="650fa-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="650fa-115">The call timed out.</span></span>|  
|<span data-ttu-id="650fa-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="650fa-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="650fa-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="650fa-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="650fa-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="650fa-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="650fa-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="650fa-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="650fa-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="650fa-120">E_FAIL</span></span>|<span data-ttu-id="650fa-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="650fa-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="650fa-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="650fa-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="650fa-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="650fa-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="650fa-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="650fa-124">E_NOTIMPL</span></span>|<span data-ttu-id="650fa-125">ホストがの実装を提供しない`GetAvailableThreads`します。</span><span class="sxs-lookup"><span data-stu-id="650fa-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="650fa-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="650fa-126">Remarks</span></span>  
 <span data-ttu-id="650fa-127">ホストでの実装が提供されていない場合`GetAvailableThreads`E_NOTIMPL の HRESULT 値を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="650fa-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="650fa-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="650fa-128">Requirements</span></span>  
 <span data-ttu-id="650fa-129">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="650fa-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="650fa-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="650fa-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="650fa-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="650fa-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="650fa-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="650fa-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="650fa-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="650fa-133">See also</span></span>

- <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="650fa-134">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="650fa-134">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
