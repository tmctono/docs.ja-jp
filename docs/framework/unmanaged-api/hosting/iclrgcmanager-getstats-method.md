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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9df9263a0356b0c3c1a6d1da950c670f5a020d1e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966227"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="2a362-102">ICLRGCManager::GetStats メソッド</span><span class="sxs-lookup"><span data-stu-id="2a362-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="2a362-103">共通言語ランタイムのガベージコレクションシステムに関する現在の統計のセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="2a362-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a362-104">構文</span><span class="sxs-lookup"><span data-stu-id="2a362-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a362-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2a362-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="2a362-106">[入力、出力]要求された統計情報を含む[COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="2a362-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a362-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="2a362-107">Return Value</span></span>  
  
|<span data-ttu-id="2a362-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2a362-108">HRESULT</span></span>|<span data-ttu-id="2a362-109">説明</span><span class="sxs-lookup"><span data-stu-id="2a362-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2a362-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2a362-110">S_OK</span></span>|<span data-ttu-id="2a362-111">`GetStats`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="2a362-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="2a362-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2a362-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2a362-113">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="2a362-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2a362-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2a362-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2a362-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="2a362-115">The call timed out.</span></span>|  
|<span data-ttu-id="2a362-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2a362-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2a362-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="2a362-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2a362-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2a362-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2a362-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="2a362-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2a362-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2a362-120">E_FAIL</span></span>|<span data-ttu-id="2a362-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="2a362-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2a362-122">メソッドから E_FAIL が返された後は、そのプロセス内で CLR を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2a362-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2a362-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="2a362-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a362-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="2a362-124">Remarks</span></span>  
 <span data-ttu-id="2a362-125">CLR は、の`Flags` `pStats`フィールドによって指定された統計のみを計算して返します。</span><span class="sxs-lookup"><span data-stu-id="2a362-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="2a362-126">フィールドを、 [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)列挙体の1つ以上の値に設定して、[COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) 構造内のどの統計情報を設定するかを指定します。`Flags`</span><span class="sxs-lookup"><span data-stu-id="2a362-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="2a362-127">使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2a362-127">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="2a362-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="2a362-128">Requirements</span></span>  
 <span data-ttu-id="2a362-129">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a362-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a362-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2a362-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a362-131">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="2a362-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a362-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a362-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a362-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a362-133">See also</span></span>

- [<span data-ttu-id="2a362-134">自動メモリ管理</span><span class="sxs-lookup"><span data-stu-id="2a362-134">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="2a362-135">COR_GC_STATS 構造体</span><span class="sxs-lookup"><span data-stu-id="2a362-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="2a362-136">COR_GC_STAT_TYPES 列挙型</span><span class="sxs-lookup"><span data-stu-id="2a362-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="2a362-137">ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="2a362-137">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="2a362-138">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a362-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="2a362-139">ICLRGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a362-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="2a362-140">CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a362-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="2a362-141">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a362-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="2a362-142">ホスティング</span><span class="sxs-lookup"><span data-stu-id="2a362-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
