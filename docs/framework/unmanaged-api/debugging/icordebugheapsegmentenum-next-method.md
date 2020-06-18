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
ms.openlocfilehash: 3d4e44eefaf99a40b9c4f1c45e7dd81192f8b607
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904274"
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="18378-102">ICorDebugHeapSegmentEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="18378-102">ICorDebugHeapSegmentEnum::Next Method</span></span>
<span data-ttu-id="18378-103">マネージヒープのメモリ領域に関する情報を格納している、指定した数の[COR_SEGMENT](cor-segment-structure.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="18378-103">Gets the specified number of [COR_SEGMENT](cor-segment-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18378-104">構文</span><span class="sxs-lookup"><span data-stu-id="18378-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18378-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="18378-105">Parameters</span></span>  
 <span data-ttu-id="18378-106">celt</span><span class="sxs-lookup"><span data-stu-id="18378-106">celt</span></span>  
 <span data-ttu-id="18378-107">から取得するセグメントの数。</span><span class="sxs-lookup"><span data-stu-id="18378-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="18378-108">セグメント</span><span class="sxs-lookup"><span data-stu-id="18378-108">segments</span></span>  
 <span data-ttu-id="18378-109">入出力ポインターの配列。各ポインターは、マネージヒープ内のメモリ領域に関する情報を提供する[COR_SEGMENT](cor-segment-structure.md)オブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="18378-109">[out] An array of pointers, each of which points to a [COR_SEGMENT](cor-segment-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="18378-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="18378-110">pceltFetched</span></span>  
 <span data-ttu-id="18378-111">入出力実際にで返される[COR_SEGMENT](cor-segment-structure.md)オブジェクトの数へのポインター `segments` 。</span><span class="sxs-lookup"><span data-stu-id="18378-111">[out] A pointer to the number of [COR_SEGMENT](cor-segment-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="18378-112">`celt` が 1 の場合、この値は`null` になることがあります。</span><span class="sxs-lookup"><span data-stu-id="18378-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18378-113">解説</span><span class="sxs-lookup"><span data-stu-id="18378-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18378-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="18378-114">Requirements</span></span>  
 <span data-ttu-id="18378-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18378-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18378-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18378-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18378-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18378-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18378-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18378-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18378-119">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="18378-119">See also</span></span>

- [<span data-ttu-id="18378-120">ICorDebugHeapSegmentEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="18378-120">ICorDebugHeapSegmentEnum Interface</span></span>](icordebugheapsegmentenum-interface.md)
- [<span data-ttu-id="18378-121">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="18378-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
