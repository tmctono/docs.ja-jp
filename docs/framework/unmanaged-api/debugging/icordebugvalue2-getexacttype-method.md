---
title: ICorDebugValue2::GetExactType メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03d701d0801c55b6e91600f0767a6d737e4915c3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479949"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="e04ed-102">ICorDebugValue2::GetExactType メソッド</span><span class="sxs-lookup"><span data-stu-id="e04ed-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="e04ed-103">"ICorDebugType"オブジェクトを表すインターフェイス ポインターを取得、<xref:System.Type>のこの値。</span><span class="sxs-lookup"><span data-stu-id="e04ed-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e04ed-104">構文</span><span class="sxs-lookup"><span data-stu-id="e04ed-104">Syntax</span></span>  
  
```  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e04ed-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e04ed-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="e04ed-106">[out]アドレスへのポインター、`ICorDebugType`を表すオブジェクトを<xref:System.Type>のこの"ICorDebugValue2"オブジェクトで表される値。</span><span class="sxs-lookup"><span data-stu-id="e04ed-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e04ed-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e04ed-107">Remarks</span></span>  
 <span data-ttu-id="e04ed-108">汎用対応`GetExactType`メソッドはどちらも、 [icordebugobjectvalue::getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)と[icordebugvalue::gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)メソッド、戻り値の型に関する情報の各.</span><span class="sxs-lookup"><span data-stu-id="e04ed-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e04ed-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="e04ed-109">Requirements</span></span>  
 <span data-ttu-id="e04ed-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e04ed-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e04ed-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e04ed-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e04ed-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e04ed-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e04ed-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e04ed-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e04ed-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e04ed-114">See also</span></span>

