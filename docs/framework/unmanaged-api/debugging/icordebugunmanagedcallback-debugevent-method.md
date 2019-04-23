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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ec45004f5dd87983187690a0a4feefb35b05e85
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183613"
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a><span data-ttu-id="695c7-102">ICorDebugUnmanagedCallback::DebugEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="695c7-102">ICorDebugUnmanagedCallback::DebugEvent Method</span></span>
<span data-ttu-id="695c7-103">ネイティブ イベントが発生したことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="695c7-103">Notifies the debugger that a native event has been fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="695c7-104">構文</span><span class="sxs-lookup"><span data-stu-id="695c7-104">Syntax</span></span>  
  
```  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="695c7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="695c7-105">Parameters</span></span>  
 `pDebugEvent`  
 <span data-ttu-id="695c7-106">[in]ネイティブ イベントへのポインター。</span><span class="sxs-lookup"><span data-stu-id="695c7-106">[in] A pointer to the native event.</span></span>  
  
 `fOutOfBand`  
 <span data-ttu-id="695c7-107">[in]`true`デバッガー呼び出されるまで、非管理対象のイベントの発生後に管理対象プロセスの状態との対話が不可能な場合、 [icordebugcontroller::continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)、それ以外の`false`します。</span><span class="sxs-lookup"><span data-stu-id="695c7-107">[in] `true`, if interaction with the managed process state is impossible after an unmanaged event occurs, until the debugger calls [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md); otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="695c7-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="695c7-108">Remarks</span></span>  
 <span data-ttu-id="695c7-109">デバッグ中のスレッドが Win32 スレッドの場合は、デバッグのインターフェイス、Win32 のメンバーを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="695c7-109">If the thread being debugged is a Win32 thread, do not use any members of the Win32 debugging interface.</span></span> <span data-ttu-id="695c7-110">呼び出すことができます`ICorDebugController::Continue`Win32 スレッドでのみ、および過去の帯域外のイベントを続行するときのみです。</span><span class="sxs-lookup"><span data-stu-id="695c7-110">You can call `ICorDebugController::Continue` only on a Win32 thread and only when continuing past an out-of-band event.</span></span>  
  
 <span data-ttu-id="695c7-111">`DebugEvent`コールバックがコールバックの標準の規則に従っていません。</span><span class="sxs-lookup"><span data-stu-id="695c7-111">The `DebugEvent` callback does not follow the standard rules for callbacks.</span></span> <span data-ttu-id="695c7-112">呼び出すと`DebugEvent`、生のプロセスになる、OS デバッグは停止状態です。</span><span class="sxs-lookup"><span data-stu-id="695c7-112">When you call `DebugEvent`, the process will be in the raw, OS-debug stopped state.</span></span> <span data-ttu-id="695c7-113">プロセスは同期されません。</span><span class="sxs-lookup"><span data-stu-id="695c7-113">The process will not be synchronized.</span></span> <span data-ttu-id="695c7-114">同期完了の状態をそれ以外の入れ子になっている可能性がマネージ コードに関する情報の要求を満たすために必要な場合に自動的に入力`DebugEvent`コールバック。</span><span class="sxs-lookup"><span data-stu-id="695c7-114">It will automatically enter the synchronized state when necessary to satisfy requests for information about managed code, which may result in other nested `DebugEvent` callbacks.</span></span>  
  
 <span data-ttu-id="695c7-115">呼び出す[icordebugprocess::clearcurrentexception](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)プロセスを続行する前に、例外イベントを無視するプロセス。</span><span class="sxs-lookup"><span data-stu-id="695c7-115">Call [ICorDebugProcess::ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) on the process to ignore an exception event before continuing the process.</span></span> <span data-ttu-id="695c7-116">このメソッドを呼び出すと、続行要求で、DBG_EXCEPTION_NOT_HANDLED ではなく DBG_CONTINUE を送信し、帯域外のブレークポイントとシングル ステップの例外を自動的にクリアします。</span><span class="sxs-lookup"><span data-stu-id="695c7-116">Calling this method sends DBG_CONTINUE instead of DBG_EXCEPTION_NOT_HANDLED on the continue request, and automatically clears out-of-band breakpoints and single-step exceptions.</span></span> <span data-ttu-id="695c7-117">帯域外のイベントは、未処理の帯域内イベントが既に存在する場合、デバッグ中のアプリケーションが停止している場合でも、いつでも取得できます。</span><span class="sxs-lookup"><span data-stu-id="695c7-117">Out-of-band events can come at any time, even when the application being debugged appears stopped and when an outstanding in-band event already exists.</span></span>  
  
 <span data-ttu-id="695c7-118">.NET framework version 2.0 では、デバッガーを過去の帯域外のブレークポイント イベント続行すぐにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="695c7-118">In the .NET Framework version 2.0, the debugger should immediately continue past an out-of-band breakpoint event.</span></span> <span data-ttu-id="695c7-119">デバッガーを使用する必要があります、 [icordebugprocess 2::setunmanagedbreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)と[icordebugprocess 2::clearunmanagedbreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)メソッドを追加し、ブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="695c7-119">The debugger should be using the [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) and [ICorDebugProcess2::ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) methods to add and remove breakpoints.</span></span> <span data-ttu-id="695c7-120">これらのメソッドは、帯域外のブレークポイントを自動的にスキップされます。</span><span class="sxs-lookup"><span data-stu-id="695c7-120">These methods will skip over any out-of-band breakpoints automatically.</span></span> <span data-ttu-id="695c7-121">したがって、ディスパッチの帯域外のだけのブレークポイントは Win32 への呼び出しなど、命令ストリーム内に既にある生のブレークポイントをする必要があります`DebugBreak`関数。</span><span class="sxs-lookup"><span data-stu-id="695c7-121">Thus, the only out-of-band breakpoints that get dispatched should be raw breakpoints that are already in the instruction stream, such as a call to the Win32 `DebugBreak` function.</span></span> <span data-ttu-id="695c7-122">使用しないで`ICorDebugProcess::ClearCurrentException`、 [icordebugprocess::getthreadcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)、 [icordebugprocess::setthreadcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)、または他のメンバー、[デバッグ API](../../../../docs/framework/unmanaged-api/debugging/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="695c7-122">Do not try to use `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess::GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess::SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md), or any other member of the [debugging API](../../../../docs/framework/unmanaged-api/debugging/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="695c7-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="695c7-123">Requirements</span></span>  
 <span data-ttu-id="695c7-124">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="695c7-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="695c7-125">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="695c7-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="695c7-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="695c7-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="695c7-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="695c7-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="695c7-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="695c7-128">See also</span></span>

- [<span data-ttu-id="695c7-129">ICorDebugUnmanagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="695c7-129">ICorDebugUnmanagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)
