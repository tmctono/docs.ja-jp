---
title: ICorProfilerCallback::ExceptionSearchCatcherFound メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchCatcherFound
helpviewer_keywords:
- ExceptionSearchCatcherFound method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchCatcherFound method [.NET Framework profiling]
ms.assetid: 190f424d-5e37-4163-a191-0895686e9476
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e41378b314b91f42fca9d1039d3011b5eaafe502
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074301"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="72eca-102">ICorProfilerCallback::ExceptionSearchCatcherFound メソッド</span><span class="sxs-lookup"><span data-stu-id="72eca-102">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>
<span data-ttu-id="72eca-103">例外処理の検索フェーズでスローされた例外のハンドラーが見つかったことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="72eca-103">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72eca-104">構文</span><span class="sxs-lookup"><span data-stu-id="72eca-104">Syntax</span></span>  
  
```  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72eca-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="72eca-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="72eca-106">[in]例外ハンドラーを含む関数の ID。</span><span class="sxs-lookup"><span data-stu-id="72eca-106">[in] The ID of the function that contains the exception handler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72eca-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="72eca-107">Requirements</span></span>  
 <span data-ttu-id="72eca-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="72eca-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72eca-109">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="72eca-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="72eca-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72eca-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="72eca-111">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="72eca-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="72eca-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="72eca-112">See also</span></span>

- [<span data-ttu-id="72eca-113">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="72eca-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
