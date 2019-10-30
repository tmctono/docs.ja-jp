---
title: ICorDebugStepper::StepRange メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type:
- apiref
ms.openlocfilehash: 2ca4542fe42fab0b5ff54b23b9492d3906698c10
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120621"
---
# <a name="icordebugsteppersteprange-method"></a><span data-ttu-id="4ea5d-102">ICorDebugStepper::StepRange メソッド</span><span class="sxs-lookup"><span data-stu-id="4ea5d-102">ICorDebugStepper::StepRange Method</span></span>
<span data-ttu-id="4ea5d-103">この ICorDebugStepper は、含まれているスレッドを1ステップずつ実行し、指定した範囲の最後のコードに到達したときにを返します。</span><span class="sxs-lookup"><span data-stu-id="4ea5d-103">Causes this ICorDebugStepper to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ea5d-104">構文</span><span class="sxs-lookup"><span data-stu-id="4ea5d-104">Syntax</span></span>  
  
```cpp  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ea5d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4ea5d-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="4ea5d-106">から`true` に設定すると、スレッド内で呼び出される関数にステップインします。</span><span class="sxs-lookup"><span data-stu-id="4ea5d-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="4ea5d-107">関数をステップオーバーするには、`false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="4ea5d-107">Set to `false` to step over the function.</span></span>  
  
 `ranges`  
 <span data-ttu-id="4ea5d-108">からCOR_DEBUG_STEP_RANGE 構造体の配列。それぞれが範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ea5d-108">[in] An array of COR_DEBUG_STEP_RANGE structures, each of which specifies a range.</span></span>  
  
 `cRangeCount`  
 <span data-ttu-id="4ea5d-109">[in] `ranges` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="4ea5d-109">[in] The size of the `ranges` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ea5d-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="4ea5d-110">Remarks</span></span>  
 <span data-ttu-id="4ea5d-111">`StepRange` メソッドは[ICorDebugStepper:: Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)メソッドと同様に機能しますが、指定された範囲外のコードに到達するまでは完了しない点が異なります。</span><span class="sxs-lookup"><span data-stu-id="4ea5d-111">The `StepRange` method works like the [ICorDebugStepper::Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) method, except that it does not complete until code outside the given range is reached.</span></span>  
  
 <span data-ttu-id="4ea5d-112">これは、一度に1つの命令をステップ実行するよりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="4ea5d-112">This can be more efficient than stepping one instruction at a time.</span></span> <span data-ttu-id="4ea5d-113">範囲は、ステッパのフレームの先頭からのオフセットペアのリストとして指定されます。</span><span class="sxs-lookup"><span data-stu-id="4ea5d-113">Ranges are specified as a list of offset pairs from the start of the stepper's frame.</span></span>  
  
 <span data-ttu-id="4ea5d-114">範囲は、メソッドの MSIL (Microsoft 中間言語) コードに対する相対値です。</span><span class="sxs-lookup"><span data-stu-id="4ea5d-114">Ranges are relative to the Microsoft intermediate language (MSIL) code of a method.</span></span> <span data-ttu-id="4ea5d-115">`false` を使用して[ICorDebugStepper:: SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)を呼び出し、メソッドのネイティブコードを基準として範囲を設定します。</span><span class="sxs-lookup"><span data-stu-id="4ea5d-115">Call [ICorDebugStepper::SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) with `false` to make the ranges relative to the native code of a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ea5d-116">［要件］</span><span class="sxs-lookup"><span data-stu-id="4ea5d-116">Requirements</span></span>  
 <span data-ttu-id="4ea5d-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ea5d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ea5d-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ea5d-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ea5d-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ea5d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ea5d-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ea5d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
