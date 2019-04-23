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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6998be3daf0ab6a6290a3400b96c32227df3e022
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175092"
---
# <a name="icordebugobjectenumnext-method"></a><span data-ttu-id="005ca-102">ICorDebugObjectEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="005ca-102">ICorDebugObjectEnum::Next Method</span></span>
<span data-ttu-id="005ca-103">列挙体の現在位置から指定した数のオブジェクトの相対仮想アドレス (Rva) を取得します。</span><span class="sxs-lookup"><span data-stu-id="005ca-103">Gets the relative virtual addresses (RVAs) of the specified number of objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="005ca-104">構文</span><span class="sxs-lookup"><span data-stu-id="005ca-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="005ca-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="005ca-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="005ca-106">[in] 取得するオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="005ca-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="005ca-107">[out]CORDB_ADDRESS オブジェクトを指す各ポインターの配列。</span><span class="sxs-lookup"><span data-stu-id="005ca-107">[out] An array of pointers, each of which points to a CORDB_ADDRESS object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="005ca-108">[out]実際に返されるオブジェクトの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="005ca-108">[out] Pointer to the number of objects actually returned.</span></span> <span data-ttu-id="005ca-109">この値は null になる場合`celt`は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="005ca-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="005ca-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="005ca-110">Requirements</span></span>  
 <span data-ttu-id="005ca-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="005ca-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="005ca-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="005ca-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="005ca-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="005ca-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="005ca-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="005ca-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="005ca-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="005ca-115">See also</span></span>
