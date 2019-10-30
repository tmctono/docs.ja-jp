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
ms.openlocfilehash: 43408486fec9cd50222eed08ec2d3397bc11bc18
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134616"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="9b59e-102">ICorDebugGCReferenceEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="9b59e-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="9b59e-103">ガベージコレクトされるオブジェクトに関する情報を格納している、指定した数の[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="9b59e-103">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b59e-104">構文</span><span class="sxs-lookup"><span data-stu-id="9b59e-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b59e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9b59e-105">Parameters</span></span>  
 <span data-ttu-id="9b59e-106">celt</span><span class="sxs-lookup"><span data-stu-id="9b59e-106">celt</span></span>  
 <span data-ttu-id="9b59e-107">から取得するルートの数。</span><span class="sxs-lookup"><span data-stu-id="9b59e-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="9b59e-108">ca</span><span class="sxs-lookup"><span data-stu-id="9b59e-108">roots</span></span>  
 <span data-ttu-id="9b59e-109">入出力ポインターの配列。各ポインターは、ガベージコレクトされるオブジェクトのルートを表す[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)オブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="9b59e-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="9b59e-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="9b59e-110">pceltFetched</span></span>  
 <span data-ttu-id="9b59e-111">入出力`roots`に実際に返された[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)オブジェクトの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="9b59e-111">[out] A pointer to the number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="9b59e-112">`celt` が 1 の場合、この値は`null` になることがあります。</span><span class="sxs-lookup"><span data-stu-id="9b59e-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b59e-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="9b59e-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b59e-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="9b59e-114">Requirements</span></span>  
 <span data-ttu-id="9b59e-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b59e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b59e-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b59e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b59e-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b59e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b59e-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b59e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b59e-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b59e-119">See also</span></span>

- [<span data-ttu-id="9b59e-120">ICorDebugGCReferenceEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9b59e-120">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="9b59e-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9b59e-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
