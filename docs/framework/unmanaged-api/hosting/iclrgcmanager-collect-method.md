---
title: ICLRGCManager::Collect メソッド
ms.date: 03/30/2017
api_name:
- ICLRGCManager.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::Collect
helpviewer_keywords:
- ICLRGCManager::Collect method [.NET Framework hosting]
- Collect method, ICLRGCManager interface [.NET Framework hosting]
ms.assetid: 0c6cbbea-c27c-4695-bda3-17c1910d8ddb
topic_type:
- apiref
ms.openlocfilehash: a7dae98d1f2dc2448bd3a5df2d6143b7be0bb734
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129256"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="b0049-102">ICLRGCManager::Collect メソッド</span><span class="sxs-lookup"><span data-stu-id="b0049-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="b0049-103">指定したジェネレーションのガベージコレクションを強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="b0049-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0049-104">構文</span><span class="sxs-lookup"><span data-stu-id="b0049-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0049-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b0049-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="b0049-106">から収集するジェネレーション。</span><span class="sxs-lookup"><span data-stu-id="b0049-106">[in] The generation to collect.</span></span> <span data-ttu-id="b0049-107">値が-1 の場合は、すべてのジェネレーションのコレクションが強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="b0049-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0049-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="b0049-108">Return Value</span></span>  
  
|<span data-ttu-id="b0049-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b0049-109">HRESULT</span></span>|<span data-ttu-id="b0049-110">説明</span><span class="sxs-lookup"><span data-stu-id="b0049-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b0049-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0049-111">S_OK</span></span>|<span data-ttu-id="b0049-112">`Collect` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="b0049-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="b0049-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b0049-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b0049-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="b0049-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b0049-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b0049-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b0049-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="b0049-116">The call timed out.</span></span>|  
|<span data-ttu-id="b0049-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b0049-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b0049-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="b0049-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b0049-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b0049-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b0049-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="b0049-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b0049-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0049-121">E_FAIL</span></span>|<span data-ttu-id="b0049-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b0049-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b0049-123">メソッドから E_FAIL が返された後は、そのプロセス内で CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b0049-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b0049-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="b0049-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0049-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="b0049-125">Remarks</span></span>  
 <span data-ttu-id="b0049-126">`Collect` メソッドは、現在の状態に関係なく、CLR のガベージコレクターがコレクションを実行するように強制します。</span><span class="sxs-lookup"><span data-stu-id="b0049-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0049-127">［要件］</span><span class="sxs-lookup"><span data-stu-id="b0049-127">Requirements</span></span>  
 <span data-ttu-id="b0049-128">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0049-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0049-129">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b0049-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b0049-130">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b0049-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b0049-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0049-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0049-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0049-132">See also</span></span>

- [<span data-ttu-id="b0049-133">自動メモリ管理</span><span class="sxs-lookup"><span data-stu-id="b0049-133">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="b0049-134">ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="b0049-134">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="b0049-135">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b0049-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="b0049-136">ICLRGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b0049-136">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="b0049-137">CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b0049-137">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="b0049-138">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b0049-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="b0049-139">ホスティング</span><span class="sxs-lookup"><span data-stu-id="b0049-139">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
