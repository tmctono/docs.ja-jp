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
ms.openlocfilehash: 1114fc744ac1811585f2c5a94858b75eda00815c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136758"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="de3a2-102">IHostManualEvent::Set メソッド</span><span class="sxs-lookup"><span data-stu-id="de3a2-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="de3a2-103">現在の[IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)インスタンスをシグナル状態に設定します。</span><span class="sxs-lookup"><span data-stu-id="de3a2-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de3a2-104">構文</span><span class="sxs-lookup"><span data-stu-id="de3a2-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="de3a2-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="de3a2-105">Return Value</span></span>  
  
|<span data-ttu-id="de3a2-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="de3a2-106">HRESULT</span></span>|<span data-ttu-id="de3a2-107">説明</span><span class="sxs-lookup"><span data-stu-id="de3a2-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="de3a2-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="de3a2-108">S_OK</span></span>|<span data-ttu-id="de3a2-109">`Set` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="de3a2-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="de3a2-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="de3a2-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="de3a2-111">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="de3a2-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="de3a2-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="de3a2-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="de3a2-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="de3a2-113">The call timed out.</span></span>|  
|<span data-ttu-id="de3a2-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="de3a2-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="de3a2-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="de3a2-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="de3a2-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="de3a2-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="de3a2-117">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="de3a2-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="de3a2-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="de3a2-118">E_FAIL</span></span>|<span data-ttu-id="de3a2-119">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="de3a2-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="de3a2-120">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="de3a2-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="de3a2-121">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="de3a2-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="de3a2-122">［要件］</span><span class="sxs-lookup"><span data-stu-id="de3a2-122">Requirements</span></span>  
 <span data-ttu-id="de3a2-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de3a2-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de3a2-124">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="de3a2-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="de3a2-125">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="de3a2-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="de3a2-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de3a2-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de3a2-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="de3a2-127">See also</span></span>

- [<span data-ttu-id="de3a2-128">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de3a2-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="de3a2-129">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de3a2-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="de3a2-130">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de3a2-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="de3a2-131">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de3a2-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="de3a2-132">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de3a2-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
