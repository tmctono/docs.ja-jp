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
ms.openlocfilehash: 98e3351c9c86961d11b0985117259d0ff3b609ae
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794419"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="0e2a9-102">ICorDebugHeapSegmentEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0e2a9-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="0e2a9-103">マネージド ヒープのメモリ領域の列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="0e2a9-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="0e2a9-104">このインターフェイスは、ICorDebugEnum インターフェイスのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="0e2a9-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0e2a9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="0e2a9-105">Methods</span></span>  
  
|<span data-ttu-id="0e2a9-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="0e2a9-106">Method</span></span>|<span data-ttu-id="0e2a9-107">説明</span><span class="sxs-lookup"><span data-stu-id="0e2a9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0e2a9-108">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="0e2a9-108">Next Method</span></span>](icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="0e2a9-109">マネージヒープの領域に関する情報を格納している、指定した数の[COR_HEAPOBJECT](cor-heapobject-structure.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="0e2a9-109">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e2a9-110">コメント</span><span class="sxs-lookup"><span data-stu-id="0e2a9-110">Remarks</span></span>  
 <span data-ttu-id="0e2a9-111">`ICorDebugHeapSegmentEnum` インターフェイスは、ICorDebugEnum インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="0e2a9-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="0e2a9-112">`ICorDebugHeapSegmentEnum` インスタンスには、 [ICorDebugProcess5:: EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md)メソッドを呼び出すことによって、 [COR_HEAPOBJECT](cor-heapobject-structure.md)インスタンスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="0e2a9-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_HEAPOBJECT](cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="0e2a9-113">コレクション内の[COR_HEAPOBJECT](cor-heapobject-structure.md)オブジェクトは、 [ICorDebugHeapSegmentEnum:: Next](icordebugheapsegmentenum-next-method.md)メソッドを呼び出すことによって列挙できます。</span><span class="sxs-lookup"><span data-stu-id="0e2a9-113">The [COR_HEAPOBJECT](cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="0e2a9-114">`ICorDebugHeapSegmentEnum` collection オブジェクトは、マネージオブジェクトが含まれている可能性があるすべてのメモリ領域を列挙しますが、それらの領域にマネージオブジェクトが実際に存在することは保証しません。</span><span class="sxs-lookup"><span data-stu-id="0e2a9-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="0e2a9-115">これには、空または予約済みのメモリ領域に関する情報が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0e2a9-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e2a9-116">要件</span><span class="sxs-lookup"><span data-stu-id="0e2a9-116">Requirements</span></span>  
 <span data-ttu-id="0e2a9-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e2a9-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e2a9-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e2a9-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e2a9-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e2a9-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e2a9-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e2a9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e2a9-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e2a9-121">See also</span></span>

- [<span data-ttu-id="0e2a9-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0e2a9-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
