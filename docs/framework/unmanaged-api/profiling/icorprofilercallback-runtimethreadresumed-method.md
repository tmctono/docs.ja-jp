---
title: ICorProfilerCallback::RuntimeThreadResumed メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadResumed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadResumed
helpviewer_keywords:
- ICorProfilerCallback::RuntimeThreadResumed method [.NET Framework profiling]
- RuntimeThreadResumed method [.NET Framework profiling]
ms.assetid: da984f89-4f53-4ab0-ae6f-3e2ee6085994
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 810875d1b91265fe886ce3cd11970cad7fee122d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228862"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="367ea-102">ICorProfilerCallback::RuntimeThreadResumed メソッド</span><span class="sxs-lookup"><span data-stu-id="367ea-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="367ea-103">指定したスレッドが中断された後に再開されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="367ea-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="367ea-104">構文</span><span class="sxs-lookup"><span data-stu-id="367ea-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="367ea-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="367ea-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="367ea-106">[in]再開されているスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="367ea-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="367ea-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="367ea-107">Requirements</span></span>  
 <span data-ttu-id="367ea-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="367ea-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="367ea-109">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="367ea-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="367ea-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="367ea-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="367ea-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="367ea-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="367ea-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="367ea-112">See also</span></span>

- [<span data-ttu-id="367ea-113">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="367ea-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="367ea-114">RuntimeThreadSuspended メソッド</span><span class="sxs-lookup"><span data-stu-id="367ea-114">RuntimeThreadSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)
