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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4166b63e0bb0ae276c48abb961e381809cc9792
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471421"
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="a79d0-102">ICorDebugStepper::IsActive メソッド</span><span class="sxs-lookup"><span data-stu-id="a79d0-102">ICorDebugStepper::IsActive Method</span></span>
<span data-ttu-id="a79d0-103">この ICorDebugStepper が現在の手順を実行中かどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="a79d0-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a79d0-104">構文</span><span class="sxs-lookup"><span data-stu-id="a79d0-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a79d0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a79d0-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="a79d0-106">[out]返します`true`ステッパでは、ステップ; 現在実行している場合を返しますそれ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="a79d0-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a79d0-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="a79d0-107">Remarks</span></span>  
 <span data-ttu-id="a79d0-108">デバッガーが受信するまで、すべてのステップ アクションがアクティブなまま、 [icordebugmanagedcallback::stepcomplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)呼び出すには、ステッパを自動的に非アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="a79d0-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="a79d0-109">ステッパ可能性がありますも非アクティブ化処理の途中で呼び出すことによって[icordebugstepper::deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)状態に達すると、コールバックの前にします。</span><span class="sxs-lookup"><span data-stu-id="a79d0-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a79d0-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="a79d0-110">Requirements</span></span>  
 <span data-ttu-id="a79d0-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a79d0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a79d0-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a79d0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a79d0-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a79d0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a79d0-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a79d0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
