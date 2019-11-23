---
title: ICorProfilerCallback2::HandleDestroyed メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleDestroyed
helpviewer_keywords:
- ICorProfilerCallback2::HandleDestroyed method [.NET Framework profiling]
- HandleDestroyed method [.NET Framework profiling]
ms.assetid: ab4f4bbd-40c7-4667-bfde-60cd73803110
topic_type:
- apiref
ms.openlocfilehash: 2ad1eb765c435244389a671c74026539fa3590cf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439755"
---
# <a name="icorprofilercallback2handledestroyed-method"></a><span data-ttu-id="e50f9-102">ICorProfilerCallback2::HandleDestroyed メソッド</span><span class="sxs-lookup"><span data-stu-id="e50f9-102">ICorProfilerCallback2::HandleDestroyed Method</span></span>
<span data-ttu-id="e50f9-103">Notifies the code profiler that a garbage collection handle has been destroyed.</span><span class="sxs-lookup"><span data-stu-id="e50f9-103">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e50f9-104">構文</span><span class="sxs-lookup"><span data-stu-id="e50f9-104">Syntax</span></span>  
  
```cpp  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e50f9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e50f9-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="e50f9-106">[in] The ID of the handle for the garbage collection.</span><span class="sxs-lookup"><span data-stu-id="e50f9-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e50f9-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="e50f9-107">Requirements</span></span>  
 <span data-ttu-id="e50f9-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e50f9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e50f9-109">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e50f9-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e50f9-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e50f9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e50f9-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e50f9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e50f9-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="e50f9-112">See also</span></span>

- [<span data-ttu-id="e50f9-113">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e50f9-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="e50f9-114">ICorProfilerCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e50f9-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
