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
ms.openlocfilehash: 1c7b3c3ea5e976645c265b34327caa38ef6a28fd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914798"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="ba4a8-102">ICorProfilerCallback::RuntimeResumeFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="ba4a8-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="ba4a8-103">ランタイムはランタイムのすべてのスレッドが再開し、通常の操作に返されますが、プロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="ba4a8-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba4a8-104">構文</span><span class="sxs-lookup"><span data-stu-id="ba4a8-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ba4a8-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="ba4a8-105">Remarks</span></span>  
 <span data-ttu-id="ba4a8-106">`RuntimeResumeFinished`コールバックと同じスレッドで発生する保証はありません、 [icorprofilercallback::runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="ba4a8-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="ba4a8-107">ただしと同じスレッドで発生することに保証、 [icorprofilercallback::runtimeresumestarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="ba4a8-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba4a8-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="ba4a8-108">Requirements</span></span>  
 <span data-ttu-id="ba4a8-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba4a8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba4a8-110">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ba4a8-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ba4a8-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba4a8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba4a8-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba4a8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba4a8-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba4a8-113">See also</span></span>

- [<span data-ttu-id="ba4a8-114">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ba4a8-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
