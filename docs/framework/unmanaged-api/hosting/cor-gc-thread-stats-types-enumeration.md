---
title: COR_GC_THREAD_STATS_TYPES 列挙体
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS_TYPES
helpviewer_keywords:
- COR_GC_THREAD_STATS_TYPES enumeration [.NET Framework hosting]
ms.assetid: aa227704-0ab1-4b08-aee2-1f439762162e
topic_type:
- apiref
ms.openlocfilehash: 2206499cad9be2a29f485ee66d468accbe00b5f5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616685"
---
# <a name="cor_gc_thread_stats_types-enumeration"></a><span data-ttu-id="ae71d-102">COR_GC_THREAD_STATS_TYPES 列挙体</span><span class="sxs-lookup"><span data-stu-id="ae71d-102">COR_GC_THREAD_STATS_TYPES Enumeration</span></span>
<span data-ttu-id="ae71d-103">スレッドのガベージコレクションの統計を示します。</span><span class="sxs-lookup"><span data-stu-id="ae71d-103">Indicates the garbage collection statistics for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae71d-104">構文</span><span class="sxs-lookup"><span data-stu-id="ae71d-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a><span data-ttu-id="ae71d-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="ae71d-105">Members</span></span>  
  
|<span data-ttu-id="ae71d-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="ae71d-106">Member</span></span>|<span data-ttu-id="ae71d-107">説明</span><span class="sxs-lookup"><span data-stu-id="ae71d-107">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|<span data-ttu-id="ae71d-108">スレッドには、最新のガベージコレクションで昇格されたバイト数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ae71d-108">The thread has bytes that were promoted in the most recent garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ae71d-109">要件</span><span class="sxs-lookup"><span data-stu-id="ae71d-109">Requirements</span></span>  
 <span data-ttu-id="ae71d-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae71d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae71d-111">**ヘッダー:** GCHost、GCHost</span><span class="sxs-lookup"><span data-stu-id="ae71d-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="ae71d-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae71d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae71d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae71d-113">See also</span></span>

- [<span data-ttu-id="ae71d-114">ホスティングの列挙体</span><span class="sxs-lookup"><span data-stu-id="ae71d-114">Hosting Enumerations</span></span>](hosting-enumerations.md)
