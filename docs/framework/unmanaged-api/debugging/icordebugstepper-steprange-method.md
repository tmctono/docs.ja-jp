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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e1ace501bf5de741ea110fe4d3bb4bc44843bf8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760526"
---
# <a name="icordebugsteppersteprange-method"></a><span data-ttu-id="f0bfb-102">ICorDebugStepper::StepRange メソッド</span><span class="sxs-lookup"><span data-stu-id="f0bfb-102">ICorDebugStepper::StepRange Method</span></span>
<span data-ttu-id="f0bfb-103">Icordebugstepper シングル ステップ実行し、その格納のスレッドでは、指定した範囲の最後のタスクを超えるコードに達した場合に返されるを表示します。</span><span class="sxs-lookup"><span data-stu-id="f0bfb-103">Causes this ICorDebugStepper to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0bfb-104">構文</span><span class="sxs-lookup"><span data-stu-id="f0bfb-104">Syntax</span></span>  
  
```cpp  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0bfb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f0bfb-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="f0bfb-106">[in]設定`true`スレッド内で呼び出される関数にステップ インします。</span><span class="sxs-lookup"><span data-stu-id="f0bfb-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="f0bfb-107">設定`false`をステップ オーバー関数。</span><span class="sxs-lookup"><span data-stu-id="f0bfb-107">Set to `false` to step over the function.</span></span>  
  
 `ranges`  
 <span data-ttu-id="f0bfb-108">[in]COR_DEBUG_STEP_RANGE 構造体の範囲を指定の配列。</span><span class="sxs-lookup"><span data-stu-id="f0bfb-108">[in] An array of COR_DEBUG_STEP_RANGE structures, each of which specifies a range.</span></span>  
  
 `cRangeCount`  
 <span data-ttu-id="f0bfb-109">[in] `ranges` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="f0bfb-109">[in] The size of the `ranges` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0bfb-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="f0bfb-110">Remarks</span></span>  
 <span data-ttu-id="f0bfb-111">`StepRange`のような方法は、機能、 [icordebugstepper::step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)メソッドが特定の範囲外のコードまでに完了しないこと以外に到達します。</span><span class="sxs-lookup"><span data-stu-id="f0bfb-111">The `StepRange` method works like the [ICorDebugStepper::Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) method, except that it does not complete until code outside the given range is reached.</span></span>  
  
 <span data-ttu-id="f0bfb-112">これは、一度に 1 つの命令をステップ実行するよりも効率的で指定できます。</span><span class="sxs-lookup"><span data-stu-id="f0bfb-112">This can be more efficient than stepping one instruction at a time.</span></span> <span data-ttu-id="f0bfb-113">範囲は、ステッパのフレームの先頭からのオフセットのペアのリストとして指定します。</span><span class="sxs-lookup"><span data-stu-id="f0bfb-113">Ranges are specified as a list of offset pairs from the start of the stepper's frame.</span></span>  
  
 <span data-ttu-id="f0bfb-114">範囲では、メソッドの Microsoft intermediate language (MSIL) コードに対して相対的です。</span><span class="sxs-lookup"><span data-stu-id="f0bfb-114">Ranges are relative to the Microsoft intermediate language (MSIL) code of a method.</span></span> <span data-ttu-id="f0bfb-115">呼び出す[icordebugstepper::setrangeil](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)で`false`メソッドのネイティブ コードの基準とした範囲にします。</span><span class="sxs-lookup"><span data-stu-id="f0bfb-115">Call [ICorDebugStepper::SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) with `false` to make the ranges relative to the native code of a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0bfb-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="f0bfb-116">Requirements</span></span>  
 <span data-ttu-id="f0bfb-117">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0bfb-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0bfb-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0bfb-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0bfb-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0bfb-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0bfb-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0bfb-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
