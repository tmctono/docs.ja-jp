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
ms.openlocfilehash: bd656445c2451d0583ddbc45e71c9e090bb80305
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892776"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a><span data-ttu-id="2c221-102">ICorDebugController::HasQueuedCallbacks メソッド</span><span class="sxs-lookup"><span data-stu-id="2c221-102">ICorDebugController::HasQueuedCallbacks Method</span></span>
<span data-ttu-id="2c221-103">マネージコールバックが、指定されたスレッドに対して現在キューに登録されているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="2c221-103">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c221-104">構文</span><span class="sxs-lookup"><span data-stu-id="2c221-104">Syntax</span></span>  
  
```cpp  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c221-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2c221-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="2c221-106">からスレッドを表す "ツールスレッド" オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2c221-106">[in] A pointer to an "ICorDebugThread" object that represents the thread.</span></span>  
  
 `pbQueued`  
 <span data-ttu-id="2c221-107">入出力マネージコールバックが、指定さ`true`れたスレッドに対して現在キューに格納されている場合は、値を指すポインター。それ以外`false`の場合は。</span><span class="sxs-lookup"><span data-stu-id="2c221-107">[out] A pointer to a value that is `true` if any managed callbacks are currently queued for the specified thread; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="2c221-108">パラメーターに null が指定されて`HasQueuedCallbacks`いる場合`true` 、は、現在マネージコールバックが任意のスレッドに対してキューに置かれている場合、を返します。 `pThread`</span><span class="sxs-lookup"><span data-stu-id="2c221-108">If null is specified for the `pThread` parameter, `HasQueuedCallbacks` will return `true` if there are currently managed callbacks queued for any thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c221-109">解説</span><span class="sxs-lookup"><span data-stu-id="2c221-109">Remarks</span></span>  
 <span data-ttu-id="2c221-110">コールバックは[、次の](icordebugcontroller-continue-method.md)ように表示されるたびに1つずつディスパッチされます。</span><span class="sxs-lookup"><span data-stu-id="2c221-110">Callbacks will be dispatched one at a time, each time [ICorDebugController::Continue](icordebugcontroller-continue-method.md) is called.</span></span> <span data-ttu-id="2c221-111">デバッガーでは、同時に発生する複数のデバッグイベントを報告する場合に、このフラグをチェックできます。</span><span class="sxs-lookup"><span data-stu-id="2c221-111">The debugger can check this flag if it wants to report multiple debugging events that occur simultaneously.</span></span>  
  
 <span data-ttu-id="2c221-112">デバッグイベントがキューに登録されている場合は、既に発生しているため、デバッガーはキュー全体をドレインして、デバッグ対象の状態を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c221-112">When debugging events are queued, they have already occurred, so the debugger must drain the entire queue to be sure of the state of the debuggee.</span></span> <span data-ttu-id="2c221-113">(を`ICorDebugController::Continue`呼び出してキューをドレインします)。たとえば、キューにスレッド*x*の2つのデバッグイベントが含まれており、デバッガーが最初のデバッグイベントの後にスレッド`ICorDebugController::Continue` *x*を中断した後にを呼び出すと、スレッドが中断されていても、スレッド*x*の2番目のデバッグイベントがディスパッチされます。</span><span class="sxs-lookup"><span data-stu-id="2c221-113">(Call `ICorDebugController::Continue` to drain the queue.) For example, if the queue contains two debugging events on thread *X*, and the debugger suspends thread *X* after the first debugging event and then calls `ICorDebugController::Continue`, the second debugging event for thread *X* will be dispatched although the thread has been suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c221-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="2c221-114">Requirements</span></span>  
 <span data-ttu-id="2c221-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c221-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c221-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c221-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c221-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c221-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c221-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c221-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c221-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c221-119">See also</span></span>
