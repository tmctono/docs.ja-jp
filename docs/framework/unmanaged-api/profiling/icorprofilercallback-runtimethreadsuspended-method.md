---
title: ICorProfilerCallback::RuntimeThreadSuspended メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadSuspended
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadSuspended
helpviewer_keywords:
- RuntimeThreadSuspended method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeThreadSuspended method [.NET Framework profiling]
ms.assetid: de830a8b-6ee1-4900-ace3-4237108f6b12
topic_type:
- apiref
ms.openlocfilehash: c8645bf828d0ad99bd25c1909cbee3314a11abf9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865871"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="9cf93-102">ICorProfilerCallback::RuntimeThreadSuspended メソッド</span><span class="sxs-lookup"><span data-stu-id="9cf93-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="9cf93-103">指定されたスレッドが中断されたか、中断されようとしていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="9cf93-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cf93-104">構文</span><span class="sxs-lookup"><span data-stu-id="9cf93-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cf93-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9cf93-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="9cf93-106">から中断されたスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="9cf93-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cf93-107">コメント</span><span class="sxs-lookup"><span data-stu-id="9cf93-107">Remarks</span></span>  
 <span data-ttu-id="9cf93-108">`RuntimeThreadSuspended` 通知は、 [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md)と、関連付けられている[ICorProfilerCallback:: RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md)コールバックの間でいつでも発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9cf93-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="9cf93-109">[ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md)と `RuntimeResumeStarted` 間で発生する通知は、アンマネージコードで実行されていて、ランタイムへの入力時に中断されたスレッドに対して行われます。</span><span class="sxs-lookup"><span data-stu-id="9cf93-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="9cf93-110">通常、このコールバックは、スレッドが中断された直後に発生します。</span><span class="sxs-lookup"><span data-stu-id="9cf93-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="9cf93-111">ただし、現在実行中のスレッド (このコールバックを呼び出したスレッド) が中断されているスレッドである場合、このコールバックはスレッドが中断される直前に発生します。</span><span class="sxs-lookup"><span data-stu-id="9cf93-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cf93-112">要件</span><span class="sxs-lookup"><span data-stu-id="9cf93-112">Requirements</span></span>  
 <span data-ttu-id="9cf93-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cf93-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cf93-114">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9cf93-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9cf93-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9cf93-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cf93-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cf93-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cf93-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="9cf93-117">See also</span></span>

- [<span data-ttu-id="9cf93-118">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9cf93-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="9cf93-119">RuntimeThreadResumed メソッド</span><span class="sxs-lookup"><span data-stu-id="9cf93-119">RuntimeThreadResumed Method</span></span>](icorprofilercallback-runtimethreadresumed-method.md)
