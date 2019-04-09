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
ms.openlocfilehash: 2b163d41280c8ea49554cecb845c4be757f55dfc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168091"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="3e446-102">ICorProfilerCallback::RuntimeResumeStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="3e446-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="3e446-103">ランタイムが実行時のすべてのスレッドを再開することをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="3e446-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e446-104">構文</span><span class="sxs-lookup"><span data-stu-id="3e446-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="3e446-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="3e446-105">Requirements</span></span>  
 <span data-ttu-id="3e446-106">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e446-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e446-107">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3e446-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3e446-108">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e446-108">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3e446-109">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="3e446-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3e446-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e446-110">See also</span></span>

- [<span data-ttu-id="3e446-111">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e446-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="3e446-112">RuntimeResumeFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="3e446-112">RuntimeResumeFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)
