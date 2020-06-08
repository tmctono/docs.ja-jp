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
ms.openlocfilehash: 25a4b101388bfc0151ba7c9c52da6561d48f806b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503160"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="b664d-102">ICorProfilerCallback::ThreadCreated メソッド</span><span class="sxs-lookup"><span data-stu-id="b664d-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="b664d-103">スレッドが作成されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="b664d-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b664d-104">構文</span><span class="sxs-lookup"><span data-stu-id="b664d-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);
```  
  
## <a name="parameters"></a><span data-ttu-id="b664d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b664d-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="b664d-106">から作成されたスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="b664d-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b664d-107">解説</span><span class="sxs-lookup"><span data-stu-id="b664d-107">Remarks</span></span>  
 <span data-ttu-id="b664d-108">この `threadId` 値はすぐに有効です。</span><span class="sxs-lookup"><span data-stu-id="b664d-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b664d-109">要件</span><span class="sxs-lookup"><span data-stu-id="b664d-109">Requirements</span></span>  
 <span data-ttu-id="b664d-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b664d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b664d-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b664d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b664d-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b664d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b664d-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b664d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b664d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b664d-114">See also</span></span>

- [<span data-ttu-id="b664d-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b664d-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="b664d-116">ThreadDestroyed メソッド</span><span class="sxs-lookup"><span data-stu-id="b664d-116">ThreadDestroyed Method</span></span>](icorprofilercallback-threaddestroyed-method.md)
