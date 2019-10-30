---
title: ICorDebugValue3::GetSize64 メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugValue3::GetSize64
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type:
- apiref
ms.openlocfilehash: 72a1b6fdc40f3169500d8cf3b3028315106ecc69
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140234"
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="94084-102">ICorDebugValue3::GetSize64 メソッド</span><span class="sxs-lookup"><span data-stu-id="94084-102">ICorDebugValue3::GetSize64 Method</span></span>
<span data-ttu-id="94084-103">この[ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)オブジェクトのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="94084-103">Gets the size, in bytes, of this [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94084-104">構文</span><span class="sxs-lookup"><span data-stu-id="94084-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94084-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="94084-105">Parameters</span></span>  
 <span data-ttu-id="94084-106">pSize</span><span class="sxs-lookup"><span data-stu-id="94084-106">pSize</span></span>  
 <span data-ttu-id="94084-107">入出力このオブジェクトのサイズ (バイト単位) へのポインター。</span><span class="sxs-lookup"><span data-stu-id="94084-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94084-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="94084-108">Remarks</span></span>  
 <span data-ttu-id="94084-109">この値の型が参照型の場合、このメソッドはオブジェクトのサイズではなく、ポインターのサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="94084-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="94084-110">`ICorDebugValue3::GetSize` メソッドは、その出力パラメーターの型の[ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)メソッドとは異なります。</span><span class="sxs-lookup"><span data-stu-id="94084-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="94084-111">[ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)では、出力パラメーターは `ULONG32`です。`ICorDebugValue3::GetSize`では、`ULONG64`です。</span><span class="sxs-lookup"><span data-stu-id="94084-111">In [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="94084-112">これにより、 [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)インターフェイスは、2gb を超える配列のサイズを報告できます。</span><span class="sxs-lookup"><span data-stu-id="94084-112">This enables the [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94084-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="94084-113">Requirements</span></span>  
 <span data-ttu-id="94084-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94084-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94084-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94084-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94084-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94084-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94084-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94084-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94084-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="94084-118">See also</span></span>

- [<span data-ttu-id="94084-119">ICorDebugValue3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="94084-119">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [<span data-ttu-id="94084-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="94084-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
