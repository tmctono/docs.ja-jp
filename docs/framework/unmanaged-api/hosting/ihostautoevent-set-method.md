---
title: IHostAutoEvent::Set メソッド
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Set
helpviewer_keywords:
- Set method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Set method [.NET Framework hosting]
ms.assetid: 46becf3e-bc0e-4338-85c0-9ab0df76a1d0
topic_type:
- apiref
ms.openlocfilehash: 792b735522580eb7460da703899a00781e525419
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124445"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="11f18-102">IHostAutoEvent::Set メソッド</span><span class="sxs-lookup"><span data-stu-id="11f18-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="11f18-103">現在の[IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)インスタンスをシグナル状態に設定します。</span><span class="sxs-lookup"><span data-stu-id="11f18-103">Sets the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11f18-104">構文</span><span class="sxs-lookup"><span data-stu-id="11f18-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="11f18-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="11f18-105">Return Value</span></span>  
  
|<span data-ttu-id="11f18-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="11f18-106">HRESULT</span></span>|<span data-ttu-id="11f18-107">説明</span><span class="sxs-lookup"><span data-stu-id="11f18-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="11f18-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="11f18-108">S_OK</span></span>|<span data-ttu-id="11f18-109">`Set` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="11f18-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="11f18-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="11f18-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="11f18-111">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="11f18-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="11f18-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="11f18-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="11f18-113">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="11f18-113">The call timed out.</span></span>|  
|<span data-ttu-id="11f18-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="11f18-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="11f18-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="11f18-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="11f18-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="11f18-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="11f18-117">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="11f18-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="11f18-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="11f18-118">E_FAIL</span></span>|<span data-ttu-id="11f18-119">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="11f18-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="11f18-120">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="11f18-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="11f18-121">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="11f18-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="11f18-122">［要件］</span><span class="sxs-lookup"><span data-stu-id="11f18-122">Requirements</span></span>  
 <span data-ttu-id="11f18-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11f18-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11f18-124">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="11f18-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="11f18-125">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="11f18-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11f18-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11f18-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11f18-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="11f18-127">See also</span></span>

- [<span data-ttu-id="11f18-128">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11f18-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="11f18-129">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11f18-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="11f18-130">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11f18-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="11f18-131">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11f18-131">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
