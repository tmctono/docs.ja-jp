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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 883e226042225b63097acf731b13abd69cc757ba
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750420"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="a1c64-102">ICorProfilerCallback::RuntimeResumeFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="a1c64-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="a1c64-103">ランタイムはランタイムのすべてのスレッドが再開し、通常の操作に返されますが、プロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="a1c64-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1c64-104">構文</span><span class="sxs-lookup"><span data-stu-id="a1c64-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="a1c64-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="a1c64-105">Remarks</span></span>  
 <span data-ttu-id="a1c64-106">`RuntimeResumeFinished`コールバックと同じスレッドで発生する保証はありません、 [icorprofilercallback::runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="a1c64-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="a1c64-107">ただしと同じスレッドで発生することに保証、 [icorprofilercallback::runtimeresumestarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="a1c64-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1c64-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="a1c64-108">Requirements</span></span>  
 <span data-ttu-id="a1c64-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1c64-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1c64-110">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a1c64-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a1c64-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1c64-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1c64-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1c64-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1c64-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1c64-113">See also</span></span>

- [<span data-ttu-id="a1c64-114">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a1c64-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
