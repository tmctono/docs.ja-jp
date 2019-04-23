---
title: ICorProfilerCallback::ExceptionOSHandlerEnter メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerEnter
helpviewer_keywords:
- ExceptionOSHandlerEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerEnter method [.NET Framework profiling]
ms.assetid: 09238b9b-9359-4780-89dc-2f5e4f57920e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1fcdd52e648b2461036921772b6b5684ba6aec22
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175839"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="734ed-102">ICorProfilerCallback::ExceptionOSHandlerEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="734ed-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>
<span data-ttu-id="734ed-103">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="734ed-103">Not implemented.</span></span> <span data-ttu-id="734ed-104">非管理対象の例外情報を必要とするプロファイラーでは、他の手段では、この情報を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="734ed-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="734ed-105">構文</span><span class="sxs-lookup"><span data-stu-id="734ed-105">Syntax</span></span>  
  
```  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="734ed-106">必要条件</span><span class="sxs-lookup"><span data-stu-id="734ed-106">Requirements</span></span>  
 <span data-ttu-id="734ed-107">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="734ed-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="734ed-108">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="734ed-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="734ed-109">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="734ed-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="734ed-110">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="734ed-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="734ed-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="734ed-111">See also</span></span>

- [<span data-ttu-id="734ed-112">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="734ed-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
