---
title: ICorDebugType::GetFirstTypeParameter メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetFirstTypeParameter
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetFirstTypeParameter
helpviewer_keywords:
- ICorDebugType::GetFirstTypeParameter method [.NET Framework debugging]
- GetFirstTypeParameter method [.NET Framework debugging]
ms.assetid: 35bb594f-af6a-4349-83fe-e98702674e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3031cf2d9509f94b50c386b44e6d9e5d9ee5509c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768231"
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a><span data-ttu-id="61e87-102">ICorDebugType::GetFirstTypeParameter メソッド</span><span class="sxs-lookup"><span data-stu-id="61e87-102">ICorDebugType::GetFirstTypeParameter Method</span></span>
<span data-ttu-id="61e87-103">1 つ目を表す、ICorDebugType へインターフェイス ポインターを取得<xref:System.Type>これによって表される型のパラメーター`ICorDebugType`します。</span><span class="sxs-lookup"><span data-stu-id="61e87-103">Gets an interface pointer to an ICorDebugType that represents the first <xref:System.Type> parameter of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61e87-104">構文</span><span class="sxs-lookup"><span data-stu-id="61e87-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61e87-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="61e87-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="61e87-106">[out]アドレスへのポインター、`ICorDebugType`最初のパラメーターを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="61e87-106">[out] A pointer to the address of an `ICorDebugType` object that represents the first parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61e87-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="61e87-107">Remarks</span></span>  
 <span data-ttu-id="61e87-108">`GetFirstTypeParameter` できる場合に呼び出される場所の種類に関する追加情報は、最大で 1 つの型パラメーター。</span><span class="sxs-lookup"><span data-stu-id="61e87-108">`GetFirstTypeParameter` can be called in cases where the additional information about the type involves, at most, one type parameter.</span></span> <span data-ttu-id="61e87-109">具体的には、使用できます、型が ELEMENT_TYPE_ARRAY、ELEMENT_TYPE_SZARRAY、ELEMENT_TYPE_BYREF、または ELEMENT_TYPE_PTR 場合、によって示される、 [icordebugtype::gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="61e87-109">In particular, it can be used if the type is an ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61e87-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="61e87-110">Requirements</span></span>  
 <span data-ttu-id="61e87-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="61e87-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61e87-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61e87-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61e87-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61e87-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61e87-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61e87-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
