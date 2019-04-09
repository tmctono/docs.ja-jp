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
ms.openlocfilehash: 33ad221f2a05357484d0877b6306d78e3864eff6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120173"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="b5075-102">ICorDebugGCReferenceEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="b5075-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="b5075-103">指定した数を取得[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)ガベージ コレクトされるオブジェクトに関する情報が含まれているインスタンス。</span><span class="sxs-lookup"><span data-stu-id="b5075-103">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5075-104">構文</span><span class="sxs-lookup"><span data-stu-id="b5075-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5075-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b5075-105">Parameters</span></span>  
 <span data-ttu-id="b5075-106">celt</span><span class="sxs-lookup"><span data-stu-id="b5075-106">celt</span></span>  
 <span data-ttu-id="b5075-107">[in]取得するルートの数。</span><span class="sxs-lookup"><span data-stu-id="b5075-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="b5075-108">ルート</span><span class="sxs-lookup"><span data-stu-id="b5075-108">roots</span></span>  
 <span data-ttu-id="b5075-109">[out]それぞれが指すポインターの配列を[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)ガベージ コレクトされるオブジェクトのルートを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b5075-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="b5075-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="b5075-110">pceltFetched</span></span>  
 <span data-ttu-id="b5075-111">[out]数へのポインター [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)で実際に返されるオブジェクト`roots`します。</span><span class="sxs-lookup"><span data-stu-id="b5075-111">[out] A pointer to the number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="b5075-112">`celt` が 1 の場合、この値は`null` になることがあります。</span><span class="sxs-lookup"><span data-stu-id="b5075-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5075-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="b5075-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5075-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="b5075-114">Requirements</span></span>  
 <span data-ttu-id="b5075-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5075-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5075-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5075-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5075-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5075-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b5075-118">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="b5075-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b5075-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5075-119">See also</span></span>

- [<span data-ttu-id="b5075-120">ICorDebugGCReferenceEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b5075-120">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="b5075-121">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="b5075-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
