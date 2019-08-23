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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3064a5793c6158ead85a9ff6d9b09f077d0bd603
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966239"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="5c1cb-102">ICLRGCManager::Collect メソッド</span><span class="sxs-lookup"><span data-stu-id="5c1cb-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="5c1cb-103">指定したジェネレーションのガベージコレクションを強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="5c1cb-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c1cb-104">構文</span><span class="sxs-lookup"><span data-stu-id="5c1cb-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c1cb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5c1cb-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="5c1cb-106">から収集するジェネレーション。</span><span class="sxs-lookup"><span data-stu-id="5c1cb-106">[in] The generation to collect.</span></span> <span data-ttu-id="5c1cb-107">値が-1 の場合は、すべてのジェネレーションのコレクションが強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="5c1cb-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5c1cb-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="5c1cb-108">Return Value</span></span>  
  
|<span data-ttu-id="5c1cb-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5c1cb-109">HRESULT</span></span>|<span data-ttu-id="5c1cb-110">説明</span><span class="sxs-lookup"><span data-stu-id="5c1cb-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5c1cb-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5c1cb-111">S_OK</span></span>|<span data-ttu-id="5c1cb-112">`Collect`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="5c1cb-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="5c1cb-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5c1cb-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5c1cb-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="5c1cb-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5c1cb-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5c1cb-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5c1cb-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="5c1cb-116">The call timed out.</span></span>|  
|<span data-ttu-id="5c1cb-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5c1cb-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5c1cb-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="5c1cb-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5c1cb-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5c1cb-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5c1cb-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="5c1cb-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5c1cb-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5c1cb-121">E_FAIL</span></span>|<span data-ttu-id="5c1cb-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5c1cb-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5c1cb-123">メソッドから E_FAIL が返された後は、そのプロセス内で CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5c1cb-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5c1cb-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="5c1cb-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c1cb-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="5c1cb-125">Remarks</span></span>  
 <span data-ttu-id="5c1cb-126">メソッド`Collect`は、現在の状態に関係なく、CLR のガベージコレクターがコレクションを実行するように強制します。</span><span class="sxs-lookup"><span data-stu-id="5c1cb-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c1cb-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="5c1cb-127">Requirements</span></span>  
 <span data-ttu-id="5c1cb-128">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c1cb-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c1cb-129">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5c1cb-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5c1cb-130">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="5c1cb-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c1cb-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c1cb-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c1cb-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c1cb-132">See also</span></span>

- [<span data-ttu-id="5c1cb-133">自動メモリ管理</span><span class="sxs-lookup"><span data-stu-id="5c1cb-133">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="5c1cb-134">ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="5c1cb-134">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="5c1cb-135">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c1cb-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="5c1cb-136">ICLRGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c1cb-136">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="5c1cb-137">CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c1cb-137">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="5c1cb-138">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5c1cb-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="5c1cb-139">ホスティング</span><span class="sxs-lookup"><span data-stu-id="5c1cb-139">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
