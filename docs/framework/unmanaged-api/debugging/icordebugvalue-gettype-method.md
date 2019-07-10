---
title: ICorDebugValue::GetType メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0dbdee35e6c73fbf2d73edd8a6c479e2f2882ea
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764315"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="3f981-102">ICorDebugValue::GetType メソッド</span><span class="sxs-lookup"><span data-stu-id="3f981-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="3f981-103">この"ICorDebugValue"オブジェクトのプリミティブ型を取得します。</span><span class="sxs-lookup"><span data-stu-id="3f981-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f981-104">構文</span><span class="sxs-lookup"><span data-stu-id="3f981-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f981-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3f981-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="3f981-106">[out]値の型を示す"CorElementType"列挙型の値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3f981-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f981-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="3f981-107">Remarks</span></span>  
 <span data-ttu-id="3f981-108">適切なサブクラスを通じてその型を調べることがありますオブジェクトが実行時の複雑な型の場合、`ICorDebugValue`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="3f981-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="3f981-109">たとえば、"ICorDebugObjectValue"を継承する`ICorDebugValue`、複合型を表します。</span><span class="sxs-lookup"><span data-stu-id="3f981-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="3f981-110">`GetType`と[icordebugobjectvalue::getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)各メソッドが値の型に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3f981-110">The `GetType` and [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="3f981-111">どちらも汎用対応によって置き換えられる[icordebugvalue 2::getexacttype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="3f981-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f981-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="3f981-112">Requirements</span></span>  
 <span data-ttu-id="3f981-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f981-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f981-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f981-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f981-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f981-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f981-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f981-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f981-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f981-117">See also</span></span>
