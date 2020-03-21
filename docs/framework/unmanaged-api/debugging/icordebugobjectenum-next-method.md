---
title: ICorDebugObjectEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugObjectEnum interface [.NET Framework debugging]
- ICorDebugObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 10093e3d-26b6-4ad7-8ef3-bbf66243fc02
topic_type:
- apiref
ms.openlocfilehash: e9b32980a5606629676549905d3c9956633f25b0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178702"
---
# <a name="icordebugobjectenumnext-method"></a><span data-ttu-id="3d9b1-102">ICorDebugObjectEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="3d9b1-102">ICorDebugObjectEnum::Next Method</span></span>
<span data-ttu-id="3d9b1-103">現在の位置から始まる、列挙体から指定した数のオブジェクトの相対仮想アドレス (RVA) を取得します。</span><span class="sxs-lookup"><span data-stu-id="3d9b1-103">Gets the relative virtual addresses (RVAs) of the specified number of objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d9b1-104">構文</span><span class="sxs-lookup"><span data-stu-id="3d9b1-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d9b1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3d9b1-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="3d9b1-106">[in] 取得するオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="3d9b1-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="3d9b1-107">[アウト]ポインターの配列で、各ポインターがCORDB_ADDRESSオブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="3d9b1-107">[out] An array of pointers, each of which points to a CORDB_ADDRESS object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="3d9b1-108">[アウト]実際に返されるオブジェクトの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3d9b1-108">[out] Pointer to the number of objects actually returned.</span></span> <span data-ttu-id="3d9b1-109">この値は null`celt`の場合は null である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3d9b1-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d9b1-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="3d9b1-110">Requirements</span></span>  
 <span data-ttu-id="3d9b1-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d9b1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d9b1-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d9b1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d9b1-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d9b1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d9b1-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d9b1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d9b1-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d9b1-115">See also</span></span>
