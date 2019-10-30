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
ms.openlocfilehash: 36eeb7ed4f80979ef2edb930e65963a1db0c894f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134905"
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="e0043-102">IGCHost::GetThreadStats メソッド</span><span class="sxs-lookup"><span data-stu-id="e0043-102">IGCHost::GetThreadStats Method</span></span>
<span data-ttu-id="e0043-103">ガベージコレクションのスレッドごとの統計を取得します。</span><span class="sxs-lookup"><span data-stu-id="e0043-103">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0043-104">構文</span><span class="sxs-lookup"><span data-stu-id="e0043-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0043-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e0043-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="e0043-106">から統計を取得するスレッドを指定するファイバークッキーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e0043-106">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="e0043-107">[入力、出力]指定したスレッドのガベージコレクションの統計情報を格納している[COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md)構造体へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e0043-107">[in, out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0043-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="e0043-108">Requirements</span></span>  
 <span data-ttu-id="e0043-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0043-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0043-110">**ヘッダー:** GCHost、GCHost</span><span class="sxs-lookup"><span data-stu-id="e0043-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="e0043-111">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="e0043-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0043-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0043-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0043-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0043-113">See also</span></span>

- [<span data-ttu-id="e0043-114">IGCHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0043-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
