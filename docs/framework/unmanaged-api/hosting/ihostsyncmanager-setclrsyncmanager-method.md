---
title: IHostSyncManager::SetCLRSyncManager メソッド
ms.date: 03/30/2017
api_name:
- IHostSyncManager.SetCLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::SetCLRSyncManager
helpviewer_keywords:
- IHostSyncManager::SetCLRSyncManager method [.NET Framework hosting]
- SetCLRSyncManager method [.NET Framework hosting]
ms.assetid: 2b8bbe76-a45d-4989-bacb-11df42f8798c
topic_type:
- apiref
ms.openlocfilehash: 9c08a790d4dad748e5d09271bd870add22255b4a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132619"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="b1578-102">IHostSyncManager::SetCLRSyncManager メソッド</span><span class="sxs-lookup"><span data-stu-id="b1578-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="b1578-103">現在の[IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)インスタンスに関連付ける[ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)インスタンスを設定します。</span><span class="sxs-lookup"><span data-stu-id="b1578-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1578-104">構文</span><span class="sxs-lookup"><span data-stu-id="b1578-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1578-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b1578-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="b1578-106">から共通言語ランタイム (CLR) によって提供される `ICLRSyncManager` インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b1578-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b1578-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="b1578-107">Return Value</span></span>  
  
|<span data-ttu-id="b1578-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b1578-108">HRESULT</span></span>|<span data-ttu-id="b1578-109">説明</span><span class="sxs-lookup"><span data-stu-id="b1578-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b1578-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b1578-110">S_OK</span></span>|<span data-ttu-id="b1578-111">`SetCLRSyncManager` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="b1578-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="b1578-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b1578-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b1578-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="b1578-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b1578-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b1578-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b1578-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="b1578-115">The call timed out.</span></span>|  
|<span data-ttu-id="b1578-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b1578-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b1578-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="b1578-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b1578-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b1578-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b1578-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="b1578-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b1578-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b1578-120">E_FAIL</span></span>|<span data-ttu-id="b1578-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b1578-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b1578-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b1578-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b1578-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="b1578-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1578-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="b1578-124">Remarks</span></span>  
 <span data-ttu-id="b1578-125">ホストと CLR の間の通信を容易にするために、ホストインターフェイスは通常、ペアになっています。</span><span class="sxs-lookup"><span data-stu-id="b1578-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="b1578-126">ペアの1つのメンバーはホストによって実装され、もう一方のメンバーは CLR によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="b1578-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="b1578-127">ホスト側実装として、`IHostSyncManager` インターフェイスは、CLR によって実装される `ICLRSyncManager` インターフェイスに対応します。</span><span class="sxs-lookup"><span data-stu-id="b1578-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="b1578-128">CLR は `SetCLRSyncManager` を呼び出して、現在の `IHostSyncManager` インスタンスに関連付けられているホストの `ICLRSyncManager` インスタンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b1578-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1578-129">［要件］</span><span class="sxs-lookup"><span data-stu-id="b1578-129">Requirements</span></span>  
 <span data-ttu-id="b1578-130">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1578-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1578-131">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b1578-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b1578-132">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b1578-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b1578-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1578-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1578-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1578-134">See also</span></span>

- [<span data-ttu-id="b1578-135">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b1578-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="b1578-136">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b1578-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
