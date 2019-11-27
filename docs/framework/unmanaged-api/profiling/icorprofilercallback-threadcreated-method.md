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
ms.openlocfilehash: 1d8aa231f65bad88806ee9b1d3c5df978c9740a2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446928"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="e4061-102">ICorProfilerCallback::ThreadCreated メソッド</span><span class="sxs-lookup"><span data-stu-id="e4061-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="e4061-103">スレッドが作成されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="e4061-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4061-104">構文</span><span class="sxs-lookup"><span data-stu-id="e4061-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="e4061-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e4061-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="e4061-106">から作成されたスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="e4061-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4061-107">コメント</span><span class="sxs-lookup"><span data-stu-id="e4061-107">Remarks</span></span>  
 <span data-ttu-id="e4061-108">`threadId` 値はすぐに有効になります。</span><span class="sxs-lookup"><span data-stu-id="e4061-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4061-109">要件</span><span class="sxs-lookup"><span data-stu-id="e4061-109">Requirements</span></span>  
 <span data-ttu-id="e4061-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4061-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4061-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e4061-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e4061-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4061-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4061-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4061-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4061-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4061-114">See also</span></span>

- [<span data-ttu-id="e4061-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e4061-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="e4061-116">ThreadDestroyed メソッド</span><span class="sxs-lookup"><span data-stu-id="e4061-116">ThreadDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)
