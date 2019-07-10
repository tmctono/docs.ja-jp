---
title: IHostManualEvent::Set メソッド
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Set
helpviewer_keywords:
- Set method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Set method [.NET Framework hosting]
ms.assetid: e930c174-f71d-4faa-bb59-f0fb3df4d77b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3756ed3bc7863411849b9d733da816e567a86628
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767307"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="1553a-102">IHostManualEvent::Set メソッド</span><span class="sxs-lookup"><span data-stu-id="1553a-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="1553a-103">現在の設定[IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)インスタンスがシグナル状態にします。</span><span class="sxs-lookup"><span data-stu-id="1553a-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1553a-104">構文</span><span class="sxs-lookup"><span data-stu-id="1553a-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1553a-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="1553a-105">Return Value</span></span>  
  
|<span data-ttu-id="1553a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1553a-106">HRESULT</span></span>|<span data-ttu-id="1553a-107">説明</span><span class="sxs-lookup"><span data-stu-id="1553a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1553a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="1553a-108">S_OK</span></span>|<span data-ttu-id="1553a-109">`Set` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="1553a-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="1553a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1553a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1553a-111">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="1553a-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1553a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1553a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1553a-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="1553a-113">The call timed out.</span></span>|  
|<span data-ttu-id="1553a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1553a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1553a-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="1553a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1553a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1553a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1553a-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="1553a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1553a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1553a-118">E_FAIL</span></span>|<span data-ttu-id="1553a-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="1553a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1553a-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="1553a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1553a-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="1553a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1553a-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="1553a-122">Requirements</span></span>  
 <span data-ttu-id="1553a-123">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1553a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1553a-124">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1553a-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1553a-125">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="1553a-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1553a-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1553a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1553a-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="1553a-127">See also</span></span>

- [<span data-ttu-id="1553a-128">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1553a-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="1553a-129">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1553a-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="1553a-130">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1553a-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="1553a-131">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1553a-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="1553a-132">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1553a-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
