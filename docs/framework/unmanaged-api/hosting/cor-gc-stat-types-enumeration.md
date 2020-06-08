---
title: COR_GC_STAT_TYPES 列挙体
ms.date: 03/30/2017
api_name:
- COR_GC_STAT_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STAT_TYPES
helpviewer_keywords:
- COR_GC_STAT_TYPES enumeration [.NET Framework hosting]
ms.assetid: fc51d6db-f7f8-408b-b93d-c166fc712c99
topic_type:
- apiref
ms.openlocfilehash: d7e78dfc4beba67cc376b221d0cd49f7200f5d23
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501704"
---
# <a name="cor_gc_stat_types-enumeration"></a><span data-ttu-id="5e75d-102">COR_GC_STAT_TYPES 列挙体</span><span class="sxs-lookup"><span data-stu-id="5e75d-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="5e75d-103">ガベージコレクション用に記録する統計を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e75d-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e75d-104">構文</span><span class="sxs-lookup"><span data-stu-id="5e75d-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="5e75d-105">解説</span><span class="sxs-lookup"><span data-stu-id="5e75d-105">Remarks</span></span>  
 <span data-ttu-id="5e75d-106">この列挙体は、 [ICLRGCManager:: GetStats](iclrgcmanager-getstats-method.md)メソッドによって設定される[COR_GC_STATS](cor-gc-stats-structure.md)構造内の統計を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e75d-106">This enumeration specifies which statistics in the [COR_GC_STATS](cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="5e75d-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="5e75d-107">Members</span></span>  
  
|<span data-ttu-id="5e75d-108">メンバー</span><span class="sxs-lookup"><span data-stu-id="5e75d-108">Member</span></span>|<span data-ttu-id="5e75d-109">説明</span><span class="sxs-lookup"><span data-stu-id="5e75d-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="5e75d-110">生成されるたびに実行されるガベージコレクションの数を記録します。</span><span class="sxs-lookup"><span data-stu-id="5e75d-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="5e75d-111">メモリ使用量とガベージコレクションサイズの統計情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="5e75d-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5e75d-112">要件</span><span class="sxs-lookup"><span data-stu-id="5e75d-112">Requirements</span></span>  
 <span data-ttu-id="5e75d-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e75d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e75d-114">**ヘッダー:** GCHost、GCHost</span><span class="sxs-lookup"><span data-stu-id="5e75d-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="5e75d-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e75d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e75d-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e75d-116">See also</span></span>

- [<span data-ttu-id="5e75d-117">COR_GC_STATS 構造体</span><span class="sxs-lookup"><span data-stu-id="5e75d-117">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="5e75d-118">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="5e75d-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
