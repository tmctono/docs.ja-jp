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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bd993eb26f26818117a20d376c3331f88c46b26
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214352"
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="0a296-102">ICorDebugHeapEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="0a296-102">ICorDebugHeapEnum::Next Method</span></span>
<span data-ttu-id="0a296-103">指定した数を取得[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)マネージ ヒープ上のオブジェクトに関する情報が含まれているインスタンス。</span><span class="sxs-lookup"><span data-stu-id="0a296-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a296-104">構文</span><span class="sxs-lookup"><span data-stu-id="0a296-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a296-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0a296-105">Parameters</span></span>  
 <span data-ttu-id="0a296-106">celt</span><span class="sxs-lookup"><span data-stu-id="0a296-106">celt</span></span>  
 <span data-ttu-id="0a296-107">[in] 取得するオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="0a296-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="0a296-108">オブジェクト</span><span class="sxs-lookup"><span data-stu-id="0a296-108">objects</span></span>  
 <span data-ttu-id="0a296-109">[out]それぞれが指すポインターの配列を[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)マネージ ヒープのオブジェクトに関する情報を提供するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0a296-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="0a296-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="0a296-110">pceltFetched</span></span>  
 <span data-ttu-id="0a296-111">[out]数へのポインター [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)で実際に返されるオブジェクト`objects`します。</span><span class="sxs-lookup"><span data-stu-id="0a296-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="0a296-112">`celt` が 1 の場合、この値は`null` になることがあります。</span><span class="sxs-lookup"><span data-stu-id="0a296-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a296-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="0a296-113">Remarks</span></span>  
 <span data-ttu-id="0a296-114">`COR_HEAPOBJECT.type` フィールドは、入れ子になった参照カウントの COM インターフェイスの識別子です。</span><span class="sxs-lookup"><span data-stu-id="0a296-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="0a296-115">この参照は、`ICorDebugHeapEnum::Next` の呼び出し元によって解放される必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a296-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a296-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="0a296-116">Requirements</span></span>  
 <span data-ttu-id="0a296-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a296-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a296-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a296-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a296-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a296-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a296-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a296-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a296-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a296-121">See also</span></span>

- [<span data-ttu-id="0a296-122">ICorDebugHeapEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0a296-122">ICorDebugHeapEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)
- [<span data-ttu-id="0a296-123">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0a296-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
