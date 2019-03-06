---
title: ICorProfilerCallback::ThreadDestroyed メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadDestroyed
helpviewer_keywords:
- ThreadDestroyed method [.NET Framework profiling]
- ICorProfilerCallback::ThreadDestroyed method [.NET Framework profiling]
ms.assetid: 4c2b66fd-0595-40a3-8931-f9c4fff97ac8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09c2aef9cc27a2e9aba34f36c1fbfd0973d3b0fa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474229"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="49b6d-102">ICorProfilerCallback::ThreadDestroyed メソッド</span><span class="sxs-lookup"><span data-stu-id="49b6d-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="49b6d-103">スレッドが破棄されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="49b6d-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49b6d-104">構文</span><span class="sxs-lookup"><span data-stu-id="49b6d-104">Syntax</span></span>  
  
```  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49b6d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="49b6d-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="49b6d-106">[in]破棄されているスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="49b6d-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49b6d-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="49b6d-107">Remarks</span></span>  
 <span data-ttu-id="49b6d-108">`threadId`値は、この呼び出しの時点では有効ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="49b6d-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49b6d-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="49b6d-109">Requirements</span></span>  
 <span data-ttu-id="49b6d-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="49b6d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49b6d-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="49b6d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="49b6d-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49b6d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49b6d-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49b6d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49b6d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="49b6d-114">See also</span></span>
- [<span data-ttu-id="49b6d-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="49b6d-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="49b6d-116">ThreadCreated メソッド</span><span class="sxs-lookup"><span data-stu-id="49b6d-116">ThreadCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)
