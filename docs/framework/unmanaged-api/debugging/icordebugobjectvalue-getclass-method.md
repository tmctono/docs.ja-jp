---
title: ICorDebugObjectValue::GetClass メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetClass
helpviewer_keywords:
- ICorDebugObjectValue::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 5be25292-8357-445f-a09b-f997c0de761c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06e9c7af1c4a769bfb45a8e9f805d97b3bad94aa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174188"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="3a783-102">ICorDebugObjectValue::GetClass メソッド</span><span class="sxs-lookup"><span data-stu-id="3a783-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="3a783-103">このオブジェクトの値のクラスを取得します。</span><span class="sxs-lookup"><span data-stu-id="3a783-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a783-104">構文</span><span class="sxs-lookup"><span data-stu-id="3a783-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a783-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3a783-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="3a783-106">[out]この"ICorDebugObjectValue"オブジェクトによって表されるオブジェクトの値のクラスを表す"ICorDebugClass"オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3a783-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a783-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="3a783-107">Remarks</span></span>  
 <span data-ttu-id="3a783-108">`GetClass`と[icordebugvalue::gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)各メソッドが値の型に関する情報を返すは両方とも汎用対応によって置き換えられる[icordebugvalue 2::getexacttype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="3a783-108">The `GetClass` and [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a783-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="3a783-109">Requirements</span></span>  
 <span data-ttu-id="3a783-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a783-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a783-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a783-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a783-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a783-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a783-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a783-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a783-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a783-114">See also</span></span>
