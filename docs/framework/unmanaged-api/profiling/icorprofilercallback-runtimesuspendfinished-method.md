---
title: ICorProfilerCallback::RuntimeSuspendFinished メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type:
- apiref
ms.openlocfilehash: 8bad09ddb2b821d0e02d43c1e3d1585b3473ec98
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446963"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="88299-102">ICorProfilerCallback::RuntimeSuspendFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="88299-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>
<span data-ttu-id="88299-103">ランタイムがすべてのランタイムスレッドの中断を完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="88299-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88299-104">構文</span><span class="sxs-lookup"><span data-stu-id="88299-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="88299-105">コメント</span><span class="sxs-lookup"><span data-stu-id="88299-105">Remarks</span></span>  
 <span data-ttu-id="88299-106">アンマネージコード内のすべてのランタイムスレッドは、ランタイムを再入力しようとするまで実行を継続できます。</span><span class="sxs-lookup"><span data-stu-id="88299-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="88299-107">その時点で、ランタイムが再開されるまで中断されます。</span><span class="sxs-lookup"><span data-stu-id="88299-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="88299-108">これは、ランタイムに入る新しいスレッドにも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="88299-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="88299-109">ランタイム内のすべてのスレッドは、割り込み可能なコードに既に存在する場合は直ちに中断されます。または、割り込み可能なコードになると中断するように求められます。</span><span class="sxs-lookup"><span data-stu-id="88299-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="88299-110">`RuntimeSuspendFinished` コールバックは、 [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)コールバックと同じスレッドで行われることが保証されています。</span><span class="sxs-lookup"><span data-stu-id="88299-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88299-111">要件</span><span class="sxs-lookup"><span data-stu-id="88299-111">Requirements</span></span>  
 <span data-ttu-id="88299-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88299-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88299-113">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="88299-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="88299-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88299-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88299-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88299-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88299-116">参照</span><span class="sxs-lookup"><span data-stu-id="88299-116">See also</span></span>

- [<span data-ttu-id="88299-117">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="88299-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="88299-118">RuntimeSuspendAborted メソッド</span><span class="sxs-lookup"><span data-stu-id="88299-118">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
