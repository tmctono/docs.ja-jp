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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6d03e760d2b08cd9ee8cdfd85e2e28223aeacd4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747237"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="79317-102">ICorProfilerCallback::RuntimeThreadSuspended メソッド</span><span class="sxs-lookup"><span data-stu-id="79317-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="79317-103">指定したスレッドが中断されているまたは約を中断することをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="79317-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79317-104">構文</span><span class="sxs-lookup"><span data-stu-id="79317-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79317-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="79317-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="79317-106">[in]中断されたスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="79317-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79317-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="79317-107">Remarks</span></span>  
 <span data-ttu-id="79317-108">`RuntimeThreadSuspended`通知の間でいつでも実行できます、 [icorprofilercallback::runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)および関連付けられた[icorprofilercallback::runtimeresumestarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="79317-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="79317-109">間に発生する通知[icorprofilercallback::runtimesuspendfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)と`RuntimeResumeStarted`で実行しているスレッドがアンマネージ コードと、ランタイムに入ったときに中断されたためです。</span><span class="sxs-lookup"><span data-stu-id="79317-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="79317-110">一般に、このコールバックは、スレッドが中断した直後に発生します。</span><span class="sxs-lookup"><span data-stu-id="79317-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="79317-111">ただし、(このコールバックが呼び出されるスレッド) の実行中のスレッドが中断される 1 つである場合は、スレッドを中断する直前のこのコールバックでが発生します。</span><span class="sxs-lookup"><span data-stu-id="79317-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79317-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="79317-112">Requirements</span></span>  
 <span data-ttu-id="79317-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="79317-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79317-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="79317-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="79317-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79317-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79317-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79317-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79317-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="79317-117">See also</span></span>

- [<span data-ttu-id="79317-118">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="79317-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="79317-119">RuntimeThreadResumed メソッド</span><span class="sxs-lookup"><span data-stu-id="79317-119">RuntimeThreadResumed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
