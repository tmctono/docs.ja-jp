---
title: ICorProfilerCallback::ThreadCreated メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadCreated
helpviewer_keywords:
- ICorProfilerCallback::ThreadCreated method [.NET Framework profiling]
- ThreadCreated method [.NET Framework profiling]
ms.assetid: cca0f799-09b8-4689-a33c-6d6537943a9b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c7cd897237539be9bd832a793ad623cf7f31c4b9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747126"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="ec351-102">ICorProfilerCallback::ThreadCreated メソッド</span><span class="sxs-lookup"><span data-stu-id="ec351-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="ec351-103">スレッドが作成されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="ec351-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec351-104">構文</span><span class="sxs-lookup"><span data-stu-id="ec351-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="ec351-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ec351-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="ec351-106">[in]作成されたスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="ec351-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec351-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="ec351-107">Remarks</span></span>  
 <span data-ttu-id="ec351-108">`threadId`値はすぐに有効です。</span><span class="sxs-lookup"><span data-stu-id="ec351-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec351-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="ec351-109">Requirements</span></span>  
 <span data-ttu-id="ec351-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec351-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec351-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ec351-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ec351-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec351-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec351-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec351-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec351-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec351-114">See also</span></span>

- [<span data-ttu-id="ec351-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ec351-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="ec351-116">ThreadDestroyed メソッド</span><span class="sxs-lookup"><span data-stu-id="ec351-116">ThreadDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)
