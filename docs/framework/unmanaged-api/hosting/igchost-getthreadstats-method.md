---
title: IGCHost::GetThreadStats メソッド
ms.date: 03/30/2017
api_name:
- IGCHost.GetThreadStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetThreadStats
helpviewer_keywords:
- IGCHost::GetThreadStats method [.NET Framework hosting]
- GetThreadStats method [.NET Framework hosting]
ms.assetid: 826baa9b-9218-4736-a509-7ab193b125a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 87e318c4f2367e8c66910978f4a9c89f36c95632
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766509"
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="881b5-102">IGCHost::GetThreadStats メソッド</span><span class="sxs-lookup"><span data-stu-id="881b5-102">IGCHost::GetThreadStats Method</span></span>
<span data-ttu-id="881b5-103">ガベージ コレクションのスレッドごとの統計情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="881b5-103">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="881b5-104">構文</span><span class="sxs-lookup"><span data-stu-id="881b5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="881b5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="881b5-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="881b5-106">[in]統計情報を取得する対象のスレッドを示すファイバー cookie へのポインター。</span><span class="sxs-lookup"><span data-stu-id="881b5-106">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="881b5-107">[入力、出力]ポインターを[COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md)の指定したスレッドのガベージ コレクションの統計情報を含む構造体。</span><span class="sxs-lookup"><span data-stu-id="881b5-107">[in, out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="881b5-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="881b5-108">Requirements</span></span>  
 <span data-ttu-id="881b5-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="881b5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="881b5-110">**ヘッダー:** GCHost.idl、GCHost.h</span><span class="sxs-lookup"><span data-stu-id="881b5-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="881b5-111">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="881b5-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="881b5-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="881b5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="881b5-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="881b5-113">See also</span></span>

- [<span data-ttu-id="881b5-114">IGCHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="881b5-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
