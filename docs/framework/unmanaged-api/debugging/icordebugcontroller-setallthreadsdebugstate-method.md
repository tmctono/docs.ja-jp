---
title: ICorDebugController::SetAllThreadsDebugState メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugController.SetAllThreadsDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9348652129a3357784654006dc16d822298f28f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749963"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="b2518-102">ICorDebugController::SetAllThreadsDebugState メソッド</span><span class="sxs-lookup"><span data-stu-id="b2518-102">ICorDebugController::SetAllThreadsDebugState Method</span></span>
<span data-ttu-id="b2518-103">プロセス内のすべてのマネージ スレッドのデバッグ状態を設定します。</span><span class="sxs-lookup"><span data-stu-id="b2518-103">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2518-104">構文</span><span class="sxs-lookup"><span data-stu-id="b2518-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2518-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b2518-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="b2518-106">[in]デバッグのスレッドの状態を指定する"CorDebugThreadState"列挙型の値。</span><span class="sxs-lookup"><span data-stu-id="b2518-106">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="b2518-107">[in]デバッグの状態設定から除外するスレッドを表す"ICorDebugThread"オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b2518-107">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="b2518-108">この値が null の場合は、反映されないスレッドはありません。</span><span class="sxs-lookup"><span data-stu-id="b2518-108">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2518-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="b2518-109">Remarks</span></span>  
 <span data-ttu-id="b2518-110">`SetAllThreadsDebugState`メソッドを使用して表示されていないスレッドに影響する可能性[EnumerateThreads メソッド](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)、そのスレッドで中断された、`SetAllThreadsDebugState`メソッドを再開する必要があります、`SetAllThreadsDebugState`メソッド。</span><span class="sxs-lookup"><span data-stu-id="b2518-110">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2518-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="b2518-111">Requirements</span></span>  
 <span data-ttu-id="b2518-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2518-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2518-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2518-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2518-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2518-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2518-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2518-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2518-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2518-116">See also</span></span>
