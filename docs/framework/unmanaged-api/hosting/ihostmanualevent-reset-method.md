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
ms.openlocfilehash: 464093291648d7c5c1f2001fbaef85fcd5d592de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136803"
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="5bd51-102">IHostManualEvent::Reset メソッド</span><span class="sxs-lookup"><span data-stu-id="5bd51-102">IHostManualEvent::Reset Method</span></span>
<span data-ttu-id="5bd51-103">現在の[IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)インスタンスを非シグナル状態にリセットします。</span><span class="sxs-lookup"><span data-stu-id="5bd51-103">Resets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bd51-104">構文</span><span class="sxs-lookup"><span data-stu-id="5bd51-104">Syntax</span></span>  
  
```cpp  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5bd51-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="5bd51-105">Return Value</span></span>  
  
|<span data-ttu-id="5bd51-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5bd51-106">HRESULT</span></span>|<span data-ttu-id="5bd51-107">説明</span><span class="sxs-lookup"><span data-stu-id="5bd51-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5bd51-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="5bd51-108">S_OK</span></span>|<span data-ttu-id="5bd51-109">`Reset` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="5bd51-109">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="5bd51-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5bd51-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5bd51-111">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="5bd51-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5bd51-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5bd51-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5bd51-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="5bd51-113">The call timed out.</span></span>|  
|<span data-ttu-id="5bd51-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5bd51-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5bd51-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="5bd51-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5bd51-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5bd51-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5bd51-117">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="5bd51-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5bd51-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5bd51-118">E_FAIL</span></span>|<span data-ttu-id="5bd51-119">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5bd51-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5bd51-120">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5bd51-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5bd51-121">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="5bd51-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5bd51-122">［要件］</span><span class="sxs-lookup"><span data-stu-id="5bd51-122">Requirements</span></span>  
 <span data-ttu-id="5bd51-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bd51-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bd51-124">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5bd51-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5bd51-125">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="5bd51-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5bd51-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bd51-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bd51-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="5bd51-127">See also</span></span>

- [<span data-ttu-id="5bd51-128">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5bd51-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="5bd51-129">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5bd51-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="5bd51-130">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5bd51-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="5bd51-131">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5bd51-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="5bd51-132">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5bd51-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
