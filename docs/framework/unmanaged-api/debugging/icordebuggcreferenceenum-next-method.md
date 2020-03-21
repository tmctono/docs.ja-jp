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
ms.openlocfilehash: d87f414e9dfd05a519b60efc7ecdd5328a6dd86f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178867"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="b82d4-102">ICorDebugGCReferenceEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="b82d4-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="b82d4-103">ガベージ コレクションされるオブジェクトに関する情報を含む、指定した数の[COR_GC_REFERENCE](cor-gc-reference-structure.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b82d4-103">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b82d4-104">構文</span><span class="sxs-lookup"><span data-stu-id="b82d4-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b82d4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b82d4-105">Parameters</span></span>  
 <span data-ttu-id="b82d4-106">celt</span><span class="sxs-lookup"><span data-stu-id="b82d4-106">celt</span></span>  
 <span data-ttu-id="b82d4-107">[in]取得するルートの数。</span><span class="sxs-lookup"><span data-stu-id="b82d4-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="b82d4-108">根</span><span class="sxs-lookup"><span data-stu-id="b82d4-108">roots</span></span>  
 <span data-ttu-id="b82d4-109">[アウト]ガベージ コレクションされるオブジェクトのルートを表す[COR_GC_REFERENCE](cor-gc-reference-structure.md)オブジェクトを指すポインターの配列。</span><span class="sxs-lookup"><span data-stu-id="b82d4-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="b82d4-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="b82d4-110">pceltFetched</span></span>  
 <span data-ttu-id="b82d4-111">[アウト]で実際に返される[COR_GC_REFERENCE](cor-gc-reference-structure.md)オブジェクトの数へのポインター `roots`。</span><span class="sxs-lookup"><span data-stu-id="b82d4-111">[out] A pointer to the number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="b82d4-112">`celt` が 1 の場合、この値は`null` になることがあります。</span><span class="sxs-lookup"><span data-stu-id="b82d4-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b82d4-113">解説</span><span class="sxs-lookup"><span data-stu-id="b82d4-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b82d4-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="b82d4-114">Requirements</span></span>  
 <span data-ttu-id="b82d4-115">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b82d4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b82d4-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b82d4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b82d4-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b82d4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b82d4-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b82d4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b82d4-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="b82d4-119">See also</span></span>

- [<span data-ttu-id="b82d4-120">ICorDebugGCReferenceEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b82d4-120">ICorDebugGCReferenceEnum Interface</span></span>](icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="b82d4-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b82d4-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
