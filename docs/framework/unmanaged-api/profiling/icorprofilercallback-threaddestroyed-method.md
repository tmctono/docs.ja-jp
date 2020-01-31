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
ms.openlocfilehash: 07041d06668d474a3d30968fb623854a24ebf0eb
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865819"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="2742c-102">ICorProfilerCallback::ThreadDestroyed メソッド</span><span class="sxs-lookup"><span data-stu-id="2742c-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="2742c-103">スレッドが破棄されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="2742c-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2742c-104">構文</span><span class="sxs-lookup"><span data-stu-id="2742c-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2742c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2742c-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="2742c-106">から破棄されたスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="2742c-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2742c-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="2742c-107">Remarks</span></span>  
 <span data-ttu-id="2742c-108">この呼び出し時に、`threadId` の値は有効ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="2742c-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2742c-109">要件</span><span class="sxs-lookup"><span data-stu-id="2742c-109">Requirements</span></span>  
 <span data-ttu-id="2742c-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2742c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2742c-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2742c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2742c-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2742c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2742c-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2742c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2742c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="2742c-114">See also</span></span>

- [<span data-ttu-id="2742c-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2742c-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="2742c-116">ThreadCreated メソッド</span><span class="sxs-lookup"><span data-stu-id="2742c-116">ThreadCreated Method</span></span>](icorprofilercallback-threadcreated-method.md)
