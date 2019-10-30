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
ms.openlocfilehash: 284a74823b01305f8c6e025f70bb9209c8607b7b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137072"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="0c227-102">ICorDebugValue::GetType メソッド</span><span class="sxs-lookup"><span data-stu-id="0c227-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="0c227-103">この "ICorDebugValue" オブジェクトのプリミティブ型を取得します。</span><span class="sxs-lookup"><span data-stu-id="0c227-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c227-104">構文</span><span class="sxs-lookup"><span data-stu-id="0c227-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c227-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0c227-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="0c227-106">入出力値の型を示す "CorElementType" 列挙値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="0c227-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c227-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="0c227-107">Remarks</span></span>  
 <span data-ttu-id="0c227-108">オブジェクトが複雑な実行時の型である場合、その型は、`ICorDebugValue` インターフェイスの適切なサブクラスを通じて検査される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0c227-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="0c227-109">たとえば、`ICorDebugValue`から継承する "" は、複合型を表します。</span><span class="sxs-lookup"><span data-stu-id="0c227-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="0c227-110">`GetType` とには、それぞれ値の型に関する情報が返され[ます。](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)</span><span class="sxs-lookup"><span data-stu-id="0c227-110">The `GetType` and [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="0c227-111">これらはどちらも、ジェネリック対応[ICorDebugValue2:: GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)メソッドに置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="0c227-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c227-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="0c227-112">Requirements</span></span>  
 <span data-ttu-id="0c227-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c227-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c227-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c227-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c227-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c227-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c227-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c227-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c227-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c227-117">See also</span></span>
