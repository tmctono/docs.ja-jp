---
title: ICorDebugStepper::SetInterceptMask メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetInterceptMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37b644227a6085352bed682f0ddd7c3455b54895
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760705"
---
# <a name="icordebugsteppersetinterceptmask-method"></a><span data-ttu-id="c9360-102">ICorDebugStepper::SetInterceptMask メソッド</span><span class="sxs-lookup"><span data-stu-id="c9360-102">ICorDebugStepper::SetInterceptMask Method</span></span>
<span data-ttu-id="c9360-103">ステップ インはコードの種類を指定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="c9360-103">Sets a value that specifies the types of code that are stepped into.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9360-104">構文</span><span class="sxs-lookup"><span data-stu-id="c9360-104">Syntax</span></span>  
  
```cpp  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9360-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c9360-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="c9360-106">[in]コードの種類を指定する CorDebugIntercept 列挙型の値の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="c9360-106">[in] A combination of values of the CorDebugIntercept enumeration that specifies the types of code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9360-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="c9360-107">Remarks</span></span>  
 <span data-ttu-id="c9360-108">インターセプターのビットが設定されている場合、特定の種類のコードをインターセプトが発生した場合に、ステッパが終了します。</span><span class="sxs-lookup"><span data-stu-id="c9360-108">If the bit for an interceptor is set, the stepper will complete when the given type of intercepting code is encountered.</span></span> <span data-ttu-id="c9360-109">ビットがオフの場合は傍受のコードはスキップされます。</span><span class="sxs-lookup"><span data-stu-id="c9360-109">If the bit is cleared, the intercepting code will be skipped.</span></span>  
  
 <span data-ttu-id="c9360-110">`SetInterceptMask`メソッドがありますで予期しない相互作用[icordebugstepper::setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (ユーザーの観点から)。</span><span class="sxs-lookup"><span data-stu-id="c9360-110">The `SetInterceptMask` method may have unforeseen interactions with [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (from the user's point of view).</span></span> <span data-ttu-id="c9360-111">たとえば場合、のみ表示されます (は、非内部) クラスの初期化コードの部分にマッピング情報が不足していますと STOP_NO_MAPPING_INFO が設定されていない (を参照してください、 [icordebugstepper::setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)メソッドとCorDebugUnmappedStop 列挙型)、ステッパ、ステップ オーバーはクラスの初期化します。</span><span class="sxs-lookup"><span data-stu-id="c9360-111">For example, if the only visible (that is, non-internal) portion of class initialization code lacks mapping information and STOP_NO_MAPPING_INFO isn't set (see the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method and the CorDebugUnmappedStop enumeration), the stepper will step over the class initialization.</span></span> <span data-ttu-id="c9360-112">既定の INTERCEPT_NONE 値だけで、`CorDebugIntercept`列挙型が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c9360-112">By default, only the INTERCEPT_NONE value of the `CorDebugIntercept` enumeration will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9360-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="c9360-113">Requirements</span></span>  
 <span data-ttu-id="c9360-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9360-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9360-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9360-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9360-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9360-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9360-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9360-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
