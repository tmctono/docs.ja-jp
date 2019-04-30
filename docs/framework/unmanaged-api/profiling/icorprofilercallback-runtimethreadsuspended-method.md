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
ms.openlocfilehash: a0748802599926f4ec218362e6f7d086aab2d8f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041744"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="d8c92-102">ICorProfilerCallback::RuntimeThreadSuspended メソッド</span><span class="sxs-lookup"><span data-stu-id="d8c92-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="d8c92-103">指定したスレッドが中断されているまたは約を中断することをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d8c92-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8c92-104">構文</span><span class="sxs-lookup"><span data-stu-id="d8c92-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8c92-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d8c92-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="d8c92-106">[in]中断されたスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="d8c92-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8c92-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="d8c92-107">Remarks</span></span>  
 <span data-ttu-id="d8c92-108">`RuntimeThreadSuspended`通知の間でいつでも実行できます、 [icorprofilercallback::runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)および関連付けられた[icorprofilercallback::runtimeresumestarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="d8c92-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="d8c92-109">間に発生する通知[icorprofilercallback::runtimesuspendfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)と`RuntimeResumeStarted`で実行しているスレッドがアンマネージ コードと、ランタイムに入ったときに中断されたためです。</span><span class="sxs-lookup"><span data-stu-id="d8c92-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="d8c92-110">一般に、このコールバックは、スレッドが中断した直後に発生します。</span><span class="sxs-lookup"><span data-stu-id="d8c92-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="d8c92-111">ただし、(このコールバックが呼び出されるスレッド) の実行中のスレッドが中断される 1 つである場合は、スレッドを中断する直前のこのコールバックでが発生します。</span><span class="sxs-lookup"><span data-stu-id="d8c92-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8c92-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="d8c92-112">Requirements</span></span>  
 <span data-ttu-id="d8c92-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8c92-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8c92-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d8c92-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d8c92-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8c92-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8c92-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8c92-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8c92-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8c92-117">See also</span></span>

- [<span data-ttu-id="d8c92-118">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d8c92-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="d8c92-119">RuntimeThreadResumed メソッド</span><span class="sxs-lookup"><span data-stu-id="d8c92-119">RuntimeThreadResumed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
