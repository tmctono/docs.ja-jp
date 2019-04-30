---
title: ICorDebugStepper::Step メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Step
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 444390622ca68244661b91dc85814b05556b12a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994319"
---
# <a name="icordebugstepperstep-method"></a><span data-ttu-id="9cc8c-102">ICorDebugStepper::Step メソッド</span><span class="sxs-lookup"><span data-stu-id="9cc8c-102">ICorDebugStepper::Step Method</span></span>
<span data-ttu-id="9cc8c-103">この icordebugstepper その格納のスレッドと、必要に応じてをシングル ステップ実行するスレッド内で呼び出される関数をシングル ステップ実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="9cc8c-103">Causes this ICorDebugStepper to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cc8c-104">構文</span><span class="sxs-lookup"><span data-stu-id="9cc8c-104">Syntax</span></span>  
  
```  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cc8c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9cc8c-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="9cc8c-106">[in]設定`true`スレッド内で呼び出される関数にステップ インします。</span><span class="sxs-lookup"><span data-stu-id="9cc8c-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="9cc8c-107">設定`false`をステップ オーバー関数。</span><span class="sxs-lookup"><span data-stu-id="9cc8c-107">Set to `false` to step over the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cc8c-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="9cc8c-108">Remarks</span></span>  
 <span data-ttu-id="9cc8c-109">共通言語ランタイムがこのステッパのフレーム内に次のマネージ命令を実行するときに、手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="9cc8c-109">The step completes when the common language runtime performs the next managed instruction in this stepper's frame.</span></span> <span data-ttu-id="9cc8c-110">場合`Step`は、ステッパに対して呼び出すと、マネージ コードのではない、スレッドがマネージ コードの次の命令が実行されたときに、手順は完了します。</span><span class="sxs-lookup"><span data-stu-id="9cc8c-110">If `Step` is called on a stepper, which is not in managed code, the step will complete when the next managed code instruction is executed by the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cc8c-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="9cc8c-111">Requirements</span></span>  
 <span data-ttu-id="9cc8c-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cc8c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cc8c-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9cc8c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9cc8c-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9cc8c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cc8c-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cc8c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
