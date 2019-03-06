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
ms.openlocfilehash: 5a26faf4f648107e7062a723663877b5b6a8e76e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497159"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="8b1df-102">ICorProfilerCallback::ThreadCreated メソッド</span><span class="sxs-lookup"><span data-stu-id="8b1df-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="8b1df-103">スレッドが作成されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="8b1df-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b1df-104">構文</span><span class="sxs-lookup"><span data-stu-id="8b1df-104">Syntax</span></span>  
  
```  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="8b1df-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8b1df-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="8b1df-106">[in]作成されたスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="8b1df-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b1df-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8b1df-107">Remarks</span></span>  
 <span data-ttu-id="8b1df-108">`threadId`値はすぐに有効です。</span><span class="sxs-lookup"><span data-stu-id="8b1df-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b1df-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="8b1df-109">Requirements</span></span>  
 <span data-ttu-id="8b1df-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b1df-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b1df-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8b1df-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8b1df-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b1df-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b1df-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b1df-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b1df-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b1df-114">See also</span></span>
- [<span data-ttu-id="8b1df-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8b1df-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="8b1df-116">ThreadDestroyed メソッド</span><span class="sxs-lookup"><span data-stu-id="8b1df-116">ThreadDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)
