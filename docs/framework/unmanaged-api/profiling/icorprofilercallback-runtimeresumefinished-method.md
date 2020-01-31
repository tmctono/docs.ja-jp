---
title: ICorProfilerCallback::RuntimeResumeFinished メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeFinished
helpviewer_keywords:
- RuntimeResumeFinished method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeResumeFinished method [.NET Framework profiling]
ms.assetid: 76de0494-dc49-426b-887d-bee98806a982
topic_type:
- apiref
ms.openlocfilehash: 5cafbca75992a5fe8a7d3d95628e0018f1a2e8fa
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865949"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="4f073-102">ICorProfilerCallback::RuntimeResumeFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="4f073-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="4f073-103">ランタイムがすべてのランタイムスレッドを再開し、通常の動作に戻ったことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="4f073-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f073-104">構文</span><span class="sxs-lookup"><span data-stu-id="4f073-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="4f073-105">コメント</span><span class="sxs-lookup"><span data-stu-id="4f073-105">Remarks</span></span>  
 <span data-ttu-id="4f073-106">`RuntimeResumeFinished` コールバックは、 [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md)コールバックと同じスレッドで実行されるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="4f073-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="4f073-107">ただし、 [ICorProfilerCallback:: RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md)コールバックと同じスレッドで発生することは保証されています。</span><span class="sxs-lookup"><span data-stu-id="4f073-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f073-108">要件</span><span class="sxs-lookup"><span data-stu-id="4f073-108">Requirements</span></span>  
 <span data-ttu-id="4f073-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f073-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f073-110">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4f073-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4f073-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f073-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f073-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f073-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f073-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f073-113">See also</span></span>

- [<span data-ttu-id="4f073-114">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4f073-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
