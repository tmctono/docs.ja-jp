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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e5fcc9d19a400e23d98a997d051c26af1c1084a3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783020"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="58fe2-102">ICorProfilerCallback::RuntimeResumeStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="58fe2-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="58fe2-103">ランタイムが実行時のすべてのスレッドを再開することをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="58fe2-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58fe2-104">構文</span><span class="sxs-lookup"><span data-stu-id="58fe2-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="58fe2-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="58fe2-105">Requirements</span></span>  
 <span data-ttu-id="58fe2-106">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="58fe2-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58fe2-107">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="58fe2-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="58fe2-108">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58fe2-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58fe2-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58fe2-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58fe2-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="58fe2-110">See also</span></span>

- [<span data-ttu-id="58fe2-111">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="58fe2-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="58fe2-112">RuntimeResumeFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="58fe2-112">RuntimeResumeFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)
