---
title: ICorDebugHeapSegmentEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugHealRegionEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum
helpviewer_keywords:
- ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 20fc1b9d-e228-4107-bd76-53934c1724b9
topic_type:
- apiref
ms.openlocfilehash: e9679029cd54ac44832add9bc4f47f8c8e9a26a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138448"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="63a75-102">ICorDebugHeapSegmentEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="63a75-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="63a75-103">マネージド ヒープのメモリ領域の列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="63a75-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="63a75-104">このインターフェイスは、ICorDebugEnum インターフェイスのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="63a75-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="63a75-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="63a75-105">Methods</span></span>  
  
|<span data-ttu-id="63a75-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="63a75-106">Method</span></span>|<span data-ttu-id="63a75-107">説明</span><span class="sxs-lookup"><span data-stu-id="63a75-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="63a75-108">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="63a75-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="63a75-109">マネージヒープの領域に関する情報を格納している、指定した数の[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="63a75-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63a75-110">コメント</span><span class="sxs-lookup"><span data-stu-id="63a75-110">Remarks</span></span>  
 <span data-ttu-id="63a75-111">`ICorDebugHeapSegmentEnum` インターフェイスは、ICorDebugEnum インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="63a75-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="63a75-112">[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) インスタンスには、 [ICorDebugProcess5:: EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)メソッドを呼び出すことによって、 インスタンスが設定されます。 `ICorDebugHeapSegmentEnum`</span><span class="sxs-lookup"><span data-stu-id="63a75-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="63a75-113">コレクション内の[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)オブジェクトは、 [ICorDebugHeapSegmentEnum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)メソッドを呼び出すことによって列挙できます。</span><span class="sxs-lookup"><span data-stu-id="63a75-113">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="63a75-114">`ICorDebugHeapSegmentEnum` collection オブジェクトは、マネージオブジェクトが含まれている可能性があるすべてのメモリ領域を列挙しますが、それらの領域にマネージオブジェクトが実際に存在することは保証しません。</span><span class="sxs-lookup"><span data-stu-id="63a75-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="63a75-115">これには、空または予約済みのメモリ領域に関する情報が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="63a75-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63a75-116">要件</span><span class="sxs-lookup"><span data-stu-id="63a75-116">Requirements</span></span>  
 <span data-ttu-id="63a75-117">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63a75-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63a75-118">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="63a75-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63a75-119">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="63a75-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63a75-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63a75-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63a75-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="63a75-121">See also</span></span>

- [<span data-ttu-id="63a75-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="63a75-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
