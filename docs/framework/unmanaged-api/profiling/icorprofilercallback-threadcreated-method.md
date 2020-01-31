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
ms.openlocfilehash: 6514606290bf006443d7011c1a428bebb4cca0f6
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865832"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="0018f-102">ICorProfilerCallback::ThreadCreated メソッド</span><span class="sxs-lookup"><span data-stu-id="0018f-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="0018f-103">スレッドが作成されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="0018f-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0018f-104">構文</span><span class="sxs-lookup"><span data-stu-id="0018f-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="0018f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0018f-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="0018f-106">から作成されたスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="0018f-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0018f-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="0018f-107">Remarks</span></span>  
 <span data-ttu-id="0018f-108">`threadId` 値はすぐに有効になります。</span><span class="sxs-lookup"><span data-stu-id="0018f-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0018f-109">要件</span><span class="sxs-lookup"><span data-stu-id="0018f-109">Requirements</span></span>  
 <span data-ttu-id="0018f-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0018f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0018f-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0018f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0018f-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0018f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0018f-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0018f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0018f-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="0018f-114">See also</span></span>

- [<span data-ttu-id="0018f-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0018f-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="0018f-116">ThreadDestroyed メソッド</span><span class="sxs-lookup"><span data-stu-id="0018f-116">ThreadDestroyed Method</span></span>](icorprofilercallback-threaddestroyed-method.md)
