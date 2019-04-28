---
title: ICorDebugHeapValue::IsValid メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue.IsValid
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e1edb1d25a62a9a689c397339740e563d986c8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700222"
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="72104-102">ICorDebugHeapValue::IsValid メソッド</span><span class="sxs-lookup"><span data-stu-id="72104-102">ICorDebugHeapValue::IsValid Method</span></span>
<span data-ttu-id="72104-103">この ICorDebugHeapValue によって表されるオブジェクトが有効かどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="72104-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="72104-104">このメソッドは、.NET Framework version 2.0 で廃止されました。</span><span class="sxs-lookup"><span data-stu-id="72104-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72104-105">構文</span><span class="sxs-lookup"><span data-stu-id="72104-105">Syntax</span></span>  
  
```  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72104-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="72104-106">Parameters</span></span>  
 `pbValid`  
 <span data-ttu-id="72104-107">[out]ヒープ上には、この値が有効かどうかを示すブール値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="72104-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72104-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="72104-108">Remarks</span></span>  
 <span data-ttu-id="72104-109">値は、ガベージ コレクターが解放された場合に有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="72104-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="72104-110">このメソッドの使用は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="72104-110">This method has been deprecated.</span></span> <span data-ttu-id="72104-111">すべての値の有効期限は、.NET Framework 2.0 で[icordebugcontroller::continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)であり、値は、検証は、呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="72104-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72104-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="72104-112">Requirements</span></span>  
 <span data-ttu-id="72104-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="72104-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72104-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72104-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72104-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72104-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72104-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72104-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
