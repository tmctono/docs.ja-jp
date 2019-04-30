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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41a9ff2c94c98a5acc930d68e648b0ea577a82c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986844"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="3b60f-102">ICorDebugValue::GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="3b60f-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="3b60f-103">この"ICorDebugValue"オブジェクトのバイト単位のサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="3b60f-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b60f-104">構文</span><span class="sxs-lookup"><span data-stu-id="3b60f-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b60f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3b60f-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="3b60f-106">[out]この値のオブジェクトのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="3b60f-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b60f-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="3b60f-107">Remarks</span></span>  
 <span data-ttu-id="3b60f-108">値の型が参照型の場合は、このメソッドは、オブジェクトのサイズではなく、ポインターのサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="3b60f-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="3b60f-109">`ICorDebugValue::GetSize`メソッドを返します。`COR_E_OVERFLOW`オブジェクトには、64 ビット プラットフォーム上で 4 GB より大きい。</span><span class="sxs-lookup"><span data-stu-id="3b60f-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="3b60f-110">使用して、 [icordebugvalue 3::getsize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)メソッド代わりにオブジェクトは 4 GB より大きい。</span><span class="sxs-lookup"><span data-stu-id="3b60f-110">Use the [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b60f-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="3b60f-111">Requirements</span></span>  
 <span data-ttu-id="3b60f-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b60f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b60f-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b60f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b60f-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b60f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b60f-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b60f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b60f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b60f-116">See also</span></span>

- [<span data-ttu-id="3b60f-117">GetSize64 メソッド</span><span class="sxs-lookup"><span data-stu-id="3b60f-117">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
