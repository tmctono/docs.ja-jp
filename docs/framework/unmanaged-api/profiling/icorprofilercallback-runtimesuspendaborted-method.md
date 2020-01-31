---
title: ICorProfilerCallback::RuntimeSuspendAborted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendAborted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted method [.NET Framework profiling]
- RuntimeSuspendAborted method [.NET Framework profiling]
ms.assetid: 5a8a4277-345b-448b-a028-fc8cff9998aa
topic_type:
- apiref
ms.openlocfilehash: 285bdd3f2a96d3c6cb0039382d9944e48c49971a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865910"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="e6861-102">ICorProfilerCallback::RuntimeSuspendAborted メソッド</span><span class="sxs-lookup"><span data-stu-id="e6861-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="e6861-103">実行中のランタイムの中断をランタイムが中止したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="e6861-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6861-104">構文</span><span class="sxs-lookup"><span data-stu-id="e6861-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e6861-105">コメント</span><span class="sxs-lookup"><span data-stu-id="e6861-105">Remarks</span></span>  
 <span data-ttu-id="e6861-106">2つのスレッドが同時にランタイムを中断しようとすると、実行時の中断が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e6861-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="e6861-107">[ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md)コールバックの後に、1つのスレッドで[ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) callback または `RuntimeSuspendAborted` コールバックが発生します。</span><span class="sxs-lookup"><span data-stu-id="e6861-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="e6861-108">`RuntimeSuspendAborted` コールバックは、`RuntimeSuspendStarted` コールバックと同じスレッドで行われることが保証されています。</span><span class="sxs-lookup"><span data-stu-id="e6861-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6861-109">要件</span><span class="sxs-lookup"><span data-stu-id="e6861-109">Requirements</span></span>  
 <span data-ttu-id="e6861-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6861-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6861-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e6861-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e6861-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6861-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6861-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6861-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6861-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6861-114">See also</span></span>

- [<span data-ttu-id="e6861-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6861-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
