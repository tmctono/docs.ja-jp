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
ms.openlocfilehash: 9300f67e75d40f041a4fba52f6742741ec9f91de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187339"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="7deec-102">ICLRGCManager::GetStats メソッド</span><span class="sxs-lookup"><span data-stu-id="7deec-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="7deec-103">共通言語ランタイムのガベージ コレクション システムに関する現在の統計情報のセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="7deec-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7deec-104">構文</span><span class="sxs-lookup"><span data-stu-id="7deec-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7deec-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7deec-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="7deec-106">[入力、出力]A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)要求の統計情報を格納しているインスタンス。</span><span class="sxs-lookup"><span data-stu-id="7deec-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7deec-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="7deec-107">Return Value</span></span>  
  
|<span data-ttu-id="7deec-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7deec-108">HRESULT</span></span>|<span data-ttu-id="7deec-109">説明</span><span class="sxs-lookup"><span data-stu-id="7deec-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7deec-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7deec-110">S_OK</span></span>|<span data-ttu-id="7deec-111">`GetStats` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="7deec-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="7deec-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7deec-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7deec-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="7deec-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7deec-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7deec-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7deec-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="7deec-115">The call timed out.</span></span>|  
|<span data-ttu-id="7deec-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7deec-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7deec-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="7deec-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7deec-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7deec-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7deec-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="7deec-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7deec-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7deec-120">E_FAIL</span></span>|<span data-ttu-id="7deec-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7deec-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7deec-122">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="7deec-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7deec-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="7deec-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7deec-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="7deec-124">Remarks</span></span>  
 <span data-ttu-id="7deec-125">CLR を計算しで指定されている統計情報のみを返す、`Flags`フィールド`pStats`します。</span><span class="sxs-lookup"><span data-stu-id="7deec-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="7deec-126">設定、`Flags`フィールドの 1 つまたは複数の値を[COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)で統計情報を指定する列挙体、 [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)は、構造体を設定します。</span><span class="sxs-lookup"><span data-stu-id="7deec-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="7deec-127">使用状況の例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7deec-127">An example of the usage is as follows:</span></span>  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="7deec-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="7deec-128">Requirements</span></span>  
 <span data-ttu-id="7deec-129">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7deec-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7deec-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7deec-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7deec-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="7deec-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7deec-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7deec-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7deec-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="7deec-133">See also</span></span>

- [<span data-ttu-id="7deec-134">自動メモリ管理</span><span class="sxs-lookup"><span data-stu-id="7deec-134">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="7deec-135">COR_GC_STATS 構造体</span><span class="sxs-lookup"><span data-stu-id="7deec-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="7deec-136">COR_GC_STAT_TYPES 列挙型</span><span class="sxs-lookup"><span data-stu-id="7deec-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="7deec-137">ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="7deec-137">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="7deec-138">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7deec-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="7deec-139">ICLRGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7deec-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="7deec-140">CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7deec-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="7deec-141">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7deec-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="7deec-142">ホスティング</span><span class="sxs-lookup"><span data-stu-id="7deec-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
