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
ms.openlocfilehash: 7edf0065fa7eb39dada167a682f2b634a438f1f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138396"
---
# <a name="icordebugheapvalueisvalid-method"></a><span data-ttu-id="2ddd5-102">ICorDebugHeapValue::IsValid メソッド</span><span class="sxs-lookup"><span data-stu-id="2ddd5-102">ICorDebugHeapValue::IsValid Method</span></span>
<span data-ttu-id="2ddd5-103">この値によって表されるオブジェクトが有効かどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="2ddd5-103">Gets a value that indicates whether the object represented by this ICorDebugHeapValue is valid.</span></span>  
  
 <span data-ttu-id="2ddd5-104">このメソッドは .NET Framework バージョン2.0 では非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="2ddd5-104">This method has been deprecated in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ddd5-105">構文</span><span class="sxs-lookup"><span data-stu-id="2ddd5-105">Syntax</span></span>  
  
```cpp  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ddd5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2ddd5-106">Parameters</span></span>  
 `pbValid`  
 <span data-ttu-id="2ddd5-107">入出力ヒープ上のこの値が有効かどうかを示すブール値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2ddd5-107">[out] A pointer to a Boolean value that indicates whether this value on the heap is valid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ddd5-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="2ddd5-108">Remarks</span></span>  
 <span data-ttu-id="2ddd5-109">値は、ガベージコレクターによって回収されている場合は無効です。</span><span class="sxs-lookup"><span data-stu-id="2ddd5-109">The value is invalid if it has been reclaimed by the garbage collector.</span></span>  
  
 <span data-ttu-id="2ddd5-110">このメソッドの使用は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="2ddd5-110">This method has been deprecated.</span></span> <span data-ttu-id="2ddd5-111">.NET Framework 2.0 では、すべての値は、"の値は無効になります。 [" が呼び出されるまで、](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)すべての値が有効になります。</span><span class="sxs-lookup"><span data-stu-id="2ddd5-111">In the .NET Framework 2.0, all values are valid until [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called, at which time the values are invalidated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ddd5-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="2ddd5-112">Requirements</span></span>  
 <span data-ttu-id="2ddd5-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ddd5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ddd5-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ddd5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ddd5-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ddd5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ddd5-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ddd5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
