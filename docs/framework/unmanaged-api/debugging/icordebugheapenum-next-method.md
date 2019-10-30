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
ms.openlocfilehash: 1beb69bfaad9acb9c269ad8becb81bea64edb6a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138470"
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="a6c75-102">ICorDebugHeapEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="a6c75-102">ICorDebugHeapEnum::Next Method</span></span>
<span data-ttu-id="a6c75-103">マネージヒープ上のオブジェクトに関する情報を格納している、指定した数の[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="a6c75-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6c75-104">構文</span><span class="sxs-lookup"><span data-stu-id="a6c75-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6c75-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a6c75-105">Parameters</span></span>  
 <span data-ttu-id="a6c75-106">celt</span><span class="sxs-lookup"><span data-stu-id="a6c75-106">celt</span></span>  
 <span data-ttu-id="a6c75-107">[in] 取得するオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="a6c75-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="a6c75-108">オブジェクト</span><span class="sxs-lookup"><span data-stu-id="a6c75-108">objects</span></span>  
 <span data-ttu-id="a6c75-109">入出力ポインターの配列。各ポインターは、マネージヒープ上のオブジェクトに関する情報を提供する[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)オブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="a6c75-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="a6c75-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="a6c75-110">pceltFetched</span></span>  
 <span data-ttu-id="a6c75-111">入出力`objects`に実際に返された[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)オブジェクトの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a6c75-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="a6c75-112">`celt` が 1 の場合、この値は`null` になることがあります。</span><span class="sxs-lookup"><span data-stu-id="a6c75-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6c75-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="a6c75-113">Remarks</span></span>  
 <span data-ttu-id="a6c75-114">`COR_HEAPOBJECT.type` フィールドは、入れ子になった参照カウントの COM インターフェイスの識別子です。</span><span class="sxs-lookup"><span data-stu-id="a6c75-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="a6c75-115">この参照は、`ICorDebugHeapEnum::Next` の呼び出し元によって解放される必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6c75-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6c75-116">［要件］</span><span class="sxs-lookup"><span data-stu-id="a6c75-116">Requirements</span></span>  
 <span data-ttu-id="a6c75-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6c75-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6c75-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6c75-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6c75-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6c75-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6c75-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6c75-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6c75-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6c75-121">See also</span></span>

- [<span data-ttu-id="a6c75-122">ICorDebugHeapEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6c75-122">ICorDebugHeapEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)
- [<span data-ttu-id="a6c75-123">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a6c75-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
