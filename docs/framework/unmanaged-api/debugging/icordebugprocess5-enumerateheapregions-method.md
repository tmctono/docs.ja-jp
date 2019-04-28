---
title: ICorDebugProcess5::EnumerateHeapRegions メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeapRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeapRegions
helpviewer_keywords:
- EnumerateHeapRegions method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeapRegions method [.NET Framework debugging]
ms.assetid: b1edba68-9c36-4f69-be9f-678ce0b33480
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61e30cf4ffe45578f7ad37de8295d227dbf313c9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61930196"
---
# <a name="icordebugprocess5enumerateheapregions-method"></a><span data-ttu-id="0dd8d-102">ICorDebugProcess5::EnumerateHeapRegions メソッド</span><span class="sxs-lookup"><span data-stu-id="0dd8d-102">ICorDebugProcess5::EnumerateHeapRegions Method</span></span>
<span data-ttu-id="0dd8d-103">マネージ ヒープのメモリの範囲の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="0dd8d-103">Gets an enumerator for the memory ranges of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dd8d-104">構文</span><span class="sxs-lookup"><span data-stu-id="0dd8d-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0dd8d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0dd8d-105">Parameters</span></span>  
 `ppRegions`  
 <span data-ttu-id="0dd8d-106">[out]アドレスへのポインター、 [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)オブジェクトがマネージ ヒープ内に存在するメモリの範囲の列挙子は、インターフェイス オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0dd8d-106">[out] A pointer to the address of an [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) interface object that is an enumerator for the ranges of memory in which objects reside in the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0dd8d-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="0dd8d-107">Remarks</span></span>  
 <span data-ttu-id="0dd8d-108">呼び出しの前に、`ICorDebugProcess5::EnumerateHeapRegions`メソッドを呼び出す必要があります、 [icordebugprocess 5::getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)メソッドの値を確認し、 `areGCStructuresValid` 、返されたフィールド[COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)現在の状態でガベージ コレクション ヒープが列挙可能なことを確認するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0dd8d-108">Before calling the `ICorDebugProcess5::EnumerateHeapRegions` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="0dd8d-109">さらに、`ICorDebugProcess5::EnumerateHeapRegions`メソッドを返します。 `E_FAIL` 、プロセスの有効期間が早すぎるでアタッチする場合は、作成する前にメモリ領域は。</span><span class="sxs-lookup"><span data-stu-id="0dd8d-109">In addition, the `ICorDebugProcess5::EnumerateHeapRegions` method returns `E_FAIL` if you attach too early in the lifetime of the process, before memory regions are created.</span></span>  
  
 <span data-ttu-id="0dd8d-110">このメソッドは、管理対象のオブジェクトを含む可能性のあるすべてのメモリ領域を列挙することが保証がマネージ オブジェクトが実際にそれらのリージョン内にあることは保証されません。</span><span class="sxs-lookup"><span data-stu-id="0dd8d-110">This method is guaranteed to enumerate all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="0dd8d-111">[ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)コレクション オブジェクトが空または予約済みのメモリ領域を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="0dd8d-111">The [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object may include empty or reserved memory regions.</span></span>  
  
 <span data-ttu-id="0dd8d-112">[ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)インターフェイス オブジェクトを列挙できる ICorDebugEnum インターフェイスから派生した標準の列挙子は、 [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0dd8d-112">The [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) objects.</span></span> <span data-ttu-id="0dd8d-113">各[COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)オブジェクトは、そのセグメント内のオブジェクトの生成と、特定のセグメントのメモリの範囲に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="0dd8d-113">Each [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) object provides information about the memory range of a particular segment, along with the generation of the objects in that segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dd8d-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="0dd8d-114">Requirements</span></span>  
 <span data-ttu-id="0dd8d-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0dd8d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dd8d-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0dd8d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0dd8d-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0dd8d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0dd8d-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dd8d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dd8d-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="0dd8d-119">See also</span></span>

- [<span data-ttu-id="0dd8d-120">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0dd8d-120">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="0dd8d-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0dd8d-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
