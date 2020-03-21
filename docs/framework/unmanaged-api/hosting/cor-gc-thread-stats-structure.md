---
title: COR_GC_THREAD_STATS 構造体
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS
helpviewer_keywords:
- COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type:
- apiref
ms.openlocfilehash: 64e0c466edcd8863244e6ed184c18422b5f66875
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178265"
---
# <a name="cor_gc_thread_stats-structure"></a><span data-ttu-id="12af8-102">COR_GC_THREAD_STATS 構造体</span><span class="sxs-lookup"><span data-stu-id="12af8-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="12af8-103">ガベージ コレクションに関連するスレッドごとの統計情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="12af8-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12af8-104">構文</span><span class="sxs-lookup"><span data-stu-id="12af8-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;
    ULONG      Flags;
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="12af8-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="12af8-105">Members</span></span>  
  
|<span data-ttu-id="12af8-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="12af8-106">Member</span></span>|<span data-ttu-id="12af8-107">説明</span><span class="sxs-lookup"><span data-stu-id="12af8-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="12af8-108">現在`COR_GC_THREAD_STATS`のインスタンスに関連付けられているスレッドに割り当てられたメモリのバイト数。</span><span class="sxs-lookup"><span data-stu-id="12af8-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="12af8-109">この数値は、ジェネレーション ゼロ ガベージ コレクションが発生するたびに 0 にクリアされます。</span><span class="sxs-lookup"><span data-stu-id="12af8-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="12af8-110">最新のガベージ コレクションで上位のジェネレーションに昇格されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="12af8-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12af8-111">解説</span><span class="sxs-lookup"><span data-stu-id="12af8-111">Remarks</span></span>  
 <span data-ttu-id="12af8-112">[型](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)の出力パラメーターを受け取ります`COR_GC_THREAD_STATS`。</span><span class="sxs-lookup"><span data-stu-id="12af8-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12af8-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="12af8-113">Requirements</span></span>  
 <span data-ttu-id="12af8-114">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12af8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12af8-115">**ヘッダー:** を行う</span><span class="sxs-lookup"><span data-stu-id="12af8-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="12af8-116">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="12af8-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12af8-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12af8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12af8-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="12af8-118">See also</span></span>

- [<span data-ttu-id="12af8-119">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="12af8-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="12af8-120">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="12af8-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
