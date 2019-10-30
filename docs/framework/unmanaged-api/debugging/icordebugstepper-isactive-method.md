---
title: ICorDebugStepper::IsActive メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::IsActive method [.NET Framework debugging]
ms.assetid: 8b35e7a9-b40e-40a9-8d8e-b82e823fc575
topic_type:
- apiref
ms.openlocfilehash: a242764710d92e81e8089bc2919734bfac4bcdb2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137571"
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="54f5f-102">ICorDebugStepper::IsActive メソッド</span><span class="sxs-lookup"><span data-stu-id="54f5f-102">ICorDebugStepper::IsActive Method</span></span>
<span data-ttu-id="54f5f-103">この ICorDebugStepper が現在ステップを実行しているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="54f5f-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54f5f-104">構文</span><span class="sxs-lookup"><span data-stu-id="54f5f-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54f5f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="54f5f-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="54f5f-106">入出力ステッパが現在ステップを実行している場合は `true` を返します。それ以外の場合は `false`を返します。</span><span class="sxs-lookup"><span data-stu-id="54f5f-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54f5f-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="54f5f-107">Remarks</span></span>  
 <span data-ttu-id="54f5f-108">すべてのステップアクションは、デバッガーが完了していない場合は、次のように[実行](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)されます。この呼び出しは、ステッパを自動的に非アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="54f5f-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="54f5f-109">[ICorDebugStepper::D eactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)を呼び出してコールバック条件に到達する前に、ステッパを途中で非アクティブにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="54f5f-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54f5f-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="54f5f-110">Requirements</span></span>  
 <span data-ttu-id="54f5f-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54f5f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54f5f-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54f5f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54f5f-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54f5f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54f5f-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54f5f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
