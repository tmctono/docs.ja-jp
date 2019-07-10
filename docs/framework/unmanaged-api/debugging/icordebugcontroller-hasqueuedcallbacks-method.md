---
title: ICorDebugController::HasQueuedCallbacks メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugController.HasQueuedCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d17f51867b64780fca9b21c5f48c88db36343af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748783"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a><span data-ttu-id="d3d24-102">ICorDebugController::HasQueuedCallbacks メソッド</span><span class="sxs-lookup"><span data-stu-id="d3d24-102">ICorDebugController::HasQueuedCallbacks Method</span></span>
<span data-ttu-id="d3d24-103">任意のマネージ コールバックが、指定されたスレッドの現在キューに登録するかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="d3d24-103">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3d24-104">構文</span><span class="sxs-lookup"><span data-stu-id="d3d24-104">Syntax</span></span>  
  
```cpp  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3d24-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d3d24-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="d3d24-106">[in]スレッドを表す"ICorDebugThread"オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d3d24-106">[in] A pointer to an "ICorDebugThread" object that represents the thread.</span></span>  
  
 `pbQueued`  
 <span data-ttu-id="d3d24-107">[out]ある値へのポインター`true`任意のマネージ コールバックがいると、それ以外の指定したスレッドのキューに置かれた場合は`false`します。</span><span class="sxs-lookup"><span data-stu-id="d3d24-107">[out] A pointer to a value that is `true` if any managed callbacks are currently queued for the specified thread; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="d3d24-108">Null が指定されている場合、`pThread`パラメーター、`HasQueuedCallbacks`戻ります`true`マネージ コールバックのいずれかのスレッド キューに存在している場合。</span><span class="sxs-lookup"><span data-stu-id="d3d24-108">If null is specified for the `pThread` parameter, `HasQueuedCallbacks` will return `true` if there are currently managed callbacks queued for any thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3d24-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="d3d24-109">Remarks</span></span>  
 <span data-ttu-id="d3d24-110">コールバックにディスパッチされる 1 つずつ、毎回なります[icordebugcontroller::continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d3d24-110">Callbacks will be dispatched one at a time, each time [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called.</span></span> <span data-ttu-id="d3d24-111">デバッガーは、同時に発生する複数のデバッグ イベントを報告する必要がある場合、このフラグを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d3d24-111">The debugger can check this flag if it wants to report multiple debugging events that occur simultaneously.</span></span>  
  
 <span data-ttu-id="d3d24-112">デバッグ イベントがキューに置かれたときに、既に発生した、ため、デバッガーがデバッグ対象の状態を必ずキュー全体をドレインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3d24-112">When debugging events are queued, they have already occurred, so the debugger must drain the entire queue to be sure of the state of the debuggee.</span></span> <span data-ttu-id="d3d24-113">(呼び出し`ICorDebugController::Continue`キューをドレインするまでにします)。たとえば、キューには、スレッドで 2 つのデバッグ イベントが含まれている場合*X*、し、デバッガー スレッドを中断します*X*デバッグの最初のイベントと、呼び出しの後に`ICorDebugController::Continue`、2 つ目のデバッグ イベントをスレッド*X*スレッドが中断されたがディスパッチされます。</span><span class="sxs-lookup"><span data-stu-id="d3d24-113">(Call `ICorDebugController::Continue` to drain the queue.) For example, if the queue contains two debugging events on thread *X*, and the debugger suspends thread *X* after the first debugging event and then calls `ICorDebugController::Continue`, the second debugging event for thread *X* will be dispatched although the thread has been suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3d24-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="d3d24-114">Requirements</span></span>  
 <span data-ttu-id="d3d24-115">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3d24-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3d24-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3d24-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3d24-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3d24-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3d24-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3d24-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3d24-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3d24-119">See also</span></span>
