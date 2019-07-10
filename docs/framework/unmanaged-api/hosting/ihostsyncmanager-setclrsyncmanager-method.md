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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 66ce6ce322a0fb58f64d65501a33f58ad92bcd2e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764557"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="6f5ff-102">IHostSyncManager::SetCLRSyncManager メソッド</span><span class="sxs-lookup"><span data-stu-id="6f5ff-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="6f5ff-103">セット、 [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)インスタンスに現在関連付ける[IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="6f5ff-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f5ff-104">構文</span><span class="sxs-lookup"><span data-stu-id="6f5ff-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f5ff-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6f5ff-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="6f5ff-106">[in]ポインター、`ICLRSyncManager`共通言語ランタイム (CLR) で指定されたインスタンス。</span><span class="sxs-lookup"><span data-stu-id="6f5ff-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f5ff-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="6f5ff-107">Return Value</span></span>  
  
|<span data-ttu-id="6f5ff-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6f5ff-108">HRESULT</span></span>|<span data-ttu-id="6f5ff-109">説明</span><span class="sxs-lookup"><span data-stu-id="6f5ff-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6f5ff-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6f5ff-110">S_OK</span></span>|<span data-ttu-id="6f5ff-111">`SetCLRSyncManager` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="6f5ff-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="6f5ff-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6f5ff-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6f5ff-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="6f5ff-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6f5ff-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6f5ff-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6f5ff-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="6f5ff-115">The call timed out.</span></span>|  
|<span data-ttu-id="6f5ff-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6f5ff-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6f5ff-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="6f5ff-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6f5ff-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6f5ff-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6f5ff-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="6f5ff-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6f5ff-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6f5ff-120">E_FAIL</span></span>|<span data-ttu-id="6f5ff-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6f5ff-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6f5ff-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="6f5ff-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6f5ff-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="6f5ff-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f5ff-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="6f5ff-124">Remarks</span></span>  
 <span data-ttu-id="6f5ff-125">ホストと CLR の間の通信を容易にホスト インターフェイスは、通常のペアになっています。</span><span class="sxs-lookup"><span data-stu-id="6f5ff-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="6f5ff-126">ペアの 1 つのメンバーは、ホストによって実装され、その他のメンバーは、CLR によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="6f5ff-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="6f5ff-127">ホスト側の実装として、`IHostSyncManager`インターフェイスに対応する、 `ICLRSyncManager` CLR によって実装されるインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6f5ff-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="6f5ff-128">CLR 呼び出し`SetCLRSyncManager`を指定する、`ICLRSyncManager`に関連付ける、現在のホスト インスタンス`IHostSyncManager`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="6f5ff-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f5ff-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="6f5ff-129">Requirements</span></span>  
 <span data-ttu-id="6f5ff-130">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f5ff-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f5ff-131">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6f5ff-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6f5ff-132">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="6f5ff-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f5ff-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f5ff-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f5ff-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f5ff-134">See also</span></span>

- [<span data-ttu-id="6f5ff-135">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6f5ff-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="6f5ff-136">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6f5ff-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
