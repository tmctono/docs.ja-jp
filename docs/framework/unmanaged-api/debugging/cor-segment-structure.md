---
title: COR_SEGMENT 構造体
ms.date: 03/30/2017
api_name:
- COR_SEGMENT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_SEGMENT
helpviewer_keywords:
- COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: faf1be65d308b223490f3ae67eed3d8a2b1688b9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223070"
---
# <a name="corsegment-structure"></a><span data-ttu-id="3ddba-102">COR_SEGMENT 構造体</span><span class="sxs-lookup"><span data-stu-id="3ddba-102">COR_SEGMENT Structure</span></span>
<span data-ttu-id="3ddba-103">マネージド ヒープのメモリ領域に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3ddba-103">Contains information about a region of memory in the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ddba-104">構文</span><span class="sxs-lookup"><span data-stu-id="3ddba-104">Syntax</span></span>  
  
```  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a><span data-ttu-id="3ddba-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="3ddba-105">Members</span></span>  
  
|<span data-ttu-id="3ddba-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="3ddba-106">Member</span></span>|<span data-ttu-id="3ddba-107">説明</span><span class="sxs-lookup"><span data-stu-id="3ddba-107">Description</span></span>|  
|------------|-----------------|  
|`start`|<span data-ttu-id="3ddba-108">メモリ領域の開始アドレス。</span><span class="sxs-lookup"><span data-stu-id="3ddba-108">The starting address of the memory region.</span></span>|  
|`end`|<span data-ttu-id="3ddba-109">メモリ領域の終了アドレス。</span><span class="sxs-lookup"><span data-stu-id="3ddba-109">The ending address of the memory region.</span></span>|  
|`gen`|<span data-ttu-id="3ddba-110">メモリ領域の生成を示す [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) 列挙メンバー。</span><span class="sxs-lookup"><span data-stu-id="3ddba-110">A [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) enumeration member that indicates the generation of the memory region.</span></span>|  
|`heap`|<span data-ttu-id="3ddba-111">メモリ領域が存在するヒープ番号。</span><span class="sxs-lookup"><span data-stu-id="3ddba-111">The heap number in which the memory region resides.</span></span> <span data-ttu-id="3ddba-112">詳細については、次の「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ddba-112">See the Remarks section for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ddba-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="3ddba-113">Remarks</span></span>  
 <span data-ttu-id="3ddba-114">`COR_SEGMENTS` 構造体は、マネージド ヒープのメモリ領域を表します。</span><span class="sxs-lookup"><span data-stu-id="3ddba-114">The `COR_SEGMENTS` structure represents a region of memory in the managed heap.</span></span>  <span data-ttu-id="3ddba-115">`COR_SEGMENTS` オブジェクトは、[ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) メソッドを呼び出すことによって入力される [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) コレクション オブジェクトのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="3ddba-115">`COR_SEGMENTS` objects are members of the [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object, which is populated by calling the [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span>  
  
 <span data-ttu-id="3ddba-116">`heap` フィールドは、報告されたヒープに対応するプロセッサ番号です。</span><span class="sxs-lookup"><span data-stu-id="3ddba-116">The `heap` field is the processor number, which corresponds to the heap being reported.</span></span> <span data-ttu-id="3ddba-117">ワークステーション ガベージ コレクターでは、ワークステーションにガベージ コレクション ヒープが 1 つしかないため、その値は常に 0 です。</span><span class="sxs-lookup"><span data-stu-id="3ddba-117">For workstation garbage collectors, its value is always zero, because workstations have only one garbage collection heap.</span></span> <span data-ttu-id="3ddba-118">サーバー ガベージ コレクターでは、その値はヒープがアタッチされているプロセッサに対応します。</span><span class="sxs-lookup"><span data-stu-id="3ddba-118">For server garbage collectors, its value corresponds to the processor the heap is attached to.</span></span> <span data-ttu-id="3ddba-119">ガベージ コレクターの実装の詳細が原因で、実際のプロセッサ数よりも、ガベージ コレクション ヒープが多かったり少なかったりする場合があります。</span><span class="sxs-lookup"><span data-stu-id="3ddba-119">Note that there may be more or fewer garbage collection heaps than there are actual processors due to the implementation details of the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ddba-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="3ddba-120">Requirements</span></span>  
 <span data-ttu-id="3ddba-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ddba-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ddba-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ddba-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ddba-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ddba-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ddba-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ddba-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ddba-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ddba-125">See also</span></span>

- [<span data-ttu-id="3ddba-126">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="3ddba-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="3ddba-127">デバッグ</span><span class="sxs-lookup"><span data-stu-id="3ddba-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
