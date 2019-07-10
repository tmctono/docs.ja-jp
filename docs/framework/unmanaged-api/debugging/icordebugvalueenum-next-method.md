---
title: ICorDebugValueEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum::Next
helpviewer_keywords:
- ICorDebugValueEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: f5ef94dd-dfee-49d3-a398-b110f8906dd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ae09b4f1cd069edf81be583c7c4226717736094
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764277"
---
# <a name="icordebugvalueenumnext-method"></a><span data-ttu-id="979ef-102">ICorDebugValueEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="979ef-102">ICorDebugValueEnum::Next Method</span></span>
<span data-ttu-id="979ef-103">列挙体の現在位置から指定された"ICorDebugValue"インスタンス数を取得します。</span><span class="sxs-lookup"><span data-stu-id="979ef-103">Gets the specified number of "ICorDebugValue" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="979ef-104">構文</span><span class="sxs-lookup"><span data-stu-id="979ef-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="979ef-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="979ef-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="979ef-106">[in]数`ICorDebugValue`インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="979ef-106">[in] The number of `ICorDebugValue` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="979ef-107">[out]それぞれが指すポインターの配列、`ICorDebugValue`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="979ef-107">[out] An array of pointers, each of which points to an `ICorDebugValue` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="979ef-108">[out]数へのポインター`ICorDebugValue`インスタンスが実際に返されます。</span><span class="sxs-lookup"><span data-stu-id="979ef-108">[out] Pointer to the number of `ICorDebugValue` instances actually returned.</span></span> <span data-ttu-id="979ef-109">この値は null になる場合`celt`は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="979ef-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="979ef-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="979ef-110">Requirements</span></span>  
 <span data-ttu-id="979ef-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="979ef-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="979ef-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="979ef-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="979ef-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="979ef-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="979ef-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="979ef-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="979ef-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="979ef-115">See also</span></span>
