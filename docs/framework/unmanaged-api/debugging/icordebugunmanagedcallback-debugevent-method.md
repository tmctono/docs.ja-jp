---
title: ICorDebugUnmanagedCallback::DebugEvent メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback.DebugEvent
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback::DebugEvent
helpviewer_keywords:
- DebugEvent method [.NET Framework debugging]
- ICorDebugUnmanagedCallback::DebugEvent method [.NET Framework debugging]
ms.assetid: be9cab04-65ec-44d5-a39a-f90709fdd043
topic_type:
- apiref
ms.openlocfilehash: cb52150a17c9ec8f4bbc25c13b85bce56b221eeb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791192"
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a><span data-ttu-id="8f4eb-102">ICorDebugUnmanagedCallback::DebugEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="8f4eb-102">ICorDebugUnmanagedCallback::DebugEvent Method</span></span>
<span data-ttu-id="8f4eb-103">ネイティブイベントが発生したことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="8f4eb-103">Notifies the debugger that a native event has been fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f4eb-104">構文</span><span class="sxs-lookup"><span data-stu-id="8f4eb-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f4eb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8f4eb-105">Parameters</span></span>  
 `pDebugEvent`  
 <span data-ttu-id="8f4eb-106">からネイティブイベントへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8f4eb-106">[in] A pointer to the native event.</span></span>  
  
 `fOutOfBand`  
 <span data-ttu-id="8f4eb-107">[in] `true`、アンマネージイベントが発生した後にマネージプロセスの状態との対話が不可能な場合は、デバッガーがコード「: Continue」を呼び出す[よう](icordebugcontroller-continue-method.md)にします。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="8f4eb-107">[in] `true`, if interaction with the managed process state is impossible after an unmanaged event occurs, until the debugger calls [ICorDebugController::Continue](icordebugcontroller-continue-method.md); otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f4eb-108">コメント</span><span class="sxs-lookup"><span data-stu-id="8f4eb-108">Remarks</span></span>  
 <span data-ttu-id="8f4eb-109">デバッグ中のスレッドが Win32 スレッドである場合は、Win32 デバッグインターフェイスのメンバーを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="8f4eb-109">If the thread being debugged is a Win32 thread, do not use any members of the Win32 debugging interface.</span></span> <span data-ttu-id="8f4eb-110">`ICorDebugController::Continue` を呼び出すことができるのは、Win32 スレッドだけで、帯域外イベントを継続している場合のみです。</span><span class="sxs-lookup"><span data-stu-id="8f4eb-110">You can call `ICorDebugController::Continue` only on a Win32 thread and only when continuing past an out-of-band event.</span></span>  
  
 <span data-ttu-id="8f4eb-111">`DebugEvent` コールバックは、コールバックの標準規則に従っていません。</span><span class="sxs-lookup"><span data-stu-id="8f4eb-111">The `DebugEvent` callback does not follow the standard rules for callbacks.</span></span> <span data-ttu-id="8f4eb-112">`DebugEvent`を呼び出すと、プロセスは、"生の OS-デバッグが停止しました" 状態になります。</span><span class="sxs-lookup"><span data-stu-id="8f4eb-112">When you call `DebugEvent`, the process will be in the raw, OS-debug stopped state.</span></span> <span data-ttu-id="8f4eb-113">プロセスは同期されません。</span><span class="sxs-lookup"><span data-stu-id="8f4eb-113">The process will not be synchronized.</span></span> <span data-ttu-id="8f4eb-114">マネージコードに関する情報の要求を満たすために必要に応じて、同期状態が自動的に入力されます。これにより、他の入れ子になった `DebugEvent` コールバックが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8f4eb-114">It will automatically enter the synchronized state when necessary to satisfy requests for information about managed code, which may result in other nested `DebugEvent` callbacks.</span></span>  
  
 <span data-ttu-id="8f4eb-115">プロセス[を続行](icordebugprocess-clearcurrentexception-method.md)する前に例外イベントを無視するには、プロセスでを実行します。</span><span class="sxs-lookup"><span data-stu-id="8f4eb-115">Call [ICorDebugProcess::ClearCurrentException](icordebugprocess-clearcurrentexception-method.md) on the process to ignore an exception event before continuing the process.</span></span> <span data-ttu-id="8f4eb-116">このメソッドを呼び出すと、CONTINUE 要求で DBG_EXCEPTION_NOT_HANDLED ではなく DBG_CONTINUE が送信され、帯域外のブレークポイントとシングルステップの例外が自動的にクリアされます。</span><span class="sxs-lookup"><span data-stu-id="8f4eb-116">Calling this method sends DBG_CONTINUE instead of DBG_EXCEPTION_NOT_HANDLED on the continue request, and automatically clears out-of-band breakpoints and single-step exceptions.</span></span> <span data-ttu-id="8f4eb-117">帯域外イベントは、デバッグ中のアプリケーションが停止した場合や、未処理の帯域内イベントが既に存在する場合でも、いつでも発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8f4eb-117">Out-of-band events can come at any time, even when the application being debugged appears stopped and when an outstanding in-band event already exists.</span></span>  
  
 <span data-ttu-id="8f4eb-118">.NET Framework バージョン2.0 では、デバッガーはすぐに帯域外のブレークポイントイベントを終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f4eb-118">In the .NET Framework version 2.0, the debugger should immediately continue past an out-of-band breakpoint event.</span></span> <span data-ttu-id="8f4eb-119">デバッガーでは、 [ICorDebugProcess2:: SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md)メソッドと[ICorDebugProcess2:: ClearUnmanagedBreakpoint](icordebugprocess2-clearunmanagedbreakpoint-method.md)メソッドを使用して、ブレークポイントの追加と削除を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f4eb-119">The debugger should be using the [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md) and [ICorDebugProcess2::ClearUnmanagedBreakpoint](icordebugprocess2-clearunmanagedbreakpoint-method.md) methods to add and remove breakpoints.</span></span> <span data-ttu-id="8f4eb-120">これらのメソッドは、帯域外のブレークポイントを自動的にスキップします。</span><span class="sxs-lookup"><span data-stu-id="8f4eb-120">These methods will skip over any out-of-band breakpoints automatically.</span></span> <span data-ttu-id="8f4eb-121">したがって、ディスパッチされるアウトオブバンドブレークポイントは、Win32 `DebugBreak` 関数の呼び出しなど、既に命令ストリームにある未加工のブレークポイントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f4eb-121">Thus, the only out-of-band breakpoints that get dispatched should be raw breakpoints that are already in the instruction stream, such as a call to the Win32 `DebugBreak` function.</span></span> <span data-ttu-id="8f4eb-122">[デバッグ API](index.md)のその他のメンバーである、`ICorDebugProcess::ClearCurrentException`、の[getthreadcontext](icordebugprocess-getthreadcontext-method.md)、テキスト[処理:: setthreadcontext](icordebugprocess-setthreadcontext-method.md)、またはその他のメンバーを使用しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="8f4eb-122">Do not try to use `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess::GetThreadContext](icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess::SetThreadContext](icordebugprocess-setthreadcontext-method.md), or any other member of the [debugging API](index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f4eb-123">要件</span><span class="sxs-lookup"><span data-stu-id="8f4eb-123">Requirements</span></span>  
 <span data-ttu-id="8f4eb-124">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f4eb-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f4eb-125">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f4eb-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f4eb-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f4eb-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f4eb-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f4eb-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f4eb-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f4eb-128">See also</span></span>

- [<span data-ttu-id="8f4eb-129">ICorDebugUnmanagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f4eb-129">ICorDebugUnmanagedCallback Interface</span></span>](icordebugunmanagedcallback-interface.md)
