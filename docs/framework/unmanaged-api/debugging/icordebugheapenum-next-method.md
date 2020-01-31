---
title: ICorDebugHeapEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum::Next
helpviewer_keywords:
- ICorDebugHeapEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 2221fd06-9e27-4113-972e-2530db8c3594
topic_type:
- apiref
ms.openlocfilehash: 2c84112984e9cb7dec2a492ac16af00e14770806
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782494"
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="68a09-102">ICorDebugHeapEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="68a09-102">ICorDebugHeapEnum::Next Method</span></span>
<span data-ttu-id="68a09-103">マネージヒープ上のオブジェクトに関する情報を格納している、指定した数の[COR_HEAPOBJECT](cor-heapobject-structure.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="68a09-103">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68a09-104">構文</span><span class="sxs-lookup"><span data-stu-id="68a09-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68a09-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="68a09-105">Parameters</span></span>  
 <span data-ttu-id="68a09-106">celt</span><span class="sxs-lookup"><span data-stu-id="68a09-106">celt</span></span>  
 <span data-ttu-id="68a09-107">[in] 取得するオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="68a09-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="68a09-108">/復元</span><span class="sxs-lookup"><span data-stu-id="68a09-108">objects</span></span>  
 <span data-ttu-id="68a09-109">入出力ポインターの配列。各ポインターは、マネージヒープ上のオブジェクトに関する情報を提供する[COR_HEAPOBJECT](cor-heapobject-structure.md)オブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="68a09-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="68a09-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="68a09-110">pceltFetched</span></span>  
 <span data-ttu-id="68a09-111">入出力`objects`で実際に返される[COR_HEAPOBJECT](cor-heapobject-structure.md)オブジェクトの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="68a09-111">[out] A pointer to the number of [COR_HEAPOBJECT](cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="68a09-112">`celt` が 1 の場合、この値は`null` になることがあります。</span><span class="sxs-lookup"><span data-stu-id="68a09-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68a09-113">コメント</span><span class="sxs-lookup"><span data-stu-id="68a09-113">Remarks</span></span>  
 <span data-ttu-id="68a09-114">`COR_HEAPOBJECT.type` フィールドは、入れ子になった参照カウントの COM インターフェイスの識別子です。</span><span class="sxs-lookup"><span data-stu-id="68a09-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="68a09-115">この参照は、`ICorDebugHeapEnum::Next` の呼び出し元によって解放される必要があります。</span><span class="sxs-lookup"><span data-stu-id="68a09-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68a09-116">要件</span><span class="sxs-lookup"><span data-stu-id="68a09-116">Requirements</span></span>  
 <span data-ttu-id="68a09-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68a09-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68a09-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="68a09-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68a09-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68a09-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68a09-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68a09-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68a09-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="68a09-121">See also</span></span>

- [<span data-ttu-id="68a09-122">ICorDebugHeapEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="68a09-122">ICorDebugHeapEnum Interface</span></span>](icordebugheapenum-interface.md)
- [<span data-ttu-id="68a09-123">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="68a09-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
