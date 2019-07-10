---
title: ICorDebugThread::SetDebugState メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread.SetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::SetDebugState
helpviewer_keywords:
- ICorDebugThread::SetDebugState method [.NET Framework debugging]
- SetDebugState method [.NET Framework debugging]
ms.assetid: 6382bdf6-d488-4952-b653-cb09b6e1c6c2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 66f60b2342b6ff64f1329cbe57032291d5139384
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770591"
---
# <a name="icordebugthreadsetdebugstate-method"></a><span data-ttu-id="1f317-102">ICorDebugThread::SetDebugState メソッド</span><span class="sxs-lookup"><span data-stu-id="1f317-102">ICorDebugThread::SetDebugState Method</span></span>
<span data-ttu-id="1f317-103">この ICorDebugThread のデバッグ状態を記述するフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="1f317-103">Sets flags that describe the debugging state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f317-104">構文</span><span class="sxs-lookup"><span data-stu-id="1f317-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f317-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1f317-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="1f317-106">[in]このスレッドのデバッグ状態を指定する CorDebugThreadState 列挙値のビットごとの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="1f317-106">[in] A bitwise combination of CorDebugThreadState enumeration values that specify the debugging state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f317-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="1f317-107">Remarks</span></span>  
 <span data-ttu-id="1f317-108">`SetDebugState` スレッドの現在のデバッグ状態を設定します。</span><span class="sxs-lookup"><span data-stu-id="1f317-108">`SetDebugState` sets the current debug state of the thread.</span></span> <span data-ttu-id="1f317-109">(「現在のデバッグ状態」状態を表しますデバッグ プロセスに続く、実際の現状ではない場合。)通常この値は、THREAD_RUNNING です。</span><span class="sxs-lookup"><span data-stu-id="1f317-109">(The "current debug state" represents the debug state if the process were to be continued, not the actual current state.) The normal value for this is THREAD_RUNNING.</span></span> <span data-ttu-id="1f317-110">デバッガーのみ、スレッドのデバッグ状態に影響を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="1f317-110">Only the debugger can affect the debug state of a thread.</span></span> <span data-ttu-id="1f317-111">デバッグ状態は最終間で継続されるため、複数経由で THREAD_SUSPENDed 継続スレッドを保持する場合は、一度の設定し、その後、それについて心配する必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1f317-111">Debug states do last across continues, so if you want to keep a thread THREAD_SUSPENDed over multiple continues, you can set it once and thereafter not have to worry about it.</span></span> <span data-ttu-id="1f317-112">スレッドの中断とプロセスを再開する可能性があります、デッドロックは通常はほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="1f317-112">Suspending threads and resuming the process can cause deadlocks, though it's usually unlikely.</span></span> <span data-ttu-id="1f317-113">スレッドおよびプロセスの組み込みの品質は、この設計では、します。</span><span class="sxs-lookup"><span data-stu-id="1f317-113">This is an intrinsic quality of threads and processes and is by-design.</span></span> <span data-ttu-id="1f317-114">デバッガーは、非同期的に中断し、デッドロックを中断するスレッドを再開できます。</span><span class="sxs-lookup"><span data-stu-id="1f317-114">A debugger can asynchronously break and resume the threads to break the deadlock.</span></span> <span data-ttu-id="1f317-115">スレッドのユーザーの状態には、USER_UNSAFE_POINT が含まれている場合、スレッドがガベージ コレクション (GC) をブロックします。</span><span class="sxs-lookup"><span data-stu-id="1f317-115">If the thread's user state includes USER_UNSAFE_POINT, then the thread may block a garbage collection (GC).</span></span> <span data-ttu-id="1f317-116">つまり、中断されたスレッドがする可能性が高いデッドロックが発生します。</span><span class="sxs-lookup"><span data-stu-id="1f317-116">This means the suspended thread has a much higher chance of causing a deadlock.</span></span> <span data-ttu-id="1f317-117">これはデバッグ イベントが既にキューに登録には影響可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1f317-117">This may not affect debug events already queued.</span></span> <span data-ttu-id="1f317-118">したがって、デバッガーが全体のイベント キューをドレインする必要があります (呼び出して[icordebugcontroller::hasqueuedcallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) を中断またはスレッドを再開する前にします。</span><span class="sxs-lookup"><span data-stu-id="1f317-118">Thus a debugger should drain the entire event queue (by calling [ICorDebugController::HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) before suspending or resuming threads.</span></span> <span data-ttu-id="1f317-119">それ以外の場合は既に中断されていると確信するスレッドでイベントを取得、可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1f317-119">Else it may get events on a thread that it believes it has already suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f317-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="1f317-120">Requirements</span></span>  
 <span data-ttu-id="1f317-121">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f317-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f317-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f317-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f317-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f317-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f317-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f317-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
