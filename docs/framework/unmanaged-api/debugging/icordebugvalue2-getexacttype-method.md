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
ms.openlocfilehash: 002e53d380140a63297a90baa270b5a6f1e5e328
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986831"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="c14bb-102">ICorDebugValue2::GetExactType メソッド</span><span class="sxs-lookup"><span data-stu-id="c14bb-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="c14bb-103">"ICorDebugType"オブジェクトを表すインターフェイス ポインターを取得、<xref:System.Type>のこの値。</span><span class="sxs-lookup"><span data-stu-id="c14bb-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c14bb-104">構文</span><span class="sxs-lookup"><span data-stu-id="c14bb-104">Syntax</span></span>  
  
```  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c14bb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c14bb-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="c14bb-106">[out]アドレスへのポインター、`ICorDebugType`を表すオブジェクトを<xref:System.Type>のこの"ICorDebugValue2"オブジェクトで表される値。</span><span class="sxs-lookup"><span data-stu-id="c14bb-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c14bb-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="c14bb-107">Remarks</span></span>  
 <span data-ttu-id="c14bb-108">汎用対応`GetExactType`メソッドはどちらも、 [icordebugobjectvalue::getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)と[icordebugvalue::gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)メソッド、戻り値の型に関する情報の各.</span><span class="sxs-lookup"><span data-stu-id="c14bb-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c14bb-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="c14bb-109">Requirements</span></span>  
 <span data-ttu-id="c14bb-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c14bb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c14bb-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c14bb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c14bb-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c14bb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c14bb-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c14bb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c14bb-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="c14bb-114">See also</span></span>
