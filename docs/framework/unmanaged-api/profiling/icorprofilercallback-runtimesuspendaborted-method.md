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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 62682ca19b9f987370ca11d2bda63fba27f28474
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783001"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="f7d17-102">ICorProfilerCallback::RuntimeSuspendAborted メソッド</span><span class="sxs-lookup"><span data-stu-id="f7d17-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="f7d17-103">ランタイムで発生しているランタイムの中断が中止されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="f7d17-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7d17-104">構文</span><span class="sxs-lookup"><span data-stu-id="f7d17-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="f7d17-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="f7d17-105">Remarks</span></span>  
 <span data-ttu-id="f7d17-106">2 つのスレッドが同時にランタイムの中断を試行した場合は、ランタイムの中断を中止する場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7d17-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="f7d17-107">いずれか、 [icorprofilercallback::runtimesuspendfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)コールバックまたは`RuntimeSuspendAborted`1 つのスレッドの次のコールバックが実行され、 [icorprofilercallback::runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="f7d17-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="f7d17-108">`RuntimeSuspendAborted`コールバックと同じスレッドで発生することが保証されます、`RuntimeSuspendStarted`コールバック。</span><span class="sxs-lookup"><span data-stu-id="f7d17-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7d17-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="f7d17-109">Requirements</span></span>  
 <span data-ttu-id="f7d17-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7d17-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7d17-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f7d17-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f7d17-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7d17-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7d17-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7d17-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7d17-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7d17-114">See also</span></span>

- [<span data-ttu-id="f7d17-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f7d17-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
