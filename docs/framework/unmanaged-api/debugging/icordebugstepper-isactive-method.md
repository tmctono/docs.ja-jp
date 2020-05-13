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
ms.openlocfilehash: faddf30248b58c68037635480d8977f22ad077d0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379019"
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="5e37a-102">ICorDebugStepper::IsActive メソッド</span><span class="sxs-lookup"><span data-stu-id="5e37a-102">ICorDebugStepper::IsActive Method</span></span>
<span data-ttu-id="5e37a-103">この ICorDebugStepper が現在ステップを実行しているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="5e37a-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e37a-104">構文</span><span class="sxs-lookup"><span data-stu-id="5e37a-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e37a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5e37a-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="5e37a-106">入出力`true`ステッパが現在ステップを実行している場合はを返します。それ以外の場合はを返し `false` ます。</span><span class="sxs-lookup"><span data-stu-id="5e37a-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e37a-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="5e37a-107">Remarks</span></span>  
 <span data-ttu-id="5e37a-108">すべてのステップアクションは、デバッガーが完了していない場合は、次のように[実行](icordebugmanagedcallback-stepcomplete-method.md)されます。この呼び出しは、ステッパを自動的に非アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="5e37a-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="5e37a-109">[ICorDebugStepper::D eactivate](icordebugstepper-deactivate-method.md)を呼び出してコールバック条件に到達する前に、ステッパを途中で非アクティブにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5e37a-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e37a-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="5e37a-110">Requirements</span></span>  
 <span data-ttu-id="5e37a-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e37a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e37a-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e37a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e37a-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e37a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e37a-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e37a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
