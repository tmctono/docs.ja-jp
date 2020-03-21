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
ms.openlocfilehash: 8a267ec7123edb73ad51f0781a78344119ec6f21
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178890"
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="9d4db-102">ICorDebugHeapSegmentEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="9d4db-102">ICorDebugHeapSegmentEnum::Next Method</span></span>
<span data-ttu-id="9d4db-103">マネージ ヒープのメモリ領域に関する情報を含む、指定した数の[COR_HEAPOBJECT](cor-heapobject-structure.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="9d4db-103">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d4db-104">構文</span><span class="sxs-lookup"><span data-stu-id="9d4db-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d4db-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9d4db-105">Parameters</span></span>  
 <span data-ttu-id="9d4db-106">celt</span><span class="sxs-lookup"><span data-stu-id="9d4db-106">celt</span></span>  
 <span data-ttu-id="9d4db-107">[in]取得するセグメントの数。</span><span class="sxs-lookup"><span data-stu-id="9d4db-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="9d4db-108">セグメント</span><span class="sxs-lookup"><span data-stu-id="9d4db-108">segments</span></span>  
 <span data-ttu-id="9d4db-109">[アウト]マネージ ヒープ内のメモリ領域に関する情報を提供する[COR_HEAPOBJECT](cor-heapobject-structure.md)オブジェクトを指すポインターの配列。</span><span class="sxs-lookup"><span data-stu-id="9d4db-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](cor-heapobject-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="9d4db-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="9d4db-110">pceltFetched</span></span>  
 <span data-ttu-id="9d4db-111">[アウト]で実際に返される[COR_HEAPOBJECT](cor-heapobject-structure.md)オブジェクトの数へのポインター `segments`。</span><span class="sxs-lookup"><span data-stu-id="9d4db-111">[out] A pointer to the number of [COR_HEAPOBJECT](cor-heapobject-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="9d4db-112">`celt` が 1 の場合、この値は`null` になることがあります。</span><span class="sxs-lookup"><span data-stu-id="9d4db-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d4db-113">解説</span><span class="sxs-lookup"><span data-stu-id="9d4db-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d4db-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="9d4db-114">Requirements</span></span>  
 <span data-ttu-id="9d4db-115">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d4db-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d4db-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d4db-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d4db-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d4db-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d4db-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d4db-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d4db-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d4db-119">See also</span></span>

- [<span data-ttu-id="9d4db-120">ICorDebugHeapSegmentEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9d4db-120">ICorDebugHeapSegmentEnum Interface</span></span>](icordebugheapsegmentenum-interface.md)
- [<span data-ttu-id="9d4db-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9d4db-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
