---
title: ICorProfilerCallback::RuntimeResumeStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeResumeStarted method [.NET Framework profiling]
- RuntimeResumeStarted method [.NET Framework profiling]
ms.assetid: 5854bfb2-c568-4f19-904a-7c9d41e7b995
topic_type:
- apiref
ms.openlocfilehash: fe204bbe6154bf3d512a998818cf053d1e96ab3d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433535"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="d06e6-102">ICorProfilerCallback::RuntimeResumeStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="d06e6-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="d06e6-103">ランタイムがすべてのランタイムスレッドを再開していることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d06e6-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d06e6-104">構文</span><span class="sxs-lookup"><span data-stu-id="d06e6-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="d06e6-105">要件</span><span class="sxs-lookup"><span data-stu-id="d06e6-105">Requirements</span></span>  
 <span data-ttu-id="d06e6-106">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d06e6-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d06e6-107">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d06e6-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d06e6-108">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d06e6-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d06e6-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d06e6-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d06e6-110">参照</span><span class="sxs-lookup"><span data-stu-id="d06e6-110">See also</span></span>

- [<span data-ttu-id="d06e6-111">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d06e6-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="d06e6-112">RuntimeResumeFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="d06e6-112">RuntimeResumeFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)
