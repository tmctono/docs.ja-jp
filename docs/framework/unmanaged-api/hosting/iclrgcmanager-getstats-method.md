---
title: ICLRGCManager::GetStats メソッド
ms.date: 03/30/2017
api_name:
- ICLRGCManager.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::GetStats
helpviewer_keywords:
- GetStats method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::GetStats method [.NET Framework hosting]
ms.assetid: ce259d1d-cd81-4490-a7a1-0d0ea0804872
topic_type:
- apiref
ms.openlocfilehash: 9e8b65c735028029f4fb44c2640df74ef171d9de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141141"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="cc2ef-102">ICLRGCManager::GetStats メソッド</span><span class="sxs-lookup"><span data-stu-id="cc2ef-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="cc2ef-103">共通言語ランタイムのガベージコレクションシステムに関する現在の統計のセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="cc2ef-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc2ef-104">構文</span><span class="sxs-lookup"><span data-stu-id="cc2ef-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc2ef-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cc2ef-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="cc2ef-106">[入力、出力]要求された統計情報を含む[COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="cc2ef-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc2ef-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="cc2ef-107">Return Value</span></span>  
  
|<span data-ttu-id="cc2ef-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cc2ef-108">HRESULT</span></span>|<span data-ttu-id="cc2ef-109">説明</span><span class="sxs-lookup"><span data-stu-id="cc2ef-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cc2ef-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cc2ef-110">S_OK</span></span>|<span data-ttu-id="cc2ef-111">`GetStats` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="cc2ef-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="cc2ef-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cc2ef-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cc2ef-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="cc2ef-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cc2ef-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cc2ef-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cc2ef-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="cc2ef-115">The call timed out.</span></span>|  
|<span data-ttu-id="cc2ef-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cc2ef-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cc2ef-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="cc2ef-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cc2ef-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cc2ef-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cc2ef-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="cc2ef-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cc2ef-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cc2ef-120">E_FAIL</span></span>|<span data-ttu-id="cc2ef-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="cc2ef-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cc2ef-122">メソッドから E_FAIL が返された後は、そのプロセス内で CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="cc2ef-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cc2ef-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="cc2ef-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc2ef-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="cc2ef-124">Remarks</span></span>  
 <span data-ttu-id="cc2ef-125">CLR は、`pStats`の `Flags` フィールドによって指定された統計のみを計算して返します。</span><span class="sxs-lookup"><span data-stu-id="cc2ef-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="cc2ef-126">[`Flags`] フィールドを[COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)列挙の1つ以上の値に設定して、 [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)構造のどの統計を設定するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="cc2ef-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="cc2ef-127">使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cc2ef-127">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="cc2ef-128">［要件］</span><span class="sxs-lookup"><span data-stu-id="cc2ef-128">Requirements</span></span>  
 <span data-ttu-id="cc2ef-129">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc2ef-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc2ef-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="cc2ef-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cc2ef-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="cc2ef-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc2ef-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc2ef-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc2ef-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc2ef-133">See also</span></span>

- [<span data-ttu-id="cc2ef-134">自動メモリ管理</span><span class="sxs-lookup"><span data-stu-id="cc2ef-134">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="cc2ef-135">COR_GC_STATS 構造体</span><span class="sxs-lookup"><span data-stu-id="cc2ef-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="cc2ef-136">COR_GC_STAT_TYPES 列挙型</span><span class="sxs-lookup"><span data-stu-id="cc2ef-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="cc2ef-137">ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="cc2ef-137">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="cc2ef-138">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cc2ef-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="cc2ef-139">ICLRGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cc2ef-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="cc2ef-140">CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cc2ef-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="cc2ef-141">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cc2ef-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="cc2ef-142">ホスティング</span><span class="sxs-lookup"><span data-stu-id="cc2ef-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
