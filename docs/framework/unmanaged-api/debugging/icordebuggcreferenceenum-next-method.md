---
title: ICorDebugGCReferenceEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f76b727511ad604c407fb2998a5ecea26f91c49
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481366"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="59031-102">ICorDebugGCReferenceEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="59031-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="59031-103">指定した数を取得[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)ガベージ コレクトされるオブジェクトに関する情報が含まれているインスタンス。</span><span class="sxs-lookup"><span data-stu-id="59031-103">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59031-104">構文</span><span class="sxs-lookup"><span data-stu-id="59031-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59031-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="59031-105">Parameters</span></span>  
 <span data-ttu-id="59031-106">celt</span><span class="sxs-lookup"><span data-stu-id="59031-106">celt</span></span>  
 <span data-ttu-id="59031-107">[in]取得するルートの数。</span><span class="sxs-lookup"><span data-stu-id="59031-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="59031-108">ルート</span><span class="sxs-lookup"><span data-stu-id="59031-108">roots</span></span>  
 <span data-ttu-id="59031-109">[out]それぞれが指すポインターの配列を[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)ガベージ コレクトされるオブジェクトのルートを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="59031-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="59031-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="59031-110">pceltFetched</span></span>  
 <span data-ttu-id="59031-111">[out]数へのポインター [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)で実際に返されるオブジェクト`roots`します。</span><span class="sxs-lookup"><span data-stu-id="59031-111">[out] A pointer to the number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="59031-112">
  `celt\` が 1 の場合、この値は`null\` になることがあります。</span><span class="sxs-lookup"><span data-stu-id="59031-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59031-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="59031-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59031-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="59031-114">Requirements</span></span>  
 <span data-ttu-id="59031-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="59031-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59031-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59031-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59031-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59031-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59031-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59031-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59031-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="59031-119">See also</span></span>
- [<span data-ttu-id="59031-120">ICorDebugGCReferenceEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="59031-120">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="59031-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="59031-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
