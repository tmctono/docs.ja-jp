---
title: ICorDebugHeapSegmentEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum::Next
helpviewer_keywords:
- ICorDebugHeapSegmentEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 51625fd0-7399-49c7-b22b-5dfb05451fe6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d260fa762033e86351577d46c770543300876869
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756677"
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="67cba-102">ICorDebugHeapSegmentEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="67cba-102">ICorDebugHeapSegmentEnum::Next Method</span></span>
<span data-ttu-id="67cba-103">指定した数を取得[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)マネージ ヒープのメモリ領域に関する情報が含まれているインスタンス。</span><span class="sxs-lookup"><span data-stu-id="67cba-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67cba-104">構文</span><span class="sxs-lookup"><span data-stu-id="67cba-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67cba-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="67cba-105">Parameters</span></span>  
 <span data-ttu-id="67cba-106">celt</span><span class="sxs-lookup"><span data-stu-id="67cba-106">celt</span></span>  
 <span data-ttu-id="67cba-107">[in]取得するセグメントの数。</span><span class="sxs-lookup"><span data-stu-id="67cba-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="67cba-108">セグメント</span><span class="sxs-lookup"><span data-stu-id="67cba-108">segments</span></span>  
 <span data-ttu-id="67cba-109">[out]それぞれが指すポインターの配列を[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)マネージ ヒープのメモリの領域に関する情報を提供するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="67cba-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="67cba-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="67cba-110">pceltFetched</span></span>  
 <span data-ttu-id="67cba-111">[out]数へのポインター [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)で実際に返されるオブジェクト`segments`します。</span><span class="sxs-lookup"><span data-stu-id="67cba-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="67cba-112">`celt` が 1 の場合、この値は`null` になることがあります。</span><span class="sxs-lookup"><span data-stu-id="67cba-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67cba-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="67cba-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67cba-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="67cba-114">Requirements</span></span>  
 <span data-ttu-id="67cba-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="67cba-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67cba-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67cba-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67cba-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67cba-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67cba-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67cba-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67cba-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="67cba-119">See also</span></span>

- [<span data-ttu-id="67cba-120">ICorDebugHeapSegmentEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67cba-120">ICorDebugHeapSegmentEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)
- [<span data-ttu-id="67cba-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67cba-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
