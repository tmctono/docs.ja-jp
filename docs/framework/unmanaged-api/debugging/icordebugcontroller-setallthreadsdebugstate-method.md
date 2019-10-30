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
ms.openlocfilehash: 1190f83e2671216cf1627eeb710ba576e4b2ec93
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125355"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="dcec1-102">ICorDebugController::SetAllThreadsDebugState メソッド</span><span class="sxs-lookup"><span data-stu-id="dcec1-102">ICorDebugController::SetAllThreadsDebugState Method</span></span>
<span data-ttu-id="dcec1-103">プロセス内のすべてのマネージスレッドのデバッグ状態を設定します。</span><span class="sxs-lookup"><span data-stu-id="dcec1-103">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcec1-104">構文</span><span class="sxs-lookup"><span data-stu-id="dcec1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcec1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dcec1-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="dcec1-106">からデバッグ用のスレッドの状態を指定する "CorDebugThreadState" 列挙の値。</span><span class="sxs-lookup"><span data-stu-id="dcec1-106">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="dcec1-107">からデバッグ状態設定から除外されるスレッドを表す "のスレッド" オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="dcec1-107">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="dcec1-108">この値が null の場合、スレッドは除外されません。</span><span class="sxs-lookup"><span data-stu-id="dcec1-108">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcec1-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="dcec1-109">Remarks</span></span>  
 <span data-ttu-id="dcec1-110">`SetAllThreadsDebugState` メソッドは、 [EnumerateThreads メソッド](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)によって表示されないスレッドに影響を与える可能性があります。そのため、`SetAllThreadsDebugState` メソッドで中断されたスレッドは、`SetAllThreadsDebugState` メソッドを使用して再開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcec1-110">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcec1-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="dcec1-111">Requirements</span></span>  
 <span data-ttu-id="dcec1-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcec1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcec1-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dcec1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dcec1-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcec1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcec1-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcec1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcec1-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="dcec1-116">See also</span></span>
