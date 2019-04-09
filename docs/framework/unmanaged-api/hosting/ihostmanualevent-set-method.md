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
ms.openlocfilehash: 674745636033f42eb8fb67babf6f5a3f013491c0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093502"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="8e109-102">IHostManualEvent::Set メソッド</span><span class="sxs-lookup"><span data-stu-id="8e109-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="8e109-103">現在の設定[IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)インスタンスがシグナル状態にします。</span><span class="sxs-lookup"><span data-stu-id="8e109-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e109-104">構文</span><span class="sxs-lookup"><span data-stu-id="8e109-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8e109-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="8e109-105">Return Value</span></span>  
  
|<span data-ttu-id="8e109-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8e109-106">HRESULT</span></span>|<span data-ttu-id="8e109-107">説明</span><span class="sxs-lookup"><span data-stu-id="8e109-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8e109-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="8e109-108">S_OK</span></span>|`Set` <span data-ttu-id="8e109-109">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="8e109-109">returned successfully.</span></span>|  
|<span data-ttu-id="8e109-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8e109-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8e109-111">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="8e109-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8e109-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8e109-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8e109-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="8e109-113">The call timed out.</span></span>|  
|<span data-ttu-id="8e109-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8e109-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8e109-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="8e109-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8e109-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8e109-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8e109-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="8e109-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8e109-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8e109-118">E_FAIL</span></span>|<span data-ttu-id="8e109-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="8e109-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8e109-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="8e109-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8e109-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="8e109-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8e109-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="8e109-122">Requirements</span></span>  
 <span data-ttu-id="8e109-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e109-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e109-124">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8e109-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e109-125">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="8e109-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="8e109-126">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="8e109-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8e109-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e109-127">See also</span></span>

- [<span data-ttu-id="8e109-128">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8e109-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="8e109-129">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8e109-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="8e109-130">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8e109-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="8e109-131">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8e109-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="8e109-132">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8e109-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
