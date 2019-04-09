---
title: IHostIoCompletionManager::GetAvailableThreads メソッド
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: bab363d1-b859-47a4-9884-5661c611cce7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1e96a12bbf9c4fdc8a0bc79661070eb7fec1a593
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123977"
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="196ee-102">IHostIoCompletionManager::GetAvailableThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="196ee-102">IHostIoCompletionManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="196ee-103">現在要求の処理はありませんが、ホストによって管理されるスレッドの合計数の I/O 完了スレッドの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="196ee-103">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="196ee-104">構文</span><span class="sxs-lookup"><span data-stu-id="196ee-104">Syntax</span></span>  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="196ee-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="196ee-105">Parameters</span></span>  
 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="196ee-106">[out]I/O 完了スレッド、ホストによって管理されるサービス要求を現在利用できる数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="196ee-106">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="196ee-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="196ee-107">Return Value</span></span>  
  
|<span data-ttu-id="196ee-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="196ee-108">HRESULT</span></span>|<span data-ttu-id="196ee-109">説明</span><span class="sxs-lookup"><span data-stu-id="196ee-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="196ee-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="196ee-110">S_OK</span></span>|`GetAvailableThreads` <span data-ttu-id="196ee-111">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="196ee-111">returned successfully.</span></span>|  
|<span data-ttu-id="196ee-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="196ee-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="196ee-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="196ee-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="196ee-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="196ee-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="196ee-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="196ee-115">The call timed out.</span></span>|  
|<span data-ttu-id="196ee-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="196ee-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="196ee-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="196ee-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="196ee-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="196ee-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="196ee-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="196ee-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="196ee-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="196ee-120">E_FAIL</span></span>|<span data-ttu-id="196ee-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="196ee-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="196ee-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="196ee-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="196ee-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="196ee-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="196ee-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="196ee-124">E_NOTIMPL</span></span>|<span data-ttu-id="196ee-125">ホストがの実装を提供しない`GetAvailableThreads`します。</span><span class="sxs-lookup"><span data-stu-id="196ee-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="196ee-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="196ee-126">Remarks</span></span>  
 <span data-ttu-id="196ee-127">ホストは、実装、パフォーマンス、スケーラビリティなどの理由で、I/O 完了スレッド プールのサイズを排他的に制御を必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="196ee-127">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="196ee-128">そのため、ホストは、実装する必要はありません`GetAvailableThreads`します。</span><span class="sxs-lookup"><span data-stu-id="196ee-128">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="196ee-129">この場合、ホストは、このメソッドから E_NOTIMPL を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="196ee-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="196ee-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="196ee-130">Requirements</span></span>  
 <span data-ttu-id="196ee-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="196ee-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="196ee-132">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="196ee-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="196ee-133">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="196ee-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="196ee-134">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="196ee-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="196ee-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="196ee-135">See also</span></span>

- [<span data-ttu-id="196ee-136">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="196ee-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="196ee-137">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="196ee-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
