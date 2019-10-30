---
title: ICorDebugValue::GetSize メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type:
- apiref
ms.openlocfilehash: 3d6caa02333229bcd49f4c6ccf8b93265181a0b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137093"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="5897b-102">ICorDebugValue::GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="5897b-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="5897b-103">この "ICorDebugValue" オブジェクトのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="5897b-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5897b-104">構文</span><span class="sxs-lookup"><span data-stu-id="5897b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5897b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5897b-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="5897b-106">入出力この値オブジェクトのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="5897b-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5897b-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="5897b-107">Remarks</span></span>  
 <span data-ttu-id="5897b-108">値の型が参照型の場合、このメソッドはオブジェクトのサイズではなく、ポインターのサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="5897b-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="5897b-109">`ICorDebugValue::GetSize` メソッドは、64ビットプラットフォームで 4 GB を超えるオブジェクトの `COR_E_OVERFLOW` を返します。</span><span class="sxs-lookup"><span data-stu-id="5897b-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="5897b-110">4 GB を超えるオブジェクトには、代わりに[ICorDebugValue3:: GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="5897b-110">Use the [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5897b-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="5897b-111">Requirements</span></span>  
 <span data-ttu-id="5897b-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5897b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5897b-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5897b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5897b-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5897b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5897b-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5897b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5897b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="5897b-116">See also</span></span>

- [<span data-ttu-id="5897b-117">GetSize64 メソッド</span><span class="sxs-lookup"><span data-stu-id="5897b-117">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
