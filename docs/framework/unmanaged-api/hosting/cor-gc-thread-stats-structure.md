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
ms.openlocfilehash: 88e81779fc9c20c506f3b0aa11ac2da3958dfe86
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616698"
---
# <a name="cor_gc_thread_stats-structure"></a><span data-ttu-id="06e58-102">COR_GC_THREAD_STATS 構造体</span><span class="sxs-lookup"><span data-stu-id="06e58-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="06e58-103">ガベージコレクションに関連するスレッドごとの統計情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="06e58-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06e58-104">構文</span><span class="sxs-lookup"><span data-stu-id="06e58-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;
    ULONG      Flags;
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="06e58-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="06e58-105">Members</span></span>  
  
|<span data-ttu-id="06e58-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="06e58-106">Member</span></span>|<span data-ttu-id="06e58-107">説明</span><span class="sxs-lookup"><span data-stu-id="06e58-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="06e58-108">現在のインスタンスに関連付けられているスレッドに割り当てられたメモリのバイト数 `COR_GC_THREAD_STATS` 。</span><span class="sxs-lookup"><span data-stu-id="06e58-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="06e58-109">ジェネレーション0のガベージコレクションが発生するたびに、この数値はゼロにクリアされます。</span><span class="sxs-lookup"><span data-stu-id="06e58-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="06e58-110">最新のガベージコレクションで上位のジェネレーションに昇格されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="06e58-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06e58-111">解説</span><span class="sxs-lookup"><span data-stu-id="06e58-111">Remarks</span></span>  
 <span data-ttu-id="06e58-112">[ICLRTask:: GetMemStats](iclrtask-getmemstats-method.md)は、型の出力パラメーターを受け取り `COR_GC_THREAD_STATS` ます。</span><span class="sxs-lookup"><span data-stu-id="06e58-112">[ICLRTask::GetMemStats](iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06e58-113">要件</span><span class="sxs-lookup"><span data-stu-id="06e58-113">Requirements</span></span>  
 <span data-ttu-id="06e58-114">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06e58-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06e58-115">**ヘッダー:** GCHost</span><span class="sxs-lookup"><span data-stu-id="06e58-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="06e58-116">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="06e58-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06e58-117">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06e58-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06e58-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="06e58-118">See also</span></span>

- [<span data-ttu-id="06e58-119">ホスト構造体</span><span class="sxs-lookup"><span data-stu-id="06e58-119">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="06e58-120">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="06e58-120">IHostTask Interface</span></span>](ihosttask-interface.md)
