---
title: IHostManualEvent::Reset メソッド
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Reset
helpviewer_keywords:
- Reset method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Reset method [.NET Framework hosting]
ms.assetid: 0d101168-b5e3-49ce-90c7-85cf2db83c4c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37ba54665dbd8d10c7e7aac9a0692c8882fb5209
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767290"
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="d7b58-102">IHostManualEvent::Reset メソッド</span><span class="sxs-lookup"><span data-stu-id="d7b58-102">IHostManualEvent::Reset Method</span></span>
<span data-ttu-id="d7b58-103">現在のリセット[IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)インスタンスを非シグナル状態にします。</span><span class="sxs-lookup"><span data-stu-id="d7b58-103">Resets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7b58-104">構文</span><span class="sxs-lookup"><span data-stu-id="d7b58-104">Syntax</span></span>  
  
```cpp  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d7b58-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="d7b58-105">Return Value</span></span>  
  
|<span data-ttu-id="d7b58-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d7b58-106">HRESULT</span></span>|<span data-ttu-id="d7b58-107">説明</span><span class="sxs-lookup"><span data-stu-id="d7b58-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d7b58-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="d7b58-108">S_OK</span></span>|<span data-ttu-id="d7b58-109">`Reset` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="d7b58-109">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="d7b58-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d7b58-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d7b58-111">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="d7b58-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d7b58-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d7b58-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d7b58-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="d7b58-113">The call timed out.</span></span>|  
|<span data-ttu-id="d7b58-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d7b58-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d7b58-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="d7b58-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d7b58-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d7b58-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d7b58-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="d7b58-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d7b58-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d7b58-118">E_FAIL</span></span>|<span data-ttu-id="d7b58-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d7b58-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d7b58-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d7b58-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d7b58-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="d7b58-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d7b58-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="d7b58-122">Requirements</span></span>  
 <span data-ttu-id="d7b58-123">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7b58-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7b58-124">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d7b58-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d7b58-125">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d7b58-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d7b58-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7b58-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7b58-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7b58-127">See also</span></span>

- [<span data-ttu-id="d7b58-128">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7b58-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="d7b58-129">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7b58-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="d7b58-130">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7b58-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="d7b58-131">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7b58-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="d7b58-132">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d7b58-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
